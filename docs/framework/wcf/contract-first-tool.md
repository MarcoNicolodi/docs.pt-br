---
title: Ferramenta Contract-First
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a880690-f460-4475-a5f4-9f91ce08fcc6
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d00a4bac555166368114951625e18991e955cc02
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="contract-first-tool"></a><span data-ttu-id="2e2d0-102">Ferramenta Contract-First</span><span class="sxs-lookup"><span data-stu-id="2e2d0-102">Contract-First Tool</span></span>
<span data-ttu-id="2e2d0-103">Contratos de serviço geralmente precisam ser criado a partir de serviços existentes.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-103">Service contracts often need to be created from existing services.</span></span> <span data-ttu-id="2e2d0-104">Em [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], classes de contrato de dados podem ser criadas automaticamente, de serviços existentes usando a ferramenta de contrato, primeiro.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-104">In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], data contract classes can be created automatically from existing services using the contract-first tool.</span></span> <span data-ttu-id="2e2d0-105">Para usar a ferramenta de contrato, primeiro, o arquivo de definição de esquema XML (XSD) deve ser baixado localmente; a ferramenta não é possível importar os contratos de dados remotos por meio de HTTP.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-105">To use the contract-first tool, the XML schema definition file (XSD) must be downloaded locally; the tool cannot import remote data contracts via HTTP.</span></span>  
  
 <span data-ttu-id="2e2d0-106">A ferramenta de contrato, primeiro é integrada ao [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] como uma tarefa de compilação.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-106">The contract-first tool is integrated into [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] as a build task.</span></span> <span data-ttu-id="2e2d0-107">Os arquivos de código gerados pela tarefa de compilação são criados toda vez que o projeto é compilado, para que o projeto pode adotar facilmente as alterações no contrato de serviço subjacente.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-107">The code files generated by the build task are created every time the project is built, so that the project can easily adopt changes in the underlying service contract.</span></span>  
  
 <span data-ttu-id="2e2d0-108">Tipos de esquema que a ferramenta do primeiro contrato pode importar incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2e2d0-108">Schema types that the contract-first tool can import include the following:</span></span>  
  
```xml  
<xsd:complexType>  
<xsd:simpleType>  
```  
  
 <span data-ttu-id="2e2d0-109">Tipos simples não serão gerados se forem tipos primitivos como `Int16` ou `String`; complexos tipos não serão gerados se eles são do tipo `Collection`.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-109">Simple types will not be generated if they are primitives such as `Int16` or `String`; complex types will not be generated if they are of type `Collection`.</span></span> <span data-ttu-id="2e2d0-110">Tipos também não serão gerados se fizerem parte de outro `xsd:complexType`.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-110">Types will also not be generated if they are part of another `xsd:complexType`.</span></span> <span data-ttu-id="2e2d0-111">Nesses casos, os tipos serão referenciados para tipos existentes no projeto em vez disso.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-111">In all these cases, the types will be referenced to existing types in the project instead.</span></span>  
  
## <a name="adding-a-data-contract-to-a-project"></a><span data-ttu-id="2e2d0-112">Adicionando um contrato de dados a um projeto</span><span class="sxs-lookup"><span data-stu-id="2e2d0-112">Adding a data contract to a project</span></span>  
 <span data-ttu-id="2e2d0-113">Antes da ferramenta do primeiro contrato pode ser usada, o contrato de serviço (XSD) deve ser adicionado ao projeto.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-113">Before the contract-first tool can be used, the service contract (XSD) must be added to the project.</span></span> <span data-ttu-id="2e2d0-114">Para os fins desta visão geral, o contrato a seguir será usado para ilustrar as funções de contrato, primeiro.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-114">For the purposes of this overview, the following contract will be used to illustrate contract-first functions.</span></span> <span data-ttu-id="2e2d0-115">Esta definição de serviço é um pequeno subconjunto de contrato de serviço usado pela API de pesquisa de Bing.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-115">This service definition is a small subset of the service contract used by Bing’s search API.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="ServiceSchema"  
    targetNamespace="http://tempuri.org/ServiceSchema.xsd"  
    elementFormDefault="qualified"  
    xmlns="http://tempuri.org/ServiceSchema.xsd"  
    xmlns:mstns="http://tempuri.org/ServiceSchema.xsd"  
    xmlns:xs="http://www.w3.org/2001/XMLSchema"  
>  
  <xs:complexType name="SearchRequest">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="1" name="Version" type="xs:string" default="2.2" />  
      <xs:element minOccurs="0" maxOccurs="1" name="Market" type="xs:string" />  
      <xs:element minOccurs="0" maxOccurs="1" name="UILanguage" type="xs:string" />  
      <xs:element minOccurs="1" maxOccurs="1" name="Query" type="xs:string" />  
      <xs:element minOccurs="1" maxOccurs="1" name="AppId" type="xs:string" />  
      <xs:element minOccurs="0" maxOccurs="1" name="Latitude" type="xs:double" />  
      <xs:element minOccurs="0" maxOccurs="1" name="Longitude" type="xs:double" />  
      <xs:element minOccurs="0" maxOccurs="1" name="Radius" type="xs:double" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:simpleType name="WebSearchOption">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="DisableHostCollapsing" />  
      <xs:enumeration value="DisableQueryAlterations" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
```  
  
 <span data-ttu-id="2e2d0-116">Para adicionar o contrato de serviço acima para o projeto, clique com o botão direito e selecione **adicionar novo...** .</span><span class="sxs-lookup"><span data-stu-id="2e2d0-116">To add the above service contract to the project, right-click the project and select **Add New…**.</span></span> <span data-ttu-id="2e2d0-117">Selecione a definição de esquema do painel WCF da caixa de diálogo modelos e nomeie o novo arquivo SampleContract.xsd.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-117">Select Schema Definition from the WCF pane of the Templates dialog, and name the new file SampleContract.xsd.</span></span> <span data-ttu-id="2e2d0-118">Copie e cole o código acima para o modo de exibição de código do novo arquivo.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-118">Copy and paste the above code into the code view of the new file.</span></span>  
  
## <a name="configuring-contract-first-options"></a><span data-ttu-id="2e2d0-119">Configurando opções de primeiro contrato</span><span class="sxs-lookup"><span data-stu-id="2e2d0-119">Configuring contract-first options</span></span>  
 <span data-ttu-id="2e2d0-120">Opções de contrato, primeiro podem ser configuradas no menu de propriedades de um [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] projeto.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-120">Contract-first options can be configured in the Properties menu of a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] project.</span></span> <span data-ttu-id="2e2d0-121">Para habilitar o desenvolvimento de contrato, primeiro, selecione o **habilitar XSD como linguagem de definição de tipo** caixa de seleção na página de WCF da janela de propriedades do projeto.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-121">To enable contract-first development, select the **Enable XSD as Type Definition Language** check box in the WCF page of the project properties window.</span></span>  
  
 <span data-ttu-id="2e2d0-122">![Opções de projeto do WCF mostrando contrato &#45; primeiro](../../../docs/framework/wcf/media/contractfirstoptions.png "ContractFirstOptions")</span><span class="sxs-lookup"><span data-stu-id="2e2d0-122">![WCF Project Options showing contract&#45;first](../../../docs/framework/wcf/media/contractfirstoptions.png "ContractFirstOptions")</span></span>  
  
 <span data-ttu-id="2e2d0-123">Para configurar propriedades avançadas, clique no botão Avançado.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-123">To configure advanced properties, click the Advanced button.</span></span>  
  
 <span data-ttu-id="2e2d0-124">![Contrato avançado &#45; Propriedades do primeiro](../../../docs/framework/wcf/media/contractfirstadvanced.png "ContractFirstAdvanced")</span><span class="sxs-lookup"><span data-stu-id="2e2d0-124">![Advanced Contract&#45;First Properties](../../../docs/framework/wcf/media/contractfirstadvanced.png "ContractFirstAdvanced")</span></span>  
  
 <span data-ttu-id="2e2d0-125">As seguintes configurações avançadas podem ser configuradas para geração de código de contratos.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-125">The following advanced settings can be configured for code generation from contracts.</span></span> <span data-ttu-id="2e2d0-126">As configurações só podem ser configuradas para todos os arquivos no projeto; as configurações não podem ser configuradas para arquivos individuais no momento.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-126">Settings can only be configured for all of the files in the project; settings cannot be configured for individual files at this time.</span></span>  
  
-   <span data-ttu-id="2e2d0-127">**Modo de serializador**: essa configuração determina qual serializador é usado para ler arquivos de contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-127">**Serializer Mode**: This setting determines which serializer is used for reading service contract files.</span></span> <span data-ttu-id="2e2d0-128">Quando **serializador XML** for selecionada, o **tipos de coleção** e **reutilizar tipos** opções serão desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-128">When **XML Serializer** is selected, the **Collection Types** and **Reuse Types** options are disabled.</span></span> <span data-ttu-id="2e2d0-129">Essas opções se aplicam somente para o **serializador de contrato de dados**.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-129">These options only apply to the **Data Contract Serializer**.</span></span>  
  
-   <span data-ttu-id="2e2d0-130">**Reutilizar tipos**: essa configuração especifica quais bibliotecas são usadas para reutilização de tipo.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-130">**Reuse Types**: This setting specifies which libraries are used for type reuse.</span></span> <span data-ttu-id="2e2d0-131">Essa configuração se aplica somente se **modo serializador** é definido como **serializador de contrato de dados**.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-131">This setting only applies if **Serializer Mode** is set to **Data Contract Serializer**.</span></span>  
  
-   <span data-ttu-id="2e2d0-132">**Tipo de coleção**: essa configuração especifica o tipo totalmente qualificado ou qualificado por assembly a ser usado para o tipo de dados da coleção.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-132">**Collection Type**: This setting specifies the fully-qualified or assembly-qualified type to be used for the collection data type.</span></span> <span data-ttu-id="2e2d0-133">Essa configuração se aplica somente se **modo serializador** é definido como **serializador de contrato de dados**.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-133">This setting only applies if **Serializer Mode** is set to **Data Contract Serializer**.</span></span>  
  
-   <span data-ttu-id="2e2d0-134">**Tipo de dicionário**: essa configuração especifica o tipo totalmente qualificado ou qualificado por assembly a ser usado para o tipo de dados do dicionário.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-134">**Dictionary Type**: This setting specifies the fully-qualified or assembly-qualified type to be used for the dictionary data type.</span></span>  
  
-   <span data-ttu-id="2e2d0-135">**EnableDataBinding**: essa configuração especifica se deve implementar o <xref:System.ComponentModel.INotifyPropertyChanged> interface em todos os tipos de dados para implementar a associação de dados.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-135">**EnableDataBinding**: This setting specifies whether to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface on all data types to implement data binding.</span></span>  
  
-   <span data-ttu-id="2e2d0-136">**ExcludedTypes**: essa configuração especifica a lista de tipos totalmente qualificado ou qualificado por assembly a serem excluídos os assemblies referenciados.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-136">**ExcludedTypes**:This setting specifies the list of fully-qualified or assembly-qualified types to be excluded from the referenced assemblies.</span></span> <span data-ttu-id="2e2d0-137">Essa configuração se aplica somente se **modo serializador** é definido como **serializador de contrato de dados**.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-137">This setting only applies if **Serializer Mode** is set to **Data Contract Serializer**.</span></span>  
  
-   <span data-ttu-id="2e2d0-138">**GenerateInternalTypes**: essa configuração especifica se é para gerar classes que são marcados como internos.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-138">**GenerateInternalTypes**: This setting specifies whether to generate classes that are marked as internal.</span></span> <span data-ttu-id="2e2d0-139">Essa configuração se aplica somente se **modo serializador** é definido como **serializador de contrato de dados**.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-139">This setting only applies if **Serializer Mode** is set to **Data Contract Serializer**.</span></span>  
  
-   <span data-ttu-id="2e2d0-140">**GenerateSerializableTypes**: essa configuração especifica se deve gerar classes com o <xref:System.SerializableAttribute> atributo.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-140">**GenerateSerializableTypes**: This setting specifies whether to generate classes with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="2e2d0-141">Essa configuração se aplica somente se **modo serializador** é definido como **serializador de contrato de dados**.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-141">This setting only applies if **Serializer Mode** is set to **Data Contract Serializer**.</span></span>  
  
-   <span data-ttu-id="2e2d0-142">**ImportXMLTypes**: essa configuração especifica se deve configurar o serializador de contrato de dados para aplicar o <xref:System.SerializableAttribute> atributo classes sem o <xref:System.Runtime.Serialization.DataContractAttribute> atributo.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-142">**ImportXMLTypes**: This setting specifies whether to configure the data contract serializer to apply the <xref:System.SerializableAttribute> attribute to classes without the <xref:System.Runtime.Serialization.DataContractAttribute> attribute.</span></span>  <span data-ttu-id="2e2d0-143">Essa configuração se aplica somente se **modo serializador** é definido como **serializador de contrato de dados**.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-143">This setting only applies if **Serializer Mode** is set to **Data Contract Serializer**.</span></span>  
  
-   <span data-ttu-id="2e2d0-144">**SupportFx35TypedDataSets**: essa configuração especifica se fornecer funcionalidade adicional para conjuntos de dados tipados criados para o .net Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-144">**SupportFx35TypedDataSets**: This setting specifies whether to provide additional functionality for typed data sets created for .Net Framework 3.5.</span></span> <span data-ttu-id="2e2d0-145">Quando **modo serializador** é definido como **serializador XML**, o <xref:System.Data.Design.TypedDataSetSchemaImporterExtensionFx35> extensão será adicionada para o importador de esquema XML quando esse valor é definido como True.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-145">When  **Serializer Mode** is set to **XML Serializer**, the <xref:System.Data.Design.TypedDataSetSchemaImporterExtensionFx35> extension will be added to the XML schema importer when this value is set to True.</span></span> <span data-ttu-id="2e2d0-146">Quando **modo serializador** é definido como **serializador de contrato de dados**, o tipo <xref:System.DateTimeOffset> serão excluídos das referências quando esse valor é definido como False, para que um <xref:System.DateTimeOffset> sempre é gerada para versões mais antigas do framework.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-146">When  **Serializer Mode** is set to **Data Contract Serializer**, the type <xref:System.DateTimeOffset> will be excluded from the References when this value is set to False, so that a <xref:System.DateTimeOffset> is always generated for older framework versions.</span></span>  
  
-   <span data-ttu-id="2e2d0-147">**InputXsdFiles**: essa configuração especifica a lista de arquivos de entrada.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-147">**InputXsdFiles**: This setting specifies the list of input files.</span></span> <span data-ttu-id="2e2d0-148">Cada arquivo deve conter um esquema XML válido.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-148">Each file must contain a valid XML schema.</span></span>  
  
-   <span data-ttu-id="2e2d0-149">**Idioma**: essa configuração especifica o idioma de código de contrato gerado.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-149">**Language**: This setting specifies the language of the generated contract code.</span></span> <span data-ttu-id="2e2d0-150">A configuração deve ser reconhecida pelo <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-150">The setting must be recognizable by <xref:System.CodeDom.Compiler.CodeDomProvider>.</span></span>  
  
-   <span data-ttu-id="2e2d0-151">**NamespaceMappings**: essa configuração especifica os mapeamentos de Namespaces de destino de XSD para namespaces CLR.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-151">**NamespaceMappings**: This setting specifies the mappings from the XSD Target Namespaces to CLR namespaces.</span></span> <span data-ttu-id="2e2d0-152">Cada mapeamento deve usar o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="2e2d0-152">Each mapping should use the following format:</span></span>  
  
    ```xml  
    "<Schema Namespace>, <CLR Namespace>"  
    ```  
  
     <span data-ttu-id="2e2d0-153">O serializador XML aceita apenas um mapeamento no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="2e2d0-153">The XML Serializer only accepts one mapping in the following format:</span></span>  
  
    ```xml  
    "*, <CLR Namespace>"  
    ```  
  
-   <span data-ttu-id="2e2d0-154">**OutputDirectory**: essa configuração especifica o diretório onde os arquivos de código serão gerados.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-154">**OutputDirectory**: This setting specifies the directory where the code files will be generated.</span></span>  
  
 <span data-ttu-id="2e2d0-155">As configurações serão usadas para gerar tipos de contrato de serviço dos arquivos de contrato de serviço quando o projeto é compilado.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-155">The settings will be used to generate service contract types from the service contract files when the project is built.</span></span>  
  
## <a name="using-contract-first-development"></a><span data-ttu-id="2e2d0-156">Usando o desenvolvimento de primeiro contrato</span><span class="sxs-lookup"><span data-stu-id="2e2d0-156">Using contract-first development</span></span>  
 <span data-ttu-id="2e2d0-157">Depois de adicionar o contrato de serviço para o projeto e confirmar as configurações de compilação, compilar o projeto, pressionando **F6**.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-157">After adding the service contract to the project and confirming the build settings, build the project by pressing **F6**.</span></span> <span data-ttu-id="2e2d0-158">Os tipos definidos no contrato de serviço, em seguida, estarão disponíveis para uso no projeto.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-158">The types defined in the service contract will then be available for use in the project.</span></span>  
  
 <span data-ttu-id="2e2d0-159">Para usar os tipos definidos no contrato de serviço, adicione uma referência a `ContractTypes` sob o namespace atual:</span><span class="sxs-lookup"><span data-stu-id="2e2d0-159">To use the types defined in the service contract, add a reference to `ContractTypes` under the current namespace:</span></span>  
  
```csharp  
using MyProjectNamespace.ContractTypes;  
```  
  
 <span data-ttu-id="2e2d0-160">Os tipos definidos no contrato de serviço será resolvidos no projeto, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-160">The types defined in the service contract will then be resolvable in the project, as shown below.</span></span>  
  
 <span data-ttu-id="2e2d0-161">![Usando tipos derivados de um contrato de serviço](../../../docs/framework/wcf/media/contractfirsttypes.png "ContractFirstTypes")</span><span class="sxs-lookup"><span data-stu-id="2e2d0-161">![Using types derived from a service contract](../../../docs/framework/wcf/media/contractfirsttypes.png "ContractFirstTypes")</span></span>  
  
 <span data-ttu-id="2e2d0-162">Os tipos gerados pela ferramenta são criados no arquivo GeneratedXSDTypes.cs.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-162">The types generated by the tool are created in the GeneratedXSDTypes.cs file.</span></span> <span data-ttu-id="2e2d0-163">O arquivo é criado na \<diretório do projeto > /obj/\<configuração de compilação > diretório /XSDGeneratedCode/ por padrão.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-163">The file is created in the \<project directory>/obj/\<build configuration>/XSDGeneratedCode/ directory by default.</span></span> <span data-ttu-id="2e2d0-164">O esquema de exemplo no início deste tópico é convertido da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="2e2d0-164">The sample schema at the beginning of this topic is converted as follows:</span></span>  
  
```csharp
//------------------------------------------------------------------------------  
// <auto-generated>  
//     This code was generated by a tool.  
//     Runtime Version:4.0.30319.17330  
//  
//     Changes to this file may cause incorrect behavior and will be lost if  
//     the code is regenerated.  
// </auto-generated>  
//------------------------------------------------------------------------------  
  
namespace TestXSD3.ContractTypes  
{  
    using System.Xml.Serialization;  
  
    /// <remarks/>  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Xml", "4.0.30319.17330")]  
    [System.SerializableAttribute()]  
    [System.Diagnostics.DebuggerStepThroughAttribute()]  
    [System.ComponentModel.DesignerCategoryAttribute("code")]  
    [System.Xml.Serialization.XmlTypeAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd")]  
    [System.Xml.Serialization.XmlRootAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd", IsNullable=true)]  
    public partial class SearchRequest  
    {  
  
        private string versionField;  
  
        private string marketField;  
  
        private string uILanguageField;  
  
        private string queryField;  
  
        private string appIdField;  
  
        private double latitudeField;  
  
        private bool latitudeFieldSpecified;  
  
        private double longitudeField;  
  
        private bool longitudeFieldSpecified;  
  
        private double radiusField;  
  
        private bool radiusFieldSpecified;  
  
        public SearchRequest()  
        {  
            this.versionField = "2.2";  
        }  
  
        /// <remarks/>  
        [System.ComponentModel.DefaultValueAttribute("2.2")]  
        public string Version  
        {  
            get  
            {  
                return this.versionField;  
            }  
            set  
            {  
                this.versionField = value;  
            }  
        }  
  
        /// <remarks/>  
        public string Market  
        {  
            get  
            {  
                return this.marketField;  
            }  
            set  
            {  
                this.marketField = value;  
            }  
        }  
  
        /// <remarks/>  
        public string UILanguage  
        {  
            get  
            {  
                return this.uILanguageField;  
            }  
            set  
            {  
                this.uILanguageField = value;  
            }  
        }  
  
        /// <remarks/>  
        public string Query  
        {  
            get  
            {  
                return this.queryField;  
            }  
            set  
            {  
                this.queryField = value;  
            }  
        }  
  
        /// <remarks/>  
        public string AppId  
        {  
            get  
            {  
                return this.appIdField;  
            }  
            set  
            {  
                this.appIdField = value;  
            }  
        }  
  
        /// <remarks/>  
        public double Latitude  
        {  
            get  
            {  
                return this.latitudeField;  
            }  
            set  
            {  
                this.latitudeField = value;  
            }  
        }  
  
        /// <remarks/>  
        [System.Xml.Serialization.XmlIgnoreAttribute()]  
        public bool LatitudeSpecified  
        {  
            get  
            {  
                return this.latitudeFieldSpecified;  
            }  
            set  
            {  
                this.latitudeFieldSpecified = value;  
            }  
        }  
  
        /// <remarks/>  
        public double Longitude  
        {  
            get  
            {  
                return this.longitudeField;  
            }  
            set  
            {  
                this.longitudeField = value;  
            }  
        }  
  
        /// <remarks/>  
        [System.Xml.Serialization.XmlIgnoreAttribute()]  
        public bool LongitudeSpecified  
        {  
            get  
            {  
                return this.longitudeFieldSpecified;  
            }  
            set  
            {  
                this.longitudeFieldSpecified = value;  
            }  
        }  
  
        /// <remarks/>  
        public double Radius  
        {  
            get  
            {  
                return this.radiusField;  
            }  
            set  
            {  
                this.radiusField = value;  
            }  
        }  
  
        /// <remarks/>  
        [System.Xml.Serialization.XmlIgnoreAttribute()]  
        public bool RadiusSpecified  
        {  
            get  
            {  
                return this.radiusFieldSpecified;  
            }  
            set  
            {  
                this.radiusFieldSpecified = value;  
            }  
        }  
    }  
  
    /// <remarks/>  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Xml", "4.0.30319.17330")]  
    [System.SerializableAttribute()]  
    [System.Xml.Serialization.XmlTypeAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd")]  
    [System.Xml.Serialization.XmlRootAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd", IsNullable=false)]  
    public enum WebSearchOption  
    {  
  
        /// <remarks/>  
        DisableHostCollapsing,  
  
        /// <remarks/>  
        DisableQueryAlterations,  
    }  
}  
```  
  
## <a name="errors-and-warnings"></a><span data-ttu-id="2e2d0-165">Erros e avisos</span><span class="sxs-lookup"><span data-stu-id="2e2d0-165">Errors and warnings</span></span>  
 <span data-ttu-id="2e2d0-166">Erros e avisos encontrados ao analisar o esquema XSD aparecerão como erros e avisos de compilação.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-166">Errors and warnings encountered in parsing the XSD schema will appear as build errors and warnings.</span></span>  
  
## <a name="interface-inheritance"></a><span data-ttu-id="2e2d0-167">Herança de interface</span><span class="sxs-lookup"><span data-stu-id="2e2d0-167">Interface Inheritance</span></span>  
 <span data-ttu-id="2e2d0-168">Não é possível usar a herança de interface com o desenvolvimento de primeiro contrato; Isso é consistente com a maneira como as interfaces se comportam em outras operações.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-168">It is not possible to use interface inheritance with contract-first development; this is consistent with the way interfaces behave in other operations.</span></span> <span data-ttu-id="2e2d0-169">Para usar uma interface que herda de uma interface base, use dois pontos de extremidade separados.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-169">In order to use an interface that inherits a base interface, use two separate endpoints.</span></span> <span data-ttu-id="2e2d0-170">O primeiro ponto de extremidade usa o contrato herdado e o segundo ponto de extremidade implementa a interface base.</span><span class="sxs-lookup"><span data-stu-id="2e2d0-170">The first endpoint uses the inherited contract, and the second endpoint implements the base interface.</span></span>