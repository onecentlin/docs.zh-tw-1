---
title: "ISymUnmanagedReader2 介面"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader2
helpviewer_keywords: ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b23e166249659b94d454070c01c003495d1018a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="29102-102">ISymUnmanagedReader2 介面</span><span class="sxs-lookup"><span data-stu-id="29102-102">ISymUnmanagedReader2 Interface</span></span>
<span data-ttu-id="29102-103">代表符號讀取器可存取文件、 方法和符號存放區內的變數。</span><span class="sxs-lookup"><span data-stu-id="29102-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="29102-104">這個介面延伸[ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)介面。</span><span class="sxs-lookup"><span data-stu-id="29102-104">This interface extends the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="29102-105">方法</span><span class="sxs-lookup"><span data-stu-id="29102-105">Methods</span></span>  
  
|<span data-ttu-id="29102-106">方法</span><span class="sxs-lookup"><span data-stu-id="29102-106">Method</span></span>|<span data-ttu-id="29102-107">說明</span><span class="sxs-lookup"><span data-stu-id="29102-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="29102-108">GetMethodByVersionPreRemap 方法</span><span class="sxs-lookup"><span data-stu-id="29102-108">GetMethodByVersionPreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="29102-109">取得符號讀取器方法，指定方法語彙基元和編輯後繼續版本號碼。</span><span class="sxs-lookup"><span data-stu-id="29102-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="29102-110">GetMethodsInDocument 方法</span><span class="sxs-lookup"><span data-stu-id="29102-110">GetMethodsInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="29102-111">取得具有所提供的文件中的程式行資訊的每個方法。</span><span class="sxs-lookup"><span data-stu-id="29102-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="29102-112">GetSymAttributePreRemap 方法</span><span class="sxs-lookup"><span data-stu-id="29102-112">GetSymAttributePreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="29102-113">取得其名稱為基礎的自訂屬性。</span><span class="sxs-lookup"><span data-stu-id="29102-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="29102-114">需求</span><span class="sxs-lookup"><span data-stu-id="29102-114">Requirements</span></span>  
 <span data-ttu-id="29102-115">**標頭：**於 CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="29102-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29102-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="29102-116">See Also</span></span>  
 [<span data-ttu-id="29102-117">診斷符號存放區介面</span><span class="sxs-lookup"><span data-stu-id="29102-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="29102-118">ISymUnmanagedReader 介面</span><span class="sxs-lookup"><span data-stu-id="29102-118">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)