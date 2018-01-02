---
title: "Como habilitar transmissão"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 6ca2cf4b-c7a1-49d8-a79b-843a90556ba4
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ea506499cf6678beb51195654739f2537b98a188
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-enable-streaming"></a><span data-ttu-id="0df66-102">Como habilitar transmissão</span><span class="sxs-lookup"><span data-stu-id="0df66-102">How to: Enable Streaming</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="0df66-103">pode enviar mensagens usando transferências em buffer ou transmitidas.</span><span class="sxs-lookup"><span data-stu-id="0df66-103"> can send messages using either buffered or streamed transfers.</span></span> <span data-ttu-id="0df66-104">No modo de transferência em buffer padrão, uma mensagem deve ser entregue completamente antes de um destinatário possa lê-lo.</span><span class="sxs-lookup"><span data-stu-id="0df66-104">In the default buffered-transfer mode, a message must be completely delivered before a receiver can read it.</span></span> <span data-ttu-id="0df66-105">No modo de transferência de streaming, o receptor pode começar a processar a mensagem antes de entregar completamente.</span><span class="sxs-lookup"><span data-stu-id="0df66-105">In streaming transfer mode, the receiver can begin to process the message before it is completely delivered.</span></span> <span data-ttu-id="0df66-106">O modo de streaming é útil quando as informações que são passadas é demoradas e podem ser processadas em série.</span><span class="sxs-lookup"><span data-stu-id="0df66-106">The streaming mode is useful when the information that is passed is lengthy and can be processed serially.</span></span> <span data-ttu-id="0df66-107">O modo contínuo também é útil quando a mensagem é muito grande para ser totalmente armazenada em buffer.</span><span class="sxs-lookup"><span data-stu-id="0df66-107">Streaming mode is also useful when the message is too large to be entirely buffered.</span></span>  
  
 <span data-ttu-id="0df66-108">Para habilitar o streaming, definir o `OperationContract` adequadamente e habilitar o streaming no nível do transporte.</span><span class="sxs-lookup"><span data-stu-id="0df66-108">To enable streaming, define the `OperationContract` appropriately and enable streaming at the transport level.</span></span>  
  
### <a name="to-stream-data"></a><span data-ttu-id="0df66-109">Para transmitir dados</span><span class="sxs-lookup"><span data-stu-id="0df66-109">To stream data</span></span>  
  
1.  <span data-ttu-id="0df66-110">Para transmitir dados, o `OperationContract` para o serviço deve atender a dois requisitos:</span><span class="sxs-lookup"><span data-stu-id="0df66-110">To stream data, the `OperationContract` for the service must satisfy two requirements:</span></span>  
  
    1.  <span data-ttu-id="0df66-111">O parâmetro que contém os dados sejam transmitidos deve ser o único parâmetro do método.</span><span class="sxs-lookup"><span data-stu-id="0df66-111">The parameter that holds the data to be streamed must be the only parameter in the method.</span></span> <span data-ttu-id="0df66-112">Por exemplo, se a mensagem de entrada for a ser transmitido, a operação deve ter exatamente um parâmetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="0df66-112">For example, if the input message is the one to be streamed, the operation must have exactly one input parameter.</span></span> <span data-ttu-id="0df66-113">Da mesma forma, se a mensagem de saída é a transmissão, a operação deve ter exatamente uma saída ou um valor de retorno.</span><span class="sxs-lookup"><span data-stu-id="0df66-113">Similarly, if the output message is to be streamed, the operation must have either exactly one output parameter or a return value.</span></span>  
  
    2.  <span data-ttu-id="0df66-114">Pelo menos um dos tipos de valor de parâmetro e retorno deve ser <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message>, ou <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="0df66-114">At least one of the types of the parameter and return value must be either <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message>, or <xref:System.Xml.Serialization.IXmlSerializable>.</span></span>  
  
     <span data-ttu-id="0df66-115">Este é um exemplo de um contrato de dados em fluxo.</span><span class="sxs-lookup"><span data-stu-id="0df66-115">The following is an example of a contract for streamed data.</span></span>  
  
     [!code-csharp[c_HowTo_EnableStreaming#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming/cs/service.cs#1)]
     [!code-vb[c_HowTo_EnableStreaming#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_enablestreaming/vb/service.vb#1)]  
  
     <span data-ttu-id="0df66-116">O `GetStream` operação recebe alguns dados no buffer de entrada como um `string`, que é armazenado em buffer e retorna um `Stream`, que é transmitido.</span><span class="sxs-lookup"><span data-stu-id="0df66-116">The `GetStream` operation receives some buffered input data as a `string`, which is buffered, and returns a `Stream`, which is streamed.</span></span> <span data-ttu-id="0df66-117">Por outro lado `UploadStream` assume um `Stream` (Streaming) e retorna um `bool` (em buffer).</span><span class="sxs-lookup"><span data-stu-id="0df66-117">Conversely `UploadStream` takes in a `Stream` (streamed) and returns a `bool` (buffered).</span></span> <span data-ttu-id="0df66-118">`EchoStream`Obtém e retorna `Stream` e é um exemplo de uma operação cujas entradas e mensagens de saída ambos são transmitidas.</span><span class="sxs-lookup"><span data-stu-id="0df66-118">`EchoStream` takes and returns `Stream` and is an example of an operation whose input and output messages are both streamed.</span></span> <span data-ttu-id="0df66-119">Por fim, `GetReversedStream` não usa nenhuma entrada e retorna um `Stream` (Streaming).</span><span class="sxs-lookup"><span data-stu-id="0df66-119">Finally, `GetReversedStream` takes no inputs and returns a `Stream` (streamed).</span></span>  
  
2.  <span data-ttu-id="0df66-120">Streaming deve ser habilitado na associação.</span><span class="sxs-lookup"><span data-stu-id="0df66-120">Streaming must be enabled on the binding.</span></span> <span data-ttu-id="0df66-121">Definir um `TransferMode` propriedade, que pode ter um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="0df66-121">You set a `TransferMode` property, which can take one of the following values:</span></span>  
  
    1.  <span data-ttu-id="0df66-122">`Buffered`,</span><span class="sxs-lookup"><span data-stu-id="0df66-122">`Buffered`,</span></span>  
  
    2.  <span data-ttu-id="0df66-123">`Streamed`, que permite a comunicação de streaming em ambas as direções.</span><span class="sxs-lookup"><span data-stu-id="0df66-123">`Streamed`, which enables streaming communication in both directions.</span></span>  
  
    3.  <span data-ttu-id="0df66-124">`StreamedRequest`, que permite que a solicitação apenas de streaming.</span><span class="sxs-lookup"><span data-stu-id="0df66-124">`StreamedRequest`, which enables streaming the request only.</span></span>  
  
    4.  <span data-ttu-id="0df66-125">`StreamedResponse`, que permite que o fluxo de resposta.</span><span class="sxs-lookup"><span data-stu-id="0df66-125">`StreamedResponse`, which enables streaming the response only.</span></span>  
  
     <span data-ttu-id="0df66-126">O `BasicHttpBinding` expõe o `TransferMode` propriedade na associação, como o `NetTcpBinding` e `NetNamedPipeBinding`.</span><span class="sxs-lookup"><span data-stu-id="0df66-126">The `BasicHttpBinding` exposes the `TransferMode` property on the binding, as does `NetTcpBinding` and `NetNamedPipeBinding`.</span></span> <span data-ttu-id="0df66-127">O `TransferMode` propriedade também pode ser definida no elemento de associação de transporte e usada em uma associação personalizada.</span><span class="sxs-lookup"><span data-stu-id="0df66-127">The `TransferMode` property can also be set on the transport binding element and used in a custom binding.</span></span>  
  
     <span data-ttu-id="0df66-128">Os exemplos a seguir mostram como definir `TransferMode` código e alterando o arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="0df66-128">The following samples show how to set `TransferMode` by code and by changing the configuration file.</span></span> <span data-ttu-id="0df66-129">Os exemplos também definido o `maxReceivedMessageSize` propriedade 64 MB, que impõe um limite de tamanho máximo permitido de mensagens no recebimento.</span><span class="sxs-lookup"><span data-stu-id="0df66-129">The samples also both set the `maxReceivedMessageSize` property to 64 MB, which places a cap on the maximum allowable size of messages on receive.</span></span> <span data-ttu-id="0df66-130">O padrão `maxReceivedMessageSize` é 64 KB, que geralmente é muito baixa para cenários de streaming.</span><span class="sxs-lookup"><span data-stu-id="0df66-130">The default `maxReceivedMessageSize` is 64 KB, which is usually too low for streaming scenarios.</span></span> <span data-ttu-id="0df66-131">Defina essa configuração de cota conforme apropriado, dependendo do tamanho máximo de mensagens de que seu aplicativo espera receber.</span><span class="sxs-lookup"><span data-stu-id="0df66-131">Set this quota setting as appropriate depending on the maximum size of messages your application expects to receive.</span></span> <span data-ttu-id="0df66-132">Observe também que `maxBufferSize` controla o tamanho máximo que é armazenado em buffer e defini-lo apropriadamente.</span><span class="sxs-lookup"><span data-stu-id="0df66-132">Also note that `maxBufferSize` controls the maximum size that is buffered, and set it appropriately.</span></span>  
  
    1.  <span data-ttu-id="0df66-133">O trecho do exemplo de configuração a seguir mostra a configuração de `TransferMode` propriedade para streaming no `basicHttpBinding` e uma associação HTTP personalizada.</span><span class="sxs-lookup"><span data-stu-id="0df66-133">The following configuration snippet from the sample shows setting the `TransferMode` property to streaming on the `basicHttpBinding` and a custom HTTP binding.</span></span>  
  
         [!code-xml[c_HowTo_EnableStreaming#103](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming/common/app.config#103)]   
  
    2.  <span data-ttu-id="0df66-134">O trecho de código a seguir mostra a configuração de `TransferMode` propriedade para streaming no `basicHttpBinding` e uma associação HTTP personalizada.</span><span class="sxs-lookup"><span data-stu-id="0df66-134">The following code snippet shows setting the `TransferMode` property to streaming on the `basicHttpBinding` and a custom HTTP binding.</span></span>  
  
         [!code-csharp[c_HowTo_EnableStreaming_code#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming_code/cs/c_howto_enablestreaming_code.cs#2)]
         [!code-vb[c_HowTo_EnableStreaming_code#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_enablestreaming_code/vb/c_howto_enablestreaming_code.vb#2)]  
  
    3.  <span data-ttu-id="0df66-135">O trecho de código a seguir mostra a configuração de `TransferMode` propriedade para streaming em uma associação personalizada de TCP.</span><span class="sxs-lookup"><span data-stu-id="0df66-135">The following code snippet shows setting the `TransferMode` property to streaming on a custom TCP binding.</span></span>  
  
         [!code-csharp[c_HowTo_EnableStreaming_code#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming_code/cs/c_howto_enablestreaming_code.cs#3)]
         [!code-vb[c_HowTo_EnableStreaming_code#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_enablestreaming_code/vb/c_howto_enablestreaming_code.vb#3)]  
  
3.  <span data-ttu-id="0df66-136">As operações `GetStream`, `UploadStream`, e `EchoStream` todos lidam com enviar dados diretamente de um arquivo ou salvar dados recebidos diretamente para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="0df66-136">The operations `GetStream`, `UploadStream`, and `EchoStream` all deal with sending data directly from a file or saving received data directly to a file.</span></span> <span data-ttu-id="0df66-137">O código a seguir é para `GetStream`.</span><span class="sxs-lookup"><span data-stu-id="0df66-137">The following code is for `GetStream`.</span></span>  
  
     [!code-csharp[c_HowTo_EnableStreaming#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming/cs/service.cs#4)]
     [!code-vb[c_HowTo_EnableStreaming#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_enablestreaming/vb/service.vb#4)]  
  
### <a name="writing-a-custom-stream"></a><span data-ttu-id="0df66-138">Gravando um fluxo personalizados</span><span class="sxs-lookup"><span data-stu-id="0df66-138">Writing a custom stream</span></span>  
  
1.  <span data-ttu-id="0df66-139">Para fazer um processamento especial em cada parte de um fluxo de dados como ele está sendo enviado ou recebida, derive uma classe de fluxo personalizados de <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="0df66-139">To do special processing on each chunk of a data stream as it is being sent or received, derive a custom stream class from <xref:System.IO.Stream>.</span></span> <span data-ttu-id="0df66-140">Como um exemplo de um fluxo personalizado, o código a seguir contém um `GetReversedStream` método e uma `ReverseStream` classe-.</span><span class="sxs-lookup"><span data-stu-id="0df66-140">As an example of a custom stream, the following code contains a `GetReversedStream` method and a `ReverseStream` class-.</span></span>  
  
     <span data-ttu-id="0df66-141">`GetReversedStream`cria e retorna uma nova instância da `ReverseStream`.</span><span class="sxs-lookup"><span data-stu-id="0df66-141">`GetReversedStream` creates and returns a new instance of `ReverseStream`.</span></span> <span data-ttu-id="0df66-142">O processamento real ocorre como o sistema lê a partir de `ReverseStream` objeto.</span><span class="sxs-lookup"><span data-stu-id="0df66-142">The actual processing happens as the system reads from the `ReverseStream` object.</span></span> <span data-ttu-id="0df66-143">O `ReverseStream.Read` método lê um bloco de bytes do arquivo de base, reverte-los e retorna os bytes invertidos.</span><span class="sxs-lookup"><span data-stu-id="0df66-143">The `ReverseStream.Read` method reads a chunk of bytes from the underlying file, reverses them, then returns the reversed bytes.</span></span> <span data-ttu-id="0df66-144">Esse método não reverte o conteúdo do arquivo inteiro; ele reserva um bloco de bytes de cada vez.</span><span class="sxs-lookup"><span data-stu-id="0df66-144">This method does not reverse the entire file content; it reverses one chunk of bytes at a time.</span></span> <span data-ttu-id="0df66-145">Este exemplo mostra como você pode executar o processamento de fluxo que o conteúdo está sendo lida para ou gravada do fluxo.</span><span class="sxs-lookup"><span data-stu-id="0df66-145">This example shows how you can perform stream processing as the content is being read to or written from the stream.</span></span>  
  
     [!code-csharp[c_HowTo_EnableStreaming#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming/cs/service.cs#2)]
     [!code-vb[c_HowTo_EnableStreaming#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_enablestreaming/vb/service.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="0df66-146">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0df66-146">See Also</span></span>  
 [<span data-ttu-id="0df66-147">Dados grandes e Streaming</span><span class="sxs-lookup"><span data-stu-id="0df66-147">Large Data and Streaming</span></span>](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)  
 [<span data-ttu-id="0df66-148">Fluxo</span><span class="sxs-lookup"><span data-stu-id="0df66-148">Stream</span></span>](../../../../docs/framework/wcf/samples/stream.md)