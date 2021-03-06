---
title: Hello atividade personalizado
ms.date: 03/30/2017
ms.assetid: 72b1dd0a-9aad-47d5-95a9-a1024ee1d0a1
ms.openlocfilehash: 35ae5933515b3280b0d8d95157c8dd5f40f7b320
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515831"
---
# <a name="hello-world-custom-activity"></a>Hello atividade personalizado
Este exemplo demonstra vários recursos importantes do Windows Workflow Foundation (WF), incluindo como criar uma atividade personalizada simple. Alguns dos recursos demonstrados nesse exemplo são criando uma atividade personalizado em C# e estão usando `in` e argumentos de `out` (<xref:System.Activities.InArgument> e <xref:System.Activities.OutArgument>).  
  
> [!IMPORTANT]
>  Os exemplos podem mais ser instalados no seu computador. Verifique o seguinte diretório (padrão) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se este diretório não existir, vá para [Windows Communication Foundation (WCF) e exemplos do Windows Workflow Foundation (WF) para o .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para baixar todos os Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemplos. Este exemplo está localizado no seguinte diretório.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\HelloWorld`  
  
## <a name="creating-a-workflow-in-code"></a>Criando um fluxo de trabalho no código  
 Nesse exemplo, duas atividades personalizados são criadas usando o código em c. Ambas as atividades personalizados herdam direta ou indiretamente de <xref:System.Activities.Activity%601> para retornar um único valor. A vantagem de usar o valor de retorno genérico, em vez de herdar da classe não genérico de <xref:System.Activities.Activity> , é que quaisquer atividades (como <xref:System.Activities.Statements.Assign>) podem acessar o valor de retorno quando usadas como parte de uma atividade composto.  
  
 AppendString  
 Esta atividade herda de <xref:System.Activities.Activity%601>, e usa uma atividade de <xref:System.Activities.Statements.Assign> que concatene duas cadeias de caracteres juntos.  
  
 Preceda a cadeia de caracteres  
 Esta atividade herda diretamente de <xref:System.Activities.CodeActivity%601>, e criar a funcionalidade semelhante à atividade de `AppendString` , que usa a lógica implementada no código em vez de ser composta de uma atividade preexistente.  
  
 Os seguintes arquivos são incluídos no projeto.  
  
 AppendString.cs  
 A atividade personalizado que acrescenta cadeias de caracteres juntos. Ele usa uma cadeia de caracteres e a combina com uma cadeia de caracteres de texto literal "hello world diz" para formar uma mensagem completa como saída.  
  
 PrependString.cs  
 Esta atividade prefixar uma cadeia de caracteres predefinida a uma cadeia de caracteres de entrada.  
  
 Sequence1.xaml  
 Um fluxo de trabalho que usa as atividades personalizado de `AppendString` e de `PrependString` .  
  
 Module.vb  
 Um programa que executa o fluxo de trabalho.  
  
#### <a name="to-use-this-sample"></a>Para usar este exemplo  
  
1.  Usando [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra o arquivo de solução de HelloWorld.sln.  
  
2.  Para criar a solução, pressione CTRL+SHIFT+B.  
  
3.  Para executar a solução, pressione F5.