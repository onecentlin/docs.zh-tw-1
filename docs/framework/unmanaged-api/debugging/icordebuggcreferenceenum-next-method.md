---
title: "ICorDebugGCReferenceEnum::Next 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugGCReferenceEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugGCReferenceEnum::Next
helpviewer_keywords:
- Next method, ICorDebugGCReferenceEnum interface [.NET Framework debugging]
- ICorDebugGCReferenceEnum::Next method [.NET Framework debugging]
ms.assetid: 91b1345c-a94f-4ef8-9696-3823d06c6d05
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 55a02b88076d6097415d108d58f74565d1f426de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="467d8-102">ICorDebugGCReferenceEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="467d8-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="467d8-103">取得指定的數目[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)含有物件將會進行記憶體回收的相關資訊的執行個體。</span><span class="sxs-lookup"><span data-stu-id="467d8-103">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="467d8-104">語法</span><span class="sxs-lookup"><span data-stu-id="467d8-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],   
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="467d8-105">參數</span><span class="sxs-lookup"><span data-stu-id="467d8-105">Parameters</span></span>  
 <span data-ttu-id="467d8-106">celt</span><span class="sxs-lookup"><span data-stu-id="467d8-106">celt</span></span>  
 <span data-ttu-id="467d8-107">[in]要擷取的根目錄的數目。</span><span class="sxs-lookup"><span data-stu-id="467d8-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="467d8-108">根目錄</span><span class="sxs-lookup"><span data-stu-id="467d8-108">roots</span></span>  
 <span data-ttu-id="467d8-109">[out]陣列的指標，其中每個指向[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)物件，代表要進行記憶體回收的物件的根。</span><span class="sxs-lookup"><span data-stu-id="467d8-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="467d8-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="467d8-110">pceltFetched</span></span>  
 <span data-ttu-id="467d8-111">[out]數目的指標[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)中實際傳回的物件`roots`。</span><span class="sxs-lookup"><span data-stu-id="467d8-111">[out] A pointer to the number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="467d8-112">如果 `celt` 為 1，則這個值可能是 `null`。</span><span class="sxs-lookup"><span data-stu-id="467d8-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="467d8-113">備註</span><span class="sxs-lookup"><span data-stu-id="467d8-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="467d8-114">需求</span><span class="sxs-lookup"><span data-stu-id="467d8-114">Requirements</span></span>  
 <span data-ttu-id="467d8-115">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="467d8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="467d8-116">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="467d8-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="467d8-117">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="467d8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="467d8-118">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="467d8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="467d8-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="467d8-119">See Also</span></span>  
 [<span data-ttu-id="467d8-120">ICorDebugGCReferenceEnum 介面</span><span class="sxs-lookup"><span data-stu-id="467d8-120">ICorDebugGCReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
 [<span data-ttu-id="467d8-121">偵錯介面</span><span class="sxs-lookup"><span data-stu-id="467d8-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)