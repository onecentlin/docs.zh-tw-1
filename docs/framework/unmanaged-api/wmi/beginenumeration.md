---
title: "BeginEnumeration 函式 （Unmanaged API 參考）"
description: "BeginEnumeration 函式會列舉值重設為開頭的列舉型別"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: BeginEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: BeginEnumeration
helpviewer_keywords: BeginEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 12a742774bff22030bdfaaa34e431059e016a4bf
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2017
---
# <a name="beginenumeration-function"></a><span data-ttu-id="c3196-103">BeginEnumeration 函式</span><span class="sxs-lookup"><span data-stu-id="c3196-103">BeginEnumeration function</span></span>
<span data-ttu-id="c3196-104">將列舉值重設回列舉的開頭。</span><span class="sxs-lookup"><span data-stu-id="c3196-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="c3196-105">語法</span><span class="sxs-lookup"><span data-stu-id="c3196-105">Syntax</span></span>  
  
```  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="c3196-106">參數</span><span class="sxs-lookup"><span data-stu-id="c3196-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="c3196-107">[in]未使用這個參數。</span><span class="sxs-lookup"><span data-stu-id="c3196-107">[in] This parameter is unused.</span></span>

<span data-ttu-id="c3196-108">`ptr`[in]指標[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)執行個體。</span><span class="sxs-lookup"><span data-stu-id="c3196-108">`ptr` [in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="c3196-109">[in]旗標或描述中值的位元組合[備註](#remarks)控制屬性包含在列舉中的區段。</span><span class="sxs-lookup"><span data-stu-id="c3196-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="c3196-110">傳回值</span><span class="sxs-lookup"><span data-stu-id="c3196-110">Return value</span></span>

<span data-ttu-id="c3196-111">這個函式傳回下列值會定義在*WbemCli.h*標頭檔，或者您可以定義它們以常數的形式在程式碼中：</span><span class="sxs-lookup"><span data-stu-id="c3196-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c3196-112">常數</span><span class="sxs-lookup"><span data-stu-id="c3196-112">Constant</span></span>  |<span data-ttu-id="c3196-113">值</span><span class="sxs-lookup"><span data-stu-id="c3196-113">Value</span></span>  |<span data-ttu-id="c3196-114">說明</span><span class="sxs-lookup"><span data-stu-id="c3196-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c3196-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c3196-115">0x80041008</span></span> | <span data-ttu-id="c3196-116">中的旗標的組合`lEnumFlags`無效，或是無效的引數所指定。</span><span class="sxs-lookup"><span data-stu-id="c3196-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="c3196-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="c3196-117">0x8004101d</span></span> | <span data-ttu-id="c3196-118">第二個呼叫`BeginEnumeration`所沒有的中間呼叫[ `EndEnumeration` ](endenumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="c3196-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="c3196-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="c3196-119">0x80041006</span></span> | <span data-ttu-id="c3196-120">使用開始新的列舉型別沒有足夠的記憶體。</span><span class="sxs-lookup"><span data-stu-id="c3196-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="c3196-121">0</span><span class="sxs-lookup"><span data-stu-id="c3196-121">0</span></span> | <span data-ttu-id="c3196-122">函式呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="c3196-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="c3196-123">備註</span><span class="sxs-lookup"><span data-stu-id="c3196-123">Remarks</span></span>

<span data-ttu-id="c3196-124">此函式會包裝呼叫[IWbemClassObject::BeginEnumeration](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="c3196-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) method.</span></span>

<span data-ttu-id="c3196-125">可以做為傳遞的旗標`lEnumFlags`引數中所定義*WbemCli.h*標頭檔，或者您可以定義它們以常數的形式在程式碼中。</span><span class="sxs-lookup"><span data-stu-id="c3196-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="c3196-126">您可以結合任何旗標，任何其他群組的每個群組從一個旗標。</span><span class="sxs-lookup"><span data-stu-id="c3196-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="c3196-127">不過，從相同群組的旗標互斥。</span><span class="sxs-lookup"><span data-stu-id="c3196-127">However, flags from the same group are mutually exclusive.</span></span> 

<span data-ttu-id="c3196-128">**群組 1**</span><span class="sxs-lookup"><span data-stu-id="c3196-128">**Group 1**</span></span>

|<span data-ttu-id="c3196-129">常數</span><span class="sxs-lookup"><span data-stu-id="c3196-129">Constant</span></span>  |<span data-ttu-id="c3196-130">值</span><span class="sxs-lookup"><span data-stu-id="c3196-130">Value</span></span>  |<span data-ttu-id="c3196-131">說明</span><span class="sxs-lookup"><span data-stu-id="c3196-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="c3196-132">0x4</span><span class="sxs-lookup"><span data-stu-id="c3196-132">0x4</span></span> | <span data-ttu-id="c3196-133">包含構成只在索引鍵屬性。</span><span class="sxs-lookup"><span data-stu-id="c3196-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="c3196-134">0x8</span><span class="sxs-lookup"><span data-stu-id="c3196-134">0x8</span></span> | <span data-ttu-id="c3196-135">包含僅限物件參考的內容。</span><span class="sxs-lookup"><span data-stu-id="c3196-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="c3196-136">**群組 2**</span><span class="sxs-lookup"><span data-stu-id="c3196-136">**Group 2**</span></span>

<span data-ttu-id="c3196-137">常數</span><span class="sxs-lookup"><span data-stu-id="c3196-137">Constant</span></span>  |<span data-ttu-id="c3196-138">值</span><span class="sxs-lookup"><span data-stu-id="c3196-138">Value</span></span>  |<span data-ttu-id="c3196-139">說明</span><span class="sxs-lookup"><span data-stu-id="c3196-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="c3196-140">0x30</span><span class="sxs-lookup"><span data-stu-id="c3196-140">0x30</span></span> | <span data-ttu-id="c3196-141">限制只系統屬性的列舉型別。</span><span class="sxs-lookup"><span data-stu-id="c3196-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="c3196-142">0x40</span><span class="sxs-lookup"><span data-stu-id="c3196-142">0x40</span></span> | <span data-ttu-id="c3196-143">包含本機和傳播屬性，但排除在列舉中的系統屬性。</span><span class="sxs-lookup"><span data-stu-id="c3196-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="c3196-144">針對類別：</span><span class="sxs-lookup"><span data-stu-id="c3196-144">For classes:</span></span>

<span data-ttu-id="c3196-145">常數</span><span class="sxs-lookup"><span data-stu-id="c3196-145">Constant</span></span>  |<span data-ttu-id="c3196-146">值</span><span class="sxs-lookup"><span data-stu-id="c3196-146">Value</span></span>  |<span data-ttu-id="c3196-147">說明</span><span class="sxs-lookup"><span data-stu-id="c3196-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="c3196-148">0x100</span><span class="sxs-lookup"><span data-stu-id="c3196-148">0x100</span></span> | <span data-ttu-id="c3196-149">限制覆寫類別定義中的屬性的列舉型別。</span><span class="sxs-lookup"><span data-stu-id="c3196-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="c3196-150">0x100</span><span class="sxs-lookup"><span data-stu-id="c3196-150">0x100</span></span> | <span data-ttu-id="c3196-151">限制覆寫目前的類別定義中的屬性並定義於類別的新屬性的列舉型別。</span><span class="sxs-lookup"><span data-stu-id="c3196-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="c3196-152">0x300</span><span class="sxs-lookup"><span data-stu-id="c3196-152">0x300</span></span> | <span data-ttu-id="c3196-153">遮罩 （而不是一個旗標），套用對`lEnumFlags`值來檢查是否有任一個`WBEM_FLAG_CLASS_OVERRIDES_ONLY`或`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES`設定。</span><span class="sxs-lookup"><span data-stu-id="c3196-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="c3196-154">0x10</span><span class="sxs-lookup"><span data-stu-id="c3196-154">0x10</span></span> | <span data-ttu-id="c3196-155">限制屬性所定義或修改此類別本身中的列舉型別。</span><span class="sxs-lookup"><span data-stu-id="c3196-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="c3196-156">0x20</span><span class="sxs-lookup"><span data-stu-id="c3196-156">0x20</span></span> | <span data-ttu-id="c3196-157">限制的列舉型別都繼承自基底類別的屬性。</span><span class="sxs-lookup"><span data-stu-id="c3196-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="c3196-158">執行個體：</span><span class="sxs-lookup"><span data-stu-id="c3196-158">For instances:</span></span>

<span data-ttu-id="c3196-159">常數</span><span class="sxs-lookup"><span data-stu-id="c3196-159">Constant</span></span>  |<span data-ttu-id="c3196-160">值</span><span class="sxs-lookup"><span data-stu-id="c3196-160">Value</span></span>  |<span data-ttu-id="c3196-161">說明</span><span class="sxs-lookup"><span data-stu-id="c3196-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="c3196-162">0x10</span><span class="sxs-lookup"><span data-stu-id="c3196-162">0x10</span></span> | <span data-ttu-id="c3196-163">限制屬性所定義或修改此類別本身中的列舉型別。</span><span class="sxs-lookup"><span data-stu-id="c3196-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="c3196-164">0x20</span><span class="sxs-lookup"><span data-stu-id="c3196-164">0x20</span></span> | <span data-ttu-id="c3196-165">限制的列舉型別都繼承自基底類別的屬性。</span><span class="sxs-lookup"><span data-stu-id="c3196-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |


## <a name="requirements"></a><span data-ttu-id="c3196-166">需求</span><span class="sxs-lookup"><span data-stu-id="c3196-166">Requirements</span></span>  
 <span data-ttu-id="c3196-167">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c3196-167">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3196-168">**標頭：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c3196-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c3196-169">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c3196-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3196-170">請參閱</span><span class="sxs-lookup"><span data-stu-id="c3196-170">See also</span></span>  
[<span data-ttu-id="c3196-171">WMI 和效能計數器 （Unmanaged API 參考）</span><span class="sxs-lookup"><span data-stu-id="c3196-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)