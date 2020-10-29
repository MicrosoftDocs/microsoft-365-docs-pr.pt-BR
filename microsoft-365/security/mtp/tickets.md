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
ms.openlocfilehash: a2650efbac0966b84e6fbfd6ce78cb732f4933b3
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769648"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a><span data-ttu-id="7cc52-104">Integre as permissões do ServiceNow no centro de segurança e centro de conformidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7cc52-104">Integrate ServiceNow tickets into the Microsoft 365 security center and compliance center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!CAUTION]
><span data-ttu-id="7cc52-105">**O período de visualização para o conector do ServiceNow está terminando**</span><span class="sxs-lookup"><span data-stu-id="7cc52-105">**The preview period for the ServiceNow connector is ending**</span></span><br>
><span data-ttu-id="7cc52-106">Esse recurso não estará mais disponível até o final de novembro de 2020.</span><span class="sxs-lookup"><span data-stu-id="7cc52-106">This capability will no longer available by the end of November 2020.</span></span> <span data-ttu-id="7cc52-107">Obrigado por seus comentários e suporte contínuo enquanto determinamos as próximas etapas.</span><span class="sxs-lookup"><span data-stu-id="7cc52-107">Thank you for your feedback and continued support while we determine next steps.</span></span>

<span data-ttu-id="7cc52-108">O ServiceNow é uma plataforma de computação em nuvem popular que ajuda as empresas a gerenciar fluxos de trabalho digitais para operações corporativas.</span><span class="sxs-lookup"><span data-stu-id="7cc52-108">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="7cc52-109">A plataforma atual tem fluxos de trabalho de ti, fluxos de trabalho de funcionários e fluxos de trabalho de cliente.</span><span class="sxs-lookup"><span data-stu-id="7cc52-109">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> [<span data-ttu-id="7cc52-110">Saiba mais sobre o ServiceNow</span><span class="sxs-lookup"><span data-stu-id="7cc52-110">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="7cc52-111">A Microsoft fez uma parceria com o ServiceNow para tornar mais fácil para os administradores de ti gerenciar suas permissões e tarefas em ambas as plataformas.</span><span class="sxs-lookup"><span data-stu-id="7cc52-111">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> <span data-ttu-id="7cc52-112">O centro de [segurança do microsoft 365](overview-security-center.md) e o [centro de conformidade da Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) estão sendo aprimorados com a capacidade de criar e controlar de forma nativa as permissões no ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="7cc52-112">[Microsoft 365 security center](overview-security-center.md) and the [Microsoft 365 compliance center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) are being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span>

- [<span data-ttu-id="7cc52-113">**Gerenciar tíquetes do ServiceNow na central de segurança**</span><span class="sxs-lookup"><span data-stu-id="7cc52-113">**Manage ServiceNow tickets in the security center**</span></span>](tickets-security-center.md)
- <span data-ttu-id="7cc52-114">**Gerenciar tíquetes do ServiceNow no centro de conformidade** (em breve)</span><span class="sxs-lookup"><span data-stu-id="7cc52-114">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7cc52-115">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="7cc52-115">Prerequisites</span></span>

<span data-ttu-id="7cc52-116">Ter acesso ao centro de segurança ou ao centro de conformidade do Microsoft 365 e a uma instância do ServiceNow com:</span><span class="sxs-lookup"><span data-stu-id="7cc52-116">Have access to the Microsoft 365 security center or compliance center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="7cc52-117">Kingston ou versão superior</span><span class="sxs-lookup"><span data-stu-id="7cc52-117">Kingston or higher version</span></span>
* <span data-ttu-id="7cc52-118">Ter credenciais do administrador HI</span><span class="sxs-lookup"><span data-stu-id="7cc52-118">Have admin HI credentials</span></span>
* <span data-ttu-id="7cc52-119">Ter privilégios de administrador na instância de fornecedor de destino</span><span class="sxs-lookup"><span data-stu-id="7cc52-119">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="7cc52-120">O ServiceNow recomenda que os usuários mantenham as configurações padrão em sua instância do ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="7cc52-120">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="7cc52-121">Ter personalizações pode causar erros ao concluir a lista de verificação de instalação e integração com a central de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7cc52-121">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="7cc52-122">Troca de dados</span><span class="sxs-lookup"><span data-stu-id="7cc52-122">Data exchange</span></span>

<span data-ttu-id="7cc52-123">Quando você conecta o centro de segurança ou o centro de conformidade do Microsoft 365 ao ServiceNow, a Microsoft recebe os seguintes dados adicionais:</span><span class="sxs-lookup"><span data-stu-id="7cc52-123">When you connect the Microsoft 365 security center or compliance center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="7cc52-124">Nome da instância do ServiceNow</span><span class="sxs-lookup"><span data-stu-id="7cc52-124">ServiceNow instance name</span></span>
* <span data-ttu-id="7cc52-125">ID do cliente do ServiceNow</span><span class="sxs-lookup"><span data-stu-id="7cc52-125">ServiceNow client ID</span></span>
* <span data-ttu-id="7cc52-126">Segredo do cliente do ServiceNow</span><span class="sxs-lookup"><span data-stu-id="7cc52-126">ServiceNow client secret</span></span>
* <span data-ttu-id="7cc52-127">Tokens de atualização & Access</span><span class="sxs-lookup"><span data-stu-id="7cc52-127">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="7cc52-128">Quando você cria uma permissão do ServiceNow no centro de segurança ou centro de conformidade do Microsoft 365, os dados a seguir são enviados para o ServiceNow:</span><span class="sxs-lookup"><span data-stu-id="7cc52-128">When you create a ServiceNow ticket from the Microsoft 365 security center or compliance center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="7cc52-129">ID de usuário que inicia a criação de tíquete</span><span class="sxs-lookup"><span data-stu-id="7cc52-129">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="7cc52-130">Nome da tarefa</span><span class="sxs-lookup"><span data-stu-id="7cc52-130">Task name</span></span>
* <span data-ttu-id="7cc52-131">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="7cc52-131">Task description</span></span>
* <span data-ttu-id="7cc52-132">Priority</span><span class="sxs-lookup"><span data-stu-id="7cc52-132">Priority</span></span>
* <span data-ttu-id="7cc52-133">Data de conclusão</span><span class="sxs-lookup"><span data-stu-id="7cc52-133">Due date</span></span>
* <span data-ttu-id="7cc52-134">Fonte de recomendação (recomendação do usuário ou recomendação da Microsoft)</span><span class="sxs-lookup"><span data-stu-id="7cc52-134">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="7cc52-135">Categoria de recomendação (dispositivos, dados, aplicativos, identidade, infraestrutura)</span><span class="sxs-lookup"><span data-stu-id="7cc52-135">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-to-servicenow"></a><span data-ttu-id="7cc52-136">Conectar-se ao ServiceNow</span><span class="sxs-lookup"><span data-stu-id="7cc52-136">Connect to ServiceNow</span></span>

<span data-ttu-id="7cc52-137">Vá para [criar e acompanhar tíquetes do ServiceNow no centro de segurança do Microsoft 365](tickets-security-center.md) para saber como se conectar ao ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="7cc52-137">Go to [Create and track ServiceNow tickets in the Microsoft 365 security center](tickets-security-center.md) to learn how to connect to ServiceNow.</span></span> <span data-ttu-id="7cc52-138">A conexão com o centro de conformidade da Microsoft 365 estará disponível em breve.</span><span class="sxs-lookup"><span data-stu-id="7cc52-138">Connecting from the Microsoft 365 compliance center is coming soon.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="7cc52-139">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="7cc52-139">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="7cc52-140">Você recebe um erro na primeira etapa da lista de verificação de instalação (criação de OAuth)</span><span class="sxs-lookup"><span data-stu-id="7cc52-140">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="7cc52-141">**Mensagem de erro** : a operação de leitura em relação a ' oauth_entity ' do escopo ' x_mioms_m365ticket ' foi recusada devido à política de acesso entre escopos da tabela</span><span class="sxs-lookup"><span data-stu-id="7cc52-141">**Error Message** : Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused because of the table's cross-scope access policy</span></span>

<span data-ttu-id="7cc52-142">O aplicativo presume que qualquer administrador na instância do ServiceNow possa criar e ler entidades OAuth.</span><span class="sxs-lookup"><span data-stu-id="7cc52-142">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="7cc52-143">Esse erro pode ser causado por uma personalização na instância do ServiceNow que restringe quem pode criar ou ler entidades OAuth.</span><span class="sxs-lookup"><span data-stu-id="7cc52-143">This error could be caused by a customization in your instance of ServiceNow that restricts who can create or read OAuth entities.</span></span>

<span data-ttu-id="7cc52-144">**O ServiceNow recomenda que os usuários mantenham a funcionalidade padrão.**</span><span class="sxs-lookup"><span data-stu-id="7cc52-144">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="7cc52-145">Defina as configurações de tabela "registros de aplicativos" como padrão:</span><span class="sxs-lookup"><span data-stu-id="7cc52-145">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="7cc52-146">Rótulo = registradores de aplicativos</span><span class="sxs-lookup"><span data-stu-id="7cc52-146">Label = Application Registeries</span></span>
* <span data-ttu-id="7cc52-147">Nome = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="7cc52-147">Name = oauth_entity</span></span>
* <span data-ttu-id="7cc52-148">Acessível a partir de = todos os escopos do aplicativo</span><span class="sxs-lookup"><span data-stu-id="7cc52-148">Accessible from = All application scopes</span></span>
* <span data-ttu-id="7cc52-149">Caixa de seleção pode ler = marcada</span><span class="sxs-lookup"><span data-stu-id="7cc52-149">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="7cc52-150">Como validar a entidade OAuth criada para o conector de conformidade de & de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7cc52-150">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="7cc52-151">Vá para a tabela registros de aplicativos ( **Menu > sistema OAuth > registro de aplicativo** ) no ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="7cc52-151">Go to application registries table ( **Menu > System OAuth > Application Registry** ) in ServiceNow.</span></span> <span data-ttu-id="7cc52-152">Encontre a entidade OAuth criada por você, com o nome que você atribuiu a ela.</span><span class="sxs-lookup"><span data-stu-id="7cc52-152">Find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="signing-in-as-the-integration-user"></a><span data-ttu-id="7cc52-153">Entrar como o usuário de integração</span><span class="sxs-lookup"><span data-stu-id="7cc52-153">Signing in as the integration user</span></span>

<span data-ttu-id="7cc52-154">Antes de autorizar a conexão entre o centro de segurança do Microsoft 365 e o ServiceNow, certifique-se de usar o logon e a senha do usuário de integração criados nas etapas de instalação.</span><span class="sxs-lookup"><span data-stu-id="7cc52-154">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user sign in and password you created in the installation steps.</span></span> <span data-ttu-id="7cc52-155">Não use suas credenciais pessoais.</span><span class="sxs-lookup"><span data-stu-id="7cc52-155">Don't use your personal credentials.</span></span>

1. <span data-ttu-id="7cc52-156">Vá para a página autorização no ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="7cc52-156">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="7cc52-157">Se você estiver conectado com suas credenciais pessoais, selecione o **não é possível** vincular no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="7cc52-157">If you're signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="7cc52-158">Entre no ServiceNow como o usuário de integração que você criou anteriormente na lista de verificação de instalação.</span><span class="sxs-lookup"><span data-stu-id="7cc52-158">Sign in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="7cc52-159">Selecione **permitir** na página do servicenow que pergunta se o conector de segurança + conformidade pode se conectar à sua conta do servicenow.</span><span class="sxs-lookup"><span data-stu-id="7cc52-159">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="7cc52-160">Continue com as etapas de configuração.</span><span class="sxs-lookup"><span data-stu-id="7cc52-160">Continue with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="7cc52-161">Como validar o usuário de integração criado com a lista de verificação de instalação do conector de conformidade do & de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7cc52-161">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="7cc52-162">Vá para a tabela usuários **(Menu > administração de usuário > usuários** ) no ServiceNow e localize o usuário de integração criado por você, com o nome atribuído a ele.</span><span class="sxs-lookup"><span data-stu-id="7cc52-162">Go to Users Table **(Menu > User Administration > Users** ) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="7cc52-163">Sua empresa tem o logon único habilitado, o que impede que você se conecte ao ServiceNow através da central de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7cc52-163">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="7cc52-164">Se sua empresa tiver habilitado o logon único e você receber um erro ou se não tiver êxito, siga uma das duas soluções.</span><span class="sxs-lookup"><span data-stu-id="7cc52-164">If your company has enabled single sign-on and you receive an error or sign in is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="sign-in-to-servicenow-as-the-integration-user"></a><span data-ttu-id="7cc52-165">Entrar no ServiceNow como o usuário de integração</span><span class="sxs-lookup"><span data-stu-id="7cc52-165">Sign in to ServiceNow as the integration user</span></span>

1. <span data-ttu-id="7cc52-166">Volte para a página autorização no ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="7cc52-166">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="7cc52-167">Selecione o **não é possível** vincular no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="7cc52-167">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="7cc52-168">Entre no ServiceNow como o usuário de integração que você criou anteriormente na lista de verificação de instalação.</span><span class="sxs-lookup"><span data-stu-id="7cc52-168">Sign in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="7cc52-169">Selecione **permitir** na página do servicenow que pergunta se o conector de segurança + conformidade pode se conectar à sua conta do servicenow.</span><span class="sxs-lookup"><span data-stu-id="7cc52-169">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="7cc52-170">Continue com as etapas de configuração.</span><span class="sxs-lookup"><span data-stu-id="7cc52-170">Continue with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="7cc52-171">Criar um usuário de administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="7cc52-171">Create a security admin user</span></span>

1. <span data-ttu-id="7cc52-172">Criar um usuário com privilégios de administrador de segurança no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7cc52-172">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="7cc52-173">O usuário precisa ter o mesmo nome e endereço de email do usuário de integração que você criou na lista de verificação de instalação.</span><span class="sxs-lookup"><span data-stu-id="7cc52-173">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="7cc52-174">Você pode remover a função de administrador de segurança após a entrada e a conexão ter sido concluída.</span><span class="sxs-lookup"><span data-stu-id="7cc52-174">You can remove the security admin role once sign-in and connection has been completed.</span></span>
2. <span data-ttu-id="7cc52-175">Entre no centro de segurança do Microsoft 365 como este usuário e siga as etapas de configuração.</span><span class="sxs-lookup"><span data-stu-id="7cc52-175">Sign in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="7cc52-176">Filtragem de IP</span><span class="sxs-lookup"><span data-stu-id="7cc52-176">IP filtering</span></span>

<span data-ttu-id="7cc52-177">Se você habilitou a filtragem de IP, talvez seja necessário permitir explicitamente endereços IP.</span><span class="sxs-lookup"><span data-stu-id="7cc52-177">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="7cc52-178">Consulte [controle de acesso de endereço IP](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) para obter informações sobre como permitir intervalos IP no ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="7cc52-178">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="7cc52-179">Consulte [Azure IP Ranges and Service Tags-Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) para obter uma lista de endereços IP para permitir.</span><span class="sxs-lookup"><span data-stu-id="7cc52-179">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="7cc52-180">A instalação está concluída, mas não vê tíquetes e não pode ser compartilhada</span><span class="sxs-lookup"><span data-stu-id="7cc52-180">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="7cc52-181">Se as etapas de instalação e configuração tiverem sido concluídas, mas você não vir os cartões do ServiceNow na Home Page e não puder compartilhar o ServiceNow pela pontuação segura da Microsoft, verifique o status da página de provisionamento em https://security.microsoft.com/ticketProvisioning .</span><span class="sxs-lookup"><span data-stu-id="7cc52-181">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="7cc52-182">Selecione **autorizar** e retornar para a página inicial.</span><span class="sxs-lookup"><span data-stu-id="7cc52-182">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="7cc52-183">Os cartões devem ser exibidos.</span><span class="sxs-lookup"><span data-stu-id="7cc52-183">The cards should appear.</span></span>

## <a name="resources"></a><span data-ttu-id="7cc52-184">Recursos</span><span class="sxs-lookup"><span data-stu-id="7cc52-184">Resources</span></span>

- [<span data-ttu-id="7cc52-185">Gerenciar tíquetes do ServiceNow na central de segurança</span><span class="sxs-lookup"><span data-stu-id="7cc52-185">Manage ServiceNow tickets in the security center</span></span>](tickets-security-center.md)
