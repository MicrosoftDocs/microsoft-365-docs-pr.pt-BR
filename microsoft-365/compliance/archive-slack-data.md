---
title: Configurar um conector para arquivar dados de margem de atraso no Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Os administradores podem configurar um conector para importar e arquivar dados da margem de atraso do Globanet no Microsoft 365. Esse conector permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: 6466beb6115037ff726b1e5fd3350032bceb2230
ms.sourcegitcommit: a3c2c737995088c1bad3b12ab401a7ef242b0272
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47957026"
---
# <a name="set-up-a-connector-to-archive-slack-data-preview"></a><span data-ttu-id="8c79c-104">Configurar um conector para arquivar dados de margem de atraso (visualização)</span><span class="sxs-lookup"><span data-stu-id="8c79c-104">Set up a connector to archive Slack data (preview)</span></span>

<span data-ttu-id="8c79c-105">Use um conector Globanet no centro de conformidade da Microsoft 365 para importar e arquivar dados de terceiros de mídia social, mensagens instantâneas e plataformas de colaboração de documentos para caixas de correio em sua organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8c79c-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive third-party data from social media, instant messaging, and document collaboration platforms to mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="8c79c-106">O Globanet fornece um conector de [conector de dados de margem de atraso](https://globanet.com/slack/) no centro de conformidade da Microsoft 365 que você pode configurar para capturar itens da fonte de dados de terceiros (regularmente) e importar esses itens para a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8c79c-106">Globanet provides a [Slack data connector](https://globanet.com/slack/) connector in the Microsoft 365 compliance center that you can configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="8c79c-107">A margem de atraso extrai mensagens e arquivos da API de margem de atraso e converte-os em um formato de mensagens de email e os importa para caixas de correio do usuário no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8c79c-107">Slack pulls messages and files from the Slack API and converts them an email messages format and then imports them to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="8c79c-108">Após os dados da margem de atraso serem armazenados nas caixas de correio do usuário, você pode aplicar recursos de conformidade do Microsoft 365, como retenção de litígio, descoberta eletrônica, políticas de retenção e rótulos de retenção e conformidade de comunicação.</span><span class="sxs-lookup"><span data-stu-id="8c79c-108">After Slack data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="8c79c-109">O uso de um conector de margem de atraso para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a se manter em conformidade com as políticas governamentais e regulamentares.</span><span class="sxs-lookup"><span data-stu-id="8c79c-109">Using a Slack connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-slack-data"></a><span data-ttu-id="8c79c-110">Visão geral do arquivamento de dados de margem de atraso</span><span class="sxs-lookup"><span data-stu-id="8c79c-110">Overview of archiving Slack data</span></span>

<span data-ttu-id="8c79c-111">A visão geral a seguir explica o processo de usar um conector para arquivar as informações de margem de atraso no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8c79c-111">The following overview explains the process of using a connector to archive the Slack information in Microsoft 365.</span></span>

![Trabalho de arquivamento de margem de atraso](../media/SlackConnectorWorkflow.png)

1. <span data-ttu-id="8c79c-113">Sua organização trabalha com a margem de atraso para configurar e configurar um site de margem de atraso.</span><span class="sxs-lookup"><span data-stu-id="8c79c-113">Your organization works with Slack to set up and configure a Slack site.</span></span>

2. <span data-ttu-id="8c79c-114">Uma vez a cada 24 horas, as mensagens de chat da margem de atraso são copiadas para o site do Globanet Merge1.</span><span class="sxs-lookup"><span data-stu-id="8c79c-114">Once every 24 hours, chat messages from Slack are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="8c79c-115">O conector também converte o conteúdo de uma mensagem de chat em um formato de mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="8c79c-115">The connector also converts the content of a chat message to an email message format.</span></span>

3. <span data-ttu-id="8c79c-116">O conector de margem de atraso que você cria no centro de conformidade da Microsoft 365, conecta-se ao site do Globanet Merge1 todos os dias e transfere as mensagens de chat para um local seguro de armazenamento do Azure na nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8c79c-116">The Slack connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the chat messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="8c79c-117">O conector importa os itens de mensagem de chat convertidos para as caixas de correio de usuários específicos usando o valor da propriedade *email* e o mapeamento de usuário automático, conforme descrito na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="8c79c-117">The connector imports the converted chat message items to the mailboxes of specific users using the value of the *Email* property and automatic user mapping, as described in Step 3.</span></span> <span data-ttu-id="8c79c-118">Uma nova subpasta na pasta caixa de entrada chamada **margem de atraso** é criada nas caixas de correio do usuário e os itens da mensagem de chat serão importados para essa pasta.</span><span class="sxs-lookup"><span data-stu-id="8c79c-118">A new subfolder in the Inbox folder named **Slack** is created in the user mailboxes, and the chat message items will be imported to that folder.</span></span> <span data-ttu-id="8c79c-119">O conector faz isso usando o valor da propriedade *email* .</span><span class="sxs-lookup"><span data-stu-id="8c79c-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="8c79c-120">Cada mensagem de chat contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem de chat.</span><span class="sxs-lookup"><span data-stu-id="8c79c-120">Every chat message contains this property, which is populated with the email address of every participant of the chat message.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8c79c-121">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="8c79c-121">Before you begin</span></span>

- <span data-ttu-id="8c79c-122">Crie uma conta do Merge1 do Globanet para conectores da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8c79c-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="8c79c-123">Para fazer isso, entre em contato com o [suporte ao cliente Globanet](https://globanet.com/ms-connectors-contact).</span><span class="sxs-lookup"><span data-stu-id="8c79c-123">To do this, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="8c79c-124">Você precisa entrar nessa conta ao criar o conector na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="8c79c-124">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="8c79c-125">Obtenha o nome de usuário e a senha para a conta de margem de atraso da sua organização.</span><span class="sxs-lookup"><span data-stu-id="8c79c-125">Obtain the username and password for your organization's Slack enterprise account.</span></span> <span data-ttu-id="8c79c-126">Você precisará entrar nessa conta na etapa 2 ao configurar a margem de atraso.</span><span class="sxs-lookup"><span data-stu-id="8c79c-126">You'll need to sign into this account in Step 2 when you configure Slack.</span></span>

- <span data-ttu-id="8c79c-127">O usuário que cria o conector de margem de atraso na etapa 1 (e conclui-lo na etapa 3) deve ser atribuído à função de exportação de importação de caixa de correio no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8c79c-127">The user who creates the Slack connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="8c79c-128">Essa função é necessária para adicionar conectores na página **conectores de dados** no centro de conformidade da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8c79c-128">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="8c79c-129">Por padrão, essa função não é atribuída a nenhum grupo de função no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8c79c-129">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="8c79c-130">Você pode adicionar a função de exportação de importação de caixa de correio ao grupo de funções Gerenciamento da organização no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8c79c-130">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="8c79c-131">Ou você pode criar um grupo de função, atribua a função de exportação de importação de caixa de correio e, em seguida, adicione os usuários apropriados como membros.</span><span class="sxs-lookup"><span data-stu-id="8c79c-131">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="8c79c-132">Para obter mais informações, consulte as seções [criar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) ou [modificar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) no artigo "gerenciar grupos de função no Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="8c79c-132">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-slack-connector"></a><span data-ttu-id="8c79c-133">Etapa 1: configurar o conector de margem de atraso</span><span class="sxs-lookup"><span data-stu-id="8c79c-133">Step 1: Set up the Slack connector</span></span>

<span data-ttu-id="8c79c-134">A primeira etapa é acessar a página **conectores de dados** no centro de conformidade da Microsoft 365 e criar um conector para dados de margem de atraso.</span><span class="sxs-lookup"><span data-stu-id="8c79c-134">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Slack data.</span></span>

1. <span data-ttu-id="8c79c-135">Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em margem de atraso dos **conectores de dados**  >  **Slack**.</span><span class="sxs-lookup"><span data-stu-id="8c79c-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Slack**.</span></span>

2. <span data-ttu-id="8c79c-136">Na página descrição da **margem de atraso** do produto, clique em **Adicionar conector**.</span><span class="sxs-lookup"><span data-stu-id="8c79c-136">On the **Slack** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="8c79c-137">Na página **termos de serviço** , clique em **aceitar**.</span><span class="sxs-lookup"><span data-stu-id="8c79c-137">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="8c79c-138">Insira um nome exclusivo que identifique o conector e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8c79c-138">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="8c79c-139">Entre em sua conta do Merge1 para configurar o conector.</span><span class="sxs-lookup"><span data-stu-id="8c79c-139">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-slack"></a><span data-ttu-id="8c79c-140">Etapa 2: configurar a margem de atraso</span><span class="sxs-lookup"><span data-stu-id="8c79c-140">Step 2: Configure Slack</span></span>

<span data-ttu-id="8c79c-141">A segunda etapa é configurar o conector de margem de atraso no site do Merge1.</span><span class="sxs-lookup"><span data-stu-id="8c79c-141">The second step is to configure the Slack connector on the Merge1 site.</span></span> <span data-ttu-id="8c79c-142">Para obter mais informações sobre como configurar o conector de margem de atraso no site do Globanet Merge1, consulte [Merge1 de terceiros conectores do usuário](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf).</span><span class="sxs-lookup"><span data-stu-id="8c79c-142">For more information about how to configure the Slack connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf).</span></span>

<span data-ttu-id="8c79c-143">Após clicar em **salvar & concluir**, você será direcionado para o centro de conformidade da Microsoft 365, para a página **mapeamento de usuário** no assistente de conector.</span><span class="sxs-lookup"><span data-stu-id="8c79c-143">After you click **Save & Finish**, you are directed back to the Microsoft 365 compliance center, to the **User mapping** page in the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="8c79c-144">Etapa 3: mapear usuários e concluir a configuração do conector</span><span class="sxs-lookup"><span data-stu-id="8c79c-144">Step 3: Map users and complete the connector setup</span></span>

1. <span data-ttu-id="8c79c-145">Na página **mapear usuários externos para usuários do Microsoft 365** , habilite o mapeamento automático do usuário.</span><span class="sxs-lookup"><span data-stu-id="8c79c-145">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span>

   <span data-ttu-id="8c79c-146">Os itens de margem de atraso incluem uma propriedade chamada *email*, que contém endereços de email para usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="8c79c-146">Slack items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="8c79c-147">Se o conector puder associar esse endereço a um usuário do Microsoft 365, os itens serão importados para a caixa de correio desse usuário.</span><span class="sxs-lookup"><span data-stu-id="8c79c-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="8c79c-148">Na página **consentimento do administrador** , clique no botão **fornecer consentimento** .</span><span class="sxs-lookup"><span data-stu-id="8c79c-148">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="8c79c-149">Você será redirecionado para o site da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8c79c-149">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="8c79c-150">Clique em **aceitar** para fornecer o consentimento.</span><span class="sxs-lookup"><span data-stu-id="8c79c-150">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="8c79c-151">Sua organização deve dar o consentimento para permitir que o serviço de importação do Office 365 acesse dados de caixa de correio em sua organização.</span><span class="sxs-lookup"><span data-stu-id="8c79c-151">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="8c79c-152">Para fornecer o consentimento do administrador, você deve estar conectado com as credenciais de um administrador global do Microsoft 365 e aceitar a solicitação de consentimento.</span><span class="sxs-lookup"><span data-stu-id="8c79c-152">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="8c79c-153">Se você não estiver conectado como um administrador global, poderá ir para [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e entrar usando as credenciais de administrador global para aceitar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="8c79c-153">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="8c79c-154">Clique em **Avançar**, revise suas configurações e vá para a página **conectores de dados** para ver o andamento do processo de importação para o novo conector.</span><span class="sxs-lookup"><span data-stu-id="8c79c-154">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-slack-connector"></a><span data-ttu-id="8c79c-155">Etapa 4: monitorar o conector de margem de atraso</span><span class="sxs-lookup"><span data-stu-id="8c79c-155">Step 4: Monitor the Slack connector</span></span>

<span data-ttu-id="8c79c-156">Depois de criar o conector de margem de atraso, você pode visualizar o status do conector no centro de conformidade da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8c79c-156">After you create the Slack connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="8c79c-157">Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **conectores de dados** no painel de navegação esquerdo.</span><span class="sxs-lookup"><span data-stu-id="8c79c-157">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="8c79c-158">Clique na guia **conectores** e selecione o conector **margem de atraso** para exibir a página de submenu, que contém as propriedades e informações sobre o conector.</span><span class="sxs-lookup"><span data-stu-id="8c79c-158">Click the **Connectors** tab and then select the **Slack** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="8c79c-159">Em **status do conector com origem**, clique no link **baixar log** para abrir (ou salvar) o log de status do conector.</span><span class="sxs-lookup"><span data-stu-id="8c79c-159">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="8c79c-160">Esse log contém informações sobre os dados que foram importados para a nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8c79c-160">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="8c79c-161">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="8c79c-161">Known issues</span></span>

- <span data-ttu-id="8c79c-162">No momento, não há suporte para a importação de anexos e itens com mais de 10 MB.</span><span class="sxs-lookup"><span data-stu-id="8c79c-162">At this time, we don't support importing attachments and items that are larger than 10 MB.</span></span> <span data-ttu-id="8c79c-163">O suporte para itens maiores estará disponível em uma data posterior.</span><span class="sxs-lookup"><span data-stu-id="8c79c-163">Support for larger items will be available at a later date.</span></span>