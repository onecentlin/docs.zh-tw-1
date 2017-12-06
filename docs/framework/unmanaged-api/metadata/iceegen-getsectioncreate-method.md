---
title: "ICeeGen::GetSectionCreate 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.GetSectionCreate
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::GetSectionCreate
helpviewer_keywords:
- ICeeGen::GetSectionCreate method [.NET Framework metadata]
- GetSectionCreate method [.NET Framework metadata]
ms.assetid: 154b2460-59ce-4874-a9f2-1b3353486ac5
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2ea9cb20b62e1b1fa8e726ba0c49c5e24202530c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="iceegengetsectioncreate-method"></a><span data-ttu-id="49f22-102">ICeeGen::GetSectionCreate 方法</span><span class="sxs-lookup"><span data-stu-id="49f22-102">ICeeGen::GetSectionCreate Method</span></span>
<span data-ttu-id="49f22-103">產生並取得使用指定的名稱和旗標值的程式碼區段。</span><span class="sxs-lookup"><span data-stu-id="49f22-103">Generates and gets a code section using the specified name and flag values.</span></span>  
  
 <span data-ttu-id="49f22-104">這個方法已經過時，不應使用。</span><span class="sxs-lookup"><span data-stu-id="49f22-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49f22-105">語法</span><span class="sxs-lookup"><span data-stu-id="49f22-105">Syntax</span></span>  
  
```  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="49f22-106">參數</span><span class="sxs-lookup"><span data-stu-id="49f22-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="49f22-107">[in]指定要建立的區段名稱的字串指標。</span><span class="sxs-lookup"><span data-stu-id="49f22-107">[in] A pointer to a string that specifies the name of the section to be created.</span></span>  
  
 `flags`  
 <span data-ttu-id="49f22-108">[in]指定選項的旗標。</span><span class="sxs-lookup"><span data-stu-id="49f22-108">[in] Flags that specify options.</span></span>  
  
 `section`  
 <span data-ttu-id="49f22-109">[out]指標，新建的程式碼區段。</span><span class="sxs-lookup"><span data-stu-id="49f22-109">[out] A pointer to the newly created code section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49f22-110">備註</span><span class="sxs-lookup"><span data-stu-id="49f22-110">Remarks</span></span>  
 <span data-ttu-id="49f22-111">呼叫`GetSectionCreate`只有當您有不由其他方法處理的特殊區段需求。</span><span class="sxs-lookup"><span data-stu-id="49f22-111">Call `GetSectionCreate` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49f22-112">需求</span><span class="sxs-lookup"><span data-stu-id="49f22-112">Requirements</span></span>  
 <span data-ttu-id="49f22-113">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="49f22-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49f22-114">**標頭：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="49f22-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="49f22-115">**程式庫：**做為 MsCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="49f22-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="49f22-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49f22-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49f22-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="49f22-117">See Also</span></span>  
 [<span data-ttu-id="49f22-118">ICeeGen 介面</span><span class="sxs-lookup"><span data-stu-id="49f22-118">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)