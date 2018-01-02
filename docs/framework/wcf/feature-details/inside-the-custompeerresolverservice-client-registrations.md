---
title: 'Sobre o CustomPeerResolverService: Registro de clientes'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40236953-a916-4236-84a6-928859e1331a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7daa3c08bb15b13543a4f972d7e4c5e4929e16e8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="inside-the-custompeerresolverservice-client-registrations"></a><span data-ttu-id="754e5-102">Sobre o CustomPeerResolverService: Registro de clientes</span><span class="sxs-lookup"><span data-stu-id="754e5-102">Inside the CustomPeerResolverService: Client Registrations</span></span>
<span data-ttu-id="754e5-103">Cada nó na malha publica suas informações de ponto de extremidade para o serviço de resolução por meio de `Register` função.</span><span class="sxs-lookup"><span data-stu-id="754e5-103">Each node in the mesh publishes its endpoint information to the resolver service through the `Register` function.</span></span> <span data-ttu-id="754e5-104">O serviço resolvedor armazena essas informações como um registro.</span><span class="sxs-lookup"><span data-stu-id="754e5-104">The resolver service stores this information as a registration record.</span></span> <span data-ttu-id="754e5-105">Este registro contém um identificador exclusivo (RegistrationID) e informações de ponto de extremidade (PeerNodeAddress) para o nó.</span><span class="sxs-lookup"><span data-stu-id="754e5-105">This record contains a unique identifier (RegistrationID) and endpoint information (PeerNodeAddress) for the node.</span></span>  
  
## <a name="stale-records-and-expiration-time"></a><span data-ttu-id="754e5-106">Registros obsoletos e a hora de expiração</span><span class="sxs-lookup"><span data-stu-id="754e5-106">Stale Records and Expiration Time</span></span>  
 <span data-ttu-id="754e5-107">Idealmente, quando um nó sai da malha, ele chamará o `Unregister` função, o que faz com que o serviço de resolução remover a entrada de registro.</span><span class="sxs-lookup"><span data-stu-id="754e5-107">Ideally, when a node leaves the mesh, it will call the `Unregister` function, which causes the resolver service to remove the registration entry.</span></span> <span data-ttu-id="754e5-108">Às vezes, nós desligado ou se tornar inacessíveis antes de chamar `Unregister`, deixando atrás de um registro obsoletos.</span><span class="sxs-lookup"><span data-stu-id="754e5-108">Sometimes, nodes shut down or become inaccessible before calling `Unregister`, leaving behind a stale registration record.</span></span>  
  
 <span data-ttu-id="754e5-109">Registros obsoletos no serviço resolvedor podem causar falhas de conexão.</span><span class="sxs-lookup"><span data-stu-id="754e5-109">Stale records in your resolver service can cause failed connections.</span></span> <span data-ttu-id="754e5-110">Se um nó tentando se conectar a uma malha recebe informações de conexão obsoleto do serviço resolvedor, pode levar mais tempo para unir com êxito a malha.</span><span class="sxs-lookup"><span data-stu-id="754e5-110">If a node trying to connect to a mesh receives stale connection information from the resolver service, it can take longer to successfully join the mesh.</span></span> <span data-ttu-id="754e5-111">Registros obsoletos também ocupam memória.</span><span class="sxs-lookup"><span data-stu-id="754e5-111">Stale records also take up memory.</span></span> <span data-ttu-id="754e5-112">Sem um eficiente limpar o processo, o cache usado para armazenar os registros pode eventualmente estouro e o serviço de resolução de falhas.</span><span class="sxs-lookup"><span data-stu-id="754e5-112">Without an efficient clean up process, the cache used to store registrations could eventually overflow and crash the resolver service.</span></span>  
  
 <span data-ttu-id="754e5-113">O <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService> marca cada registro com um tempo de expiração (DateTime) e armazena essas informações como parte do registro.</span><span class="sxs-lookup"><span data-stu-id="754e5-113">The <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService> marks each record with an expiration time (DateTime), and stores that information as part of the record.</span></span> <span data-ttu-id="754e5-114">O serviço usa a hora de expiração para identificar registros obsoletos.</span><span class="sxs-lookup"><span data-stu-id="754e5-114">The service uses the expiration time to identify stale records.</span></span> <span data-ttu-id="754e5-115">Implementações personalizadas devem fazer algo semelhante.</span><span class="sxs-lookup"><span data-stu-id="754e5-115">Custom implementations should do something similar.</span></span>  
  
## <a name="refreshinterval-and-cleanupinterval"></a><span data-ttu-id="754e5-116">Intervalo de atualização e para CleanupInterval</span><span class="sxs-lookup"><span data-stu-id="754e5-116">RefreshInterval and CleanupInterval</span></span>  
 <span data-ttu-id="754e5-117">O `RefreshInterval` propriedade o <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService> define por quanto tempo os registros estarão válidos na tabela de pesquisa de registro do serviço.</span><span class="sxs-lookup"><span data-stu-id="754e5-117">The `RefreshInterval` property of the <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService> defines how long registration records remain valid in the service's registration lookup table.</span></span> <span data-ttu-id="754e5-118">Quando a quantidade de tempo fornecido para essa propriedade tiver passado para um determinado registro, que o registro se torna obsoleto e está marcado para exclusão.</span><span class="sxs-lookup"><span data-stu-id="754e5-118">When the amount of time supplied to this property has passed for a given record, that record becomes stale and is marked for deletion.</span></span>  
  
 <span data-ttu-id="754e5-119">O `CleanupInterval` propriedade o <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService> informa quantas vezes o serviço para pesquisar e excluir registros obsoletos.</span><span class="sxs-lookup"><span data-stu-id="754e5-119">The `CleanupInterval` property of the <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService> tells the service how often to search for and delete stale registration records.</span></span> <span data-ttu-id="754e5-120">O `CleanupInterval` deve ser definido como um tempo maior que ou igual ao `RefreshInterval` definido no serviço.</span><span class="sxs-lookup"><span data-stu-id="754e5-120">The `CleanupInterval` should be set to a time greater than or equal to the `RefreshInterval` set on the service.</span></span>  
  
 <span data-ttu-id="754e5-121">Para implementar seu próprio serviço de resolução, você precisa escrever uma função de manutenção para remover registros obsoletos.</span><span class="sxs-lookup"><span data-stu-id="754e5-121">To implement your own resolver service, you need to write a maintenance function to remove stale registration records.</span></span> <span data-ttu-id="754e5-122">Há várias maneiras de fazer isso:</span><span class="sxs-lookup"><span data-stu-id="754e5-122">There are several ways to do this:</span></span>  
  
-   <span data-ttu-id="754e5-123">**Manutenção periódica**: definir um timer para off periodicamente e percorrer o repositório de dados para excluir registros antigos.</span><span class="sxs-lookup"><span data-stu-id="754e5-123">**Periodic maintenance**: Set a timer to go off periodically, and go through your data store to delete old records.</span></span> <span data-ttu-id="754e5-124">O <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService> usa essa abordagem.</span><span class="sxs-lookup"><span data-stu-id="754e5-124">The <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService> uses this approach.</span></span>  
  
-   <span data-ttu-id="754e5-125">**Exclusão passivo**: em vez de pesquisar ativamente registros obsoletos em intervalos regulares, você pode identificar e excluir registros obsoletos quando seu serviço já está executando outra função.</span><span class="sxs-lookup"><span data-stu-id="754e5-125">**Passive deletion**: Instead of actively searching for stale records at regular intervals, you can identify and delete stale records when your service is already performing another function.</span></span> <span data-ttu-id="754e5-126">Isso pode potencialmente lenta tempo de resposta para solicitações de clientes resolvedor, mas elimina a necessidade de um temporizador e pode ser mais eficiente se alguns nós são esperado para sair sem chamar `Unregister`.</span><span class="sxs-lookup"><span data-stu-id="754e5-126">This may potentially slow down response time to requests from the resolver clients, but it eliminates the need for a timer, and may be more efficient if few nodes are expected to leave without calling `Unregister`.</span></span>  
  
## <a name="registrationlifetime-and-refresh"></a><span data-ttu-id="754e5-127">RegistrationLifetime e atualização</span><span class="sxs-lookup"><span data-stu-id="754e5-127">RegistrationLifetime and Refresh</span></span>  
 <span data-ttu-id="754e5-128">Quando um nó se registra com um serviço de resolução, ele recebe um <xref:System.ServiceModel.PeerResolvers.RegisterResponseInfo> objeto do serviço.</span><span class="sxs-lookup"><span data-stu-id="754e5-128">When a node registers with a resolver service, it receives a <xref:System.ServiceModel.PeerResolvers.RegisterResponseInfo> object from the service.</span></span> <span data-ttu-id="754e5-129">Esse objeto tem um `RegistrationLifetime` propriedade que indica para o nó de quanto tempo ele tem antes do registro expira e é removido, o serviço de resolução.</span><span class="sxs-lookup"><span data-stu-id="754e5-129">This object has a `RegistrationLifetime` property which indicates to the node how much time it has before the registration expires and is removed by the resolver service.</span></span> <span data-ttu-id="754e5-130">Se, por exemplo, o `RegistrationLifetime` é 2 minutos, o nó precisa chamar `Refresh` em menos de 2 minutos para garantir o registro permanecerá atualizado e não será excluído.</span><span class="sxs-lookup"><span data-stu-id="754e5-130">If, for example, the `RegistrationLifetime` is 2 minutes, the node needs to call `Refresh` in under 2 minutes to ensure the record stays fresh and is not deleted.</span></span> <span data-ttu-id="754e5-131">Quando o serviço resolvedor recebe um `Refresh` solicitação, ele procura o registro e redefine a hora de expiração.</span><span class="sxs-lookup"><span data-stu-id="754e5-131">When the resolver service receives a `Refresh` request, it looks up the record and resets the expiration time.</span></span> <span data-ttu-id="754e5-132">Atualize o retorna um <xref:System.ServiceModel.PeerResolvers.RefreshResponseInfo> do objeto com um `RegistrationLifetime` propriedade.</span><span class="sxs-lookup"><span data-stu-id="754e5-132">Refresh returns a <xref:System.ServiceModel.PeerResolvers.RefreshResponseInfo> object with a `RegistrationLifetime` property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="754e5-133">Consulte também</span><span class="sxs-lookup"><span data-stu-id="754e5-133">See Also</span></span>  
 [<span data-ttu-id="754e5-134">Resolvedor Peer</span><span class="sxs-lookup"><span data-stu-id="754e5-134">Peer Resolvers</span></span>](../../../../docs/framework/wcf/feature-details/peer-resolvers.md)