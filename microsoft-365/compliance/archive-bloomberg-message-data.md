---
title: Configurar um conector para arquivar dados de mensagem do Bloomberg
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
description: Os administradores podem configurar um conector de dados para importar e arquivar dados da ferramenta de email de mensagem do Bloomberg para o Microsoft 365. Isso permite que você arquive dados de fontes de dados de terceiros no Microsoft 365 para que possa usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar os dados de terceiros da sua organização.
ms.openlocfilehash: 700a0619d2299fc7254628059787478cc0e168fa
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44937318"
---
# <a name="set-up-a-connector-to-archive-bloomberg-message-data-preview"></a><span data-ttu-id="ac586-104">Configurar um conector para arquivar dados de mensagem do Bloomberg (visualização)</span><span class="sxs-lookup"><span data-stu-id="ac586-104">Set up a connector to archive Bloomberg Message data (preview)</span></span>

<span data-ttu-id="ac586-105">Use um conector de dados no centro de conformidade da Microsoft 365 para importar e arquivar dados de email de serviços financeiros da ferramenta de colaboração de [mensagens do Bloomberg](https://www.bloomberg.com/professional/product/collaboration/) .</span><span class="sxs-lookup"><span data-stu-id="ac586-105">Use a data connector in the Microsoft 365 compliance center to import and archive financial services email data from the [Bloomberg Message](https://www.bloomberg.com/professional/product/collaboration/) collaboration tool.</span></span> <span data-ttu-id="ac586-106">Depois de configurar e configurar um conector, ele se conecta ao site do Bloomberg Secure FTP (SFTP) de sua organização uma vez a cada dia e importa itens de email para caixas de correio no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac586-106">After you set up and configure a connector, it connects to your organization's Bloomberg secure FTP (SFTP) site once every day, and imports email items to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="ac586-107">Depois que o Bloomberg Message data é armazenado nas caixas de correio do usuário, você pode aplicar recursos de conformidade do Microsoft 365, como retenção de litígio, pesquisa de conteúdo, arquivamento in-loco, auditoria, conformidade de comunicação e políticas de retenção da Microsoft 365 para dados de mensagem do Bloomberg.</span><span class="sxs-lookup"><span data-stu-id="ac586-107">After Bloomberg Message data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation hold, content search, In-place archiving, auditing, Communication compliance, and Microsoft 365 retention policies to Bloomberg Message data.</span></span> <span data-ttu-id="ac586-108">Por exemplo, você pode pesquisar emails de mensagens do Bloomberg usando a ferramenta de pesquisa de conteúdo ou associar a caixa de correio que contém os dados de mensagem do Bloomberg a um funcionário em uma caixa de descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="ac586-108">For example, you can search Bloomberg Message emails using the content search tool or associate the mailbox that contains the Bloomberg Message data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="ac586-109">O uso de um conector de mensagens do Bloomberg para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a se manter em conformidade com as políticas governamentais e regulamentares.</span><span class="sxs-lookup"><span data-stu-id="ac586-109">Using a Bloomberg Message connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-bloomberg-message-data"></a><span data-ttu-id="ac586-110">Visão geral do arquivamento de dados de mensagem do Bloomberg</span><span class="sxs-lookup"><span data-stu-id="ac586-110">Overview of archiving Bloomberg Message data</span></span>

<span data-ttu-id="ac586-111">A visão geral a seguir explica o processo de usar um conector para arquivar dados de mensagem do Bloomberg no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac586-111">The following overview explains the process of using a connector to archive Bloomberg Message data in Microsoft 365.</span></span>

![Processo de importação e arquivamento de mensagens do Bloomberg](../media/BloombergMessageArchiving.png)

1. <span data-ttu-id="ac586-113">Sua organização trabalha com o Bloomberg para configurar um site do Bloomberg SFTP.</span><span class="sxs-lookup"><span data-stu-id="ac586-113">Your organization works with Bloomberg to set up a Bloomberg SFTP site.</span></span> <span data-ttu-id="ac586-114">Você também trabalhará com o Bloomberg para configurar o Bloomberg para copiar mensagens de email no site do Bloomberg SFTP.</span><span class="sxs-lookup"><span data-stu-id="ac586-114">You'll also work with Bloomberg to configure Bloomberg Message to copy email messages to the Bloomberg SFTP site.</span></span>

2. <span data-ttu-id="ac586-115">Uma vez a cada 24 horas, as mensagens de email da mensagem do Bloomberg são copiadas para o site Bloomberg SFTP.</span><span class="sxs-lookup"><span data-stu-id="ac586-115">Once every 24 hours, email messages from Bloomberg Message are copied to the Bloomberg SFTP site.</span></span>

3. <span data-ttu-id="ac586-116">O conector de mensagens do Bloomberg que você cria no centro de conformidade da Microsoft 365 conecta-se ao site do Bloomberg SFTP todos os dias e transfere as mensagens de email das últimas 24 horas para uma área de armazenamento do Azure segura na nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ac586-116">The Bloomberg Message connector that you create in the Microsoft 365 compliance center connects to the Bloomberg SFTP site every day and transfers the email messages from the previous 24 hours to a secure Azure Storage area in the Microsoft Cloud.</span></span>

4. <span data-ttu-id="ac586-117">O conector importa os itens de mensagem de email para a caixa de correio de um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="ac586-117">The connector imports the email message items to the mailbox of a specific user.</span></span> <span data-ttu-id="ac586-118">Uma nova pasta chamada BloombergMessage será criada na caixa de correio do usuário específico e os itens serão importados para ela.</span><span class="sxs-lookup"><span data-stu-id="ac586-118">A new folder named BloombergMessage will be created in the specific user's mailbox and the items will be imported to it.</span></span> 

   <span data-ttu-id="ac586-119">O conector faz isso usando o valor da propriedade CorporateEmailAddress.</span><span class="sxs-lookup"><span data-stu-id="ac586-119">The connector does this by using the value of the CorporateEmailAddress property.</span></span> <span data-ttu-id="ac586-120">Cada mensagem de email contém essa propriedade, que é preenchida com o endereço de email de cada participante da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="ac586-120">Every email message contains this property, which is populated with the email address of every participant of the email message.</span></span> <span data-ttu-id="ac586-121">Além do mapeamento automático de usuários usando o valor da propriedade *CorporateEmailAddress* , você também pode definir um mapeamento personalizado carregando um arquivo de mapeamento CSV.</span><span class="sxs-lookup"><span data-stu-id="ac586-121">In addition to automatic user mapping using the value of the *CorporateEmailAddress* property, you can also define a custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="ac586-122">Este arquivo de mapeamento contém um Bloomberg UUID e o endereço de caixa de correio do Microsoft 365 correspondente para cada usuário da sua organização.</span><span class="sxs-lookup"><span data-stu-id="ac586-122">This mapping file contains a Bloomberg UUID and the corresponding Microsoft 365 mailbox address for each user in your organization.</span></span> <span data-ttu-id="ac586-123">Se você habilitar o mapeamento automático de usuários e fornecer um mapeamento personalizado, para cada item de email, o conector examinará primeiro o arquivo de mapeamento personalizado.</span><span class="sxs-lookup"><span data-stu-id="ac586-123">If you enable automatic user mapping and provide a custom mapping, for every email item the connector will first look at the custom-mapping file.</span></span> <span data-ttu-id="ac586-124">Se não encontrar um usuário válido do Microsoft 365 que corresponda ao UUID do Bloomberg de um usuário, o conector usará a propriedade *CorporateEmailAddress* do item de email.</span><span class="sxs-lookup"><span data-stu-id="ac586-124">If it doesn't find a valid Microsoft 365 user that corresponds to a user's Bloomberg UUID, the connector uses the *CorporateEmailAddress* property of the email item.</span></span> <span data-ttu-id="ac586-125">Se o conector não localizar um usuário válido do Microsoft 365 no arquivo de mapeamento personalizado ou na propriedade *CorporateEmailAddress* do item de email, o item não será importado.</span><span class="sxs-lookup"><span data-stu-id="ac586-125">If the connector doesn't find a valid Microsoft 365 user in either the custom-mapping file or the *CorporateEmailAddress* property of the email item, the item won't be imported.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ac586-126">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="ac586-126">Before you begin</span></span>

<span data-ttu-id="ac586-127">Muitas das etapas de implementação necessárias para arquivar dados de mensagem do Bloomberg são externas para o Microsoft 365 e devem ser concluídas para que você possa criar o conector no centro de conformidade.</span><span class="sxs-lookup"><span data-stu-id="ac586-127">Many of the implementation steps required to archive Bloomberg Message data are external to Microsoft 365 and must be completed before you can create the connector in the compliance center.</span></span>

- <span data-ttu-id="ac586-128">Sua organização deve dar o consentimento para permitir que o serviço de importação do Office 365 acesse dados de caixa de correio em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ac586-128">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="ac586-129">Para concordar com essa solicitação, [acesse esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), entre com as credenciais de um administrador global do Office 365 e aceite a solicitação.</span><span class="sxs-lookup"><span data-stu-id="ac586-129">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of an Office 365 global admin, and then accept the request.</span></span> <span data-ttu-id="ac586-130">Você precisa concluir esta etapa para poder criar com êxito o conector de mensagens do Bloomberg na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="ac586-130">You have to complete this step before you can successfully create the Bloomberg Message connector in Step 3.</span></span>

- <span data-ttu-id="ac586-131">Inscreva-se no [Bloomberg em qualquer lugar](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA).</span><span class="sxs-lookup"><span data-stu-id="ac586-131">Subscribe to [Bloomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA).</span></span> <span data-ttu-id="ac586-132">Isso é necessário para que você possa fazer logon no Bloomberg em qualquer lugar para acessar o site do Bloomberg SFTP que você precisa configurar e configurar.</span><span class="sxs-lookup"><span data-stu-id="ac586-132">This is required so that you can log in to Bloomberg Anywhere to access the Bloomberg SFTP site that you have to set up and configure.</span></span>

- <span data-ttu-id="ac586-133">Configurar um site Bloomberg SFTP (protocolo de transferência segura de arquivos).</span><span class="sxs-lookup"><span data-stu-id="ac586-133">Set up a Bloomberg SFTP (Secure file transfer protocol) site.</span></span> <span data-ttu-id="ac586-134">Depois de trabalhar com o Bloomberg para configurar o site SFTP, os dados da mensagem do Bloomberg são carregados no site do SFTP todos os dias.</span><span class="sxs-lookup"><span data-stu-id="ac586-134">After working with Bloomberg to set up the SFTP site, data from Bloomberg Message is uploaded to the SFTP site every day.</span></span> <span data-ttu-id="ac586-135">O conector que você cria na etapa 2 se conecta a esse site SFTP e transfere os dados de email para caixas de correio do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac586-135">The connector you create in Step 2 connects to this SFTP site and transfers the email data to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="ac586-136">O SFTP também criptografa os dados de mensagem do Bloomberg que são enviados para caixas de correio durante o processo de transferência.</span><span class="sxs-lookup"><span data-stu-id="ac586-136">SFTP also encrypts the Bloomberg Message data that is sent to mailboxes during the transfer process.</span></span>

  <span data-ttu-id="ac586-137">Para obter informações sobre o Bloomberg SFTP (também chamado *de BB-SFTP*):</span><span class="sxs-lookup"><span data-stu-id="ac586-137">For information about Bloomberg SFTP (also called *BB-SFTP*):</span></span>

  - <span data-ttu-id="ac586-138">Consulte o documento "padrões de conectividade SFTP" no [suporte do Bloomberg](https://www.bloomberg.com/professional/support/documentation/).</span><span class="sxs-lookup"><span data-stu-id="ac586-138">See the "SFTP Connectivity Standards" document at [Bloomberg Support](https://www.bloomberg.com/professional/support/documentation/).</span></span>

  - <span data-ttu-id="ac586-139">Contatar o [suporte ao cliente do Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc).</span><span class="sxs-lookup"><span data-stu-id="ac586-139">Contact [Bloomberg customer support](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc).</span></span>

   > [!NOTE]
   > <span data-ttu-id="ac586-140">Se sua organização já implantou um conector para arquivar dados instantâneos do Bloomberg, você não precisa configurar outro site SFTP.</span><span class="sxs-lookup"><span data-stu-id="ac586-140">If your organization already deployed a connector to archive Instant Bloomberg data, you don't need to set up another SFTP site.</span></span> <span data-ttu-id="ac586-141">Você pode usar o mesmo site SFTP para o Bloomberg Message Connector.</span><span class="sxs-lookup"><span data-stu-id="ac586-141">You can use the same SFTP site for the Bloomberg Message connector.</span></span>

- <span data-ttu-id="ac586-142">Depois de trabalhar com o Bloomberg para configurar um site SFTP, o Bloomberg fornecerá algumas informações depois que você responder à mensagem de email de implementação do Bloomberg.</span><span class="sxs-lookup"><span data-stu-id="ac586-142">After you work with Bloomberg to set up an SFTP site, Bloomberg will provide some information to you after you respond to the Bloomberg implementation email message.</span></span> <span data-ttu-id="ac586-143">Salve uma cópia das informações a seguir.</span><span class="sxs-lookup"><span data-stu-id="ac586-143">Save a copy of the following information.</span></span> <span data-ttu-id="ac586-144">Você pode usá-lo para configurar um conector na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="ac586-144">You use it to set up a connector in Step 3.</span></span>

  - <span data-ttu-id="ac586-145">O código da empresa, que é uma ID da sua organização e é usado para fazer logon no site do Bloomberg SFTP.</span><span class="sxs-lookup"><span data-stu-id="ac586-145">Firm code, which is an ID for your organization and is used to log in to the Bloomberg SFTP site.</span></span>

  - <span data-ttu-id="ac586-146">Senha para seu site do Bloomberg SFTP</span><span class="sxs-lookup"><span data-stu-id="ac586-146">Password for your Bloomberg SFTP site</span></span>

  - <span data-ttu-id="ac586-147">URL para o site do Bloomberg SFTP (por exemplo, sftp.bloomberg.com).</span><span class="sxs-lookup"><span data-stu-id="ac586-147">URL for Bloomberg SFTP site (for example, sftp.bloomberg.com).</span></span> <span data-ttu-id="ac586-148">Além disso, o Bloomberg também pode fornecer um endereço IP correspondente para o site do Bloomberg SFTP, que também pode ser usado para configurar o conector.</span><span class="sxs-lookup"><span data-stu-id="ac586-148">In addition, Bloomberg may also provide a corresponding IP address for the Bloomberg SFTP site, which also can be used to set up the connector.</span></span>

  - <span data-ttu-id="ac586-149">Número de porta para o site Bloomberg SFTP</span><span class="sxs-lookup"><span data-stu-id="ac586-149">Port number for Bloomberg SFTP site</span></span>

- <span data-ttu-id="ac586-150">O usuário que cria um conector de mensagens do Bloomberg na etapa 3 (e quem baixa as chaves públicas e o endereço IP na etapa 1) deve receber a função de exportação de importação de caixa de correio no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ac586-150">The user who creates a Bloomberg Message connector in Step 3 (and who downloads the public keys and IP address in Step 1) must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="ac586-151">Isso é necessário para adicionar conectores na página **conectores de dados** no centro de conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac586-151">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="ac586-152">Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ac586-152">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="ac586-153">Você pode adicionar a função de exportação de importação de caixa de correio ao grupo de funções Gerenciamento da organização no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ac586-153">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="ac586-154">Ou você pode criar um grupo de função, atribua a função de exportação de importação de caixa de correio e, em seguida, adicione os usuários apropriados como membros.</span><span class="sxs-lookup"><span data-stu-id="ac586-154">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="ac586-155">Para obter mais informações, consulte as seções [criar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) ou [modificar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) no artigo "gerenciar grupos de função no Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="ac586-155">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>


## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a><span data-ttu-id="ac586-156">Etapa 1: obter as chaves públicas SSH e PGP</span><span class="sxs-lookup"><span data-stu-id="ac586-156">Step 1: Obtain SSH and PGP public keys</span></span>

<span data-ttu-id="ac586-157">A primeira etapa é obter uma cópia das chaves públicas para SSH (Secure Shell) e PGP (boa privacidade).</span><span class="sxs-lookup"><span data-stu-id="ac586-157">The first step is to obtain a copy of the public keys for Secure Shell (SSH) and Pretty Good Privacy (PGP).</span></span> <span data-ttu-id="ac586-158">Use essas chaves na etapa 2 para configurar o site do Bloomberg SFTP para permitir que o conector (que você criou na etapa 3) se conecte ao site SFTP e transfira os dados de email de mensagem do Bloomberg para as caixas de correio do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac586-158">You use these keys in Step 2 to configure the Bloomberg SFTP site to allow the connector (that you create in Step 3) to connect to the SFTP site and transfer the Bloomberg Message email data to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="ac586-159">Você também obtém um endereço IP nesta etapa, que você usa ao configurar o site do Bloomberg SFTP.</span><span class="sxs-lookup"><span data-stu-id="ac586-159">You also obtain an IP address in this step, which you use when configuring the Bloomberg SFTP site.</span></span>

1. <span data-ttu-id="ac586-160">Vá para [ https://compliance.microsoft.com\ ] ( https://compliance.microsoft.com) e clique em **conectores de dados** no painel de navegação esquerdo.</span><span class="sxs-lookup"><span data-stu-id="ac586-160">Go to [https://compliance.microsoft.com\](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="ac586-161">Na página **conectores de dados** sob **mensagem do Bloomberg**, clique em **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="ac586-161">On the **Data connectors** page under **Bloomberg Message**, click **View**.</span></span>

3. <span data-ttu-id="ac586-162">Na página descrição do produto de **mensagem do Bloomberg** , clique em **Adicionar conector**</span><span class="sxs-lookup"><span data-stu-id="ac586-162">On the **Bloomberg Message** product description page, click **Add connector**</span></span>

4. <span data-ttu-id="ac586-163">Na página **termos de serviço** , clique em **aceitar**.</span><span class="sxs-lookup"><span data-stu-id="ac586-163">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="ac586-164">No **site adicionar credenciais para Bloomberg SFTP** , em etapa 1, clique na **chave de download SSH**, **baixar a chave PGP**e baixar links de **endereço IP** para salvar uma cópia de cada arquivo no computador local.</span><span class="sxs-lookup"><span data-stu-id="ac586-164">On the **Add credentials for Bloomberg SFTP site** under step 1, click the **Download SSH key**, **Download PGP key**, and **Download IP address** links to save a copy of each file to your local computer.</span></span> <span data-ttu-id="ac586-165">Esses arquivos contêm os seguintes itens que são usados para configurar o site do Bloomberg SFTP na etapa 2:</span><span class="sxs-lookup"><span data-stu-id="ac586-165">These files contain the following items that are used to configure the Bloomberg SFTP site in Step 2:</span></span>

   - <span data-ttu-id="ac586-166">Chave pública SSH: essa chave é usada para configurar o Secure Shell (SSH) para habilitar um logon remoto seguro quando o conector se conecta ao site do Bloomberg SFTP.</span><span class="sxs-lookup"><span data-stu-id="ac586-166">SSH public key: This key is used to configure Secure Shell (SSH) to enable a secure remote login when the connector connects to the Bloomberg SFTP site.</span></span>

   - <span data-ttu-id="ac586-167">Chave pública do PGP: essa chave é usada para configurar a criptografia de dados que são transferidos do site do Bloomberg SFTP para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac586-167">PGP public key: This key is used to configure the encryption of data that's transferred from the Bloomberg SFTP site to Microsoft 365.</span></span>

   - <span data-ttu-id="ac586-168">Endereço IP: o site do Bloomberg SFTP é configurado para aceitar uma solicitação de conexão apenas desse endereço IP, que é usado pelo conector de mensagens do Bloomberg que você criou na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="ac586-168">IP address: The Bloomberg SFTP site is configured to accept a connection request only from this IP address, which is used by the Bloomberg Message connector that you create in Step 3.</span></span>

6. <span data-ttu-id="ac586-169">Clique em **Cancelar** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="ac586-169">Click **Cancel** to close the wizard.</span></span> <span data-ttu-id="ac586-170">Você volta para este assistente na etapa 3 para criar o conector.</span><span class="sxs-lookup"><span data-stu-id="ac586-170">You come back to this wizard in Step 3 to create the connector.</span></span>

## <a name="step-2-configure-the-bloomberg-sftp-site"></a><span data-ttu-id="ac586-171">Etapa 2: configurar o site do Bloomberg SFTP</span><span class="sxs-lookup"><span data-stu-id="ac586-171">Step 2: Configure the Bloomberg SFTP site</span></span>

> [!NOTE]
> <span data-ttu-id="ac586-172">Conforme mencionado anteriormente, se você for a organização configurou anteriormente um site do Bloomberg SFTP para arquivar dados de Bloomberg instantâneos, não será necessário configurar outro.</span><span class="sxs-lookup"><span data-stu-id="ac586-172">As previously stated, if you're organization has previously set up a Bloomberg SFTP site to archive Instant Bloomberg data, you don't have to set up another one.</span></span> <span data-ttu-id="ac586-173">Você pode especificar o mesmo site SFTP ao criar o conector na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="ac586-173">You can specify the same SFTP site when you create the connector in Step 3.</span></span>

<span data-ttu-id="ac586-174">A próxima etapa é usar as chaves públicas SSH e PGP e o endereço IP obtido na etapa 1 para configurar a autenticação SSH e a criptografia PGP para o site Bloomberg SFTP.</span><span class="sxs-lookup"><span data-stu-id="ac586-174">The next step is to use the SSH and PGP public keys and the IP address that you obtained in Step 1 to configure SSH authentication and PGP encryption for the Bloomberg SFTP site.</span></span> <span data-ttu-id="ac586-175">Isso permite que o conector de mensagens do Bloomberg que você criou na etapa 3 se conecte ao site Bloomberg SFTP e transfira dados de mensagem do Bloomberg para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac586-175">This lets the Bloomberg Message connector that you create in Step 3 connect to the Bloomberg SFTP site and transfer Bloomberg Message data to Microsoft 365.</span></span> <span data-ttu-id="ac586-176">Você precisa trabalhar com o suporte ao cliente Bloomberg para configurar seu site do Bloomberg SFTP.</span><span class="sxs-lookup"><span data-stu-id="ac586-176">You need to work with Bloomberg customer support to set up your Bloomberg SFTP site.</span></span> <span data-ttu-id="ac586-177">Entre em contato com o [suporte ao cliente Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) para obter assistência.</span><span class="sxs-lookup"><span data-stu-id="ac586-177">Contact [Bloomberg customer support](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) for assistance.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac586-178">O Bloomberg recomenda que você anexe os três arquivos baixados na etapa 1 a uma mensagem de email e envie-o à sua equipe de suporte ao cliente ao trabalhar com eles para configurar seu site do Bloomberg SFTP.</span><span class="sxs-lookup"><span data-stu-id="ac586-178">Bloomberg recommends that you attach the three files that you downloaded in Step 1 to an email message and send it to their customer support team when working with them to set up your Bloomberg SFTP site.</span></span>

## <a name="step-3-create-a-bloomberg-message-connector"></a><span data-ttu-id="ac586-179">Etapa 3: criar um conector de mensagens do Bloomberg</span><span class="sxs-lookup"><span data-stu-id="ac586-179">Step 3: Create a Bloomberg Message connector</span></span>

<span data-ttu-id="ac586-180">A última etapa é criar um conector de mensagens do Bloomberg no centro de conformidade da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac586-180">The last step is to create a Bloomberg Message connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="ac586-181">O conector usa as informações que você fornece para se conectar ao site do Bloomberg SFTP e transferir mensagens de email para as caixas de correio de usuário correspondentes no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac586-181">The connector uses the information you provide to connect to the Bloomberg SFTP site and transfer email messages to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="ac586-182">Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **conectores de dados** no painel de navegação esquerdo.</span><span class="sxs-lookup"><span data-stu-id="ac586-182">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="ac586-183">Na página **conectores de dados** sob **mensagem do Bloomberg**, clique em **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="ac586-183">On the **Data connectors** page under **Bloomberg Message**, click **View**.</span></span>

3. <span data-ttu-id="ac586-184">Na página descrição do produto de **mensagem do Bloomberg** , clique em **Adicionar conector**</span><span class="sxs-lookup"><span data-stu-id="ac586-184">On the **Bloomberg Message** product description page, click **Add connector**</span></span>

4. <span data-ttu-id="ac586-185">Na página **termos de serviço** , clique em **aceitar**.</span><span class="sxs-lookup"><span data-stu-id="ac586-185">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="ac586-186">Na página **Adicionar credenciais para o site do Bloomberg SFTP** , em etapa 3, insira as informações necessárias nas caixas a seguir e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ac586-186">On the **Add credentials for Bloomberg SFTP site** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

      - <span data-ttu-id="ac586-187">**Código da empresa:** A ID da sua organização que é usada como o nome de usuário para o site do Bloomberg SFTP.</span><span class="sxs-lookup"><span data-stu-id="ac586-187">**Firm code:** The ID for your organization that is used as the username for the Bloomberg SFTP site.</span></span>

      - <span data-ttu-id="ac586-188">**Senha:** A senha do site do Bloomberg SFTP da sua organização.</span><span class="sxs-lookup"><span data-stu-id="ac586-188">**Password:** The password for your organization's Bloomberg SFTP site.</span></span>

      - <span data-ttu-id="ac586-189">**URL de SFTP:** A URL do site do Bloomberg SFTP (por exemplo, sftp.bloomberg.com).</span><span class="sxs-lookup"><span data-stu-id="ac586-189">**SFTP URL:** The URL for the Bloomberg SFTP site (for example, sftp.bloomberg.com).</span></span>

      - <span data-ttu-id="ac586-190">**Porta SFTP:** O número da porta do site Bloomberg SFTP.</span><span class="sxs-lookup"><span data-stu-id="ac586-190">**SFTP port:** The port number for the Bloomberg SFTP site.</span></span> <span data-ttu-id="ac586-191">O conector usa essa porta para se conectar ao site SFTP.</span><span class="sxs-lookup"><span data-stu-id="ac586-191">The connector uses this port to connect to the SFTP site.</span></span>

6. <span data-ttu-id="ac586-192">Na página de **mapeamento do usuário** , habilite o mapeamento automático de usuários e forneça mapeamento de usuário personalizado conforme necessário</span><span class="sxs-lookup"><span data-stu-id="ac586-192">On the **User-mapping** page, enable automatic user mapping and provide custom user mapping as required</span></span>

7. <span data-ttu-id="ac586-193">Clique em **Avançar**, revise suas configurações e clique em preparar para criar o conector.</span><span class="sxs-lookup"><span data-stu-id="ac586-193">Click **Next**, review your settings, and then click prepare to create the connector.</span></span>

8. <span data-ttu-id="ac586-194">Vá para a página **conectores de dados** para ver o andamento do processo de importação para o novo conector.</span><span class="sxs-lookup"><span data-stu-id="ac586-194">Go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="ac586-195">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="ac586-195">Known issues</span></span>

- <span data-ttu-id="ac586-196">Não há suporte para o encadeamento de emails de mensagem do Bloomberg para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac586-196">Threading of Bloomberg Message email imported to Microsoft 365 isn't supported.</span></span> <span data-ttu-id="ac586-197">Mensagens individuais enviadas a uma pessoa são importadas, mas não são apresentadas em uma conversa encadeada.</span><span class="sxs-lookup"><span data-stu-id="ac586-197">Individual messages sent to a person are imported, but they aren't presented in a threaded conversation.</span></span> <span data-ttu-id="ac586-198">A Microsoft está trabalhando para dar suporte ao encadeamento em versões posteriores do conector de dados de mensagem do Bloomberg.</span><span class="sxs-lookup"><span data-stu-id="ac586-198">Microsoft is working to support threading in later versions of the Bloomberg Message data connector.</span></span>