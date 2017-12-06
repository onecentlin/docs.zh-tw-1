---
title: "ICorProfilerObjectEnum 介面"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerObjectEnum
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerObjectEnum
helpviewer_keywords: ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 13e1651c-9523-40ef-bfd7-87fb94519f8b
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8b46f33485a63404f11dc0606e420ec9c3c43f1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerobjectenum-interface"></a><span data-ttu-id="fa4df-102">ICorProfilerObjectEnum 介面</span><span class="sxs-lookup"><span data-stu-id="fa4df-102">ICorProfilerObjectEnum Interface</span></span>
<span data-ttu-id="fa4df-103">提供方法，以循序逐一查看所產生的已凍結物件的集合[Ngen.exe （原生映像產生器）](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)。</span><span class="sxs-lookup"><span data-stu-id="fa4df-103">Provides methods to sequentially iterate through a collection of frozen objects that are generated by the [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fa4df-104">方法</span><span class="sxs-lookup"><span data-stu-id="fa4df-104">Methods</span></span>  
  
|<span data-ttu-id="fa4df-105">方法</span><span class="sxs-lookup"><span data-stu-id="fa4df-105">Method</span></span>|<span data-ttu-id="fa4df-106">說明</span><span class="sxs-lookup"><span data-stu-id="fa4df-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fa4df-107">Clone 方法</span><span class="sxs-lookup"><span data-stu-id="fa4df-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-clone-method.md)|<span data-ttu-id="fa4df-108">取得這個 `ICorProfilerObjectEnum` 介面複本的介面指標。</span><span class="sxs-lookup"><span data-stu-id="fa4df-108">Gets an interface pointer to a copy of this `ICorProfilerObjectEnum` interface.</span></span>|  
|[<span data-ttu-id="fa4df-109">GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="fa4df-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-getcount-method.md)|<span data-ttu-id="fa4df-110">取得集合中的已凍結的物件總數。</span><span class="sxs-lookup"><span data-stu-id="fa4df-110">Gets the total number of frozen objects in the collection.</span></span>|  
|[<span data-ttu-id="fa4df-111">Next 方法</span><span class="sxs-lookup"><span data-stu-id="fa4df-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-next-method.md)|<span data-ttu-id="fa4df-112">取得指定的數目的連續物件的物件，從序列中列舉值的目前位置開始的循序集合。</span><span class="sxs-lookup"><span data-stu-id="fa4df-112">Gets the specified number of contiguous objects from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="fa4df-113">Reset 方法</span><span class="sxs-lookup"><span data-stu-id="fa4df-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-reset-method.md)|<span data-ttu-id="fa4df-114">將列舉值的資料指標移至序列的開始位置。</span><span class="sxs-lookup"><span data-stu-id="fa4df-114">Moves this enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="fa4df-115">Skip 方法</span><span class="sxs-lookup"><span data-stu-id="fa4df-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-skip-method.md)|<span data-ttu-id="fa4df-116">將這個列舉值的資料指標從其目前位置前移，以略過指定的項目數目。</span><span class="sxs-lookup"><span data-stu-id="fa4df-116">Advances the cursor of this enumerator from its current position so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa4df-117">備註</span><span class="sxs-lookup"><span data-stu-id="fa4df-117">Remarks</span></span>  
 <span data-ttu-id="fa4df-118">`ICorProfilerObjectEnum` 介面是列舉值。</span><span class="sxs-lookup"><span data-stu-id="fa4df-118">The `ICorProfilerObjectEnum` interface is an enumerator.</span></span> <span data-ttu-id="fa4df-119">它可讓陣列的接收端以適合接收端的速率，從傳送端提取項目。</span><span class="sxs-lookup"><span data-stu-id="fa4df-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="fa4df-120">收件者是能夠明確控制陣列項目的流程，也就是說，藉此避免發生與傳遞大型陣列做為方法參數相關的問題。</span><span class="sxs-lookup"><span data-stu-id="fa4df-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems related to passing large arrays as method parameters.</span></span>  
  
 <span data-ttu-id="fa4df-121">使用[icorprofilerinfo2:: Enummodulefrozenobjects](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md)取得指標`ICorProfilerObjectEnum`介面。</span><span class="sxs-lookup"><span data-stu-id="fa4df-121">Use [ICorProfilerInfo2::EnumModuleFrozenObjects](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md) to obtain a pointer to the `ICorProfilerObjectEnum` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa4df-122">需求</span><span class="sxs-lookup"><span data-stu-id="fa4df-122">Requirements</span></span>  
 <span data-ttu-id="fa4df-123">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fa4df-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa4df-124">**標頭：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fa4df-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fa4df-125">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa4df-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa4df-126">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa4df-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa4df-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fa4df-127">See Also</span></span>  
 [<span data-ttu-id="fa4df-128">分析介面</span><span class="sxs-lookup"><span data-stu-id="fa4df-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="fa4df-129">EnumModuleFrozenObjects 方法</span><span class="sxs-lookup"><span data-stu-id="fa4df-129">EnumModuleFrozenObjects Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md)