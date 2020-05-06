---
title: Criar e acompanhar tíquetes por meio do ServiceNow
description: Saiba como criar e acompanhar tíquetes no ServiceNow do centro de segurança do Microsoft 365.
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
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: 6070878d6cf0efd8a85d05ff6ef89ee49baf4144
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034183"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="efcd5-104">Gerenciar tíquetes pelo ServiceNow</span><span class="sxs-lookup"><span data-stu-id="efcd5-104">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="efcd5-105">O ServiceNow é uma plataforma de computação em nuvem popular que ajuda as empresas a gerenciar fluxos de trabalho digitais para operações corporativas.</span><span class="sxs-lookup"><span data-stu-id="efcd5-105">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="efcd5-106">A plataforma atual tem fluxos de trabalho de ti, fluxos de trabalho de funcionários e fluxos de trabalho de cliente.</span><span class="sxs-lookup"><span data-stu-id="efcd5-106">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> <span data-ttu-id="efcd5-107">A Microsoft fez uma parceria com o ServiceNow para tornar mais fácil para os administradores de ti gerenciar suas permissões e tarefas em ambas as plataformas.</span><span class="sxs-lookup"><span data-stu-id="efcd5-107">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> [<span data-ttu-id="efcd5-108">Saiba mais sobre o ServiceNow</span><span class="sxs-lookup"><span data-stu-id="efcd5-108">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="efcd5-109">A central de segurança do Microsoft 365 agora é aprimorada com a capacidade de criar e controlar de forma nativa as permissões no ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="efcd5-109">Microsoft 365 security center is now enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="efcd5-110">Administradores de segurança podem enviar uma ação de melhoria de [Pontuação segura da Microsoft](microsoft-secure-score.md) diretamente para o ServiceNow e criar uma permissão.</span><span class="sxs-lookup"><span data-stu-id="efcd5-110">Security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="efcd5-111">As permissões de gerenciamento de incidentes e de alterações podem ser criadas.</span><span class="sxs-lookup"><span data-stu-id="efcd5-111">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="efcd5-112">Eles podem ser rastreados na home page do centro de segurança da Microsoft e o ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="efcd5-112">They can then be tracked in the Microsoft security center home page, and ServiceNow.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="efcd5-113">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="efcd5-113">Prerequisites</span></span>

<span data-ttu-id="efcd5-114">Ter acesso à central de segurança do Microsoft 365 e uma instância do ServiceNow com:</span><span class="sxs-lookup"><span data-stu-id="efcd5-114">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="efcd5-115">Kingston ou versão superior</span><span class="sxs-lookup"><span data-stu-id="efcd5-115">Kingston or higher version</span></span>
* <span data-ttu-id="efcd5-116">Ter credenciais do administrador HI</span><span class="sxs-lookup"><span data-stu-id="efcd5-116">Have admin HI credentials</span></span>
* <span data-ttu-id="efcd5-117">Ter privilégios de administrador na instância de fornecedor de destino</span><span class="sxs-lookup"><span data-stu-id="efcd5-117">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="efcd5-118">O ServiceNow recomenda que os usuários mantenham as configurações padrão em sua instância do ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="efcd5-118">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="efcd5-119">Ter personalizações pode causar erros ao concluir a lista de verificação de instalação e integração com a central de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="efcd5-119">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="efcd5-120">Troca de dados</span><span class="sxs-lookup"><span data-stu-id="efcd5-120">Data exchange</span></span>

<span data-ttu-id="efcd5-121">Quando você conecta o centro de segurança do Microsoft 365 ao ServiceNow, a Microsoft recebe os seguintes dados adicionais:</span><span class="sxs-lookup"><span data-stu-id="efcd5-121">When you connect the Microsoft 365 security center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="efcd5-122">Nome da instância do ServiceNow</span><span class="sxs-lookup"><span data-stu-id="efcd5-122">ServiceNow instance name</span></span>
* <span data-ttu-id="efcd5-123">ID do cliente do ServiceNow</span><span class="sxs-lookup"><span data-stu-id="efcd5-123">ServiceNow client ID</span></span>
* <span data-ttu-id="efcd5-124">Segredo do cliente do ServiceNow</span><span class="sxs-lookup"><span data-stu-id="efcd5-124">ServiceNow client secret</span></span>
* <span data-ttu-id="efcd5-125">Tokens de atualização & Access</span><span class="sxs-lookup"><span data-stu-id="efcd5-125">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="efcd5-126">Quando você cria uma permissão do ServiceNow no centro de segurança do Microsoft 365, os dados a seguir são enviados para o ServiceNow:</span><span class="sxs-lookup"><span data-stu-id="efcd5-126">When you create a ServiceNow ticket from the Microsoft 365 security center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="efcd5-127">ID de usuário que inicia a criação de tíquete</span><span class="sxs-lookup"><span data-stu-id="efcd5-127">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="efcd5-128">Nome da tarefa</span><span class="sxs-lookup"><span data-stu-id="efcd5-128">Task name</span></span>
* <span data-ttu-id="efcd5-129">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="efcd5-129">Task description</span></span>
* <span data-ttu-id="efcd5-130">Prioridade</span><span class="sxs-lookup"><span data-stu-id="efcd5-130">Priority</span></span>
* <span data-ttu-id="efcd5-131">Data de conclusão</span><span class="sxs-lookup"><span data-stu-id="efcd5-131">Due date</span></span>
* <span data-ttu-id="efcd5-132">Fonte de recomendação (recomendação do usuário ou recomendação da Microsoft)</span><span class="sxs-lookup"><span data-stu-id="efcd5-132">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="efcd5-133">Categoria de recomendação (dispositivos, dados, aplicativos, identidade, infraestrutura)</span><span class="sxs-lookup"><span data-stu-id="efcd5-133">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="efcd5-134">Conectar a central de segurança do Microsoft 365 ao ServiceNow</span><span class="sxs-lookup"><span data-stu-id="efcd5-134">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="efcd5-135">Navegue até a home page do centro de segurança do Microsoft 365 para ver o cartão de conexão do ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="efcd5-135">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![Você usa o ServiceNow](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="efcd5-137">Selecione "conectar ao ServiceNow" para ir para a página de configuração do ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="efcd5-137">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="efcd5-138">Siga as instruções para autorizar o aplicativo conector 365 da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="efcd5-138">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="efcd5-139">Antes de autorizar a conexão entre o centro de segurança do Microsoft 365 e o ServiceNow, certifique-se de usar o logon e a senha de usuário de integração que você criou nas etapas de instalação.</span><span class="sxs-lookup"><span data-stu-id="efcd5-139">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="efcd5-140">Não use suas credenciais pessoais.</span><span class="sxs-lookup"><span data-stu-id="efcd5-140">Do not use your personal credentials.</span></span>

<span data-ttu-id="efcd5-141">Após ter seguido as orientações e autorizar a conexão, veja o status da conexão na página conexão da central de segurança do Microsoft 365 e na experiência do aplicativo do Microsoft 365 Ticketing Connector.</span><span class="sxs-lookup"><span data-stu-id="efcd5-141">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="efcd5-142">Agora, você está pronto para começar a criar tarefas!</span><span class="sxs-lookup"><span data-stu-id="efcd5-142">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="efcd5-143">Criar uma tarefa e compartilhá-la para o ServiceNow</span><span class="sxs-lookup"><span data-stu-id="efcd5-143">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="efcd5-144">Depois que a integração é configurada, crie tarefas do ServiceNow com base em ações específicas de melhoria da Pontuação segura da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="efcd5-144">Once the integration is set up, create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="efcd5-145">Vá para qualquer ação de melhoria na pontuação segura no portal da central de segurança do Microsoft 365 e selecione o ícone "compartilhar".</span><span class="sxs-lookup"><span data-stu-id="efcd5-145">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the "share" icon.</span></span> <span data-ttu-id="efcd5-146">Uma das opções de DropDown é o ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="efcd5-146">One of the dropdown options is ServiceNow.</span></span>

![Compartilhamento do ServiceNow em Pontuação segura](../../media/servicenow-share.png)

<span data-ttu-id="efcd5-148">Uma tarefa é gerada onde você pode definir a prioridade e editar o nome, a descrição ou a data de conclusão.</span><span class="sxs-lookup"><span data-stu-id="efcd5-148">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="efcd5-149">Após todos os campos obrigatórios serem preenchidos, envie a tarefa para o ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="efcd5-149">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="efcd5-150">A tarefa está visível no ServiceNow como uma solicitação de alteração de configuração e segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="efcd5-150">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="efcd5-151">Controlar ingressos</span><span class="sxs-lookup"><span data-stu-id="efcd5-151">Track tickets</span></span>

<span data-ttu-id="efcd5-152">Depois que o gerenciamento de alterações e as permissões de gerenciamento de incidentes tiverem sido criados, eles serão exibidos em cartões na home page do centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="efcd5-152">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="efcd5-153">A partir desses cartões, você pode criar um tíquete, exibir todos os tíquetes ou gerenciar a configuração do ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="efcd5-153">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![Tíquetes de gerenciamento de alterações do ServiceNow](../../media/change-management-375.png)  ![Tíquetes de gerenciamento de incidentes do ServiceNow](../../media/incident-management-375.png)

<span data-ttu-id="efcd5-156">Para reprovisionar ou gerenciar sua integração do ServiceNow no centro de segurança do Microsoft 365, selecione **gerenciar a configuração do servicenow** em qualquer um dos cartões.</span><span class="sxs-lookup"><span data-stu-id="efcd5-156">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="efcd5-157">A partir daí, remova a conexão atual do ServiceNow e personalize os nomes de estado de tíquete.</span><span class="sxs-lookup"><span data-stu-id="efcd5-157">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="efcd5-158">Com as permissões do ServiceNow visíveis no centro de segurança do Microsoft 365, suas tarefas residem em um local onde elas podem ser rastreadas e aplicadas junto com seus outros itens do painel de segurança.</span><span class="sxs-lookup"><span data-stu-id="efcd5-158">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="efcd5-159">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="efcd5-159">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="efcd5-160">Você recebe um erro na primeira etapa da lista de verificação de instalação (criação de OAuth)</span><span class="sxs-lookup"><span data-stu-id="efcd5-160">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="efcd5-161">**Mensagem de erro**: a operação de leitura em relação a ' oauth_entity ' do escopo ' x_mioms_m365ticket ' foi recusada devido à política de acesso entre escopos da tabela</span><span class="sxs-lookup"><span data-stu-id="efcd5-161">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="efcd5-162">O aplicativo presume que qualquer administrador na instância do ServiceNow possa criar e ler entidades OAuth.</span><span class="sxs-lookup"><span data-stu-id="efcd5-162">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="efcd5-163">Esse erro pode ser causado devido a uma personalização na instância do ServiceNow, que restringe quem pode criar/ler entidades OAuth.</span><span class="sxs-lookup"><span data-stu-id="efcd5-163">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="efcd5-164">**O ServiceNow recomenda que os usuários mantenham a funcionalidade padrão.**</span><span class="sxs-lookup"><span data-stu-id="efcd5-164">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="efcd5-165">Defina as configurações de tabela "registros de aplicativos" como padrão:</span><span class="sxs-lookup"><span data-stu-id="efcd5-165">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="efcd5-166">Rótulo = registradores de aplicativos</span><span class="sxs-lookup"><span data-stu-id="efcd5-166">Label = Application Registeries</span></span>
* <span data-ttu-id="efcd5-167">Nome = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="efcd5-167">Name = oauth_entity</span></span>
* <span data-ttu-id="efcd5-168">Acessível a partir de = todos os escopos do aplicativo</span><span class="sxs-lookup"><span data-stu-id="efcd5-168">Accessible from = All application scopes</span></span>
* <span data-ttu-id="efcd5-169">Caixa de seleção pode ler = marcada</span><span class="sxs-lookup"><span data-stu-id="efcd5-169">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="efcd5-170">Como validar a entidade OAuth criada para o conector de conformidade de & de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="efcd5-170">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="efcd5-171">Vá para a tabela registros de aplicativos (**Menu > registro de aplicativo > OAuth de sistema**) no ServiceNow e localize a entidade OAuth criada por você, com o nome que você atribuiu a ela.</span><span class="sxs-lookup"><span data-stu-id="efcd5-171">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow and find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="logging-in-as-the-integration-user"></a><span data-ttu-id="efcd5-172">Como fazer logon como o usuário de integração</span><span class="sxs-lookup"><span data-stu-id="efcd5-172">Logging in as the integration user</span></span>

<span data-ttu-id="efcd5-173">Antes de autorizar a conexão entre o centro de segurança do Microsoft 365 e o ServiceNow, certifique-se de usar o logon e a senha de usuário de integração que você criou nas etapas de instalação.</span><span class="sxs-lookup"><span data-stu-id="efcd5-173">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="efcd5-174">Não use suas credenciais pessoais.</span><span class="sxs-lookup"><span data-stu-id="efcd5-174">Do not use your personal credentials.</span></span>

1. <span data-ttu-id="efcd5-175">Vá para a página autorização no ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="efcd5-175">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="efcd5-176">Se você estiver conectado com suas credenciais pessoais, selecione o **não é possível** vincular no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="efcd5-176">If you are signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="efcd5-177">Faça logon no ServiceNow como o usuário de integração que você criou anteriormente na lista de verificação de instalação.</span><span class="sxs-lookup"><span data-stu-id="efcd5-177">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="efcd5-178">Selecione **permitir** na página do servicenow que pergunta se o conector de segurança + conformidade pode se conectar à sua conta do servicenow.</span><span class="sxs-lookup"><span data-stu-id="efcd5-178">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="efcd5-179">Prossiga com as etapas de configuração.</span><span class="sxs-lookup"><span data-stu-id="efcd5-179">Proceed with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="efcd5-180">Como validar o usuário de integração criado com a lista de verificação de instalação do conector de conformidade do & de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="efcd5-180">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="efcd5-181">Vá para a tabela usuários **(Menu > administração de usuário > usuários**) no ServiceNow e localize o usuário de integração criado por você, com o nome atribuído a ele.</span><span class="sxs-lookup"><span data-stu-id="efcd5-181">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="efcd5-182">Sua empresa tem o logon único habilitado, o que impede que você se conecte ao ServiceNow através da central de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="efcd5-182">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="efcd5-183">Se sua empresa ativou o logon único e você recebe um erro ou o logon não é bem-sucedido, siga uma das duas soluções.</span><span class="sxs-lookup"><span data-stu-id="efcd5-183">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="log-into-servicenow-as-the-integration-user"></a><span data-ttu-id="efcd5-184">Faça logon no ServiceNow como o usuário de integração</span><span class="sxs-lookup"><span data-stu-id="efcd5-184">Log into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="efcd5-185">Volte para a página autorização no ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="efcd5-185">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="efcd5-186">Selecione o **não é possível** vincular no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="efcd5-186">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="efcd5-187">Faça logon no ServiceNow como o usuário de integração que você criou anteriormente na lista de verificação de instalação.</span><span class="sxs-lookup"><span data-stu-id="efcd5-187">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="efcd5-188">Selecione **permitir** na página do servicenow que pergunta se o conector de segurança + conformidade pode se conectar à sua conta do servicenow.</span><span class="sxs-lookup"><span data-stu-id="efcd5-188">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="efcd5-189">Prossiga com as etapas de configuração.</span><span class="sxs-lookup"><span data-stu-id="efcd5-189">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="efcd5-190">Criar um usuário de administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="efcd5-190">Create a security admin user</span></span>

1. <span data-ttu-id="efcd5-191">Criar um usuário com privilégios de administrador de segurança no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="efcd5-191">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="efcd5-192">O usuário precisa ter o mesmo nome e endereço de email do usuário de integração que você criou na lista de verificação de instalação.</span><span class="sxs-lookup"><span data-stu-id="efcd5-192">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="efcd5-193">Você pode remover a função de administrador de segurança após o logon e a conexão ter sido concluída.</span><span class="sxs-lookup"><span data-stu-id="efcd5-193">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="efcd5-194">Faça logon no centro de segurança do Microsoft 365 como este usuário e siga as etapas de configuração.</span><span class="sxs-lookup"><span data-stu-id="efcd5-194">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="efcd5-195">Filtragem de IP</span><span class="sxs-lookup"><span data-stu-id="efcd5-195">IP filtering</span></span>

<span data-ttu-id="efcd5-196">Se você habilitou a filtragem de IP, talvez seja necessário permitir explicitamente endereços IP.</span><span class="sxs-lookup"><span data-stu-id="efcd5-196">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="efcd5-197">Consulte [controle de acesso de endereço IP](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) para obter informações sobre como permitir intervalos IP no ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="efcd5-197">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="efcd5-198">Consulte [Azure IP Ranges and Service Tags-Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) para obter uma lista de endereços IP para permitir.</span><span class="sxs-lookup"><span data-stu-id="efcd5-198">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="efcd5-199">A instalação está concluída, mas não vê tíquetes e não pode ser compartilhada</span><span class="sxs-lookup"><span data-stu-id="efcd5-199">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="efcd5-200">Se as etapas de instalação e configuração tiverem sido concluídas, mas você não vir os cartões do ServiceNow na Home Page e não puder compartilhar o ServiceNow pela pontuação segura da Microsoft, verifique o status da página de https://security.microsoft.com/ticketProvisioningprovisionamento em.</span><span class="sxs-lookup"><span data-stu-id="efcd5-200">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="efcd5-201">Selecione **autorizar** e retornar para a página inicial.</span><span class="sxs-lookup"><span data-stu-id="efcd5-201">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="efcd5-202">Os cartões devem ser exibidos.</span><span class="sxs-lookup"><span data-stu-id="efcd5-202">The cards should appear.</span></span>

