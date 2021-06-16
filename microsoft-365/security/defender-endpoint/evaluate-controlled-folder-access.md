---
title: Avaliar o acesso controlado a pastas
description: Veja como o acesso controlado a pastas pode ajudar a proteger os arquivos de serem alterados por aplicativos mal-intencionados.
keywords: Exploit protection, windows 10, windows defender, ransomware, protect, evaluate, test, demo, try
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 4254c5ea24d8c901ac5f6337b0c626afe02747e2
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926638"
---
# <a name="evaluate-controlled-folder-access"></a><span data-ttu-id="998cf-104">Avaliar o acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="998cf-104">Evaluate controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="998cf-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="998cf-105">**Applies to:**</span></span>
- [<span data-ttu-id="998cf-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="998cf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="998cf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="998cf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="998cf-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="998cf-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="998cf-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="998cf-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="998cf-110">[O acesso controlado](controlled-folders.md) a pastas é um recurso que ajuda a proteger seus documentos e arquivos contra modificação por aplicativos suspeitos ou mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="998cf-110">[Controlled folder access](controlled-folders.md) is a feature that helps protect your documents and files from modification by suspicious or malicious apps.</span></span> <span data-ttu-id="998cf-111">O acesso controlado a pastas é suportado no Windows Server 2019 e Windows 10 clientes.</span><span class="sxs-lookup"><span data-stu-id="998cf-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span>

<span data-ttu-id="998cf-112">É especialmente útil ajudar a proteger contra [ransomware](https://www.microsoft.com/wdsi/threats/ransomware) que tenta criptografar seus arquivos e mantê-los como reféns.</span><span class="sxs-lookup"><span data-stu-id="998cf-112">It is especially useful in helping protect against [ransomware](https://www.microsoft.com/wdsi/threats/ransomware) that attempts to encrypt your files and hold them hostage.</span></span>

<span data-ttu-id="998cf-113">Este artigo ajuda você a avaliar o acesso controlado a pastas.</span><span class="sxs-lookup"><span data-stu-id="998cf-113">This article helps you evaluate controlled folder access.</span></span> <span data-ttu-id="998cf-114">Ele explica como habilitar o modo de auditoria para que você possa testar o recurso diretamente em sua organização.</span><span class="sxs-lookup"><span data-stu-id="998cf-114">It explains how to enable audit mode so you can test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="998cf-115">Você também pode visitar o site de [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) cenário de demonstração do Microsoft Defender para Ponto de Extremidade no demo.wd.microsoft.com para confirmar se o recurso está funcionando e ver como ele funciona.</span><span class="sxs-lookup"><span data-stu-id="998cf-115">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="998cf-116">Usar o modo de auditoria para medir o impacto</span><span class="sxs-lookup"><span data-stu-id="998cf-116">Use audit mode to measure impact</span></span>

<span data-ttu-id="998cf-117">Habilita o acesso controlado a pastas no modo de auditoria para ver um registro do que *teria* ocorrido se estivesse totalmente habilitado.</span><span class="sxs-lookup"><span data-stu-id="998cf-117">Enable the controlled folder access in audit mode to see a record of what *would* have happened if it was fully enabled.</span></span> <span data-ttu-id="998cf-118">Teste como o recurso funcionará em sua organização para garantir que ele não afeta seus aplicativos de linha de negócios.</span><span class="sxs-lookup"><span data-stu-id="998cf-118">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="998cf-119">Você também pode ter uma ideia de quantas tentativas suspeitas de modificação de arquivo geralmente ocorrem em um determinado período de tempo.</span><span class="sxs-lookup"><span data-stu-id="998cf-119">You can also get an idea of how many suspicious file modification attempts generally occur over a certain period of time.</span></span>

<span data-ttu-id="998cf-120">Para habilitar o modo de auditoria, use o seguinte cmdlet do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="998cf-120">To enable audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> <span data-ttu-id="998cf-121">Se você quiser auditar totalmente como o acesso controlado a pastas funcionará em sua organização, você precisará usar uma ferramenta de gerenciamento para implantar essa configuração em dispositivos em sua rede.</span><span class="sxs-lookup"><span data-stu-id="998cf-121">If you want to fully audit how controlled folder access will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>
<span data-ttu-id="998cf-122">Você também pode usar a Política de Grupo, o Intune, o gerenciamento de dispositivo móvel (MDM) ou o Microsoft Endpoint Manager para configurar e implantar a configuração, conforme descrito no tópico principal de acesso controlado a [pastas.](controlled-folders.md)</span><span class="sxs-lookup"><span data-stu-id="998cf-122">You can also use Group Policy, Intune, mobile device management (MDM), or Microsoft Endpoint Manager to configure and deploy the setting, as described in the main [controlled folder access topic](controlled-folders.md).</span></span>

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a><span data-ttu-id="998cf-123">Revisar eventos de acesso controlado a pastas Windows Visualizador de Eventos</span><span class="sxs-lookup"><span data-stu-id="998cf-123">Review controlled folder access events in Windows Event Viewer</span></span>

<span data-ttu-id="998cf-124">Os seguintes eventos de acesso controlado a pastas aparecem Windows Visualizador de Eventos na pasta Microsoft/Windows/Windows Defender/Operacional.</span><span class="sxs-lookup"><span data-stu-id="998cf-124">The following controlled folder access events appear in Windows Event Viewer under Microsoft/Windows/Windows Defender/Operational folder.</span></span>

<span data-ttu-id="998cf-125">ID de evento</span><span class="sxs-lookup"><span data-stu-id="998cf-125">Event ID</span></span> | <span data-ttu-id="998cf-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="998cf-126">Description</span></span>
-|-
 <span data-ttu-id="998cf-127">5007</span><span class="sxs-lookup"><span data-stu-id="998cf-127">5007</span></span> | <span data-ttu-id="998cf-128">Evento quando as configurações são alteradas</span><span class="sxs-lookup"><span data-stu-id="998cf-128">Event when settings are changed</span></span>
 <span data-ttu-id="998cf-129">1124</span><span class="sxs-lookup"><span data-stu-id="998cf-129">1124</span></span> | <span data-ttu-id="998cf-130">Evento de acesso controlado a pastas auditadas</span><span class="sxs-lookup"><span data-stu-id="998cf-130">Audited controlled folder access event</span></span>
 <span data-ttu-id="998cf-131">1123</span><span class="sxs-lookup"><span data-stu-id="998cf-131">1123</span></span> | <span data-ttu-id="998cf-132">Evento de acesso controlado de pasta bloqueado</span><span class="sxs-lookup"><span data-stu-id="998cf-132">Blocked controlled folder access event</span></span>

> [!TIP]
> <span data-ttu-id="998cf-133">Você pode configurar uma assinatura [Windows encaminhamento de eventos para](/windows/win32/wec/setting-up-a-source-initiated-subscription) coletar os logs centralmente.</span><span class="sxs-lookup"><span data-stu-id="998cf-133">You can configure a [Windows Event Forwarding subscription](/windows/win32/wec/setting-up-a-source-initiated-subscription) to collect the logs centrally.</span></span> 

## <a name="customize-protected-folders-and-apps"></a><span data-ttu-id="998cf-134">Personalizar pastas e aplicativos protegidos</span><span class="sxs-lookup"><span data-stu-id="998cf-134">Customize protected folders and apps</span></span>

<span data-ttu-id="998cf-135">Durante sua avaliação, você pode desejar adicionar à lista de pastas protegidas ou permitir que determinados aplicativos modifiquem arquivos.</span><span class="sxs-lookup"><span data-stu-id="998cf-135">During your evaluation, you may wish to add to the list of protected folders, or allow certain apps to modify files.</span></span>

<span data-ttu-id="998cf-136">Consulte [Proteger pastas importantes](controlled-folders.md) com acesso controlado a pastas para configurar o recurso com ferramentas de gerenciamento, incluindo A Política de Grupo, PowerShell e provedores de serviços de configuração de MDM (CSPs).</span><span class="sxs-lookup"><span data-stu-id="998cf-136">See [Protect important folders with controlled folder access](controlled-folders.md) for configuring the feature with management tools, including Group Policy, PowerShell, and MDM configuration service providers (CSPs).</span></span>

## <a name="see-also"></a><span data-ttu-id="998cf-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="998cf-137">See also</span></span>

* [<span data-ttu-id="998cf-138">Proteger pastas importantes com acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="998cf-138">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="998cf-139">Avaliar o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="998cf-139">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
* [<span data-ttu-id="998cf-140">Usar o modo de auditoria</span><span class="sxs-lookup"><span data-stu-id="998cf-140">Use audit mode</span></span>](audit-windows-defender.md)
