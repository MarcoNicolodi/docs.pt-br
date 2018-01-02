---
title: Tratamento de erro e ponte
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ae87d1a-b615-4014-a494-a53f63ff0137
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cc809b75a965107594f7b2aa8a78d412bf284d8e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="bridging-and-error-handling"></a><span data-ttu-id="5156b-102">Tratamento de erro e ponte</span><span class="sxs-lookup"><span data-stu-id="5156b-102">Bridging and Error Handling</span></span>
<span data-ttu-id="5156b-103">Este exemplo demonstra como o [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] o serviço de roteamento é usado para a ponte de comunicação entre um cliente e um serviço que usam ligações diferentes.</span><span class="sxs-lookup"><span data-stu-id="5156b-103">This sample demonstrates how the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] routing service is used for bridging communication between a client and a service that use different bindings.</span></span> <span data-ttu-id="5156b-104">Este exemplo também mostra como usar um serviço de backup para cenários de failover.</span><span class="sxs-lookup"><span data-stu-id="5156b-104">This sample also shows how to use a back-up service for failover scenarios.</span></span> <span data-ttu-id="5156b-105">O serviço de roteamento é um [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] componente que torna mais fácil incluir um roteador baseado em conteúdo em seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5156b-105">The routing service is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="5156b-106">Este exemplo se adapta o padrão [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Calculadora de exemplo para se comunicar usando o serviço de roteamento.</span><span class="sxs-lookup"><span data-stu-id="5156b-106">This sample adapts the standard [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Calculator Sample to communicate using the routing service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5156b-107">Os exemplos podem mais ser instalados no seu computador.</span><span class="sxs-lookup"><span data-stu-id="5156b-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="5156b-108">Verifique o seguinte diretório (padrão) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="5156b-108">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5156b-109">Se este diretório não existir, vá para [Windows Communication Foundation (WCF) e exemplos do Windows Workflow Foundation (WF) para o .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para baixar todos os [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemplos.</span><span class="sxs-lookup"><span data-stu-id="5156b-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5156b-110">Este exemplo está localizado no seguinte diretório.</span><span class="sxs-lookup"><span data-stu-id="5156b-110">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\ErrorHandlingAndBridging`  
  
## <a name="sample-details"></a><span data-ttu-id="5156b-111">Detalhes de exemplo</span><span class="sxs-lookup"><span data-stu-id="5156b-111">Sample Details</span></span>  
 <span data-ttu-id="5156b-112">Neste exemplo, o cliente de cálculo é configurado para enviar mensagens a um ponto de extremidade exposto pelo roteador.</span><span class="sxs-lookup"><span data-stu-id="5156b-112">In this sample, the Calculator client is configured to send messages to an endpoint exposed by the router.</span></span> <span data-ttu-id="5156b-113">O serviço de roteamento está configurado para aceitar todas as mensagens enviadas a ele e encaminhá-los para um ponto de extremidade que corresponde ao serviço de cálculo.</span><span class="sxs-lookup"><span data-stu-id="5156b-113">The routing service is configured to accept all messages sent to it and to forward them to an endpoint that corresponds to the Calculator service.</span></span> <span data-ttu-id="5156b-114">Os pontos a seguir descrevem a configuração do serviço Calculadora primário, o serviço de cálculo de backup e o cliente de cálculo e como ocorre a comunicação entre o cliente e o serviço usando o serviço de roteamento:</span><span class="sxs-lookup"><span data-stu-id="5156b-114">The following points describe the configuration of the primary Calculator service, the back-up Calculator service, and the Calculator client and how the communication between the client and the service happens using the routing service:</span></span>  
  
-   <span data-ttu-id="5156b-115">O cliente de cálculo é configurado para usar BasicHttpBinding enquanto o serviço de cálculo é configurado para usar NetTcpBinding.</span><span class="sxs-lookup"><span data-stu-id="5156b-115">The Calculator client is configured to use BasicHttpBinding while the Calculator service is configured to use NetTcpBinding.</span></span> <span data-ttu-id="5156b-116">O serviço de roteamento converte automaticamente as mensagens conforme necessário antes de enviá-los para o serviço de cálculo e também converte as respostas para que o cliente de cálculo pode acessá-los.</span><span class="sxs-lookup"><span data-stu-id="5156b-116">The routing service automatically converts the messages as necessary before sending them to the Calculator service and it also converts the responses so that the Calculator client can access them.</span></span>  
  
-   <span data-ttu-id="5156b-117">O serviço de roteamento conhece os dois serviços de cálculo: o serviço de calculadora primário e o serviço de cálculo do backup.</span><span class="sxs-lookup"><span data-stu-id="5156b-117">The routing service knows about two Calculator services: the primary Calculator service and the back-up Calculator service.</span></span> <span data-ttu-id="5156b-118">O serviço de roteamento primeiro tenta se comunicar com o ponto de extremidade de serviço principal Calculadora.</span><span class="sxs-lookup"><span data-stu-id="5156b-118">The routing service first attempts to communicate with the primary Calculator service endpoint.</span></span> <span data-ttu-id="5156b-119">Se essa tentativa falhar porque o ponto de extremidade está inativo, o serviço de roteamento, em seguida, tenta se comunicar com o ponto de extremidade do serviço de cálculo do backup.</span><span class="sxs-lookup"><span data-stu-id="5156b-119">If this attempt fails due to the endpoint being down, the routing service then tries to communicate with the back-up Calculator service endpoint.</span></span>  
  
 <span data-ttu-id="5156b-120">Portanto, as mensagens enviadas do cliente são recebidas pelo roteador e são redirecionadas para o serviço de cálculo real.</span><span class="sxs-lookup"><span data-stu-id="5156b-120">Thus messages sent from the client are received by the router and are rerouted to the actual Calculator service.</span></span> <span data-ttu-id="5156b-121">Se o ponto de extremidade de serviço de Calculadora estiver inativo, o serviço de roteamento encaminha a mensagem para o ponto de extremidade do serviço de cálculo do backup.</span><span class="sxs-lookup"><span data-stu-id="5156b-121">If the Calculator service endpoint is down, the routing service routes the message to the back-up Calculator service endpoint.</span></span> <span data-ttu-id="5156b-122">Mensagens do serviço de cálculo do backup são enviadas para o roteador do serviço, que por sua vez passa de volta para o cliente de cálculo.</span><span class="sxs-lookup"><span data-stu-id="5156b-122">Messages from the back-up Calculator service are sent back to the service router, which in turn passes them back to the Calculator client.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5156b-123">Uma lista de backup pode ter mais de um ponto de extremidade definido.</span><span class="sxs-lookup"><span data-stu-id="5156b-123">A back-up list can have more than one endpoint defined.</span></span> <span data-ttu-id="5156b-124">Nesse caso se o ponto de extremidade de serviço de backup estiver inativo, o serviço de roteamento tenta se conectar ao próximo ponto de extremidade de backup na lista até que ocorra uma conexão bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="5156b-124">In this case if the back-up service endpoint is down, the routing service attempts to connect to the next back-up endpoint in the list until a successful connection occurs.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="5156b-125">Para usar este exemplo</span><span class="sxs-lookup"><span data-stu-id="5156b-125">To use this sample</span></span>  
  
1.  <span data-ttu-id="5156b-126">Usando [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra RouterBridgingAndErrorHandling.sln.</span><span class="sxs-lookup"><span data-stu-id="5156b-126">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open RouterBridgingAndErrorHandling.sln.</span></span>  
  
2.  <span data-ttu-id="5156b-127">Pressione F5 ou CTRL + SHIFT + B no Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5156b-127">Press F5 or CTRL+SHIFT+B in Visual Studio</span></span>  
  
    1.  <span data-ttu-id="5156b-128">Se você quiser iniciar os projetos necessários quando você pressionar F5, clique duas vezes a solução, selecione **propriedades**e no **projeto de inicialização** nó **aspropriedadescomuns**, selecione **vários projetos de inicialização**e defina todos os projetos para **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="5156b-128">If you would like to auto-launch the necessary projects when you press F5, right-click the solution, select **Properties**, and in the **Startup Project** node under **Common Properties**, select **Multiple Startup Projects**, and set all projects to **Start**.</span></span>  
  
    2.  <span data-ttu-id="5156b-129">Se você compilar o projeto com CTRL + SHIFT + B, inicie os seguintes aplicativos:</span><span class="sxs-lookup"><span data-stu-id="5156b-129">If you build the project with CTRL+SHIFT+B, start the following applications:</span></span>  
  
        1.  <span data-ttu-id="5156b-130">Cliente de cálculo (. / CalculatorClient/bin/client.exe)</span><span class="sxs-lookup"><span data-stu-id="5156b-130">Calculator client (./CalculatorClient/bin/client.exe)</span></span>  
  
        2.  <span data-ttu-id="5156b-131">Serviço de cálculo (. / CalculatorService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="5156b-131">Calculator service (./CalculatorService/bin/service.exe)</span></span>  
  
        3.  <span data-ttu-id="5156b-132">O serviço de roteamento (. / RoutingService/bin/RoutingService.exe)</span><span class="sxs-lookup"><span data-stu-id="5156b-132">Routing Service (./RoutingService/bin/RoutingService.exe)</span></span>  
  
3.  <span data-ttu-id="5156b-133">No cliente de cálculo, pressione ENTER para iniciar o cliente.</span><span class="sxs-lookup"><span data-stu-id="5156b-133">In the Calculator Client, press ENTER to start the client.</span></span>  
  
     <span data-ttu-id="5156b-134">Você verá a seguinte saída:</span><span class="sxs-lookup"><span data-stu-id="5156b-134">You should see the following output:</span></span>  
  
    ```Output  
    Add(100,15.99) = 115.99  
    Subtract(145,76.54) = 68.46  
    Multiply(9,81.25) = 731.25  
    Divide(22,7) = 3.14285714285714  
    ```  
  
## <a name="configurable-via-code-or-appconfig"></a><span data-ttu-id="5156b-135">Configuráveis por meio de código ou App. config</span><span class="sxs-lookup"><span data-stu-id="5156b-135">Configurable Via Code or App.config</span></span>  
 <span data-ttu-id="5156b-136">O vem de exemplo configurado para usar um arquivo App. config para definir o comportamento do roteador.</span><span class="sxs-lookup"><span data-stu-id="5156b-136">The sample ships configured to use an App.config file to define the router’s behavior.</span></span> <span data-ttu-id="5156b-137">Você também pode alterar o nome do arquivo App. config para algo diferente para que ele não é reconhecido e remova a chamada de método para `ConfigureRouterViaCode()`.</span><span class="sxs-lookup"><span data-stu-id="5156b-137">You can also change the name of the App.config file to something else so that it is not recognized and uncomment the method call to `ConfigureRouterViaCode()`.</span></span> <span data-ttu-id="5156b-138">Um método resulta no mesmo comportamento do roteador.</span><span class="sxs-lookup"><span data-stu-id="5156b-138">Either method results in the same behavior from the router.</span></span>  
  
### <a name="scenario"></a><span data-ttu-id="5156b-139">Cenário</span><span class="sxs-lookup"><span data-stu-id="5156b-139">Scenario</span></span>  
 <span data-ttu-id="5156b-140">Este exemplo demonstra o roteador de serviço, agindo como um manipulador de protocolo de ponte e o erro.</span><span class="sxs-lookup"><span data-stu-id="5156b-140">This sample demonstrates the service router acting as a protocol bridge and error handler.</span></span> <span data-ttu-id="5156b-141">Nesse cenário, nenhum roteamento baseado em conteúdo ocorre; o serviço de roteamento atua como um nó de proxy transparente configurado para passar mensagens diretamente para um conjunto predefinido de pontos de extremidade de destino.</span><span class="sxs-lookup"><span data-stu-id="5156b-141">In this scenario, no content-based routing occurs; the routing service acts as a transparent proxy node configured to pass messages directly to a preconfigured set of destination endpoints.</span></span> <span data-ttu-id="5156b-142">O serviço de roteamento também executa as etapas adicionais de forma transparente a manipulação de erros que ocorrem quando ele tenta enviar para os pontos de extremidade que ele está configurado para se comunicar com.</span><span class="sxs-lookup"><span data-stu-id="5156b-142">The routing service also performs the additional steps of transparently handling errors that occur when it tries to send to the endpoints that it is configured to communicate with.</span></span> <span data-ttu-id="5156b-143">Agindo como uma ponte de protocolo, o serviço de roteamento permite que o usuário defina um protocolo para comunicação externa e outro para comunicação interna.</span><span class="sxs-lookup"><span data-stu-id="5156b-143">By acting as a protocol bridge, the routing service enables the user to define one protocol for external communication and another for internal communication.</span></span>  
  
### <a name="real-world-scenario"></a><span data-ttu-id="5156b-144">Cenário do mundo real</span><span class="sxs-lookup"><span data-stu-id="5156b-144">Real World Scenario</span></span>  
 <span data-ttu-id="5156b-145">A Contoso deseja fornecer um ponto de extremidade de serviço interoperável com o mundo, ao otimizar o desempenho internamente.</span><span class="sxs-lookup"><span data-stu-id="5156b-145">Contoso wants to provide an interoperable service endpoint to the world, while optimizing performance internally.</span></span> <span data-ttu-id="5156b-146">Assim, ele expõe seus serviços para o mundo por meio de um ponto de extremidade usando o BasicHttpBinding internamente usando o serviço de roteamento para acabar com essa conexão ao ponto de extremidade usando NetTcpBinding, que usam seus serviços.</span><span class="sxs-lookup"><span data-stu-id="5156b-146">Thus it exposes its services to the world through an endpoint using the BasicHttpBinding, while internally using the routing service to bridge that connection to the endpoint using NetTcpBinding, which its services use.</span></span> <span data-ttu-id="5156b-147">Além disso, a Contoso deseja sua oferta de serviço para ser tolerante a falhas de interrupções temporárias em qualquer uma das sua produção serviços e virtualiza, portanto, vários pontos de extremidade por trás do serviço de roteador usando o de recursos automaticamente o failover para o tratamento de erros extremidade de backup quando necessário.</span><span class="sxs-lookup"><span data-stu-id="5156b-147">Furthermore, Contoso wants its service offering to be tolerant of temporary outages in any one of their production services and thus virtualizes multiple endpoints behind the router service using the ’s error handling capabilities to automatically failover to back-up endpoints when necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5156b-148">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5156b-148">See Also</span></span>  
 [<span data-ttu-id="5156b-149">Exemplos de persistência e hospedagem de AppFabric</span><span class="sxs-lookup"><span data-stu-id="5156b-149">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)