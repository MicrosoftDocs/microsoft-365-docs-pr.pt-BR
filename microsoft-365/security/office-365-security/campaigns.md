---
title: Exibições de campanhas na ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Saiba mais sobre os Modos de Exibição de Campanhas na Proteção Avançada contra Ameaças do Office 365.
ms.openlocfilehash: 69b11319ffb033b628e59abac931b6a3f30d082c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637813"
---
# <a name="campaign-views-in-atp"></a><span data-ttu-id="505e3-103">Exibições de campanha na ATP</span><span class="sxs-lookup"><span data-stu-id="505e3-103">Campaign Views in ATP</span></span>

<span data-ttu-id="505e3-104">O modo de exibição de campanha é um recurso da proteção avançada contra ameaças (ATP) no centro de conformidade & segurança que identifica e categoriza os ataques de phishing no serviço.</span><span class="sxs-lookup"><span data-stu-id="505e3-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="505e3-105">Os Modos de Exibição de Campanhas podem ajudá-lo a:</span><span class="sxs-lookup"><span data-stu-id="505e3-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="505e3-106">Investigar e responder de forma eficiente os ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="505e3-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="505e3-107">Entender melhor o escopo do ataque.</span><span class="sxs-lookup"><span data-stu-id="505e3-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="505e3-108">Mostrar valor aos tomadores de decisões.</span><span class="sxs-lookup"><span data-stu-id="505e3-108">Show value to decision makers.</span></span>

<span data-ttu-id="505e3-109">Os Modos de Exibição de Campanhas permitem que você veja o panorama de um ataque de forma mais rápida e completa do que qualquer pessoa.</span><span class="sxs-lookup"><span data-stu-id="505e3-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="505e3-110">O que é uma campanha?</span><span class="sxs-lookup"><span data-stu-id="505e3-110">What is a campaign?</span></span>

<span data-ttu-id="505e3-111">Uma campanha é um ataque coordenado por email contra uma ou várias organizações.</span><span class="sxs-lookup"><span data-stu-id="505e3-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="505e3-112">Os ataques de email que roubam credenciais e dados da empresa são um setor grande e lucrative.</span><span class="sxs-lookup"><span data-stu-id="505e3-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="505e3-113">À medida que as tecnologias aumentam em um esforço para interromper ataques, os invasores modificam seus métodos em um esforço para garantir o sucesso contínuo.</span><span class="sxs-lookup"><span data-stu-id="505e3-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="505e3-114">A Microsoft aproveita as vastas quantidades de dados anti-phishing, antispam e antimalware em todo o serviço para ajudar a identificar campanhas.</span><span class="sxs-lookup"><span data-stu-id="505e3-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="505e3-115">Analisamos e classificamos as informações de ataque de acordo com vários fatores.</span><span class="sxs-lookup"><span data-stu-id="505e3-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="505e3-116">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="505e3-116">For example:</span></span>

- <span data-ttu-id="505e3-117">**Fonte de ataque**: endereços IP de origem e domínios de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="505e3-117">**Attack source**: Source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="505e3-118">**Propriedades da mensagem de ataque**: o conteúdo, estilo e tom das mensagens de ataque.</span><span class="sxs-lookup"><span data-stu-id="505e3-118">**Attack message properties**: The content, style, and tone of the attack messages.</span></span>

- <span data-ttu-id="505e3-119">**Destinatários de um ataque**: domínios do destinatário, funções de trabalho do destinatário (administradores, executivos, etc.), tipos de empresa (grandes, pequenas, públicas, privadas etc.) e setores.</span><span class="sxs-lookup"><span data-stu-id="505e3-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="505e3-120">**Carga de ataque**: links mal-intencionados, anexos ou outras cargas nas mensagens de ataque.</span><span class="sxs-lookup"><span data-stu-id="505e3-120">**Attack payload**: Malicious links, attachments, or other payloads in the attack messages.</span></span>

<span data-ttu-id="505e3-121">Uma campanha pode ser de vida curta ou pode abranger vários dias, semanas ou meses com períodos ativos e inativos.</span><span class="sxs-lookup"><span data-stu-id="505e3-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="505e3-122">Uma campanha pode ser iniciada em sua organização específica ou sua organização pode fazer parte de uma campanha maior em várias empresas.</span><span class="sxs-lookup"><span data-stu-id="505e3-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-security--compliance-center"></a><span data-ttu-id="505e3-123">Exibições de campanha o centro de conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="505e3-123">Campaign Views the Security & Compliance Center</span></span>

<span data-ttu-id="505e3-124">Os modos de exibição de campanha estão disponíveis no [centro de conformidade e segurança &](https://protection.office.com) nas **campanhas**de **Gerenciamento** \> de ameaças.</span><span class="sxs-lookup"><span data-stu-id="505e3-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**.</span></span>

![Visão geral das campanhas no Centro de Conformidade e Segurança](../../media/campaigns-overview.png)

<span data-ttu-id="505e3-126">Você também pode acessar o modo de exibição campanhas de:</span><span class="sxs-lookup"><span data-stu-id="505e3-126">You can also get to Campaigns View from:</span></span>

- <span data-ttu-id="505e3-127">**Threat management** \> **Explorer** Gerenciador \> de gerenciamento de ameaças **Exibir** \> **campanhas**</span><span class="sxs-lookup"><span data-stu-id="505e3-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="505e3-128">**Threat management** \> **Explorer** Gerenciador \> de gerenciamento de ameaças **Exibir** \> **todas as** \> **campanhas** de email</span><span class="sxs-lookup"><span data-stu-id="505e3-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign**</span></span>

> [!TIP]
> <span data-ttu-id="505e3-129">Caso não veja nenhum dado da campanha, experimente alterar o intervalo de datas.</span><span class="sxs-lookup"><span data-stu-id="505e3-129">If you don't see any campaign data, try changing the date range.</span></span>

<span data-ttu-id="505e3-130">A página Visão geral mostra as seguintes informações sobre a campanha:</span><span class="sxs-lookup"><span data-stu-id="505e3-130">The overview page shows the following information about the campaign:</span></span>

- <span data-ttu-id="505e3-131">**Nome**</span><span class="sxs-lookup"><span data-stu-id="505e3-131">**Name**</span></span>

- <span data-ttu-id="505e3-132">**Exemplo de assunto**: a linha de assunto de uma das mensagens na campanha.</span><span class="sxs-lookup"><span data-stu-id="505e3-132">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="505e3-133">Observe que todas as mensagens na campanha não terão necessariamente o mesmo assunto.</span><span class="sxs-lookup"><span data-stu-id="505e3-133">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="505e3-134">**Tipo**: atualmente, esse valor é sempre **Phish**.</span><span class="sxs-lookup"><span data-stu-id="505e3-134">**Type**: Currently, this value is always **Phish**.</span></span>

- <span data-ttu-id="505e3-135">**Subtipo**: quando disponível, a marca que está sendo visada por esta campanha.</span><span class="sxs-lookup"><span data-stu-id="505e3-135">**Subtype**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="505e3-136">Quando a detecção é orientada pela tecnologia ATP, o prefixo **ATP-** é adicionado ao valor de subtipo.</span><span class="sxs-lookup"><span data-stu-id="505e3-136">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="505e3-137">**Destinatários**: o número de usuários que foram alvos desta campanha.</span><span class="sxs-lookup"><span data-stu-id="505e3-137">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="505e3-138">**Caixa de entrada**: o número de usuários que receberam mensagens desta campanha em sua caixa de entrada (não entregue a lixo eletrônico).</span><span class="sxs-lookup"><span data-stu-id="505e3-138">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to Junk).</span></span>

- <span data-ttu-id="505e3-139">**Clicado**: o número de usuários que clicaram na URL na mensagem de phishing.</span><span class="sxs-lookup"><span data-stu-id="505e3-139">**Clicked**: The number of users that clicked on the URL in the phishing message.</span></span>

- <span data-ttu-id="505e3-140">**Taxa de clique**: a porcentagem conforme calculada por "**clicado** / em**caixa de entrada**".</span><span class="sxs-lookup"><span data-stu-id="505e3-140">**Click Rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="505e3-141">Esse valor é um indicador da eficácia da campanha e se os destinatários podem identificar a mensagem como phishing e evitar clicar na URL de carga.</span><span class="sxs-lookup"><span data-stu-id="505e3-141">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

- <span data-ttu-id="505e3-142">**Visitado**: quantos usuários realmente o fizeram no site de carga de transferência.</span><span class="sxs-lookup"><span data-stu-id="505e3-142">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="505e3-143">Se houver valores **clicados** , mas os links seguros bloquearam o acesso ao site, esse valor será zero.</span><span class="sxs-lookup"><span data-stu-id="505e3-143">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="505e3-144">Quando você clica no nome de uma campanha, os detalhes da campanha aparecem em um submenu.</span><span class="sxs-lookup"><span data-stu-id="505e3-144">When you click on the name of a campaign, the campaign details appears in a flyout.</span></span>

## <a name="campaign-details"></a><span data-ttu-id="505e3-145">Detalhes da campanha</span><span class="sxs-lookup"><span data-stu-id="505e3-145">Campaign details</span></span>

<span data-ttu-id="505e3-146">No modo de exibição de detalhes da campanha, estão disponíveis muitas informações sobre a campanha:</span><span class="sxs-lookup"><span data-stu-id="505e3-146">In the campaign details view, a lot of information is available about the campaign:</span></span>

- <span data-ttu-id="505e3-147">Informações da campanha:</span><span class="sxs-lookup"><span data-stu-id="505e3-147">Campaign information:</span></span>

  - <span data-ttu-id="505e3-148">**ID**: o identificador exclusivo da campanha.</span><span class="sxs-lookup"><span data-stu-id="505e3-148">**ID**: The unique campaign identifier.</span></span>

  - <span data-ttu-id="505e3-149">**Iniciado** e **Finalizado**: o filtro do intervalo de datas selecionado.</span><span class="sxs-lookup"><span data-stu-id="505e3-149">**Started** and **Ended**: the date range filter you selected.</span></span>

  - <span data-ttu-id="505e3-150">**Impacto**: os seguintes dados para o filtro de intervalo de datas selecionado:</span><span class="sxs-lookup"><span data-stu-id="505e3-150">**Impact**: The following data for the date range filter you selected:</span></span>
  
    - <span data-ttu-id="505e3-151">O número total de destinatários.</span><span class="sxs-lookup"><span data-stu-id="505e3-151">The total number of recipients.</span></span>

    - <span data-ttu-id="505e3-152">O número de mensagens que foram "caixa de entrada" (isto é, entregues na caixa de entrada, não em lixo eletrônico).</span><span class="sxs-lookup"><span data-stu-id="505e3-152">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to Junk).</span></span>

    - <span data-ttu-id="505e3-153">Quantos usuários clicaram na carga da URL na mensagem de phishing.</span><span class="sxs-lookup"><span data-stu-id="505e3-153">How many users clicked on the URL payload in the phishing message.</span></span>

    - <span data-ttu-id="505e3-154">Howe muitos usuários visitaram a URL.</span><span class="sxs-lookup"><span data-stu-id="505e3-154">Howe many users visited the URL.</span></span>

  - <span data-ttu-id="505e3-155">Uma linha do tempo de atividade da campanha: quando a campanha começou e terminou e o volume de mensagens neste período.</span><span class="sxs-lookup"><span data-stu-id="505e3-155">A timeline of campaign activity: When the campaign started and ended, and the volume of messages over time.</span></span>

### <a name="campaign-flow"></a><span data-ttu-id="505e3-156">Fluxo de campanha</span><span class="sxs-lookup"><span data-stu-id="505e3-156">Campaign flow</span></span>

<span data-ttu-id="505e3-157">Os detalhes importantes sobre a campanha são apresentados em um diagrama de fluxo horizontal (conhecido como diagrama _Sankey_) na seção **Fluxo**.</span><span class="sxs-lookup"><span data-stu-id="505e3-157">Important details about the campaign are presented in a horizontal flow diagram (known as a _Sankey_ diagram) in the **Flow** section.</span></span> <span data-ttu-id="505e3-158">Esses detalhes ajudarão você a entender os elementos da campanha e o impacto potencial na sua organização.</span><span class="sxs-lookup"><span data-stu-id="505e3-158">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

![Detalhes da campanha que não contêm cliques de usuários na URL](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="505e3-160">Se passar o mouse sobre uma faixa horizontal no diagrama, você verá o número de mensagens relacionadas (por exemplo, mensagens de um determinado IP de origem, mensagens do IP de origem usando o domínio do remetente especificado, etc.).</span><span class="sxs-lookup"><span data-stu-id="505e3-160">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="505e3-161">O diagrama contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="505e3-161">The diagram contains the following information:</span></span>

- <span data-ttu-id="505e3-162">**IPs do remetente**</span><span class="sxs-lookup"><span data-stu-id="505e3-162">**Sender IPs**</span></span>

- <span data-ttu-id="505e3-163">**Domínios do remetente**</span><span class="sxs-lookup"><span data-stu-id="505e3-163">**Sender domains**</span></span>

- <span data-ttu-id="505e3-164">**Verdicts de filtro**: os valores aqui estão relacionados à verdicts de filtragem phishing e spam disponível, conforme descrito em [cabeçalhos de mensagem antispam](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="505e3-164">**Filter verdicts**: The values here are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="505e3-165">Os valores disponíveis são descritos na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="505e3-165">The available values are described in the following table:</span></span>

  |<span data-ttu-id="505e3-166">Valor</span><span class="sxs-lookup"><span data-stu-id="505e3-166">Value</span></span>|<span data-ttu-id="505e3-167">Veredicto de filtro de spam</span><span class="sxs-lookup"><span data-stu-id="505e3-167">Spam filter verdict</span></span>|<span data-ttu-id="505e3-168">Descrição</span><span class="sxs-lookup"><span data-stu-id="505e3-168">Description</span></span>|
  |:-----|:-----|:-----|
  | <span data-ttu-id="505e3-169">**Permitido**</span><span class="sxs-lookup"><span data-stu-id="505e3-169">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="505e3-170">A mensagem foi marcada como não spam e/ou a filtragem ignorada antes de ser avaliada pela filtragem de spam (por exemplo, por uma regra de fluxo de emails, também conhecida como regra de transporte).</span><span class="sxs-lookup"><span data-stu-id="505e3-170">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="505e3-171">A mensagem ignorou a filtragem de spam por outros motivos (por exemplo, o remetente e o destinatário parecem estar na mesma organização).</span><span class="sxs-lookup"><span data-stu-id="505e3-171">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="505e3-172">**Blocked**</span><span class="sxs-lookup"><span data-stu-id="505e3-172">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="505e3-173">A mensagem foi marcada como spam antes de ser avaliada pela filtragem de spam (por exemplo, por uma regra de fluxo de emails).</span><span class="sxs-lookup"><span data-stu-id="505e3-173">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="505e3-174">**Detectado**</span><span class="sxs-lookup"><span data-stu-id="505e3-174">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="505e3-175">A mensagem foi marcada como spam pela filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="505e3-175">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="505e3-176">**Não detectado**</span><span class="sxs-lookup"><span data-stu-id="505e3-176">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="505e3-177">A mensagem foi marcada como não spam por filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="505e3-177">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="505e3-178">**Solta**</span><span class="sxs-lookup"><span data-stu-id="505e3-178">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="505e3-179">A mensagem ignorou a filtragem de spam porque foi liberada da quarentena.</span><span class="sxs-lookup"><span data-stu-id="505e3-179">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="505e3-180">**Permissão de locatário**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="505e3-180">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="505e3-181">A mensagem ignorou a filtragem de spam devido às configurações de política antispam (por exemplo, o remetente estava na lista de remetentes permitidos ou na lista de domínios permitidos).</span><span class="sxs-lookup"><span data-stu-id="505e3-181">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="505e3-182">**Bloco de locatário**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="505e3-182">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="505e3-183">A mensagem foi bloqueada por filtragem de spam devido às configurações de política antispam (por exemplo, o remetente estava na lista de remetentes permitidos ou na lista de domínios permitidos).</span><span class="sxs-lookup"><span data-stu-id="505e3-183">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="505e3-184">**Usuário permitir**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="505e3-184">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="505e3-185">A mensagem ignorou a filtragem de spam porque o remetente estava na lista de remetentes confiáveis do usuário no Outlook.</span><span class="sxs-lookup"><span data-stu-id="505e3-185">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="505e3-186">**Bloco de usuário**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="505e3-186">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="505e3-187">A mensagem foi bloqueada por filtragem de spam porque o remetente estava na lista de remetentes bloqueados de um usuário no Outlook.</span><span class="sxs-lookup"><span data-stu-id="505e3-187">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="505e3-188">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="505e3-188">**ZAP**</span></span>|<span data-ttu-id="505e3-189">n/d</span><span class="sxs-lookup"><span data-stu-id="505e3-189">n/a</span></span>|<span data-ttu-id="505e3-190">A [limpeza automática de zero horas (zap)](zero-hour-auto-purge.md) levou à mensagem entregue de acordo com suas configurações de política antispam (movidas para a pasta lixo eletrônico ou colocada em quarentena).</span><span class="sxs-lookup"><span data-stu-id="505e3-190">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|

  <span data-ttu-id="505e3-191"><sup>\*</sup>Revise suas políticas antispam, pois a mensagem permitida provavelmente teria sido bloqueada pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="505e3-191"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="505e3-192"><sup>\*\*</sup>Revise suas políticas antispam, pois essas mensagens devem ser colocadas em quarentena, não entregues.</span><span class="sxs-lookup"><span data-stu-id="505e3-192"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="505e3-193">**Locais de entrega**: Você provavelmente desejará investigar as mensagens que foram realmente entregues aos destinatários (na pasta Caixa de Entrada ou Lixo Eletrônico), mesmo se os usuários não clicarem na URL do payload na mensagem.</span><span class="sxs-lookup"><span data-stu-id="505e3-193">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="505e3-194">Você também pode remover as mensagens em quarentena da quarentena.</span><span class="sxs-lookup"><span data-stu-id="505e3-194">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="505e3-195">Para obter mais informações, consulte [Quarantine Email messages in Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="505e3-195">For more information, see [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="505e3-196">**Pasta excluída**</span><span class="sxs-lookup"><span data-stu-id="505e3-196">**Deleted folder**</span></span>

  - <span data-ttu-id="505e3-197">**Abandonado**</span><span class="sxs-lookup"><span data-stu-id="505e3-197">**Dropped**</span></span>

  - <span data-ttu-id="505e3-198">**Externo**: o destinatário está localizado em sua organização de email local.</span><span class="sxs-lookup"><span data-stu-id="505e3-198">**External**: The recipient is located in your on-premises email organization.</span></span>

  - <span data-ttu-id="505e3-199">**Falhou**</span><span class="sxs-lookup"><span data-stu-id="505e3-199">**Failed**</span></span>

  - <span data-ttu-id="505e3-200">**Encaminhadas**</span><span class="sxs-lookup"><span data-stu-id="505e3-200">**Forwarded**</span></span>

  - <span data-ttu-id="505e3-201">**Caixa de Entrada**</span><span class="sxs-lookup"><span data-stu-id="505e3-201">**Inbox**</span></span>

  - <span data-ttu-id="505e3-202">**Pasta Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="505e3-202">**Junk folder**</span></span>

  - <span data-ttu-id="505e3-203">**Quarentena**</span><span class="sxs-lookup"><span data-stu-id="505e3-203">**Quarantine**</span></span>

  - <span data-ttu-id="505e3-204">**Unknown**</span><span class="sxs-lookup"><span data-stu-id="505e3-204">**Unknown**</span></span>

> [!NOTE]
> <span data-ttu-id="505e3-205">Em todas as camadas que contêm mais de 10 itens, os dez principais itens são mostrados, enquanto o restante é agrupado em **outros**.</span><span class="sxs-lookup"><span data-stu-id="505e3-205">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="505e3-206">Cliques na URL</span><span class="sxs-lookup"><span data-stu-id="505e3-206">URL clicks</span></span>

<span data-ttu-id="505e3-207">Quando uma mensagem de phishing é entregue a um destinatário (na caixa de entrada ou na pasta lixo eletrônico), há sempre a chance de que o usuário clique na URL de carga.</span><span class="sxs-lookup"><span data-stu-id="505e3-207">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="505e3-208">Não clicar na URL em uma mensagem entregue é uma pequena medida do sucesso, mas você precisa determinar por que a mensagem de phishing foi entregue à caixa de correio em primeiro lugar.</span><span class="sxs-lookup"><span data-stu-id="505e3-208">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="505e3-209">Se um usuário clicou na URL de carga na mensagem de phishing, as ações são exibidas na área de **cliques da URL** do diagrama no modo de exibição detalhes da campanha.</span><span class="sxs-lookup"><span data-stu-id="505e3-209">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="505e3-210">**Permitido**</span><span class="sxs-lookup"><span data-stu-id="505e3-210">**Allowed**</span></span>

- <span data-ttu-id="505e3-211">**BlockPage**: o destinatário clicou na URL de carga, mas seu acesso ao site mal-intencionado foi bloqueado pelas políticas de [links seguros de ATP](atp-safe-links.md) em sua organização.</span><span class="sxs-lookup"><span data-stu-id="505e3-211">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="505e3-212">**BlockPageOverride**: o destinatário clicou na URL de carga da mensagem, os links seguros de ATP tentaram interrompê-los, mas eles tinham permissão para substituir o bloco.</span><span class="sxs-lookup"><span data-stu-id="505e3-212">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="505e3-213">Você precisa investigar suas [políticas de links seguros](set-up-atp-safe-links-policies.md) para ver por que os usuários têm permissão para substituir os links de segurança veredicto e continuar no site mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="505e3-213">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="505e3-214">**PendingDetonationPage**: os anexos seguros de ATP estão no processo de abertura da URL de carga em um ambiente de computador virtual e ver o que acontece.</span><span class="sxs-lookup"><span data-stu-id="505e3-214">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="505e3-215">**PendingDetonationPageOverride**: o destinatário tinha permissão para substituir o processo de acionamento de carga e abrir a URL sem aguardar os resultados.</span><span class="sxs-lookup"><span data-stu-id="505e3-215">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="505e3-216">Guias</span><span class="sxs-lookup"><span data-stu-id="505e3-216">Tabs</span></span>

<span data-ttu-id="505e3-217">Há várias guias no modo de exibição de detalhes da campanha que permitem uma investigação mais detalhada.</span><span class="sxs-lookup"><span data-stu-id="505e3-217">There are several tabs in the campaign details view that allow you to further investigate the campaign.</span></span>

- <span data-ttu-id="505e3-218">**Cliques de URL**: se os usuários não clicar na URL de carga na mensagem de phishing, esta seção ficará em branco.</span><span class="sxs-lookup"><span data-stu-id="505e3-218">**URL Clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="505e3-219">Se um usuário conseguir clicar na URL, os seguintes valores serão preenchidos:</span><span class="sxs-lookup"><span data-stu-id="505e3-219">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="505e3-220">**Usuário**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="505e3-220">**User**<sup>\*</sup></span></span>

  - <span data-ttu-id="505e3-221">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="505e3-221">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="505e3-222">**Hora do clique**</span><span class="sxs-lookup"><span data-stu-id="505e3-222">**Click Time**</span></span>

  - <span data-ttu-id="505e3-223">**Ação do clique**</span><span class="sxs-lookup"><span data-stu-id="505e3-223">**Click Action**</span></span>

- <span data-ttu-id="505e3-224">**IPs do remetente**</span><span class="sxs-lookup"><span data-stu-id="505e3-224">**Sender IPs**</span></span>

  - <span data-ttu-id="505e3-225">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="505e3-225">**Sender IP**<sup>\*</sup></span></span>

  - <span data-ttu-id="505e3-226">**Contagem total**</span><span class="sxs-lookup"><span data-stu-id="505e3-226">**Total Count**</span></span>

  - <span data-ttu-id="505e3-227">**Contagem na caixa de entrada**</span><span class="sxs-lookup"><span data-stu-id="505e3-227">**Inboxed Count**</span></span>

  - <span data-ttu-id="505e3-228">**Contagem bloqueado**</span><span class="sxs-lookup"><span data-stu-id="505e3-228">**Blocked Count**</span></span>

  - <span data-ttu-id="505e3-229">**SPF aprovado**: o remetente foi autenticado pela [estrutura de política de remetente (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="505e3-229">**SPF Passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="505e3-230">Um remetente que não passa pela validação SPF indica que o remetente não está autenticado ou a mensagem está falsificando um remetente legítimo.</span><span class="sxs-lookup"><span data-stu-id="505e3-230">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="505e3-231">**Remetentes**</span><span class="sxs-lookup"><span data-stu-id="505e3-231">**Senders**</span></span>

  - <span data-ttu-id="505e3-232">**Remetente**: Este é o endereço do remetente real no comando mail SMTP from, que não é necessariamente o endereço de email que os usuários vêem em seus clientes de email.</span><span class="sxs-lookup"><span data-stu-id="505e3-232">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>

  - <span data-ttu-id="505e3-233">**Contagem total**</span><span class="sxs-lookup"><span data-stu-id="505e3-233">**Total Count**</span></span>

  - <span data-ttu-id="505e3-234">**Caixa de entrada**</span><span class="sxs-lookup"><span data-stu-id="505e3-234">**Inboxed**</span></span>

  - <span data-ttu-id="505e3-235">**Não caixa de entrada**</span><span class="sxs-lookup"><span data-stu-id="505e3-235">**Not Inboxed**</span></span>

  - <span data-ttu-id="505e3-236">**DKIM passado**: o remetente foi autenticado por [chaves de domínio identificadas por email (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span><span class="sxs-lookup"><span data-stu-id="505e3-236">**DKIM Passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="505e3-237">Um remetente que não passa DKIM validação indica que o remetente não está autenticado ou a mensagem está falsificando um remetente legítimo.</span><span class="sxs-lookup"><span data-stu-id="505e3-237">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

  - <span data-ttu-id="505e3-238">**DMARC passado**: o remetente foi autenticado por [autenticação de mensagens baseadas em domínio, relatórios e conformidade (DMARC)](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="505e3-238">**DMARC Passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="505e3-239">Um remetente que não passa DMARC validação indica que o remetente não está autenticado ou a mensagem está falsificando um remetente legítimo.</span><span class="sxs-lookup"><span data-stu-id="505e3-239">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="505e3-240">**Payloads**</span><span class="sxs-lookup"><span data-stu-id="505e3-240">**Payloads**</span></span>

  - <span data-ttu-id="505e3-241">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="505e3-241">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="505e3-242">**Contagem total**</span><span class="sxs-lookup"><span data-stu-id="505e3-242">**Total Count**</span></span>

<span data-ttu-id="505e3-243"><sup>\*</sup> Clicar nesse valor abre um novo submenu que contém mais detalhes sobre o item especificado (usuário, URL, etc.) na parte superior do modo de exibição de detalhes da campanha.</span><span class="sxs-lookup"><span data-stu-id="505e3-243"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="505e3-244">Para retornar ao modo de exibição de detalhes da campanha, clique em **Concluído** no novo submenu.</span><span class="sxs-lookup"><span data-stu-id="505e3-244">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="505e3-245">Botões</span><span class="sxs-lookup"><span data-stu-id="505e3-245">Buttons</span></span>

<span data-ttu-id="505e3-246">Os botões no modo de exibição de detalhes da campanha permitem usar os recursos do Explorador de Ameaças para investigar ainda mais a campanha.</span><span class="sxs-lookup"><span data-stu-id="505e3-246">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="505e3-247">**Explorar campanhas**: abre uma nova guia de pesquisa do Explorador de Ameaças usando o valor **ID da campanha** como filtro de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="505e3-247">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="505e3-248">**Explorar mensagens de caixa de entrada**: abre uma nova guia de pesquisa do explorador de ameaças usando a **ID de campanha** e o **local de entrega: caixa de entrada** como o filtro de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="505e3-248">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
