---
title: "Método ICorDebugThread4::HadUnhandledException"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread4.HadUnhandledException Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread4::HadUnhandledException
helpviewer_keywords:
- ICorDebugThread4::HadUnhandledException method [.NET Framework debugging]
- HadUnhandledException method [.NET Framework debugging]
ms.assetid: 05558daa-39e2-4c38-aeaf-e2aec4a09468
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ea29fa02e74c204cde003b18520bf512b0d21d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugthread4hadunhandledexception-method"></a><span data-ttu-id="3cfe5-102">Método ICorDebugThread4::HadUnhandledException</span><span class="sxs-lookup"><span data-stu-id="3cfe5-102">ICorDebugThread4::HadUnhandledException Method</span></span>
<span data-ttu-id="3cfe5-103">Indica se o thread nunca teve uma exceção sem tratamento.</span><span class="sxs-lookup"><span data-stu-id="3cfe5-103">Indicates whether the thread has ever had an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cfe5-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3cfe5-104">Syntax</span></span>  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3cfe5-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="3cfe5-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="3cfe5-106">[out] Um ponteiro para o endereço de uma enumeração ordenada de [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) estruturas.</span><span class="sxs-lookup"><span data-stu-id="3cfe5-106">[out] A pointer to the address of an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3cfe5-107">Valor de retorno</span><span class="sxs-lookup"><span data-stu-id="3cfe5-107">Return Value</span></span>  
 <span data-ttu-id="3cfe5-108">Este método retorna a seguintes HRESULTs específicos, bem como o HRESULT erros que indicam falha do método.</span><span class="sxs-lookup"><span data-stu-id="3cfe5-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3cfe5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3cfe5-109">HRESULT</span></span>|<span data-ttu-id="3cfe5-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="3cfe5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3cfe5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3cfe5-111">S_OK</span></span>|<span data-ttu-id="3cfe5-112">O thread teve uma exceção sem tratamento desde sua criação.</span><span class="sxs-lookup"><span data-stu-id="3cfe5-112">The thread has had an unhandled exception since its creation.</span></span>|  
|<span data-ttu-id="3cfe5-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="3cfe5-113">S_FALSE</span></span>|<span data-ttu-id="3cfe5-114">O thread nunca teve uma exceção sem tratamento.</span><span class="sxs-lookup"><span data-stu-id="3cfe5-114">The thread has never had an unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cfe5-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="3cfe5-115">Remarks</span></span>  
 <span data-ttu-id="3cfe5-116">Este método indica se o thread nunca teve uma exceção sem tratamento.</span><span class="sxs-lookup"><span data-stu-id="3cfe5-116">This method indicates whether the thread has ever had an unhandled exception.</span></span> <span data-ttu-id="3cfe5-117">No momento do retorno de chamada de exceção sem tratamento é acionado ou anexação JIT nativo é iniciado, esse método é garantido para retornar S_OK.</span><span class="sxs-lookup"><span data-stu-id="3cfe5-117">By the time the unhandled exception callback is triggered or native JIT-attach is initiated, this method is guaranteed to return S_OK.</span></span> <span data-ttu-id="3cfe5-118">Não há nenhuma garantia de que o [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) método retornará a exceção não tratada; no entanto, ele irá se o processo não ainda sido continua depois de obter o retorno de chamada de exceção sem tratamento ou após nativo de anexação JIT.</span><span class="sxs-lookup"><span data-stu-id="3cfe5-118">There is no guarantee that the [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) method will return the unhandled exception; however, it will if the process has not yet been continued after getting the unhandled exception callback or upon native JIT-attach.</span></span> <span data-ttu-id="3cfe5-119">Além disso, é possível (embora improvável) para ter mais de um thread com uma exceção sem tratamento no momento nativo de anexação JIT é disparado.</span><span class="sxs-lookup"><span data-stu-id="3cfe5-119">Furthermore, it is possible (although unlikely) to have more than one thread with an unhandled exception at the time native JIT-attach is triggered.</span></span> <span data-ttu-id="3cfe5-120">Nesse caso, não há nenhuma maneira de determinar qual exceção acionada a anexação JIT.</span><span class="sxs-lookup"><span data-stu-id="3cfe5-120">In such a case there is no way to determine which exception triggered the JIT-attach.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cfe5-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cfe5-121">Requirements</span></span>  
 <span data-ttu-id="3cfe5-122">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cfe5-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cfe5-123">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3cfe5-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3cfe5-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3cfe5-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3cfe5-125">**Versões do .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cfe5-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cfe5-126">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3cfe5-126">See Also</span></span>  
 [<span data-ttu-id="3cfe5-127">Interface ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="3cfe5-127">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [<span data-ttu-id="3cfe5-128">Interfaces de depuração</span><span class="sxs-lookup"><span data-stu-id="3cfe5-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="3cfe5-129">Depuração</span><span class="sxs-lookup"><span data-stu-id="3cfe5-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)