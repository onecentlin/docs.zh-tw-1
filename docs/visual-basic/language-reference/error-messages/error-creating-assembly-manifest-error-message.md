---
title: "建立組件資訊清單時發生錯誤：&lt;錯誤訊息&gt;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5e88d28ef787eb57b71d94f4ee51c09e9751dbff
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a>建立組件資訊清單時發生錯誤：&lt;錯誤訊息&gt;
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 編譯器呼叫組件連結器 (Al.exe，也稱為 Alink) 使用資訊清單產生組件。 連結器在建立組件的前置發出階段回報了錯誤。  
  
 如果指定的金鑰檔或金鑰容器有問題，便可能發生此情形。 若要完全簽署組件，您必須提供有效的金鑰檔，其中包含公開和私密金鑰的相關資訊。 若要延遲簽署組件，您必須選取 [僅延遲簽署] 核取方塊，並提供有效的金鑰檔，其中包含公開金鑰資訊的相關資訊。 延遲簽署組件時不需要私密金鑰。 如需詳細資訊，請參閱[如何：使用強式名稱簽署組件](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)。  
  
 **錯誤 ID:** BC30140  
  
## <a name="to-correct-this-error"></a>更正這個錯誤  
  
1.  請檢查引用的錯誤訊息，請參閱主題[Al.exe](../../../framework/tools/al-exe-assembly-linker.md)。 以錯誤 AL1019 進一步說明和建議  
  
2.  如果錯誤持續發生，請收集情況的相關資訊，並通知 Microsoft 產品支援服務。  
  
## <a name="see-also"></a>請參閱  
 [如何：使用強式名稱簽署組件](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [專案設計工具、簽署頁面](/visualstudio/ide/reference/signing-page-project-designer)  
 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)。  
 [告訴我們](/visualstudio/ide/talk-to-us)
