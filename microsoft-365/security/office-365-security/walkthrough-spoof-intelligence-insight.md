---
title: Gerenciar envios com spoofed usando a política de inteligência de spoof e o insight de inteligência de spoof
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a usar a política de inteligência de spoof e o insight de inteligência spoof para permitir ou bloquear os envios esofados detectados.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0e5c83bc50197e30c12f8f7aeedc83930d7ff5e
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793203"
---
# <a name="manage-spoofed-senders-using-the-spoof-intelligence-policy-and-spoof-intelligence-insight-in-eop"></a><span data-ttu-id="3acc2-103">Gerenciar envios com spoofed usando a política de inteligência de spoof e o insight de inteligência de spoof no EOP</span><span class="sxs-lookup"><span data-stu-id="3acc2-103">Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3acc2-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="3acc2-104">**Applies to**</span></span>
- [<span data-ttu-id="3acc2-105">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="3acc2-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="3acc2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3acc2-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="3acc2-107">Este artigo descreve a experiência de gerenciamento de remetentes despojado mais antiga que está sendo substituída.</span><span class="sxs-lookup"><span data-stu-id="3acc2-107">This article describes the older spoofed sender management experience that's being replaced.</span></span> <span data-ttu-id="3acc2-108">Para obter mais informações sobre a nova experiência, consulte [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="3acc2-108">For more information about the new experience, see [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md)</span></span>

<span data-ttu-id="3acc2-109">Em organizações Microsoft 365 com caixas de correio no Exchange Online ou organizações de Proteção do Exchange Online (EOP) autônomas sem caixas de correio Exchange Online, as mensagens de email de entrada são automaticamente protegidas contra a falsas informações pelo EOP a partir de outubro de 2018.</span><span class="sxs-lookup"><span data-stu-id="3acc2-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="3acc2-110">O EOP usa **a inteligência de** fraude como parte da defesa geral da sua organização contra phishing.</span><span class="sxs-lookup"><span data-stu-id="3acc2-110">EOP uses **spoof intelligence** as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="3acc2-111">Para obter mais informações, consulte [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="3acc2-111">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="3acc2-112">A política de inteligência de **spoof** (e somente) padrão ajuda a garantir que os emails espoados enviados por remetentes legítimos não são capturados em filtros de spam do EOP enquanto protegem seus usuários contra ataques de spam ou phishing.</span><span class="sxs-lookup"><span data-stu-id="3acc2-112">The default (and only) **spoof intelligence policy** helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters while protecting your users from spam or phishing attacks.</span></span> <span data-ttu-id="3acc2-113">Você também pode usar o insight de inteligência **Spoof** para determinar rapidamente quais envios externos estão enviando emails não autenticados (mensagens de domínios que não passam verificações SPF, DKIM ou DMARC).</span><span class="sxs-lookup"><span data-stu-id="3acc2-113">You can also use the **Spoof intelligence insight** to quickly determine which external senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="3acc2-114">Você pode gerenciar a inteligência de spoof no Centro de Conformidade & Segurança ou no PowerShell (Exchange Online PowerShell para organizações Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem Exchange Online caixas de correio).</span><span class="sxs-lookup"><span data-stu-id="3acc2-114">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3acc2-115">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="3acc2-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3acc2-116">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="3acc2-116">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span>
  - <span data-ttu-id="3acc2-117">Para ir diretamente para a página **Configurações anti-spam** para a política de inteligência de spoof, use <https://protection.office.com/antispam> .</span><span class="sxs-lookup"><span data-stu-id="3acc2-117">To go directly to the **Anti-spam settings** page for the spoof intelligence policy, use <https://protection.office.com/antispam>.</span></span>
  - <span data-ttu-id="3acc2-118">Para ir diretamente para a página **Painel de segurança** para o insight de inteligência de spoof, use <https://protection.office.com/searchandinvestigation/dashboard> .</span><span class="sxs-lookup"><span data-stu-id="3acc2-118">To go directly to the **Security dashboard** page for the spoof intelligence insight, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

- <span data-ttu-id="3acc2-119">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="3acc2-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="3acc2-120">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="3acc2-120">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="3acc2-121">Você precisa de permissões em **Exchange Online** antes de poder realizar os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="3acc2-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="3acc2-122">Para modificar a política de inteligência de spoof ou habilitar ou  desabilitar a inteligência de spoof, você precisa ser membro dos grupos de função Gerenciamento da Organização ou Administrador **de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="3acc2-122">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="3acc2-123">Para acesso somente leitura à política de inteligência de spoof, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="3acc2-123">For read-only access to the spoof intelligence policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="3acc2-124">Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="3acc2-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="3acc2-125">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="3acc2-125">**Notes**:</span></span>

  - <span data-ttu-id="3acc2-126">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3acc2-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="3acc2-127">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="3acc2-127">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="3acc2-128">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="3acc2-128">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="3acc2-129">As opções de inteligência de spoof são descritas em Configurações de [Spoof em políticas anti-phishing.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="3acc2-129">The options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="3acc2-130">Você pode habilitar, desabilitar e configurar as configurações de inteligência de spoof em políticas anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="3acc2-130">You can enable, disable, and configure the spoof intelligence settings in anti-phishing policies.</span></span> <span data-ttu-id="3acc2-131">Para obter instruções com base em sua assinatura, consulte um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="3acc2-131">For instructions based on your subscription, see one of the following topics:</span></span>

  - <span data-ttu-id="3acc2-132">[Configurar políticas anti-phishing no EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="3acc2-132">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>
  - <span data-ttu-id="3acc2-133">[Configure políticas anti-phishing no Microsoft Defender para Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="3acc2-133">[Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="3acc2-134">Para nossas configurações recomendadas para a inteligência de spoof, consulte Configurações de política [anti-phishing do EOP.](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="3acc2-134">For our recommended settings for spoof intelligence, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings).</span></span>

## <a name="manage-spoofed-senders"></a><span data-ttu-id="3acc2-135">Gerenciar envios com spoofed</span><span class="sxs-lookup"><span data-stu-id="3acc2-135">Manage spoofed senders</span></span>

<span data-ttu-id="3acc2-136">Há duas maneiras de permitir e bloquear os envios de spoofed:</span><span class="sxs-lookup"><span data-stu-id="3acc2-136">There are two ways to allow and block spoofed senders:</span></span>

- [<span data-ttu-id="3acc2-137">Usar a política de inteligência de spoof</span><span class="sxs-lookup"><span data-stu-id="3acc2-137">Use the spoof intelligence policy</span></span>](#manage-spoofed-senders-in-the-spoof-intelligence-policy)
- [<span data-ttu-id="3acc2-138">Usar o insight de inteligência de spoof</span><span class="sxs-lookup"><span data-stu-id="3acc2-138">Use the spoof intelligence insight</span></span>](#manage-spoofed-senders-in-the-spoof-intelligence-insight)

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-policy"></a><span data-ttu-id="3acc2-139">Gerenciar envios com spoofed na política de inteligência de spoof</span><span class="sxs-lookup"><span data-stu-id="3acc2-139">Manage spoofed senders in the spoof intelligence policy</span></span>

1. <span data-ttu-id="3acc2-140">No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="3acc2-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="3acc2-141">Na página **Configurações anti-spam,** clique em ![ Expandir ícone para expandir a política de inteligência de ](../../media/scc-expand-icon.png) **Spoof.**</span><span class="sxs-lookup"><span data-stu-id="3acc2-141">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![Selecione a política de inteligência de spoof](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="3acc2-143">Faça uma das seguintes seleções:</span><span class="sxs-lookup"><span data-stu-id="3acc2-143">Make one of the following selections:</span></span>

   - <span data-ttu-id="3acc2-144">**Revisar novos envios**</span><span class="sxs-lookup"><span data-stu-id="3acc2-144">**Review new senders**</span></span>
   - <span data-ttu-id="3acc2-145">**Mostrar-me os envios que já revisei**</span><span class="sxs-lookup"><span data-stu-id="3acc2-145">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="3acc2-146">No guia Decidir se esses senders têm permissão para fazer a **spoofe** do seu flyout de usuários que aparece, selecione uma das seguintes guias:</span><span class="sxs-lookup"><span data-stu-id="3acc2-146">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="3acc2-147">**Seus Domínios**: Os senders são os usuários que são depondo em seus domínios internos.</span><span class="sxs-lookup"><span data-stu-id="3acc2-147">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="3acc2-148">**Domínios Externos**: Os senders são os usuários depondo em domínios externos.</span><span class="sxs-lookup"><span data-stu-id="3acc2-148">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="3acc2-149">Clique ![ em Expandir ícone na coluna Permitido a ](../../media/scc-expand-icon.png) **spoof?**</span><span class="sxs-lookup"><span data-stu-id="3acc2-149">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="3acc2-150">Escolha **Sim** para permitir que o remetente spoofed ou escolha **Não** para marcar a mensagem como falsa.</span><span class="sxs-lookup"><span data-stu-id="3acc2-150">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="3acc2-151">A ação é controlada pela política anti-phishing padrão ou políticas anti-phishing personalizadas (o valor padrão é Mover mensagem para a pasta **Lixo Eletrônico**).</span><span class="sxs-lookup"><span data-stu-id="3acc2-151">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="3acc2-152">Para saber mais, confira [Configurações de inteligência contra falsificação nas políticas anti phishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="3acc2-152">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![Captura de tela mostrando o sobrevoo de remetentes e se o remetente tem permissão para fazer a spoof](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="3acc2-154">As colunas e os valores que você vê são explicados na lista a seguir:</span><span class="sxs-lookup"><span data-stu-id="3acc2-154">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="3acc2-155">**Usuário com spoofed**: a conta de usuário que está sendo esofada.</span><span class="sxs-lookup"><span data-stu-id="3acc2-155">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="3acc2-156">Esse é o remetente da mensagem no endereço De (também conhecido como endereço) mostrado `5322.From` nos clientes de email.</span><span class="sxs-lookup"><span data-stu-id="3acc2-156">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="3acc2-157">A validade desse endereço não é verificada pelo SPF.</span><span class="sxs-lookup"><span data-stu-id="3acc2-157">The validity of this address is not checked by SPF.</span></span>
     - <span data-ttu-id="3acc2-158">Na guia **Seus Domínios,** o valor contém um único endereço de email ou, se o servidor de email de origem estiver spoofando várias contas de usuário, ele contém **Mais de um**.</span><span class="sxs-lookup"><span data-stu-id="3acc2-158">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>
     - <span data-ttu-id="3acc2-159">Na guia **Domínios Externos,** o valor contém o domínio do usuário espouado, não o endereço de email completo.</span><span class="sxs-lookup"><span data-stu-id="3acc2-159">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="3acc2-160">**Infraestrutura de** Envio : o domínio encontrado em um registro DET (pesquisa DNS) reverso do endereço IP do servidor de email de origem.</span><span class="sxs-lookup"><span data-stu-id="3acc2-160">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="3acc2-161">Se o endereço IP de origem não tiver registro PTR, a infraestrutura de envio será identificada como \<source IP\> /24 (por exemplo, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="3acc2-161">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

     <span data-ttu-id="3acc2-162">Para obter mais informações sobre fontes de mensagens e envios de mensagens, consulte Uma visão [geral dos padrões de mensagens de email.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span><span class="sxs-lookup"><span data-stu-id="3acc2-162">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="3acc2-163">**# de mensagens**: o número de mensagens da infraestrutura de envio para sua organização que contêm o remetente ou remetentes despojados especificados nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="3acc2-163">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="3acc2-164">**# de reclamações do usuário**: Reclamações registradas por seus usuários contra esse remetente nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="3acc2-164">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="3acc2-165">As reclamações geralmente são na forma de envios de lixo eletrônico para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3acc2-165">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="3acc2-166">**Resultado da** autenticação : um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="3acc2-166">**Authentication result**: One of the following values:</span></span>
      - <span data-ttu-id="3acc2-167">**Passado**: o remetente passou verificações de autenticação de email de remetente (SPF ou DKIM).</span><span class="sxs-lookup"><span data-stu-id="3acc2-167">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="3acc2-168">**Falha**: O remetente falhou nas verificações de autenticação do remetente EOP.</span><span class="sxs-lookup"><span data-stu-id="3acc2-168">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="3acc2-169">**Desconhecido**: o resultado dessas verificações não é conhecido.</span><span class="sxs-lookup"><span data-stu-id="3acc2-169">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="3acc2-170">**Decisão definida por**: Mostra quem determinou se a infraestrutura de envio tem permissão para fazer a spoof do usuário:</span><span class="sxs-lookup"><span data-stu-id="3acc2-170">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>
       - <span data-ttu-id="3acc2-171">**Política de inteligência de spoof** (automática)</span><span class="sxs-lookup"><span data-stu-id="3acc2-171">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="3acc2-172">**Admin** (manual)</span><span class="sxs-lookup"><span data-stu-id="3acc2-172">**Admin** (manual)</span></span>

   - <span data-ttu-id="3acc2-173">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span><span class="sxs-lookup"><span data-stu-id="3acc2-173">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="3acc2-174">**Permitido a spoof?**: Os valores que você vê aqui são:</span><span class="sxs-lookup"><span data-stu-id="3acc2-174">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="3acc2-175">**Sim**: As mensagens da combinação de usuário e de envio de infraestruturas falsas são permitidas e não tratadas como emails falsas.</span><span class="sxs-lookup"><span data-stu-id="3acc2-175">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="3acc2-176">**Não**: As mensagens da combinação de usuário e de envio de infraestruturas falsas são marcadas como falsas.</span><span class="sxs-lookup"><span data-stu-id="3acc2-176">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="3acc2-177">A ação é controlada pela política anti-phishing padrão ou políticas anti-phishing personalizadas (o valor padrão é Mover mensagem para a pasta **Lixo Eletrônico**).</span><span class="sxs-lookup"><span data-stu-id="3acc2-177">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="3acc2-178">Consulte a próxima seção para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3acc2-178">See the next section for more information.</span></span>

     - <span data-ttu-id="3acc2-179">**Alguns usuários** ( somente a guia **Domínios):** uma infraestrutura de envio é a spoofing de vários usuários, onde alguns usuários com spoofed são permitidos e outros não.</span><span class="sxs-lookup"><span data-stu-id="3acc2-179">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="3acc2-180">Use a **guia Detalhada** para ver os endereços específicos.</span><span class="sxs-lookup"><span data-stu-id="3acc2-180">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="3acc2-181">Na parte inferior da página, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3acc2-181">At the bottom of the page, click **Save**.</span></span>

#### <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="3acc2-182">Usar o PowerShell para gerenciar os envios de spoofed</span><span class="sxs-lookup"><span data-stu-id="3acc2-182">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="3acc2-183">Para exibir os envios permitidos e bloqueados em inteligência de spoof, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="3acc2-183">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="3acc2-184">Este exemplo retorna informações detalhadas sobre todos os senders que têm permissão para espocar usuários em seus domínios.</span><span class="sxs-lookup"><span data-stu-id="3acc2-184">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="3acc2-185">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="3acc2-185">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="3acc2-186">Para configurar os envios permitidos e bloqueados na inteligência de spoof, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="3acc2-186">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="3acc2-187">Capture a lista atual de envios esofados detectados escrevendo a saída do cmdlet **Get-PhishFilterPolicy** em um arquivo CSV executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3acc2-187">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file by running the following command:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="3acc2-188">Edite o arquivo CSV para adicionar ou modificar os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="3acc2-188">Edit the CSV file to add or modify the following values:</span></span>
   - <span data-ttu-id="3acc2-189">**Remetente** (domínio no registro PTR do servidor de origem ou endereço IP/24)</span><span class="sxs-lookup"><span data-stu-id="3acc2-189">**Sender** (domain in source server's PTR record or IP/24 address)</span></span>
   - <span data-ttu-id="3acc2-190">**SpoofedUser**: um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="3acc2-190">**SpoofedUser**: One of the following values:</span></span>
     - <span data-ttu-id="3acc2-191">O endereço de email do usuário interno.</span><span class="sxs-lookup"><span data-stu-id="3acc2-191">The internal user's email address.</span></span>
     - <span data-ttu-id="3acc2-192">O domínio de email do usuário externo.</span><span class="sxs-lookup"><span data-stu-id="3acc2-192">The external user's email domain.</span></span>
     - <span data-ttu-id="3acc2-193">Um valor em branco que indica que você deseja bloquear ou permitir todas as mensagens falsas do Remetente especificado **,** independentemente do endereço de email falsa.</span><span class="sxs-lookup"><span data-stu-id="3acc2-193">A blank value that indicates you want to block or allow any and all spoofed messages from the specified **Sender**, regardless of the spoofed email address.</span></span>
   - <span data-ttu-id="3acc2-194">**AllowedToSpoof** (Sim ou Não)</span><span class="sxs-lookup"><span data-stu-id="3acc2-194">**AllowedToSpoof** (Yes or No)</span></span>
   - <span data-ttu-id="3acc2-195">**SpoofType** (Interno ou Externo)</span><span class="sxs-lookup"><span data-stu-id="3acc2-195">**SpoofType** (Internal or External)</span></span>

   <span data-ttu-id="3acc2-196">Salve o arquivo, leia o arquivo e armazene o conteúdo como uma variável `$UpdateSpoofedSenders` nomeada executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3acc2-196">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders` by running the following command:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="3acc2-197">Use a variável para configurar a política de inteligência de `$UpdateSpoofedSenders` spoof executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3acc2-197">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy by running the following command:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="3acc2-198">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="3acc2-198">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy).</span></span>

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-insight"></a><span data-ttu-id="3acc2-199">Gerenciar envios com spoofed no insight de inteligência de spoof</span><span class="sxs-lookup"><span data-stu-id="3acc2-199">Manage spoofed senders in the spoof intelligence insight</span></span>

1. <span data-ttu-id="3acc2-200">No Centro de Conformidade & segurança, vá para **Painel de Gerenciamento de** \> **Ameaças.**</span><span class="sxs-lookup"><span data-stu-id="3acc2-200">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard**.</span></span>

2. <span data-ttu-id="3acc2-201">Na linha **Insights,** procure um dos seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="3acc2-201">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="3acc2-202">**Domínios provavelmente desfalsados** nos últimos sete dias : Essa visão indica que a inteligência de spoof está habilitada (ela está habilitada por padrão).</span><span class="sxs-lookup"><span data-stu-id="3acc2-202">**Likely spoofed domains over the past seven days**: This insight indicates that spoof intelligence is enabled (it's enabled by default).</span></span>
   - <span data-ttu-id="3acc2-203">**Habilitar** a Proteção contra Spoof : essa visão indica que a inteligência de spoof está desabilitada e clicar no insight permite que você habilita a inteligência de spoof.</span><span class="sxs-lookup"><span data-stu-id="3acc2-203">**Enable Spoof Protection**: This insight indicates that spoof intelligence is disabled, and clicking on the insight allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="3acc2-204">O insight no painel mostra informações como esta:</span><span class="sxs-lookup"><span data-stu-id="3acc2-204">The insight on the dashboard shows you information like this:</span></span>

   ![Captura de tela do insight de inteligência de spoof](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="3acc2-206">Esse insight tem dois modos:</span><span class="sxs-lookup"><span data-stu-id="3acc2-206">This insight has two modes:</span></span>

   - <span data-ttu-id="3acc2-207">**Modo de** visão : se a inteligência falsa estiver habilitada, a visão mostra quantas mensagens foram impactadas por nossos recursos de inteligência falsa nos últimos sete dias.</span><span class="sxs-lookup"><span data-stu-id="3acc2-207">**Insight mode**: If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past seven days.</span></span>
   - <span data-ttu-id="3acc2-208">**E se o modo**: se a inteligência falsa estiver  desabilitada, a visão mostra quantas mensagens teriam sido impactadas por nossos recursos de inteligência falsas nos últimos sete dias.</span><span class="sxs-lookup"><span data-stu-id="3acc2-208">**What if mode**: If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past seven days.</span></span>

   <span data-ttu-id="3acc2-209">De qualquer forma, os domínios despojados exibidos no insight são separados em duas **categorias: domínios** suspeitos e domínios não **suspeitos.**</span><span class="sxs-lookup"><span data-stu-id="3acc2-209">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domains** and **Non-suspicious domains**.</span></span>

   - <span data-ttu-id="3acc2-210">**Domínios suspeitos**:</span><span class="sxs-lookup"><span data-stu-id="3acc2-210">**Suspicious domains**:</span></span>
     - <span data-ttu-id="3acc2-211">**Spoof** de alta confiança: com base nos padrões de envio históricos e na pontuação de reputação dos domínios, estamos altamente confiantes de que os domínios são falsas, e as mensagens desses domínios são mais propensas a serem mal-intencionadas.</span><span class="sxs-lookup"><span data-stu-id="3acc2-211">**High-confidence spoof**: Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>
     - <span data-ttu-id="3acc2-212">**Spoof** de confiança moderada : com base nos padrões de envio históricos e na pontuação de reputação dos domínios, estamos moderadamente confiantes de que os domínios são falsas e que as mensagens enviadas desses domínios são legítimas.</span><span class="sxs-lookup"><span data-stu-id="3acc2-212">**Moderate confidence spoof**: Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="3acc2-213">Falsos positivos são mais prováveis nessa categoria do que falsos falsos.</span><span class="sxs-lookup"><span data-stu-id="3acc2-213">False positives are more likely in this category than high-confidence spoof.</span></span>
   - <span data-ttu-id="3acc2-214">**Domínios não suspeitos**: O domínio com falha na autenticação de email explícito verifica [SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC](use-dmarc-to-validate-email.md)).</span><span class="sxs-lookup"><span data-stu-id="3acc2-214">**Non-suspicious domains**: The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="3acc2-215">No entanto, o domínio passou nossas verificações implícitas de autenticação de email ([autenticação composta](email-validation-and-authentication.md#composite-authentication)).</span><span class="sxs-lookup"><span data-stu-id="3acc2-215">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="3acc2-216">Como resultado, nenhuma ação anti-spoofing foi tomada na mensagem.</span><span class="sxs-lookup"><span data-stu-id="3acc2-216">As a result, no anti-spoofing action was taken on the message.</span></span>

#### <a name="view-detailed-information-about-suspicious-and-nonsuspicious-domains"></a><span data-ttu-id="3acc2-217">Exibir informações detalhadas sobre domínios suspeitos e não suspiciosos</span><span class="sxs-lookup"><span data-stu-id="3acc2-217">View detailed information about suspicious and nonsuspicious domains</span></span>

1. <span data-ttu-id="3acc2-218">No insight de inteligência de spoof, clique em **Domínios** suspeitos ou **domínios** não suspeitos para ir para a página de informações de **inteligência de Spoof.**</span><span class="sxs-lookup"><span data-stu-id="3acc2-218">On the Spoof intelligence insight, click **Suspicious domains** or **Non-suspicious domains** to go to the **Spoof intelligence insight** page.</span></span> <span data-ttu-id="3acc2-219">A página de informações **do Spoof Intelligence** contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="3acc2-219">The **Spoof Intelligence insight** page contains the following information:</span></span>

   - <span data-ttu-id="3acc2-220">**Domínio spoofed**: O domínio do usuário que é exibido na caixa **De** em clientes de email.</span><span class="sxs-lookup"><span data-stu-id="3acc2-220">**Spoofed domain**: The domain of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="3acc2-221">Esse endereço também é conhecido como `5322.From` endereço.</span><span class="sxs-lookup"><span data-stu-id="3acc2-221">This address is also known as the `5322.From` address.</span></span>
   - <span data-ttu-id="3acc2-222">**Infraestrutura**: Também conhecida como infraestrutura _de envio._</span><span class="sxs-lookup"><span data-stu-id="3acc2-222">**Infrastructure**: Also known as the _sending infrastructure_.</span></span> <span data-ttu-id="3acc2-223">O domínio encontrado em um registro DNS reverso (registro PTR) do endereço IP do servidor de email de origem.</span><span class="sxs-lookup"><span data-stu-id="3acc2-223">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="3acc2-224">Se o endereço IP de origem não tiver registro PTR, a infraestrutura de envio será identificada como \<source IP\> /24 (por exemplo, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="3acc2-224">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>
   - <span data-ttu-id="3acc2-225">**Contagem de** mensagens : o número de mensagens da infraestrutura de envio para sua organização que contêm o domínio empoeirado especificado nos últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="3acc2-225">**Message count**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed domain within the last 7 days.</span></span>
   - <span data-ttu-id="3acc2-226">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed domain.</span><span class="sxs-lookup"><span data-stu-id="3acc2-226">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed domain.</span></span>
   - <span data-ttu-id="3acc2-227">**Tipo de spoof**: esse valor é **Externo**.</span><span class="sxs-lookup"><span data-stu-id="3acc2-227">**Spoof type**: This value is **External**.</span></span>
   - <span data-ttu-id="3acc2-228">**Permitido a spoof?**: Os valores que você vê aqui são:</span><span class="sxs-lookup"><span data-stu-id="3acc2-228">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="3acc2-229">**Sim**: As mensagens da combinação do domínio do usuário falsa e da infraestrutura de envio são permitidas e não tratadas como emails falsas.</span><span class="sxs-lookup"><span data-stu-id="3acc2-229">**Yes**: Messages from the combination of spoofed user's domain and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="3acc2-230">**Não**: As mensagens da combinação do domínio do usuário falsa e da infraestrutura de envio são marcadas como falsas.</span><span class="sxs-lookup"><span data-stu-id="3acc2-230">**No**: Messages from the combination of spoofed user's domain and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="3acc2-231">A ação é controlada pela política anti-phishing padrão ou políticas anti-phishing personalizadas (o valor padrão é Mover mensagem para a pasta **Lixo Eletrônico**).</span><span class="sxs-lookup"><span data-stu-id="3acc2-231">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span>

2. <span data-ttu-id="3acc2-232">Selecione um item na lista para exibir detalhes sobre o par de infraestrutura de envio/domínio em um sobremenu.</span><span class="sxs-lookup"><span data-stu-id="3acc2-232">Select an item in the list to view details about the domain/sending infrastructure pair in a flyout.</span></span> <span data-ttu-id="3acc2-233">As informações incluem:</span><span class="sxs-lookup"><span data-stu-id="3acc2-233">The information includes:</span></span>
   - <span data-ttu-id="3acc2-234">Por que pegamos isso.</span><span class="sxs-lookup"><span data-stu-id="3acc2-234">Why we caught this.</span></span>
   - <span data-ttu-id="3acc2-235">O que você precisa fazer.</span><span class="sxs-lookup"><span data-stu-id="3acc2-235">What you need to do.</span></span>
   - <span data-ttu-id="3acc2-236">Um resumo de domínio.</span><span class="sxs-lookup"><span data-stu-id="3acc2-236">A domain summary.</span></span>
   - <span data-ttu-id="3acc2-237">WhoIs dados sobre o remetente.</span><span class="sxs-lookup"><span data-stu-id="3acc2-237">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="3acc2-238">Mensagens semelhantes que vimos em seu locatário do mesmo remetente.</span><span class="sxs-lookup"><span data-stu-id="3acc2-238">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="3acc2-239">A partir daqui, você também pode optar por adicionar ou remover o par de infraestrutura de envio/domínio da lista de permissão Permitido para **spoof** remetente.</span><span class="sxs-lookup"><span data-stu-id="3acc2-239">From here, you can also choose to add or remove the domain/sending infrastructure pair from the **Allowed to spoof** sender allow list.</span></span> <span data-ttu-id="3acc2-240">Basta definir a alternância de acordo.</span><span class="sxs-lookup"><span data-stu-id="3acc2-240">Simply set the toggle accordingly.</span></span>

   ![Captura de tela de um domínio no painel de detalhes de informações de inteligência de Spoof](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="3acc2-242">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="3acc2-242">How do you know these procedures worked?</span></span>

<span data-ttu-id="3acc2-243">Para verificar se você configurou a inteligência de spoof com os senders que têm permissão e não têm permissão para fazer a spoof, use qualquer uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="3acc2-243">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, use any of the following steps:</span></span>

- <span data-ttu-id="3acc2-244">No Centro de Conformidade & Segurança,  vá até Política de Gerenciamento de Ameaças Política De expansão de Spoof intelligence selecione Mostrar remetentes Que eu já revisei selecione a guia Seus Domínios ou Domínios Externos e verifique o valor Permitido para a \>  \>  \>  \>  \> **spoof?**   para o remetente.</span><span class="sxs-lookup"><span data-stu-id="3acc2-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="3acc2-245">No PowerShell, execute os seguintes comandos para exibir os senders que têm permissão e não têm permissão para fazer a spoof:</span><span class="sxs-lookup"><span data-stu-id="3acc2-245">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="3acc2-246">No PowerShell, execute o seguinte comando para exportar a lista de todos os envios despojados para um arquivo CSV:</span><span class="sxs-lookup"><span data-stu-id="3acc2-246">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```
