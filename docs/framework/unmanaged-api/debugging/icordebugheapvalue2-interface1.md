---
title: ICorDebugHeapValue2 Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapValue2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapValue2
helpviewer_keywords: ICorDebugHeapValue2 interface [.NET Framework debugging]
ms.assetid: 87360a52-90b1-4ada-80c0-589a556116d8
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: de5e867d0f0b6ef47deeeda0f139da3911d3bc67
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugheapvalue2-interface1"></a><span data-ttu-id="322cc-102">ICorDebugHeapValue2 Interface1</span><span class="sxs-lookup"><span data-stu-id="322cc-102">ICorDebugHeapValue2 Interface1</span></span>
<span data-ttu-id="322cc-103">支援的通用語言執行平台 (CLR) 處理的 ICorDebugHeapValue 的延伸模組。</span><span class="sxs-lookup"><span data-stu-id="322cc-103">An extension of ICorDebugHeapValue that provides support for common language runtime (CLR) handles.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="322cc-104">方法</span><span class="sxs-lookup"><span data-stu-id="322cc-104">Methods</span></span>  
  
|<span data-ttu-id="322cc-105">方法</span><span class="sxs-lookup"><span data-stu-id="322cc-105">Method</span></span>|<span data-ttu-id="322cc-106">說明</span><span class="sxs-lookup"><span data-stu-id="322cc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="322cc-107">CreateHandle 方法</span><span class="sxs-lookup"><span data-stu-id="322cc-107">CreateHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue2-createhandle-method.md)|<span data-ttu-id="322cc-108">建立指定類型的控制代碼，這個`ICorDebugHeapValue2`物件。</span><span class="sxs-lookup"><span data-stu-id="322cc-108">Creates a handle of the specified type for this `ICorDebugHeapValue2` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="322cc-109">備註</span><span class="sxs-lookup"><span data-stu-id="322cc-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="322cc-110">這個介面不支援跨電腦或跨處理序的遠端呼叫。</span><span class="sxs-lookup"><span data-stu-id="322cc-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="322cc-111">需求</span><span class="sxs-lookup"><span data-stu-id="322cc-111">Requirements</span></span>  
 <span data-ttu-id="322cc-112">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="322cc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="322cc-113">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="322cc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="322cc-114">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="322cc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="322cc-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="322cc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="322cc-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="322cc-116">See Also</span></span>  
 [<span data-ttu-id="322cc-117">偵錯介面</span><span class="sxs-lookup"><span data-stu-id="322cc-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)