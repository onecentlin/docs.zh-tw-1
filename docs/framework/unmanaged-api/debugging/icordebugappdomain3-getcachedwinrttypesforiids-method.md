---
title: "ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs 方法"
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
- ICorDebugAppDomain3.GetCachedWinRTTypesForIIDs
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs method, [.NET Framework debugging]
- GetCachedWinRTTypesForIIDs method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 23682ca0-1bcf-48e6-996e-69f7ba337682
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5a7ce44dcfc709b4fea1952471cf31f5f07d4d0e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a>ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs 方法
取得列舉值的快取[!INCLUDE[wrt](../../../../includes/wrt-md.md)]應用程式定義域中的類型取決於其介面識別項。  
  
## <a name="syntax"></a>語法  
  
```  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
#### <a name="parameters"></a>參數  
 `cReqTypes`  
 [in]必要的型別數目。  
  
 `iidsToResolve`  
 [in]指標陣列，其中包含對應到受管理的表示法的介面識別碼[!INCLUDE[wrt](../../../../includes/wrt-md.md)]要擷取的類型。  
  
 `ppTypesEnum`  
 [out]允許的快取列舉"ICorDebugTypeEnum 」 介面物件的位址指標受管理的表示法[!INCLUDE[wrt](../../../../includes/wrt-md.md)]擷取類型，根據中的介面識別碼`iidsToResolve`。  
  
## <a name="remarks"></a>備註  
 如果方法時，無法擷取特定的介面識別項的資訊，"ICorDebugTypeEnum"集合中的對應項目會有一種`ELEMENT_TYPE_END`資料擷取問題，因為錯誤或`ELEMENT_TYPE_VOID`未知的介面識別項。  
  
## <a name="requirements"></a>需求  
 **平台：**[!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 **標頭：** CorDebug.idl、 CorDebug.h  
  
 **程式庫：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>請參閱  
 [ICorDebugAppDomain3 介面](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
