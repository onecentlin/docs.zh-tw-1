---
title: "ICorProfilerCallback::UnmanagedToManagedTransition 方法"
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
- ICorProfilerCallback.UnmanagedToManagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition
helpviewer_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition method [.NET Framework profiling]
- UnmanagedToManagedTransition method [.NET Framework profiling]
ms.assetid: ade2cc01-9b81-4e09-a5f9-b3b9dda27e96
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1653a92563f0031fcb4c215dd58e4e1ac73030d5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a>ICorProfilerCallback::UnmanagedToManagedTransition 方法
通知分析工具，從 unmanaged 程式碼轉換為 managed 程式碼已發生。  
  
## <a name="syntax"></a>語法  
  
```  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
#### <a name="parameters"></a>參數  
 `functionId`  
 [in]所呼叫之函式的識別碼。  
  
 `reason`  
 [in]值為[COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md)指出轉換是發生由於 unmanaged 程式碼呼叫至 managed 程式碼，或因為從受管理的一個由呼叫 unmanaged 函式傳回的列舉。  
  
## <a name="remarks"></a>備註  
 如果值`reason`是 COR_PRF_TRANSITION_RETURN 和`functionId`不是 null，函式識別碼就是 unmanaged 的函式，並將永遠不會有已編譯使用在 just-in-time (JIT) 編譯器。 Unmanaged 函式有與其相關聯，例如名稱及一些中繼資料的一些基本資訊。  
  
 如果值`reason`是 COR_PRF_TRANSITION_CALL，這可能會出現，呼叫的函式 （亦即，managed 函式） 尚未被 JIT 編譯。  
  
## <a name="requirements"></a>需求  
 **平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** CorProf.idl、CorProf.h  
  
 **程式庫：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>請參閱  
 [ICorProfilerCallback 介面](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ManagedToUnmanagedTransition 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)  
 [在 C++ 中使用明確的 PInvoke (DllImport 屬性)](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)  
 [使用 C++ Interop (隱含 PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)
