---
title: "ISymUnmanagedReader::GetMethodsFromDocumentPosition 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetMethodsFromDocumentPosition
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetMethodsFromDocumentPosition
helpviewer_keywords:
- GetMethodsFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodsFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 83605f1e-e4f3-49e6-859b-f13cad68bb54
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7f82cf213e9bcc83055cfaa42b9acab9d395d405
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a><span data-ttu-id="ea789-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition 方法</span><span class="sxs-lookup"><span data-stu-id="ea789-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition Method</span></span>
<span data-ttu-id="ea789-103">傳回的陣列的方法，其中每個包含文件中指定位置的中斷點。</span><span class="sxs-lookup"><span data-stu-id="ea789-103">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea789-104">語法</span><span class="sxs-lookup"><span data-stu-id="ea789-104">Syntax</span></span>  
  
```  
HRESULT GetMethodsFromDocumentPosition (  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32 line,  
    [in]  ULONG32 column,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is (cMethod),  
        length_is (*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea789-105">參數</span><span class="sxs-lookup"><span data-stu-id="ea789-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="ea789-106">[in]指定的文件。</span><span class="sxs-lookup"><span data-stu-id="ea789-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="ea789-107">[in]指定的文件行。</span><span class="sxs-lookup"><span data-stu-id="ea789-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="ea789-108">[in]指定的文件的資料行。</span><span class="sxs-lookup"><span data-stu-id="ea789-108">[in] The column of the specified document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="ea789-109">[in] `pRetVal` 陣列的大小。</span><span class="sxs-lookup"><span data-stu-id="ea789-109">[in] The size of the `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="ea789-110">[out]此變數會接收中傳回的元素數目的指標`pRetVal`陣列。</span><span class="sxs-lookup"><span data-stu-id="ea789-110">[out] A pointer to a variable that receives the number of elements returned in the `pRetVal` array.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="ea789-111">[out]陣列的指標，其中每個指向[ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)物件，代表包含中斷點的方法。</span><span class="sxs-lookup"><span data-stu-id="ea789-111">[out] An array of pointers, each of which points to an [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) object that represents a method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ea789-112">傳回值</span><span class="sxs-lookup"><span data-stu-id="ea789-112">Return Value</span></span>  
 <span data-ttu-id="ea789-113">如果方法成功則為 S_OK否則，E_FAIL 或其他錯誤程式碼。</span><span class="sxs-lookup"><span data-stu-id="ea789-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea789-114">需求</span><span class="sxs-lookup"><span data-stu-id="ea789-114">Requirements</span></span>  
 <span data-ttu-id="ea789-115">**標頭：**於 CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ea789-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea789-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ea789-116">See Also</span></span>  
 [<span data-ttu-id="ea789-117">ISymUnmanagedReader 介面</span><span class="sxs-lookup"><span data-stu-id="ea789-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)