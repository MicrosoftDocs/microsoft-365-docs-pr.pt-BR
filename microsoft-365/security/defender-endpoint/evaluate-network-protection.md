---
title: Avaliar a proteção de rede
description: Veja como a proteção de rede funciona testando cenários comuns contra os qual ela protege.
keywords: Proteção de rede, explorações, site mal-intencionado, ip, domínio, domínios, avaliar, testar, demonstração
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ade50e85dbfcf5f59921a65d5b97bb47d21e5b12
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570919"
---
# <a name="evaluate-network-protection"></a><span data-ttu-id="631a2-104">Avaliar a proteção de rede</span><span class="sxs-lookup"><span data-stu-id="631a2-104">Evaluate network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="631a2-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="631a2-105">**Applies to:**</span></span>
- [<span data-ttu-id="631a2-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="631a2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- - [<span data-ttu-id="631a2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="631a2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="631a2-108">[A proteção de](network-protection.md) rede ajuda a impedir que os funcionários usem qualquer aplicativo para acessar domínios perigosos que podem hospedar esquemas de phishing, explorações e outros conteúdos mal-intencionados na Internet.</span><span class="sxs-lookup"><span data-stu-id="631a2-108">[Network protection](network-protection.md) helps prevent employees from using any application to access dangerous domains that may host phishing scams, exploits, and other malicious content on the Internet.</span></span>

<span data-ttu-id="631a2-109">Este artigo ajuda você a avaliar a proteção de rede habilitando o recurso e orientando você para um site de teste.</span><span class="sxs-lookup"><span data-stu-id="631a2-109">This article helps you evaluate network protection by enabling the feature and guiding you to a testing site.</span></span> <span data-ttu-id="631a2-110">Os sites neste artigo de avaliação não são mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="631a2-110">The sites in this evaluation article aren't malicious.</span></span> <span data-ttu-id="631a2-111">Eles são sites criados especialmente que se parecem mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="631a2-111">They're specially created websites that pretend to be malicious.</span></span> <span data-ttu-id="631a2-112">O site replicará o comportamento que ocorreria se um usuário visitasse um site ou domínio mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="631a2-112">The site will replicate the behavior that would happen if a user visited a malicious site or domain.</span></span>

> [!TIP]
> <span data-ttu-id="631a2-113">Você também pode visitar o site do Microsoft Defender Testground [no](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) demo.wd.microsoft.com para ver como funcionam outros recursos de proteção.</span><span class="sxs-lookup"><span data-stu-id="631a2-113">You can also visit the Microsoft Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how other protection features work.</span></span>

## <a name="enable-network-protection-in-audit-mode"></a><span data-ttu-id="631a2-114">Habilitar a proteção de rede no modo de auditoria</span><span class="sxs-lookup"><span data-stu-id="631a2-114">Enable network protection in audit mode</span></span>

<span data-ttu-id="631a2-115">Habilita a proteção de rede no modo de auditoria para ver quais endereços IP e domínios teriam sido bloqueados.</span><span class="sxs-lookup"><span data-stu-id="631a2-115">Enable network protection in audit mode to see which IP addresses and domains would have been blocked.</span></span> <span data-ttu-id="631a2-116">Você pode garantir que ele não afete aplicativos de linha de negócios ou ter uma ideia da frequência com que os bloqueios ocorrem.</span><span class="sxs-lookup"><span data-stu-id="631a2-116">You can make sure it doesn't affect line-of-business apps, or get an idea of how often blocks occur.</span></span>

1. <span data-ttu-id="631a2-117">Digite **o powershell** no menu Iniciar, clique com o botão direito do **mouse Windows PowerShell** e selecione Executar como **administrador**</span><span class="sxs-lookup"><span data-stu-id="631a2-117">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="631a2-118">Insira o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="631a2-118">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

### <a name="visit-a-fake-malicious-domain"></a><span data-ttu-id="631a2-119">Visite um domínio mal-intencionado (falso)</span><span class="sxs-lookup"><span data-stu-id="631a2-119">Visit a (fake) malicious domain</span></span>

1. <span data-ttu-id="631a2-120">Abra o Internet Explorer, o Google Chrome ou qualquer outro navegador de sua preferência.</span><span class="sxs-lookup"><span data-stu-id="631a2-120">Open Internet Explorer, Google Chrome, or any other browser of your choice.</span></span>

1. <span data-ttu-id="631a2-121">Acesse [https://smartscreentestratings2.net](https://smartscreentestratings2.net).</span><span class="sxs-lookup"><span data-stu-id="631a2-121">Go to [https://smartscreentestratings2.net](https://smartscreentestratings2.net).</span></span>

<span data-ttu-id="631a2-122">A conexão de rede será permitida e uma mensagem de teste será exibida.</span><span class="sxs-lookup"><span data-stu-id="631a2-122">The network connection will be allowed and a test message will be displayed.</span></span>

![Notificação de exemplo que diz Conexão bloqueada: seu administrador de Segurança do Windows <2> <8> bloquear essa conexão de rede.](/microsoft-365/security/defender-endpoint/images/np-notif)

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="631a2-125">Revisar eventos de proteção de rede Windows Visualizador de Eventos</span><span class="sxs-lookup"><span data-stu-id="631a2-125">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="631a2-126">Para revisar aplicativos que teriam sido bloqueados, abra o Visualizador de Eventos e filtre a ID do Evento 1125 no log Microsoft-Windows-Windows-Defender/Operational.</span><span class="sxs-lookup"><span data-stu-id="631a2-126">To review apps that would have been blocked, open Event Viewer and filter for Event ID 1125 in the Microsoft-Windows-Windows-Defender/Operational log.</span></span> <span data-ttu-id="631a2-127">A tabela a seguir lista todos os eventos de proteção de rede.</span><span class="sxs-lookup"><span data-stu-id="631a2-127">The following table lists all network protection events.</span></span>

| <span data-ttu-id="631a2-128">ID de evento</span><span class="sxs-lookup"><span data-stu-id="631a2-128">Event ID</span></span> | <span data-ttu-id="631a2-129">Fornecer/Fonte</span><span class="sxs-lookup"><span data-stu-id="631a2-129">Provide/Source</span></span> | <span data-ttu-id="631a2-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="631a2-130">Description</span></span> |
|-|-|-|
|<span data-ttu-id="631a2-131">5007</span><span class="sxs-lookup"><span data-stu-id="631a2-131">5007</span></span> | <span data-ttu-id="631a2-132">Windows Defender (Operacional)</span><span class="sxs-lookup"><span data-stu-id="631a2-132">Windows Defender (Operational)</span></span> | <span data-ttu-id="631a2-133">Evento quando as configurações são alteradas</span><span class="sxs-lookup"><span data-stu-id="631a2-133">Event when settings are changed</span></span> |
|<span data-ttu-id="631a2-134">1125</span><span class="sxs-lookup"><span data-stu-id="631a2-134">1125</span></span> | <span data-ttu-id="631a2-135">Windows Defender (Operacional)</span><span class="sxs-lookup"><span data-stu-id="631a2-135">Windows Defender (Operational)</span></span> | <span data-ttu-id="631a2-136">Evento quando uma conexão de rede é auditada</span><span class="sxs-lookup"><span data-stu-id="631a2-136">Event when a network connection is audited</span></span> |
|<span data-ttu-id="631a2-137">1126</span><span class="sxs-lookup"><span data-stu-id="631a2-137">1126</span></span> | <span data-ttu-id="631a2-138">Windows Defender (Operacional)</span><span class="sxs-lookup"><span data-stu-id="631a2-138">Windows Defender (Operational)</span></span> | <span data-ttu-id="631a2-139">Evento quando uma conexão de rede é bloqueada</span><span class="sxs-lookup"><span data-stu-id="631a2-139">Event when a network connection is blocked</span></span> |

## <a name="see-also"></a><span data-ttu-id="631a2-140">Confira também</span><span class="sxs-lookup"><span data-stu-id="631a2-140">See also</span></span>

* [<span data-ttu-id="631a2-141">Proteção de rede</span><span class="sxs-lookup"><span data-stu-id="631a2-141">Network protection</span></span>](network-protection.md)
* [<span data-ttu-id="631a2-142">Habilitar a proteção de rede</span><span class="sxs-lookup"><span data-stu-id="631a2-142">Enable network protection</span></span>](enable-network-protection.md)
* [<span data-ttu-id="631a2-143">Solucionar problemas de proteção de rede</span><span class="sxs-lookup"><span data-stu-id="631a2-143">Troubleshoot network protection</span></span>](troubleshoot-np.md)
