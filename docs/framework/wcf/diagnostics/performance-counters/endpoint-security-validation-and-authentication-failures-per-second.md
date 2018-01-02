---
title: "Ponto de extremidade: falhas de autenticação e validação de segurança por segundo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89a70b90-d7e4-4b03-9b84-4dc88ce3d605
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: c6b50aa00fe59d0ad23d5ca0b77c7b89f97a0d1e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="endpoint-security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="f249e-102">Ponto de extremidade: falhas de autenticação e validação de segurança por segundo</span><span class="sxs-lookup"><span data-stu-id="f249e-102">Endpoint: Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="f249e-103">Nome do contador: validação de segurança e autenticação de falhas por segundo</span><span class="sxs-lookup"><span data-stu-id="f249e-103">Counter name: Security Validation and Authentication Failures Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="f249e-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="f249e-104">Description</span></span>  
 <span data-ttu-id="f249e-105">Esse contador é incrementado sempre que uma mensagem foi rejeitada devido a um problema de segurança não coberto pelo contador "Chamadas de segurança não autorizado".</span><span class="sxs-lookup"><span data-stu-id="f249e-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="f249e-106">Esses problemas incluem:</span><span class="sxs-lookup"><span data-stu-id="f249e-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="f249e-107">Não é possível ler o token de cliente da mensagem.</span><span class="sxs-lookup"><span data-stu-id="f249e-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="f249e-108">Token de cliente falha na autenticação (por exemplo, senha incorreta).</span><span class="sxs-lookup"><span data-stu-id="f249e-108">Client token has failed authentication (for example, bad password).</span></span>  
  
-   <span data-ttu-id="f249e-109">Falha na verificação de assinatura (por exemplo, a mensagem foi violada).</span><span class="sxs-lookup"><span data-stu-id="f249e-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="f249e-110">A mensagem é uma duplicata da anterior, o que pode ocorrer durante um ataque de repetição.</span><span class="sxs-lookup"><span data-stu-id="f249e-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="f249e-111">Ocorreu uma falha de descriptografia.</span><span class="sxs-lookup"><span data-stu-id="f249e-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="f249e-112">Alguns necessários faltam elementos (por exemplo, timestamp ausente ou bloquear os dados criptografados) da mensagem.</span><span class="sxs-lookup"><span data-stu-id="f249e-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="f249e-113">Ocorreram erros durante o handshake TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="f249e-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="f249e-114">Esse contador é do tipo de contador de desempenho [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cujo valor é calculado usando a fórmula a seguir:</span><span class="sxs-lookup"><span data-stu-id="f249e-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula:</span></span>  
  
 <span data-ttu-id="f249e-115">(N1-N0)/((D1-D0)/F)</span><span class="sxs-lookup"><span data-stu-id="f249e-115">(N1-N0)/((D1-D0)/F)</span></span>