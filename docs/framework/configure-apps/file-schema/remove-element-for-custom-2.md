---
title: '&lt;remover&gt; elemento para NameValueSectionHandler e DictionarySectionHandler'
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 27b01120cb279dc23b3b081e35f17addc6d1897d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="5cdca-102">\<Remover > elemento NameValueSectionHandler e DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="5cdca-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="5cdca-103">Remove uma configuração definida anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5cdca-103">Removes a previously defined setting.</span></span>

<span data-ttu-id="5cdca-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="5cdca-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="5cdca-105">&nbsp;&nbsp;[**\<sectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="5cdca-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="5cdca-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Remover >**</span><span class="sxs-lookup"><span data-stu-id="5cdca-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="5cdca-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5cdca-107">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="5cdca-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="5cdca-108">Attribute</span></span>

|           | <span data-ttu-id="5cdca-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="5cdca-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="5cdca-110">**key**</span><span class="sxs-lookup"><span data-stu-id="5cdca-110">**key**</span></span>   | <span data-ttu-id="5cdca-111">Atributo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="5cdca-111">Required attribute.</span></span><br><br><span data-ttu-id="5cdca-112">Especifica o nome da configuração a ser removido.</span><span class="sxs-lookup"><span data-stu-id="5cdca-112">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="5cdca-113">Elemento pai</span><span class="sxs-lookup"><span data-stu-id="5cdca-113">Parent element</span></span>

| <span data-ttu-id="5cdca-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="5cdca-114">Element</span></span> | <span data-ttu-id="5cdca-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="5cdca-115">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="5cdca-116">**\<sectionName >** elemento</span><span class="sxs-lookup"><span data-stu-id="5cdca-116">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="5cdca-117">Define as configurações para as seções de configuração personalizadas que usam o <xref:System.Configuration.NameValueSectionHandler> e <xref:System.Configuration.DictionarySectionHandler> classes.</span><span class="sxs-lookup"><span data-stu-id="5cdca-117">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="5cdca-118">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="5cdca-118">Child elements</span></span>

<span data-ttu-id="5cdca-119">Nenhum</span><span class="sxs-lookup"><span data-stu-id="5cdca-119">None</span></span>

## <a name="remarks"></a><span data-ttu-id="5cdca-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="5cdca-120">Remarks</span></span>

<span data-ttu-id="5cdca-121">Você pode usar o  **\<remover >** elemento para remover as configurações do seu aplicativo que foram definidas em um nível superior na hierarquia de arquivos de configuração.</span><span class="sxs-lookup"><span data-stu-id="5cdca-121">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="5cdca-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5cdca-122">Example</span></span>

<span data-ttu-id="5cdca-123">O exemplo a seguir mostra como usar o  **\<remover >** elemento em um arquivo de configuração do aplicativo para remover as configurações previamente definidas no arquivo de configuração da máquina.</span><span class="sxs-lookup"><span data-stu-id="5cdca-123">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="5cdca-124">O seguinte código de arquivo de configuração de máquina declara a seção  **\<mySection >** e adiciona as duas configurações, `key1` e `key2`, a ela:</span><span class="sxs-lookup"><span data-stu-id="5cdca-124">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

<span data-ttu-id="5cdca-125">O seguinte código de arquivo de configuração de aplicativo remove o `key2` configuração de  **\<mySection >**:</span><span class="sxs-lookup"><span data-stu-id="5cdca-125">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="5cdca-126">arquivo de configuração</span><span class="sxs-lookup"><span data-stu-id="5cdca-126">Configuration file</span></span>

<span data-ttu-id="5cdca-127">Esse elemento pode ser usado no arquivo de configuração do aplicativo, o arquivo de configuração de máquina (*Machine. config*), e *Web. config* arquivos que não estão no nível de diretório do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5cdca-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="5cdca-128">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5cdca-128">See also</span></span>

[<span data-ttu-id="5cdca-129">Esquema de arquivo de configuração para o .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5cdca-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)