---
title: "Método ISymUnmanagedWriter::Abort"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.Abort
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::Abort
helpviewer_keywords:
- ISymUnmanagedWriter::Abort method [.NET Framework debugging]
- Abort method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 416b220f-38d4-48e0-bb49-d2faa7366702
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 29dd11972e8db80f36820bba1eb679070d02146e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="41462-102">Método ISymUnmanagedWriter::Abort</span><span class="sxs-lookup"><span data-stu-id="41462-102">ISymUnmanagedWriter::Abort Method</span></span>
<span data-ttu-id="41462-103">Fecha o gravador de símbolo sem confirmar os símbolos para o armazenamento de símbolo.</span><span class="sxs-lookup"><span data-stu-id="41462-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="41462-104">Após essa chamada, o gravador de símbolo se torna inválido para obter informações mais atualizadas.</span><span class="sxs-lookup"><span data-stu-id="41462-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="41462-105">Para confirmar os símbolos e fechar o gravador de símbolo, use o [Isymunmanagedwriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) método em vez disso.</span><span class="sxs-lookup"><span data-stu-id="41462-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41462-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="41462-106">Syntax</span></span>  
  
```  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="41462-107">Valor de retorno</span><span class="sxs-lookup"><span data-stu-id="41462-107">Return Value</span></span>  
 <span data-ttu-id="41462-108">S_OK se o método for bem-sucedido; Caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="41462-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41462-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41462-109">Requirements</span></span>  
 <span data-ttu-id="41462-110">**Cabeçalho:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="41462-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41462-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="41462-111">See Also</span></span>  
 [<span data-ttu-id="41462-112">Interface ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="41462-112">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)