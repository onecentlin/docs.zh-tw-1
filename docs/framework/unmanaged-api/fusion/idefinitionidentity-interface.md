---
title: "IDefinitionIdentity 介面"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDefinitionIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IDefinitionIdentity
helpviewer_keywords: IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a63436f107a2604fd5620854339447a4af254e52
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="0bbbd-102">IDefinitionIdentity 介面</span><span class="sxs-lookup"><span data-stu-id="0bbbd-102">IDefinitionIdentity Interface</span></span>
<span data-ttu-id="0bbbd-103">代表目前範圍中定義的應用程式的程式碼的唯一的簽章。</span><span class="sxs-lookup"><span data-stu-id="0bbbd-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0bbbd-104">方法</span><span class="sxs-lookup"><span data-stu-id="0bbbd-104">Methods</span></span>  
  
|<span data-ttu-id="0bbbd-105">方法</span><span class="sxs-lookup"><span data-stu-id="0bbbd-105">Method</span></span>|<span data-ttu-id="0bbbd-106">說明</span><span class="sxs-lookup"><span data-stu-id="0bbbd-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="0bbbd-107">取得新的介面指標`IDefinitionIdentity`物件與此相同`IDefinitionIdentity`，除非有指定的屬性變更。</span><span class="sxs-lookup"><span data-stu-id="0bbbd-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="0bbbd-108">取得的介面指標[IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)物件，其中包含與此相關聯的屬性`IDefinitionIdentity`。</span><span class="sxs-lookup"><span data-stu-id="0bbbd-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="0bbbd-109">指定的命名空間中取得具有指定名稱之屬性的值。</span><span class="sxs-lookup"><span data-stu-id="0bbbd-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="0bbbd-110">設定為指定的值指定的命名空間中具有指定的名稱的屬性。</span><span class="sxs-lookup"><span data-stu-id="0bbbd-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0bbbd-111">需求</span><span class="sxs-lookup"><span data-stu-id="0bbbd-111">Requirements</span></span>  
 <span data-ttu-id="0bbbd-112">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0bbbd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bbbd-113">**標頭：** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="0bbbd-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="0bbbd-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bbbd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bbbd-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0bbbd-115">See Also</span></span>  
 [<span data-ttu-id="0bbbd-116">融合介面</span><span class="sxs-lookup"><span data-stu-id="0bbbd-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)