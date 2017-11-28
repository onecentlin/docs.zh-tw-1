---
title: "ASSEMBLY_INFO 結構"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ASSEMBLY_INFO
api_location: fusion.dll
api_type: COM
f1_keywords: ASSEMBLY_INFO
helpviewer_keywords: ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d532bbd2d338f942c09c4213620468a3361db5f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="assemblyinfo-structure"></a><span data-ttu-id="ee901-102">ASSEMBLY_INFO 結構</span><span class="sxs-lookup"><span data-stu-id="ee901-102">ASSEMBLY_INFO Structure</span></span>
<span data-ttu-id="ee901-103">包含在全域組件快取中註冊組件的資訊。</span><span class="sxs-lookup"><span data-stu-id="ee901-103">Contains information about an assembly that is registered in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee901-104">語法</span><span class="sxs-lookup"><span data-stu-id="ee901-104">Syntax</span></span>  
  
```  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="ee901-105">成員</span><span class="sxs-lookup"><span data-stu-id="ee901-105">Members</span></span>  
  
|<span data-ttu-id="ee901-106">成員</span><span class="sxs-lookup"><span data-stu-id="ee901-106">Member</span></span>|<span data-ttu-id="ee901-107">說明</span><span class="sxs-lookup"><span data-stu-id="ee901-107">Description</span></span>|  
|------------|-----------------|  
|`cbAssemblyInfo`|<span data-ttu-id="ee901-108">以位元組為單位的結構大小。</span><span class="sxs-lookup"><span data-stu-id="ee901-108">The size, in bytes, of the structure.</span></span> <span data-ttu-id="ee901-109">這個欄位被保留供未來擴充。</span><span class="sxs-lookup"><span data-stu-id="ee901-109">This field is reserved for future extensibility.</span></span>|  
|`dwAssemblyFlags`|<span data-ttu-id="ee901-110">旗標，表示組件的相關的安裝詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ee901-110">Flags that indicate installation details about the assembly.</span></span> <span data-ttu-id="ee901-111">支援下列值：</span><span class="sxs-lookup"><span data-stu-id="ee901-111">The following values are supported:</span></span><br /><br /> <span data-ttu-id="ee901-112">-ASSEMBLYINFO_FLAG_INSTALLED 值，指出已安裝的組件。</span><span class="sxs-lookup"><span data-stu-id="ee901-112">-   The ASSEMBLYINFO_FLAG_INSTALLED value, which indicates that the assembly is installed.</span></span> <span data-ttu-id="ee901-113">目前的.NET framework 版本一律設定`dwAssemblyFlags`為這個值。</span><span class="sxs-lookup"><span data-stu-id="ee901-113">The current version of the .NET Framework always sets `dwAssemblyFlags` to this value.</span></span><br /><span data-ttu-id="ee901-114">表示組件是常駐裝載-ASSEMBLYINFO_FLAG_PAYLOADRESIDENT 值。</span><span class="sxs-lookup"><span data-stu-id="ee901-114">-   The ASSEMBLYINFO_FLAG_PAYLOADRESIDENT value, which indicates that the assembly is a payload resident.</span></span> <span data-ttu-id="ee901-115">目前的.NET framework 版本永遠不會設定`dwAssemblyFlags`為這個值。</span><span class="sxs-lookup"><span data-stu-id="ee901-115">The current version of the .NET Framework never sets `dwAssemblyFlags` to this value.</span></span>|  
|`uliAssemblySizeInKB`|<span data-ttu-id="ee901-116">總大小，以 kb 為單位的組件包含的檔案。</span><span class="sxs-lookup"><span data-stu-id="ee901-116">The total size, in kilobytes, of the files that the assembly contains.</span></span>|  
|`pszCurrentAssemblyPathBuf`|<span data-ttu-id="ee901-117">資訊清單檔案會保留目前的路徑字串緩衝區的指標。</span><span class="sxs-lookup"><span data-stu-id="ee901-117">A pointer to a string buffer that holds the current path to the manifest file.</span></span> <span data-ttu-id="ee901-118">路徑必須以 null 字元結尾。</span><span class="sxs-lookup"><span data-stu-id="ee901-118">The path must end with a null character.</span></span>|  
|`cchBuf`|<span data-ttu-id="ee901-119">的寬字元數目，包括 null 結束字元，`pszCurrentAssemblyPathBuf`包含。</span><span class="sxs-lookup"><span data-stu-id="ee901-119">The number of wide characters, including the null terminator, that `pszCurrentAssemblyPathBuf` contains.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ee901-120">需求</span><span class="sxs-lookup"><span data-stu-id="ee901-120">Requirements</span></span>  
 <span data-ttu-id="ee901-121">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ee901-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee901-122">**標頭：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="ee901-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ee901-123">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee901-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee901-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ee901-124">See Also</span></span>  
 [<span data-ttu-id="ee901-125">融合結構</span><span class="sxs-lookup"><span data-stu-id="ee901-125">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [<span data-ttu-id="ee901-126">全域組件快取</span><span class="sxs-lookup"><span data-stu-id="ee901-126">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)