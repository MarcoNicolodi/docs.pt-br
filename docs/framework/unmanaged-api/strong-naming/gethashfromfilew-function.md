---
title: Função GetHashFromFileW
ms.date: 03/30/2017
api_name:
- GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW function [.NET Framework strong naming]
ms.assetid: 97c2d7a6-5376-45a1-ba65-146a249147cc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 00ee1139b4b8340a73740117b74208a6a1f6b639
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461585"
---
# <a name="gethashfromfilew-function"></a>Função GetHashFromFileW
Gera um hash com base no conteúdo do arquivo especificado por uma cadeia de caracteres Unicode.  
  
 Essa função foi preterida. Use o [Iclrstrongname](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) método em vez disso.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
#### <a name="parameters"></a>Parâmetros  
 `wszFilePath`  
 [in] O nome de Unicode do arquivo para hash.  
  
 `piHashAlg`  
 [out no] O algoritmo para usar ao gerar o hash. Os algoritmos válidos são aquelas definidas por CryptoAPI Win32. Se `piHashAlg` for definido como 0, o algoritmo padrão CALG_SHA-1 é usado.  
  
 `pbHash`  
 [out] Uma matriz de bytes que contém o hash gerado.  
  
 `cchHash`  
 [in] O tamanho máximo do buffer apontado pelo `pbHash`.  
  
 `pchHash`  
 [out] O tamanho, em bytes, de `pbHash`.  
  
## <a name="remarks"></a>Comentários  
 Essa função é o mesmo que [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md), exceto que a especificação de nome de arquivo for Unicode em vez de ANSI.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** StrongName.h  
  
 **Biblioteca:** incluído como um recurso no MSCOREE  
  
 **Versões do .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte também  
 [Método GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)  
 [Método GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)  
 [Interface ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
