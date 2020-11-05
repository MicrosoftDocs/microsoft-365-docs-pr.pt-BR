---
title: Configurar a inteligência contra falsificação
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender sobre a inteligência de falsificação na proteção do Exchange Online (EOP), onde você pode permitir ou bloquear remetentes falsificados específicos.
ms.openlocfilehash: 4d40dae9518b451affc11c6666ee8f7454eceff3
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920639"
---
# <a name="configure-spoof-intelligence-in-eop"></a><span data-ttu-id="04ed0-103">Configurar o spoof Intelligence no EOP</span><span class="sxs-lookup"><span data-stu-id="04ed0-103">Configure spoof intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="04ed0-104">Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, as mensagens de email de entrada são protegidas automaticamente contra falsificação por EOP a partir de outubro de 2018.</span><span class="sxs-lookup"><span data-stu-id="04ed0-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="04ed0-105">O EOP usa a inteligência de falsificação como parte da defesa geral da sua organização contra phishing.</span><span class="sxs-lookup"><span data-stu-id="04ed0-105">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="04ed0-106">Para obter mais informações, consulte [proteção contra falsificação no EOP](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="04ed0-106">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="04ed0-107">Quando um remetente falsifica um endereço de email, ele parece ser um usuário em um dos domínios da sua organização ou um usuário em um domínio externo que envia emails para sua organização.</span><span class="sxs-lookup"><span data-stu-id="04ed0-107">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="04ed0-108">Invasores que falsificam remetentes para enviar spam ou phishing email precisam ser bloqueados.</span><span class="sxs-lookup"><span data-stu-id="04ed0-108">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="04ed0-109">Mas há situações em que remetentes legítimos estão falsificando.</span><span class="sxs-lookup"><span data-stu-id="04ed0-109">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="04ed0-110">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="04ed0-110">For example:</span></span>

- <span data-ttu-id="04ed0-111">Cenários legítimos para falsificação de domínios internos:</span><span class="sxs-lookup"><span data-stu-id="04ed0-111">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="04ed0-112">Remetentes de terceiros usam seu domínio para enviar emails em massa aos seus próprios funcionários para pesquisas da empresa.</span><span class="sxs-lookup"><span data-stu-id="04ed0-112">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>
  - <span data-ttu-id="04ed0-113">Uma empresa externa gera e envia anúncios ou atualizações de produtos em seu nome.</span><span class="sxs-lookup"><span data-stu-id="04ed0-113">An external company generates and sends advertising or product updates on your behalf.</span></span>
  - <span data-ttu-id="04ed0-114">Um assistente precisa regularmente enviar emails para outra pessoa em sua organização.</span><span class="sxs-lookup"><span data-stu-id="04ed0-114">An assistant regularly needs to send email for another person within your organization.</span></span>
  - <span data-ttu-id="04ed0-115">Um aplicativo interno envia notificações por email.</span><span class="sxs-lookup"><span data-stu-id="04ed0-115">An internal application sends email notifications.</span></span>

- <span data-ttu-id="04ed0-116">Cenários legítimos para falsificação de domínios externos:</span><span class="sxs-lookup"><span data-stu-id="04ed0-116">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="04ed0-117">O remetente está em uma lista de endereçamento (também conhecida como lista de discussão) e a lista de endereçamento envia emails do remetente original para todos os participantes na lista de endereçamento.</span><span class="sxs-lookup"><span data-stu-id="04ed0-117">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>
  - <span data-ttu-id="04ed0-118">Uma empresa externa envia emails em nome de outra empresa (por exemplo, um relatório automatizado ou uma empresa de software como serviço).</span><span class="sxs-lookup"><span data-stu-id="04ed0-118">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="04ed0-119">A inteligência de falsificação e, especificamente, a política de inteligência de fraudes padrão (e apenas) ajuda a garantir que o email falso enviado por remetentes legítimos não seja detectado nos filtros de spam do EOP ou sistemas de email externos, enquanto protege seus usuários contra ataques de spam ou phishing.</span><span class="sxs-lookup"><span data-stu-id="04ed0-119">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="04ed0-120">Você pode gerenciar a inteligência de falsificação no centro de conformidade & segurança ou no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="04ed0-120">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="04ed0-121">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="04ed0-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="04ed0-122">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="04ed0-122">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="04ed0-123">Para ir diretamente à página de **Configurações antispam** , use <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="04ed0-123">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="04ed0-124">Para ir diretamente para a página **anti-phishing** , use <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="04ed0-124">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="04ed0-125">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="04ed0-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="04ed0-126">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="04ed0-126">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="04ed0-127">Você precisa ter permissões atribuídas antes de poder executar os procedimentos neste tópico:</span><span class="sxs-lookup"><span data-stu-id="04ed0-127">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="04ed0-128">Para modificar a política de inteligência de spoof ou habilitar ou desabilitar a inteligência de spoof, você precisa ser membro de um dos grupos de função a seguir:</span><span class="sxs-lookup"><span data-stu-id="04ed0-128">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="04ed0-129">**Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="04ed0-129">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="04ed0-130">**Gerenciamento de organizações** ou **Gerenciamento de higiene** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="04ed0-130">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="04ed0-131">Para acesso somente leitura à política de inteligência de falsificação, você precisa ser membro de um dos grupos de função a seguir:</span><span class="sxs-lookup"><span data-stu-id="04ed0-131">For read-only access to the spoof intelligence policy, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="04ed0-132">**Leitor de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="04ed0-132">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="04ed0-133">**Gerenciamento da organização Somente visualização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="04ed0-133">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="04ed0-134">Para obter as configurações recomendadas para a inteligência de falsificação, confira [configurações de política anti-phishing padrão do EOP](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="04ed0-134">For our recommended settings for spoof intelligence, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="04ed0-135">Usar o centro de conformidade de & de segurança para gerenciar remetentes falsificados</span><span class="sxs-lookup"><span data-stu-id="04ed0-135">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="04ed0-136">Se você tiver uma assinatura do Microsoft 365 Enterprise E5 ou tiver adquirido separadamente um complemento do Microsoft defender para Office 365, também poderá gerenciar os remetentes que estão falsificando seu domínio por meio da [compreensão de inteligência de falsificação](walkthrough-spoof-intelligence-insight.md).</span><span class="sxs-lookup"><span data-stu-id="04ed0-136">If you have an Microsoft 365 Enterprise E5 subscription or have separately purchased an Microsoft Defender for Office 365 add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="04ed0-137">No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="04ed0-137">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="04ed0-138">Na página **configurações antispam** , clique em ![ expandir ícone ](../../media/scc-expand-icon.png) para expandir política de **inteligência de fraude**.</span><span class="sxs-lookup"><span data-stu-id="04ed0-138">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![Selecione a política de inteligência de spoof](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="04ed0-140">Faça uma das seguintes seleções:</span><span class="sxs-lookup"><span data-stu-id="04ed0-140">Make one of the following selections:</span></span>

   - <span data-ttu-id="04ed0-141">**Revisar novos remetentes**</span><span class="sxs-lookup"><span data-stu-id="04ed0-141">**Review new senders**</span></span>
   - <span data-ttu-id="04ed0-142">**Mostrar os remetentes que eu já revisei**</span><span class="sxs-lookup"><span data-stu-id="04ed0-142">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="04ed0-143">Em **decidir se esses remetentes têm permissão para falsificar o** submenu de usuários exibido, selecione uma das seguintes guias:</span><span class="sxs-lookup"><span data-stu-id="04ed0-143">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="04ed0-144">**Seus domínios** : remetentes que falsificam usuários em seus domínios internos.</span><span class="sxs-lookup"><span data-stu-id="04ed0-144">**Your Domains** : Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="04ed0-145">**Domínios externos** : remetentes que falsificam usuários em domínios externos.</span><span class="sxs-lookup"><span data-stu-id="04ed0-145">**External Domains** : Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="04ed0-146">Clique em ![ expandir ícone ](../../media/scc-expand-icon.png) na coluna **permitido para falsificação?** .</span><span class="sxs-lookup"><span data-stu-id="04ed0-146">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="04ed0-147">Escolha **Sim** para permitir o remetente falsificado ou escolha **não** para marcar a mensagem como falsificada.</span><span class="sxs-lookup"><span data-stu-id="04ed0-147">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="04ed0-148">A ação é controlada pela política anti-phishing padrão ou políticas anti-phishing personalizadas (o valor padrão é **mover mensagem para a pasta lixo eletrônico** ).</span><span class="sxs-lookup"><span data-stu-id="04ed0-148">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder** ).</span></span> <span data-ttu-id="04ed0-149">Para obter mais informações, consulte [configurações de spoof em políticas anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="04ed0-149">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![Captura de tela mostrando o submenu de remetentes falsificados e se o remetente tem permissão para falsificar](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="04ed0-151">As colunas e os valores que você vê são explicados na lista a seguir:</span><span class="sxs-lookup"><span data-stu-id="04ed0-151">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="04ed0-152">**Usuário falsificado** : a conta de usuário que está sendo falsificada.</span><span class="sxs-lookup"><span data-stu-id="04ed0-152">**Spoofed user** : The user account that's being spoofed.</span></span> <span data-ttu-id="04ed0-153">Este é o remetente da mensagem no endereço de (também conhecido como o `5322.From` endereço) que é mostrado nos clientes de email.</span><span class="sxs-lookup"><span data-stu-id="04ed0-153">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="04ed0-154">A validade desse endereço não é verificada por SPF.</span><span class="sxs-lookup"><span data-stu-id="04ed0-154">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="04ed0-155">Na guia **domínios** , o valor contém um único endereço de email ou, se o servidor de email de origem estiver falsificando várias contas de usuário, ele conterá **mais de um**.</span><span class="sxs-lookup"><span data-stu-id="04ed0-155">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="04ed0-156">Na guia **domínios externos** , o valor contém o domínio do usuário falsificado, e não o endereço de email completo.</span><span class="sxs-lookup"><span data-stu-id="04ed0-156">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="04ed0-157">**Infraestrutura de envio** : o domínio encontrado em uma pesquisa de DNS inversa (registro PTR) do endereço IP do servidor de email de origem ou o endereço IP, se a fonte não tiver um registro PTR.</span><span class="sxs-lookup"><span data-stu-id="04ed0-157">**Sending Infrastructure** : The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address, or the IP address if the source has no PTR record.</span></span>

     <span data-ttu-id="04ed0-158">Para obter mais informações sobre fontes de mensagens e remetentes de mensagens, consulte [uma visão geral dos padrões de mensagens de email](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span><span class="sxs-lookup"><span data-stu-id="04ed0-158">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="04ed0-159">**n º de mensagens** : o número de mensagens da infraestrutura de envio para sua organização que contêm o remetente falsificado especificado ou remetentes nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="04ed0-159">**# of messages** : The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="04ed0-160">**n º de reclamações de usuários** : reclamações arquivadas pelos usuários em relação a esse remetente nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="04ed0-160">**# of user complaints** : Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="04ed0-161">As reclamações geralmente estão na forma de envios de lixo eletrônico para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="04ed0-161">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="04ed0-162">**Resultado da autenticação** : um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="04ed0-162">**Authentication result** : One of the following values:</span></span>

      - <span data-ttu-id="04ed0-163">**Aprovado** : o remetente passou por verificações de autenticação de email do remetente (SPF ou DKIM).</span><span class="sxs-lookup"><span data-stu-id="04ed0-163">**Passed** : The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="04ed0-164">**Falha** : o remetente falhou EOP verificações de autenticação do remetente.</span><span class="sxs-lookup"><span data-stu-id="04ed0-164">**Failed** : The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="04ed0-165">**Desconhecido** : o resultado dessas verificações não é conhecido.</span><span class="sxs-lookup"><span data-stu-id="04ed0-165">**Unknown** : The result of these checks isn't known.</span></span>

   - <span data-ttu-id="04ed0-166">**Decisão definida por** : mostra quem determinou se a infraestrutura de envio tem permissão para falsificar o usuário:</span><span class="sxs-lookup"><span data-stu-id="04ed0-166">**Decision set by** : Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>

       - <span data-ttu-id="04ed0-167">**Política de inteligência de spoof** (automática)</span><span class="sxs-lookup"><span data-stu-id="04ed0-167">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="04ed0-168">**Administrador** (manual)</span><span class="sxs-lookup"><span data-stu-id="04ed0-168">**Admin** (manual)</span></span>

   - <span data-ttu-id="04ed0-169">**Última vista** : a última data em que uma mensagem foi recebida da infraestrutura de envio que contém o usuário falsificado.</span><span class="sxs-lookup"><span data-stu-id="04ed0-169">**Last seen** : The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="04ed0-170">**Permitido para falsificar?** : os valores que você vê aqui são:</span><span class="sxs-lookup"><span data-stu-id="04ed0-170">**Allowed to spoof?** : The values that you see here are:</span></span>

     - <span data-ttu-id="04ed0-171">**Sim** : as mensagens da combinação de usuário falsificado e infraestrutura de envio são permitidas e não são tratadas como email falsificado.</span><span class="sxs-lookup"><span data-stu-id="04ed0-171">**Yes** : Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>

     - <span data-ttu-id="04ed0-172">**No** : as mensagens da combinação de usuário falsificado e infraestrutura de envio são marcadas como falsificadas.</span><span class="sxs-lookup"><span data-stu-id="04ed0-172">**No** : Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="04ed0-173">A ação é controlada pela política anti-phishing padrão ou políticas anti-phishing personalizadas (o valor padrão é **mover mensagem para a pasta lixo eletrônico** ).</span><span class="sxs-lookup"><span data-stu-id="04ed0-173">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder** ).</span></span> <span data-ttu-id="04ed0-174">Consulte a próxima seção para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="04ed0-174">See the next section for more information.</span></span>

     - <span data-ttu-id="04ed0-175">**Alguns usuários** (apenas **a guia Domínios** ): uma infraestrutura de envio está falsificando vários usuários, onde alguns usuários falsificados são permitidos e outros não.</span><span class="sxs-lookup"><span data-stu-id="04ed0-175">**Some users** ( **Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="04ed0-176">Use a guia **detalhada** para ver os endereços específicos.</span><span class="sxs-lookup"><span data-stu-id="04ed0-176">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="04ed0-177">Na parte inferior da página, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="04ed0-177">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="04ed0-178">Usar o PowerShell para gerenciar remetentes falsificados</span><span class="sxs-lookup"><span data-stu-id="04ed0-178">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="04ed0-179">Para exibir os remetentes permitidos e bloqueados no spoof Intelligence, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="04ed0-179">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="04ed0-180">Este exemplo retorna informações detalhadas sobre todos os remetentes que têm permissão para falsificar usuários em seus domínios.</span><span class="sxs-lookup"><span data-stu-id="04ed0-180">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="04ed0-181">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="04ed0-181">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="04ed0-182">Para configurar remetentes permitidos e bloqueados no spoof Intelligence, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="04ed0-182">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="04ed0-183">Capture a lista atual de remetentes falsificados detectados escrevendo a saída do cmdlet **Get-PhishFilterPolicy** para um arquivo CSV:</span><span class="sxs-lookup"><span data-stu-id="04ed0-183">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="04ed0-184">Edite o arquivo CSV para adicionar ou modificar os valores de **SpoofedUser** (endereço de email) e **AllowedToSpoof** (Sim ou não).</span><span class="sxs-lookup"><span data-stu-id="04ed0-184">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="04ed0-185">Salve o arquivo, leia o arquivo e armazene o conteúdo como uma variável chamada `$UpdateSpoofedSenders` :</span><span class="sxs-lookup"><span data-stu-id="04ed0-185">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="04ed0-186">Use a `$UpdateSpoofedSenders` variável para configurar a política de inteligência de falsificação:</span><span class="sxs-lookup"><span data-stu-id="04ed0-186">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="04ed0-187">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="04ed0-187">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="04ed0-188">Usar o centro de conformidade de & de segurança para configurar o spoof Intelligence</span><span class="sxs-lookup"><span data-stu-id="04ed0-188">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="04ed0-189">As opções de configuração para a inteligência de falsificação são descritas em [configurações de spoof em políticas anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="04ed0-189">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="04ed0-190">Você pode definir as configurações de inteligência de spoofing na política anti-phishing padrão e também em políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="04ed0-190">You can configure spoof intelligence settings in the default anti-phishing policy, and also in custom policies.</span></span> <span data-ttu-id="04ed0-191">Para obter instruções com base em sua assinatura, consulte um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="04ed0-191">For instructions based on your subscription, see one of the following topics:</span></span>

- <span data-ttu-id="04ed0-192">[Configure as políticas anti-phishing no EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="04ed0-192">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="04ed0-193">[Configure as políticas anti-phishing no Microsoft defender para Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="04ed0-193">[Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="04ed0-194">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="04ed0-194">How do you know these procedures worked?</span></span>

<span data-ttu-id="04ed0-195">Para verificar se você configurou a inteligência de spoof com remetentes que são permitidos e não têm permissão para falsificar e se você configurou as configurações de inteligência de spoof, use qualquer uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="04ed0-195">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="04ed0-196">No centro de conformidade e segurança &, vá para política de **Gerenciamento de ameaças** \> **Policy** \> **anti-spam** \> expanda **política de inteligência de falsificação** \> selecionar **Mostrar remetentes que eu já revisei** \> Selecione a guia **domínios** ou **domínios externos** e verifique o valor **permitido para falsificação?** para o remetente.</span><span class="sxs-lookup"><span data-stu-id="04ed0-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="04ed0-197">No PowerShell, execute os seguintes comandos para exibir os remetentes que são permitidos e não podem ser falsificados:</span><span class="sxs-lookup"><span data-stu-id="04ed0-197">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="04ed0-198">No PowerShell, execute o seguinte comando para exportar a lista de todos os remetentes falsificados para um arquivo CSV:</span><span class="sxs-lookup"><span data-stu-id="04ed0-198">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="04ed0-199">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** anti-phishing \> **Policy** \> **Anti-phishing** ou **anti-phishing de ATP** e execute uma das seguintes etapas:  </span><span class="sxs-lookup"><span data-stu-id="04ed0-199">In the Security & Compliance Center, go to **Threat management** \> **Policy**  \> **Anti-phishing**  or **ATP anti-phishing** , and do either of the following steps:</span></span>

  - <span data-ttu-id="04ed0-200">Selecione uma política na lista.</span><span class="sxs-lookup"><span data-stu-id="04ed0-200">Select a policy from the list.</span></span> <span data-ttu-id="04ed0-201">No submenu exibido, verifique os valores na seção **spoof** .</span><span class="sxs-lookup"><span data-stu-id="04ed0-201">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
  - <span data-ttu-id="04ed0-202">Clique em **política padrão**.</span><span class="sxs-lookup"><span data-stu-id="04ed0-202">Click **Default policy**.</span></span> <span data-ttu-id="04ed0-203">No submenu exibido, verifique os valores na seção **spoof** .</span><span class="sxs-lookup"><span data-stu-id="04ed0-203">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

- <span data-ttu-id="04ed0-204">No PowerShell do Exchange Online, substitua \<Name\> com o padrão de antiphishing do Office365 ou o nome de uma política personalizada e execute o seguinte comando para verificar as configurações:</span><span class="sxs-lookup"><span data-stu-id="04ed0-204">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom policy, and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableAntiSpoofEnforcement,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="04ed0-205">Outras maneiras de gerenciar falsificação e phishing</span><span class="sxs-lookup"><span data-stu-id="04ed0-205">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="04ed0-206">Fique à medida sobre falsificação e proteção contra phishing.</span><span class="sxs-lookup"><span data-stu-id="04ed0-206">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="04ed0-207">Aqui estão as maneiras relacionadas à verificação de remetentes que falsificam seu domínio e ajudam a evitar que eles danifiquem sua organização:</span><span class="sxs-lookup"><span data-stu-id="04ed0-207">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="04ed0-208">Verifique o **relatório de falsificação de emails**.</span><span class="sxs-lookup"><span data-stu-id="04ed0-208">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="04ed0-209">Você pode usar esse relatório com frequência para exibir e ajudar a gerenciar remetentes falsificados.</span><span class="sxs-lookup"><span data-stu-id="04ed0-209">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="04ed0-210">Para saber mais, confira [relatório de detecções de spoof](view-email-security-reports.md#spoof-detections-report).</span><span class="sxs-lookup"><span data-stu-id="04ed0-210">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="04ed0-211">Revise a configuração da estrutura de política de remetente (SPF).</span><span class="sxs-lookup"><span data-stu-id="04ed0-211">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="04ed0-212">Para obter uma introdução rápida à SPF e para configurá-la rapidamente, confira [Configurar a SPF no Microsoft 365 para ajudar a evitar falsificação](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="04ed0-212">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="04ed0-213">Para compreender melhor como o Office 365 usa SPF, para solucionar problemas, ou para saber mais sobre implantações incomuns, como implantações híbridas, comece com [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="04ed0-213">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="04ed0-214">Revise sua configuração de email identificado do DomainKeys (DKIM).</span><span class="sxs-lookup"><span data-stu-id="04ed0-214">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="04ed0-215">Você deve usar o DKIM além de SPF e DMARC para ajudar a impedir que os invasores enviem mensagens parecidas com o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="04ed0-215">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="04ed0-216">O DKIM possibilita adicionar uma assinatura digital a mensagens de email no cabeçalho da mensagem.</span><span class="sxs-lookup"><span data-stu-id="04ed0-216">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="04ed0-217">Para saber mais, confira [usar DKIM para validar emails de saída enviados do seu domínio personalizado no Office 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="04ed0-217">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="04ed0-218">Revise a configuração de autenticação, geração de relatórios e conformidade da mensagem baseada em domínio (DMARC).</span><span class="sxs-lookup"><span data-stu-id="04ed0-218">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="04ed0-219">Implementar o DMARC com SPF e DKIM proporciona proporção adicional contra o spoofing e o phishing no email.</span><span class="sxs-lookup"><span data-stu-id="04ed0-219">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="04ed0-220">O DMARC ajuda os sistemas de recepção de email a determinarem o que fazer com as mensagens enviadas a partir do seu domínio que falharem em verificações de SPF ou de DKIM.</span><span class="sxs-lookup"><span data-stu-id="04ed0-220">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="04ed0-221">Para saber mais, confira [usar DMARC para validar emails no Office 365](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="04ed0-221">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>
