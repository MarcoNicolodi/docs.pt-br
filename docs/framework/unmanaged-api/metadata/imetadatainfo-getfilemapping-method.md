---
title: "Método IMetaDataInfo::GetFileMapping"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataInfo.GetFileMapping
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataInfo::GetFileMapping
helpviewer_keywords:
- IMetaDataInfo::GetFileMapping method [.NET Framework metadata]
- GetFileMapping method [.NET Framework metadata]
ms.assetid: 2868dfec-c992-4606-88bb-a8e0b6b18271
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 74f44d366ec4f3848f7c8436e208dcaee3466fe1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatainfogetfilemapping-method"></a><span data-ttu-id="c8217-102">Método IMetaDataInfo::GetFileMapping</span><span class="sxs-lookup"><span data-stu-id="c8217-102">IMetaDataInfo::GetFileMapping Method</span></span>
<span data-ttu-id="c8217-103">Obtém a região de memória do arquivo mapeado e o tipo de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="c8217-103">Gets the memory region of the mapped file, and the type of mapping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8217-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c8217-104">Syntax</span></span>  
  
```  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8217-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="c8217-105">Parameters</span></span>  
 `ppvData`  
 <span data-ttu-id="c8217-106">[out] Um ponteiro para o início do arquivo mapeado.</span><span class="sxs-lookup"><span data-stu-id="c8217-106">[out] A pointer to the start of the mapped file.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="c8217-107">[out] O tamanho da região de dados mapeado.</span><span class="sxs-lookup"><span data-stu-id="c8217-107">[out] The size of the mapped region.</span></span> <span data-ttu-id="c8217-108">Se `pdwMappingType` é `fmFlat`, esse é o tamanho do arquivo.</span><span class="sxs-lookup"><span data-stu-id="c8217-108">If `pdwMappingType` is `fmFlat`, this is the size of the file.</span></span>  
  
 `pdwMappingType`  
 <span data-ttu-id="c8217-109">[out] Um [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) valor que indica o tipo de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="c8217-109">[out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) value that indicates the type of mapping.</span></span> <span data-ttu-id="c8217-110">A implementação atual do common language runtime (CLR) sempre retorna `fmFlat`.</span><span class="sxs-lookup"><span data-stu-id="c8217-110">The current implementation of the common language runtime (CLR) always returns `fmFlat`.</span></span> <span data-ttu-id="c8217-111">Outros valores são reservados para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="c8217-111">Other values are reserved for future use.</span></span> <span data-ttu-id="c8217-112">No entanto, você sempre deve verificar o valor retornado, pois outros valores podem ser habilitados em versões futuras, ou versões de serviço.</span><span class="sxs-lookup"><span data-stu-id="c8217-112">However, you should always verify the returned value, because other values may be enabled in future versions or service releases.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8217-113">Valor de retorno</span><span class="sxs-lookup"><span data-stu-id="c8217-113">Return Value</span></span>  
  
|<span data-ttu-id="c8217-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c8217-114">HRESULT</span></span>|<span data-ttu-id="c8217-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="c8217-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c8217-116">Todas as saídas são preenchidas.</span><span class="sxs-lookup"><span data-stu-id="c8217-116">All outputs are filled.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="c8217-117">NULO foi passado como um valor de argumento.</span><span class="sxs-lookup"><span data-stu-id="c8217-117">NULL was passed as an argument value.</span></span>|  
|`COR_E_NOTSUPPORTED`|<span data-ttu-id="c8217-118">A implementação de CLR não pode fornecer informações sobre a região de memória.</span><span class="sxs-lookup"><span data-stu-id="c8217-118">The CLR implementation cannot provide information about the memory region.</span></span> <span data-ttu-id="c8217-119">Isso pode ocorrer pelos seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="c8217-119">This can happen for the following reasons:</span></span><br /><br /> <span data-ttu-id="c8217-120">-O escopo de metadados foi aberto com o `ofWrite` ou `ofCopyMemory` sinalizador.</span><span class="sxs-lookup"><span data-stu-id="c8217-120">-   The metadata scope was opened with the `ofWrite` or `ofCopyMemory` flag.</span></span><br /><span data-ttu-id="c8217-121">-O escopo de metadados foi aberto sem o `ofReadOnly` sinalizador.</span><span class="sxs-lookup"><span data-stu-id="c8217-121">-   The metadata scope was opened without the `ofReadOnly` flag.</span></span><br /><span data-ttu-id="c8217-122">-A [Imetadatadispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) método foi usado para abrir somente a parte de metadados do arquivo.</span><span class="sxs-lookup"><span data-stu-id="c8217-122">-   The [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method was used to open only the metadata portion of the file.</span></span><br /><span data-ttu-id="c8217-123">-O arquivo não é um arquivo PE (executável portátil).</span><span class="sxs-lookup"><span data-stu-id="c8217-123">-   The file is not a portable executable (PE) file.</span></span> <span data-ttu-id="c8217-124">**Observação:** essas condições dependem da implementação de CLR e é provavelmente serão reduzidas em futuras versões do CLR.</span><span class="sxs-lookup"><span data-stu-id="c8217-124">**Note:**  These conditions depend on the CLR implementation, and are likely to be weakened in future versions of the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8217-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="c8217-125">Remarks</span></span>  
 <span data-ttu-id="c8217-126">A memória que `ppvData` aponta para é válido somente quando o escopo de metadados subjacente é aberto.</span><span class="sxs-lookup"><span data-stu-id="c8217-126">The memory that `ppvData` points to is valid only as long as the underlying metadata scope is open.</span></span>  
  
 <span data-ttu-id="c8217-127">Para que esse método funcione, quando você mapeia os metadados de um arquivo em disco na memória chamando o [Imetadatadispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) método, você deve especificar o `ofReadOnly` sinalizador e você não deve especificar o `ofWrite` ou `ofCopyMemory` sinalizador.</span><span class="sxs-lookup"><span data-stu-id="c8217-127">In order for this method to work, when you map the metadata of an on-disk file into memory by calling the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, you must specify the `ofReadOnly` flag and you must not specify the `ofWrite` or `ofCopyMemory` flag.</span></span>  
  
 <span data-ttu-id="c8217-128">A escolha do tipo de mapeamento de arquivo para cada escopo é específica para uma determinada implementação do CLR.</span><span class="sxs-lookup"><span data-stu-id="c8217-128">The choice of file mapping type for each scope is specific to a given implementation of the CLR.</span></span> <span data-ttu-id="c8217-129">Ele não pode ser definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="c8217-129">It cannot be set by the user.</span></span> <span data-ttu-id="c8217-130">A implementação atual do CLR sempre retorna `fmFlat` em `pdwMappingType`, mas isso pode mudar em futuras versões do CLR ou em futuras versões do serviço de uma determinada versão.</span><span class="sxs-lookup"><span data-stu-id="c8217-130">The current implementation of the CLR always returns `fmFlat` in `pdwMappingType`, but this can change in future versions of the CLR or in future service releases of a given version.</span></span> <span data-ttu-id="c8217-131">Você sempre deve verificar o valor retornado `pdwMappingType`porque diferentes tipos terá diferentes layouts e deslocamentos.</span><span class="sxs-lookup"><span data-stu-id="c8217-131">You should always check the returned value in `pdwMappingType`, because different types will have different layouts and offsets.</span></span>  
  
 <span data-ttu-id="c8217-132">Não há suporte para passar NULL para qualquer um dos três parâmetros.</span><span class="sxs-lookup"><span data-stu-id="c8217-132">Passing NULL for any of the three parameters is not supported.</span></span> <span data-ttu-id="c8217-133">O método retorna `E_INVALIDARG`, e nenhuma das saídas são preenchidas.</span><span class="sxs-lookup"><span data-stu-id="c8217-133">The method returns `E_INVALIDARG`, and none of the outputs are filled.</span></span> <span data-ttu-id="c8217-134">Ignorar o tipo de mapeamento ou o tamanho da região pode resultar no encerramento anormal do programa.</span><span class="sxs-lookup"><span data-stu-id="c8217-134">Ignoring the mapping type or the size of the region can result in abnormal program termination.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8217-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c8217-135">Requirements</span></span>  
 <span data-ttu-id="c8217-136">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8217-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8217-137">**Cabeçalho:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c8217-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c8217-138">**Biblioteca:** usado como um recurso no MSCOREE</span><span class="sxs-lookup"><span data-stu-id="c8217-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c8217-139">**Versões do .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8217-139">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8217-140">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c8217-140">See Also</span></span>  
 [<span data-ttu-id="c8217-141">Interface IMetaDataInfo</span><span class="sxs-lookup"><span data-stu-id="c8217-141">IMetaDataInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)  
 [<span data-ttu-id="c8217-142">Enumeração CorFileMapping</span><span class="sxs-lookup"><span data-stu-id="c8217-142">CorFileMapping Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)