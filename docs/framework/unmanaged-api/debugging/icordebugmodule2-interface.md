---
title: ICorDebugModule2 Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugModule2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2
helpviewer_keywords:
- ICorDebugModule2 interface [.NET Framework debugging]
ms.assetid: 0847e64f-fdbe-4c96-8168-da20fdc84d80
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a3d62619fd83264bdc774cc1f09f4d98492d0a57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule2-interface1"></a>ICorDebugModule2 Interface1
可做為 ICorDebugModule 介面的邏輯擴充。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[ApplyChanges 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|適用於執行的處理序的中繼資料中的變更和 Microsoft intermediate language (MSIL) 程式碼中的變更。|  
|[GetJITCompilerFlags 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|取得旗標，控制在 just-in-time (JIT) 編譯這個`ICorDebugModule2`。|  
|[ResolveAssembly 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|解析指定的中繼資料語彙基元所參考的組件。|  
|[SetJITCompilerFlags 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|設定旗標，以控制 JIT 編譯這個`ICorDebugModule2`。|  
|[SetJMCStatus 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|在此設定的所有類別的所有方法的 Just My Code (JMC) 狀態`ICorDebugModule2`和指定的值以外的`pTokens`陣列，它會設定為相反側的值。|  
  
## <a name="remarks"></a>備註  
  
> [!NOTE]
>  這個介面不支援跨電腦或跨處理序的遠端呼叫。  
  
## <a name="requirements"></a>需求  
 **平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** CorDebug.idl、 CorDebug.h  
  
 **程式庫：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>請參閱  
 [偵錯介面](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
