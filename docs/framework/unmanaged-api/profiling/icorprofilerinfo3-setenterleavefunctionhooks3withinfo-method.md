---
title: "ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.SetEnterLeaveFunctionHooks3WithInfo Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
ms.assetid: ca8ea534-e441-47b8-be85-466410988c0a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a30dde6f406cfb6d1140e7cd8e2a8f8f3ab40006
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3withinfo-method"></a><span data-ttu-id="50c6a-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo 方法</span><span class="sxs-lookup"><span data-stu-id="50c6a-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo Method</span></span>
<span data-ttu-id="50c6a-103">指定要呼叫的程式碼剖析工具實作函式[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)， [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)，和[FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)受管理的函式的攔截。</span><span class="sxs-lookup"><span data-stu-id="50c6a-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50c6a-104">語法</span><span class="sxs-lookup"><span data-stu-id="50c6a-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks3WithInfo(  
            [in] FunctionEnter3WithInfo    *pFuncEnter3,  
            [in] FunctionLeave3withInfo    *pFuncLeave3,  
            [in] FunctionTailcall3WithInfo *pFuncTailcall3);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="50c6a-105">參數</span><span class="sxs-lookup"><span data-stu-id="50c6a-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="50c6a-106">[in]指向要做為實作`FunctionEnter3WithInfo`回呼。</span><span class="sxs-lookup"><span data-stu-id="50c6a-106">[in] A pointer to the implementation to be used as the `FunctionEnter3WithInfo` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="50c6a-107">[in]指向要做為實作`FunctionLeave3WithInfo`回呼。</span><span class="sxs-lookup"><span data-stu-id="50c6a-107">[in] A pointer to the implementation to be used as the `FunctionLeave3WithInfo` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="50c6a-108">[in]指向要做為實作`FunctionTailcall3WithInfo`回呼。</span><span class="sxs-lookup"><span data-stu-id="50c6a-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50c6a-109">備註</span><span class="sxs-lookup"><span data-stu-id="50c6a-109">Remarks</span></span>  
 <span data-ttu-id="50c6a-110">[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)， [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)，和[FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)攔截程序提供堆疊框架和引數的檢查。</span><span class="sxs-lookup"><span data-stu-id="50c6a-110">The [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) hooks provide stack frame and argument inspection.</span></span> <span data-ttu-id="50c6a-111">若要存取該資訊之後， `COR_PRF_ENABLE_FUNCTION_ARGS`， `COR_PRF_ENABLE_FUNCTION_RETVAL`，及/或`COR_PRF_ENABLE_FRAME_INFO`旗標必須設定。</span><span class="sxs-lookup"><span data-stu-id="50c6a-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="50c6a-112">分析工具可以使用[icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)方法來設定事件的旗標，然後使用`SetEnterLeaveFunctionHooks3WithInfo`方法來註冊您的實作，此函式。</span><span class="sxs-lookup"><span data-stu-id="50c6a-112">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the `SetEnterLeaveFunctionHooks3WithInfo` method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="50c6a-113">一次只能有一組的回呼可能在作用中，會優先使用最新版本。</span><span class="sxs-lookup"><span data-stu-id="50c6a-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="50c6a-114">因此，如果程式碼剖析工具呼叫兩者[SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)和`SetEnterLeaveFunctionHooks3WithInfo`，`SetEnterLeaveFunctionHooks3WithInfo`用。</span><span class="sxs-lookup"><span data-stu-id="50c6a-114">Therefore, if a profiler calls both [SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and `SetEnterLeaveFunctionHooks3WithInfo`, `SetEnterLeaveFunctionHooks3WithInfo` is used.</span></span>  
  
 <span data-ttu-id="50c6a-115">`SetEnterLeaveFunctionHooks3WithInfo`方法可能只會從程式碼剖析工具呼叫[icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)回呼。</span><span class="sxs-lookup"><span data-stu-id="50c6a-115">The `SetEnterLeaveFunctionHooks3WithInfo` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50c6a-116">需求</span><span class="sxs-lookup"><span data-stu-id="50c6a-116">Requirements</span></span>  
 <span data-ttu-id="50c6a-117">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="50c6a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50c6a-118">**標頭：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="50c6a-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="50c6a-119">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50c6a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50c6a-120">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50c6a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50c6a-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="50c6a-121">See Also</span></span>  
 [<span data-ttu-id="50c6a-122">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="50c6a-122">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)  
 [<span data-ttu-id="50c6a-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="50c6a-123">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 [<span data-ttu-id="50c6a-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="50c6a-124">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [<span data-ttu-id="50c6a-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="50c6a-125">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 [<span data-ttu-id="50c6a-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="50c6a-126">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="50c6a-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="50c6a-127">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="50c6a-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="50c6a-128">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="50c6a-129">分析全域靜態函式</span><span class="sxs-lookup"><span data-stu-id="50c6a-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
 [<span data-ttu-id="50c6a-130">ICorProfilerInfo3 介面</span><span class="sxs-lookup"><span data-stu-id="50c6a-130">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="50c6a-131">分析介面</span><span class="sxs-lookup"><span data-stu-id="50c6a-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="50c6a-132">程式碼剖析</span><span class="sxs-lookup"><span data-stu-id="50c6a-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)