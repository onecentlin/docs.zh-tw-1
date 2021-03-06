---
title: "延後的執行範例 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a22bea1-c755-4aac-800a-fcd9e5107ace
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a4d2146901d9282b0df706b483afef79f714f660
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="deferred-execution-example-visual-basic"></a>延後的執行範例 (Visual Basic)
本主題顯示延後執行與延遲評估如何影響您 LINQ to XML 查詢的執行。  
  
## <a name="example"></a>範例  
 下列範例顯示利用使用延後執行的擴充方法時的執行順序。 此範例會宣告三個字串的陣列。 接著，它會逐一查看 `ConvertCollectionToUpperCase` 所傳回的集合。  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module Module1  
  
    <Extension()>  
    Private Iterator Function ConvertCollectionToUpperCase(  
    ByVal source As IEnumerable(Of String)) _  
    As IEnumerable(Of String)   
        For Each str As String In source  
            Console.WriteLine("ToUpper: source {0}", str)   
            Yield str.ToUpper()  
        Next  
    End Function  
  
    Sub Main()  
        Dim stringArray = New String() {"abc", "def", "ghi"}  
  
        Dim q = From str In stringArray.ConvertCollectionToUpperCase()  
                Select str  
  
        For Each Str As String In q  
            Console.WriteLine("Main: str {0}", Str)   
        Next  
    End Sub  
  
End Module  
```  
  
 這個範例會產生下列輸出：  
  
```  
ToUpper: source abc  
Main: str ABC  
ToUpper: source def  
Main: str DEF  
ToUpper: source ghi  
Main: str GHI  
```  
  
 請注意，逐一查看 `ConvertCollectionToUpperCase` 所傳回的集合時，會從來源字串陣列擷取每個項目，並在下一個項目從來源字串陣列擷取前，轉換為大寫。  
  
 您可以看到在所傳回之集合中的每個項目在 `foreach` 的 `Main` 迴圈中處理前，字串的整個陣列都沒有轉換為大寫。  
  
## <a name="see-also"></a>另請參閱  
 [教學課程： 延後執行 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md)
