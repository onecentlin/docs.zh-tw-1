---
title: "GetTypeLibInfo 函式"
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
- GetTypeLibInfo
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- GetTypeLibInfo
helpviewer_keywords:
- GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4f6b1ad18809b46b7a2b38137231028f696d51b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="gettypelibinfo-function"></a>GetTypeLibInfo 函式
傳回指定的類型程式庫的相關資訊，藉由檢查其[TLIBATTR](https://msdn.microsoft.com/library/ms221376\(v=vs.85\).aspx)結構。  
  
## <a name="syntax"></a>語法  
  
```  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
#### <a name="parameters"></a>參數  
 `szFile`  
 [in]類型程式庫檔案名稱。  
  
 `pTypeLibID`  
 [out]類型程式庫的 GUID。  
  
 `pTypeLibLCID`  
 [out]當地語系化類型程式庫的識別碼。  
  
 `pTypeLibPlatform`  
 [out]A [SYSKIND](https://msdn.microsoft.com/library/ms221272\(v=vs.85\).aspx)識別目標作業系統類型程式庫的旗標。 常見的值為 SYS_WIN32 和 SYS_WIN64。  
  
 `pTypeLibMajorVer`  
 [out]類型程式庫的主要版本號碼。 例如，針對版本*x.y*，主要版本號碼是*x*。  
  
 `pTypeLibMinorVer`  
 [out]類型程式庫的次要版本號碼。 例如，針對版本*x.y*，次要版本號碼是*y*。  
  
## <a name="remarks"></a>備註  
 `GetTypeLibInfo`函式會呼叫[Tlbexp.exe （類型程式庫匯出工具）](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)。 此工具會產生類型程式庫會描述 common language runtime (CLR) 組件中的類型。  
  
 如果任何參數是 null，則此函數會傳回`HRESULT`的`E_POINTER`。 否則它會傳回 `S_OK`。  
  
## <a name="requirements"></a>需求  
 **平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** TlbRef.h  
  
 **程式庫：** TlbRef.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>請參閱  
 [Tlbexp Helper 函式](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [LoadTypeLibEx 函式](https://msdn.microsoft.com/library/ms221249\(v=vs.85\).aspx)
