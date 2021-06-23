---
title: Configurar um conector para arquivar dados fuze em Microsoft 365
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
description: Saiba como configurar e usar um conector 17a-4 Fuze DataParser para importar e arquivar dados fuze em Microsoft 365.
ms.openlocfilehash: eb7e66bf3a8d00431ad7e393471110b36efa8e65
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096359"
---
# <a name="set-up-a-connector-to-archive-fuze-data-preview"></a><span data-ttu-id="9d843-103">Configurar um conector para arquivar dados fuze (visualização)</span><span class="sxs-lookup"><span data-stu-id="9d843-103">Set up a connector to archive Fuze data (preview)</span></span>

<span data-ttu-id="9d843-104">Use o [Fuze DataParser](https://www.17a-4.com/fuze-dataparser/) do 17a-4 LLC para importar e arquivar dados do Fuze para caixas de correio de usuário em sua organização Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9d843-104">Use the [Fuze DataParser](https://www.17a-4.com/fuze-dataparser/) from 17a-4 LLC to import and archive data from Fuze to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="9d843-105">O DataParser inclui um conector Fuze configurado para capturar itens de uma fonte de dados de terceiros e importar esses itens para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9d843-105">The DataParser includes a Fuze connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="9d843-106">O conector Fuze DataParser converte dados fuze em um formato de mensagem de email e importa esses itens para caixas de correio de usuário em Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9d843-106">The Fuze DataParser connector converts Fuze data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="9d843-107">Depois que os dados fuze são armazenados em caixas de correio de usuário, você pode aplicar Microsoft 365 de conformidade, como Retenção de Litígio, Descoberta Eletrônico, políticas de retenção e rótulos de retenção e conformidade de comunicação.</span><span class="sxs-lookup"><span data-stu-id="9d843-107">After Fuze data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="9d843-108">Usar um conector Fuze para importar e arquivar dados em Microsoft 365 pode ajudar sua organização a permanecer em conformidade com políticas governamentais e regulatórias.</span><span class="sxs-lookup"><span data-stu-id="9d843-108">Using a Fuze connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-fuze-data"></a><span data-ttu-id="9d843-109">Visão geral dos dados fuze de arquivamento</span><span class="sxs-lookup"><span data-stu-id="9d843-109">Overview of archiving Fuze data</span></span>

<span data-ttu-id="9d843-110">A visão geral a seguir explica o processo de uso de um conector de dados para arquivar dados fuze em Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9d843-110">The following overview explains the process of using a data connector to archive Fuze data in Microsoft 365.</span></span>

![Fluxo de trabalho de arquivamento para dados fuze de 17a-4](../media/FuzeDataParserConnectorWorkflow.png)

1. <span data-ttu-id="9d843-112">Sua organização trabalha com o 17a-4 para configurar e configurar o Fuze DataParser.</span><span class="sxs-lookup"><span data-stu-id="9d843-112">Your organization works with 17a-4 to set up and configure the Fuze DataParser.</span></span>

2. <span data-ttu-id="9d843-113">Regularmente, os itens Fuze são coletados pelo DataParser.</span><span class="sxs-lookup"><span data-stu-id="9d843-113">On a regular basis, Fuze items are collected by the DataParser.</span></span> <span data-ttu-id="9d843-114">O DataParser também converte o conteúdo de uma mensagem em um formato de mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="9d843-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="9d843-115">O conector Fuze DataParser criado no Centro de conformidade do Microsoft 365 conecta-se ao DataParser e transfere as mensagens para um local seguro do Azure Armazenamento na nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9d843-115">The Fuze DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="9d843-116">Uma subpasta na pasta Caixa de Entrada chamada **Fuze DataParser** é criada nas caixas de correio do usuário e os itens Fuze são importados para essa pasta.</span><span class="sxs-lookup"><span data-stu-id="9d843-116">A subfolder in the Inbox folder named **Fuze DataParser** is created in the user mailboxes, and the Fuze items are imported to that folder.</span></span> <span data-ttu-id="9d843-117">O conector determina para qual caixa de correio importar itens usando o valor da *propriedade Email.*</span><span class="sxs-lookup"><span data-stu-id="9d843-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="9d843-118">Cada item Fuze contém essa propriedade, que é preenchida com o endereço de email de cada participante.</span><span class="sxs-lookup"><span data-stu-id="9d843-118">Every Fuze item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="9d843-119">Antes de configurar um conector</span><span class="sxs-lookup"><span data-stu-id="9d843-119">Before you set up a connector</span></span>

- <span data-ttu-id="9d843-120">Crie uma conta DataParser para conectores da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9d843-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="9d843-121">Para fazer isso, entre em [contato com 17a-4 LLC](https://www.17a-4.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="9d843-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="9d843-122">Você precisa entrar nessa conta ao criar o conector na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="9d843-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="9d843-123">O usuário que cria o conector Fuze DataParser na Etapa 1 (e o conclui na Etapa 3) deve ser atribuído à função De exportação de importação de caixa de correio no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9d843-123">The user who creates the Fuze DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="9d843-124">Essa função é necessária para adicionar conectores na página **Conectores de** dados no Centro de conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9d843-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="9d843-125">Por padrão, essa função não é atribuída a um grupo de funções no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9d843-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="9d843-126">Você pode adicionar a função Exportar Importação de Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9d843-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="9d843-127">Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros.</span><span class="sxs-lookup"><span data-stu-id="9d843-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="9d843-128">Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de funções em Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="9d843-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-fuze-dataparser-connector"></a><span data-ttu-id="9d843-129">Etapa 1: Configurar um conector Fuze DataParser</span><span class="sxs-lookup"><span data-stu-id="9d843-129">Step 1: Set up a Fuze DataParser connector</span></span>

<span data-ttu-id="9d843-130">A primeira etapa é acessar a página Conectores de dados no Centro de conformidade do Microsoft 365 e criar um conector 17a-4 para dados fuze.</span><span class="sxs-lookup"><span data-stu-id="9d843-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for Fuze data.</span></span>

1. <span data-ttu-id="9d843-131">Vá para <https://compliance.microsoft.com> e clique em **Conectores de dados**  >  **Fuze DataParser**.</span><span class="sxs-lookup"><span data-stu-id="9d843-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **Fuze DataParser**.</span></span>

2. <span data-ttu-id="9d843-132">Na página **Descrição do produto Fuze DataParser,** clique **em Adicionar conector**.</span><span class="sxs-lookup"><span data-stu-id="9d843-132">On the **Fuze DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="9d843-133">Na página **Termos de serviço,** clique em **Aceitar**.</span><span class="sxs-lookup"><span data-stu-id="9d843-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="9d843-134">Insira um nome exclusivo que identifique o conector e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="9d843-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="9d843-135">Entre na sua conta 17a-4 e conclua as etapas no assistente de conexão Fuze DataParser.</span><span class="sxs-lookup"><span data-stu-id="9d843-135">Sign in to your 17a-4 account and complete the steps in the Fuze DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-fuze-dataparser-connector"></a><span data-ttu-id="9d843-136">Etapa 2: Configurar o conector Fuze DataParser</span><span class="sxs-lookup"><span data-stu-id="9d843-136">Step 2: Configure the Fuze DataParser connector</span></span>

<span data-ttu-id="9d843-137">Trabalhe com o Suporte 17a-4 para configurar o conector Fuze DataParser.</span><span class="sxs-lookup"><span data-stu-id="9d843-137">Work with 17a-4 Support to configure the Fuze DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="9d843-138">Etapa 3: Mapear usuários</span><span class="sxs-lookup"><span data-stu-id="9d843-138">Step 3: Map users</span></span>

<span data-ttu-id="9d843-139">O conector Fuze DataParser mapeará automaticamente os usuários para seus endereços de email Microsoft 365 antes de importar dados para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9d843-139">The Fuze DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-fuze-dataparser-connector"></a><span data-ttu-id="9d843-140">Etapa 4: Monitorar o conector Fuze DataParser</span><span class="sxs-lookup"><span data-stu-id="9d843-140">Step 4: Monitor the Fuze DataParser connector</span></span>

<span data-ttu-id="9d843-141">Depois de criar um conector Fuze DataParser, você pode exibir o status do conector no Centro de conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9d843-141">After you create a Fuze DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="9d843-142">Vá para <https://compliance.microsoft.com> e clique **em Conectores de dados** na nav esquerda.</span><span class="sxs-lookup"><span data-stu-id="9d843-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="9d843-143">Clique na **guia Conectores** e selecione o conector Fuze DataParser que você criou para exibir a página de sobrevoo, que contém as propriedades e informações sobre o conector.</span><span class="sxs-lookup"><span data-stu-id="9d843-143">Click the **Connectors** tab and then select the Fuze DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="9d843-144">Em **Status do conector com origem**, clique no link Baixar **log** para abrir (ou salvar) o log de status do conector.</span><span class="sxs-lookup"><span data-stu-id="9d843-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="9d843-145">Esse log contém dados que foram importados para a nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9d843-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="9d843-146">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="9d843-146">Known issues</span></span>

<span data-ttu-id="9d843-147">Neste momento, não há suporte para importação de anexos ou itens maiores que 10 MB.</span><span class="sxs-lookup"><span data-stu-id="9d843-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="9d843-148">O suporte para itens maiores estará disponível posteriormente.</span><span class="sxs-lookup"><span data-stu-id="9d843-148">Support for larger items will be available at a later date.</span></span>
