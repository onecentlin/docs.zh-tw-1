---
title: "ICorDebugProcess::IsTransitionStub 方法"
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
- ICorDebugProcess.IsTransitionStub
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsTransitionStub
helpviewer_keywords:
- ICorDebugProcess::IsTransitionStub method [.NET Framework debugging]
- IsTransitionStub method [.NET Framework debugging]
ms.assetid: f7653317-7e48-4163-be03-f50f1a4b0f70
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9fe38cf5f53c2514b845238c1d52fa12df526fdd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessistransitionstub-method"></a>ICorDebugProcess::IsTransitionStub 方法
取得值，指出是否會導致轉換為 managed 程式碼的虛設常式內的位址。  
  
## <a name="syntax"></a>語法  
  
```  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
#### <a name="parameters"></a>參數  
 `address`  
 [in]A`CORDB_ADDRESS`值，指定有問題的位址。  
  
 `pbTransitionStub`  
 [out]為的布林值的指標`true`如果指定的位址是內部的虛設常式會將導致轉換為 managed 程式碼; 否則為 *`pbTransitionStub`是`false`。  
  
## <a name="remarks"></a>備註  
 `IsTransitionStub`決定何時將逐步執行控制權傳回給受管理的 stepper unmanaged 逐步執行程式碼可以使用方法。  
  
 您也可以藉由查看可攜式執行檔 (PE) 中的資訊識別轉換 stub。  
  
## <a name="requirements"></a>需求  
 **平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** CorDebug.idl、 CorDebug.h  
  
 **程式庫：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
