---
title: Especialistas em ameaças da Microsoft
ms.reviewer: ''
description: Os Especialistas em Ameaças da Microsoft fornece uma camada adicional de experiência para o Microsoft Defender para o Ponto de Extremidade.
keywords: serviço de busca de ameaças gerenciada, busca de ameaças gerenciadas, serviço de detecção e resposta gerenciada (MDR), MTE, Especialistas em Ameaças da Microsoft, MTE-TAN, notificação de ataque direcionado, Notificação de Ataque Direcionado
search.product: Windows 10
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4c61fcdfb452fb075498dcc2858bb7a9b4b81a2f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165940"
---
# <a name="microsoft-threat-experts"></a><span data-ttu-id="7c651-104">Especialistas em ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="7c651-104">Microsoft Threat Experts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7c651-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="7c651-105">**Applies to:**</span></span>
- [<span data-ttu-id="7c651-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="7c651-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="7c651-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7c651-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7c651-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="7c651-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7c651-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="7c651-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="7c651-110">Os Especialistas em Ameaças da Microsoft são um serviço gerenciado de busca de ameaças que fornece aos seus Centros de Operação de Segurança (SOCs) monitoramento e análise de nível especializado para ajudá-los a garantir que ameaças críticas em seus ambientes exclusivos não se esmaeçam.</span><span class="sxs-lookup"><span data-stu-id="7c651-110">Microsoft Threat Experts is a managed threat hunting service that provides your Security Operation Centers (SOCs) with expert level monitoring and analysis to help them ensure that critical threats in your unique environments don’t get missed.</span></span>
  
<span data-ttu-id="7c651-111">Esse serviço gerenciado de busca de ameaças fornece informações e dados orientados por especialistas por meio desses dois recursos: notificação de ataque direcionada e acesso a especialistas sob demanda.</span><span class="sxs-lookup"><span data-stu-id="7c651-111">This managed threat hunting service provides expert-driven insights and data through these two capabilities: targeted attack notification and access to experts on demand.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7c651-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="7c651-112">Before you begin</span></span> 
> [!NOTE]
> <span data-ttu-id="7c651-113">Discuta os requisitos de qualificação com seu provedor de serviços técnicos da Microsoft e a equipe de conta antes de aplicar ao serviço de busca de ameaças gerenciado.</span><span class="sxs-lookup"><span data-stu-id="7c651-113">Discuss the eligibility requirements with your Microsoft Technical Service provider and account team before you apply to the managed threat hunting service.</span></span>

<span data-ttu-id="7c651-114">Se você for um cliente do Microsoft Defender para Ponto de Extremidade, precisará aplicar-se aos Especialistas em Ameaças da Microsoft - Notificações de Ataque Direcionadas para obter informações e análises especiais que ajudam a identificar as ameaças mais **críticas** em seu ambiente para que você possa responder rapidamente a elas</span><span class="sxs-lookup"><span data-stu-id="7c651-114">If you're a Microsoft Defender for Endpoint customer, you need to apply for **Microsoft Threat Experts - Targeted Attack Notifications** to get special insights and analysis that help identify the most critical threats in your environment so you can respond to them quickly</span></span>

<span data-ttu-id="7c651-115">Para se inscrever nos Especialistas em Ameaças da Microsoft - Benefícios de Notificações de Ataques **Direcionados,** acesse Configurações Recursos avançados gerais Microsoft Threat Experts - Notificações de Ataque  >    >    >  **Direcionadas** a aplicar.</span><span class="sxs-lookup"><span data-stu-id="7c651-115">To enroll to Microsoft Threat Experts - Targeted Attack Notifications benefits, go to **Settings** > **General** > **Advanced features** > **Microsoft Threat Experts - Targeted Attack Notifications** to apply.</span></span> <span data-ttu-id="7c651-116">Uma vez aceito, você receberá os benefícios das Notificações de Ataque Direcionados.</span><span class="sxs-lookup"><span data-stu-id="7c651-116">Once accepted, you will get the benefits of Targeted Attack Notifications.</span></span>

<span data-ttu-id="7c651-117">Entre em contato com sua equipe de conta ou representante da Microsoft para se inscrever no **Microsoft Threat Experts -** Especialistas sob Demanda para consultar nossos especialistas em ameaças sobre detecções e adversários relevantes que sua organização está enfrentando.</span><span class="sxs-lookup"><span data-stu-id="7c651-117">Contact your account team or Microsoft representative to subscribe to **Microsoft Threat Experts - Experts on Demand** to consult with our threat experts on relevant detections and adversaries that your organization is facing.</span></span>

<span data-ttu-id="7c651-118">Confira [Configurar recursos de Especialistas em Ameaças da Microsoft](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#before-you-begin) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="7c651-118">See [Configure Microsoft Threat Experts capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#before-you-begin) for details.</span></span> 

## <a name="microsoft-threat-experts---targeted-attack-notification"></a><span data-ttu-id="7c651-119">Especialistas em ameaças da Microsoft - Notificação de ataque direcionada</span><span class="sxs-lookup"><span data-stu-id="7c651-119">Microsoft Threat Experts - Targeted attack notification</span></span> 
<span data-ttu-id="7c651-120">Especialistas em ameaças da Microsoft - A notificação de ataque direcionada fornece a busca proativa das ameaças mais importantes à sua rede, incluindo invasões de adversários humanos, ataques de teclado ou ataques avançados, como a ciber-espionagem.</span><span class="sxs-lookup"><span data-stu-id="7c651-120">Microsoft Threat Experts - Targeted attack notification provides proactive hunting for the most important threats to your network, including human adversary intrusions, hands-on-keyboard attacks, or advanced attacks like cyber-espionage.</span></span> <span data-ttu-id="7c651-121">Essas notificações são um novo alerta.</span><span class="sxs-lookup"><span data-stu-id="7c651-121">These notifications shows up as a new alert.</span></span> <span data-ttu-id="7c651-122">O serviço de busca gerenciada inclui:</span><span class="sxs-lookup"><span data-stu-id="7c651-122">The managed hunting service includes:</span></span>  
- <span data-ttu-id="7c651-123">Monitoramento e análise de ameaças, reduzindo o tempo de vida e o risco para os negócios</span><span class="sxs-lookup"><span data-stu-id="7c651-123">Threat monitoring and analysis, reducing dwell time and risk to the business</span></span> 
- <span data-ttu-id="7c651-124">Inteligência artificial treinado pelo caçador para descobrir e priorizar ataques conhecidos e desconhecidos</span><span class="sxs-lookup"><span data-stu-id="7c651-124">Hunter-trained artificial intelligence to discover and prioritize both known and unknown attacks</span></span>  
- <span data-ttu-id="7c651-125">Identificar os riscos mais importantes, ajudando os SOCs a maximizar o tempo e a energia</span><span class="sxs-lookup"><span data-stu-id="7c651-125">Identifying the most important risks, helping SOCs maximize time and energy</span></span> 
- <span data-ttu-id="7c651-126">Escopo de comprometimento e o máximo de contexto que pode ser entregue rapidamente para habilitar a resposta rápida do SOC.</span><span class="sxs-lookup"><span data-stu-id="7c651-126">Scope of compromise and as much context as can be quickly delivered to enable fast SOC response.</span></span> 
 
## <a name="microsoft-threat-experts---experts-on-demand"></a><span data-ttu-id="7c651-127">Especialistas em ameaças da Microsoft - Especialistas sob demanda</span><span class="sxs-lookup"><span data-stu-id="7c651-127">Microsoft Threat Experts - Experts on Demand</span></span>
<span data-ttu-id="7c651-128">Os clientes podem envolver nossos especialistas em segurança diretamente de dentro do Centro de Segurança do Microsoft Defender para uma resposta o tempo e a precisão.</span><span class="sxs-lookup"><span data-stu-id="7c651-128">Customers can engage our security experts directly from within Microsoft Defender Security Center for timely and accurate response.</span></span> <span data-ttu-id="7c651-129">Os especialistas fornecem informações necessárias para entender melhor as ameaças complexas que afetam sua organização, desde consultas de alerta, dispositivos potencialmente comprometidos, causa raiz de uma conexão de rede suspeita, até informações adicionais sobre ameaças em relação a campanhas avançadas de ameaças persistentes em andamento.</span><span class="sxs-lookup"><span data-stu-id="7c651-129">Experts provide insights needed to better understand the complex threats affecting your organization, from alert inquiries, potentially compromised devices, root cause of a suspicious network connection, to additional threat intelligence regarding ongoing advanced persistent threat campaigns.</span></span> <span data-ttu-id="7c651-130">Com essa funcionalidade, você pode:</span><span class="sxs-lookup"><span data-stu-id="7c651-130">With this capability, you can:</span></span>
- <span data-ttu-id="7c651-131">Obter esclarecimento adicional sobre alertas, incluindo a causa raiz ou o escopo do incidente</span><span class="sxs-lookup"><span data-stu-id="7c651-131">Get additional clarification on alerts including root cause or scope of the incident</span></span> 
- <span data-ttu-id="7c651-132">Obtenha clareza no comportamento do dispositivo suspeito e nas próximas etapas se enfrentar um invasor avançado</span><span class="sxs-lookup"><span data-stu-id="7c651-132">Gain clarity into suspicious device behavior and next steps if faced with an advanced attacker</span></span>  
- <span data-ttu-id="7c651-133">Determinar riscos e proteção em relação a atores de ameaças, campanhas ou técnicas de invasores emergentes</span><span class="sxs-lookup"><span data-stu-id="7c651-133">Determine risk and protection regarding threat actors, campaigns, or emerging attacker techniques</span></span> 

<span data-ttu-id="7c651-134">A opção de **consultar um especialista em ameaças** está disponível em vários locais no portal para que você possa se envolver com especialistas no contexto de sua investigação:</span><span class="sxs-lookup"><span data-stu-id="7c651-134">The option to **Consult a threat expert** is available in several places in the portal so you can engage with experts in the context of your investigation:</span></span>

- <span data-ttu-id="7c651-135"><i>**Menu ajuda e suporte**</i></span><span class="sxs-lookup"><span data-stu-id="7c651-135"><i>**Help and support menu**</i></span></span><BR>
<span data-ttu-id="7c651-136">![Captura de tela da opção de menu MTE-EOD](images/mte-eod-menu.png)</span><span class="sxs-lookup"><span data-stu-id="7c651-136">![Screenshot of MTE-EOD menu option](images/mte-eod-menu.png)</span></span>

- <span data-ttu-id="7c651-137"><i>**Menu ações da página do dispositivo**</i></span><span class="sxs-lookup"><span data-stu-id="7c651-137"><i>**Device page actions menu**</i></span></span><BR>
<span data-ttu-id="7c651-138">![Captura de tela da opção menu de ação de página do dispositivo MTE-EOD](images/mte-eod-machines.png)</span><span class="sxs-lookup"><span data-stu-id="7c651-138">![Screenshot of MTE-EOD device page action menu option](images/mte-eod-machines.png)</span></span>

- <span data-ttu-id="7c651-139"><i>**Menu Ações de página de alertas**</i></span><span class="sxs-lookup"><span data-stu-id="7c651-139"><i>**Alerts page actions menu**</i></span></span><BR>
<span data-ttu-id="7c651-140">![Captura de tela da opção menu de ação de página de alerta do MTE-EOD](images/mte-eod-alerts.png)</span><span class="sxs-lookup"><span data-stu-id="7c651-140">![Screenshot of MTE-EOD alert page action menu option](images/mte-eod-alerts.png)</span></span>

- <span data-ttu-id="7c651-141"><i>**Menu Ações de página de arquivo**</i></span><span class="sxs-lookup"><span data-stu-id="7c651-141"><i>**File page actions menu**</i></span></span><BR>
<span data-ttu-id="7c651-142">![Captura de tela da opção menu de ação de página de arquivo MTE-EOD](images/mte-eod-file.png)</span><span class="sxs-lookup"><span data-stu-id="7c651-142">![Screenshot of MTE-EOD file page action menu option](images/mte-eod-file.png)</span></span>

> [!NOTE]
> <span data-ttu-id="7c651-143">Se você quiser acompanhar o status de seus casos de Especialistas sob Demanda por meio do Microsoft Services Hub, entre em contato com seu Gerente de Conta Técnica.</span><span class="sxs-lookup"><span data-stu-id="7c651-143">If you would like to track the status of your Experts on Demand cases through Microsoft Services Hub, reach out to your Technical Account Manager.</span></span> 

<span data-ttu-id="7c651-144">Assista a este vídeo para uma visão geral rápida do Microsoft Services Hub.</span><span class="sxs-lookup"><span data-stu-id="7c651-144">Watch this video for a quick overview of the Microsoft Services Hub.</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f] 

   
## <a name="related-topic"></a><span data-ttu-id="7c651-145">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7c651-145">Related topic</span></span>
- [<span data-ttu-id="7c651-146">Configurar recursos de Especialistas em Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="7c651-146">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md)
