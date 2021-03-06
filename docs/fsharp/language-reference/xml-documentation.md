---
title: "XML 文件 (F#)"
description: "從註解產生文件，以了解 F # 中的支援。"
keywords: "Visual F#, F#, 函式程式設計"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: d99ab1b6-e170-4ec2-a543-43ea7ab15bb2
ms.openlocfilehash: 20768a7d4ea17c926318043f658691819a3d7d2f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="xml-documentation"></a>XML 文件

您可以產生三斜線 （/ /） 文件註解 F # 中的程式碼。 XML 註解可以在程式碼檔 (.fs) 或簽章 (.fsi) 檔案中的宣告之前。


## <a name="generating-documentation-from-comments"></a>從註解產生文件
相同內其他.NET Framework 語言的支援 F # 中產生文件從註解。 如同其他.NET Framework 語言， [-doc 編譯器選項](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04)可讓您產生 XML 檔案，其中包含您可以使用 Sandcastle 之類的工具來轉換文件的資訊。 組件的語言所撰寫的其他.NET Framework 通常用於使用所設計的工具所產生的文件產生 Api 為基礎的 F # 建構的編譯形式的檢視。 除非工具是專門為了支援 F #，這些工具所產生的文件不符合應用程式開發介面 F # 檢視。

如需如何從 XML 產生文件的詳細資訊，請參閱[XML 文件註解 &#40;& #35。程式設計手冊 &#41;](https://msdn.microsoft.com/library/b2s063f7).


## <a name="recommended-tags"></a>建議的標記
有兩種方式，撰寫 XML 文件註解。 其中一個是剛撰寫的文件直接在三斜線註解，而不使用 XML 標記。 如果您這麼做時，整個註解文字會被視為緊接在後面的程式碼建構的摘要文件。 當您想要撰寫的簡短摘要每個建構時，請使用這個方法。 另一個方法是用來提供更多結構化文件的 XML 標記。 第二種方法可讓您指定個別的附註的簡短摘要、 其他註解、 文件集的每個參數和型別參數和擲回的例外狀況和傳回值的描述。 下表說明在 F # XML 程式碼註解中才能辨識的 XML 標記。



|標記語法|說明|
|----------|-----------|
|**&lt;c&gt;***文字***&lt;/c&gt;**|指定*文字*是程式碼。 這個標記可以供文件產生器，來顯示文字的字型，適用於程式碼。|
|**&lt;摘要&gt;***文字* **&lt; /摘要&gt;**|指定*文字*程式項目的簡短描述。 描述通常是一個或兩個句子。|
|**&lt;註解&gt;***文字* **&lt; /註解&gt;**|指定*文字*包含補充資訊的程式項目。|
|**&lt;name ="***名稱***"&gt;***描述***&lt;/param&gt;**|指定的名稱和函式或方法參數的描述。|
|**&lt;typeparam 名稱 ="***名稱***"&gt;***描述***&lt;/typeparam&gt;**|指定的名稱和型別參數的描述。|
|**&lt;傳回&gt;***文字* **&lt; /returns>&gt;**|指定*文字*描述函式或方法的傳回值。|
|**&lt;例外狀況 cref ="***類型***"&gt;***描述***&lt;/exception&gt;**|指定可以產生的例外狀況的情況下擲回的類型。|
|**&lt;cref ="***參考***"&gt;***文字* **&lt; /請參閱&gt;**|指定的內嵌連結，另一個程式項目。 *參考*是它會出現在 XML 文件檔的名稱。 *文字*是連結中所顯示的文字。|
|**&lt;另請參閱 cref ="***參考***"/&gt;**|指定另一種類型的文件的 < 另請參閱連結。 *參考*是它會出現在 XML 文件檔的名稱。 另請參閱通常會出現在文件頁面底部的連結。|
|**&lt;para&gt;***文字***&lt;/para&gt;**|指定一段文字。 這用來分隔文字內**備註**標記。|

## <a name="example"></a>範例

### <a name="description"></a>描述
以下是典型的 XML 文件註解，簽章檔案中。


### <a name="code"></a>程式碼
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7101.fs)]
    
## <a name="example"></a>範例

### <a name="description"></a>描述
下列範例顯示的替代方法，沒有 XML 標記。 在此範例中，註解中的整個文字會被視為摘要。 請注意，如果您未明確指定摘要的標記，您不應該指定其他的標籤，例如**param**或**傳回**標記。


### <a name="code"></a>程式碼
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7102.fs)]
    
## <a name="see-also"></a>另請參閱
[F# 語言參考](index.md)

[編譯器選項](compiler-options.md)
