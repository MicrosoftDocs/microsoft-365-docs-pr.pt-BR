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
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender sobre a inteligência de spoof no Exchange Online Protection (EOP), onde você pode permitir ou bloquear envios de spoofed específicos.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c13c080829236b9a27b6a1a82e1c27256749b5c2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203010"
---
# <a name="configure-spoof-intelligence-in-eop"></a><span data-ttu-id="ffc94-103">Configurar a inteligência de spoof no EOP</span><span class="sxs-lookup"><span data-stu-id="ffc94-103">Configure spoof intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ffc94-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="ffc94-104">**Applies to**</span></span>
- [<span data-ttu-id="ffc94-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ffc94-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ffc94-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="ffc94-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ffc94-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ffc94-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ffc94-108">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações do Exchange Online Protection (EOP) autônomas sem caixas de correio do Exchange Online, as mensagens de email de entrada são automaticamente protegidas contra a falsas informações pelo EOP a partir de outubro de 2018.</span><span class="sxs-lookup"><span data-stu-id="ffc94-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="ffc94-109">O EOP usa a inteligência de fraude como parte da defesa geral da sua organização contra phishing.</span><span class="sxs-lookup"><span data-stu-id="ffc94-109">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="ffc94-110">Para obter mais informações, consulte [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="ffc94-110">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="ffc94-111">Quando um remetente faz a spoofes de um endereço de email, ele parece ser um usuário em um dos domínios da sua organização ou um usuário em um domínio externo que envia emails para sua organização.</span><span class="sxs-lookup"><span data-stu-id="ffc94-111">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="ffc94-112">Os invasores que spoof remetentes para enviar emails de spam ou phishing precisam ser bloqueados.</span><span class="sxs-lookup"><span data-stu-id="ffc94-112">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="ffc94-113">Mas há cenários em que os envios legítimos são spoofing.</span><span class="sxs-lookup"><span data-stu-id="ffc94-113">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="ffc94-114">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ffc94-114">For example:</span></span>

- <span data-ttu-id="ffc94-115">Cenários legítimos para a spoofing de domínios internos:</span><span class="sxs-lookup"><span data-stu-id="ffc94-115">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="ffc94-116">Os envios de terceiros usam seu domínio para enviar emails em massa para seus próprios funcionários para sondagens da empresa.</span><span class="sxs-lookup"><span data-stu-id="ffc94-116">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>
  - <span data-ttu-id="ffc94-117">Uma empresa externa gera e envia atualizações de anúncios ou produtos em seu nome.</span><span class="sxs-lookup"><span data-stu-id="ffc94-117">An external company generates and sends advertising or product updates on your behalf.</span></span>
  - <span data-ttu-id="ffc94-118">Um assistente precisa enviar emails regularmente para outra pessoa em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ffc94-118">An assistant regularly needs to send email for another person within your organization.</span></span>
  - <span data-ttu-id="ffc94-119">Um aplicativo interno envia notificações por email.</span><span class="sxs-lookup"><span data-stu-id="ffc94-119">An internal application sends email notifications.</span></span>

- <span data-ttu-id="ffc94-120">Cenários legítimos para a spoofing de domínios externos:</span><span class="sxs-lookup"><span data-stu-id="ffc94-120">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="ffc94-121">O remetente está em uma lista de email (também conhecida como lista de discussão), e a lista de emails retransmite emails do remetente original para todos os participantes na lista de email.</span><span class="sxs-lookup"><span data-stu-id="ffc94-121">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>
  - <span data-ttu-id="ffc94-122">Uma empresa externa envia emails em nome de outra empresa (por exemplo, um relatório automatizado ou uma empresa de software como serviço).</span><span class="sxs-lookup"><span data-stu-id="ffc94-122">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="ffc94-123">A inteligência de spoof e, especificamente, a política de inteligência de spoof (e somente) padrão, ajuda a garantir que o email empoado enviado por remetentes legítimos não seja capturado em filtros de spam do EOP ou sistemas de email externos, enquanto protege seus usuários contra ataques de spam ou phishing.</span><span class="sxs-lookup"><span data-stu-id="ffc94-123">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="ffc94-124">Você pode gerenciar a inteligência de spoof no Centro de Conformidade & Segurança ou no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="ffc94-124">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ffc94-125">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="ffc94-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ffc94-126">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="ffc94-126">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ffc94-127">Para ir diretamente à página de **Configurações antispam**, use <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="ffc94-127">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="ffc94-128">Para ir diretamente para a página **Anti-phishing,** use <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="ffc94-128">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="ffc94-129">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ffc94-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ffc94-130">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="ffc94-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ffc94-131">Você precisa de permissões em **Exchange Online** antes de poder realizar os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="ffc94-131">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="ffc94-132">Para modificar a política de inteligência de spoof ou habilitar ou  desabilitar a inteligência de spoof, você precisa ser membro dos grupos de função Gerenciamento da Organização ou Administrador **de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="ffc94-132">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="ffc94-133">Para acesso somente leitura à política de inteligência de spoof, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="ffc94-133">For read-only access to the spoof intelligence policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="ffc94-134">Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="ffc94-134">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="ffc94-135">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="ffc94-135">**Notes**:</span></span>

  - <span data-ttu-id="ffc94-136">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ffc94-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ffc94-137">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ffc94-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="ffc94-138">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="ffc94-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="ffc94-139">Para nossas configurações recomendadas para a inteligência de spoof, consulte Configurações de política [anti-phishing](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings)padrão do EOP.</span><span class="sxs-lookup"><span data-stu-id="ffc94-139">For our recommended settings for spoof intelligence, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="ffc94-140">Usar o Centro de Conformidade & segurança para gerenciar os envios com spoofed</span><span class="sxs-lookup"><span data-stu-id="ffc94-140">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="ffc94-141">Se você tiver uma assinatura do Microsoft 365 Enterprise E5 ou tiver comprado separadamente um complemento do Microsoft Defender para Office 365, você também poderá gerenciar os envios que estão spoofando seu domínio por meio do insight [Spoof Intelligence](walkthrough-spoof-intelligence-insight.md).</span><span class="sxs-lookup"><span data-stu-id="ffc94-141">If you have an Microsoft 365 Enterprise E5 subscription or have separately purchased a Microsoft Defender for Office 365 add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="ffc94-142">No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="ffc94-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="ffc94-143">Na página **Configurações anti-spam,** clique em ![ Expandir ícone para expandir a política de inteligência de ](../../media/scc-expand-icon.png) **Spoof.**</span><span class="sxs-lookup"><span data-stu-id="ffc94-143">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![Selecione a política de inteligência de spoof](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="ffc94-145">Faça uma das seguintes seleções:</span><span class="sxs-lookup"><span data-stu-id="ffc94-145">Make one of the following selections:</span></span>

   - <span data-ttu-id="ffc94-146">**Revisar novos envios**</span><span class="sxs-lookup"><span data-stu-id="ffc94-146">**Review new senders**</span></span>
   - <span data-ttu-id="ffc94-147">**Mostrar-me os envios que já revisei**</span><span class="sxs-lookup"><span data-stu-id="ffc94-147">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="ffc94-148">No guia Decidir se esses senders têm permissão para fazer a **spoofe** do seu flyout de usuários que aparece, selecione uma das seguintes guias:</span><span class="sxs-lookup"><span data-stu-id="ffc94-148">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="ffc94-149">**Seus Domínios**: Os senders são os usuários que são depondo em seus domínios internos.</span><span class="sxs-lookup"><span data-stu-id="ffc94-149">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="ffc94-150">**Domínios Externos**: Os senders são os usuários depondo em domínios externos.</span><span class="sxs-lookup"><span data-stu-id="ffc94-150">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="ffc94-151">Clique ![ em Expandir ícone na coluna Permitido a ](../../media/scc-expand-icon.png) **spoof?**</span><span class="sxs-lookup"><span data-stu-id="ffc94-151">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="ffc94-152">Escolha **Sim** para permitir que o remetente spoofed ou escolha **Não** para marcar a mensagem como falsa.</span><span class="sxs-lookup"><span data-stu-id="ffc94-152">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="ffc94-153">A ação é controlada pela política anti-phishing padrão ou políticas anti-phishing personalizadas (o valor padrão é Mover mensagem para a pasta **Lixo Eletrônico**).</span><span class="sxs-lookup"><span data-stu-id="ffc94-153">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="ffc94-154">Para obter mais informações, consulte [Configurações de Spoof em políticas anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="ffc94-154">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![Captura de tela mostrando o sobrevoo de remetentes e se o remetente tem permissão para fazer a spoof](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="ffc94-156">As colunas e os valores que você vê são explicados na lista a seguir:</span><span class="sxs-lookup"><span data-stu-id="ffc94-156">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="ffc94-157">**Usuário com spoofed**: a conta de usuário que está sendo esofada.</span><span class="sxs-lookup"><span data-stu-id="ffc94-157">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="ffc94-158">Esse é o remetente da mensagem no endereço De (também conhecido como endereço) mostrado `5322.From` nos clientes de email.</span><span class="sxs-lookup"><span data-stu-id="ffc94-158">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="ffc94-159">A validade desse endereço não é verificada pelo SPF.</span><span class="sxs-lookup"><span data-stu-id="ffc94-159">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="ffc94-160">Na guia **Seus Domínios,** o valor contém um único endereço de email ou, se o servidor de email de origem estiver spoofando várias contas de usuário, ele contém **Mais de um**.</span><span class="sxs-lookup"><span data-stu-id="ffc94-160">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="ffc94-161">Na guia **Domínios Externos,** o valor contém o domínio do usuário espouado, não o endereço de email completo.</span><span class="sxs-lookup"><span data-stu-id="ffc94-161">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="ffc94-162">**Infraestrutura de** Envio : o domínio encontrado em um registro DET (pesquisa DNS) reverso do endereço IP do servidor de email de origem.</span><span class="sxs-lookup"><span data-stu-id="ffc94-162">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="ffc94-163">Se o endereço IP de origem não tiver registro PTR, a infraestrutura de envio será identificada como \<source IP\> /24 (por exemplo, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="ffc94-163">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

     <span data-ttu-id="ffc94-164">Para obter mais informações sobre fontes de mensagens e envios de mensagens, consulte Uma visão [geral dos padrões de mensagens de email.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span><span class="sxs-lookup"><span data-stu-id="ffc94-164">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="ffc94-165">**# de mensagens**: o número de mensagens da infraestrutura de envio para sua organização que contêm o remetente ou remetentes despojados especificados nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="ffc94-165">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="ffc94-166">**# de reclamações do usuário**: Reclamações registradas por seus usuários contra esse remetente nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="ffc94-166">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="ffc94-167">As reclamações geralmente são na forma de envios de lixo eletrônico para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ffc94-167">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="ffc94-168">**Resultado da** autenticação : um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="ffc94-168">**Authentication result**: One of the following values:</span></span>
      - <span data-ttu-id="ffc94-169">**Passado**: o remetente passou verificações de autenticação de email de remetente (SPF ou DKIM).</span><span class="sxs-lookup"><span data-stu-id="ffc94-169">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="ffc94-170">**Falha**: O remetente falhou nas verificações de autenticação do remetente EOP.</span><span class="sxs-lookup"><span data-stu-id="ffc94-170">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="ffc94-171">**Desconhecido**: o resultado dessas verificações não é conhecido.</span><span class="sxs-lookup"><span data-stu-id="ffc94-171">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="ffc94-172">**Decisão definida por**: Mostra quem determinou se a infraestrutura de envio tem permissão para fazer a spoof do usuário:</span><span class="sxs-lookup"><span data-stu-id="ffc94-172">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>
       - <span data-ttu-id="ffc94-173">**Política de inteligência de spoof** (automática)</span><span class="sxs-lookup"><span data-stu-id="ffc94-173">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="ffc94-174">**Admin** (manual)</span><span class="sxs-lookup"><span data-stu-id="ffc94-174">**Admin** (manual)</span></span>

   - <span data-ttu-id="ffc94-175">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span><span class="sxs-lookup"><span data-stu-id="ffc94-175">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="ffc94-176">**Permitido a spoof?**: Os valores que você vê aqui são:</span><span class="sxs-lookup"><span data-stu-id="ffc94-176">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="ffc94-177">**Sim**: As mensagens da combinação de usuário e de envio de infraestruturas falsas são permitidas e não tratadas como emails falsas.</span><span class="sxs-lookup"><span data-stu-id="ffc94-177">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="ffc94-178">**Não**: As mensagens da combinação de usuário e de envio de infraestruturas falsas são marcadas como falsas.</span><span class="sxs-lookup"><span data-stu-id="ffc94-178">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="ffc94-179">A ação é controlada pela política anti-phishing padrão ou políticas anti-phishing personalizadas (o valor padrão é Mover mensagem para a pasta **Lixo Eletrônico**).</span><span class="sxs-lookup"><span data-stu-id="ffc94-179">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="ffc94-180">Consulte a próxima seção para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ffc94-180">See the next section for more information.</span></span>

     - <span data-ttu-id="ffc94-181">**Alguns usuários** ( somente a guia **Domínios):** uma infraestrutura de envio é a spoofing de vários usuários, onde alguns usuários com spoofed são permitidos e outros não.</span><span class="sxs-lookup"><span data-stu-id="ffc94-181">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="ffc94-182">Use a **guia Detalhada** para ver os endereços específicos.</span><span class="sxs-lookup"><span data-stu-id="ffc94-182">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="ffc94-183">Na parte inferior da página, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ffc94-183">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="ffc94-184">Usar o PowerShell para gerenciar os envios de spoofed</span><span class="sxs-lookup"><span data-stu-id="ffc94-184">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="ffc94-185">Para exibir os envios permitidos e bloqueados em inteligência de spoof, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="ffc94-185">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="ffc94-186">Este exemplo retorna informações detalhadas sobre todos os senders que têm permissão para espocar usuários em seus domínios.</span><span class="sxs-lookup"><span data-stu-id="ffc94-186">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="ffc94-187">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="ffc94-187">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="ffc94-188">Para configurar os envios permitidos e bloqueados na inteligência de spoof, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="ffc94-188">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="ffc94-189">Capture a lista atual de envios esofados detectados escrevendo a saída do cmdlet **Get-PhishFilterPolicy** em um arquivo CSV:</span><span class="sxs-lookup"><span data-stu-id="ffc94-189">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="ffc94-190">Edite o arquivo CSV para adicionar ou modificar os valores **SpoofedUser** (endereço de email) e **AllowedToSpoof** (Sim ou Não).</span><span class="sxs-lookup"><span data-stu-id="ffc94-190">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="ffc94-191">Salve o arquivo, leia o arquivo e armazene o conteúdo como uma variável chamada `$UpdateSpoofedSenders` :</span><span class="sxs-lookup"><span data-stu-id="ffc94-191">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="ffc94-192">Use a `$UpdateSpoofedSenders` variável para configurar a política de inteligência de spoof:</span><span class="sxs-lookup"><span data-stu-id="ffc94-192">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="ffc94-193">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="ffc94-193">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="ffc94-194">Usar o Centro de Conformidade & segurança para configurar a inteligência de spoof</span><span class="sxs-lookup"><span data-stu-id="ffc94-194">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="ffc94-195">As opções de configuração para a inteligência de fraude são descritas em Configurações de [Spoof em políticas anti-phishing.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="ffc94-195">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="ffc94-196">Você pode configurar configurações de inteligência de spoof na política anti-phishing padrão e também em políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="ffc94-196">You can configure spoof intelligence settings in the default anti-phishing policy, and also in custom policies.</span></span> <span data-ttu-id="ffc94-197">Para obter instruções com base em sua assinatura, consulte um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="ffc94-197">For instructions based on your subscription, see one of the following topics:</span></span>

- <span data-ttu-id="ffc94-198">[Configurar políticas anti-phishing no EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="ffc94-198">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="ffc94-199">[Configurar políticas anti-phishing no Microsoft Defender para Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ffc94-199">[Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="ffc94-200">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="ffc94-200">How do you know these procedures worked?</span></span>

<span data-ttu-id="ffc94-201">Para verificar se você configurou a inteligência de spoof com os senders que têm permissão e não têm permissão para fazer a spoof e que você configurou as configurações de inteligência de spoof, use qualquer uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="ffc94-201">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="ffc94-202">No Centro de Conformidade & Segurança,  vá até Política de Gerenciamento de Ameaças Política De expansão de Spoof intelligence selecione Mostrar remetentes Que eu já revisei selecione a guia Seus Domínios ou Domínios Externos e verifique o valor Permitido para a \>  \>  \>  \>  \> **spoof?**   para o remetente.</span><span class="sxs-lookup"><span data-stu-id="ffc94-202">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="ffc94-203">No PowerShell, execute os seguintes comandos para exibir os senders que têm permissão e não têm permissão para fazer a spoof:</span><span class="sxs-lookup"><span data-stu-id="ffc94-203">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="ffc94-204">No PowerShell, execute o seguinte comando para exportar a lista de todos os envios despojados para um arquivo CSV:</span><span class="sxs-lookup"><span data-stu-id="ffc94-204">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="ffc94-205">No Centro de Conformidade & segurança, vá para Política de Gerenciamento de Ameaças  \>  \> **Anti-phishing** ou **anti-phishing atp** e faça uma das seguintes etapas:  </span><span class="sxs-lookup"><span data-stu-id="ffc94-205">In the Security & Compliance Center, go to **Threat management** \> **Policy**  \> **Anti-phishing**  or **ATP anti-phishing**, and do either of the following steps:</span></span>

  - <span data-ttu-id="ffc94-206">Selecione uma política na lista.</span><span class="sxs-lookup"><span data-stu-id="ffc94-206">Select a policy from the list.</span></span> <span data-ttu-id="ffc94-207">No sobrevoo exibido, verifique os valores na seção **Spoof.**</span><span class="sxs-lookup"><span data-stu-id="ffc94-207">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
  - <span data-ttu-id="ffc94-208">Clique **em Política padrão**.</span><span class="sxs-lookup"><span data-stu-id="ffc94-208">Click **Default policy**.</span></span> <span data-ttu-id="ffc94-209">No sobrevoo exibido, verifique os valores na seção **Spoof.**</span><span class="sxs-lookup"><span data-stu-id="ffc94-209">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

- <span data-ttu-id="ffc94-210">No PowerShell do Exchange Online, substitua pelo Padrão AntiPhish do Office365 ou o nome de uma política personalizada e execute o seguinte comando para verificar \<Name\> as configurações:</span><span class="sxs-lookup"><span data-stu-id="ffc94-210">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom policy, and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableSpoofIntelligence,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="ffc94-211">Outras maneiras de gerenciar a fraude e o phishing</span><span class="sxs-lookup"><span data-stu-id="ffc94-211">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="ffc94-212">Seja diligente sobre a proteção contra fraude e phishing.</span><span class="sxs-lookup"><span data-stu-id="ffc94-212">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="ffc94-213">Aqui estão as maneiras relacionadas de verificar os envios que fazem a spoofing do seu domínio e ajudar a impedir que eles danificarem sua organização:</span><span class="sxs-lookup"><span data-stu-id="ffc94-213">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="ffc94-214">Verifique o **Relatório de Email de Spoof.**</span><span class="sxs-lookup"><span data-stu-id="ffc94-214">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="ffc94-215">Você pode usar esse relatório com frequência para exibir e ajudar a gerenciar os envios com spoofed.</span><span class="sxs-lookup"><span data-stu-id="ffc94-215">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="ffc94-216">Para obter informações, consulte [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span><span class="sxs-lookup"><span data-stu-id="ffc94-216">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="ffc94-217">Revise a configuração da Estrutura de Política do Remetente (SPF).</span><span class="sxs-lookup"><span data-stu-id="ffc94-217">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="ffc94-218">Para obter uma introdução rápida à SPF e para configurá-la rapidamente, confira [Configurar a SPF no Microsoft 365 para ajudar a evitar falsificação](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="ffc94-218">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="ffc94-219">Para compreender melhor como o Office 365 usa SPF, para solucionar problemas, ou para saber mais sobre implantações incomuns, como implantações híbridas, comece com [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="ffc94-219">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="ffc94-220">Revise sua configuração DKIM (DomainKeys Identified Mail).</span><span class="sxs-lookup"><span data-stu-id="ffc94-220">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="ffc94-221">Você deve usar o DKIM, além de SPF e DMARC, para ajudar a impedir que os invasores enviem mensagens que pareçam que vêm do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="ffc94-221">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="ffc94-222">O DKIM possibilita adicionar uma assinatura digital a mensagens de email no cabeçalho da mensagem.</span><span class="sxs-lookup"><span data-stu-id="ffc94-222">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="ffc94-223">Para obter informações, [consulte Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="ffc94-223">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="ffc94-224">Revise sua configuração de Autenticação, Relatório e Conformidade (DMARC) baseada em domínio.</span><span class="sxs-lookup"><span data-stu-id="ffc94-224">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="ffc94-225">Implementar o DMARC com SPF e DKIM proporciona proporção adicional contra o spoofing e o phishing no email.</span><span class="sxs-lookup"><span data-stu-id="ffc94-225">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="ffc94-226">O DMARC ajuda os sistemas de recepção de email a determinarem o que fazer com as mensagens enviadas a partir do seu domínio que falharem em verificações de SPF ou de DKIM.</span><span class="sxs-lookup"><span data-stu-id="ffc94-226">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="ffc94-227">Para obter informações, [consulte Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="ffc94-227">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>