---
title: "Método ISymUnmanagedNamespace::GetNamespaces"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedNamespace.GetNamespaces
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedNamespace::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedNamespace::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 0ea9d9af-8709-4a46-872b-f54d9e840088
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ef84358443520aa0548ef2244c2537b7a593f9e3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="18e13-102">Método ISymUnmanagedNamespace::GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="18e13-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>
<span data-ttu-id="18e13-103">Obtém o filho desse namespace.</span><span class="sxs-lookup"><span data-stu-id="18e13-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18e13-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="18e13-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="18e13-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="18e13-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="18e13-106">[in] Um `ULONG32` que indica o tamanho do `namespaces` matriz.</span><span class="sxs-lookup"><span data-stu-id="18e13-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="18e13-107">[out] Um ponteiro para um `ULONG32` que recebe o tamanho, em caracteres, do buffer necessário para conter os namespaces.</span><span class="sxs-lookup"><span data-stu-id="18e13-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="18e13-108">[out] Um ponteiro para o buffer que contém os namespaces.</span><span class="sxs-lookup"><span data-stu-id="18e13-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18e13-109">Valor de retorno</span><span class="sxs-lookup"><span data-stu-id="18e13-109">Return Value</span></span>  
 <span data-ttu-id="18e13-110">S_OK se o método for bem-sucedido; Caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="18e13-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18e13-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="18e13-111">Requirements</span></span>  
 <span data-ttu-id="18e13-112">**Cabeçalho:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="18e13-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18e13-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="18e13-113">See Also</span></span>  
 [<span data-ttu-id="18e13-114">Interface ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="18e13-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)