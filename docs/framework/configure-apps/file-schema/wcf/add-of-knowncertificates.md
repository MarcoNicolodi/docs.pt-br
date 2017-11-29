---
title: '&lt;adicionar&gt; &lt;knownCertificates&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e19bb495f360352b7304595323265d28773660a4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-of-ltknowncertificatesgt"></a><span data-ttu-id="3f637-102">&lt;adicionar&gt; &lt;knownCertificates&gt;</span><span class="sxs-lookup"><span data-stu-id="3f637-102">&lt;add&gt; of &lt;knownCertificates&gt;</span></span>
<span data-ttu-id="3f637-103">Adiciona um certificado x. 509 à coleção de certificados conhecidos.</span><span class="sxs-lookup"><span data-stu-id="3f637-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
 <span data-ttu-id="3f637-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3f637-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3f637-105">\<comportamentos ></span><span class="sxs-lookup"><span data-stu-id="3f637-105">\<behaviors></span></span>  
<span data-ttu-id="3f637-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3f637-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="3f637-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="3f637-107">\<behavior></span></span>  
<span data-ttu-id="3f637-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="3f637-108">\<serviceCredentials></span></span>  
<span data-ttu-id="3f637-109">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="3f637-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="3f637-110">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="3f637-110">\<knownCertificates></span></span>  
<span data-ttu-id="3f637-111">\<add></span><span class="sxs-lookup"><span data-stu-id="3f637-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f637-112">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3f637-112">Syntax</span></span>  
  
```xml  
<knownCertificates>   
   <add findValue="String"  
      storeLocation="CurrentUser/LocalMachine"  
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>  
</knownCertificates>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f637-113">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="3f637-113">Attributes and Elements</span></span>  
 <span data-ttu-id="3f637-114">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="3f637-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f637-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="3f637-115">Attributes</span></span>  
  
|<span data-ttu-id="3f637-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="3f637-116">Attribute</span></span>|<span data-ttu-id="3f637-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="3f637-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3f637-118">findValue</span><span class="sxs-lookup"><span data-stu-id="3f637-118">findValue</span></span>|<span data-ttu-id="3f637-119">Cadeia.</span><span class="sxs-lookup"><span data-stu-id="3f637-119">String.</span></span> <span data-ttu-id="3f637-120">O valor a ser procurado.</span><span class="sxs-lookup"><span data-stu-id="3f637-120">The value to search for.</span></span>|  
|<span data-ttu-id="3f637-121">storeLocation</span><span class="sxs-lookup"><span data-stu-id="3f637-121">storeLocation</span></span>|<span data-ttu-id="3f637-122">Enumeração.</span><span class="sxs-lookup"><span data-stu-id="3f637-122">Enumeration.</span></span> <span data-ttu-id="3f637-123">Um dos dois locais de repositório para pesquisar.</span><span class="sxs-lookup"><span data-stu-id="3f637-123">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="3f637-124">storeName</span><span class="sxs-lookup"><span data-stu-id="3f637-124">storeName</span></span>|<span data-ttu-id="3f637-125">Enumeração.</span><span class="sxs-lookup"><span data-stu-id="3f637-125">Enumeration.</span></span> <span data-ttu-id="3f637-126">Um dos repositórios de sistema para pesquisar.</span><span class="sxs-lookup"><span data-stu-id="3f637-126">One of the system stores to search.</span></span>|  
|<span data-ttu-id="3f637-127">X509FindType</span><span class="sxs-lookup"><span data-stu-id="3f637-127">x509FindType</span></span>|<span data-ttu-id="3f637-128">Enumeração.</span><span class="sxs-lookup"><span data-stu-id="3f637-128">Enumeration.</span></span> <span data-ttu-id="3f637-129">Um dos campos de certificado a ser pesquisado.</span><span class="sxs-lookup"><span data-stu-id="3f637-129">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="3f637-130">findValue atributo</span><span class="sxs-lookup"><span data-stu-id="3f637-130">findValue Attribute</span></span>  
  
|<span data-ttu-id="3f637-131">Valor</span><span class="sxs-lookup"><span data-stu-id="3f637-131">Value</span></span>|<span data-ttu-id="3f637-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="3f637-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3f637-133">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="3f637-133">String</span></span>|<span data-ttu-id="3f637-134">O valor depende do campo (especificado pelo atributo X509FindType) que está sendo pesquisado.</span><span class="sxs-lookup"><span data-stu-id="3f637-134">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="3f637-135">Por exemplo, se você está procurando uma impressão digital, o valor deve ser uma cadeia de caracteres de números hexadecimais.</span><span class="sxs-lookup"><span data-stu-id="3f637-135">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="3f637-136">Atributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="3f637-136">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="3f637-137">Valor</span><span class="sxs-lookup"><span data-stu-id="3f637-137">Value</span></span>|<span data-ttu-id="3f637-138">Descrição</span><span class="sxs-lookup"><span data-stu-id="3f637-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3f637-139">Enumeração</span><span class="sxs-lookup"><span data-stu-id="3f637-139">Enumeration</span></span>|<span data-ttu-id="3f637-140">Os valores incluem: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="3f637-140">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="3f637-141">storeLocation atributo</span><span class="sxs-lookup"><span data-stu-id="3f637-141">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="3f637-142">Valor</span><span class="sxs-lookup"><span data-stu-id="3f637-142">Value</span></span>|<span data-ttu-id="3f637-143">Descrição</span><span class="sxs-lookup"><span data-stu-id="3f637-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3f637-144">Enumeração</span><span class="sxs-lookup"><span data-stu-id="3f637-144">Enumeration</span></span>|<span data-ttu-id="3f637-145">CurrentUser ou LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="3f637-145">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="3f637-146">Atributo da storeName</span><span class="sxs-lookup"><span data-stu-id="3f637-146">storeName Attribute</span></span>  
  
|<span data-ttu-id="3f637-147">Valor</span><span class="sxs-lookup"><span data-stu-id="3f637-147">Value</span></span>|<span data-ttu-id="3f637-148">Descrição</span><span class="sxs-lookup"><span data-stu-id="3f637-148">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3f637-149">Enumeração</span><span class="sxs-lookup"><span data-stu-id="3f637-149">Enumeration</span></span>|<span data-ttu-id="3f637-150">Os valores incluem: catálogo de endereços, AuthRoot, CertificateAuthority, não permitidas, My, raiz, TrustedPeople e TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="3f637-150">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3f637-151">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="3f637-151">Child Elements</span></span>  
 <span data-ttu-id="3f637-152">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="3f637-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3f637-153">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="3f637-153">Parent Elements</span></span>  
  
|<span data-ttu-id="3f637-154">Elemento</span><span class="sxs-lookup"><span data-stu-id="3f637-154">Element</span></span>|<span data-ttu-id="3f637-155">Descrição</span><span class="sxs-lookup"><span data-stu-id="3f637-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3f637-156">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="3f637-156">\<knownCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)|<span data-ttu-id="3f637-157">Representa uma coleção de certificados x. 509 que são fornecidos por um Token de segurança Service (STS) para validação dos tokens de segurança.</span><span class="sxs-lookup"><span data-stu-id="3f637-157">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f637-158">Comentários</span><span class="sxs-lookup"><span data-stu-id="3f637-158">Remarks</span></span>  
 <span data-ttu-id="3f637-159">O cenário de token emitido tem três etapas.</span><span class="sxs-lookup"><span data-stu-id="3f637-159">The issued token scenario has three stages.</span></span> <span data-ttu-id="3f637-160">O primeiro estágio, um cliente tentar acessar um serviço é chamado um *do serviço de token seguro*.</span><span class="sxs-lookup"><span data-stu-id="3f637-160">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="3f637-161">O serviço de token seguro, em seguida, autentica o cliente e subsequentemente emite para o cliente um token, normalmente um token de segurança asserções SAML (Markup Language).</span><span class="sxs-lookup"><span data-stu-id="3f637-161">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="3f637-162">O cliente, em seguida, retorne para o serviço com o token.</span><span class="sxs-lookup"><span data-stu-id="3f637-162">The client then returns to the service with the token.</span></span> <span data-ttu-id="3f637-163">O serviço examina o token de dados que permite que o serviço autenticar o token e, portanto, o cliente.</span><span class="sxs-lookup"><span data-stu-id="3f637-163">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="3f637-164">Para autenticar o token, o certificado usa o serviço de token seguro deve ser conhecida para o serviço.</span><span class="sxs-lookup"><span data-stu-id="3f637-164">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="3f637-165">O [ \<issuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) elemento é o repositório de todos esses certificados de serviço de token seguro.</span><span class="sxs-lookup"><span data-stu-id="3f637-165">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="3f637-166">Para adicionar certificados, use o [ \<knownCertificates >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="3f637-166">To add certificates, use the [\<knownCertificates>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="3f637-167">Inserir uma [ \<Adicionar > elemento \<knownCertificates > elemento](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) para cada certificado, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="3f637-167">Insert an [\<add> element \<knownCertificates> Element](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>  
   <knownCertificates>  
      <add findValue="www.contoso.com"   
           storeLocation="LocalMachine" storeName="My"   
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 <span data-ttu-id="3f637-168">Por padrão, os certificados devem ser obtidos de um serviço de token seguro.</span><span class="sxs-lookup"><span data-stu-id="3f637-168">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="3f637-169">Esses "conhecidos" certificados Certifique-se de que apenas legítimas clientes podem acessar um serviço.</span><span class="sxs-lookup"><span data-stu-id="3f637-169">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="3f637-170">Para examinar as condições exigidas para um cliente seja autenticado por um serviço federado, bem como para obter mais informações sobre este elemento de configuração, consulte [como: configurar credenciais em um serviço de Federação](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="3f637-170">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="3f637-171">Para obter mais informações sobre cenários federados, consulte [federação e Tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="3f637-171">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f637-172">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3f637-172">Example</span></span>  
 <span data-ttu-id="3f637-173">O exemplo a seguir adiciona um certificado no repositório de todos os certificados STS.</span><span class="sxs-lookup"><span data-stu-id="3f637-173">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
```xml  
<serviceBehaviors>  
 <behavior name="myServiceBehavior">  
  <serviceCredentials>  
   <issuedTokenAuthentication>  
    <knownCertificates>  
     <add findValue="www.contoso.com" storeLocation="LocalMachine"   
           storeName="CertificateAuthority"  
           x509FindType="FindByIssuerName" />  
     </knownCertificates>  
    </issuedTokenAuthentication>  
   </serviceCredentials>  
  </behavior>  
 </serviceBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3f637-174">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3f637-174">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>  
 [<span data-ttu-id="3f637-175">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="3f637-175">\<knownCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)  
 [<span data-ttu-id="3f637-176">Trabalhar com certificados</span><span class="sxs-lookup"><span data-stu-id="3f637-176">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="3f637-177">Federação e Tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="3f637-177">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="3f637-178">Como: configurar as credenciais em um serviço de Federação</span><span class="sxs-lookup"><span data-stu-id="3f637-178">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="3f637-179">Protegendo serviços e clientes</span><span class="sxs-lookup"><span data-stu-id="3f637-179">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)