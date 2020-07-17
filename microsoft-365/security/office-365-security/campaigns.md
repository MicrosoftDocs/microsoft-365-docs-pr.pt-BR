---
title: Exibições de campanha na ATP
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
ms.openlocfilehash: fe443c43fa5cea8ec6e3e1c0bc5ee5307b5c28f6
ms.sourcegitcommit: 9ee1261c405f82b49c62390a25dfdea23340d644
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2020
ms.locfileid: "45039423"
---
# <a name="campaign-views-in-atp"></a><span data-ttu-id="7b2d9-103">Exibições de campanha na ATP</span><span class="sxs-lookup"><span data-stu-id="7b2d9-103">Campaign Views in ATP</span></span>

<span data-ttu-id="7b2d9-104">O modo de exibição de campanha é um recurso da proteção avançada contra ameaças (ATP) no centro de conformidade & segurança que identifica e categoriza os ataques de phishing no serviço.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="7b2d9-105">Os Modos de Exibição de Campanhas podem ajudá-lo a:</span><span class="sxs-lookup"><span data-stu-id="7b2d9-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="7b2d9-106">Investigar e responder de forma eficiente os ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="7b2d9-107">Entender melhor o escopo do ataque.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="7b2d9-108">Mostrar valor aos tomadores de decisões.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-108">Show value to decision makers.</span></span>

<span data-ttu-id="7b2d9-109">Os Modos de Exibição de Campanhas permitem que você veja o panorama de um ataque de forma mais rápida e completa do que qualquer pessoa.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="7b2d9-110">O que é uma campanha?</span><span class="sxs-lookup"><span data-stu-id="7b2d9-110">What is a campaign?</span></span>

<span data-ttu-id="7b2d9-111">Uma campanha é um ataque coordenado por email contra uma ou várias organizações.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="7b2d9-112">Os ataques de email que roubam credenciais e dados da empresa são um setor grande e lucrative.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="7b2d9-113">À medida que as tecnologias aumentam em um esforço para interromper ataques, os invasores modificam seus métodos em um esforço para garantir o sucesso contínuo.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="7b2d9-114">A Microsoft aproveita as vastas quantidades de dados anti-phishing, antispam e antimalware em todo o serviço para ajudar a identificar campanhas.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="7b2d9-115">Analisamos e classificamos as informações de ataque de acordo com vários fatores.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="7b2d9-116">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7b2d9-116">For example:</span></span>

- <span data-ttu-id="7b2d9-117">**Fonte de ataque**: os endereços IP de origem e os domínios de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-117">**Attack source**: The source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="7b2d9-118">**Propriedades da mensagem de ataque**: o conteúdo, o estilo e o Tom das mensagens.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-118">**Attack message properties**: The content, style, and tone of the messages.</span></span>

- <span data-ttu-id="7b2d9-119">**Destinatários de um ataque**: domínios do destinatário, funções de trabalho do destinatário (administradores, executivos, etc.), tipos de empresa (grandes, pequenas, públicas, privadas etc.) e setores.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="7b2d9-120">**Carga de ataque**: links mal-intencionados, anexos ou outras cargas nas mensagens.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-120">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="7b2d9-121">Uma campanha pode ser de vida curta ou pode abranger vários dias, semanas ou meses com períodos ativos e inativos.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="7b2d9-122">Uma campanha pode ser iniciada em sua organização específica ou sua organização pode fazer parte de uma campanha maior em várias empresas.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-security--compliance-center"></a><span data-ttu-id="7b2d9-123">Exibições de campanha o centro de conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="7b2d9-123">Campaign Views the Security & Compliance Center</span></span>

<span data-ttu-id="7b2d9-124">Os modos de exibição de campanha estão disponíveis no [centro de conformidade & segurança](https://protection.office.com) em campanhas de **Gerenciamento de ameaças** \> **Campaigns**ou diretamente em <https://protection.office.com/campaigns> .</span><span class="sxs-lookup"><span data-stu-id="7b2d9-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![Visão geral das campanhas no Centro de Conformidade e Segurança](../../media/campaigns-overview.png)

<span data-ttu-id="7b2d9-126">Você também pode obter modos de exibição de campanha de:</span><span class="sxs-lookup"><span data-stu-id="7b2d9-126">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="7b2d9-127">**Gerenciamento** \> de ameaças **Explorer** \> **Exibir** \> **Campanhas**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="7b2d9-128">**Gerenciamento** \> de ameaças **Explorer** \> **Exibir** \> **Todos os emails** \> Guia **campanha**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>

- <span data-ttu-id="7b2d9-129">**Gerenciamento** \> de ameaças **Explorer** \> **Exibir** \> **Phish** \> Guia **campanha**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-129">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>

- <span data-ttu-id="7b2d9-130">**Gerenciamento** \> de ameaças **Explorer** \> **Exibir** \> **Malware** \> Guia **campanha**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-130">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="7b2d9-131">Para acessar modos de exibição de campanha, você precisa ser membro dos grupos de função de **Gerenciamento da organização**, **administrador de segurança**ou leitor de **segurança** no centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-131">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="7b2d9-132">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="7b2d9-132">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="7b2d9-133">Visão geral de campanhas</span><span class="sxs-lookup"><span data-stu-id="7b2d9-133">Campaigns overview</span></span>

<span data-ttu-id="7b2d9-134">A página Visão geral mostra informações sobre todas as campanhas.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-134">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="7b2d9-135">Na guia **campanha** padrão, a área **tipo de campanha** mostra um gráfico de barras que mostra o número de destinatários por dia.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-135">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="7b2d9-136">Por padrão, o gráfico mostra tanto dados de **phishing** quanto de **malware** .</span><span class="sxs-lookup"><span data-stu-id="7b2d9-136">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="7b2d9-137">Se você não vir nenhum dado da campanha, tente alterar o intervalo de datas ou os [filtros](#filters-and-settings).</span><span class="sxs-lookup"><span data-stu-id="7b2d9-137">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="7b2d9-138">O restante da página Visão geral mostra as seguintes informações na guia **campanha** :</span><span class="sxs-lookup"><span data-stu-id="7b2d9-138">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="7b2d9-139">**Nome**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-139">**Name**</span></span>

- <span data-ttu-id="7b2d9-140">**Exemplo de assunto**: a linha de assunto de uma das mensagens na campanha.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-140">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="7b2d9-141">Observe que todas as mensagens na campanha não terão necessariamente o mesmo assunto.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-141">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="7b2d9-142">**Direcionado**: o percentual conforme calculado por: (o número de destinatários da campanha em sua organização)/(o número total de destinatários na campanha em todas as organizações no serviço).</span><span class="sxs-lookup"><span data-stu-id="7b2d9-142">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="7b2d9-143">Esse valor indica o grau para o qual a campanha é especificamente direcionada para sua organização (um valor mais alto) versus direcionado para outras organizações no serviço (um valor mais baixo).</span><span class="sxs-lookup"><span data-stu-id="7b2d9-143">This value indicates the degree to which the campaign is specifically directed at your organization (a higher value) vs. directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="7b2d9-144">**Tipo**: esse valor é **Phish** ou **malware**.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-144">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="7b2d9-145">**Subtipo**: esse valor contém mais detalhes sobre a campanha.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-145">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="7b2d9-146">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7b2d9-146">For example:</span></span>

  - <span data-ttu-id="7b2d9-147">**Phish**: quando disponível, a marca que está sendo enphishingada por esta campanha.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-147">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="7b2d9-148">Por exemplo,,,,, `Microsoft` `365` `Unknown` `Outlook` ou `DocuSign` .</span><span class="sxs-lookup"><span data-stu-id="7b2d9-148">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>

  - <span data-ttu-id="7b2d9-149">**Malware**: por exemplo, `HTML/PHISH` ou `HTML/<MalwareFamilyName>` .</span><span class="sxs-lookup"><span data-stu-id="7b2d9-149">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

<span data-ttu-id="7b2d9-150">Quando disponível, a marca que está sendo enphishingada por esta campanha.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-150">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="7b2d9-151">Quando a detecção é orientada pela tecnologia ATP, o prefixo **ATP-** é adicionado ao valor de subtipo.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-151">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="7b2d9-152">**Destinatários**: o número de usuários que foram alvos desta campanha.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-152">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="7b2d9-153">**Caixa de entrada**: o número de usuários que receberam mensagens desta campanha em sua caixa de entrada (não entregue na pasta lixo eletrônico).</span><span class="sxs-lookup"><span data-stu-id="7b2d9-153">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="7b2d9-154">**Clicado**: o número de usuários que clicaram na URL ou abriram o anexo na mensagem de phishing.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-154">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="7b2d9-155">**Taxa de clique**: a porcentagem conforme calculada por "**clicado**em  /  **caixa de entrada**".</span><span class="sxs-lookup"><span data-stu-id="7b2d9-155">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="7b2d9-156">Esse valor é um indicador da eficácia da campanha e se os destinatários podem identificar a mensagem como phishing e evitar clicar na URL de carga.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-156">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

  <span data-ttu-id="7b2d9-157">Observe que esse valor não é usado em campanhas de malware.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-157">Note that this value isn't used in malware campaigns.</span></span>

- <span data-ttu-id="7b2d9-158">**Visitado**: quantos usuários realmente o fizeram no site de carga de transferência.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-158">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="7b2d9-159">Se houver valores **clicados** , mas os links seguros bloquearam o acesso ao site, esse valor será zero.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-159">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="7b2d9-160">A guia **origem da campanha** mostra as fontes de mensagens em um mapa do mundo.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-160">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="7b2d9-161">Filtros e configurações</span><span class="sxs-lookup"><span data-stu-id="7b2d9-161">Filters and settings</span></span>

<span data-ttu-id="7b2d9-162">Na parte superior da página modos de exibição de campanha, há várias configurações de filtro e de consulta para ajudá-lo a encontrar e isolar campanhas específicas.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-162">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![Filtros de campanha](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="7b2d9-164">A filtragem mais básica que você pode fazer é a data/hora de início e a data/hora de término.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-164">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="7b2d9-165">Para filtrar mais detalhadamente o modo de exibição, você pode fazer uma única propriedade com vários valores, clicando no botão **tipo de campanha** , fazendo sua seleção e, em seguida, clicando em **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-165">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="7b2d9-166">As propriedades de campanha disponíveis são descritas na lista a seguir:</span><span class="sxs-lookup"><span data-stu-id="7b2d9-166">The available campaign properties are described in the following list:</span></span>

- <span data-ttu-id="7b2d9-167">Básico</span><span class="sxs-lookup"><span data-stu-id="7b2d9-167">Basic</span></span>

  - <span data-ttu-id="7b2d9-168">**Tipo de campanha**: selecione **malware** ou **phishing**.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-168">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="7b2d9-169">Limpar as seleções tem o mesmo resultado que selecionar ambos.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-169">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="7b2d9-170">**Nome da campanha**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-170">**Campaign name**</span></span>
  - <span data-ttu-id="7b2d9-171">**Subtipo de campanha**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-171">**Campaign subtype**</span></span>
  - <span data-ttu-id="7b2d9-172">**Sender**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-172">**Sender**</span></span>
  - <span data-ttu-id="7b2d9-173">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-173">**Recipients**</span></span>
  - <span data-ttu-id="7b2d9-174">**Domínio do remetente**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-174">**Sender domain**</span></span>
  - <span data-ttu-id="7b2d9-175">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-175">**Subject**</span></span>
  - <span data-ttu-id="7b2d9-176">**Nome do arquivo anexo**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-176">**Attachment filename**</span></span>
  - <span data-ttu-id="7b2d9-177">**Família de malware**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-177">**Malware family**</span></span>
  - <span data-ttu-id="7b2d9-178">**Ação de entrega**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-178">**Delivery action**</span></span>
  - <span data-ttu-id="7b2d9-179">**Tecnologia de detecção**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-179">**Detection technology**</span></span>
  - <span data-ttu-id="7b2d9-180">**Marcas**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-180">**Tags**</span></span>
  - <span data-ttu-id="7b2d9-181">**Substituições de sistema**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-181">**System overrides**</span></span>

- <span data-ttu-id="7b2d9-182">Avançado</span><span class="sxs-lookup"><span data-stu-id="7b2d9-182">Advanced</span></span>

  - <span data-ttu-id="7b2d9-183">**ID de mensagem da Internet**: disponível no campo de cabeçalho **Message-ID** no cabeçalho da mensagem.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-183">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="7b2d9-184">Um valor de exemplo é `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Observe os colchetes angulares).</span><span class="sxs-lookup"><span data-stu-id="7b2d9-184">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  
  - <span data-ttu-id="7b2d9-185">**ID da mensagem de rede**: um valor de GUID que está disponível no campo de cabeçalho **X-MS-Exchange-Organization-Network-Message-ID** no cabeçalho da mensagem.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-185">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  
  - <span data-ttu-id="7b2d9-186">**IP do remetente**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-186">**Sender IP**</span></span>
  
  - <span data-ttu-id="7b2d9-187">**Attachment SHA256**: para localizar o valor de hash SHA256 de um arquivo no Windows, execute o seguinte comando em um prompt de comando: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .</span><span class="sxs-lookup"><span data-stu-id="7b2d9-187">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  
  - <span data-ttu-id="7b2d9-188">**ID do cluster**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-188">**Cluster ID**</span></span>
  
  - <span data-ttu-id="7b2d9-189">**ID da política de alerta**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-189">**Alert Policy ID**</span></span>

- <span data-ttu-id="7b2d9-190">URLs</span><span class="sxs-lookup"><span data-stu-id="7b2d9-190">URLs</span></span>

  - <span data-ttu-id="7b2d9-191">**Domínio da URL**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-191">**URL domain**</span></span>
  - <span data-ttu-id="7b2d9-192">**Caminho e domínio da URL**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-192">**URL domain and path**</span></span>
  - <span data-ttu-id="7b2d9-193">**URL**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-193">**URL**</span></span>
  - <span data-ttu-id="7b2d9-194">**Caminho da URL**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-194">**URL path**</span></span>
  - <span data-ttu-id="7b2d9-195">**Clique em veredicto**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-195">**Click verdict**</span></span>

<span data-ttu-id="7b2d9-196">Para uma filtragem mais avançada, incluindo a filtragem por várias propriedades, você pode clicar no botão de **filtro avançado** para criar uma consulta.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-196">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="7b2d9-197">As mesmas propriedades de campanha estão disponíveis, mas com os seguintes aprimoramentos:</span><span class="sxs-lookup"><span data-stu-id="7b2d9-197">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="7b2d9-198">Você pode clicar em **Adicionar uma condição** para selecionar várias condições.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-198">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="7b2d9-199">Você pode escolher o operador **and** ou **or** entre condições.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-199">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="7b2d9-200">Você pode selecionar o item de **grupo de condição** na parte inferior da lista de condições para formar condições compostas complexas.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-200">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="7b2d9-201">Quando tiver terminado, clique no botão **consulta** .</span><span class="sxs-lookup"><span data-stu-id="7b2d9-201">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="7b2d9-202">Depois de criar um filtro básico ou avançado, você poderá salvá-lo usando **Salvar consulta** ou **Salvar consulta como**.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-202">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="7b2d9-203">Posteriormente, quando você retornar a exibições de campanhas, poderá carregar um filtro salvo clicando em **configurações de consulta salvas**.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-203">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="7b2d9-204">Para exportar o gráfico ou a lista de campanhas, clique em **Exportar** e selecione **exportar dados do gráfico** ou **Exportar lista de campanhas**.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-204">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="7b2d9-205">Se você tiver uma assinatura ATP do Microsoft defender, poderá clicar em **WDATP** para conectar ou desconectar as informações de campanhas com o Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-205">If you have a Microsoft Defender ATP subscription, you can click **WDATP** to connect or disconnect the campaigns information with Microsoft Defender ATP.</span></span> <span data-ttu-id="7b2d9-206">Para obter mais informações, consulte [integrar o Office 365 ATP com o Microsoft defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span><span class="sxs-lookup"><span data-stu-id="7b2d9-206">For more information, see [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="7b2d9-207">Detalhes da campanha</span><span class="sxs-lookup"><span data-stu-id="7b2d9-207">Campaign details</span></span>

<span data-ttu-id="7b2d9-208">Quando você clica no nome de uma campanha, os detalhes da campanha aparecem em um submenu.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-208">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="7b2d9-209">Informações de campanha</span><span class="sxs-lookup"><span data-stu-id="7b2d9-209">Campaign information</span></span>

<span data-ttu-id="7b2d9-210">Na parte superior do modo de exibição detalhes da campanha, as seguintes informações de campanha estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="7b2d9-210">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="7b2d9-211">**ID**: o identificador exclusivo da campanha.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-211">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="7b2d9-212">**Iniciado** e **finalizado**: a data de início e a data de término da campanha.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-212">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="7b2d9-213">Observe que essas datas podem ser estendidas além das datas de filtro selecionadas na página Visão geral.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-213">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="7b2d9-214">**Impacto**: Esta seção contém os seguintes dados para o filtro de intervalo de datas que você selecionou (ou que você selecionou na linha do tempo):</span><span class="sxs-lookup"><span data-stu-id="7b2d9-214">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  
  - <span data-ttu-id="7b2d9-215">O número total de destinatários.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-215">The total number of recipients.</span></span>
  - <span data-ttu-id="7b2d9-216">O número de mensagens que foram "caixa de entrada" (isto é, entregues na caixa de entrada, e não na pasta lixo eletrônico).</span><span class="sxs-lookup"><span data-stu-id="7b2d9-216">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="7b2d9-217">Quantos usuários clicaram na carga da URL na mensagem de phishing.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-217">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="7b2d9-218">Howe muitos usuários visitaram a URL.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-218">Howe many users visited the URL.</span></span>

- <span data-ttu-id="7b2d9-219">**Direcionado**: o percentual conforme calculado por: (o número de destinatários da campanha em sua organização)/(o número total de destinatários na campanha em todas as organizações no serviço).</span><span class="sxs-lookup"><span data-stu-id="7b2d9-219">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="7b2d9-220">Observe que esse valor é calculado sobre todo o tempo de vida da campanha e não altera as datas do filtro.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-220">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change the filter dates.</span></span>

- <span data-ttu-id="7b2d9-221">Uma linha do tempo interativa da atividade de campanha: a linha do tempo mostra a atividade durante todo o tempo de vida da campanha.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-221">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="7b2d9-222">Por padrão, a área sombreada inclui o filtro intervalo de datas que você selecionou na visão geral.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-222">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="7b2d9-223">Você pode clicar e arrastar para selecionar um ponto inicial e um ponto final específicos, <u>o que irá alterar os dados exibidos na área de **impacto** e no restante da página, conforme descrito nas próximas seções</u>.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-223">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="7b2d9-224">Na barra de título, você pode clicar no botão de **gravação da campanha de download** ![ baixar o ícone de gravação da campanha ](../../media/download-campaign-write-up-button.png) para baixar os detalhes da campanha em um documento do Word (por padrão, CampaignReport.docx).</span><span class="sxs-lookup"><span data-stu-id="7b2d9-224">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="7b2d9-225">Observe que este documento contém detalhes sobre todo o tempo de vida da campanha (não apenas as datas de filtro selecionadas).</span><span class="sxs-lookup"><span data-stu-id="7b2d9-225">Note that this document contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![Informações de campanha](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="7b2d9-227">Fluxo de campanha</span><span class="sxs-lookup"><span data-stu-id="7b2d9-227">Campaign flow</span></span>

<span data-ttu-id="7b2d9-228">No meio do modo de exibição detalhes da campanha, detalhes importantes sobre a campanha são apresentados na seção **fluxo** em um diagrama de fluxo horizontal (conhecido como diagrama do _Sankey_ ).</span><span class="sxs-lookup"><span data-stu-id="7b2d9-228">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="7b2d9-229">Esses detalhes ajudarão você a entender os elementos da campanha e o impacto potencial na sua organização.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-229">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="7b2d9-230">As informações exibidas no diagrama de **fluxo** são controladas pelo intervalo de datas sombreado na linha do tempo, conforme descrito na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-230">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![Detalhes da campanha que não contêm cliques de usuários na URL](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="7b2d9-232">Se passar o mouse sobre uma faixa horizontal no diagrama, você verá o número de mensagens relacionadas (por exemplo, mensagens de um determinado IP de origem, mensagens do IP de origem usando o domínio do remetente especificado, etc.).</span><span class="sxs-lookup"><span data-stu-id="7b2d9-232">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="7b2d9-233">O diagrama contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="7b2d9-233">The diagram contains the following information:</span></span>

- <span data-ttu-id="7b2d9-234">**IPs do remetente**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-234">**Sender IPs**</span></span>

- <span data-ttu-id="7b2d9-235">**Domínios do remetente**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-235">**Sender domains**</span></span>

- <span data-ttu-id="7b2d9-236">**Filter verdicts**: estes valores estão relacionados à verdicts de filtragem phishing e spam disponível, conforme descrito em [cabeçalhos de mensagem](anti-spam-message-headers.md)antispam.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-236">**Filter verdicts**: These values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="7b2d9-237">Os valores disponíveis são descritos na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="7b2d9-237">The available values are described in the following table:</span></span>

  ||||
  |---|---|---|
  |<span data-ttu-id="7b2d9-238">**Valor**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-238">**Value**</span></span>|<span data-ttu-id="7b2d9-239">**Veredicto de filtro de spam**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-239">**Spam filter verdict**</span></span>|<span data-ttu-id="7b2d9-240">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-240">**Description**</span></span>|
  |<span data-ttu-id="7b2d9-241">**Permitido**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-241">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="7b2d9-242">A mensagem foi marcada como não spam e/ou a filtragem ignorada antes de ser avaliada pela filtragem de spam (por exemplo, por uma regra de fluxo de emails, também conhecida como regra de transporte).</span><span class="sxs-lookup"><span data-stu-id="7b2d9-242">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="7b2d9-243">A mensagem ignorou a filtragem de spam por outros motivos (por exemplo, o remetente e o destinatário parecem estar na mesma organização).</span><span class="sxs-lookup"><span data-stu-id="7b2d9-243">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="7b2d9-244">**Blocked**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-244">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="7b2d9-245">A mensagem foi marcada como spam antes de ser avaliada pela filtragem de spam (por exemplo, por uma regra de fluxo de emails).</span><span class="sxs-lookup"><span data-stu-id="7b2d9-245">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="7b2d9-246">**Detectado**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-246">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="7b2d9-247">A mensagem foi marcada como spam pela filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-247">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="7b2d9-248">**Não detectado**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-248">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="7b2d9-249">A mensagem foi marcada como não spam por filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-249">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="7b2d9-250">**Solta**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-250">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="7b2d9-251">A mensagem ignorou a filtragem de spam porque foi liberada da quarentena.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-251">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="7b2d9-252">**Permissão de locatário**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7b2d9-252">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="7b2d9-253">A mensagem ignorou a filtragem de spam devido às configurações de política antispam (por exemplo, o remetente estava na lista de remetentes permitidos ou na lista de domínios permitidos).</span><span class="sxs-lookup"><span data-stu-id="7b2d9-253">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="7b2d9-254">**Bloco de locatário**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="7b2d9-254">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="7b2d9-255">A mensagem foi bloqueada por filtragem de spam devido às configurações de política antispam (por exemplo, o remetente estava na lista de remetentes permitidos ou na lista de domínios permitidos).</span><span class="sxs-lookup"><span data-stu-id="7b2d9-255">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="7b2d9-256">**Usuário permitir**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7b2d9-256">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="7b2d9-257">A mensagem ignorou a filtragem de spam porque o remetente estava na lista de remetentes confiáveis do usuário no Outlook.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-257">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="7b2d9-258">**Bloco de usuário**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="7b2d9-258">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="7b2d9-259">A mensagem foi bloqueada por filtragem de spam porque o remetente estava na lista de remetentes bloqueados de um usuário no Outlook.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-259">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="7b2d9-260">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-260">**ZAP**</span></span>|<span data-ttu-id="7b2d9-261">n/d</span><span class="sxs-lookup"><span data-stu-id="7b2d9-261">n/a</span></span>|<span data-ttu-id="7b2d9-262">A [limpeza automática de zero horas (zap)](zero-hour-auto-purge.md) levou à mensagem entregue de acordo com suas configurações de política antispam (movidas para a pasta lixo eletrônico ou colocada em quarentena).</span><span class="sxs-lookup"><span data-stu-id="7b2d9-262">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|
  |

  <span data-ttu-id="7b2d9-263"><sup>\*</sup>Revise suas políticas antispam, pois a mensagem permitida provavelmente teria sido bloqueada pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-263"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="7b2d9-264"><sup>\*\*</sup>Revise suas políticas antispam, pois essas mensagens devem ser colocadas em quarentena, não entregues.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-264"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="7b2d9-265">**Locais de entrega**: Você provavelmente desejará investigar as mensagens que foram realmente entregues aos destinatários (na pasta Caixa de Entrada ou Lixo Eletrônico), mesmo se os usuários não clicarem na URL do payload na mensagem.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-265">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="7b2d9-266">Você também pode remover as mensagens em quarentena da quarentena.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-266">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="7b2d9-267">Para obter mais informações, consulte [mensagens de email em quarentena no EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="7b2d9-267">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="7b2d9-268">**Pasta excluída**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-268">**Deleted folder**</span></span>
  - <span data-ttu-id="7b2d9-269">**Abandonado**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-269">**Dropped**</span></span>
  - <span data-ttu-id="7b2d9-270">**Externo**: o destinatário está localizado em sua organização de email local em ambientes híbridos.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-270">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="7b2d9-271">**Falhou**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-271">**Failed**</span></span>
  - <span data-ttu-id="7b2d9-272">**Encaminhadas**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-272">**Forwarded**</span></span>
  - <span data-ttu-id="7b2d9-273">**Caixa de Entrada**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-273">**Inbox**</span></span>
  - <span data-ttu-id="7b2d9-274">**Pasta Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-274">**Junk folder**</span></span>
  - <span data-ttu-id="7b2d9-275">**Quarentena**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-275">**Quarantine**</span></span>
  - <span data-ttu-id="7b2d9-276">**Unknown**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-276">**Unknown**</span></span>

- <span data-ttu-id="7b2d9-277">**Cliques de URL**: eles são descritos na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-277">**URL clicks**: These are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="7b2d9-278">Em todas as camadas que contêm mais de 10 itens, os dez principais itens são mostrados, enquanto o restante é agrupado em **outros**.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-278">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="7b2d9-279">Cliques na URL</span><span class="sxs-lookup"><span data-stu-id="7b2d9-279">URL clicks</span></span>

<span data-ttu-id="7b2d9-280">Quando uma mensagem de phishing é entregue a um destinatário (na caixa de entrada ou na pasta lixo eletrônico), há sempre a chance de que o usuário clique na URL de carga.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-280">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="7b2d9-281">Não clicar na URL em uma mensagem entregue é uma pequena medida do sucesso, mas você precisa determinar por que a mensagem de phishing foi entregue à caixa de correio em primeiro lugar.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-281">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="7b2d9-282">Se um usuário clicou na URL de carga na mensagem de phishing, as ações são exibidas na área de **cliques da URL** do diagrama no modo de exibição detalhes da campanha.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-282">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="7b2d9-283">**Permitido**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-283">**Allowed**</span></span>

- <span data-ttu-id="7b2d9-284">**BlockPage**: o destinatário clicou na URL de carga, mas seu acesso ao site mal-intencionado foi bloqueado pelas políticas de [links seguros de ATP](atp-safe-links.md) em sua organização.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-284">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="7b2d9-285">**BlockPageOverride**: o destinatário clicou na URL de carga da mensagem, os links seguros de ATP tentaram interrompê-los, mas eles tinham permissão para substituir o bloco.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-285">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="7b2d9-286">Você precisa investigar suas [políticas de links seguros](set-up-atp-safe-links-policies.md) para ver por que os usuários têm permissão para substituir os links de segurança veredicto e continuar no site mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-286">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="7b2d9-287">**PendingDetonationPage**: os anexos seguros de ATP estão no processo de abertura da URL de carga em um ambiente de computador virtual e ver o que acontece.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-287">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="7b2d9-288">**PendingDetonationPageOverride**: o destinatário tinha permissão para substituir o processo de acionamento de carga e abrir a URL sem aguardar os resultados.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-288">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="7b2d9-289">Guias</span><span class="sxs-lookup"><span data-stu-id="7b2d9-289">Tabs</span></span>

<span data-ttu-id="7b2d9-290">As guias no modo de exibição detalhes da campanha permitem investigar ainda mais a campanha.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-290">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="7b2d9-291">As informações exibidas nas guias são controladas pelo intervalo de datas sombreado na linha do tempo, conforme descrito na seção [informações da campanha](#campaign-information) .</span><span class="sxs-lookup"><span data-stu-id="7b2d9-291">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="7b2d9-292">**Cliques de URL**: se os usuários não clicar na URL de carga na mensagem de phishing, esta seção ficará em branco.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-292">**URL clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="7b2d9-293">Se um usuário conseguir clicar na URL, os seguintes valores serão preenchidos:</span><span class="sxs-lookup"><span data-stu-id="7b2d9-293">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="7b2d9-294">**Usuário**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7b2d9-294">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="7b2d9-295">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7b2d9-295">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="7b2d9-296">**Horário de clique**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-296">**Click time**</span></span>
  - <span data-ttu-id="7b2d9-297">**Clique em veredicto**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-297">**Click verdict**</span></span>

- <span data-ttu-id="7b2d9-298">**IPs do remetente**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-298">**Sender IPs**</span></span>

  - <span data-ttu-id="7b2d9-299">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7b2d9-299">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="7b2d9-300">**Contagem total**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-300">**Total count**</span></span>
  - <span data-ttu-id="7b2d9-301">**Caixa de entrada**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-301">**Inboxed**</span></span>
  - <span data-ttu-id="7b2d9-302">**Não caixa de entrada**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-302">**Not Inboxed**</span></span>
  - <span data-ttu-id="7b2d9-303">**SPF aprovado**: o remetente foi autenticado pela [estrutura de política de remetente (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="7b2d9-303">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="7b2d9-304">Um remetente que não passa pela validação SPF indica que o remetente não está autenticado ou a mensagem está falsificando um remetente legítimo.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-304">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="7b2d9-305">**Remetentes**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-305">**Senders**</span></span>

  - <span data-ttu-id="7b2d9-306">**Remetente**: Este é o endereço do remetente real no comando mail SMTP from, que não é necessariamente o endereço de email que os usuários vêem em seus clientes de email.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-306">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="7b2d9-307">**Contagem total**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-307">**Total count**</span></span>
  - <span data-ttu-id="7b2d9-308">**Caixa de entrada**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-308">**Inboxed**</span></span>
  - <span data-ttu-id="7b2d9-309">**Não caixa de entrada**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-309">**Not Inboxed**</span></span>
  - <span data-ttu-id="7b2d9-310">**DKIM passado**: o remetente foi autenticado por [chaves de domínio identificadas por email (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span><span class="sxs-lookup"><span data-stu-id="7b2d9-310">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="7b2d9-311">Um remetente que não passa DKIM validação indica que o remetente não está autenticado ou a mensagem está falsificando um remetente legítimo.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-311">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="7b2d9-312">**DMARC passado**: o remetente foi autenticado por [autenticação de mensagens baseadas em domínio, relatórios e conformidade (DMARC)](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="7b2d9-312">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="7b2d9-313">Um remetente que não passa DMARC validação indica que o remetente não está autenticado ou a mensagem está falsificando um remetente legítimo.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-313">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="7b2d9-314">**Anexos**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-314">**Attachments**</span></span>

  - <span data-ttu-id="7b2d9-315">**Filename**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-315">**Filename**</span></span>
  - <span data-ttu-id="7b2d9-316">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-316">**SHA256**</span></span>
  - <span data-ttu-id="7b2d9-317">**Família de malware**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-317">**Malware family**</span></span>
  - <span data-ttu-id="7b2d9-318">**Contagem total**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-318">**Total count**</span></span>

- <span data-ttu-id="7b2d9-319">**URL**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-319">**URL**</span></span>

  - <span data-ttu-id="7b2d9-320">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7b2d9-320">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="7b2d9-321">**Contagem total**</span><span class="sxs-lookup"><span data-stu-id="7b2d9-321">**Total Count**</span></span>

<span data-ttu-id="7b2d9-322"><sup>\*</sup> Clicar nesse valor abre um novo submenu que contém mais detalhes sobre o item especificado (usuário, URL, etc.) na parte superior do modo de exibição de detalhes da campanha.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-322"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="7b2d9-323">Para retornar ao modo de exibição de detalhes da campanha, clique em **Concluído** no novo submenu.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-323">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="7b2d9-324">Botões</span><span class="sxs-lookup"><span data-stu-id="7b2d9-324">Buttons</span></span>

<span data-ttu-id="7b2d9-325">Os botões no modo de exibição de detalhes da campanha permitem usar os recursos do Explorador de Ameaças para investigar ainda mais a campanha.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-325">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="7b2d9-326">**Explorar campanhas**: abre uma nova guia de pesquisa do Explorador de Ameaças usando o valor **ID da campanha** como filtro de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-326">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="7b2d9-327">**Explorar mensagens de caixa de entrada**: abre uma nova guia de pesquisa do explorador de ameaças usando a **ID de campanha** e o **local de entrega: caixa de entrada** como o filtro de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-327">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
