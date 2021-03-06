---
title: "$ (C# 參考)"
ms.date: 02/09/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- $ language element [C#]
ms.assetid: 7d9e21b5-eac3-4878-9530-50e4da578acd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d245bab063721abdb930aae113aab2094553b9bb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="-c-reference"></a>$ (C# 參考)

將字串常值識別為[字串插值](../keywords/interpolated-strings.md)。 字串插值是類似範本的字串，其中包含常值文字及「插入運算式」。 解析字串插值時 (例如在指派陳述式或方法呼叫中)，其插入運算式會以運算式在結果字串中的字串表示取代。 字串插值會以 .NET Framework 支援的[複合格式字串](../../../standard/base-types/composite-format.md)取代。

下列範例使用 `$` 字元來定義字串插值。

[!code-csharp[interpolated-string-symbol](../../../../samples/snippets/csharp/language-reference/keywords/dollar-sign1.cs#1)]

如需字串插值的詳細資訊，請參閱[字串插值](../keywords/interpolated-strings.md)主題。

## <a name="see-also"></a>另請參閱  
 [C# 參考](../../../csharp/language-reference/index.md)  
 [C# 程式設計指南](../../../csharp/programming-guide/index.md)  
 [C# 特殊字元](../../../csharp/language-reference/tokens/index.md)
