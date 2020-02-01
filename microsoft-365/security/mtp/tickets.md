---
title: Criar e acompanhar tíquetes por meio do ServiceNow
description: A central de segurança do Microsoft 365 está sendo aprimorada com a capacidade de criar e controlar de forma nativa as permissões no ServiceNow. Os administradores de segurança podem enviar uma recomendação de Pontuação segura diretamente para o ServiceNow e criar uma permissão.
keywords: segurança, Microsoft 365, M365, Pontuação segura, central de segurança, ServiceNow, tíquetes, tarefas
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
ms.openlocfilehash: 26e227b4b1e8047ca962ca9e65b139bacae55e03
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599988"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="5836c-105">Gerenciar tíquetes pelo ServiceNow</span><span class="sxs-lookup"><span data-stu-id="5836c-105">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="5836c-106">A central de segurança do Microsoft 365 está sendo aprimorada com a capacidade de criar e controlar de forma nativa as permissões no ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="5836c-106">Microsoft 365 security center is being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="5836c-107">Administradores de segurança podem enviar uma ação de melhoria de [Pontuação segura da Microsoft](microsoft-secure-score.md) diretamente para o ServiceNow e criar uma permissão.</span><span class="sxs-lookup"><span data-stu-id="5836c-107">Security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="5836c-108">As permissões de gerenciamento de incidentes e de alterações podem ser criadas.</span><span class="sxs-lookup"><span data-stu-id="5836c-108">Both incident management and change management tickets can be created.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5836c-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="5836c-109">Prerequisites</span></span>

<span data-ttu-id="5836c-110">Ter acesso à central de segurança do Microsoft 365 e uma instância do ServiceNow com:</span><span class="sxs-lookup"><span data-stu-id="5836c-110">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="5836c-111">Kingston ou versão superior</span><span class="sxs-lookup"><span data-stu-id="5836c-111">Kingston or higher version</span></span>
* <span data-ttu-id="5836c-112">Ter credenciais do administrador HI</span><span class="sxs-lookup"><span data-stu-id="5836c-112">Have admin HI credentials</span></span>
* <span data-ttu-id="5836c-113">Ter privilégios de administrador na instância de fornecedor de destino</span><span class="sxs-lookup"><span data-stu-id="5836c-113">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="5836c-114">O ServiceNow recomenda que os usuários mantenham as configurações padrão em sua instância do ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="5836c-114">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="5836c-115">Ter personalizações pode causar erros ao concluir a lista de verificação de instalação e integração com a central de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5836c-115">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="5836c-116">Troca de dados</span><span class="sxs-lookup"><span data-stu-id="5836c-116">Data exchange</span></span>

<span data-ttu-id="5836c-117">Quando você conecta o centro de segurança do Microsoft 365 ao ServiceNow, a Microsoft recebe os seguintes dados adicionais:</span><span class="sxs-lookup"><span data-stu-id="5836c-117">When you connect the Microsoft 365 security center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="5836c-118">Nome da instância do ServiceNow</span><span class="sxs-lookup"><span data-stu-id="5836c-118">ServiceNow instance name</span></span>
* <span data-ttu-id="5836c-119">ID do cliente do ServiceNow</span><span class="sxs-lookup"><span data-stu-id="5836c-119">ServiceNow client ID</span></span>
* <span data-ttu-id="5836c-120">Segredo do cliente do ServiceNow</span><span class="sxs-lookup"><span data-stu-id="5836c-120">ServiceNow client secret</span></span>
* <span data-ttu-id="5836c-121">Tokens de atualização & Access</span><span class="sxs-lookup"><span data-stu-id="5836c-121">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="5836c-122">Quando você cria uma permissão do ServiceNow no centro de segurança do Microsoft 365, os dados a seguir são enviados para o ServiceNow:</span><span class="sxs-lookup"><span data-stu-id="5836c-122">When you create a ServiceNow ticket from the Microsoft 365 security center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="5836c-123">ID de usuário que inicia a criação de tíquete</span><span class="sxs-lookup"><span data-stu-id="5836c-123">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="5836c-124">Nome da tarefa</span><span class="sxs-lookup"><span data-stu-id="5836c-124">Task name</span></span>
* <span data-ttu-id="5836c-125">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="5836c-125">Task description</span></span>
* <span data-ttu-id="5836c-126">Prioridade</span><span class="sxs-lookup"><span data-stu-id="5836c-126">Priority</span></span>
* <span data-ttu-id="5836c-127">Data de conclusão</span><span class="sxs-lookup"><span data-stu-id="5836c-127">Due date</span></span>
* <span data-ttu-id="5836c-128">Fonte de recomendação (recomendação do usuário ou recomendação da Microsoft)</span><span class="sxs-lookup"><span data-stu-id="5836c-128">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="5836c-129">Categoria de recomendação (dispositivos, dados, aplicativos, identidade, infraestrutura)</span><span class="sxs-lookup"><span data-stu-id="5836c-129">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="5836c-130">Conectar a central de segurança do Microsoft 365 ao ServiceNow</span><span class="sxs-lookup"><span data-stu-id="5836c-130">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="5836c-131">Navegue até a home page do centro de segurança do Microsoft 365 para ver o cartão de conexão do ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="5836c-131">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![Você usa o ServiceNow](../images/do-you-use-servicenow-250.png)

<span data-ttu-id="5836c-133">Selecione "conectar ao ServiceNow" para ir para a página de configuração do ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="5836c-133">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="5836c-134">Siga as instruções para autorizar o aplicativo conector 365 da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5836c-134">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="5836c-135">Antes de autorizar a conexão entre o centro de segurança do Microsoft 365 e o ServiceNow, certifique-se de usar o logon e a senha de usuário de integração que você criou nas etapas de instalação.</span><span class="sxs-lookup"><span data-stu-id="5836c-135">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="5836c-136">Não use suas credenciais pessoais.</span><span class="sxs-lookup"><span data-stu-id="5836c-136">Do not use your personal credentials.</span></span>

<span data-ttu-id="5836c-137">Após ter seguido as orientações e autorizar a conexão, veja o status da conexão na página conexão da central de segurança do Microsoft 365 e na experiência do aplicativo do Microsoft 365 Ticketing Connector.</span><span class="sxs-lookup"><span data-stu-id="5836c-137">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="5836c-138">Agora, você está pronto para começar a criar tarefas!</span><span class="sxs-lookup"><span data-stu-id="5836c-138">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="5836c-139">Criar uma tarefa e compartilhá-la para o ServiceNow</span><span class="sxs-lookup"><span data-stu-id="5836c-139">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="5836c-140">Depois que a integração é configurada, crie tarefas do ServiceNow com base em ações específicas de melhoria da Pontuação segura da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5836c-140">Once the integration is set up, create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="5836c-141">Vá para qualquer ação de melhoria na pontuação segura no portal da central de segurança do Microsoft 365 e selecione o ícone "compartilhar".</span><span class="sxs-lookup"><span data-stu-id="5836c-141">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the “share” icon.</span></span> <span data-ttu-id="5836c-142">Uma das opções de DropDown é o ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="5836c-142">One of the dropdown options is ServiceNow.</span></span>

![Compartilhamento do ServiceNow em Pontuação segura](../images/servicenow-share.png)

<span data-ttu-id="5836c-144">Uma tarefa é gerada onde você pode definir a prioridade e editar o nome, a descrição ou a data de conclusão.</span><span class="sxs-lookup"><span data-stu-id="5836c-144">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="5836c-145">Após todos os campos obrigatórios serem preenchidos, envie a tarefa para o ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="5836c-145">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="5836c-146">A tarefa está visível no ServiceNow como uma solicitação de alteração de configuração e segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5836c-146">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="5836c-147">Controlar ingressos</span><span class="sxs-lookup"><span data-stu-id="5836c-147">Track tickets</span></span>

<span data-ttu-id="5836c-148">Depois que o gerenciamento de alterações e as permissões de gerenciamento de incidentes tiverem sido criados, eles serão exibidos em cartões na home page do centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5836c-148">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="5836c-149">A partir desses cartões, você pode criar um tíquete, exibir todos os tíquetes ou gerenciar a configuração do ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="5836c-149">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![Tíquetes de gerenciamento de alterações do ServiceNow](../images/change-management-375.png)  ![Tíquetes de gerenciamento de incidentes do ServiceNow](../images/incident-management-375.png)

<span data-ttu-id="5836c-152">Para reprovisionar ou gerenciar sua integração do ServiceNow no centro de segurança do Microsoft 365, selecione **gerenciar a configuração do servicenow** em qualquer um dos cartões.</span><span class="sxs-lookup"><span data-stu-id="5836c-152">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="5836c-153">A partir daí, remova a conexão atual do ServiceNow e personalize os nomes de estado de tíquete.</span><span class="sxs-lookup"><span data-stu-id="5836c-153">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="5836c-154">Com as permissões do ServiceNow visíveis no centro de segurança do Microsoft 365, suas tarefas residem em um local onde elas podem ser rastreadas e aplicadas junto com seus outros itens do painel de segurança.</span><span class="sxs-lookup"><span data-stu-id="5836c-154">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="5836c-155">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="5836c-155">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="5836c-156">Você recebe um erro na primeira etapa da lista de verificação de instalação (criação de OAuth)</span><span class="sxs-lookup"><span data-stu-id="5836c-156">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="5836c-157">**Mensagem de erro**: a operação de leitura em relação a ' oauth_entity ' do escopo ' x_mioms_m365ticket ' foi recusada devido à política de acesso entre escopos da tabela</span><span class="sxs-lookup"><span data-stu-id="5836c-157">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="5836c-158">O aplicativo presume que qualquer administrador na instância do ServiceNow possa criar e ler entidades OAuth.</span><span class="sxs-lookup"><span data-stu-id="5836c-158">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="5836c-159">Esse erro pode ser causado devido a uma personalização na instância do ServiceNow, que restringe quem pode criar/ler entidades OAuth.</span><span class="sxs-lookup"><span data-stu-id="5836c-159">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="5836c-160">**O ServiceNow recomenda que os usuários mantenham a funcionalidade padrão.**</span><span class="sxs-lookup"><span data-stu-id="5836c-160">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="5836c-161">Defina as configurações de tabela "registros de aplicativos" como padrão:</span><span class="sxs-lookup"><span data-stu-id="5836c-161">Set the “application registries” table configurations to default:</span></span>

* <span data-ttu-id="5836c-162">Rótulo = registradores de aplicativos</span><span class="sxs-lookup"><span data-stu-id="5836c-162">Label = Application Registeries</span></span>
* <span data-ttu-id="5836c-163">Nome = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="5836c-163">Name = oauth_entity</span></span>
* <span data-ttu-id="5836c-164">Acessível a partir de = todos os escopos do aplicativo</span><span class="sxs-lookup"><span data-stu-id="5836c-164">Accessible from = All application scopes</span></span>
* <span data-ttu-id="5836c-165">Caixa de seleção pode ler = marcada</span><span class="sxs-lookup"><span data-stu-id="5836c-165">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="5836c-166">Como validar a entidade OAuth criada para o conector de conformidade de & de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5836c-166">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="5836c-167">Vá para a tabela registros de aplicativos (**Menu > registro de aplicativo > OAuth de sistema**) no ServiceNow e localize a entidade OAuth criada por você, com o nome que você atribuiu a ela.</span><span class="sxs-lookup"><span data-stu-id="5836c-167">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow and find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="logging-in-as-the-integration-user"></a><span data-ttu-id="5836c-168">Como fazer logon como o usuário de integração</span><span class="sxs-lookup"><span data-stu-id="5836c-168">Logging in as the integration user</span></span>

<span data-ttu-id="5836c-169">Antes de autorizar a conexão entre o centro de segurança do Microsoft 365 e o ServiceNow, certifique-se de usar o logon e a senha de usuário de integração que você criou nas etapas de instalação.</span><span class="sxs-lookup"><span data-stu-id="5836c-169">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="5836c-170">Não use suas credenciais pessoais.</span><span class="sxs-lookup"><span data-stu-id="5836c-170">Do not use your personal credentials.</span></span>

1. <span data-ttu-id="5836c-171">Vá para a página autorização no ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="5836c-171">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="5836c-172">Se você estiver conectado com suas credenciais pessoais, selecione o **não é possível** vincular no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="5836c-172">If you are signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="5836c-173">Faça logon no ServiceNow como o usuário de integração que você criou anteriormente na lista de verificação de instalação.</span><span class="sxs-lookup"><span data-stu-id="5836c-173">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="5836c-174">Selecione **permitir** na página do servicenow que pergunta se o conector de segurança + conformidade pode se conectar à sua conta do servicenow.</span><span class="sxs-lookup"><span data-stu-id="5836c-174">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="5836c-175">Prossiga com as etapas de configuração.</span><span class="sxs-lookup"><span data-stu-id="5836c-175">Proceed with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="5836c-176">Como validar o usuário de integração criado com a lista de verificação de instalação do conector de conformidade do & de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5836c-176">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="5836c-177">Vá para a tabela usuários **(Menu > administração de usuário > usuários**) no ServiceNow e localize o usuário de integração criado por você, com o nome atribuído a ele.</span><span class="sxs-lookup"><span data-stu-id="5836c-177">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="5836c-178">Sua empresa tem o logon único habilitado, o que impede que você se conecte ao ServiceNow através da central de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5836c-178">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="5836c-179">Se sua empresa ativou o logon único e você recebe um erro ou o logon não é bem-sucedido, siga uma das duas soluções.</span><span class="sxs-lookup"><span data-stu-id="5836c-179">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="log-into-servicenow-as-the-integration-user"></a><span data-ttu-id="5836c-180">Faça logon no ServiceNow como o usuário de integração</span><span class="sxs-lookup"><span data-stu-id="5836c-180">Log into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="5836c-181">Volte para a página autorização no ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="5836c-181">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="5836c-182">Selecione o **não é possível** vincular no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="5836c-182">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="5836c-183">Faça logon no ServiceNow como o usuário de integração que você criou anteriormente na lista de verificação de instalação.</span><span class="sxs-lookup"><span data-stu-id="5836c-183">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="5836c-184">Selecione **permitir** na página do servicenow que pergunta se o conector de segurança + conformidade pode se conectar à sua conta do servicenow.</span><span class="sxs-lookup"><span data-stu-id="5836c-184">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="5836c-185">Prossiga com as etapas de configuração.</span><span class="sxs-lookup"><span data-stu-id="5836c-185">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="5836c-186">Criar um usuário de administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="5836c-186">Create a security admin user</span></span>

1. <span data-ttu-id="5836c-187">Criar um usuário com privilégios de administrador de segurança no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5836c-187">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="5836c-188">O usuário precisa ter o mesmo nome e endereço de email do usuário de integração que você criou na lista de verificação de instalação.</span><span class="sxs-lookup"><span data-stu-id="5836c-188">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="5836c-189">Você pode remover a função de administrador de segurança após o logon e a conexão ter sido concluída.</span><span class="sxs-lookup"><span data-stu-id="5836c-189">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="5836c-190">Faça logon no centro de segurança do Microsoft 365 como este usuário e siga as etapas de configuração.</span><span class="sxs-lookup"><span data-stu-id="5836c-190">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="5836c-191">A instalação está concluída, mas não vê tíquetes e não pode ser compartilhada</span><span class="sxs-lookup"><span data-stu-id="5836c-191">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="5836c-192">Se as etapas de instalação e configuração tiverem sido concluídas, mas você não vir os cartões do ServiceNow na Home Page e não puder compartilhar o ServiceNow pela pontuação segura da Microsoft, verifique o status da página de https://security.microsoft.com/ticketProvisioningprovisionamento em.</span><span class="sxs-lookup"><span data-stu-id="5836c-192">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="5836c-193">Selecione **autorizar** e retornar para a página inicial.</span><span class="sxs-lookup"><span data-stu-id="5836c-193">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="5836c-194">Os cartões devem ser exibidos.</span><span class="sxs-lookup"><span data-stu-id="5836c-194">The cards should appear.</span></span>

