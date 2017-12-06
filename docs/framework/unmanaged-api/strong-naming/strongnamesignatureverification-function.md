---
title: "StrongNameSignatureVerification 函式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameSignatureVerification
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameSignatureVerification
helpviewer_keywords: StrongNameSignatureVerification function [.NET Framework strong naming]
ms.assetid: 933758dd-231e-4382-8819-242c0a13a4b7
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a2c04aba5b774b299e26be8dc532b894b6c6fad5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamesignatureverification-function"></a><span data-ttu-id="716cd-102">StrongNameSignatureVerification 函式</span><span class="sxs-lookup"><span data-stu-id="716cd-102">StrongNameSignatureVerification Function</span></span>
<span data-ttu-id="716cd-103">取得值，指出是否在提供的路徑上組件資訊清單包含強式名稱簽章，根據指定的旗標加以確認。</span><span class="sxs-lookup"><span data-stu-id="716cd-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
 <span data-ttu-id="716cd-104">此函式已被取代。</span><span class="sxs-lookup"><span data-stu-id="716cd-104">This function has been deprecated.</span></span> <span data-ttu-id="716cd-105">使用[iclrstrongname:: Strongnamesignatureverification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)方法改為。</span><span class="sxs-lookup"><span data-stu-id="716cd-105">Use the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="716cd-106">語法</span><span class="sxs-lookup"><span data-stu-id="716cd-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="716cd-107">參數</span><span class="sxs-lookup"><span data-stu-id="716cd-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="716cd-108">[in]可攜式執行 （.dll 或.exe） 檔來確認組件的路徑。</span><span class="sxs-lookup"><span data-stu-id="716cd-108">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="716cd-109">[in]若要修改的驗證行為的旗標。</span><span class="sxs-lookup"><span data-stu-id="716cd-109">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="716cd-110">支援下列值：</span><span class="sxs-lookup"><span data-stu-id="716cd-110">The following values are supported:</span></span>  
  
-   <span data-ttu-id="716cd-111">`SN_INFLAG_FORCE_VER`(0x00000001)-強制執行驗證，即使它是需要覆寫登錄設定。</span><span class="sxs-lookup"><span data-stu-id="716cd-111">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   <span data-ttu-id="716cd-112">`SN_INFLAG_INSTALL`(0x00000002)-指定驗證資訊清單的第一次。</span><span class="sxs-lookup"><span data-stu-id="716cd-112">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
-   <span data-ttu-id="716cd-113">`SN_INFLAG_ADMIN_ACCESS`(0x00000004)-指定快取可讓擁有系統管理權限的使用者存取。</span><span class="sxs-lookup"><span data-stu-id="716cd-113">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   <span data-ttu-id="716cd-114">`SN_INFLAG_USER_ACCESS`(0x00000008)-指定的組件都是只能由目前的使用者存取。</span><span class="sxs-lookup"><span data-stu-id="716cd-114">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   <span data-ttu-id="716cd-115">`SN_INFLAG_ALL_ACCESS`(0x00000010)-指定快取會提供任何保證的存取限制。</span><span class="sxs-lookup"><span data-stu-id="716cd-115">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   <span data-ttu-id="716cd-116">`SN_INFLAG_RUNTIME`(0x80000000)-保留供內部偵錯。</span><span class="sxs-lookup"><span data-stu-id="716cd-116">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="716cd-117">[out]旗標，表示是否已驗證的強式名稱簽章。</span><span class="sxs-lookup"><span data-stu-id="716cd-117">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="716cd-118">支援下列值：</span><span class="sxs-lookup"><span data-stu-id="716cd-118">The following value is supported:</span></span>  
  
-   <span data-ttu-id="716cd-119">`SN_OUTFLAG_WAS_VERIFIED`(0x00000001)-此值設為`false`來指定驗證成功登錄設定所造成。</span><span class="sxs-lookup"><span data-stu-id="716cd-119">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="716cd-120">傳回值</span><span class="sxs-lookup"><span data-stu-id="716cd-120">Return Value</span></span>  
 <span data-ttu-id="716cd-121">`true`如果驗證成功。否則， `false`。</span><span class="sxs-lookup"><span data-stu-id="716cd-121">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="716cd-122">需求</span><span class="sxs-lookup"><span data-stu-id="716cd-122">Requirements</span></span>  
 <span data-ttu-id="716cd-123">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="716cd-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="716cd-124">**標頭：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="716cd-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="716cd-125">**程式庫：**包含做為 MsCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="716cd-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="716cd-126">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="716cd-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="716cd-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="716cd-127">See Also</span></span>  
 [<span data-ttu-id="716cd-128">StrongNameSignatureVerification 方法</span><span class="sxs-lookup"><span data-stu-id="716cd-128">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [<span data-ttu-id="716cd-129">StrongNameSignatureVerificationEx 方法</span><span class="sxs-lookup"><span data-stu-id="716cd-129">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [<span data-ttu-id="716cd-130">ICLRStrongName 介面</span><span class="sxs-lookup"><span data-stu-id="716cd-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)