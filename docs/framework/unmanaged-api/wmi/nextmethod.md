---
title: "Função NextMethod (referência de API não gerenciada)"
description: "A função NextMethod recupera o próximo método em uma enumeração."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: NextMethod
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: NextMethod
helpviewer_keywords: NextMethod function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d9b14424bb914be3ba127670e1b6490f79854d6e
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2017
---
# <a name="nextmethod-function"></a><span data-ttu-id="1f53c-103">Função NextMethod</span><span class="sxs-lookup"><span data-stu-id="1f53c-103">NextMethod function</span></span>
<span data-ttu-id="1f53c-104">Recupera o próximo método em uma enumeração que começa com uma chamada para [BeginMethodEnumeration](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="1f53c-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="1f53c-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1f53c-105">Syntax</span></span>  
  
```  
HRESULT NextMethod (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature   
); 
```  

## <a name="parameters"></a><span data-ttu-id="1f53c-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="1f53c-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="1f53c-107">[in] Esse parâmetro é usado.</span><span class="sxs-lookup"><span data-stu-id="1f53c-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="1f53c-108">[in] Um ponteiro para um [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instância.</span><span class="sxs-lookup"><span data-stu-id="1f53c-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="1f53c-109">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="1f53c-109">[in] Reserved.</span></span> <span data-ttu-id="1f53c-110">Esse parâmetro deve ser 0.</span><span class="sxs-lookup"><span data-stu-id="1f53c-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="1f53c-111">[out] Um ponteiro que aponta para `null` antes da chamada.</span><span class="sxs-lookup"><span data-stu-id="1f53c-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="1f53c-112">Quando a função retornar, o endereço de um novo `BSTR` que contém o nome do método.</span><span class="sxs-lookup"><span data-stu-id="1f53c-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span> 

`ppSignatureIn`  
<span data-ttu-id="1f53c-113">[out] Um ponteiro que recebe um ponteiro para um [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) que contém o `in` parâmetros do método.</span><span class="sxs-lookup"><span data-stu-id="1f53c-113">[out] A pointer that receives a pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) that contains the `in` parameters for the method.</span></span> 

`ppSignatureOut`  
<span data-ttu-id="1f53c-114">[out] Um ponteiro que recebe um ponteiro para um [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) que contém o `out` parâmetros do método.</span><span class="sxs-lookup"><span data-stu-id="1f53c-114">[out] A pointer that receives a pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) that contains the `out` parameters for the method.</span></span> 

## <a name="return-value"></a><span data-ttu-id="1f53c-115">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="1f53c-115">Return value</span></span>

<span data-ttu-id="1f53c-116">Os seguintes valores retornados por essa função são definidos no *WbemCli.h* arquivo de cabeçalho, ou você pode defini-los como constantes em seu código:</span><span class="sxs-lookup"><span data-stu-id="1f53c-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1f53c-117">Constante</span><span class="sxs-lookup"><span data-stu-id="1f53c-117">Constant</span></span>  |<span data-ttu-id="1f53c-118">Valor</span><span class="sxs-lookup"><span data-stu-id="1f53c-118">Value</span></span>  |<span data-ttu-id="1f53c-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="1f53c-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="1f53c-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="1f53c-120">0x8004101d</span></span> | <span data-ttu-id="1f53c-121">Não houve nenhuma chamada para o [ `BeginEnumeration` ](beginenumeration.md) função.</span><span class="sxs-lookup"><span data-stu-id="1f53c-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="1f53c-122">0</span><span class="sxs-lookup"><span data-stu-id="1f53c-122">0</span></span> | <span data-ttu-id="1f53c-123">A chamada de função foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="1f53c-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="1f53c-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="1f53c-124">0x40005</span></span> | <span data-ttu-id="1f53c-125">Não há nenhuma propriedade mais na enumeração.</span><span class="sxs-lookup"><span data-stu-id="1f53c-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="1f53c-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="1f53c-126">Remarks</span></span>

<span data-ttu-id="1f53c-127">Essa função encapsula uma chamada para o [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="1f53c-127">This function wraps a call to the [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="1f53c-128">O chamador começa a sequência de enumeração chamando o [BeginMethodEnumeration](beginmethodenumeration.md) de função e, em seguida, chama a função [NextMethod] até que a função retornará `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="1f53c-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="1f53c-129">Opcionalmente, o chamador conclui a sequência chamando [EndMethodEnumeration](endmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="1f53c-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="1f53c-130">O chamador pode encerrar a enumeração antecipada chamando [EndMethodEnumeration](endmethodenumeration.md) a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="1f53c-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="1f53c-131">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1f53c-131">Example</span></span>

<span data-ttu-id="1f53c-132">Para obter um exemplo de C++, consulte o [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="1f53c-132">For a C++ example, see the [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="1f53c-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f53c-133">Requirements</span></span>  
 <span data-ttu-id="1f53c-134">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f53c-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f53c-135">**Cabeçalho:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1f53c-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1f53c-136">**Versões do .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1f53c-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f53c-137">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1f53c-137">See also</span></span>  
[<span data-ttu-id="1f53c-138">WMI e contadores de desempenho (referência de API não gerenciada)</span><span class="sxs-lookup"><span data-stu-id="1f53c-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)