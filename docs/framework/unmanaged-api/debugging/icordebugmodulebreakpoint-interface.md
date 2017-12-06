---
title: ICorDebugModuleBreakpoint Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModuleBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModuleBreakpoint
helpviewer_keywords: ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: 34667162-f314-475f-ae1b-ce9cb0fcbb83
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3e3937c6c0baef4cc927b5c5d789826c70beebf2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodulebreakpoint-interface1"></a><span data-ttu-id="07b04-102">ICorDebugModuleBreakpoint Interface1</span><span class="sxs-lookup"><span data-stu-id="07b04-102">ICorDebugModuleBreakpoint Interface1</span></span>
<span data-ttu-id="07b04-103">提供特定模組的存取。</span><span class="sxs-lookup"><span data-stu-id="07b04-103">Provides access to specific modules.</span></span> <span data-ttu-id="07b04-104">這個介面是 ICorDebugBreakpoint 介面的子類別。</span><span class="sxs-lookup"><span data-stu-id="07b04-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="07b04-105">方法</span><span class="sxs-lookup"><span data-stu-id="07b04-105">Methods</span></span>  
  
|<span data-ttu-id="07b04-106">方法</span><span class="sxs-lookup"><span data-stu-id="07b04-106">Method</span></span>|<span data-ttu-id="07b04-107">說明</span><span class="sxs-lookup"><span data-stu-id="07b04-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="07b04-108">GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="07b04-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="07b04-109">取得參考的模組設定此中斷點的位置 ICorDebugModule 介面指標。</span><span class="sxs-lookup"><span data-stu-id="07b04-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07b04-110">備註</span><span class="sxs-lookup"><span data-stu-id="07b04-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07b04-111">這個介面不支援跨電腦或跨處理序的遠端呼叫。</span><span class="sxs-lookup"><span data-stu-id="07b04-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07b04-112">需求</span><span class="sxs-lookup"><span data-stu-id="07b04-112">Requirements</span></span>  
 <span data-ttu-id="07b04-113">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="07b04-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07b04-114">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="07b04-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07b04-115">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07b04-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07b04-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07b04-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07b04-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="07b04-117">See Also</span></span>  
 [<span data-ttu-id="07b04-118">偵錯介面</span><span class="sxs-lookup"><span data-stu-id="07b04-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)