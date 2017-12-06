---
title: "IMetaDataEmit::DefineMethod 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineMethod
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineMethod
helpviewer_keywords:
- DefineMethod method [.NET Framework metadata]
- IMetaDataEmit::DefineMethod method [.NET Framework metadata]
ms.assetid: 3e2102c5-48b7-4c0e-b805-7e2b5e156e3d
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: de55ee714dcba512befae3d2311a9880a08ba29f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinemethod-method"></a><span data-ttu-id="61345-102">IMetaDataEmit::DefineMethod 方法</span><span class="sxs-lookup"><span data-stu-id="61345-102">IMetaDataEmit::DefineMethod Method</span></span>
<span data-ttu-id="61345-103">建立方法或全域函式的定義與指定的簽章，並傳回該方法定義的語彙基元。</span><span class="sxs-lookup"><span data-stu-id="61345-103">Creates a definition for a method or global function with the specified signature, and returns a token to that method definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61345-104">語法</span><span class="sxs-lookup"><span data-stu-id="61345-104">Syntax</span></span>  
  
```  
HRESULT DefineMethod (      
    [in]  mdTypeDef         td,   
    [in]  LPCWSTR           szName,   
    [in]  DWORD             dwMethodFlags,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [in]  ULONG             ulCodeRVA,   
    [in]  DWORD             dwImplFlags,   
    [out] mdMethodDef      *pmd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="61345-105">參數</span><span class="sxs-lookup"><span data-stu-id="61345-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="61345-106">[in]`mdTypedef`語彙基元之父類別或方法的父介面。</span><span class="sxs-lookup"><span data-stu-id="61345-106">[in] The `mdTypedef` token of the parent class or parent interface of the method.</span></span> <span data-ttu-id="61345-107">設定`td`至`mdTokenNil`，如果您正在定義全域函式。</span><span class="sxs-lookup"><span data-stu-id="61345-107">Set `td` to `mdTokenNil`, if you are defining a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="61345-108">[in]以 Unicode 成員名稱。</span><span class="sxs-lookup"><span data-stu-id="61345-108">[in] The member name in Unicode.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="61345-109">[in]值為[CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md)列舉，指定方法或全域函式的屬性。</span><span class="sxs-lookup"><span data-stu-id="61345-109">[in] A value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration that specifies the attributes of the method or global function.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="61345-110">[in]方法簽章。</span><span class="sxs-lookup"><span data-stu-id="61345-110">[in] The method signature.</span></span> <span data-ttu-id="61345-111">簽章會保存提供的一樣。</span><span class="sxs-lookup"><span data-stu-id="61345-111">The signature is persisted as supplied.</span></span> <span data-ttu-id="61345-112">如果您要指定任何參數的其他資訊，請使用[imetadataemit:: Setparamprops](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="61345-112">If you need to specify additional information for any parameters, use the [IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="61345-113">[in]中的位元組計數`pvSigBlob`。</span><span class="sxs-lookup"><span data-stu-id="61345-113">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="61345-114">[in]程式碼的位址。</span><span class="sxs-lookup"><span data-stu-id="61345-114">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="61345-115">[in]值為[CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)列舉，指定方法的實作功能。</span><span class="sxs-lookup"><span data-stu-id="61345-115">[in] A value of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the implementation features of the method.</span></span>  
  
 `pmd`  
 <span data-ttu-id="61345-116">[out]成員語彙基元。</span><span class="sxs-lookup"><span data-stu-id="61345-116">[out] The member token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61345-117">備註</span><span class="sxs-lookup"><span data-stu-id="61345-117">Remarks</span></span>  
 <span data-ttu-id="61345-118">中繼資料 API 會確保保存相同順序的方法呼叫端指定封入類別或介面中所指定發出`td`參數。</span><span class="sxs-lookup"><span data-stu-id="61345-118">The metadata API guarantees to persist methods in the same order as the caller emits them for a given enclosing class or interface, which is specified in the `td` parameter.</span></span>  
  
 <span data-ttu-id="61345-119">使用有關的其他資訊`DefineMethod`，如下所示的特定參數設定。</span><span class="sxs-lookup"><span data-stu-id="61345-119">Additional information regarding the use of `DefineMethod` and particular parameter settings is given below.</span></span>  
  
## <a name="slots-in-the-v-table"></a><span data-ttu-id="61345-120">在 v-table 中的位置</span><span class="sxs-lookup"><span data-stu-id="61345-120">Slots in the V-table</span></span>  
 <span data-ttu-id="61345-121">執行階段會使用方法定義，來設定 v-table 位置。</span><span class="sxs-lookup"><span data-stu-id="61345-121">The runtime uses method definitions to set up v-table slots.</span></span> <span data-ttu-id="61345-122">在其中一個或多個位置需要略過，這類情況下保留同位檢查 COM 介面的版面配置，但對於 dummy 方法定義成採用位置或 v-table; 中的位置設定`dwMethodFlags`至`mdRTSpecialName`值[CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md)列舉和指定名稱為：</span><span class="sxs-lookup"><span data-stu-id="61345-122">In the case where one or more slots need to be skipped, such as to preserve parity with a COM interface layout, a dummy method is defined to take up the slot or slots in the v-table; set the `dwMethodFlags` to the `mdRTSpecialName` value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration and specify the name as:</span></span>  
  
 <span data-ttu-id="61345-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span><span class="sxs-lookup"><span data-stu-id="61345-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span></span>  
  
 <span data-ttu-id="61345-124">其中*SequenceNumber*是方法的序號和*CountOfSlots*是要在 v-table 中略過的位置數目。</span><span class="sxs-lookup"><span data-stu-id="61345-124">where *SequenceNumber* is the sequence number of the method and *CountOfSlots* is the number of slots to skip in the v-table.</span></span> <span data-ttu-id="61345-125">如果*CountOfSlots*已省略，則假設為 1。</span><span class="sxs-lookup"><span data-stu-id="61345-125">If *CountOfSlots* is omitted, 1 is assumed.</span></span> <span data-ttu-id="61345-126">這些虛擬方法不可以從 managed 或 unmanaged 程式碼呼叫，任何嘗試從 managed 或 unmanaged 程式碼呼叫它們，就會產生例外狀況。</span><span class="sxs-lookup"><span data-stu-id="61345-126">These dummy methods are not callable from either managed or unmanaged code and any attempt to call them, from either managed or unmanaged code, generates an exception.</span></span> <span data-ttu-id="61345-127">其唯一用途就是以使用執行階段產生 COM 整合 v 資料表中的空間。</span><span class="sxs-lookup"><span data-stu-id="61345-127">Their only purpose is to take up space in the v-table that the runtime generates for COM integration.</span></span>  
  
## <a name="duplicate-methods"></a><span data-ttu-id="61345-128">重複的方法</span><span class="sxs-lookup"><span data-stu-id="61345-128">Duplicate Methods</span></span>  
 <span data-ttu-id="61345-129">您不應定義重複的方法。</span><span class="sxs-lookup"><span data-stu-id="61345-129">You should not define duplicate methods.</span></span> <span data-ttu-id="61345-130">也就是說，您不應該呼叫`DefineMethod`與一組重複的值在`td`， `wzName`，和`pvSig`參數。</span><span class="sxs-lookup"><span data-stu-id="61345-130">That is, you should not call `DefineMethod` with a duplicate set of values in the `td`, `wzName`, and `pvSig` parameters.</span></span> <span data-ttu-id="61345-131">(這三個參數一起唯一定義的方法。)。</span><span class="sxs-lookup"><span data-stu-id="61345-131">(These three parameters together uniquely define the method.).</span></span> <span data-ttu-id="61345-132">不過，使用重複的三倍，前提為其中一個方法定義中，設定`mdPrivateScope`位元`dwMethodFlags`參數。</span><span class="sxs-lookup"><span data-stu-id="61345-132">However, you can use a duplicate triple provided that, for one of the method definitions, you set the `mdPrivateScope` bit in the `dwMethodFlags` parameter.</span></span> <span data-ttu-id="61345-133">(`mdPrivateScope`位元表示編譯器將不會發出這個方法定義的參考。)</span><span class="sxs-lookup"><span data-stu-id="61345-133">(The `mdPrivateScope` bit means that the compiler will not emit a reference to this method definition.)</span></span>  
  
## <a name="method-implementation-information"></a><span data-ttu-id="61345-134">方法實作資訊</span><span class="sxs-lookup"><span data-stu-id="61345-134">Method Implementation Information</span></span>  
 <span data-ttu-id="61345-135">在方法宣告為階段，通常不為已知方法實作的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="61345-135">Information about the method implementation is often not known at the time the method is declared.</span></span> <span data-ttu-id="61345-136">因此，您不需要將值在傳遞`ulCodeRVA`和`dwImplFlags`參數呼叫時`DefineMethod`。</span><span class="sxs-lookup"><span data-stu-id="61345-136">Therefore, you do not need to pass values in the `ulCodeRVA` and `dwImplFlags` parameters when calling `DefineMethod`.</span></span> <span data-ttu-id="61345-137">提供值的順序可以稍後透過[imetadataemit:: Setmethodimplflags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md)或[imetadataemit:: Setrva](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)視情況。</span><span class="sxs-lookup"><span data-stu-id="61345-137">The values can be supplied later through [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) or [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), as appropriate.</span></span>  
  
 <span data-ttu-id="61345-138">在某些情況下，例如平台引動過程 (PInvoke) 或 COM interop 案例中，不會提供方法主體，以及`ulCodeRVA`應該設定為零。</span><span class="sxs-lookup"><span data-stu-id="61345-138">In some situations, such as platform invocation (PInvoke) or COM interop scenarios, the method body will not be supplied, and `ulCodeRVA` should be set to zero.</span></span> <span data-ttu-id="61345-139">在這些情況下，此方法不應標記為抽象，因為執行階段會尋找實作。</span><span class="sxs-lookup"><span data-stu-id="61345-139">In these situations, the method should not be tagged as abstract, because the runtime will locate the implementation.</span></span>  
  
## <a name="defining-a-method-for-pinvoke"></a><span data-ttu-id="61345-140">定義方法為 PInvoke</span><span class="sxs-lookup"><span data-stu-id="61345-140">Defining a Method for PInvoke</span></span>  
 <span data-ttu-id="61345-141">對於透過 PInvoke 呼叫每個 unmanaged 函式，您必須定義受管理的方法，表示目標 unmanaged 函式。</span><span class="sxs-lookup"><span data-stu-id="61345-141">For each unmanaged function to be called through PInvoke, you must define a managed method that represents the target unmanaged function.</span></span> <span data-ttu-id="61345-142">若要定義受管理的方法，請使用`DefineMethod`與某些參數設為特定值，視 PInvoke 中使用的方式而定：</span><span class="sxs-lookup"><span data-stu-id="61345-142">To define the managed method, use `DefineMethod` with some of the parameters set to certain values, depending on the way in which PInvoke is used:</span></span>  
  
-   <span data-ttu-id="61345-143">True PInvoke-牽涉到位於 unmanaged DLL 中的外部的 unmanaged 方法的引動過程。</span><span class="sxs-lookup"><span data-stu-id="61345-143">True PInvoke - involves invocation of an external unmanaged method that resides in an unmanaged DLL.</span></span>  
  
-   <span data-ttu-id="61345-144">本機 PInvoke-包含內嵌在目前的受管理模組的原生 unmanaged 方法的引動過程。</span><span class="sxs-lookup"><span data-stu-id="61345-144">Local PInvoke - involves invocation of a native unmanaged method that is embedded in the current managed module.</span></span>  
  
 <span data-ttu-id="61345-145">下表提供的參數設定。</span><span class="sxs-lookup"><span data-stu-id="61345-145">The parameter settings are given in the following table.</span></span>  
  
|<span data-ttu-id="61345-146">參數</span><span class="sxs-lookup"><span data-stu-id="61345-146">Parameter</span></span>|<span data-ttu-id="61345-147">值，則為 true 的 PInvoke</span><span class="sxs-lookup"><span data-stu-id="61345-147">Values for true PInvoke</span></span>|<span data-ttu-id="61345-148">本機 PInvoke 值</span><span class="sxs-lookup"><span data-stu-id="61345-148">Values for local PInvoke</span></span>|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||<span data-ttu-id="61345-149">設定`mdStatic`; 清除`mdSynchronized`和`mdAbstract`。</span><span class="sxs-lookup"><span data-stu-id="61345-149">Set `mdStatic`; clear `mdSynchronized` and `mdAbstract`.</span></span>|  
|`pvSigBlob`|<span data-ttu-id="61345-150">有效 common language runtime (CLR) 方法簽章以有效的參數將 managed 類型。</span><span class="sxs-lookup"><span data-stu-id="61345-150">A valid common language runtime (CLR) method signature with parameters that are valid managed types.</span></span>|<span data-ttu-id="61345-151">有效的 CLR 方法簽章，以有效的參數將 managed 類型。</span><span class="sxs-lookup"><span data-stu-id="61345-151">A valid CLR method signature with parameters that are valid managed types.</span></span>|  
|`ulCodeRVA`||<span data-ttu-id="61345-152">0</span><span class="sxs-lookup"><span data-stu-id="61345-152">0</span></span>|  
|`dwImplFlags`|<span data-ttu-id="61345-153">設定`miCil`和`miManaged`。</span><span class="sxs-lookup"><span data-stu-id="61345-153">Set `miCil` and `miManaged`.</span></span>|<span data-ttu-id="61345-154">設定`miNative`和`miUnmanaged`。</span><span class="sxs-lookup"><span data-stu-id="61345-154">Set `miNative` and `miUnmanaged`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="61345-155">需求</span><span class="sxs-lookup"><span data-stu-id="61345-155">Requirements</span></span>  
 <span data-ttu-id="61345-156">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="61345-156">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61345-157">**標頭：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="61345-157">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="61345-158">**程式庫：**做為 MSCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="61345-158">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="61345-159">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61345-159">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61345-160">另請參閱</span><span class="sxs-lookup"><span data-stu-id="61345-160">See Also</span></span>  
 [<span data-ttu-id="61345-161">IMetaDataEmit 介面</span><span class="sxs-lookup"><span data-stu-id="61345-161">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="61345-162">IMetaDataEmit2 介面</span><span class="sxs-lookup"><span data-stu-id="61345-162">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)