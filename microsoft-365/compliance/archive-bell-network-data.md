---
title: Configurar um conector para arquivar dados de rede SMS/MMS da Bell
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Os administradores podem configurar um conector de Telemensagem para importar e arquivar dados SMS e MMS da rede Bell. Isso permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: df89ff9e078ef8439ddc8258de5cf5dfc88c6450
ms.sourcegitcommit: d39694d7b2c98350b0d568dfd03fa0ef44ed4c1d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "46602110"
---
# <a name="set-up-a-connector-to-archive-bell-network-data-preview"></a><span data-ttu-id="d2aa4-104">Configurar um conector para arquivar dados de rede Bell (visualização)</span><span class="sxs-lookup"><span data-stu-id="d2aa4-104">Set up a connector to archive Bell Network data (preview)</span></span>

<span data-ttu-id="d2aa4-105">Use um conector de Telemensagem no centro de conformidade da Microsoft 365 para importar e arquivar mensagens de serviço de mensagens curtas (SMS) e Multimedia Messaging Service (MMS) da rede Bell.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-105">Use a TeleMessage connector in the Microsoft 365 compliance center to import and archive Short Messaging Service (SMS) and Multimedia Messaging Service (MMS) messages from the Bell Network.</span></span> <span data-ttu-id="d2aa4-106">Depois de configurar e configurar um conector, ele se conecta à rede de Bell da sua organização uma vez por dia e importa as mensagens SMS e MMS para caixas de correio no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-106">After you set up and configure a connector, it connects to your organization's Bell Network once every day, and imports SMS and MMS messages to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="d2aa4-107">Depois que as mensagens SMS e MMS são armazenadas nas caixas de correio do usuário, você pode aplicar recursos de conformidade do Microsoft 365, como retenção de litígio, pesquisa de conteúdo e políticas de retenção da Microsoft 365 para Bell dados de rede.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-107">After the SMS and MMS messages are stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, and Microsoft 365 retention policies to Bell Network data.</span></span> <span data-ttu-id="d2aa4-108">Por exemplo, você pode pesquisar a rede de Bell SMS/MMS usando a pesquisa de conteúdo ou associar a caixa de correio que contém os dados do Bell Network Connector com um funcionário em uma caixa de descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-108">For example, you can search Bell Network SMS/MMS using Content Search or associate the mailbox that contains the Bell Network connector data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="d2aa4-109">O uso de um conector de rede Bell para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a se manter em conformidade com as políticas governamentais e regulamentares.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-109">Using a Bell Network connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-bell-network-data"></a><span data-ttu-id="d2aa4-110">Visão geral do arquivamento de dados de rede Bell</span><span class="sxs-lookup"><span data-stu-id="d2aa4-110">Overview of archiving Bell Network data</span></span>

<span data-ttu-id="d2aa4-111">A visão geral a seguir explica o processo de usar um conector para arquivar dados de rede Bell no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-111">The following overview explains the process of using a connector to archive Bell Network data in Microsoft 365.</span></span>

![Fluxo de trabalho de arquivamento de rede Bell](../media/BellNetworkConnectorWorkflow.png)

1. <span data-ttu-id="d2aa4-113">Sua organização funciona com telemessage e Bell para configurar um conector de rede Bell.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-113">Your organization works with TeleMessage and Bell to set up a Bell Network connector.</span></span> <span data-ttu-id="d2aa4-114">Para obter mais informações, consulte [Bell Network archiverr](https://www.telemessage.com/office365-activation-for-bell-network-archiver).</span><span class="sxs-lookup"><span data-stu-id="d2aa4-114">For more information, see [Bell Network Archiver](https://www.telemessage.com/office365-activation-for-bell-network-archiver).</span></span>

2. <span data-ttu-id="d2aa4-115">Uma vez a cada 24 horas, as mensagens SMS e MMS da rede de Bell da sua organização são copiadas para o site de Telemensagem.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-115">Once every 24 hours, SMS and MMS messages from your organization’s Bell Network are copied to the TeleMessage site.</span></span>

3. <span data-ttu-id="d2aa4-116">O conector de rede Bell que você cria no centro de conformidade da Microsoft 365 se conecta ao site de Telemensagem todos os dias e transfere as mensagens SMS e MMS das últimas 24 horas para um local seguro de armazenamento do Azure na nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-116">The Bell Network connector that you create in the Microsoft 365 compliance center connects to the TeleMessage site every day and transfers the SMS and MMS messages from the previous 24 hours to a secure Azure Storage location in the Microsoft Cloud.</span></span> <span data-ttu-id="d2aa4-117">O conector também converte o conteúdo de mensagens SMS e MMS em um formato de mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-117">The connector also converts the content of SMS and MMS messages to an email message format.</span></span>

4. <span data-ttu-id="d2aa4-118">O conector importa os itens de comunicação móvel para a caixa de correio de usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-118">The connector imports the mobile communication items to the mailbox of specific users.</span></span> <span data-ttu-id="d2aa4-119">Uma nova pasta chamada **Bell SMS/MMS Network Archiver** é criada na caixa de correio de um usuário específico e os itens são importados para ela.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-119">A new folder named **Bell SMS/MMS Network Archiver** is created in a specific user's mailbox and the items are imported to it.</span></span> <span data-ttu-id="d2aa4-120">O conector faz esse mapeamento usando o valor da propriedade de *endereço de email do usuário* .</span><span class="sxs-lookup"><span data-stu-id="d2aa4-120">The connector does this mapping by using the value of the *User’s Email address* property.</span></span> <span data-ttu-id="d2aa4-121">Cada mensagem SMS e MMS contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-121">Every SMS and MMS message contains this property, which is populated with the email address of every participant of the message.</span></span>

   <span data-ttu-id="d2aa4-122">Além do mapeamento automático de usuários usando o valor da propriedade de *endereço de email do usuário* , você também pode definir um mapeamento personalizado carregando um arquivo de mapeamento CSV.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-122">In addition to automatic user mapping using the value of the *User’s Email address* property, you can also define a custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="d2aa4-123">Este arquivo de mapeamento contém o número de telefone celular e o endereço de email correspondente do Microsoft 365 para usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-123">This mapping file contains the mobile phone number and corresponding Microsoft 365 email address for users in your organization.</span></span> <span data-ttu-id="d2aa4-124">Se você habilitar o mapeamento de usuário automático e o mapeamento personalizado, para cada item de rede Bell, o conector procurará primeiro no arquivo de mapeamento personalizado.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-124">If you enable both automatic user mapping and custom mapping, for every Bell Network item the connector first looks at custom mapping file.</span></span> <span data-ttu-id="d2aa4-125">Se não encontrar um usuário válido do Microsoft 365 que corresponda ao número de telefone celular de um usuário, o conector usará os valores na propriedade de endereço de email do item que está tentando importar.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-125">If it doesn't find a valid Microsoft 365 user that corresponds to a user's mobile phone number, the connector will use the values in the email address property of the item it's trying to import.</span></span> <span data-ttu-id="d2aa4-126">Se o conector não localizar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade de endereço de email do item de rede Bell, o item não será importado.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-126">If the connector doesn't find a valid Microsoft 365 user in either the custom mapping file or in the email address property of the Bell Network item, the item won't be imported.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d2aa4-127">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="d2aa4-127">Before you begin</span></span>

<span data-ttu-id="d2aa4-128">Muitas das etapas de implementação necessárias para arquivar dados de rede Bell são externas para o Microsoft 365 e devem ser concluídas para que você possa criar um conector no centro de conformidade.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-128">Many of the implementation steps required to archive Bell Network data are external to Microsoft 365 and must be completed before you can create a connector in the compliance center.</span></span>

- <span data-ttu-id="d2aa4-129">Solicite o [serviço de arquivador de rede Bell de Telemensagem](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) e obtenha uma conta de administração válida para sua organização.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-129">Order the [Bell Network Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) and get a valid administration account for your organization.</span></span> <span data-ttu-id="d2aa4-130">Você precisará entrar nessa conta quando criar o conector no centro de conformidade.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-130">You'll need to sign into this account when you create the connector in the compliance center.</span></span>

- <span data-ttu-id="d2aa4-131">Obtenha os detalhes do contato de facturação e conta de rede da Bell para que você possa preencher os formulários de integração de Telemensagem e solicitar o serviço de arquivamento de mensagens de Bell.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-131">Obtain your Bell Network account and billing contact details so you can fill-out the TeleMessage onboarding forms and order the message archiving service from Bell.</span></span>

- <span data-ttu-id="d2aa4-132">Registre todos os usuários que exigem o arquivamento de rede SMS/MMS de Bell na conta de Telemensagem.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-132">Register all users that require Bell SMS/MMS Network archiving in the TeleMessage account.</span></span> <span data-ttu-id="d2aa4-133">Ao registrar usuários, certifique-se de usar o mesmo endereço de email usado para a conta do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-133">When registering users, be sure to use the same email address that's used for their Microsoft 365 account.</span></span>

- <span data-ttu-id="d2aa4-134">Seus funcionários devem ter telefones celulares de propriedade corporativa e responsáveis corporativos na rede móvel Bell.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-134">Your employees must have corporate-owned and corporate-liable mobile phones on the Bell mobile network.</span></span> <span data-ttu-id="d2aa4-135">O arquivamento de mensagens no Microsoft 365 não está disponível para funcionários de propriedade ou "Traga seus próprios dispositivos (BYOD).</span><span class="sxs-lookup"><span data-stu-id="d2aa4-135">Archiving messages in Microsoft 365 isn't available for employee-owned or "Bring Your Own Devices (BYOD) devices.</span></span>

- <span data-ttu-id="d2aa4-136">Sua organização deve dar o consentimento para permitir que o serviço de importação do Office 365 acesse dados de caixa de correio em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-136">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="d2aa4-137">Você precisará fornecer esse consentimento ao criar o conector.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-137">You will need to provide this consent when you create the connector.</span></span> <span data-ttu-id="d2aa4-138">Para concordar com essa solicitação, [acesse esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), entre com as credenciais de um administrador global do Office 365 e aceite a solicitação.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-138">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of an Office 365 global admin, and then accept the request.</span></span> <span data-ttu-id="d2aa4-139">Você precisa concluir esta etapa para poder criar um conector de rede Bell com êxito.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-139">You have to complete this step before you can successfully create a Bell Network connector.</span></span>

- <span data-ttu-id="d2aa4-140">O usuário que cria um conector de rede Bell deve ser atribuído à função de exportação de importação de caixa de correio no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-140">The user who creates a Bell Network connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="d2aa4-141">Isso é necessário para adicionar conectores na página **conectores de dados** no centro de conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-141">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="d2aa4-142">Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-142">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="d2aa4-143">Você pode adicionar a função de exportação de importação de caixa de correio ao grupo de funções Gerenciamento da organização no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-143">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="d2aa4-144">Ou você pode criar um grupo de função, atribua a função de exportação de importação de caixa de correio e, em seguida, adicione os usuários apropriados como membros.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-144">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="d2aa4-145">Para obter mais informações, consulte as seções [criar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) ou [modificar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) no artigo "gerenciar grupos de função no Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="d2aa4-145">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="create-a-bell-network-connector"></a><span data-ttu-id="d2aa4-146">Criar um conector de rede Bell</span><span class="sxs-lookup"><span data-stu-id="d2aa4-146">Create a Bell Network connector</span></span>

<span data-ttu-id="d2aa4-147">A última etapa é criar um conector de rede Bell no centro de conformidade da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-147">The last step is to create a Bell Network connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="d2aa4-148">O conector usa as informações que você fornece para se conectar ao site de Telemensagem e transferir mensagens SMS/MMS para as caixas de caixa de correio de usuário correspondentes no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-148">The connector uses the information you provide to connect to the TeleMessage site and transfer SMS/ MMS messages to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="d2aa4-149">Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **conectores de dados**  >  **Bell SMS/MMS Network Archiver**.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-149">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** > **Bell SMS/MMS Network Archiver**.</span></span>

2. <span data-ttu-id="d2aa4-150">Na página de descrição do produto de **rede Bell** , clique em **Adicionar conector**</span><span class="sxs-lookup"><span data-stu-id="d2aa4-150">On the **Bell Network** product description page, click **Add connector**</span></span>

3. <span data-ttu-id="d2aa4-151">Na página **termos de serviço** , clique em **aceitar**.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-151">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="d2aa4-152">Na página **logon na Telemensagem** , em etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-152">On the **Login to TeleMessage** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

   - <span data-ttu-id="d2aa4-153">**Nome de usuário:** O nome de usuário de sua mensagem.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-153">**Username:** Your TeleMessage username.</span></span>

   - <span data-ttu-id="d2aa4-154">**Senha:** Sua senha de Telemensagem.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-154">**Password:** Your TeleMessage password.</span></span>

5. <span data-ttu-id="d2aa4-155">Depois que o conector é criado, você pode fechar a janela pop-up e ir para a próxima página.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-155">After the connector is created, you can close the pop-up window and go to the next page.</span></span>

6. <span data-ttu-id="d2aa4-156">Na página **mapeamento de usuário** , habilite o mapeamento de usuário automático.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-156">On the **User mapping** page, enable automatic user mapping.</span></span> <span data-ttu-id="d2aa4-157">Para habilitar o mapeamento personalizado, carregue um arquivo CSV que contenha as informações de mapeamento do usuário e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-157">To enable custom mapping, upload a CSV file that contains the user mapping information, and then click **Next**.</span></span>

7. <span data-ttu-id="d2aa4-158">Forneça o consentimento do administrador e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-158">Provide admin consent and then click **Next**.</span></span>

   <span data-ttu-id="d2aa4-159">Para fornecer o consentimento do administrador, você deve estar conectado com as credenciais de um administrador global do Office 365 e aceitar a solicitação de consentimento.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-159">To provide admin consent, you must be signed in with the credentials of an Office 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="d2aa4-160">Se você não estiver conectado como um administrador global, poderá ir para [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e entrar usando credenciais de administrador global para aceitar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-160">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign-in using global admin credentials to accept the request.</span></span>

8. <span data-ttu-id="d2aa4-161">Revise suas configurações e clique em **concluir** para criar o conector.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-161">Review your settings, and then click **Finish** to create the connector.</span></span>

9. <span data-ttu-id="d2aa4-162">Vá até a guia **conectores** na página **conectores de dados** no centro de conformidade para ver o andamento do processo de importação para o novo conector.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-162">Go to the **Connectors** tab on the **Data connectors** page in the compliance center to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="d2aa4-163">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="d2aa4-163">Known issues</span></span>

- <span data-ttu-id="d2aa4-164">O conector não importa nenhum item com mais de 10 MB.</span><span class="sxs-lookup"><span data-stu-id="d2aa4-164">The connector doesn’t import any item larger than 10 MB.</span></span>