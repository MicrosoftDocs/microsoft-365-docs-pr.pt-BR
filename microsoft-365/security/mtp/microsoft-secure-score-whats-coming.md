---
title: O que está acontecendo na pontuação segura da Microsoft?
description: Descreve a pontuação segura da Microsoft na central de segurança do Microsoft 365, como os detalhes são calculados e quais administradores de segurança podem esperar.
keywords: segurança, malware, Microsoft 365, M365, Pontuação segura, central de segurança, ações de melhoria
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
ms.openlocfilehash: 48ff6d6f5cac0991895c40cae90ca31657cfedff
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844877"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="7566d-104">O que está acontecendo na pontuação segura da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="7566d-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="7566d-105">Para tornar a [Pontuação segura da Microsoft](microsoft-secure-score.md) um melhor representante da postura de segurança e melhorar a usabilidade, estamos fazendo algumas alterações em um futuro próximo.</span><span class="sxs-lookup"><span data-stu-id="7566d-105">To make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="7566d-106">Sua pontuação e a pontuação máxima possível mudarão.</span><span class="sxs-lookup"><span data-stu-id="7566d-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="7566d-107">No entanto, isso não implica uma alteração na postura de segurança.</span><span class="sxs-lookup"><span data-stu-id="7566d-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="7566d-108">Para saber mais sobre as alterações recentes, confira [o que há de novo na pontuação segura da Microsoft?](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="7566d-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="june-2020"></a><span data-ttu-id="7566d-109">Junho de 2020</span><span class="sxs-lookup"><span data-stu-id="7566d-109">June 2020</span></span>

### <a name="remove-improvement-action-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="7566d-110">Remover ação de melhoria para a proteção avançada contra ameaças do Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="7566d-110">Remove improvement action for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="7566d-111">Ativar as regras de redução da superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="7566d-111">Turn on Attack Surface Reduction rules</span></span>

### <a name="add-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="7566d-112">Adicionar ações de melhoria para a proteção avançada contra ameaças do Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="7566d-112">Add improvement actions for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="7566d-113">Bloquear o Adobe Reader de criar processos filhos</span><span class="sxs-lookup"><span data-stu-id="7566d-113">Block Adobe Reader from creating child processes</span></span>
* <span data-ttu-id="7566d-114">Usar proteção avançada contra ransomware</span><span class="sxs-lookup"><span data-stu-id="7566d-114">Use advanced protection against ransomware</span></span>
* <span data-ttu-id="7566d-115">Bloquear todos os aplicativos do Office para criar processos filhos</span><span class="sxs-lookup"><span data-stu-id="7566d-115">Block all Office applications from creating child processes</span></span>
* <span data-ttu-id="7566d-116">Impedir que aplicativos do Office criem conteúdo executável</span><span class="sxs-lookup"><span data-stu-id="7566d-116">Block Office applications from creating executable content</span></span>
* <span data-ttu-id="7566d-117">Bloquear JavaScript ou VBScript de iniciar conteúdo executável baixado</span><span class="sxs-lookup"><span data-stu-id="7566d-117">Block JavaScript or VBScript from launching downloaded executable content</span></span>
* <span data-ttu-id="7566d-118">Bloquear a execução de scripts potencialmente ofuscados</span><span class="sxs-lookup"><span data-stu-id="7566d-118">Block execution of potentially obfuscated scripts</span></span>
* <span data-ttu-id="7566d-119">Bloquear conteúdo executável de cliente de email e webmail</span><span class="sxs-lookup"><span data-stu-id="7566d-119">Block executable content from email client and webmail</span></span>
* <span data-ttu-id="7566d-120">Bloquear o aplicativo de comunicação do Office para criar processos filhos</span><span class="sxs-lookup"><span data-stu-id="7566d-120">Block Office communication application from creating child processes</span></span>
* <span data-ttu-id="7566d-121">Bloquear processos não confiáveis e não assinados executados no USB</span><span class="sxs-lookup"><span data-stu-id="7566d-121">Block untrusted and unsigned processes that run from USB</span></span>
* <span data-ttu-id="7566d-122">Bloquear persistência por meio de assinatura de evento WMI</span><span class="sxs-lookup"><span data-stu-id="7566d-122">Block persistence through WMI event subscription</span></span>
* <span data-ttu-id="7566d-123">Bloquear aplicativos do Office de injetar código em outros processos</span><span class="sxs-lookup"><span data-stu-id="7566d-123">Block Office applications from injecting code into other processes</span></span>
* <span data-ttu-id="7566d-124">Bloquear a execução de arquivos executáveis, a menos que eles atendam a um critério de lista de predominância, idade ou confiável</span><span class="sxs-lookup"><span data-stu-id="7566d-124">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>
* <span data-ttu-id="7566d-125">Bloquear criações de processo provenientes de comandos do PSExec e WMI</span><span class="sxs-lookup"><span data-stu-id="7566d-125">Block process creations originating from PSExec and WMI commands</span></span>
* <span data-ttu-id="7566d-126">Bloquear o furto de credenciais do subsistema de autoridade de segurança local do Windows (lsass.exe)</span><span class="sxs-lookup"><span data-stu-id="7566d-126">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>
* <span data-ttu-id="7566d-127">Bloquear chamadas de API Win32 de macros do Office</span><span class="sxs-lookup"><span data-stu-id="7566d-127">Block Win32 API calls from Office macros</span></span>
