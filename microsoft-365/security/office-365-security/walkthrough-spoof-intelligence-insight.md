---
title: Walkthrough-visão geral da inteligência de falsificação
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender como funciona a compreensão da inteligência de falsificação. Eles podem determinar rapidamente quais remetentes estão enviando emails legitimamente para suas organizações de domínios que não passam por verificações de autenticação de email (SPF, DKIM ou DMARC).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 89a31c6df7c9b6e02f52ea414ceb6334427feab1
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920473"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a><span data-ttu-id="160d4-104">Walkthrough-visão geral da inteligência de falsificação no Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="160d4-104">Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="160d4-105">Nas organizações Microsoft 365 com o defender para Office 365, você pode usar a compreensão de inteligência de falsificação para determinar rapidamente quais remetentes estão enviando legitimamente emails não autenticados (mensagens de domínios que não passam verificações de SPF, DKIM ou DMARC).</span><span class="sxs-lookup"><span data-stu-id="160d4-105">In Microsoft 365 organizations with Defender for Office 365, you can use the Spoof intelligence insight to quickly determine which senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="160d4-106">Ao permitir que remetentes conhecidos enviem mensagens falsificadas de locais conhecidos, você pode reduzir falsos positivos (bons emails marcados como defeituosos).</span><span class="sxs-lookup"><span data-stu-id="160d4-106">By allowing known senders to send spoofed messages from known locations, you can reduce false positives (good email marked as bad).</span></span> <span data-ttu-id="160d4-107">Ao monitorar os remetentes falsificados permitidos, você fornece uma camada adicional de segurança para impedir que mensagens não seguras cheguem à sua organização.</span><span class="sxs-lookup"><span data-stu-id="160d4-107">By monitoring the allowed spoofed senders, you provide an additional layer of security to prevent unsafe messages from arriving in your organization.</span></span>

<span data-ttu-id="160d4-108">Para obter mais informações sobre relatórios e informações, consulte [relatórios e insights no centro de conformidade de & de segurança](reports-and-insights-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="160d4-108">For more information about reports and insights, see [Reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

<span data-ttu-id="160d4-109">Este passo a passo é um dos vários para o centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="160d4-109">This walkthrough is one of several for the Security & Compliance Center.</span></span> <span data-ttu-id="160d4-110">Para sobre como navegar por relatórios e insights, consulte as orientações na seção [Tópicos relacionados](#related-topics) .</span><span class="sxs-lookup"><span data-stu-id="160d4-110">To about navigating reports and insights, see the walkthroughs in the [Related topics](#related-topics) section.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="160d4-111">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="160d4-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="160d4-112">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="160d4-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="160d4-113">Para ir diretamente para a página do **painel de segurança** , use <https://protection.office.com/searchandinvestigation/dashboard> .</span><span class="sxs-lookup"><span data-stu-id="160d4-113">To go directly to the **Security dashboard** page, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

  <span data-ttu-id="160d4-114">Você pode exibir a percepção de inteligência de falsificação de mais de um painel no centro de conformidade & segurança.</span><span class="sxs-lookup"><span data-stu-id="160d4-114">You can view the Spoof intelligence insight from more than one dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="160d4-115">Independentemente de qual painel você está vendo, a percepção fornece os mesmos detalhes e permite que você realize rapidamente as mesmas tarefas.</span><span class="sxs-lookup"><span data-stu-id="160d4-115">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>

- <span data-ttu-id="160d4-116">Você precisa receber permissões antes de executar os procedimentos deste tópico.</span><span class="sxs-lookup"><span data-stu-id="160d4-116">You need to be assigned permissions before you can do the procedures in this topic.</span></span> <span data-ttu-id="160d4-117">Para usar o spoof Intelligence percepção, você precisa ser membro de um dos seguintes grupos de função:</span><span class="sxs-lookup"><span data-stu-id="160d4-117">To use the spoof intelligence insight, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="160d4-118">**Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="160d4-118">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="160d4-119">**Gerenciamento de organizações** ou **Gerenciamento de higiene** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="160d4-119">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>
  - <span data-ttu-id="160d4-120">**Leitor de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="160d4-120">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="160d4-121">**Gerenciamento da organização Somente visualização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="160d4-121">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="160d4-122">Você habilita e desabilita a inteligência de spoof em políticas anti-phishing no Microsoft defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="160d4-122">You enable and disable spoof intelligence in anti-phishing policies in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="160d4-123">Para obter mais informações, consulte [Configure anti-phishing Policies in Microsoft defender for Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="160d4-123">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="160d4-124">Para usar o spoof Intelligence para monitorar e gerenciar remetentes que estão enviando mensagens não autenticadas, consulte [Configure spoof Intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="160d4-124">To use spoof intelligence to monitor and manage senders who are sending you unauthenticated messages, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a><span data-ttu-id="160d4-125">Abrir a percepção de compreensão da falsificação no centro de conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="160d4-125">Open the spoof intelligence insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="160d4-126">No centro de conformidade & segurança, vá para o painel **Gerenciamento de ameaças** \> **.**</span><span class="sxs-lookup"><span data-stu-id="160d4-126">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>

2. <span data-ttu-id="160d4-127">Na linha **insights** , procure um dos seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="160d4-127">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="160d4-128">O **spoof Intelligence está habilitado** : a percepção é denominada **domínios falsificados que falharam na autenticação dos últimos 30 dias**.</span><span class="sxs-lookup"><span data-stu-id="160d4-128">**Spoof intelligence is enabled** : The insight is named **Spoofed domains that failed authentication of the past 30 days**.</span></span> <span data-ttu-id="160d4-129">É o padrão.</span><span class="sxs-lookup"><span data-stu-id="160d4-129">This is the default.</span></span>
   - <span data-ttu-id="160d4-130">A **inteligência de falsificação está desabilitada** : a percepção em chamado **habilitar proteção contra falsificação** e clicar nele permite habilitar a inteligência de falsificação.</span><span class="sxs-lookup"><span data-stu-id="160d4-130">**Spoof intelligence is disabled** : The insight in named **Enable Spoof Protection** , and clicking on it allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="160d4-131">A percepção do painel mostra as informações como esta:</span><span class="sxs-lookup"><span data-stu-id="160d4-131">The insight on the dashboard shows you information like this:</span></span>

   ![Captura de tela do spoof Intelligence percepção](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="160d4-133">Esta percepção tem dois modos:</span><span class="sxs-lookup"><span data-stu-id="160d4-133">This insight has two modes:</span></span>

   - <span data-ttu-id="160d4-134">**Modo de percepção** : se a inteligência de falsificação estiver habilitada, a percepção mostrará quantas mensagens foram impactadas por nossos recursos de inteligência de fraude nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="160d4-134">**Insight mode** : If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   - <span data-ttu-id="160d4-135">**E se modo** : se a inteligência de falsificação estiver desabilitada, a percepção mostrará quantas mensagens *teriam* sido impactadas por nossos recursos de inteligência de fraude nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="160d4-135">**What if mode** : If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   <span data-ttu-id="160d4-136">De qualquer forma, os domínios falsificados exibidos na percepção são separados em duas categorias: **pares de domínios suspeitos** e **pares de domínios não suspeitos**.</span><span class="sxs-lookup"><span data-stu-id="160d4-136">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domain pairs** and **Non-suspicious domain pairs**.</span></span> <span data-ttu-id="160d4-137">Essas categorias são subdivididas em três buckets diferentes para revisão.</span><span class="sxs-lookup"><span data-stu-id="160d4-137">These categories are further subdivided into three different buckets for you to review.</span></span>

   <span data-ttu-id="160d4-138">Um **par de domínio** é uma combinação do endereço de e da infraestrutura de envio:</span><span class="sxs-lookup"><span data-stu-id="160d4-138">A **domain pair** is a combination of the From address and the sending infrastructure:</span></span>

   - <span data-ttu-id="160d4-139">O endereço de é o endereço de email do remetente que é exibido na caixa de em clientes de email.</span><span class="sxs-lookup"><span data-stu-id="160d4-139">The From address is the sender's email address that's displayed in the From box in email clients.</span></span> <span data-ttu-id="160d4-140">Esse endereço também é conhecido como o `5322.From` endereço.</span><span class="sxs-lookup"><span data-stu-id="160d4-140">This address is also known as the `5322.From` address.</span></span>

   - <span data-ttu-id="160d4-141">A infraestrutura de envio, ou remetente, é o domínio organizacional da pesquisa de DNS inversa (registro PTR) do endereço IP de envio.</span><span class="sxs-lookup"><span data-stu-id="160d4-141">The sending infrastructure, or sender, is the organizational domain of the reverse DNS lookup (PTR record) of the sending IP address.</span></span> <span data-ttu-id="160d4-142">Se o endereço IP de envio não tiver um registro PTR, o remetente será identificado pelo IP de envio com a máscara de sub-rede 255.255.255.0 em notação CIDR (/24).</span><span class="sxs-lookup"><span data-stu-id="160d4-142">If the sending IP address has no PTR record, then the sender is identified by the sending IP with the 255.255.255.0 subnet mask in CIDR notation (/24).</span></span> <span data-ttu-id="160d4-143">Por exemplo, se o endereço IP for 192.168.100.100, o endereço IP completo do remetente será 192.168.100.100/24.</span><span class="sxs-lookup"><span data-stu-id="160d4-143">For example, if the IP address is 192.168.100.100 then the complete IP address of the sender is 192.168.100.100/24.</span></span>

   <span data-ttu-id="160d4-144">Os **pares de domínios suspeitos** incluem:</span><span class="sxs-lookup"><span data-stu-id="160d4-144">**Suspicious domain pairs** include:</span></span>

   - <span data-ttu-id="160d4-145">**Falsificação de alta confiança** : com base nos padrões de envio históricos e na pontuação de reputação dos domínios, temos certeza de que os domínios estão falsificando, e as mensagens desses domínios provavelmente serão mal-intencionadas.</span><span class="sxs-lookup"><span data-stu-id="160d4-145">**High-confidence spoof** : Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>

   - <span data-ttu-id="160d4-146">**Falsificação de confiança moderada** : com base nos padrões de envio históricos e na pontuação de reputação dos domínios, temos certeza de que os domínios estão sendo falsificados e que as mensagens enviadas desses domínios são legítimas.</span><span class="sxs-lookup"><span data-stu-id="160d4-146">**Moderate confidence spoof** : Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="160d4-147">Falsos positivos são mais prováveis nesta categoria do que a falsificação de alta confiança.</span><span class="sxs-lookup"><span data-stu-id="160d4-147">False positives are more likely in this category than high-confidence spoof.</span></span>

   - <span data-ttu-id="160d4-148">**Pares de domínios não suspeitos** (inclui **falsificação** renovada): o domínio falhou nas verificações de autenticação de email explícitas [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC](use-dmarc-to-validate-email.md)).</span><span class="sxs-lookup"><span data-stu-id="160d4-148">**Non-suspicious domain pairs** (includes **rescued spoof** ): The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="160d4-149">No entanto, o domínio passou por nossas verificações de autenticação de email implícito ([autenticação composta](email-validation-and-authentication.md#composite-authentication)).</span><span class="sxs-lookup"><span data-stu-id="160d4-149">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="160d4-150">Como resultado, nenhuma ação anti-falsificação foi tomada na mensagem.</span><span class="sxs-lookup"><span data-stu-id="160d4-150">As a result, no anti-spoofing action was taken on the message.</span></span>

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a><span data-ttu-id="160d4-151">Exibir informações detalhadas sobre pares de domínio suspeitos da compreensão da inteligência de falsificação</span><span class="sxs-lookup"><span data-stu-id="160d4-151">View detailed information about suspicious domain pairs from the spoof intelligence insight</span></span>

1. <span data-ttu-id="160d4-152">Na percepção de inteligência de falsificação, clique em qualquer um dos pares de domínio (alto, moderado ou cogatado).</span><span class="sxs-lookup"><span data-stu-id="160d4-152">On the Spoof intelligence insight, click any of the domain pairs (high, moderate, or rescued).</span></span>

   <span data-ttu-id="160d4-153">A página **informações sobre spoof Intelligence** aparece.</span><span class="sxs-lookup"><span data-stu-id="160d4-153">The **Spoof Intelligence insight** page appears.</span></span> <span data-ttu-id="160d4-154">A página mostra uma lista de remetentes que estão enviando emails não autenticados para sua organização.</span><span class="sxs-lookup"><span data-stu-id="160d4-154">The page shows you a list of senders who are sending unauthenticated email into your organization.</span></span>

   <span data-ttu-id="160d4-155">Essas informações ajudam a determinar se as mensagens falsificadas são autorizadas ou se você precisa tomar mais ações.</span><span class="sxs-lookup"><span data-stu-id="160d4-155">This information helps you determine whether spoofed messages are authorized, or if you need to take further action.</span></span>

   <span data-ttu-id="160d4-156">Você pode classificar as informações por contagem de mensagens, a data em que a falsificação foi detectada pela última vez e muito mais.</span><span class="sxs-lookup"><span data-stu-id="160d4-156">You can sort the information by message count, the date the spoof was last detected, and more.</span></span>

2. <span data-ttu-id="160d4-157">Selecione um item na tabela para abrir um painel de detalhes que contenha informações avançadas sobre o par de domínio.</span><span class="sxs-lookup"><span data-stu-id="160d4-157">Select an item in the table to open a details pane that contains rich information about the domain pair.</span></span> <span data-ttu-id="160d4-158">As informações incluem:</span><span class="sxs-lookup"><span data-stu-id="160d4-158">The information includes:</span></span>
   - <span data-ttu-id="160d4-159">Por que detectamos isso.</span><span class="sxs-lookup"><span data-stu-id="160d4-159">Why we caught this.</span></span>
   - <span data-ttu-id="160d4-160">O que você precisa fazer.</span><span class="sxs-lookup"><span data-stu-id="160d4-160">What you need to do.</span></span>
   - <span data-ttu-id="160d4-161">Um resumo de domínio.</span><span class="sxs-lookup"><span data-stu-id="160d4-161">A domain summary.</span></span>
   - <span data-ttu-id="160d4-162">Dados de WhoIs sobre o remetente.</span><span class="sxs-lookup"><span data-stu-id="160d4-162">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="160d4-163">Mensagens semelhantes que vimos no seu locatário do mesmo remetente.</span><span class="sxs-lookup"><span data-stu-id="160d4-163">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="160d4-164">A partir daqui, você também pode optar por adicionar ou remover o par de domínio da lista de remetentes confiáveis do **AllowedToSpoof** .</span><span class="sxs-lookup"><span data-stu-id="160d4-164">From here, you can also choose to add or remove the domain pair from the **AllowedToSpoof** safe sender list.</span></span>

   ![Captura de tela de um domínio no painel de detalhes do spoof Intelligence Insight](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-list"></a><span data-ttu-id="160d4-166">Adicionar ou remover um domínio da lista AllowedToSpoof</span><span class="sxs-lookup"><span data-stu-id="160d4-166">Add or remove a domain from the AllowedToSpoof list</span></span>

<span data-ttu-id="160d4-167">Você adiciona ou remove um domínio da lista AllowedToSpoof (remetente seguro) no painel de detalhes da compreensão de inteligência de spoof para o par de domínio.</span><span class="sxs-lookup"><span data-stu-id="160d4-167">You add or remove a domain from the AllowedToSpoof (safe sender) list in the details pane of the spoof intelligence insight for the domain pair.</span></span> <span data-ttu-id="160d4-168">Basta definir a opção de alternância.</span><span class="sxs-lookup"><span data-stu-id="160d4-168">Simply set the toggle accordingly.</span></span>

<span data-ttu-id="160d4-169">Permitir um par de domínios permite apenas a combinação do domínio falsificado *e* da infraestrutura de envio.</span><span class="sxs-lookup"><span data-stu-id="160d4-169">Allowing a domain pair only allows the combination of the spoofed domain *and* the sending infrastructure.</span></span> <span data-ttu-id="160d4-170">Ele não permite o envio de emails do domínio falsificado de qualquer fonte, nem permite o envio de emails da infraestrutura de envio para qualquer domínio.</span><span class="sxs-lookup"><span data-stu-id="160d4-170">It does not allow email from the spoofed domain from any source, nor does it allow email from the sending infrastructure for any domain.</span></span>

<span data-ttu-id="160d4-171">Por exemplo, você permite que o seguinte par de domínio envie mensagens falsificadas para sua organização:</span><span class="sxs-lookup"><span data-stu-id="160d4-171">For example, you allow the following domain pair to send spoofed messages into your organization:</span></span>

- <span data-ttu-id="160d4-172">*Domínio falsificado* : gmail.com "</span><span class="sxs-lookup"><span data-stu-id="160d4-172">*Spoofed Domain* : gmail.com"</span></span>
- <span data-ttu-id="160d4-173">*Infraestrutura de envio* `tms.mx.com` :</span><span class="sxs-lookup"><span data-stu-id="160d4-173">*Sending Infrastructure* `tms.mx.com`:</span></span>

<span data-ttu-id="160d4-174">Somente os emails desse par de domínio poderão ser falsificados.</span><span class="sxs-lookup"><span data-stu-id="160d4-174">Only email from that domain pair will be allowed to spoof.</span></span> <span data-ttu-id="160d4-175">Outros remetentes tentando falsificar o gmail.com não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="160d4-175">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="160d4-176">As mensagens em outros domínios de tms.mx.com são verificadas por inteligência de falsificação.</span><span class="sxs-lookup"><span data-stu-id="160d4-176">Messages in other domains from tms.mx.com are checked by spoof intelligence.</span></span>

## <a name="related-topics"></a><span data-ttu-id="160d4-177">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="160d4-177">Related topics</span></span>

[<span data-ttu-id="160d4-178">Proteção contra falsificação no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="160d4-178">Anti-spoofing protection in Microsoft 365</span></span>](anti-spoofing-protection.md)
