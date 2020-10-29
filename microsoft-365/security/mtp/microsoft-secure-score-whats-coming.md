---
title: O que está chegando à pontuação segura da Microsoft
description: Descreve quais novas alterações estão chegando à pontuação segura da Microsoft na central de segurança do Microsoft 365.
keywords: Pontuação segura da Microsoft, Pontuação segura, Pontuação segura do Office 365, pontuação de segurança da Microsoft, centro de segurança da Microsoft 365, ações de melhoria
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 82ec67cae86525c055b2232667cccb603830d15f
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779243"
---
# <a name="whats-coming-to-microsoft-secure-score"></a><span data-ttu-id="f5cf2-104">O que está chegando à pontuação segura da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f5cf2-104">What's coming to Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f5cf2-105">Estamos fazendo algumas alterações em um futuro próximo para tornar a [Pontuação segura da Microsoft](microsoft-secure-score.md) um representante melhor da sua postura de segurança e melhorar a usabilidade.</span><span class="sxs-lookup"><span data-stu-id="f5cf2-105">We're making some changes in the near future to make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability.</span></span> <span data-ttu-id="f5cf2-106">Sua pontuação e a pontuação máxima possível podem ser alteradas.</span><span class="sxs-lookup"><span data-stu-id="f5cf2-106">Your score and the maximum possible score may change.</span></span>

## <a name="proposed-changes"></a><span data-ttu-id="f5cf2-107">Alterações propostas</span><span class="sxs-lookup"><span data-stu-id="f5cf2-107">Proposed changes</span></span>

### <a name="november-2020"></a><span data-ttu-id="f5cf2-108">Novembro de 2020</span><span class="sxs-lookup"><span data-stu-id="f5cf2-108">November 2020</span></span>

<span data-ttu-id="f5cf2-109">Removendo a capacidade de criar tíquetes do ServiceNow por meio de Pontuação segura, acessando **> ServiceNow** .</span><span class="sxs-lookup"><span data-stu-id="f5cf2-109">Removing the ability to create ServiceNow tickets through Secure Score by going to **Share > ServiceNow** .</span></span>

- <span data-ttu-id="f5cf2-110">O período de visualização do conector do ServiceNow está terminando.</span><span class="sxs-lookup"><span data-stu-id="f5cf2-110">The preview period for the ServiceNow connector is ending.</span></span> <span data-ttu-id="f5cf2-111">Esse recurso não estará mais disponível até o final de 2020.</span><span class="sxs-lookup"><span data-stu-id="f5cf2-111">This capability will no longer available by the end of 2020.</span></span> <span data-ttu-id="f5cf2-112">Obrigado por seus comentários e suporte contínuo enquanto determinamos as próximas etapas.</span><span class="sxs-lookup"><span data-stu-id="f5cf2-112">Thank you for your feedback and continued support while we determine next steps.</span></span>

<span data-ttu-id="f5cf2-113">Adicionando 18 ações aprimoradas relacionadas ao Microsoft defender para ponto de extremidade (anteriormente Microsoft defender ATP):</span><span class="sxs-lookup"><span data-stu-id="f5cf2-113">Adding 18 improvement actions related to Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

<span data-ttu-id="f5cf2-114">Recomendações relacionadas à redução da superfície de ataque (ASR):</span><span class="sxs-lookup"><span data-stu-id="f5cf2-114">Attack Surface Reduction (ASR) related recommendations:</span></span>
- <span data-ttu-id="f5cf2-115">Bloquear conteúdo executável de cliente de email e webmail</span><span class="sxs-lookup"><span data-stu-id="f5cf2-115">Block executable content from email client and webmail</span></span>
- <span data-ttu-id="f5cf2-116">Bloquear todos os aplicativos do Office para criar processos filhos</span><span class="sxs-lookup"><span data-stu-id="f5cf2-116">Block all Office applications from creating child processes</span></span>
- <span data-ttu-id="f5cf2-117">Impedir que aplicativos do Office criem conteúdo executável</span><span class="sxs-lookup"><span data-stu-id="f5cf2-117">Block Office applications from creating executable content</span></span>
- <span data-ttu-id="f5cf2-118">Bloquear aplicativos do Office de injetar código em outros processos</span><span class="sxs-lookup"><span data-stu-id="f5cf2-118">Block Office applications from injecting code into other processes</span></span>
- <span data-ttu-id="f5cf2-119">Bloquear JavaScript ou VBScript de iniciar conteúdo executável baixado</span><span class="sxs-lookup"><span data-stu-id="f5cf2-119">Block JavaScript or VBScript from launching downloaded executable content</span></span>
- <span data-ttu-id="f5cf2-120">Bloquear a execução de scripts potencialmente ofuscados</span><span class="sxs-lookup"><span data-stu-id="f5cf2-120">Block execution of potentially obfuscated scripts</span></span>
- <span data-ttu-id="f5cf2-121">Bloquear chamadas de API Win32 de macros do Office</span><span class="sxs-lookup"><span data-stu-id="f5cf2-121">Block Win32 API calls from Office macros</span></span>
- <span data-ttu-id="f5cf2-122">Bloquear a execução de arquivos executáveis, a menos que eles atendam a um critério de lista de predominância, idade ou confiável</span><span class="sxs-lookup"><span data-stu-id="f5cf2-122">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>
- <span data-ttu-id="f5cf2-123">Usar proteção avançada contra ransomware</span><span class="sxs-lookup"><span data-stu-id="f5cf2-123">Use advanced protection against ransomware</span></span>
- <span data-ttu-id="f5cf2-124">Bloquear o furto de credenciais do subsistema de autoridade de segurança local do Windows (lsass.exe)</span><span class="sxs-lookup"><span data-stu-id="f5cf2-124">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>
- <span data-ttu-id="f5cf2-125">Bloquear criações de processo provenientes de comandos do PSExec e WMI</span><span class="sxs-lookup"><span data-stu-id="f5cf2-125">Block process creations originating from PSExec and WMI commands</span></span>
- <span data-ttu-id="f5cf2-126">Bloquear processos não confiáveis e não assinados executados no USB</span><span class="sxs-lookup"><span data-stu-id="f5cf2-126">Block untrusted and unsigned processes that run from USB</span></span>
- <span data-ttu-id="f5cf2-127">Bloquear o aplicativo de comunicação do Office para criar processos filhos</span><span class="sxs-lookup"><span data-stu-id="f5cf2-127">Block Office communication application from creating child processes</span></span>
- <span data-ttu-id="f5cf2-128">Bloquear o Adobe Reader de criar processos filhos</span><span class="sxs-lookup"><span data-stu-id="f5cf2-128">Block Adobe Reader from creating child processes</span></span>
- <span data-ttu-id="f5cf2-129">Bloquear persistência por meio de assinatura de evento WMI</span><span class="sxs-lookup"><span data-stu-id="f5cf2-129">Block persistence through WMI event subscription</span></span>

<span data-ttu-id="f5cf2-130">Recomendações relacionadas a serviços:</span><span class="sxs-lookup"><span data-stu-id="f5cf2-130">Services related recommendations:</span></span>
- <span data-ttu-id="f5cf2-131">Corrigir o caminho de serviço sem cotação para os serviços do Windows</span><span class="sxs-lookup"><span data-stu-id="f5cf2-131">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="f5cf2-132">Alterar o caminho do executável do serviço para um local protegido comum</span><span class="sxs-lookup"><span data-stu-id="f5cf2-132">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="f5cf2-133">Alterar a conta de serviço para evitar a senha em cache no registro do Windows</span><span class="sxs-lookup"><span data-stu-id="f5cf2-133">Change service account to avoid cached password in windows registry</span></span>

## <a name="related-resources"></a><span data-ttu-id="f5cf2-134">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="f5cf2-134">Related resources</span></span>

- [<span data-ttu-id="f5cf2-135">Visão geral da Pontuação segura da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f5cf2-135">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="f5cf2-136">Avaliar sua postura de segurança</span><span class="sxs-lookup"><span data-stu-id="f5cf2-136">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="f5cf2-137">Acompanhar o histórico de Pontuação segura da Microsoft e atingir as metas</span><span class="sxs-lookup"><span data-stu-id="f5cf2-137">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="f5cf2-138">Novidades</span><span class="sxs-lookup"><span data-stu-id="f5cf2-138">What's new</span></span>](microsoft-secure-score-whats-new.md)
