---
title: Integre as permissões do ServiceNow no centro de segurança e centro de conformidade do Microsoft 365
description: Saiba como criar e acompanhar tíquetes no ServiceNow no centro de segurança e centro de conformidade do Microsoft 365.
keywords: segurança, Microsoft 365, M365, conformidade, centro de conformidade, central de segurança, ServiceNow, tíquetes, tarefas, NEVEr, conexão
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: d258bf3ec4c04eafd22e850329ca925b4c974e94
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086662"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a><span data-ttu-id="9408b-104">Integre as permissões do ServiceNow no centro de segurança e centro de conformidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9408b-104">Integrate ServiceNow tickets into the Microsoft 365 security center and compliance center</span></span>

[!include[Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="9408b-105">O ServiceNow é uma plataforma de computação em nuvem popular que ajuda as empresas a gerenciar fluxos de trabalho digitais para operações corporativas.</span><span class="sxs-lookup"><span data-stu-id="9408b-105">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="9408b-106">A plataforma atual tem fluxos de trabalho de ti, fluxos de trabalho de funcionários e fluxos de trabalho de cliente.</span><span class="sxs-lookup"><span data-stu-id="9408b-106">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> [<span data-ttu-id="9408b-107">Saiba mais sobre o ServiceNow</span><span class="sxs-lookup"><span data-stu-id="9408b-107">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="9408b-108">A Microsoft fez uma parceria com o ServiceNow para tornar mais fácil para os administradores de ti gerenciar suas permissões e tarefas em ambas as plataformas.</span><span class="sxs-lookup"><span data-stu-id="9408b-108">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> <span data-ttu-id="9408b-109">O centro de [segurança do microsoft 365](overview-security-center.md) e o [centro de conformidade da Microsoft 365](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center) estão sendo aprimorados com a capacidade de criar e controlar de forma nativa as permissões no ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="9408b-109">[Microsoft 365 security center](overview-security-center.md) and the [Microsoft 365 compliance center](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center) are being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span>

- [<span data-ttu-id="9408b-110">**Gerenciar tíquetes do ServiceNow na central de segurança**</span><span class="sxs-lookup"><span data-stu-id="9408b-110">**Manage ServiceNow tickets in the security center**</span></span>](tickets-security-center.md)
- <span data-ttu-id="9408b-111">**Gerenciar tíquetes do ServiceNow no centro de conformidade** (em breve)</span><span class="sxs-lookup"><span data-stu-id="9408b-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9408b-112">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="9408b-112">Prerequisites</span></span>

<span data-ttu-id="9408b-113">Ter acesso ao centro de segurança ou ao centro de conformidade do Microsoft 365 e a uma instância do ServiceNow com:</span><span class="sxs-lookup"><span data-stu-id="9408b-113">Have access to the Microsoft 365 security center or compliance center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="9408b-114">Kingston ou versão superior</span><span class="sxs-lookup"><span data-stu-id="9408b-114">Kingston or higher version</span></span>
* <span data-ttu-id="9408b-115">Ter credenciais do administrador HI</span><span class="sxs-lookup"><span data-stu-id="9408b-115">Have admin HI credentials</span></span>
* <span data-ttu-id="9408b-116">Ter privilégios de administrador na instância de fornecedor de destino</span><span class="sxs-lookup"><span data-stu-id="9408b-116">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="9408b-117">O ServiceNow recomenda que os usuários mantenham as configurações padrão em sua instância do ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="9408b-117">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="9408b-118">Ter personalizações pode causar erros ao concluir a lista de verificação de instalação e integração com a central de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9408b-118">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="9408b-119">Troca de dados</span><span class="sxs-lookup"><span data-stu-id="9408b-119">Data exchange</span></span>

<span data-ttu-id="9408b-120">Quando você conecta o centro de segurança ou o centro de conformidade do Microsoft 365 ao ServiceNow, a Microsoft recebe os seguintes dados adicionais:</span><span class="sxs-lookup"><span data-stu-id="9408b-120">When you connect the Microsoft 365 security center or compliance center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="9408b-121">Nome da instância do ServiceNow</span><span class="sxs-lookup"><span data-stu-id="9408b-121">ServiceNow instance name</span></span>
* <span data-ttu-id="9408b-122">ID do cliente do ServiceNow</span><span class="sxs-lookup"><span data-stu-id="9408b-122">ServiceNow client ID</span></span>
* <span data-ttu-id="9408b-123">Segredo do cliente do ServiceNow</span><span class="sxs-lookup"><span data-stu-id="9408b-123">ServiceNow client secret</span></span>
* <span data-ttu-id="9408b-124">Tokens de atualização & Access</span><span class="sxs-lookup"><span data-stu-id="9408b-124">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="9408b-125">Quando você cria uma permissão do ServiceNow no centro de segurança ou centro de conformidade do Microsoft 365, os dados a seguir são enviados para o ServiceNow:</span><span class="sxs-lookup"><span data-stu-id="9408b-125">When you create a ServiceNow ticket from the Microsoft 365 security center or compliance center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="9408b-126">ID de usuário que inicia a criação de tíquete</span><span class="sxs-lookup"><span data-stu-id="9408b-126">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="9408b-127">Nome da tarefa</span><span class="sxs-lookup"><span data-stu-id="9408b-127">Task name</span></span>
* <span data-ttu-id="9408b-128">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="9408b-128">Task description</span></span>
* <span data-ttu-id="9408b-129">Priority</span><span class="sxs-lookup"><span data-stu-id="9408b-129">Priority</span></span>
* <span data-ttu-id="9408b-130">Data de conclusão</span><span class="sxs-lookup"><span data-stu-id="9408b-130">Due date</span></span>
* <span data-ttu-id="9408b-131">Fonte de recomendação (recomendação do usuário ou recomendação da Microsoft)</span><span class="sxs-lookup"><span data-stu-id="9408b-131">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="9408b-132">Categoria de recomendação (dispositivos, dados, aplicativos, identidade, infraestrutura)</span><span class="sxs-lookup"><span data-stu-id="9408b-132">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-to-servicenow"></a><span data-ttu-id="9408b-133">Conectar-se ao ServiceNow</span><span class="sxs-lookup"><span data-stu-id="9408b-133">Connect to ServiceNow</span></span>

<span data-ttu-id="9408b-134">Vá para [criar e acompanhar tíquetes do ServiceNow no centro de segurança do Microsoft 365](tickets-security-center.md) para saber como se conectar ao ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="9408b-134">Go to [Create and track ServiceNow tickets in the Microsoft 365 security center](tickets-security-center.md) to learn how to connect to ServiceNow.</span></span> <span data-ttu-id="9408b-135">A conexão com o centro de conformidade da Microsoft 365 estará disponível em breve.</span><span class="sxs-lookup"><span data-stu-id="9408b-135">Connecting from the Microsoft 365 compliance center is coming soon.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="9408b-136">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="9408b-136">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="9408b-137">Você recebe um erro na primeira etapa da lista de verificação de instalação (criação de OAuth)</span><span class="sxs-lookup"><span data-stu-id="9408b-137">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="9408b-138">**Mensagem de erro**: a operação de leitura em relação a ' oauth_entity ' do escopo ' x_mioms_m365ticket ' foi recusada devido à política de acesso entre escopos da tabela</span><span class="sxs-lookup"><span data-stu-id="9408b-138">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="9408b-139">O aplicativo presume que qualquer administrador na instância do ServiceNow possa criar e ler entidades OAuth.</span><span class="sxs-lookup"><span data-stu-id="9408b-139">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="9408b-140">Esse erro pode ser causado devido a uma personalização na instância do ServiceNow, que restringe quem pode criar/ler entidades OAuth.</span><span class="sxs-lookup"><span data-stu-id="9408b-140">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="9408b-141">**O ServiceNow recomenda que os usuários mantenham a funcionalidade padrão.**</span><span class="sxs-lookup"><span data-stu-id="9408b-141">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="9408b-142">Defina as configurações de tabela "registros de aplicativos" como padrão:</span><span class="sxs-lookup"><span data-stu-id="9408b-142">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="9408b-143">Rótulo = registradores de aplicativos</span><span class="sxs-lookup"><span data-stu-id="9408b-143">Label = Application Registeries</span></span>
* <span data-ttu-id="9408b-144">Nome = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="9408b-144">Name = oauth_entity</span></span>
* <span data-ttu-id="9408b-145">Acessível a partir de = todos os escopos do aplicativo</span><span class="sxs-lookup"><span data-stu-id="9408b-145">Accessible from = All application scopes</span></span>
* <span data-ttu-id="9408b-146">Caixa de seleção pode ler = marcada</span><span class="sxs-lookup"><span data-stu-id="9408b-146">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="9408b-147">Como validar a entidade OAuth criada para o conector de conformidade de & de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9408b-147">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="9408b-148">Vá para a tabela registros de aplicativos (**Menu > registro de aplicativo > OAuth de sistema**) no ServiceNow e localize a entidade OAuth criada por você, com o nome que você atribuiu a ela.</span><span class="sxs-lookup"><span data-stu-id="9408b-148">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow and find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="logging-in-as-the-integration-user"></a><span data-ttu-id="9408b-149">Como fazer logon como o usuário de integração</span><span class="sxs-lookup"><span data-stu-id="9408b-149">Logging in as the integration user</span></span>

<span data-ttu-id="9408b-150">Antes de autorizar a conexão entre o centro de segurança do Microsoft 365 e o ServiceNow, certifique-se de usar o logon e a senha de usuário de integração que você criou nas etapas de instalação.</span><span class="sxs-lookup"><span data-stu-id="9408b-150">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="9408b-151">Não use suas credenciais pessoais.</span><span class="sxs-lookup"><span data-stu-id="9408b-151">Do not use your personal credentials.</span></span>

1. <span data-ttu-id="9408b-152">Vá para a página autorização no ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="9408b-152">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="9408b-153">Se você estiver conectado com suas credenciais pessoais, selecione o **não é possível** vincular no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="9408b-153">If you are signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="9408b-154">Faça logon no ServiceNow como o usuário de integração que você criou anteriormente na lista de verificação de instalação.</span><span class="sxs-lookup"><span data-stu-id="9408b-154">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="9408b-155">Selecione **permitir** na página do servicenow que pergunta se o conector de segurança + conformidade pode se conectar à sua conta do servicenow.</span><span class="sxs-lookup"><span data-stu-id="9408b-155">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="9408b-156">Prossiga com as etapas de configuração.</span><span class="sxs-lookup"><span data-stu-id="9408b-156">Proceed with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="9408b-157">Como validar o usuário de integração criado com a lista de verificação de instalação do conector de conformidade do & de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9408b-157">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="9408b-158">Vá para a tabela usuários **(Menu > administração de usuário > usuários**) no ServiceNow e localize o usuário de integração criado por você, com o nome atribuído a ele.</span><span class="sxs-lookup"><span data-stu-id="9408b-158">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="9408b-159">Sua empresa tem o logon único habilitado, o que impede que você se conecte ao ServiceNow através da central de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9408b-159">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="9408b-160">Se sua empresa ativou o logon único e você recebe um erro ou o logon não é bem-sucedido, siga uma das duas soluções.</span><span class="sxs-lookup"><span data-stu-id="9408b-160">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="log-into-servicenow-as-the-integration-user"></a><span data-ttu-id="9408b-161">Faça logon no ServiceNow como o usuário de integração</span><span class="sxs-lookup"><span data-stu-id="9408b-161">Log into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="9408b-162">Volte para a página autorização no ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="9408b-162">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="9408b-163">Selecione o **não é possível** vincular no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="9408b-163">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="9408b-164">Faça logon no ServiceNow como o usuário de integração que você criou anteriormente na lista de verificação de instalação.</span><span class="sxs-lookup"><span data-stu-id="9408b-164">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="9408b-165">Selecione **permitir** na página do servicenow que pergunta se o conector de segurança + conformidade pode se conectar à sua conta do servicenow.</span><span class="sxs-lookup"><span data-stu-id="9408b-165">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="9408b-166">Prossiga com as etapas de configuração.</span><span class="sxs-lookup"><span data-stu-id="9408b-166">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="9408b-167">Criar um usuário de administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="9408b-167">Create a security admin user</span></span>

1. <span data-ttu-id="9408b-168">Criar um usuário com privilégios de administrador de segurança no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9408b-168">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="9408b-169">O usuário precisa ter o mesmo nome e endereço de email do usuário de integração que você criou na lista de verificação de instalação.</span><span class="sxs-lookup"><span data-stu-id="9408b-169">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="9408b-170">Você pode remover a função de administrador de segurança após o logon e a conexão ter sido concluída.</span><span class="sxs-lookup"><span data-stu-id="9408b-170">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="9408b-171">Faça logon no centro de segurança do Microsoft 365 como este usuário e siga as etapas de configuração.</span><span class="sxs-lookup"><span data-stu-id="9408b-171">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="9408b-172">Filtragem de IP</span><span class="sxs-lookup"><span data-stu-id="9408b-172">IP filtering</span></span>

<span data-ttu-id="9408b-173">Se você habilitou a filtragem de IP, talvez seja necessário permitir explicitamente endereços IP.</span><span class="sxs-lookup"><span data-stu-id="9408b-173">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="9408b-174">Consulte [controle de acesso de endereço IP](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) para obter informações sobre como permitir intervalos IP no ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="9408b-174">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="9408b-175">Consulte [Azure IP Ranges and Service Tags-Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) para obter uma lista de endereços IP para permitir.</span><span class="sxs-lookup"><span data-stu-id="9408b-175">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="9408b-176">A instalação está concluída, mas não vê tíquetes e não pode ser compartilhada</span><span class="sxs-lookup"><span data-stu-id="9408b-176">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="9408b-177">Se as etapas de instalação e configuração tiverem sido concluídas, mas você não vir os cartões do ServiceNow na Home Page e não puder compartilhar o ServiceNow pela pontuação segura da Microsoft, verifique o status da página de provisionamento em https://security.microsoft.com/ticketProvisioning .</span><span class="sxs-lookup"><span data-stu-id="9408b-177">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="9408b-178">Selecione **autorizar** e retornar para a página inicial.</span><span class="sxs-lookup"><span data-stu-id="9408b-178">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="9408b-179">Os cartões devem ser exibidos.</span><span class="sxs-lookup"><span data-stu-id="9408b-179">The cards should appear.</span></span>

## <a name="resources"></a><span data-ttu-id="9408b-180">Recursos</span><span class="sxs-lookup"><span data-stu-id="9408b-180">Resources</span></span>

- [<span data-ttu-id="9408b-181">Gerenciar tíquetes do ServiceNow na central de segurança</span><span class="sxs-lookup"><span data-stu-id="9408b-181">Manage ServiceNow tickets in the security center</span></span>](tickets-security-center.md)