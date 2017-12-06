---
title: "ICLRDataTarget3::GetExceptionThreadID 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICLRDataTarget3.GetExceptionThreadID
api_location: mscordbi.dll
api_type: COM
ms.assetid: 307d6ac7-4a86-45f3-999d-6b47004a68f2
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f05d264d4bf55de930a07eda6bf369570c8b7fa8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a><span data-ttu-id="d4c62-102">ICLRDataTarget3::GetExceptionThreadID 方法</span><span class="sxs-lookup"><span data-stu-id="d4c62-102">ICLRDataTarget3::GetExceptionThreadID Method</span></span>
<span data-ttu-id="d4c62-103">由通用語言執行平台 (CLR) 資料存取服務呼叫，以取得擲回例外狀況之執行緒的 ID。</span><span class="sxs-lookup"><span data-stu-id="d4c62-103">Called by the common language runtime (CLR) data access services to get the ID of the thread that threw the exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4c62-104">語法</span><span class="sxs-lookup"><span data-stu-id="d4c62-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4c62-105">參數</span><span class="sxs-lookup"><span data-stu-id="d4c62-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="d4c62-106">[out] 擲回例外狀況之執行緒的 ID。</span><span class="sxs-lookup"><span data-stu-id="d4c62-106">[out] The ID of the thread that threw the exception.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4c62-107">傳回值</span><span class="sxs-lookup"><span data-stu-id="d4c62-107">Return Value</span></span>  
 <span data-ttu-id="d4c62-108">如果成功，傳回值為 `S_OK`，如果失敗，則傳回失敗 `HRESULT` 程式碼。</span><span class="sxs-lookup"><span data-stu-id="d4c62-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="d4c62-109">`HRESULT` 程式碼可以包括 (但不限於) 下列項目：</span><span class="sxs-lookup"><span data-stu-id="d4c62-109">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="d4c62-110">傳回碼</span><span class="sxs-lookup"><span data-stu-id="d4c62-110">Return code</span></span>|<span data-ttu-id="d4c62-111">描述</span><span class="sxs-lookup"><span data-stu-id="d4c62-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="d4c62-112">方法成功。</span><span class="sxs-lookup"><span data-stu-id="d4c62-112">Method succeeded.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="d4c62-113">找不到例外狀況的有效執行緒 ID。</span><span class="sxs-lookup"><span data-stu-id="d4c62-113">Could not find a valid thread ID for the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4c62-114">備註</span><span class="sxs-lookup"><span data-stu-id="d4c62-114">Remarks</span></span>  
 <span data-ttu-id="d4c62-115">此方法是由偵錯應用程式的作者來實作。</span><span class="sxs-lookup"><span data-stu-id="d4c62-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4c62-116">需求</span><span class="sxs-lookup"><span data-stu-id="d4c62-116">Requirements</span></span>  
 <span data-ttu-id="d4c62-117">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d4c62-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4c62-118">**標頭：** ClrData.idl、 ClrData.h</span><span class="sxs-lookup"><span data-stu-id="d4c62-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="d4c62-119">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4c62-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4c62-120">**.NET framework 版本：**[!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4c62-120">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4c62-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d4c62-121">See Also</span></span>  
 [<span data-ttu-id="d4c62-122">ICLRDataTarget3 介面</span><span class="sxs-lookup"><span data-stu-id="d4c62-122">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [<span data-ttu-id="d4c62-123">GetExceptionContextRecord 方法</span><span class="sxs-lookup"><span data-stu-id="d4c62-123">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)  
 [<span data-ttu-id="d4c62-124">GetExceptionRecord 方法</span><span class="sxs-lookup"><span data-stu-id="d4c62-124">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)