---
title: Microsoft.Transactions.TransactionBridge.PreparedMessageRetry
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2194292d-bf5f-4aef-9336-cd3c4795cb71
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2ccfbb975ab274dd0a8f558db44e7d24178ed36a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="microsofttransactionstransactionbridgepreparedmessageretry"></a><span data-ttu-id="3c310-102">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span><span class="sxs-lookup"><span data-stu-id="3c310-102">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span></span>
<span data-ttu-id="3c310-103">Uma tentativa de mensagem preparada foi enviada a um coordenador que não responde.</span><span class="sxs-lookup"><span data-stu-id="3c310-103">A prepared message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3c310-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="3c310-104">Description</span></span>  
 <span data-ttu-id="3c310-105">Rastreado se o Gerenciador de transações local necessário reenviar uma mensagem preparada para coordenador superior porque não recebeu uma resposta em uma determinada quantidade de tempo /</span><span class="sxs-lookup"><span data-stu-id="3c310-105">Traced if the local Transaction Manager needed to resend a Prepared message to a superior coordinator because it did not receive a response in a given amount of time/</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="3c310-106">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="3c310-106">Troubleshooting</span></span>  
 <span data-ttu-id="3c310-107">Investigue os possível problemas na rede ou produto que evitar que sejam entregues em tempo de resposta.</span><span class="sxs-lookup"><span data-stu-id="3c310-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="3c310-108">Se muitas dessas mensagens são vistas, ele pode indicar problemas de infraestrutura ou tempos de resposta anormalmente longo.</span><span class="sxs-lookup"><span data-stu-id="3c310-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="3c310-109">Os dois problemas reduzirá drasticamente a taxa de transferência de transações no sistema.</span><span class="sxs-lookup"><span data-stu-id="3c310-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c310-110">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3c310-110">See Also</span></span>  
 [<span data-ttu-id="3c310-111">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="3c310-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="3c310-112">Usando o rastreamento para solucionar problemas de seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="3c310-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 <span data-ttu-id="3c310-113">[Administration and Diagnostics](../../../../../docs/framework/wcf/diagnostics/index.md) (Administração e diagnósticos)</span><span class="sxs-lookup"><span data-stu-id="3c310-113">[Administration and Diagnostics](../../../../../docs/framework/wcf/diagnostics/index.md)</span></span>