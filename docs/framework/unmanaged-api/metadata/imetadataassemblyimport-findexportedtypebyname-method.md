---
title: "IMetaDataAssemblyImport::FindExportedTypeByName 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.FindExportedTypeByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::FindExportedTypeByName
helpviewer_keywords:
- FindExportedTypeByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindExportedTypeByName method [.NET Framework metadata]
ms.assetid: 46264b2c-574d-4dde-aafc-77187a104fdd
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b7ef0e09cb5a44e612e545fc4ee7278c2d128174
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="269fa-102">IMetaDataAssemblyImport::FindExportedTypeByName 方法</span><span class="sxs-lookup"><span data-stu-id="269fa-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="269fa-103">取得指標匯出的類型，指定其名稱與封入型別。</span><span class="sxs-lookup"><span data-stu-id="269fa-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="269fa-104">語法</span><span class="sxs-lookup"><span data-stu-id="269fa-104">Syntax</span></span>  
  
```  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,   
    [in]  mdToken           mdtExportedType,   
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="269fa-105">參數</span><span class="sxs-lookup"><span data-stu-id="269fa-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="269fa-106">[in]匯出的類型名稱。</span><span class="sxs-lookup"><span data-stu-id="269fa-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="269fa-107">[in]匯出類型的封入類別之中繼資料語彙基元。</span><span class="sxs-lookup"><span data-stu-id="269fa-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="269fa-108">這個值是`mdExportedTypeNil`如果所要求的匯出類型不是巢狀的類型。</span><span class="sxs-lookup"><span data-stu-id="269fa-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="269fa-109">[out]指標`mdExportedType`表示匯出的類型語彙基元。</span><span class="sxs-lookup"><span data-stu-id="269fa-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="269fa-110">備註</span><span class="sxs-lookup"><span data-stu-id="269fa-110">Remarks</span></span>  
 <span data-ttu-id="269fa-111">`FindExportedTypeByName`方法會使用標準來解析參考的 common language runtime 所採用的規則。</span><span class="sxs-lookup"><span data-stu-id="269fa-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="269fa-112">需求</span><span class="sxs-lookup"><span data-stu-id="269fa-112">Requirements</span></span>  
 <span data-ttu-id="269fa-113">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="269fa-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="269fa-114">**標頭：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="269fa-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="269fa-115">**程式庫：**做為 MsCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="269fa-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="269fa-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="269fa-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="269fa-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="269fa-117">See Also</span></span>  
 [<span data-ttu-id="269fa-118">IMetaDataAssemblyImport 介面</span><span class="sxs-lookup"><span data-stu-id="269fa-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="269fa-119">執行階段如何找出組件</span><span class="sxs-lookup"><span data-stu-id="269fa-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)