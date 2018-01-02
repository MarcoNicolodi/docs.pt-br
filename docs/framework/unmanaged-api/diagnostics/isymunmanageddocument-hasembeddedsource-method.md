---
title: "Método ISymUnmanagedDocument::HasEmbeddedSource"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.HasEmbeddedSource
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::HasEmbeddedSource
helpviewer_keywords:
- HasEmbeddedSource method [.NET Framework debugging]
- ISymUnmanagedDocument::HasEmbeddedSource method [.NET Framework debugging]
ms.assetid: 385fc4d3-365c-4645-b7b0-6c4c5344b79f
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 383b2070dcc5407e6033021cef20beed19319e65
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="afa8f-102">Método ISymUnmanagedDocument::HasEmbeddedSource</span><span class="sxs-lookup"><span data-stu-id="afa8f-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>
<span data-ttu-id="afa8f-103">Retorna `true` se o documento tem origem inserida nos símbolos de depuração; caso contrário, retornará `false`.</span><span class="sxs-lookup"><span data-stu-id="afa8f-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afa8f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="afa8f-104">Syntax</span></span>  
  
```  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="afa8f-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="afa8f-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="afa8f-106">[out] Um ponteiro para uma variável que indica se o documento tem origem inserida nos símbolos de depuração.</span><span class="sxs-lookup"><span data-stu-id="afa8f-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="afa8f-107">Valor de retorno</span><span class="sxs-lookup"><span data-stu-id="afa8f-107">Return Value</span></span>  
 <span data-ttu-id="afa8f-108">S_OK se o método for bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="afa8f-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afa8f-109">Consulte também</span><span class="sxs-lookup"><span data-stu-id="afa8f-109">See Also</span></span>  
 [<span data-ttu-id="afa8f-110">Interface ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="afa8f-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)