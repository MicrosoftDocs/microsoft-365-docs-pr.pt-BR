---
title: Modos de Exibição de Campanhas no Office 365 ATP
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
ms.openlocfilehash: 65ae346fc4ffdcc502c7f479d7d92753cdb5b5bc
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599758"
---
# <a name="campaign-views-in-office-365-atp"></a><span data-ttu-id="5671a-103">Modos de Exibição de Campanha no Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="5671a-103">Campaign Views in Office 365 ATP</span></span>

> [!NOTE]
> <span data-ttu-id="5671a-104">Os recursos descritos neste tópico estão atualmente em versão prévia e estão sujeitos a alterações.</span><span class="sxs-lookup"><span data-stu-id="5671a-104">The features described in this topic are currently in preview, and are subject to change.</span></span>

<span data-ttu-id="5671a-105">Os Modos de Exibição de Campanhas é um recurso no ATP (Proteção Avançada contra Ameaças) no Centro de Conformidade e Segurança do Office 365 que identifica e categoriza os ataques de phishing no serviço.</span><span class="sxs-lookup"><span data-stu-id="5671a-105">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Office 365 Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="5671a-106">Os Modos de Exibição de Campanhas podem ajudá-lo a:</span><span class="sxs-lookup"><span data-stu-id="5671a-106">Campaign Views can help you to:</span></span>

- <span data-ttu-id="5671a-107">Investigar e responder de forma eficiente os ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="5671a-107">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="5671a-108">Entender melhor o escopo do ataque.</span><span class="sxs-lookup"><span data-stu-id="5671a-108">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="5671a-109">Mostrar valor aos tomadores de decisões.</span><span class="sxs-lookup"><span data-stu-id="5671a-109">Show value to decision makers.</span></span>

<span data-ttu-id="5671a-110">Os Modos de Exibição de Campanhas permitem que você veja o panorama de um ataque de forma mais rápida e completa do que qualquer pessoa.</span><span class="sxs-lookup"><span data-stu-id="5671a-110">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="5671a-111">O que é uma campanha?</span><span class="sxs-lookup"><span data-stu-id="5671a-111">What is a campaign?</span></span>

<span data-ttu-id="5671a-112">Uma campanha é um ataque coordenado por email contra uma ou várias organizações.</span><span class="sxs-lookup"><span data-stu-id="5671a-112">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="5671a-113">Hoje, os ataques por email que roubam credenciais e dados da empresa são negócios grandes e lucrativos.</span><span class="sxs-lookup"><span data-stu-id="5671a-113">Today, email attacks that steal credentials and company data are a big and lucrative business.</span></span> <span data-ttu-id="5671a-114">À medida que as tecnologias focam seus esforços para interromper os ataques, os invasores são sofisticados o suficiente para modificar seus métodos em um esforço para garantir o sucesso contínuo.</span><span class="sxs-lookup"><span data-stu-id="5671a-114">As technologies increase in an effort to stop attacks, attackers are sophisticated enough to modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="5671a-115">A Microsoft aproveita o vasto volume de dados e experiência de antiphishing, antispam e antimalware no serviço do Office 365 em todo o mundo para identificar as campanhas.</span><span class="sxs-lookup"><span data-stu-id="5671a-115">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data and experience across the entire Office 365 service world-wide to identify campaigns.</span></span> <span data-ttu-id="5671a-116">As informações do ataque são analisadas e classificadas de acordo com vários fatores.</span><span class="sxs-lookup"><span data-stu-id="5671a-116">The attack information is analyzed and classified according to several factors.</span></span> <span data-ttu-id="5671a-117">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5671a-117">For example:</span></span>

- <span data-ttu-id="5671a-118">**Fonte de ataque**: endereços IP de origem e domínios de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="5671a-118">**Attack source**: Source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="5671a-119">**Propriedades da mensagem de ataque**: o conteúdo, estilo e tom das mensagens de ataque.</span><span class="sxs-lookup"><span data-stu-id="5671a-119">**Attack message properties**: The content, style, and tone of the attack messages.</span></span>

- <span data-ttu-id="5671a-120">**Destinatários de um ataque**: domínios do destinatário, funções de trabalho do destinatário (administradores, executivos, etc.), tipos de empresa (grandes, pequenas, públicas, privadas etc.) e setores.</span><span class="sxs-lookup"><span data-stu-id="5671a-120">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="5671a-121">**Payload de ataque**: links mal-intencionados, anexos ou outros payloads.</span><span class="sxs-lookup"><span data-stu-id="5671a-121">**Attack payload**: Malicious links, attachments, or other payloads.</span></span>

## <a name="campaign-views-the-office-365-security--compliance-center"></a><span data-ttu-id="5671a-122">Modos de Exibição de Campanhas no Centro de Conformidade e Segurança do Office 365</span><span class="sxs-lookup"><span data-stu-id="5671a-122">Campaign Views the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="5671a-123">Os Modos de Exibição de Campanhas estão disponíveis no [Centro de Conformidade e Segurança](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center) nos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="5671a-123">Campaign Views is available in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center) at the following locations:</span></span>

- <span data-ttu-id="5671a-124">**Gerenciamento de ameaças** \> **Explorer** \> **Exibir** \> **Phish** \> **Campanha principal (visualização)**</span><span class="sxs-lookup"><span data-stu-id="5671a-124">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Top campaign (Preview)**</span></span>

- <span data-ttu-id="5671a-125">**Gerenciamento de ameaças** \> **Explorer** \> **Exibir** \> **Todos os emails** \> **Campanha principal (visualização)**</span><span class="sxs-lookup"><span data-stu-id="5671a-125">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Top campaign (Preview)**</span></span>

![Visão geral das campanhas no Centro de Conformidade e Segurança](../media/campaigns-overview.png)

> [!TIP]
> <span data-ttu-id="5671a-127">No momento, a única filtragem disponível é o intervalo de datas.</span><span class="sxs-lookup"><span data-stu-id="5671a-127">Currently, the only filtering that's available is the date range.</span></span> <span data-ttu-id="5671a-128">Caso não veja nenhum dado da campanha, experimente alterar o intervalo de datas.</span><span class="sxs-lookup"><span data-stu-id="5671a-128">If you don't see any campaign data, try changing the date range.</span></span>

<span data-ttu-id="5671a-129">A página Visão geral mostra as seguintes informações sobre a campanha:</span><span class="sxs-lookup"><span data-stu-id="5671a-129">The overview page shows the following information about the campaign:</span></span>

- <span data-ttu-id="5671a-130">**Nome**</span><span class="sxs-lookup"><span data-stu-id="5671a-130">**Name**</span></span>

- <span data-ttu-id="5671a-131">**Exemplo de assunto**: a linha de assunto de uma das mensagens na campanha.</span><span class="sxs-lookup"><span data-stu-id="5671a-131">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="5671a-132">Observe que _todas_ as mensagens na campanha não terão necessariamente essa mesma linha de assunto.</span><span class="sxs-lookup"><span data-stu-id="5671a-132">Note that _all_ the messages in the campaign will not necessarily have this same subject line.</span></span>

- <span data-ttu-id="5671a-133">**Tipo**: atualmente, esse valor será sempre **Phish**.</span><span class="sxs-lookup"><span data-stu-id="5671a-133">**Type**: Currently, this value will always be **Phish**.</span></span>

- <span data-ttu-id="5671a-134">**Subtipo**: quando disponível, a marca que está sendo visada por esta campanha.</span><span class="sxs-lookup"><span data-stu-id="5671a-134">**Subtype**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="5671a-135">Quando a detecção é orientada pela tecnologia ATP, o prefixo **ATP-** é adicionado ao valor do subtipo.</span><span class="sxs-lookup"><span data-stu-id="5671a-135">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="5671a-136">**Destinatários**: o número de usuários que foram alvos desta campanha.</span><span class="sxs-lookup"><span data-stu-id="5671a-136">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="5671a-137">**Entregue**: o número de usuários que receberam mensagens desta campanha na caixa de entrada.</span><span class="sxs-lookup"><span data-stu-id="5671a-137">**Delivered**: The number of users that received messages from this campaign into their Inbox.</span></span>

- <span data-ttu-id="5671a-138">**ID**: o identificador exclusivo da campanha.</span><span class="sxs-lookup"><span data-stu-id="5671a-138">**ID**: A unique identifier for the campaign.</span></span>

<span data-ttu-id="5671a-139">Quando você clica no nome de uma campanha, os detalhes da campanha aparecem em um submenu.</span><span class="sxs-lookup"><span data-stu-id="5671a-139">When you click on the name of a campaign, the campaign details appears in a flyout.</span></span>

## <a name="campaign-details"></a><span data-ttu-id="5671a-140">Detalhes da campanha</span><span class="sxs-lookup"><span data-stu-id="5671a-140">Campaign details</span></span>

<span data-ttu-id="5671a-141">No modo de exibição de detalhes da campanha, estão disponíveis muitas informações sobre a campanha:</span><span class="sxs-lookup"><span data-stu-id="5671a-141">In the campaign details view, a lot of information is available about the campaign:</span></span>

- <span data-ttu-id="5671a-142">Informações da campanha:</span><span class="sxs-lookup"><span data-stu-id="5671a-142">Campaign information:</span></span>

  - <span data-ttu-id="5671a-143">**ID**: o mesmo identificador exclusivo da campanha na tela visão geral.</span><span class="sxs-lookup"><span data-stu-id="5671a-143">**ID**: The same unique identifier of the campaign from the overview screen.</span></span>

  - <span data-ttu-id="5671a-144">**Iniciado** e **Finalizado**: o filtro do intervalo de datas selecionado.</span><span class="sxs-lookup"><span data-stu-id="5671a-144">**Started** and **Ended**: the date range filter you selected.</span></span>

  - <span data-ttu-id="5671a-145">**Impacto**: o número de mensagens enviadas no intervalo de datas selecionado, quantas eram "caixa de entrada" (isto é, entregue na caixa de entrada) e quantos usuários clicaram na URL do payload na mensagem de phishing.</span><span class="sxs-lookup"><span data-stu-id="5671a-145">**Impact**: the number of messages sent in the date range you selected, how many were "inboxed" (that is, delivered to the Inbox), and how many users clicked on the URL payload in the phishing message.</span></span>

  - <span data-ttu-id="5671a-146">Uma linha do tempo de atividade da campanha: quando a campanha começou e terminou e o volume de mensagens neste período.</span><span class="sxs-lookup"><span data-stu-id="5671a-146">A timeline of campaign activity: When the campaign started and ended, and the volume of messages over time.</span></span>

### <a name="campaign-flow"></a><span data-ttu-id="5671a-147">Fluxo de campanha</span><span class="sxs-lookup"><span data-stu-id="5671a-147">Campaign flow</span></span>

<span data-ttu-id="5671a-148">Os detalhes importantes sobre a campanha são apresentados em um diagrama de fluxo horizontal (conhecido como diagrama _Sankey_) na seção **Fluxo**.</span><span class="sxs-lookup"><span data-stu-id="5671a-148">Important details about the campaign are presented in a horizontal flow diagram (known as a _Sankey_ diagram) in the **Flow** section.</span></span> <span data-ttu-id="5671a-149">Esses detalhes ajudarão você a entender os elementos da campanha e o impacto potencial na sua organização.</span><span class="sxs-lookup"><span data-stu-id="5671a-149">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

![Detalhes da campanha que não contêm cliques de usuários na URL](../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="5671a-151">Se passar o mouse sobre uma faixa horizontal no diagrama, você verá o número de mensagens relacionadas (por exemplo, mensagens de um determinado IP de origem, mensagens do IP de origem usando o domínio do remetente especificado, etc.).</span><span class="sxs-lookup"><span data-stu-id="5671a-151">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="5671a-152">O diagrama contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="5671a-152">The diagram contains the following information:</span></span>

- <span data-ttu-id="5671a-153">**IPs do remetente**</span><span class="sxs-lookup"><span data-stu-id="5671a-153">**Sender IPs**</span></span>

- <span data-ttu-id="5671a-154">**Domínios do remetente**</span><span class="sxs-lookup"><span data-stu-id="5671a-154">**Sender domains**</span></span>

- <span data-ttu-id="5671a-155">**Filtrar veredictos**: os valores aqui estão relacionados aos veredictos do filtro antiphishing e antispam disponíveis, como descrito em [Cabeçalhos de mensagem antispam](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="5671a-155">**Filter verdicts**: The values here are related to the available anti-phishing and anti-spam filter verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="5671a-156">O mais importante aqui são os valores **Permissão do locatário**, que significa que uma configuração definida na organização permitiu uma mensagem que de outra forma seria bloqueada pelo serviço (por exemplo, um domínio na lista de Remetentes permitidos).</span><span class="sxs-lookup"><span data-stu-id="5671a-156">Of great interest here are the values **Tenant Allow**, which means a configured setting in the organization allowed a message through that would have been otherwise blocked by the service (for example, a domain in the Allowed Senders list).</span></span>

  - <span data-ttu-id="5671a-157">**Bloqueio do locatário**: esse valor indica que uma configuração na sua organização (por exemplo, uma entrada de domínio na [lista de Remetentes bloqueados](create-block-sender-lists-in-office-365.md)) detectou a mensagem e determinou onde ela foi entregue.</span><span class="sxs-lookup"><span data-stu-id="5671a-157">**Tenant Block**: This value indicates that a setting in your organization (for example, a domain entry in the [Blocked Senders list](create-block-sender-lists-in-office-365.md)) both detected the message and determined where it was delivered.</span></span> <span data-ttu-id="5671a-158">Para mensagens que não estão em quarentena, examine as configurações de remetentes bloqueados para determinar por que a mensagem foi entregue.</span><span class="sxs-lookup"><span data-stu-id="5671a-158">For messages that weren't quarantined, review your blocked senders settings to determine why the message was delivered.</span></span>

  - <span data-ttu-id="5671a-159">**Detectado**</span><span class="sxs-lookup"><span data-stu-id="5671a-159">**Detected**</span></span>

  - <span data-ttu-id="5671a-160">**Permissão do locatário**</span><span class="sxs-lookup"><span data-stu-id="5671a-160">**Tenant Allow**</span></span>

- <span data-ttu-id="5671a-161">**Locais de entrega**: Você provavelmente desejará investigar as mensagens que foram realmente entregues aos destinatários (na pasta Caixa de Entrada ou Lixo Eletrônico), mesmo se os usuários não clicarem na URL do payload na mensagem.</span><span class="sxs-lookup"><span data-stu-id="5671a-161">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="5671a-162">Você também pode remover as mensagens em quarentena em [Colocar mensagens de email em quarentena no Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="5671a-162">You can also remove the quarantined messages from [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="5671a-163">**Pasta Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="5671a-163">**Junk folder**</span></span>

  - <span data-ttu-id="5671a-164">**Quarentena**</span><span class="sxs-lookup"><span data-stu-id="5671a-164">**Quarantine**</span></span>

  - <span data-ttu-id="5671a-165">**Caixa de Entrada**</span><span class="sxs-lookup"><span data-stu-id="5671a-165">**Inbox**</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="5671a-166">Cliques na URL</span><span class="sxs-lookup"><span data-stu-id="5671a-166">URL clicks</span></span>

<span data-ttu-id="5671a-167">Há sempre uma chance de que as mensagens entregues na pasta Caixa de Entrada ou Lixo Eletrônico do destinatário possam ser acionadas pelo usuário (ou seja, o usuário clicará na URL mal-intencionada da mensagem).</span><span class="sxs-lookup"><span data-stu-id="5671a-167">There's always the chance that messages delivered to the recipient's Inbox or Junk Email folder can be acted upon by the user (that is, user will click on the malicious URL in the message).</span></span> <span data-ttu-id="5671a-168">Se eles não clicaram, isso é uma pequena vitória, embora você certamente precise determinar por que a mensagem prejudicial foi entregue à caixa de correio deles.</span><span class="sxs-lookup"><span data-stu-id="5671a-168">If they haven't, that's a small measure of success, although you certainly need to determine why the harmful message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="5671a-169">Se um usuário clicou na URL mal-intencionada, as ações serão exibidas na área do diagrama **Cliques na URL**.</span><span class="sxs-lookup"><span data-stu-id="5671a-169">If a user has clicked on the malicious URL, the actions are displayed in the **URL clicks** area of the diagram.</span></span>

![Detalhes da campanha que contêm cliques de usuários na URL](../media/campaign-details-with-recipient-actions.png)

- <span data-ttu-id="5671a-171">**Bloqueio de Links Seguros**: este valor indica que o destinatário clicou na URL do payload na mensagem, mas foi bloqueado pelas políticas de [Links Seguros ATP](atp-safe-links.md) da sua organização.</span><span class="sxs-lookup"><span data-stu-id="5671a-171">**Safe Links Block**: This value indicates the recipient clicked on the payload URL in the message, but it was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="5671a-172">**Substituir Bloqueio de Links Seguros**: esse valor também indica que o destinatário clicou na URL do payload na mensagem, os Links de Seguros do ATP tentaram pará-lo, mas eles tiveram permissão para substituir o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="5671a-172">**Safe Links Block Override**: This value also indicates the recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="5671a-173">É necessário investigar as suas [políticas de Links Seguros](set-up-atp-safe-links-policies.md)para ver por que os usuários têm permissão para substituir o veredicto dos Links Seguros e clicar em URLs mal-intencionadas.</span><span class="sxs-lookup"><span data-stu-id="5671a-173">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and click on malicious URLs.</span></span>

### <a name="tabs"></a><span data-ttu-id="5671a-174">Guias</span><span class="sxs-lookup"><span data-stu-id="5671a-174">Tabs</span></span>

<span data-ttu-id="5671a-175">Há várias guias no modo de exibição de detalhes da campanha que permitem uma investigação mais detalhada.</span><span class="sxs-lookup"><span data-stu-id="5671a-175">There are several tabs in the campaign details view that allow you to further investigate the campaign.</span></span>

- <span data-ttu-id="5671a-176">**Cliques na URL**: se não houve cliques na URL do payload na mensagem de phishing, essa seção ficará em branco.</span><span class="sxs-lookup"><span data-stu-id="5671a-176">**URL Clicks**: If the payload URL in the phishing message wasn't clicked, this section will be blank.</span></span> <span data-ttu-id="5671a-177">Se um usuário conseguiu clicar na URL, você</span><span class="sxs-lookup"><span data-stu-id="5671a-177">If a user was able to click on the URL, you</span></span>

  - <span data-ttu-id="5671a-178">**Usuário**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5671a-178">**User**<sup>\*</sup></span></span>

  - <span data-ttu-id="5671a-179">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5671a-179">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="5671a-180">**Hora do clique**</span><span class="sxs-lookup"><span data-stu-id="5671a-180">**Click Time**</span></span>

  - <span data-ttu-id="5671a-181">**Ação do clique**</span><span class="sxs-lookup"><span data-stu-id="5671a-181">**Click Action**</span></span>

- <span data-ttu-id="5671a-182">**IPs do remetente**</span><span class="sxs-lookup"><span data-stu-id="5671a-182">**Sender IPs**</span></span>

  - <span data-ttu-id="5671a-183">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5671a-183">**Sender IP**<sup>\*</sup></span></span>

  - <span data-ttu-id="5671a-184">**Contagem total**</span><span class="sxs-lookup"><span data-stu-id="5671a-184">**Total Count**</span></span>

  - <span data-ttu-id="5671a-185">**Contagem na caixa de entrada**</span><span class="sxs-lookup"><span data-stu-id="5671a-185">**Inboxed Count**</span></span>

  - <span data-ttu-id="5671a-186">**Contagem bloqueado**</span><span class="sxs-lookup"><span data-stu-id="5671a-186">**Blocked Count**</span></span>

  - <span data-ttu-id="5671a-187">**SPF transmitido**</span><span class="sxs-lookup"><span data-stu-id="5671a-187">**SPF Passed**</span></span>

- <span data-ttu-id="5671a-188">**Remetentes**</span><span class="sxs-lookup"><span data-stu-id="5671a-188">**Senders**</span></span>

  - <span data-ttu-id="5671a-189">**Remetente**</span><span class="sxs-lookup"><span data-stu-id="5671a-189">**Sender**</span></span>

  - <span data-ttu-id="5671a-190">**Contagem total**</span><span class="sxs-lookup"><span data-stu-id="5671a-190">**Total Count**</span></span>

  - <span data-ttu-id="5671a-191">**Contagem na caixa de entrada**</span><span class="sxs-lookup"><span data-stu-id="5671a-191">**Inboxed Count**</span></span>

  - <span data-ttu-id="5671a-192">**Contagem bloqueado**</span><span class="sxs-lookup"><span data-stu-id="5671a-192">**Blocked Count**</span></span>

  - <span data-ttu-id="5671a-193">**DKIM aprovado**</span><span class="sxs-lookup"><span data-stu-id="5671a-193">**DKIM Passed**</span></span>

  - <span data-ttu-id="5671a-194">**DMARC aprovado**</span><span class="sxs-lookup"><span data-stu-id="5671a-194">**DMARC Passed**</span></span>

- <span data-ttu-id="5671a-195">**Payloads**</span><span class="sxs-lookup"><span data-stu-id="5671a-195">**Payloads**</span></span>

  - <span data-ttu-id="5671a-196">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5671a-196">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="5671a-197">**Contagem total**</span><span class="sxs-lookup"><span data-stu-id="5671a-197">**Total Count**</span></span>

<span data-ttu-id="5671a-198"><sup>\*</sup> Clicar nesse valor abre um novo submenu que contém mais detalhes sobre o item especificado (usuário, URL, etc.) na parte superior do modo de exibição de detalhes da campanha.</span><span class="sxs-lookup"><span data-stu-id="5671a-198"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="5671a-199">Para retornar ao modo de exibição de detalhes da campanha, clique em **Concluído** no novo submenu.</span><span class="sxs-lookup"><span data-stu-id="5671a-199">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="5671a-200">Botões</span><span class="sxs-lookup"><span data-stu-id="5671a-200">Buttons</span></span>

<span data-ttu-id="5671a-201">Os botões no modo de exibição de detalhes da campanha permitem usar os recursos do Explorador de Ameaças para investigar ainda mais a campanha.</span><span class="sxs-lookup"><span data-stu-id="5671a-201">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="5671a-202">**Explorar campanhas**: abre uma nova guia de pesquisa do Explorador de Ameaças usando o valor **ID da campanha** como filtro de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="5671a-202">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="5671a-203">**Explorar mensagens da Caixa de Entrada**: abre uma nova guia de pesquisa do Explorador de Ameaças usando a **ID da campanha** e o **Local de entrega: Caixa de Entrada** como filtro da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="5671a-203">**Explore Inbox messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
