---
title: "多載屬性和方法 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], mulltiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8a872540716941ccd0dbb8b058508b89ce26a988
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="overloaded-properties-and-methods-visual-basic"></a>多載屬性和方法 (Visual Basic)
多載，就是建立多個程序、 執行個體建構函式或具有相同名稱但不同的引數類型的類別中的屬性。  
  
## <a name="overloading-usage"></a>多載使用方式  
 當您採用不同的資料類型上作業的程序的相同名稱的物件模型規定，多載會特別有用。 例如，可以顯示數種不同的資料類型的類別可以有`Display`看起來像這樣的程序：  
  
 [!code-vb[VbVbalrOOP#64](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_1.vb)]  
  
 沒有多載中，您必須建立不同的名稱，每個程序，即使它們沒有相同的作業，如下所示：  
  
 [!code-vb[VbVbalrOOP#65](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_2.vb)]  
  
 多載可讓您更輕鬆地使用屬性或方法，因為它提供了可用的資料類型的選擇。 例如，多載`Display`方法討論之前可以呼叫任何下列程式碼：  
  
 [!code-vb[VbVbalrOOP#66](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_3.vb)]  
  
 在執行階段，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]呼叫正確的程序根據資料型別參數的您所指定。  
  
## <a name="overloading-rules"></a>多載規則  
 您可以新增兩個或多個屬性具有相同名稱的方法，以建立多載的成員的類別。 除了多載衍生的成員，每個多載的成員必須具有不同的參數清單，並多載屬性或程序時，無法做為區別的功能使用下列項目：  
  
-   修飾詞，例如`ByVal`或`ByRef`，套用至成員或成員的參數。  
  
-   參數的名稱  
  
-   程序的傳回型別  
  
 `Overloads`關鍵字是選擇性的多載時，但是，如果任何多載成員會使用`Overloads`關鍵字，則所有其他多載的成員具有相同名稱也必須指定此關鍵字。  
  
 在衍生的類別可以多載繼承的成員與具有相同參數和參數類型，這道程序的成員*的名稱和簽章，以遮蔽*。 如果`Overloads`的名稱和簽章，以遮蔽，成員的衍生的類別的實作將會使用而不是基底類別中實作，而且該成員的所有多載可用的執行個體時，會使用關鍵字在衍生的類別。  
  
 如果`Overloads`多載繼承的成員具有相同參數和參數類型的成員時，省略關鍵字，則稱為多載*的名稱，以遮蔽*。 名稱，以遮蔽取代繼承的成員，實作，而它會使得所有其他多載衍生的類別和及其子系的執行個體無法使用。  
  
 `Overloads`和`Shadows`修飾詞不能同時用於相同的屬性或方法。  
  
### <a name="example"></a>範例  
 下列範例會建立多載的方法都接受`String`或`Decimal`金額和傳回包含營業稅的字串表示。  
  
##### <a name="to-use-this-example-to-create-an-overloaded-method"></a>使用此範例來建立多載的方法  
  
1.  開啟新的專案，然後加入類別，名為`TaxClass`。  
  
2.  將下列程式碼加入 `TaxClass` 類別。  
  
     [!code-vb[VbVbalrOOP#67](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_4.vb)]  
  
3.  將下列程序加入至表單。  
  
     [!code-vb[VbVbalrOOP#68](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_5.vb)]  
  
4.  將按鈕加入到您的表單並呼叫`ShowTax`程序從`Button1_Click`按鈕的事件。  
  
5.  執行專案，然後按一下 若要測試的多載表單上的按鈕`ShowTax`程序。  
  
 在執行階段，編譯器會選擇適當的多載函式所使用的參數相符。 當您按一下按鈕時，使用第一次呼叫多載的方法`Price`參數是字串和訊息，「 價格會是一個字串。 稅是 $5.12 「 顯示。 `TaxAmount`使用呼叫`Decimal`值的第二個時間和訊息，「 價格是十進位數。 稅是 $5.12 「 顯示。  
  
## <a name="see-also"></a>另請參閱  
 [物件和類別](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Visual Basic 中的遮蔽功能](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [Sub 陳述式](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [繼承的基本概念](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)  
 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)  
 [多載](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
