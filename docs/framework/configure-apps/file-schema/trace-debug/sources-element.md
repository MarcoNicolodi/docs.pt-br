---
title: '&lt;fontes&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sources
helpviewer_keywords:
- sources element
- trace sources
- <sources> element
ms.assetid: c727b2e2-423a-4463-a223-013f40ff16a3
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 7abe1f4a536d9f321e0a8b300f9542255433c030
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2017
---
# <a name="ltsourcesgt-element"></a><span data-ttu-id="2d836-102">&lt;fontes&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="2d836-102">&lt;sources&gt; Element</span></span>
<span data-ttu-id="2d836-103">Especifica as fontes de rastreamento que iniciam as mensagens de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="2d836-103">Specifies trace sources that initiate tracing messages.</span></span>  
  
 <span data-ttu-id="2d836-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2d836-104">\<configuration></span></span>  
<span data-ttu-id="2d836-105">\<System. Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="2d836-105">\<system.diagnostics></span></span>  
<span data-ttu-id="2d836-106">\<fontes ></span><span class="sxs-lookup"><span data-stu-id="2d836-106">\<sources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d836-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2d836-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d836-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="2d836-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2d836-109">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="2d836-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d836-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="2d836-110">Attributes</span></span>  
 <span data-ttu-id="2d836-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="2d836-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2d836-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="2d836-112">Child Elements</span></span>  
  
|<span data-ttu-id="2d836-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="2d836-113">Element</span></span>|<span data-ttu-id="2d836-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="2d836-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d836-115">\<source></span><span class="sxs-lookup"><span data-stu-id="2d836-115">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)|<span data-ttu-id="2d836-116">Elemento obrigatório.</span><span class="sxs-lookup"><span data-stu-id="2d836-116">Required element.</span></span><br /><br /> <span data-ttu-id="2d836-117">Especifica uma origem de rastreamento que inicia as mensagens de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="2d836-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2d836-118">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="2d836-118">Parent Elements</span></span>  
  
|<span data-ttu-id="2d836-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="2d836-119">Element</span></span>|<span data-ttu-id="2d836-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="2d836-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2d836-121">O elemento raiz em cada arquivo de configuração usado pelos aplicativos do Common Language Runtime e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2d836-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="2d836-122">Especifica os ouvintes de rastreamento que coletam, armazenam e roteiam mensagens e o nível em que uma opção de rastreamento é definida.</span><span class="sxs-lookup"><span data-stu-id="2d836-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d836-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="2d836-123">Remarks</span></span>  
 <span data-ttu-id="2d836-124">Esse elemento pode ser usado no arquivo de configuração de máquina (Machine. config) e o arquivo de configuração do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2d836-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d836-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="2d836-125">Example</span></span>  
 <span data-ttu-id="2d836-126">O exemplo a seguir mostra como usar o `<sources>` elemento a ser adicionado a origem de rastreamento `mySource` e definir o nível para a alternância de origem nomeado `sourceSwitch`.</span><span class="sxs-lookup"><span data-stu-id="2d836-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="2d836-127">Um ouvinte de rastreamento do console é adicionado, que grava informações de rastreamento para o console.</span><span class="sxs-lookup"><span data-stu-id="2d836-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <sources>  
         <source name="mySource" switchName="sourceSwitch"   
            switchType="System.Diagnostics.SourceSwitch"  >  
            <listeners>  
               <add name="console"   
                  type="System.Diagnostics.ConsoleTraceListener" >  
                  <filter type="System.Diagnostics.EventTypeFilter"   
                     initializeData="Error" />  
               </add>  
               <remove name="Default" />  
            </listeners>  
         </source>  
      </sources>  
      <switches>  
         <add name="sourceSwitch" value="Warning" />  
      </switches>    
   </system.diagnostics>   
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d836-128">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2d836-128">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.ConsoleTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 <xref:System.Diagnostics.XmlWriterTraceListener>  
 [<span data-ttu-id="2d836-129">Esquema de configurações de rastreamento e depuração</span><span class="sxs-lookup"><span data-stu-id="2d836-129">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="2d836-130">\<source></span><span class="sxs-lookup"><span data-stu-id="2d836-130">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)