---
title: "COR_NATIVE_LINK 結構"
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
- COR_NATIVE_LINK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_NATIVE_LINK
helpviewer_keywords:
- COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 63e5946e98e7c862a2502a71a02e605a38086618
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="cornativelink-structure"></a>COR_NATIVE_LINK 結構
包含用來連結原生程式碼的資訊。  
  
## <a name="syntax"></a>語法  
  
```  
typedef struct   
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a>成員  
  
|成員|描述|  
|------------|-----------------|  
|`m_linkType`|要連結原生程式碼的類型。 這個值是其中一個[CorNativeLinkType](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)值。|  
|`m_flags`|連結器在連結機器碼時使用的旗標。 這個值是其中一個[CorNativeLinkFlags](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)值。|  
|`m_entryPoint`|MemberRef 中繼資料語彙基元所代表的進入點。 格式是`lib:entrypoint`。|  
  
## <a name="requirements"></a>需求  
 **平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** Cor.h  
  
 **程式庫：**做為 MsCorEE.dll 中的資源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>請參閱  
 [中繼資料結構](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [CorNativeLinkType 列舉](../../../../docs/framework/unmanaged-api/metadata/cornativelinktype-enumeration.md)  
 [CorNativeLinkFlags 列舉](../../../../docs/framework/unmanaged-api/metadata/cornativelinkflags-enumeration.md)
