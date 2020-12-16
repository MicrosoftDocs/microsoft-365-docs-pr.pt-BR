---
title: Piloto do Microsoft 365 a partir do meu domínio personalizado
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
ms.custom: ''
search.appverid:
- BCS160
- MET150
- MOE150
description: Aprenda a usar o recurso de email piloto do meu domínio personalizado para uma caixa de correio do Microsoft 365 usando apenas duas contas de teste.
ms.openlocfilehash: 6cc5b1163f666af4bd13047ab3b1fda7fd747b5f
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688212"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="daf9e-103">Piloto do Microsoft 365 a partir do meu domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="daf9e-103">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="daf9e-104">Você pode usar o Microsoft 365 piloto com estes requisitos e limitações:</span><span class="sxs-lookup"><span data-stu-id="daf9e-104">You can pilot Microsoft 365 with these requirements and limitations:</span></span>

- <span data-ttu-id="daf9e-105">Seu provedor de email atual deve fornecer encaminhamento de email.</span><span class="sxs-lookup"><span data-stu-id="daf9e-105">Your current email provider must provide email forwarding.</span></span>

- <span data-ttu-id="daf9e-106">Você deve gerenciar seus registros DNS do Microsoft 365 em seu provedor de host DNS, em vez de ter o Microsoft 365 gerenciando esses registros para você.</span><span class="sxs-lookup"><span data-stu-id="daf9e-106">You must manage your Microsoft 365 DNS records at your DNS hosting provider, rather than have Microsoft 365 manage these records for you.</span></span>

    <span data-ttu-id="daf9e-107">Para saber mais, confira [Adicionar registros DNS para conectar seu domínio](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span><span class="sxs-lookup"><span data-stu-id="daf9e-107">To learn more, see [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

- <span data-ttu-id="daf9e-108">As informações de disponibilidade para os usuários no outro servidor de email não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="daf9e-108">Free/busy information for users on the other email server is not available.</span></span>

- <span data-ttu-id="daf9e-109">Os administradores não podem administrar todas as contas de usuário a partir de um único local.</span><span class="sxs-lookup"><span data-stu-id="daf9e-109">Admins can't administer all user accounts from a single location.</span></span>

- <span data-ttu-id="daf9e-110">Os usuários podem não conseguir usar a filtragem de spam do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="daf9e-110">Users might not be able to use Microsoft 365 spam filtering.</span></span>

- <span data-ttu-id="daf9e-111">Isso é recomendado para um número muito pequeno de usuários e aplicável somente ao uso de email para um piloto.</span><span class="sxs-lookup"><span data-stu-id="daf9e-111">This is recommended for a very small number of users and only applies to the use of email for a pilot.</span></span>

## <a name="set-up-a-microsoft-365-pilot"></a><span data-ttu-id="daf9e-112">Configurar um piloto do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="daf9e-112">Set up a Microsoft 365 pilot</span></span>

<span data-ttu-id="daf9e-113">Siga estas etapas para configurar um piloto do Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="daf9e-113">Follow these steps to set up a Microsoft 365 pilot:</span></span>

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a><span data-ttu-id="daf9e-114">Etapa 1: Entre no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="daf9e-114">Step 1: Sign in to the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="daf9e-115">Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="daf9e-115">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your work or school account.</span></span>

2. <span data-ttu-id="daf9e-116">No painel de navegação à esquerda, selecione **Configurações** > **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="daf9e-116">Select **Settings** > **Domains** in the left navigation pane.</span></span>

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a><span data-ttu-id="daf9e-117">Etapa 2: Verifique se você é o proprietário do domínio que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="daf9e-117">Step 2: Verify that you own the domain you want to use</span></span>

1. <span data-ttu-id="daf9e-118">Na página **Domínios**, selecione **Adicionar domínio**.</span><span class="sxs-lookup"><span data-stu-id="daf9e-118">On the **Domains** page, select **Add domain**.</span></span>

2. <span data-ttu-id="daf9e-119">Digite o nome do domínio na caixa, selecione **Usar este domínio** e selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="daf9e-119">Type the domain name in the box, select **Use this domain**, and then select **Continue**.</span></span>

3. <span data-ttu-id="daf9e-120">Selecione os serviços que você deseja testar com seu domínio, como email e mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="daf9e-120">Select the services you want to test with your domain, like email and instant messaging.</span></span>

5. <span data-ttu-id="daf9e-121">Na página **Verificar domínio**, siga as instruções passo a passo e selecione **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="daf9e-121">On the **Verify** domain page, follow the step-by-step instructions, amd then select **Verify**.</span></span>

    <span data-ttu-id="daf9e-122">Leva entre alguns minutos e até 72 horas para que as alterações de DNS entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="daf9e-122">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span>

    <span data-ttu-id="daf9e-123">Você será solicitado a modificar seus registros de DNS quando a verificação for bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="daf9e-123">When verification is successful, you are asked to modify your DNS records.</span></span>

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a><span data-ttu-id="daf9e-124">Etapa 3: Marque o domínio como compartilhado no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="daf9e-124">Step 3: Mark the domain as shared in Exchange Online</span></span>

1. <span data-ttu-id="daf9e-125">No centro de administração do Exchange, na seção **Fluxo de emails**, selecione **Domínios aceitos** e, em seguida, selecione o domínio que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="daf9e-125">In the Exchange admin center, in the **Mail flow** section, select **Accepted domains**, and then select the domain you want to modify.</span></span>

2. <span data-ttu-id="daf9e-126">Clique duas vezes para abrir a janela e selecione **Retransmissão Interna**.</span><span class="sxs-lookup"><span data-stu-id="daf9e-126">Double-click to open the window, and then select **Internal Relay**.</span></span> 

3. <span data-ttu-id="daf9e-127">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="daf9e-127">Select **Save**.</span></span>

    <span data-ttu-id="daf9e-128">Esta configuração pode exigir alguns minutos para entrar em vigor.</span><span class="sxs-lookup"><span data-stu-id="daf9e-128">This setting might require a few minutes to take effect.</span></span>

### <a name="step-4-unblock-the-existing-email-server-optional"></a><span data-ttu-id="daf9e-129">Etapa 4: Desbloqueie o servidor de email existente (opcional)</span><span class="sxs-lookup"><span data-stu-id="daf9e-129">Step 4: Unblock the existing email server (optional)</span></span>

<span data-ttu-id="daf9e-130">O Microsoft 365 usa a Proteção do Exchange Online (EOP) para a proteção contra spam.</span><span class="sxs-lookup"><span data-stu-id="daf9e-130">Microsoft 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="daf9e-131">A EOP poderá bloquear o seu servidor de email existente se detectar um alto volume de spam sendo encaminhado pelo seu servidor de email atual.</span><span class="sxs-lookup"><span data-stu-id="daf9e-131">EOP might block your existing mail server if it detects a high volume of spam being forwarded by your current mail server.</span></span> <span data-ttu-id="daf9e-132">Se você confiar na proteção contra spam do seu outro provedor de email, poderá desbloquear o servidor no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="daf9e-132">If you trust the spam protection for your other email provider, you can unblock the server in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="daf9e-133">Desbloquear o seu servidor de email existente permite que qualquer spam recebido pelo seu servidor original chegue nas caixas de correio do Microsoft 365. Assim, você não poderá avaliar o quão bem a Microsoft 365 evita spam.</span><span class="sxs-lookup"><span data-stu-id="daf9e-133">Unblocking your existing email server allows any spam that arrives through your original server to come to the Microsoft 365 mailboxes, and you can’t evaluate how well Microsoft 365 prevents spam.</span></span>

1. <span data-ttu-id="daf9e-134">No painel de navegação do centro de administração do Exchange, selecione **Proteção** e, em seguida, selecione **Filtro de conexão**.</span><span class="sxs-lookup"><span data-stu-id="daf9e-134">In the Exchange admin center navigation pane, select **Protection**, and then select **Connection filter**.</span></span>

2. <span data-ttu-id="daf9e-135">Na **Lista de IP Permitidos**, selecione **+** e adicione o endereço IP do servidor de email do seu provedor de email atual.</span><span class="sxs-lookup"><span data-stu-id="daf9e-135">In the **IP Allow list**, select **+**, and add the mail server IP address for your current email provider.</span></span> 

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a><span data-ttu-id="daf9e-136">Etapa 5: Crie contas de usuário e defina o endereço principal para resposta </span><span class="sxs-lookup"><span data-stu-id="daf9e-136">Step 5: Create user accounts and set the primary reply-to address</span></span>

1. <span data-ttu-id="daf9e-137">No Centro de administração do Microsoft 365, barra de navegação à esquerda, selecione **Usuários** > **Usuários Ativos**.</span><span class="sxs-lookup"><span data-stu-id="daf9e-137">In the Microsoft 365 admin center left navigation, select **Users** > **Active Users**.</span></span>

2. <span data-ttu-id="daf9e-138">Crie duas contas de teste adicionando dois usuários existentes.</span><span class="sxs-lookup"><span data-stu-id="daf9e-138">Create two test accounts by adding two existing users.</span></span>

    <span data-ttu-id="daf9e-139">Para cada conta, selecione **+ Adicionar um usuário** e preencha as informações necessárias, incluindo o método de senha que você deseja testar.</span><span class="sxs-lookup"><span data-stu-id="daf9e-139">For each account, select **+ Add a user**, and fill out the required information, including the password method you want to test.</span></span>

    <span data-ttu-id="daf9e-140">Para garantir que o email de um usuário permaneça o mesmo, o campo **Nome de usuário** deve corresponder ao endereço de email atual do usuário.</span><span class="sxs-lookup"><span data-stu-id="daf9e-140">To ensure a user’s email stays the same, the **User name** field must match the user’s current email address.</span></span>

3. <span data-ttu-id="daf9e-141">Escolha a licença apropriada, clique em **Avançar** e clique em **Terminar de adicionar**.</span><span class="sxs-lookup"><span data-stu-id="daf9e-141">Choose the appropriate license, click **Next**, and then click **Finish adding**.</span></span> 

4. <span data-ttu-id="daf9e-142">Ao lado de **Nome de usuário**, selecione seu nome de domínio personalizado na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="daf9e-142">Next to **User name**, select your custom domain name from the drop-down list.</span></span> 

5. <span data-ttu-id="daf9e-143">Selecione **Criar** > **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="daf9e-143">Select **Create** > **Close**.</span></span>

### <a name="step-6-configure-mail-to-flow-from-microsoft-365-or-office-365-to-email-server"></a><span data-ttu-id="daf9e-144">Etapa 6: \* \* Configure o email para fluir do Microsoft 365 ou do Office 365 para o Servidor de email</span><span class="sxs-lookup"><span data-stu-id="daf9e-144">Step 6: \*\*Configure mail to flow from Microsoft 365 or Office 365 to Email server</span></span>

<span data-ttu-id="daf9e-145">Há duas etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="daf9e-145">There are two steps for this:</span></span>

1. <span data-ttu-id="daf9e-146">Configure seu ambiente Microsoft 365 ou o Office 365.</span><span class="sxs-lookup"><span data-stu-id="daf9e-146">Configure your Microsoft 365 or Office 365 environment.</span></span>

2. <span data-ttu-id="daf9e-147">Configure um conector a partir do Microsoft 365 ou do Office 365 para seu servidor de email.</span><span class="sxs-lookup"><span data-stu-id="daf9e-147">Set up a connector from Microsoft 365 or Office 365 to your email server.</span></span>

### <a name="1-configure-your-microsoft-365-or-office-365-environment"></a><span data-ttu-id="daf9e-148">1. Configure o seu ambiente do Microsoft 365 ou do Office 365</span><span class="sxs-lookup"><span data-stu-id="daf9e-148">1. Configure your Microsoft 365 or Office 365 environment</span></span>

<span data-ttu-id="daf9e-149">Verifique se você concluiu o seguinte no Microsoft 365 ou no Office 365:</span><span class="sxs-lookup"><span data-stu-id="daf9e-149">Make sure you have completed the following in Microsoft 365 or Office 365:</span></span>

1. <span data-ttu-id="daf9e-150">Para configurar conectores, você precisa ter permissões atribuídas antes de começar.</span><span class="sxs-lookup"><span data-stu-id="daf9e-150">To set up connectors, you need permissions assigned before you can begin.</span></span> <span data-ttu-id="daf9e-151">Para verificar quais são as permissões necessárias, confira a entrada dos conectores do Microsoft 365 e do Office 365 no tópico [Permissões de recurso na EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/feature-permissions-in-eop).</span><span class="sxs-lookup"><span data-stu-id="daf9e-151">To check what permissions you need, see the Microsoft 365 and Office 365 connectors entry in the [Feature permissions in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/feature-permissions-in-eop) topic.</span></span>

2. <span data-ttu-id="daf9e-152">Se você quiser que a EOP ou o Exchange Online façam a retransmissão de email de seus servidores de email para a Internet:</span><span class="sxs-lookup"><span data-stu-id="daf9e-152">If you want EOP or Exchange Online to relay email from your email servers to the Internet, either:</span></span>

   - <span data-ttu-id="daf9e-153">Use um certificado configurado com um nome de assunto que corresponda a um domínio aceito no Microsoft 365 ou no Office 365.</span><span class="sxs-lookup"><span data-stu-id="daf9e-153">Use a certificate configured with a subject name that matches an accepted domain in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="daf9e-154">É recomendável que o nome comum ou assunto alternativo do seu certificado coincida com o domínio SMTP principal da sua organização.</span><span class="sxs-lookup"><span data-stu-id="daf9e-154">We recommend that your certificate's common name or subject alternative name matches the primary SMTP domain for your organization.</span></span> <span data-ttu-id="daf9e-155">Para obter detalhes, confira: [Pré-requisitos do seu ambiente de email local](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#prerequisites-for-your-on-premises-email-environment).</span><span class="sxs-lookup"><span data-stu-id="daf9e-155">For details, see [Prerequisites for your on-premises email environment](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#prerequisites-for-your-on-premises-email-environment).</span></span>

   <span data-ttu-id="daf9e-156">-OU-</span><span class="sxs-lookup"><span data-stu-id="daf9e-156">-OR-</span></span>

   - <span data-ttu-id="daf9e-157">Verifique que todos os seus domínios e subdomínios de remetente da organização sejam configurados como domínios aceitos no Microsoft 365 ou no Office 365.</span><span class="sxs-lookup"><span data-stu-id="daf9e-157">Make sure that all your organization sender domains and subdomains are configured as accepted domains in Microsoft 365 or Office 365.</span></span>

   <span data-ttu-id="daf9e-158">Para saber mais sobre como definir domínios aceitos, confira [Gerenciar domínios aceitos no Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) e [Habilitar o fluxo de emails para subdomínios no Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span><span class="sxs-lookup"><span data-stu-id="daf9e-158">For more information about defining accepted domains, see [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) and [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

3. <span data-ttu-id="daf9e-159">Decida se você deseja usar regras de fluxo de email (também conhecidas como regras de transporte) ou nomes de domínio para entregar emails do Microsoft 365 ou do Office 365 para seus servidores de email.</span><span class="sxs-lookup"><span data-stu-id="daf9e-159">Decide whether you want to use mail flow rules (also known as transport rules) or domain names to deliver mail from Microsoft 365 or Office 365 to your email servers.</span></span> <span data-ttu-id="daf9e-160">A maioria das empresas optará por entregar emails de todos os domínios aceitos.</span><span class="sxs-lookup"><span data-stu-id="daf9e-160">Most businesses choose to deliver mail for all accepted domains.</span></span> <span data-ttu-id="daf9e-161">Para saber mais, consulte [Cenário: roteamento de email condicional no Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).</span><span class="sxs-lookup"><span data-stu-id="daf9e-161">For more information, see [Scenario: Conditional mail routing in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).</span></span>

> [!NOTE]
> <span data-ttu-id="daf9e-162">Você pode configurar regras de fluxo de email conforme descrito nas [ações da regra de fluxo de email no Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="daf9e-162">You can set up mail flow rules as described in [Mail flow rule actions in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span> <span data-ttu-id="daf9e-163">Por exemplo, talvez você queira usar regras de transporte com conectores se atualmente seu email for direcionado por meio de listas de distribuição para vários sites.</span><span class="sxs-lookup"><span data-stu-id="daf9e-163">For example, you might want to use mail flow rules with connectors if your mail is currently directed via distribution lists to multiple sites.</span></span>

### <a name="2-set-up-a-connector-from-microsoft-365-or-office-365-to-your-email-server"></a><span data-ttu-id="daf9e-164">2. Configure um conector a partir do Microsoft 365 ou do Office 365 para seu servidor de email</span><span class="sxs-lookup"><span data-stu-id="daf9e-164">2. Set up a connector from Microsoft 365 or Office 365 to your email server</span></span>

<span data-ttu-id="daf9e-165">Para criar um conector no Microsoft 365 ou no Office 365, clique em **Admin** e em **Exchange** para acessar o Centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="daf9e-165">To create a connector in Microsoft 365 or Office 365, click **Admin**, and then click **Exchange** to go to the Exchange admin center.</span></span> <span data-ttu-id="daf9e-166">Em seguida, clique em **fluxo de emails** e clique em **conectores**.</span><span class="sxs-lookup"><span data-stu-id="daf9e-166">Next, click **mail flow**, and click **connectors**.</span></span>

<span data-ttu-id="daf9e-167">Configure conectores usando o assistente.</span><span class="sxs-lookup"><span data-stu-id="daf9e-167">Set up connectors using the wizard.</span></span>

<span data-ttu-id="daf9e-168">Para iniciar o assistente, clique no sinal de adição **+**.</span><span class="sxs-lookup"><span data-stu-id="daf9e-168">To start the wizard, click the plus symbol **+**.</span></span> <span data-ttu-id="daf9e-169">Na primeira tela, escolha **De** Office 365 e **Para** o Servidor de Email da Sua Organização.</span><span class="sxs-lookup"><span data-stu-id="daf9e-169">On the first screen, choose **From** Office 365 and **To** Your Organization Mail server.</span></span>

<span data-ttu-id="daf9e-170">Clique em **Próxima** e siga as instruções no assistente.</span><span class="sxs-lookup"><span data-stu-id="daf9e-170">Click **Next**, and follow the instructions in the wizard.</span></span> <span data-ttu-id="daf9e-171">Clique nos links **Ajuda** ou **Saiba mais** se precisar de mais informações.</span><span class="sxs-lookup"><span data-stu-id="daf9e-171">Click the **Help** or **Learn More** links if you need more information.</span></span> <span data-ttu-id="daf9e-172">O assistente guiará você durante a configuração.</span><span class="sxs-lookup"><span data-stu-id="daf9e-172">The wizard will guide you through setup.</span></span> <span data-ttu-id="daf9e-173">No fim, verifique a validação do seu conector.</span><span class="sxs-lookup"><span data-stu-id="daf9e-173">At the end, make sure your connector validates.</span></span> <span data-ttu-id="daf9e-174">Se o conector não validar, clique duas vezes na mensagem exibida para obter mais informações e consulte o artigo [Validar conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors) para obter ajuda na resolução de problemas.</span><span class="sxs-lookup"><span data-stu-id="daf9e-174">If the connector does not validate, double-click the message displayed to get more information, and see [Validate connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors) for help resolving issues.</span></span>



### <a name="step-7-update-dns-records-at-your-dns-hosting-provider"></a><span data-ttu-id="daf9e-175">Etapa 7: Atualize os registros DNS em seu provedor de hospedagem DNS</span><span class="sxs-lookup"><span data-stu-id="daf9e-175">Step 7: Update DNS records at your DNS hosting provider</span></span>

<span data-ttu-id="daf9e-176">Entre no site do seu provedor de hospedagem DNS e siga as instruções em [Adicionar registros DNS para conectar seu domínio](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span><span class="sxs-lookup"><span data-stu-id="daf9e-176">Sign in to your DNS hosting provider's website, and follow the instructions at [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

<span data-ttu-id="daf9e-177">**Faça as duas exceções a seguir:**</span><span class="sxs-lookup"><span data-stu-id="daf9e-177">**Make the following two exceptions:**</span></span>

- <span data-ttu-id="daf9e-178">Não crie um novo registro MX ou altere seu registro MX existente.</span><span class="sxs-lookup"><span data-stu-id="daf9e-178">Do not create a new MX record or change your existing MX record.</span></span>

- <span data-ttu-id="daf9e-179">Se você já tiver um registro SPF (Sender Policy Framework) para o seu provedor de email anterior, em vez de criar um novo registro SPF (TXT) para o Exchange Online, adicione "include:spf.protection.outlook.com" ao registro TXT atual.</span><span class="sxs-lookup"><span data-stu-id="daf9e-179">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, add "include:spf.protection.outlook.com" to the current TXT record.</span></span>

    <span data-ttu-id="daf9e-180">Por exemplo, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span><span class="sxs-lookup"><span data-stu-id="daf9e-180">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>

    <span data-ttu-id="daf9e-181">Se você não tiver um registro SPF, modifique o recomendado pela Microsoft 365 para incluir o domínio do seu provedor de email atual e, então, adicione spf.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="daf9e-181">If you don't have an SPF record, modify the one recommended by Microsoft 365 to include the domain for your current email provider, and add spf.protection.outlook.com.</span></span> <span data-ttu-id="daf9e-182">Isso autoriza as mensagens de saída de ambos os sistemas de email.</span><span class="sxs-lookup"><span data-stu-id="daf9e-182">This authorizes outgoing messages from both email systems.</span></span>

### <a name="step-8-set-up-email-forwarding-at-your-current-provider"></a><span data-ttu-id="daf9e-183">Etapa 8: Configure o encaminhamento de email em seu provedor atual</span><span class="sxs-lookup"><span data-stu-id="daf9e-183">Step 8: Set up email forwarding at your current provider</span></span>

<span data-ttu-id="daf9e-184">No seu provedor de email atual, configure o encaminhamento das contas de emails dos usuários para o seu domínio onmicrosoft.com:</span><span class="sxs-lookup"><span data-stu-id="daf9e-184">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>

- <span data-ttu-id="daf9e-185">Encaminhar a caixa de correio do Usuário A para usera@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="daf9e-185">Forward User A mailbox to usera@yourcompany.onmicrosoft.com</span></span>

- <span data-ttu-id="daf9e-186">Encaminhar a caixa de correio do Usuário B para userb@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="daf9e-186">Forward User B mailbox to userb@yourcompany.onmicrosoft.com</span></span>

<span data-ttu-id="daf9e-187">Quando você concluir esta etapa, todos os emails enviados para usera@yourcompany.com e userb@yourcompany.com estarão disponíveis no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="daf9e-187">When you complete this step, all email sent to usera@yourcompany.com and userb@yourcompany.com is available in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="daf9e-188">Entre em contato com seu provedor de email atual para saber as etapas exatas para configurar o encaminhamento de emails.</span><span class="sxs-lookup"><span data-stu-id="daf9e-188">Contact your current email provider for the exact steps to set up email forwarding.</span></span><br/>
> <span data-ttu-id="daf9e-189">Não é necessário manter uma cópia das mensagens no provedor de email atual.</span><span class="sxs-lookup"><span data-stu-id="daf9e-189">You don't need to keep a copy of messages at the current email provider.</span></span><br/>
> <span data-ttu-id="daf9e-190">A maioria dos provedores encaminham emails deixando o Endereço de resposta do remetente intacto, para que as respostas sejam encaminhadas para o remetente original.</span><span class="sxs-lookup"><span data-stu-id="daf9e-190">Most providers forward email by leaving the Reply-to address of the sender intact so that replies go to the original sender.</span></span>

### <a name="step-9-test-mail-flow"></a><span data-ttu-id="daf9e-191">Etapa 9: Teste o fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="daf9e-191">Step 9: Test mail flow</span></span>

1. <span data-ttu-id="daf9e-192">Entre no Outlook Web App usando as credenciais do Usuário A.</span><span class="sxs-lookup"><span data-stu-id="daf9e-192">Sign in to Outlook Web App using the credentials for User A.</span></span>

2. <span data-ttu-id="daf9e-193">Realize estes testes:</span><span class="sxs-lookup"><span data-stu-id="daf9e-193">Perform these tests:</span></span>

    - <span data-ttu-id="daf9e-194">Teste o email local da Microsoft enviando um email, por exemplo, para o usuário B. O email é entregue imediatamente.</span><span class="sxs-lookup"><span data-stu-id="daf9e-194">Test local Microsoft email by sending an email, for example, to User B. The email is delivered immediately.</span></span> <span data-ttu-id="daf9e-195">Neste cenário, a mensagem não é roteada para a caixa de correio do usuário B, no seu servidor original, porque a caixa de correio do Microsoft 365 é local.</span><span class="sxs-lookup"><span data-stu-id="daf9e-195">In this scenario, the message is not routed to the mailbox for User B on your original server because the Microsoft 365 mailbox is local.</span></span>

    - <span data-ttu-id="daf9e-196">Faça um teste enviando um email para um usuário do sistema de email existente, por exemplo, para o usuário C. O email é enviado para a caixa de correio do usuário C no seu servidor de email original.</span><span class="sxs-lookup"><span data-stu-id="daf9e-196">Test email to a user on the existing email system by sending an email, for example, to User C. The email is delivered to the mailbox for User C on your original mail server.</span></span>

    - <span data-ttu-id="daf9e-197">Verifique se o encaminhamento está configurado corretamente a partir de conta externa ou de uma conta de email de funcionário no sistema de email existente.</span><span class="sxs-lookup"><span data-stu-id="daf9e-197">Verify that forwarding is set up properly from an outside account, or from an employee email account on the existing email system.</span></span> <span data-ttu-id="daf9e-198">Por exemplo, a partir da conta do servidor original para o usuário C, ou uma conta do Hotmail, envie um email para o usuário A e verifique se chegará à caixa de correio do Microsoft 365 do usuário A.</span><span class="sxs-lookup"><span data-stu-id="daf9e-198">For example, from the original server account for User C or a Hotmail account, send User A an email and verify that it arrives in the Microsoft 365 mailbox for User A.</span></span>

### <a name="step-10-move-mailbox-contents"></a><span data-ttu-id="daf9e-199">Etapa 10: Mova o conteúdo da caixa de correio</span><span class="sxs-lookup"><span data-stu-id="daf9e-199">Step 10: Move mailbox contents</span></span>

<span data-ttu-id="daf9e-200">Como você está movendo apenas dois usuários de teste, e o usuário A e o usuário B estão usando o Outlook, você pode mover o email abrindo o arquivo .PST antigo no novo perfil do Outlook e copiar as mensagens, os itens do calendário, os contatos e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="daf9e-200">Because you are moving only two test users, and User A and User B are both using Outlook, you can move the email by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, and so on.</span></span> <span data-ttu-id="daf9e-201">Para obter mais informações, confira [Importar emails, contatos e calendário de um arquivo .pst do Outlook](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span><span class="sxs-lookup"><span data-stu-id="daf9e-201">For more information, see [Import email, contacts, and calendar from an Outlook .pst file](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span></span>

<span data-ttu-id="daf9e-202">Depois de importá-los para os locais apropriados na caixa de correio do Microsoft 365, os itens podem ser acessados em qualquer dispositivo, em qualquer lugar.</span><span class="sxs-lookup"><span data-stu-id="daf9e-202">After they’re imported to the appropriate locations in the Microsoft 365 mailbox, the items can be accessed from any device, anywhere.</span></span>

