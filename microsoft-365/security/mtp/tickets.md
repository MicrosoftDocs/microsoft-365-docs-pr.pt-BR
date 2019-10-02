---
title: Criar e acompanhar tíquetes por meio do ServiceNow
description: A central de segurança do Microsoft 365 está sendo aprimorada com a capacidade de criar e controlar de forma nativa as permissões no ServiceNow. Isso permite que os administradores de segurança enviem uma recomendação de Pontuação segura diretamente para o ServiceNow e criem uma permissão.
keywords: segurança, Microsoft 365, M365, Pontuação segura, central de segurança, ServiceNow, tíquetes, tarefas
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.openlocfilehash: b0b8cda81bb6cec3958e7b2a758da191d803a0ed
ms.sourcegitcommit: acf29701bfba3e4843e49a79fde012f3c7a7024a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2019
ms.locfileid: "37350322"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="e5965-105">Gerenciar tíquetes pelo ServiceNow</span><span class="sxs-lookup"><span data-stu-id="e5965-105">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="e5965-106">A central de segurança do Microsoft 365 está sendo aprimorada com a capacidade de criar e controlar de forma nativa as permissões no ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="e5965-106">Microsoft 365 security center is being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="e5965-107">Isso permite que os administradores de segurança enviem uma ação de melhoria de [Pontuação segura da Microsoft](microsoft-secure-score.md) diretamente para o ServiceNow e crie uma permissão.</span><span class="sxs-lookup"><span data-stu-id="e5965-107">This allows security administrators to send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="e5965-108">As permissões de gerenciamento de incidentes e de alterações podem ser criadas.</span><span class="sxs-lookup"><span data-stu-id="e5965-108">Both incident management and change management tickets can be created.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e5965-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e5965-109">Prerequisites</span></span>

<span data-ttu-id="e5965-110">Ter acesso à central de segurança do Microsoft 365 e uma instância do ServiceNow com:</span><span class="sxs-lookup"><span data-stu-id="e5965-110">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="e5965-111">Kingston ou versão superior</span><span class="sxs-lookup"><span data-stu-id="e5965-111">Kingston or higher version</span></span>
* <span data-ttu-id="e5965-112">Ter credenciais do administrador HI</span><span class="sxs-lookup"><span data-stu-id="e5965-112">Have admin HI credentials</span></span>
* <span data-ttu-id="e5965-113">Ter privilégios de administrador na instância de fornecedor de destino</span><span class="sxs-lookup"><span data-stu-id="e5965-113">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="e5965-114">O ServiceNow recomenda que os usuários mantenham as configurações da caixa (padrão) em sua instância do ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="e5965-114">ServiceNow recommends users keep out of the box settings (default) in your ServiceNow instance.</span></span>  <span data-ttu-id="e5965-115">Ter personalizações pode causar erros ao concluir a lista de verificação de instalação e integração com a central de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e5965-115">Having customizations could cause errors in completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="e5965-116">Troca de dados</span><span class="sxs-lookup"><span data-stu-id="e5965-116">Data exchange</span></span>

<span data-ttu-id="e5965-117">Quando você conectar a central de segurança do Microsoft 365 ao ServiceNow, a Microsoft receberá os seguintes dados adicionais:</span><span class="sxs-lookup"><span data-stu-id="e5965-117">When you connect the Microsoft 365 security center to ServiceNow, Microsoft will be receiving the following additional data:</span></span>

* <span data-ttu-id="e5965-118">Nome da instância do ServiceNow</span><span class="sxs-lookup"><span data-stu-id="e5965-118">ServiceNow instance name</span></span>
* <span data-ttu-id="e5965-119">ID do cliente do ServiceNow</span><span class="sxs-lookup"><span data-stu-id="e5965-119">ServiceNow client ID</span></span>
* <span data-ttu-id="e5965-120">Segredo do cliente do ServiceNow</span><span class="sxs-lookup"><span data-stu-id="e5965-120">ServiceNow client secret</span></span>
* <span data-ttu-id="e5965-121">Tokens de atualização & Access</span><span class="sxs-lookup"><span data-stu-id="e5965-121">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="e5965-122">Quando você cria uma permissão do ServiceNow no centro de segurança do Microsoft 365, os dados a seguir são enviados para o ServiceNow:</span><span class="sxs-lookup"><span data-stu-id="e5965-122">When you create a ServiceNow ticket from the Microsoft 365 security center the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="e5965-123">ID de usuário que inicia a criação de tíquete</span><span class="sxs-lookup"><span data-stu-id="e5965-123">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="e5965-124">Nome da tarefa</span><span class="sxs-lookup"><span data-stu-id="e5965-124">Task name</span></span>
* <span data-ttu-id="e5965-125">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="e5965-125">Task description</span></span>
* <span data-ttu-id="e5965-126">Prioridade</span><span class="sxs-lookup"><span data-stu-id="e5965-126">Priority</span></span>
* <span data-ttu-id="e5965-127">Data de conclusão</span><span class="sxs-lookup"><span data-stu-id="e5965-127">Due date</span></span>
* <span data-ttu-id="e5965-128">Fonte de recomendação (recomendação do usuário ou recomendação da Microsoft)</span><span class="sxs-lookup"><span data-stu-id="e5965-128">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="e5965-129">Categoria de recomendação (dispositivos, dados, aplicativos, identidade, infraestrutura)</span><span class="sxs-lookup"><span data-stu-id="e5965-129">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="e5965-130">Conectar a central de segurança do Microsoft 365 ao ServiceNow</span><span class="sxs-lookup"><span data-stu-id="e5965-130">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="e5965-131">Navegue até a home page do centro de segurança do Microsoft 365, onde você verá um cartão perguntando se você usa o ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="e5965-131">Navigate to the Microsoft 365 security center home page, where you will see a card asking if you use ServiceNow.</span></span>

![Você usa o ServiceNow](../images/do-you-use-servicenow-250.png)

<span data-ttu-id="e5965-133">A partir daí, você será enviado para a página de configuração do ServiceNow, onde você seguirá as instruções para autorizar o aplicativo do conector 365 da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e5965-133">From there you will be sent to the ServiceNow set up page where you'll follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

<span data-ttu-id="e5965-134">Ao autorizar a conexão entre o centro de segurança do Microsoft 365 e o ServiceNow, certifique-se de usar o logon e a senha de usuário de integração que você criou nas etapas de instalação e não suas credenciais pessoais.</span><span class="sxs-lookup"><span data-stu-id="e5965-134">When authorizing the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps and not your personal credentials.</span></span>

<span data-ttu-id="e5965-135">Depois de seguir as instruções e autorizar a conexão, você pode exibir o status da conexão na página de conexão da central de segurança do Microsoft 365 e na experiência do aplicativo do Microsoft 365 Ticketing Connector.</span><span class="sxs-lookup"><span data-stu-id="e5965-135">After following the directions and authorizing the connection, you can view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="e5965-136">Agora, você está pronto para começar a criar tarefas!</span><span class="sxs-lookup"><span data-stu-id="e5965-136">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="e5965-137">Criar uma tarefa e compartilhá-la para o ServiceNow</span><span class="sxs-lookup"><span data-stu-id="e5965-137">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="e5965-138">Depois que a integração é configurada, você pode criar tarefas do ServiceNow com base em ações específicas de melhoria da Pontuação segura da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e5965-138">Once the integration is set up, you can create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="e5965-139">Vá para qualquer ação de melhoria na pontuação segura no portal da central de segurança do Microsoft 365 e selecione o ícone "compartilhar".</span><span class="sxs-lookup"><span data-stu-id="e5965-139">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the “share” icon.</span></span> <span data-ttu-id="e5965-140">Uma das opções de DropDown é o ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="e5965-140">One of the dropdown options is ServiceNow.</span></span>

![Compartilhamento do ServiceNow em Pontuação segura](../images/servicenow-share.png)

<span data-ttu-id="e5965-142">Uma tarefa será gerada onde você pode definir a prioridade e editar o nome, a descrição ou a data de conclusão.</span><span class="sxs-lookup"><span data-stu-id="e5965-142">A task will then be generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="e5965-143">Após todos os campos obrigatórios serem preenchidos, você pode enviar a tarefa para o ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="e5965-143">Once all the required fields are filled in, you can send the task to ServiceNow.</span></span>

<span data-ttu-id="e5965-144">A tarefa estará visível no ServiceNow como uma solicitação de alteração de configuração e segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e5965-144">The task will be visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="e5965-145">Controlar ingressos</span><span class="sxs-lookup"><span data-stu-id="e5965-145">Track tickets</span></span>

<span data-ttu-id="e5965-146">Depois que as permissões de gerenciamento de alterações e de gerenciamento de incidentes tiverem sido criadas, elas serão exibidas em cartões na home page do centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e5965-146">Once ServiceNow change management and incident management tickets have been created, they will be displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="e5965-147">A partir desses cartões, você pode criar um tíquete, exibir todos os tíquetes ou gerenciar a configuração do ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="e5965-147">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![Tíquetes de gerenciamento de alterações do ServiceNow](../images/change-management-375.png)  ![Tíquetes de gerenciamento de incidentes do ServiceNow](../images/incident-management-375.png)

<span data-ttu-id="e5965-150">Para reprovisionar ou gerenciar sua integração do ServiceNow no centro de segurança do Microsoft 365, selecione **gerenciar a configuração do servicenow** em qualquer um dos cartões.</span><span class="sxs-lookup"><span data-stu-id="e5965-150">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="e5965-151">A partir daí, você pode remover a conexão atual do ServiceNow e personalizar os nomes de estado de permissão.</span><span class="sxs-lookup"><span data-stu-id="e5965-151">From there you can  remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="e5965-152">Com as permissões do ServiceNow visíveis na central de segurança do Microsoft 365, suas tarefas permanecerão em um local onde poderão ser rastreadas e aplicadas junto com seus outros itens do painel de segurança.</span><span class="sxs-lookup"><span data-stu-id="e5965-152">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks will live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="e5965-153">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="e5965-153">Frequently asked questions</span></span>

### <a name="i-am-receiving-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="e5965-154">Estou recebendo um erro na primeira etapa da lista de verificação de instalação (criação de OAuth)</span><span class="sxs-lookup"><span data-stu-id="e5965-154">I am receiving an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="e5965-155">**Mensagem de erro**: a operação de leitura em relação a ' oauth_entity ' do escopo ' x_mioms_m365ticket ' foi recusada devido à política de acesso entre escopos da tabela</span><span class="sxs-lookup"><span data-stu-id="e5965-155">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="e5965-156">Nosso aplicativo presume que qualquer administrador na instância do ServiceNow possa criar e ler entidades OAuth.</span><span class="sxs-lookup"><span data-stu-id="e5965-156">Our app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="e5965-157">Esse erro pode ser causado devido a uma personalização na instância do ServiceNow, que restringe quem pode criar/ler entidades OAuth.</span><span class="sxs-lookup"><span data-stu-id="e5965-157">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span> <span data-ttu-id="e5965-158">O ServiceNow recomenda que os usuários mantenham a funcionalidade da caixa (padrão).</span><span class="sxs-lookup"><span data-stu-id="e5965-158">ServiceNow recommends users keep out of the box functionality (default).</span></span>

<span data-ttu-id="e5965-159">Defina as configurações de tabela "registros de aplicativos" como padrão:</span><span class="sxs-lookup"><span data-stu-id="e5965-159">Set the “application registries” table configurations to default:</span></span>

* <span data-ttu-id="e5965-160">Rótulo = registradores de aplicativos</span><span class="sxs-lookup"><span data-stu-id="e5965-160">Label = Application Registeries</span></span>
* <span data-ttu-id="e5965-161">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="e5965-161">Name = oauth_entity</span></span>
* <span data-ttu-id="e5965-162">Acessível a partir de = todos os escopos do aplicativo</span><span class="sxs-lookup"><span data-stu-id="e5965-162">Accessible from = All application scopes</span></span>
* <span data-ttu-id="e5965-163">Caixa de seleção pode ler = marcada</span><span class="sxs-lookup"><span data-stu-id="e5965-163">Can read = check box selected</span></span>

<span data-ttu-id="e5965-164">**O ServiceNow recomenda que os usuários mantenham a funcionalidade da caixa (padrão).**</span><span class="sxs-lookup"><span data-stu-id="e5965-164">**ServiceNow recommends users keep out of the box functionality (default).**</span></span>

### <a name="how-do-i-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="e5965-165">Como validar a entidade OAuth criada para o conector de conformidade de & de segurança do Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="e5965-165">How do I validate the OAuth entity created for Microsoft 365 Security & Compliance connector?</span></span>

<span data-ttu-id="e5965-166">Vá para a tabela registros de aplicativos (menu > registro de aplicativo > OAuth de sistema) no ServiceNow e localize a entidade OAuth criada por você (nome que você atribuiu).</span><span class="sxs-lookup"><span data-stu-id="e5965-166">Go to application registries table (Menu > System OAuth > Application Registry) in ServiceNow and find the OAuth entity created by you (name that you assigned it).</span></span>

### <a name="how-do-i-validate-the-integration-user-created-in-step-two-of-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="e5965-167">Como validar o usuário de integração criado na etapa dois da lista de verificação de instalação para o conector de conformidade & segurança da Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="e5965-167">How do I validate the Integration User created in step two of installation checklist for Microsoft 365 Security & Compliance connector?</span></span>

<span data-ttu-id="e5965-168">Vá para a tabela Users (menu > administração de usuário > usuários) no ServiceNow e localize o usuário de integração criado por você (nome que você atribuiu a ele).</span><span class="sxs-lookup"><span data-stu-id="e5965-168">Go to Users Table (Menu > User Administration > Users) in ServiceNow and find the Integration user created by you (name that you assigned it).</span></span>

<span data-ttu-id="e5965-169">Ao autorizar a conexão entre o centro de segurança do Microsoft 365 e o ServiceNow, certifique-se de usar o logon e a senha de usuário de integração que você criou nas etapas de instalação e não suas credenciais pessoais.</span><span class="sxs-lookup"><span data-stu-id="e5965-169">When authorizing the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps and not your personal credentials.</span></span>

### <a name="i-have-completed-the-installation-and-set-up-steps-but-i-am-unable-to-see-the-servicenow-cards-on-the-home-page-and-cannot-see-the-share-icon-in-microsoft-secure-score"></a><span data-ttu-id="e5965-170">Concluí as etapas de instalação e configuração, mas não consigo ver os cartões do ServiceNow na Home Page e não consigo ver o ícone de compartilhamento na pontuação segura da Microsoft</span><span class="sxs-lookup"><span data-stu-id="e5965-170">I have completed the installation and set up steps, but I am unable to see the ServiceNow cards on the home page and cannot see the Share icon in Microsoft Secure Score</span></span>

<span data-ttu-id="e5965-171">Verifique o status da página de provisionamento, acessando https://security.microsoft.com/ticketProvisioning.</span><span class="sxs-lookup"><span data-stu-id="e5965-171">Check the status of the provisioning page by going to https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="e5965-172">Selecione **salvar** e retornar para a página inicial.</span><span class="sxs-lookup"><span data-stu-id="e5965-172">Select **Save** and return to the home page.</span></span> <span data-ttu-id="e5965-173">Os cartões devem ser exibidos.</span><span class="sxs-lookup"><span data-stu-id="e5965-173">The cards should appear.</span></span>
