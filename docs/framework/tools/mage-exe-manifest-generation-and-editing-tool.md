---
title: Mage.exe (Ferramenta de Geração e Edição de Manifesto)
ms.date: 03/30/2017
helpviewer_keywords:
- Manifest Generation and Editing tool
- Mage.exe
ms.assetid: 77dfe576-2962-407e-af13-82255df725a1
ms.openlocfilehash: 8144e82f55522f65de96c120f42c50702b80fa16
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36208251"
---
# <a name="mageexe-manifest-generation-and-editing-tool"></a>Mage.exe (Ferramenta de Geração e Edição de Manifesto)
A Manifest Generation and Editing Tool (*Mage.exe*) é uma ferramenta de linha de comando compatível com a criação e a edição dos manifestos de aplicativo e implantação. Como uma ferramenta de linha de comando, *Mage.exe* pode ser executada tanto de scripts de lote quanto de outros aplicativos baseados no Windows, inclusive aplicativos do [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].  
  
 Também é possível usar *MageUI.exe*, um aplicativo gráfico, em vez de *Mage.exe*. Para obter mais informações, consulte [MageUI.exe (Ferramenta de Geração e Edição de Manifesto, Cliente Gráfico)](../../../docs/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md).  
  
 Essa ferramenta é instalada automaticamente com o Visual Studio. Para executar a ferramenta, use o Prompt de Comando do Desenvolvedor (ou o Prompt de Comando do Visual Studio no Windows 7). Para obter mais informações, consulte [Prompts de Comando](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 Duas versões de *Mage.exe* e de *MageUI.exe* estão incluídas como um componente da configuração do [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)]. Para ver informações da versão, execute *MageUI.exe*, selecione **Ajuda** e então selecione **Sobre**. Esta documentação descreve a versão 4.0.x.x do *Mage.exe* e do *MageUI.exe*.  
  
 No prompt de comando, digite o seguinte:  
  
## <a name="syntax"></a>Sintaxe  
  
```  
Mage [commands] [commandOptions]  
```  
  
#### <a name="parameters"></a>Parâmetros  
 A tabela a seguir mostra os comandos compatíveis com *Mage.exe*. Para obter mais informações sobre as opções com suporte por esses comandos, consulte [Opções de Comando Novas e Atualizadas](#NewUpdate) e [Opções do Comando de Entrada](#Sign).  
  
|Comando|Descrição|  
|-------------|-----------------|  
|**-cc, ClearApplicationCache**|Limpa o cache do aplicativo baixado somente de todos os aplicativos online.|  
|**-n, -New** *fileType [newOptions]*|Cria um novo arquivo do tipo indicado. Os tipos válidos são:<br /><br /> -   `Deployment`: cria um novo manifesto de implantação.<br />-   `Application`: cria um novo manifesto do aplicativo.<br /><br /> Se você não especificar parâmetros adicionais com esse comando, ele criará um arquivo do tipo apropriado, com as marcas padrão adequadas e os valores de atributo.<br /><br /> Use a opção **-ToFile** (consulte na tabela a seguir) para especificar o nome e o caminho do arquivo novo.<br /><br /> Use a opção **-FromDirectory** (consulte na tabela a seguir) para criar um manifesto do aplicativo com todos os assemblies de um aplicativo adicionado à seção \<dependency> do manifesto.|  
|**-u, -Update** *[filePath] [updateOptions]*|Faz uma ou mais alterações em um arquivo de manifesto. Você não precisa especificar o tipo de arquivo que está editando. Mage.exe examinará o arquivo usando um conjunto de heurística e determinará se ele é um manifesto de implantação ou um manifesto de aplicativo.<br /><br /> Se você já tiver assinado um arquivo com um certificado, **-Update** removerá o bloco de assinatura chave. Isso é porque a assinatura-chave contém um hash do arquivo e a modificação do arquivo invalida o hash.<br /><br /> Use a opção **-ToFile** (consulte na tabela a seguir) para especificar um novo nome e caminho de arquivo, em vez de substituir o arquivo existente.|  
|**-s, -Sign** `[signOptions]`|Usa um par de chaves ou um certificado X509 para assinar um arquivo. As assinaturas são inseridas como elementos XML nos arquivos.<br /><br /> Você deve estar conectado à Internet ao assinar um manifesto que especifica um valor **-TimestampUri**.|  
|**-h, -?, -Help** *[verbose]*|Descreve todos os comandos disponíveis e suas opções. Especifique `verbose` para obter ajuda detalhada.|  
  
<a name="NewUpdate"></a>   
## <a name="new-and-update-command-options"></a>Opções de Comando Novas e Atualizadas  

A tabela a seguir mostra as opções compatíveis com os comandos `-New` e `-Update`:  
  
|Opções|Valor padrão|Aplica-se a|Descrição|  
|-------------|-------------------|----------------|-----------------|  
|**-a, -Algorithm**|sha1RSA|Manifestos de aplicativo.<br /><br /> Manifestos de implantação.|Especifica o algoritmo com o qual gerar resumos de dependência. O valor deve ser "sha256RSA" ou "sha1RSA.<br /><br /> Use com a opção "-Update". Essa opção é ignorada durante o uso da opção "-Sign"|  
|**-appc, -AppCodeBase** `manifestReference`||Manifestos de implantação.|Insere uma referência de URL ou de caminho do arquivo no arquivo de manifesto do aplicativo. Esse valor deve ser o caminho completo do manifesto de aplicativo.|  
|**-appm, -AppManifest** `manifestPath`||Manifestos de implantação.|Insere uma referência para o manifesto de aplicativo de uma implantação no manifesto de implantação.<br /><br /> O arquivo indicado por `manifestPath` deve existir, ou *Mage.exe* emitirá um erro. Se o arquivo referenciado por `manifestPath` não for um manifesto do aplicativo, *Mage.exe* emitirá um erro.|  
|**-cf, -CertFile** `filePath`||Todos os tipos de arquivo.|Especifica o local de um certificado digital X509 para assinar um manifesto. Essa opção poderá ser usada com a opção **-Password** se o certificado exigir uma senha.<br/><br/>A partir do SDK do .NET Framework 4.6.2 (distribuído com o Visual Studio), do SDK do Windows e do Pacote do Desenvolvedor do .NET Framework 4.6.2, o *Mage.exe* assina manifestos CNG, bem como certificados CAPI.|  
|**-ch, -CertHash** `hashSignature`||Todos os tipos de arquivo.|O hash de um certificado digital armazenado no repositório de certificados pessoais do computador cliente. Isso corresponde à cadeia de caracteres Impressão Digital de um certificado digital exibido no Windows Certificates Console.<br /><br /> `hashSignature` pode ter maiúsculas ou minúsculas e ser fornecido como uma única cadeia de caracteres ou com cada octeto da Impressão Digital separado por espaços e toda a Impressão Digital entre aspas.|  
|**-fd, -FromDirectory** `directoryPath`||Manifestos de aplicativo.|Popula o manifesto do aplicativo com descrições de todos os assemblies e arquivos encontrados em `directoryPath`, inclusive todos os subdiretórios, em que `directoryPath` é o diretório que contém o aplicativo que você deseja implantar. Para cada arquivo no diretório, *Mage.exe* decide se o arquivo é um assembly ou um arquivo estático. Se for um assembly, ele adicionará uma marca `<dependency>` e um atributo `installFrom` ao aplicativo com o nome do assembly, a base de código e a versão. Se for um arquivo estático, ele adicionará uma marca `<file>`. *Mage.exe* também usará um conjunto simples de heurística para detectar o executável principal do aplicativo e o marcará como o ponto de entrada do aplicativo ClickOnce no manifesto.<br /><br /> *Mage.exe* jamais marcará automaticamente um arquivo como um arquivo de "dados". Você deve fazer isso manualmente. Para obter mais informações, consulte [Como incluir um arquivo de dados em um aplicativo ClickOnce](/visualstudio/deployment/how-to-include-a-data-file-in-a-clickonce-application).<br /><br /> *Mage.exe* também gera um hash para cada arquivo com base em seu tamanho. ClickOnce usa esses hashes para garantir que ninguém adultere os arquivos de implantação desde a criação do manifesto. Se algum dos arquivos na sua implantação mudar, você poderá executar o *Mage.exe* com o comando **-Update** e com a opção **-FromDirectory**, e ele atualizará as versões do assembly e hashes de todos os arquivos referenciados.<br /><br /> **-FromDirectory** incluirá todos os arquivos em todos os subdiretórios encontrados em `directoryPath`.<br /><br /> Se você usar **-FromDirectory** com o comando **-Update**, o *Mage.exe* removerá todos os arquivos no manifesto do aplicativo que não existem mais no diretório.|  
|**-if, -IconFile**  `filePath`||Manifestos de aplicativo.|Especifica o caminho completo para um arquivo de ícone .ICO. Esse ícone é exibido ao lado do nome do aplicativo no menu Iniciar e na entrada Adicionar ou Remover Programas. Se nenhum ícone for fornecido, será usado um ícone padrão.|  
|**-ip, -IncludeProviderURL**  `url`|true|Manifestos de implantação.|Indica se o manifesto de implantação inclui o valor local de atualização definido por **-ProviderURL**.|  
|**-i, -Install** `willInstall`|true|Manifestos de implantação.|Indica se o aplicativo ClickOnce deve ou não ser instalado no computador local, ou se o deve ser executado na Web. A instalação de um aplicativo dá a esse aplicativo uma presença no menu **Iniciar** do Windows. Os valores válidos são "true" ou "t" e "false" ou "f".<br /><br /> Se você especificar a opção **-MinVersion** e um usuário tiver uma versão inferior a **-MinVersion** instalada, ela forçará a instalação do aplicativo, independentemente do valor passado para **-Install**.<br /><br /> Essa opção não pode ser usada com a opção **-BrowserHosted**. A tentativa de especificar ambos para o mesmo manifesto resultará em um erro.|  
|**-mv, -MinVersion**  `[version]`|A versão listada no manifesto de implantação do ClickOnce conforme especificado pelo sinalizador **-Version**.|Manifestos de implantação.|A versão mínima desse aplicativo que um usuário pode executar. Esse sinalizador torna a versão nomeada do aplicativo uma atualização obrigatória. Se liberar uma versão do produto com uma atualização para uma alteração importante ou uma falha de segurança crítica, você poderá usar esse sinalizador para especificar se essa atualização deve ser instalada e se o usuário não pode continuar executando versões anteriores.<br /><br /> `version` tem a mesma semântica do argumento do sinalizador **-Version**.|  
|**-n, -Name** `nameString`|Implantar|Todos os tipos de arquivo.|O nome usado para identificar o aplicativo. O ClickOnce usará esse nome para identificar o aplicativo no menu **Iniciar** (se o aplicativo estiver configurado para se instalar) e nas caixas de diálogo Elevação de Permissão. **Observação:** se você estiver atualizando um manifesto existente e não especificar um nome do editor com essa opção, *Mage.exe* atualizará o manifesto com o nome da organização definido no computador. Para usar um nome diferente, não se esqueça de usar essa opção e especificar o nome do editor desejado.|  
|**-pwd, -Password** `passwd`||Todos os tipos de arquivo.|A senha que é usada na assinatura de um manifesto com um certificado digital. Deve ser usado com a opção **-CertFile**.|  
|**-p, Processor** `processorValue`|Msil|Manifestos de aplicativo.<br /><br /> Manifestos de implantação.|A arquitetura do microprocessador em que essa distribuição será executada. Esse valor será obrigatório se você estiver preparando uma ou mais instalações cujos assemblies foram pré-compilados para um microprocessador específico. Os valores válidos incluem `msil`, `x86`, `ia64` e `amd64`. `msil` é a Microsoft Intermediate Language, o que significa que todos os assemblies independem da plataforma e o CLR (Common Language Runtime) os compilará just-in-time quando o aplicativo for executado pela primeira vez.|  
|**-pu,** **-ProviderURL** `url`||Manifestos de implantação.|Especifica a URL que o ClickOnce examinará em busca de atualizações de aplicativo.|  
|**-pub, -Publisher** `publisherName`||Manifestos de aplicativo.<br /><br /> Manifestos de implantação.|Adiciona o nome do editor ao elemento de descrição do manifesto de implantação ou de aplicativo. Quando usado em um manifesto do aplicativo, **-UseManifestForTrust** também deve ser especificado com um valor "true" ou "t", do contrário, esse parâmetro gerará um erro.|  
|**-s, -SupportURL**  `url`||Manifestos de aplicativo.<br /><br /> Manifestos de implantação.|Especifica o link exibido em Adicionar ou Remover Programas do aplicativo ClickOnce.|  
|**-ti, -TimestampUri** `uri`||Manifestos de aplicativo.<br /><br /> Manifestos de implantação.|A URL de um serviço de carimbo de data/hora digital. O carimbo de data/hora dos manifestos evita que você precise assinar novamente os manifestos, caso o certificado digital expire antes de implantar a próxima versão do aplicativo. Para obter mais informações, consulte [Membros do programa de certificado raiz do Windows](http://go.microsoft.com/fwlink/?LinkId=159000).|  
|**-t, -ToFile** `filePath`|– New:<br />– Implantação: deploy.application<br />– Aplicativo: application.exe.manifest<br />– Update:<br />– O arquivo de entrada.|Todos os tipos de arquivo.|Especifica o caminho de saída do arquivo que foi criado ou modificado.<br /><br /> Se **-ToFile** não for fornecido quando você usar **-New**, a saída será gravada no diretório de trabalho atual. Se **-ToFile** não for fornecido quando você usar **-Update**, o *Mage.exe* gravará o arquivo novamente no arquivo de entrada.|  
|**-tr, -TrustLevel** `level`|Com base na zona em que reside a URL do aplicativo.|Manifestos de aplicativo.|O nível de confiança a ser concedido ao aplicativo em computadores cliente. Entre os valores estão "Internet", "Intranet" e "FullTrust".|  
|**-um, -UseManifestForTrust** `willUseForTrust`|False|Manifestos de aplicativo.|Especifica se a assinatura digital do manifesto de aplicativo será usada para na tomada de decisões de confiança quando o aplicativo é executado no cliente. A especificação de "true" ou "t" indica que o manifesto do aplicativo será usado em decisões de confiança. A especificação de "false" ou "f" indica que a assinatura do manifesto de implantação será usada.|  
|**-v, -Version** `versionNumber`|1.0.0.0|Manifestos de aplicativo.<br /><br /> Manifestos de implantação.|A versão da implantação. O argumento deve ser uma cadeia de caracteres de versão válida do formato "*N.N.N.N*", em que "*N*" é um inteiro de 32 bits sem sinal.|  
|**-wpf, -WPFBrowserApp**  `isWPFApp`|false|Manifestos de aplicativo.<br /><br /> Manifestos de implantação.|Só use esse sinalizador se o aplicativo for um aplicativo do WPF (Windows Presentation Foundation) que será hospedado dentro do Internet Explorer, e não um executável autônomo. Os valores válidos são "true" ou "t" e "false" ou "f".<br /><br /> Para manifestos de aplicativo, insere o atributo `hostInBrowser` no elemento `entryPoint` do manifesto de aplicativo.<br /><br /> Para manifestos de implantação, define o atributo `install` no elemento `deployment` como falso e salva o manifesto de implantação com uma extensão .xbap. A especificação desse argumento com o argumento **-Install** produz um erro, porque um aplicativo hospedado por navegador não pode ser instalado, aplicativo offline.|  
  
<a name="Sign"></a>   
## <a name="sign-command-options"></a>Opções do Comando de Entrada  
 A tabela a seguir mostra as opções compatíveis com o comando `-Sign`, que se aplicam a todos os tipos de arquivos.  
  
|Opções|Descrição|  
|-------------|-----------------|  
|**-cf, -CertFile** `filePath`|Especifica o local de um certificado digital para assinar um manifesto. Essa opção pode ser usada com a opção **-Password**.|  
|**-ch, -CertHash** `hashSignature`|O hash de um certificado digital armazenado no repositório de certificados pessoais do computador cliente. Isso corresponde à propriedade Impressão Digital de um certificado digital exibido no Windows Certificates Console.<br /><br /> `hashSignature` pode ter maiúsculas ou minúsculas e ser fornecido como uma única cadeia de caracteres ou com cada octeto da Impressão Digital separado por espaços e toda a Impressão Digital entre aspas.|  
|**-pwd, -Password** `passwd`|A senha que é usada na assinatura de um manifesto com um certificado digital. Deve ser usado com a opção **-CertFile**.|  
|**-t, -ToFile** `filePath`|Especifica o caminho de saída do arquivo que foi criado ou modificado.|  
  
## <a name="remarks"></a>Comentários  
 Os argumentos para *Mage.exe* não diferenciam maiúsculas de minúsculas. Os comandos e as opções podem ser precedidos por um traço (-) ou uma barra (/).  
  
 Todos os argumentos usados com o comando **-Sign** também podem ser usados a qualquer momento com os comandos **-New** ou **-Update**. Os comandos a seguir são equivalentes.  
  
```  
mage -Sign c:\HelloWorldDeployment\HelloWorld.deploy -CertFile cert.pfx  
mage -Update c:\HelloWorldDeployment\HelloWorld.deploy -CertFile cert.pfx  
```  
  
> [!NOTE]
>  A partir do .NET Framework versão 4.6.2, certificados CNG também têm suporte.  
  
 A assinatura é a última tarefa que você deve realizar, porque um documento assinado usa um hash do arquivo para verificar se a assinatura é válida para o documento. Se fizer alguma alteração em um arquivo assinado, você deverá assiná-lo novamente. Se você assinar um documento que foi assinado anteriormente, *Mage.exe* substituirá a assinatura anterior pela nova.  
  
 Quando você usar a opção **-AppManifest** para preencher um manifesto de implantação, o *Mage.exe* presumirá que o manifesto do aplicativo vai residir no mesmo diretório que o manifesto de implantação dentro de um subdiretório chamado depois da versão atual da implantação, e configurará o manifesto de implantação adequadamente. Se o manifesto de aplicativo for residir em outro lugar, use a opção **-AppCodeBase** para definir o local alternativo.  
  
 O manifesto de implantação e de aplicativo deverá ser assinado antes de você implantar o aplicativo. Para obter orientação sobre como assinar manifestos, consulte [Visão geral sobre implantação de aplicativos confiáveis](/visualstudio/deployment/trusted-application-deployment-overview).  
  
 A opção **-TrustLevel** para manifestos do aplicativo descreve o conjunto de permissões que um aplicativo precisa para ser executado no computador cliente. Por padrão, os aplicativos recebem um nível de confiança com base na *zona* em que a URL reside. Os aplicativos implantados em uma rede corporativa costumam ser colocados na zona Intranet, enquanto os implantados na Internet são colocados na zona Internet. Ambas as zonas de segurança impõem restrições sobre o acesso do aplicativo a recursos locais, com a zona Intranet um pouco mais permissiva do que a zona Internet. A zona FullTrust dá aos aplicativos acesso completo para recursos locais de um computador. Se você usar a opção **-TrustLevel** para colocar um aplicativo nessa zona, o componente Gerenciador de Confiança do CLR solicitará ao usuário decidir se deseja conceder ou não esse nível de confiança mais alto. Se estiver implantando o aplicativo em uma rede corporativa, você poderá usar a Implantação do Aplicativo de Confiança para aumentar o nível de confiança do aplicativo sem perguntar ao usuário.  
  
 Os manifestos de aplicativo também dão suporte a seções de confiança personalizadas. Isso ajuda o aplicativo a obedecer o princípio de segurança de solicitar permissão mínima, porque é possível configurar o manifesto para exigir apenas essas permissões específicas que o aplicativo exige para execução. *Mage.exe* não dá suporte direto à adição de uma seção de confiança personalizada. É possível adicionar uma usando um editor de texto, um analisador XML ou a ferramenta gráfica *MageUI.exe*. Para obter mais informações sobre como usar *MageUI.exe* para adicionar seções de confiança personalizadas, veja [MageUI.exe (Manifest Generation and Editing Tool, Cliente Gráfico)](../../../docs/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md).  
  
 Novo manifesto criado com a versão 4 de *Mage.exe*, incluído no [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)], têm como destino [!INCLUDE[net_client_v40_long](../../../includes/net-client-v40-long-md.md)]. Para ter versões anteriores do .NET Framework como destino, você deverá usar uma versão anterior do *Mage.exe*. Ao adicionar ou remover assemblies de um manifesto existente, ou assinar novamente um manifesto existente, *Mage.exe* não atualiza o manifesto para ter [!INCLUDE[net_client_v40_long](../../../includes/net-client-v40-long-md.md)] como destino. As tabelas a seguir mostram esses recursos e limitações.  
  
|Versão do manifesto|Operação|Mage v2.0|Mage v4.0|  
|----------------------|---------------|---------------|---------------|  
|Manifesto dos aplicativos com a versão 2.0 ou 3.x do .NET Framework como destino|Abrir|OK|OK|  
||Fechar|OK|OK|  
||Salvar|OK|OK|  
||Assinar Novamente|OK|OK|  
||Novo|OK|Sem suporte|  
||Atualizar (veja abaixo)|OK|OK|  
|Manifesto dos aplicativos com a versão 4 do .NET Framework como destino|Abrir|OK|OK|  
||Fechar|OK|OK|  
||Salvar|OK|OK|  
||Assinar Novamente|OK|OK|  
||Novo|Sem suporte|OK|  
||Atualizar (veja abaixo)|Sem suporte|OK|  
  
|Versão do manifesto|Detalhes da Operação de Atualização|Mage v2.0|Mage v4.0|  
|----------------------|------------------------------|---------------|---------------|  
|Manifesto dos aplicativos com a versão 2.0 ou 3.x do .NET Framework como destino|Modificar um assembly|OK|OK|  
||Adicionar um assembly|OK|OK|  
||Remover um assembly|OK|OK|  
|Manifesto dos aplicativos com a versão 4 do .NET Framework como destino|Modificar um assembly|Sem suporte|OK|  
||Adicionar um assembly|Sem suporte|OK|  
||Remover um assembly|Sem suporte|OK|  
  
 Mage.exe cria novos manifestos com o [!INCLUDE[net_client_v40_long](../../../includes/net-client-v40-long-md.md)] como destino. Os aplicativos ClickOnces com [!INCLUDE[net_client_v40_long](../../../includes/net-client-v40-long-md.md)] como destino podem ser executados no [!INCLUDE[net_client_v40_long](../../../includes/net-client-v40-long-md.md)] e na versão completa do [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]. Se o destino do aplicativo for a versão completa do [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] e não puder ser executado no [!INCLUDE[net_client_v40_long](../../../includes/net-client-v40-long-md.md)], remova o elemento `<framework>` do cliente usando um editor de texto e assine novamente o manifesto. A seguir, um elemento `<framework>` de amostra com o [!INCLUDE[net_client_v40_long](../../../includes/net-client-v40-long-md.md)] como destino.  
  
```xml  
<framework targetVersion="4.0" profile="client" supportedRuntime="4.0.20506" />  
```  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir abre a interface do usuário para Mage (*MageUI.exe*).  
  
```  
mage  
```  
  
 Os exemplos a seguir criam um manifesto de implantação padrão e o manifesto do aplicativo. Esses arquivos são todos criados no diretório de trabalho atual e chamados deploy.application e application.exe.manifest, respectivamente.  
  
```  
mage -New Deployment  
mage -New Application  
```  
  
 O exemplo a seguir cria um manifesto de aplicativo populado com todos os assemblies e arquivos de recurso do diretório atual.  
  
```  
mage -New Application -FromDirectory . -Version 1.0.0.0  
```  
  
 O exemplo a seguir continua o exemplo anterior especificando o nome da implantação e o microprocessador de destino. Ele também especifica uma URL na qual o ClickOnce deve verificar se há atualizações.  
  
```  
mage -New Application -FromDirectory . -Name "Hello, World! Application" -Version 1.0.0.0 -Processor "x86" -ProviderUrl http://internalserver/HelloWorld/  
```  
  
 O exemplo a seguir demonstra como criar um par de manifestos para implantar um aplicativo do WPF que será hospedado no Internet Explorer.  
  
```  
mage -New Application -FromDirectory . -Version 1.0.0.0 -WPFBrowserApp true  
mage -New Deployment -AppManifest 1.0.0.0\application.manifest -WPFBrowserApp true  
```  
  
 O exemplo a seguir atualiza um manifesto de implantação com informações de um manifesto de aplicativo e define a base de código do local do manifesto de aplicativo.  
  
```  
mage -Update HelloWorld.deploy -AppManifest 1.0.0.0\application.manifest -AppCodeBase http://internalserver/HelloWorld.deploy  
```  
  
 O exemplo a seguir edita o manifesto de implantação para forçar uma atualização da versão instalada do usuário.  
  
```  
mage -Update c:\HelloWorldDeployment\HelloWorld.deploy -MinVersion 1.1.0.0  
```  
  
 O exemplo a seguir informa o manifesto de implantação para recuperar o manifesto do aplicativo de outro diretório.  
  
```  
mage -Update HelloWorld.deploy -AppCodeBase http://anotherserver/HelloWorld/1.1.0.0/  
```  
  
 O exemplo a seguir assina um manifesto de implantação existente usando um certificado digital no diretório de trabalho atual.  
  
```  
mage -Sign deploy.application -CertFile cert.pfx -Password <passwd>  
```  
  
## <a name="see-also"></a>Consulte também  
 [Segurança e implantação do ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)  
 [Passo a passo: implantando um aplicativo ClickOnce manualmente](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)  
 [Visão geral da implantação de aplicativos confiáveis](/visualstudio/deployment/trusted-application-deployment-overview)  
 [MageUI.exe (Ferramenta de Geração e Edição de Manifesto, cliente gráfico)](../../../docs/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)  
 [Prompts de Comando](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
