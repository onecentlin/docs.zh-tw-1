---
title: "HOW TO：將 WCF 用戶端設為與 WSE3.0 服務交互操作"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 3dadd7f1-d207-4ea5-a73b-3e8aa44407f8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ea71737e1e214aa1a035739901bf79f8ef4a9c7a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-configure-a-wcf-client-to-interoperate-with-wse30-services"></a>HOW TO：將 WCF 用戶端設為與 WSE3.0 服務交互操作
當 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 用戶端設定為使用 WS-Addressing August 2004 版本規格時，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 用戶端的連線層級與 Microsoft .NET 服務的 Web Services Enhancements (WSE) 3.0 相容。  
  
### <a name="to-configure-a-wcf-client-to-interoperate-with-a-wse-30-web-service"></a>將 WCF 用戶端設定為與 WSE 3.0 Web 服務交互操作  
  
1.  執行[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)建立[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]WSE 3.0 Web 服務用戶端。  
  
     針對 WSE Web 服務，會建立 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 用戶端類別。  
  
     如需詳細資訊，關於建立[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]用戶端，請參閱[How to： 建立用戶端](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)。  
  
2.  建立類別，表示可與 WSE 3.0 Web 服務通訊的繫結。  
  
     下列類別是一部分[與 WSE 互通](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41)範例。  
  
    1.  建立從 <xref:System.ServiceModel.Channels.Binding> 類別衍生的類別。  
  
         下列程式碼範例會建立一個名為 `WseHttpBinding` 的類別，此類別衍生自 <xref:System.ServiceModel.Channels.Binding> 類別。  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  將屬性加入至類別，以指定 WSE 通行判斷提示 (Turnkey Assertion)、是否需要衍生金鑰、是否使用安全工作階段、是否需要簽章確認，以及訊息保護設定。  
  
         下列程式碼範例會定義`SecurityAssertion,``RequireDerivedKeys, EstablishSecurityContext, MessageProtectionOrder`指定 WSE 通行判斷提示、 是否需要衍生的金鑰、 是否使用安全工作階段、 是否需要簽章確認和訊息保護設定，屬性分別。  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3.  覆寫 <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> 方法來設定繫結屬性。  
  
         下列程式碼範例會藉由取得 `SecurityAssertion` 和 `MessageProtectionOrder` 屬性的值，指定傳輸、訊息編碼和訊息保護設定。  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3.  在用戶端應用程式程式碼中，加入程式碼以設定繫結屬性。  
  
     下列程式碼範例會指定 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 用戶端必須依照 WSE 3.0 `AnonymousForCertificate` 通行安全性判斷提示所定義，使用訊息保護和驗證。 此外，也需要安全工作階段和衍生金鑰。  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a>範例  
 下列程式碼範例會定義自訂的繫結，此繫結會公開 WSE 3.0 通行安全性判斷提示屬性的對應屬性。 接著會使用名為 `WseHttpBinding` 的自訂繫結，指定 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 用戶端的繫結屬性。  
  
  
[!code-csharp[c_WCFClientToWSEService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#0)]
[!code-vb[c_WCFClientToWSEService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#0)]  
  
## <a name="see-also"></a>請參閱  
 <xref:System.ServiceModel.Channels.Binding>  
 [與 WSE 互通](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41)
