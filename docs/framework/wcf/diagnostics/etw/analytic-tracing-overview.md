---
title: "分析追蹤的概觀"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- analytic tracing [WCF], overview
ms.assetid: ae55e9cc-0809-442f-921f-d644290ebf15
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3492821d56f7089c2aa53bba566690ded02f8a5b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="analytic-tracing-overview"></a>分析追蹤的概觀
[!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] 中的分析追蹤是一項高效能、低詳細等級的追蹤功能，設定於 Windows 事件追蹤 (ETW) 之上。 ETW 是在核心層級執行，可大幅降低追蹤作業的負荷。 它能有效率地緩衝使用者和核心模式的事件，並且允許動態啟用記錄，而不需重新啟動服務。 事件發出和接收之後，即可在事件記錄檔中使用追蹤資料。  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)] ETW 的詳細資訊，請參閱 [使用 ETW 改善偵錯和效能調整](http://go.microsoft.com/fwlink/?LinkId=164781)。  
  
 除了使用 Windows 系統、安全性和應用程式事件記錄檔分析應用程式之外， [!INCLUDE[wv](../../../../../includes/wv-md.md)] 和 [!INCLUDE[lserver](../../../../../includes/lserver-md.md)] 也在應用程式和服務記錄檔最上層節點下引進了額外的記錄檔。 這些新記錄檔的目的在於儲存特定應用程式或特定元件的事件，而非影響整個系統的全域事件 (例如安全性事件記錄檔可能會記錄的事件類型)。 [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] 會統合並相互關聯以下項目的記錄檔： [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 追蹤事件、 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 訊息記錄和 [!INCLUDE[wf1](../../../../../includes/wf1-md.md)] 應用程式和服務記錄檔的追蹤記錄。  
  
## <a name="concepts-and-capabilities"></a>概念和功能  
 下列概念和功能適用於 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 分析追蹤。  
  
### <a name="enabling-wcf-diagnostics-settings"></a>啟用 WCF 診斷設定  
 在中啟用 WCF 診斷\<system.serviceModel >\<診斷 > 組態區段。  
  
```xml  
<system.serviceModel>  
  <diagnostics>  
```  
  
 Web 裝載 IIS 虛擬應用程式的 WCF 診斷設定是在本身的 Web.config 檔案中啟用。 另一個選擇是在應用程式內的子目錄中建立 Web.config。  這個選擇會將設定套用至子目錄內的所有服務。  為確保針對應用程式內的所有服務一致初始化診斷設定，這些設定應該在應用程式目錄的 Web.config 內，而不是在應用程式內的其中一個個別子目錄中。  
  
### <a name="channels"></a>通道  
 ETW 允許軟體元件使用通道將追蹤事件導向特定對象。 例如，您可以將系統管理員的事件傳送至一個通道，以及將應用程式開發人員重視的事件傳送至另一個通道。 通道會加以命名並且註冊至 Windows，如此消費者就可以使用事件檢視器檢視通道的事件。  
  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 中 [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] 的分析追蹤功能會寫入 Microsoft-Windows-Application-Server-Applications 通道。 此通道是專為想要在實際執行時監控 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 服務健康狀況的使用者所設計。 它會定義一個小型事件集，可在許多健康狀況監控和疑難排解的情況中使用。  
  
 若要啟用 Windows 事件追蹤資訊清單，以便在事件記錄檔中正確解碼訊息，請依照下列方式，在命令列上使用 ServiceModelReg 工具：  
  
 `ServiceModelReg.exe -i -c:etw`  
  
### <a name="dynamic-configuration"></a>動態組態  
 ETW 基礎結構可讓您使用標準 Windows 工具，以動態方式啟用和設定追蹤。 [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)][動態地啟用分析追蹤](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)。  
  
### <a name="message-flow-tracing"></a>訊息流程追蹤  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)] 如何啟用訊息流程追蹤的詳細資訊，請參閱 [Configuring Message Flow Tracing](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)。  
  
### <a name="keywords"></a>關鍵字  
 關鍵字可用來篩選追蹤訊息，以及定義發出事件的 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 元件。 [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)][動態地啟用分析追蹤](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)。
