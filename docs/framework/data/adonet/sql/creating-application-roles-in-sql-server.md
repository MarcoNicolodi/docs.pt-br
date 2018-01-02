---
title: "Criando funções de aplicativo no SQL Server"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27442435-dfb2-4062-8c59-e2960833a638
caps.latest.revision: "9"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 632b25408db8556dd9604f653f975bccbea75e2b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="creating-application-roles-in-sql-server"></a><span data-ttu-id="ab174-102">Criando funções de aplicativo no SQL Server</span><span class="sxs-lookup"><span data-stu-id="ab174-102">Creating Application Roles in SQL Server</span></span>
<span data-ttu-id="ab174-103">As funções de aplicativo fornecem uma maneira de atribuir permissões para um aplicativo em vez de uma função ou usuário do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ab174-103">Application roles provide a way to assign permissions to an application instead of a database role or user.</span></span> <span data-ttu-id="ab174-104">Os usuários podem se conectar ao banco de dados, ativar a função de aplicativo e presumir as permissões concedidas ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ab174-104">Users can connect to the database, activate the application role, and assume the permissions granted to the application.</span></span> <span data-ttu-id="ab174-105">As permissões concedidas para a função de aplicativo são impostas para a duração da conexão.</span><span class="sxs-lookup"><span data-stu-id="ab174-105">The permissions granted to the application role are in force for the duration of the connection.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ab174-106">As funções de aplicativo são ativadas quando um aplicativo cliente fornece um nome da função de aplicativo e uma senha na cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="ab174-106">Application roles are activated when a client application supplies an application role name and a password in the connection string.</span></span> <span data-ttu-id="ab174-107">Eles apresentam uma vulnerabilidade de segurança em um aplicativo de duas camadas porque a senha deve ser armazenada no computador cliente.</span><span class="sxs-lookup"><span data-stu-id="ab174-107">They present a security vulnerability in a two-tier application because the password must be stored on the client computer.</span></span> <span data-ttu-id="ab174-108">Em um aplicativo de três camadas, você pode armazenar a senha para que não possa ser acessada por usuários do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ab174-108">In a three-tier application, you can store the password so that it cannot be accessed by users of the application.</span></span>  
  
## <a name="application-role-features"></a><span data-ttu-id="ab174-109">Recursos da função de aplicativo</span><span class="sxs-lookup"><span data-stu-id="ab174-109">Application Role Features</span></span>  
 <span data-ttu-id="ab174-110">As funções de aplicativo têm os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="ab174-110">Application roles have the following features:</span></span>  
  
-   <span data-ttu-id="ab174-111">Ao contrário das funções de banco de dados, as funções de aplicativo não contêm nenhum membro.</span><span class="sxs-lookup"><span data-stu-id="ab174-111">Unlike database roles, application roles contain no members.</span></span>  
  
-   <span data-ttu-id="ab174-112">As funções de aplicativo são ativadas quando um aplicativo fornece o nome da função de aplicativo e uma senha para o procedimento armazenado do sistema `sp_setapprole`.</span><span class="sxs-lookup"><span data-stu-id="ab174-112">Application roles are activated when an application supplies the application role name and a password to the `sp_setapprole` system stored procedure.</span></span>  
  
-   <span data-ttu-id="ab174-113">A senha deve ser armazenado no computador cliente e ser fornecida em tempo de execução; uma função de aplicativo não pode ser ativada de dentro do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ab174-113">The password must be stored on the client computer and supplied at run time; an application role cannot be activated from inside of SQL Server.</span></span>  
  
-   <span data-ttu-id="ab174-114">A senha não é criptografada.</span><span class="sxs-lookup"><span data-stu-id="ab174-114">The password is not encrypted.</span></span> <span data-ttu-id="ab174-115">A senha do parâmetro é armazenada como um hash unidirecional.</span><span class="sxs-lookup"><span data-stu-id="ab174-115">The parameter password is stored as a one-way hash.</span></span>  
  
-   <span data-ttu-id="ab174-116">Quando forem ativadas, as permissões adquiridas por meio da função de aplicativo permanecem aplicadas para a duração da conexão.</span><span class="sxs-lookup"><span data-stu-id="ab174-116">Once activated, permissions acquired through the application role remain in effect for the duration of the connection.</span></span>  
  
-   <span data-ttu-id="ab174-117">A função de aplicativo herda as permissões concedidas para a função `public`.</span><span class="sxs-lookup"><span data-stu-id="ab174-117">The application role inherits permissions granted to the `public` role.</span></span>  
  
-   <span data-ttu-id="ab174-118">Se um membro da função de servidor fixa do `sysadmin` ativar uma função de aplicativo, o contexto de segurança mudará para a função de aplicativo para a duração da conexão.</span><span class="sxs-lookup"><span data-stu-id="ab174-118">If a member of the `sysadmin` fixed server role activates an application role, the security context switches to that of the application role for the duration of the connection.</span></span>  
  
-   <span data-ttu-id="ab174-119">Se você criar uma conta de `guest` em um banco de dados que tenha uma função de aplicativo, não precisará criar um usuário de banco de dados para a função de aplicativo ou para nenhum dos logons que a chamam.</span><span class="sxs-lookup"><span data-stu-id="ab174-119">If you create a `guest` account in a database that has an application role, you do not need to create a database user account for the application role or for any of the logins that invoke it.</span></span> <span data-ttu-id="ab174-120">As funções de aplicativo poderão acessar diretamente outro banco de dados somente se uma conta de `guest` existir no segundo banco de dados</span><span class="sxs-lookup"><span data-stu-id="ab174-120">Application roles can directly access another database only if a `guest` account exists in the second database</span></span>  
  
-   <span data-ttu-id="ab174-121">As funções internas que retornam os nomes de logon, como SYSTEM_USER, retornam o nome do logon que chamou a função de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ab174-121">Built-in functions that return login names, such as SYSTEM_USER, return the name of the login that invoked the application role.</span></span> <span data-ttu-id="ab174-122">As funções internas que retornam os nomes de usuário de banco de dados retornam o nome da função de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ab174-122">Built-in functions that return database user names return the name of the application role.</span></span>  
  
### <a name="the-principle-of-least-privilege"></a><span data-ttu-id="ab174-123">O princípio de privilégios mínimos</span><span class="sxs-lookup"><span data-stu-id="ab174-123">The Principle of Least Privilege</span></span>  
 <span data-ttu-id="ab174-124">As funções de aplicativo devem receber somente as permissões necessárias no caso de a senha ser comprometida.</span><span class="sxs-lookup"><span data-stu-id="ab174-124">Application roles should be granted only required permissions in case the password is compromised.</span></span> <span data-ttu-id="ab174-125">As permissões para a função `public` devem ser revogadas em qualquer banco de dados usando uma função de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ab174-125">Permissions to the `public` role should be revoked in any database using an application role.</span></span> <span data-ttu-id="ab174-126">Desative a conta de `guest` em qualquer banco de dados ao qual você não queira que chamadores da função de aplicativo tenham acesso.</span><span class="sxs-lookup"><span data-stu-id="ab174-126">Disable the `guest` account in any database you do not want callers of the application role to have access to.</span></span>  
  
### <a name="application-role-enhancements"></a><span data-ttu-id="ab174-127">Aprimoramentos da função de aplicativo</span><span class="sxs-lookup"><span data-stu-id="ab174-127">Application Role Enhancements</span></span>  
 <span data-ttu-id="ab174-128">O contexto de execução pode ser alternado de volta para o chamador original após ter ativado uma função do aplicativo, eliminando a necessidade de desativar o pool de conexões.</span><span class="sxs-lookup"><span data-stu-id="ab174-128">The execution context can be switched back to the original caller after activating an application role, removing the need to disable connection pooling.</span></span> <span data-ttu-id="ab174-129">O procedimento `sp_setapprole` tem uma nova opção que cria um cookie, que contém informações de contexto sobre o chamador.</span><span class="sxs-lookup"><span data-stu-id="ab174-129">The `sp_setapprole` procedure has a new option that creates a cookie, which contains context information about the caller.</span></span> <span data-ttu-id="ab174-130">Você pode reverter a sessão chamando o procedimento `sp_unsetapprole`, passando o cookie.</span><span class="sxs-lookup"><span data-stu-id="ab174-130">You can revert the session by calling the `sp_unsetapprole` procedure, passing it the cookie.</span></span>  
  
## <a name="application-role-alternatives"></a><span data-ttu-id="ab174-131">Alternativas a funções de aplicativo</span><span class="sxs-lookup"><span data-stu-id="ab174-131">Application Role Alternatives</span></span>  
 <span data-ttu-id="ab174-132">As funções de aplicativo dependem da segurança de uma senha, que apresenta uma vulnerabilidade de segurança em potencial.</span><span class="sxs-lookup"><span data-stu-id="ab174-132">Application roles depend on the security of a password, which presents a potential security vulnerability.</span></span> <span data-ttu-id="ab174-133">As senhas podem ser expostas sendo inseridas no código do aplicativo ou salvas no disco.</span><span class="sxs-lookup"><span data-stu-id="ab174-133">Passwords may be exposed by being embedded in application code or saved on disk.</span></span>  
  
 <span data-ttu-id="ab174-134">Você pode querer considerar as seguintes alternativas.</span><span class="sxs-lookup"><span data-stu-id="ab174-134">You may want to consider the following alternatives.</span></span>  
  
-   <span data-ttu-id="ab174-135">Use a troca de contexto com a instrução EXECUTE AS com suas cláusulas NO REVERT e WITH COOKIE.</span><span class="sxs-lookup"><span data-stu-id="ab174-135">Use context switching with the EXECUTE AS statement with its NO REVERT and WITH COOKIE clauses.</span></span> <span data-ttu-id="ab174-136">Você pode criar uma conta de usuário em um banco de dados que não seja mapeado para um logon.</span><span class="sxs-lookup"><span data-stu-id="ab174-136">You can create a user account in a database that is not mapped to a login.</span></span> <span data-ttu-id="ab174-137">Em seguida, você atribui permissões para essa conta.</span><span class="sxs-lookup"><span data-stu-id="ab174-137">You then assign permissions to this account.</span></span> <span data-ttu-id="ab174-138">Usar EXECUTE AS a um usuário sem logon é mais seguro porque é baseado em permissão, não baseado em senha.</span><span class="sxs-lookup"><span data-stu-id="ab174-138">Using EXECUTE AS with a login-less user is more secure because it is permission-based, not password-based.</span></span> <span data-ttu-id="ab174-139">Para obter mais informações, consulte [personalizando permissões com representação no SQL Server](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ab174-139">For more information, see [Customizing Permissions with Impersonation in SQL Server](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md).</span></span>  
  
-   <span data-ttu-id="ab174-140">Assine procedimentos armazenados com certificados, concedendo permissão somente para executar os procedimentos.</span><span class="sxs-lookup"><span data-stu-id="ab174-140">Sign stored procedures with certificates, granting only permission to execute the procedures.</span></span> <span data-ttu-id="ab174-141">Para obter mais informações, consulte [assinatura de procedimentos armazenados no SQL Server](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ab174-141">For more information, see [Signing Stored Procedures in SQL Server](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md).</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="ab174-142">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="ab174-142">External Resources</span></span>  
 <span data-ttu-id="ab174-143">Para obter mais informações, consulte os seguintes recursos.</span><span class="sxs-lookup"><span data-stu-id="ab174-143">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="ab174-144">Recurso</span><span class="sxs-lookup"><span data-stu-id="ab174-144">Resource</span></span>|<span data-ttu-id="ab174-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="ab174-145">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="ab174-146">[Funções de aplicativo](http://msdn.microsoft.com/library/ms190998.aspx) nos Manuais Online do SQL Server</span><span class="sxs-lookup"><span data-stu-id="ab174-146">[Application Roles](http://msdn.microsoft.com/library/ms190998.aspx) in SQL Server Books Online</span></span>|<span data-ttu-id="ab174-147">Descreve como criar e usar funções de aplicativo no SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="ab174-147">Describes how to create and use application roles in SQL Server 2008.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ab174-148">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ab174-148">See Also</span></span>  
 <span data-ttu-id="ab174-149">[Securing ADO.NET Applications](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md) (Protegendo aplicativos ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="ab174-149">[Securing ADO.NET Applications](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)</span></span>  
 [<span data-ttu-id="ab174-150">Visão geral de segurança do SQL Server</span><span class="sxs-lookup"><span data-stu-id="ab174-150">Overview of SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [<span data-ttu-id="ab174-151">Cenários de segurança do aplicativo no SQL Server</span><span class="sxs-lookup"><span data-stu-id="ab174-151">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 <span data-ttu-id="ab174-152">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917) (Central de desenvolvedores do DataSet e de provedores gerenciados do ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="ab174-152">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)</span></span>