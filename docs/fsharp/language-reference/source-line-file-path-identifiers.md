---
title: "原始碼程式行、檔案與路徑識別項 (F#)"
description: "了解如何使用內建 F # 識別碼的值可讓您存取原始程式碼行號、 目錄和檔案名稱，在程式碼中。"
keywords: "Visual F#, F#, 函式程式設計"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4cfe7439-275c-4d08-980b-784e240bbf29
ms.openlocfilehash: 44cc0914226c120f2b877ce3decd25caa6817eec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="source-line-file-and-path-identifiers"></a><span data-ttu-id="f5b2c-104">原始碼程式行、檔案與路徑識別項</span><span class="sxs-lookup"><span data-stu-id="f5b2c-104">Source Line, File, and Path Identifiers</span></span>

<span data-ttu-id="f5b2c-105">識別項`__LINE__`，`__SOURCE_DIRECTORY__`和`__SOURCE_FILE__`是內建可讓您存取您的程式碼的來源行號、 目錄和檔案名稱的值。</span><span class="sxs-lookup"><span data-stu-id="f5b2c-105">The identifiers `__LINE__`, `__SOURCE_DIRECTORY__` and `__SOURCE_FILE__` are built-in values that enable you to access the source line number, directory and file name in your code.</span></span>


## <a name="syntax"></a><span data-ttu-id="f5b2c-106">語法</span><span class="sxs-lookup"><span data-stu-id="f5b2c-106">Syntax</span></span>

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a><span data-ttu-id="f5b2c-107">備註</span><span class="sxs-lookup"><span data-stu-id="f5b2c-107">Remarks</span></span>
<span data-ttu-id="f5b2c-108">每個這些值都有類型`string`。</span><span class="sxs-lookup"><span data-stu-id="f5b2c-108">Each of these values has type `string`.</span></span>

<span data-ttu-id="f5b2c-109">下表摘要說明原始程式行、 檔案和 F # 中可用的路徑識別項。</span><span class="sxs-lookup"><span data-stu-id="f5b2c-109">The following table summarizes the source line, file, and path identifiers that are available in F#.</span></span> <span data-ttu-id="f5b2c-110">這些識別項不是前置處理器巨集;它們是編譯器可辨識的內建值。</span><span class="sxs-lookup"><span data-stu-id="f5b2c-110">These identifiers are not preprocessor macros; they are built-in values that are recognized by the compiler.</span></span>

|<span data-ttu-id="f5b2c-111">預先定義的識別項</span><span class="sxs-lookup"><span data-stu-id="f5b2c-111">Predefined identifier</span></span>|<span data-ttu-id="f5b2c-112">說明</span><span class="sxs-lookup"><span data-stu-id="f5b2c-112">Description</span></span>|
|---------------------|-----------|
|`__LINE__`|<span data-ttu-id="f5b2c-113">判斷值為目前的行號，考慮`#line`指示詞。</span><span class="sxs-lookup"><span data-stu-id="f5b2c-113">Evaluates to the current line number, considering `#line` directives.</span></span>|
|`__SOURCE_DIRECTORY__`|<span data-ttu-id="f5b2c-114">評估目前的完整路徑的來源目錄中，為考慮`#line`指示詞。</span><span class="sxs-lookup"><span data-stu-id="f5b2c-114">Evaluates to the current full path of the source directory, considering `#line` directives.</span></span>|
|`__SOURCE_FILE__`|<span data-ttu-id="f5b2c-115">判斷值為目前的來源檔案名稱和其路徑中，考慮`#line`指示詞。</span><span class="sxs-lookup"><span data-stu-id="f5b2c-115">Evaluates to the current source file name and its path, considering `#line` directives.</span></span>|
<span data-ttu-id="f5b2c-116">如需有關`#line`指示詞，請參閱[編譯器指示詞](compiler-directives.md)。</span><span class="sxs-lookup"><span data-stu-id="f5b2c-116">For more information about the `#line` directive, see [Compiler Directives](compiler-directives.md).</span></span>

## <a name="example"></a><span data-ttu-id="f5b2c-117">範例</span><span class="sxs-lookup"><span data-stu-id="f5b2c-117">Example</span></span>

<span data-ttu-id="f5b2c-118">下列程式碼範例示範如何使用這些值。</span><span class="sxs-lookup"><span data-stu-id="f5b2c-118">The following code example demonstrates the use of these values.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

<span data-ttu-id="f5b2c-119">輸出：</span><span class="sxs-lookup"><span data-stu-id="f5b2c-119">Output:</span></span>

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo\Program.fs
```

## <a name="see-also"></a><span data-ttu-id="f5b2c-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f5b2c-120">See Also</span></span>
[<span data-ttu-id="f5b2c-121">編譯器指示詞</span><span class="sxs-lookup"><span data-stu-id="f5b2c-121">Compiler Directives</span></span>](compiler-directives.md)

[<span data-ttu-id="f5b2c-122">F# 語言參考</span><span class="sxs-lookup"><span data-stu-id="f5b2c-122">F# Language Reference</span></span>](index.md)