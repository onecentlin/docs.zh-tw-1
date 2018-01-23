---
title: "使用 .NET Compiler Platform SDK 工作區模型"
description: "此概觀可讓您了解用來查詢與管理程式碼之工作區和專案的類型。"
author: billwagner
ms.author: wiwagn
ms.date: 10/15/2017
ms.topic: conceptual
ms.prod: .net
ms.devlang: devlang-csharp
ms.custom: mvc
ms.openlocfilehash: d0d4e9c012b025b9393ac34f0833795fca9841d5
ms.sourcegitcommit: d095094e942eedf09530ea5636fbaf9029853027
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2017
---
# <a name="work-with-a-workspace"></a><span data-ttu-id="12a66-103">使用工作區</span><span class="sxs-lookup"><span data-stu-id="12a66-103">Work with a workspace</span></span>

<span data-ttu-id="12a66-104">[工作區] 層是執行程式碼分析以及重構整個方案的起點。</span><span class="sxs-lookup"><span data-stu-id="12a66-104">The **Workspaces** layer is the starting point for doing code analysis and refactoring over entire solutions.</span></span> <span data-ttu-id="12a66-105">在這層內，工作區 API 可協助您將方案中的所有專案資訊都組織成單一物件模型，以讓您直接存取原始程式文字、語法樹狀結構、語意模型和編譯這類編譯器層物件模型，而不需要剖析檔案、設定選項，或管理專案間相依性。</span><span class="sxs-lookup"><span data-stu-id="12a66-105">Within this layer, the Workspace API assists you in organizing all the information about the projects in a solution into a single object model, offering you direct access to compiler layer object models like source text, syntax trees, semantic models, and compilations without needing to parse files, configure options, or manage inter-project dependencies.</span></span> 

<span data-ttu-id="12a66-106">IDE 這類主機環境為您提供對應至開啟方案的工作區。</span><span class="sxs-lookup"><span data-stu-id="12a66-106">Host environments, like an IDE, provide a workspace for you corresponding to the open solution.</span></span> <span data-ttu-id="12a66-107">只要載入方案檔，也可以在 IDE 外部使用此模型。</span><span class="sxs-lookup"><span data-stu-id="12a66-107">It is also possible to use this model outside of an IDE by simply loading a solution file.</span></span>

## <a name="workspace"></a><span data-ttu-id="12a66-108">工作區</span><span class="sxs-lookup"><span data-stu-id="12a66-108">Workspace</span></span>

<span data-ttu-id="12a66-109">工作區會主動將方案呈現為專案集合，且每個專案都有文件集合。</span><span class="sxs-lookup"><span data-stu-id="12a66-109">A workspace is an active representation of your solution as a collection of projects, each with a collection of documents.</span></span> <span data-ttu-id="12a66-110">工作區通常會繫結至在使用者鍵入或管理屬性時不斷變更的主機環境。</span><span class="sxs-lookup"><span data-stu-id="12a66-110">A workspace is typically tied to a host environment that is constantly changing as a user types or manipulates properties.</span></span> 

<span data-ttu-id="12a66-111"><xref:Microsoft.CodeAnalysis.Workspace> 可以存取方案的目前模型。</span><span class="sxs-lookup"><span data-stu-id="12a66-111">The <xref:Microsoft.CodeAnalysis.Workspace> provides access to the current model of the solution.</span></span> <span data-ttu-id="12a66-112">主機環境變更時，工作區會引發對應事件，並更新 <xref:Microsoft.CodeAnalysis.Workspace.CurrentSolution?displayProperty=nameWithType> 屬性。</span><span class="sxs-lookup"><span data-stu-id="12a66-112">When a change in the host environment occurs, the workspace fires corresponding events, and the <xref:Microsoft.CodeAnalysis.Workspace.CurrentSolution?displayProperty=nameWithType> property is updated.</span></span> <span data-ttu-id="12a66-113">例如，使用者在文字編輯器中鍵入以對應至其中一個來源文件時，工作區會使用事件來發出訊號：方案的整體模型已變更以及已修改的文件。</span><span class="sxs-lookup"><span data-stu-id="12a66-113">For example, when the user types in a text editor corresponding to one of the source documents, the workspace uses an event to signal that the overall model of the solution has changed and which document was modified.</span></span> <span data-ttu-id="12a66-114">您接著可以分析新模型的正確性、反白顯示精確度區域，或者對程式碼變更進行建議來回應這些變更。</span><span class="sxs-lookup"><span data-stu-id="12a66-114">You can then react to those changes by analyzing the new model for correctness, highlighting areas of significance, or making a suggestion for a code change.</span></span> 

<span data-ttu-id="12a66-115">您也可以建立獨立工作區，而獨立工作區與主機環境中斷連線，或用於沒有主機環境的應用程式中。</span><span class="sxs-lookup"><span data-stu-id="12a66-115">You can also create stand-alone workspaces that are disconnected from the host environment or used in an application that has no host environment.</span></span>

## <a name="solutions-projects-documents"></a><span data-ttu-id="12a66-116">方案, 專案, 文件</span><span class="sxs-lookup"><span data-stu-id="12a66-116">Solutions, projects, documents</span></span>

<span data-ttu-id="12a66-117">雖然每次按下按鍵時都可能變更工作區，但是您可以分開使用方案的模型。</span><span class="sxs-lookup"><span data-stu-id="12a66-117">Although a workspace may change every time a key is pressed, you can work with the model of the solution in isolation.</span></span> 

<span data-ttu-id="12a66-118">方案是專案和文件的不可變模型。</span><span class="sxs-lookup"><span data-stu-id="12a66-118">A solution is an immutable model of the projects and documents.</span></span> <span data-ttu-id="12a66-119">這表示可以共用模型，而不鎖定或重複。</span><span class="sxs-lookup"><span data-stu-id="12a66-119">This means that the model can be shared without locking or duplication.</span></span> <span data-ttu-id="12a66-120">從 <xref:Microsoft.CodeAnalysis.Workspace.CurrentSolution?displayProperty=nameWithType> 屬性取得方案執行個體之後，該執行個體將永遠不會變更。</span><span class="sxs-lookup"><span data-stu-id="12a66-120">After you obtain a solution instance from the <xref:Microsoft.CodeAnalysis.Workspace.CurrentSolution?displayProperty=nameWithType> property, that instance will never change.</span></span> <span data-ttu-id="12a66-121">不過，像是語法樹狀結構和編譯，您可以根據現有方案和特定變更來建構新執行個體以修改方案。</span><span class="sxs-lookup"><span data-stu-id="12a66-121">However, like with syntax trees and compilations, you can modify solutions by constructing new instances based on existing solutions and specific changes.</span></span> <span data-ttu-id="12a66-122">若要取得工作區以反映變更，則必須將已變更的方案明確地套用回工作區。</span><span class="sxs-lookup"><span data-stu-id="12a66-122">To get the workspace to reflect your changes, you must explicitly apply the changed solution back to the workspace.</span></span>

<span data-ttu-id="12a66-123">專案是整體不可變方案模型的一部分。</span><span class="sxs-lookup"><span data-stu-id="12a66-123">A project is a part of the overall immutable solution model.</span></span> <span data-ttu-id="12a66-124">它代表所有原始程式碼文件、剖析和編譯選項，以及組件和專案對專案參考。</span><span class="sxs-lookup"><span data-stu-id="12a66-124">It represents all the source code documents, parse and compilation options, and both assembly and project-to-project references.</span></span> <span data-ttu-id="12a66-125">在專案中，您可以存取對應編譯，而不需要判斷專案相依性，或是剖析任何原始程式檔。</span><span class="sxs-lookup"><span data-stu-id="12a66-125">From a project, you can access the corresponding compilation without needing to determine project dependencies or parse any source files.</span></span>

<span data-ttu-id="12a66-126">文件也是整體不可變方案模型的一部分。</span><span class="sxs-lookup"><span data-stu-id="12a66-126">A document is also a part of the overall immutable solution model.</span></span> <span data-ttu-id="12a66-127">文件代表單一原始程式檔，您可以從中存取檔案、語法樹狀結構和語意模型的文字。</span><span class="sxs-lookup"><span data-stu-id="12a66-127">A document represents a single source file from which you can access the text of the file, the syntax tree, and the semantic model.</span></span>

<span data-ttu-id="12a66-128">下圖呈現工作區與主機環境的關係、工具，以及如何進行編輯。</span><span class="sxs-lookup"><span data-stu-id="12a66-128">The following diagram is a representation of how the Workspace relates to the host environment, tools, and how edits are made.</span></span>

![包含專案和原始程式檔之工作區不同項目間的關聯性](media/workspace-obj-relations.png)

## <a name="summary"></a><span data-ttu-id="12a66-130">總結</span><span class="sxs-lookup"><span data-stu-id="12a66-130">Summary</span></span>

<span data-ttu-id="12a66-131">Roslyn 會公開一組編譯器 API 和工作區 API，以提供您原始程式碼的豐富資訊，並且使用 C# 和 Visual Basic 語言也完全不失真。</span><span class="sxs-lookup"><span data-stu-id="12a66-131">Roslyn exposes a set of compiler APIs and Workspaces APIs that provides rich information about your source code and that has full fidelity with the C# and Visual Basic languages.</span></span>  <span data-ttu-id="12a66-132">.NET Compiler Platform SDK 可大幅降低建立以程式碼為中心之工具和應用程式的入門障礙。</span><span class="sxs-lookup"><span data-stu-id="12a66-132">The .NET Compiler Platform SDK dramatically lowers the barrier to entry for creating code-focused tools and applications.</span></span> <span data-ttu-id="12a66-133">它在多個領域中創造了許多創新的機會，例如中繼程式設計、程式碼產生和轉換、C# 和 VB 語言的交互使用，以及在網域特定語言中內嵌 C# 和 VB。</span><span class="sxs-lookup"><span data-stu-id="12a66-133">It creates many opportunities for innovation in areas such as meta-programming, code generation and transformation, interactive use of the C# and VB languages, and embedding of C# and VB in domain specific languages.</span></span>  