---
title: "My.Forms 和 My.WebServices 提供的預設物件執行個體 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 44265c3f6f38a001192a8d92f2fbb6edeaca21cb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a>My.Forms 和 My.WebServices 提供的預設物件執行個體 (Visual Basic)
[My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)和[My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)物件提供存取表單、 資料來源，以及您的應用程式所使用的 XML Web 服務。 這些提供項目的集合來執行這個*預設執行個體會*的每個物件。  
  
## <a name="default-instances"></a>預設執行個體  
 預設執行個體是執行個體之類別的執行階段所提供，不需要為宣告並具現化使用`Dim`和`New`陳述式。 下列範例會示範如何您可能會宣告並具現化的執行個體<xref:System.Windows.Forms.Form>類別稱為 「 `Form1`，和如何您現在已可取得的預設執行個體，這個<xref:System.Windows.Forms.Form>類別透過`My.Forms`。  
  
 [!code-vb[VbVbcnMy#5](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_1.vb)]  
  
 [!code-vb[VbVbcnMy#6](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_2.vb)]  
  
 `My.Forms`物件傳回的預設執行個體的集合，每個`Form`存在於您的專案中的類別。 同樣地，`My.WebServices`提供每個 Web 服務 proxy 類別的預設執行個體，您已在您的應用程式中建立的參考。  
  
## <a name="see-also"></a>另請參閱  
 [My.Forms 物件](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [My.WebServices 物件](../../../visual-basic/language-reference/objects/my-webservices-object.md)  
 [My 如何相依於專案類型](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
