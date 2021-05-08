---
title: Avaliar as regras da redução da superfície de ataque
description: Veja como a redução de superfície de ataque bloquearia e impediria ataques com a ferramenta de demonstração personalizada.
keywords: Redução de superfície de ataque, quadris, sistema de prevenção contra invasões de host, regras de proteção, antiexploit, exploração, prevenção de infecção, avaliação, teste, demonstração
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: dansimp
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 73b23427ff401f2a37c399131d6aa01330ff9de5
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245295"
---
# <a name="evaluate-attack-surface-reduction-rules"></a><span data-ttu-id="61085-104">Avaliar as regras da redução da superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="61085-104">Evaluate attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="61085-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="61085-105">**Applies to:**</span></span>

- [<span data-ttu-id="61085-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="61085-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="61085-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61085-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="61085-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="61085-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="61085-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="61085-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="61085-110">As regras de redução de superfície de ataque ajudam a evitar ações normalmente usadas pelo malware para comprometer dispositivos ou redes.</span><span class="sxs-lookup"><span data-stu-id="61085-110">Attack surface reduction rules help prevent actions typically used by malware to compromise devices or networks.</span></span> <span data-ttu-id="61085-111">As regras de redução de superfície de ataque ajudam a fechar muitos dos pontos de entrada comuns usados por malware e ransomware.</span><span class="sxs-lookup"><span data-stu-id="61085-111">Attack surface reduction rules help close off many of the common entry points used by malware and ransomware.</span></span> 

<span data-ttu-id="61085-112">Definir regras de redução de superfície de ataque para dispositivos que executam qualquer uma das seguintes edições e versões de Windows:</span><span class="sxs-lookup"><span data-stu-id="61085-112">Set attack surface reduction rules for devices running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="61085-113">Windows 10 Pro, versão [1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) ou posterior</span><span class="sxs-lookup"><span data-stu-id="61085-113">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="61085-114">Windows 10 Enterprise, versão [1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) ou posterior</span><span class="sxs-lookup"><span data-stu-id="61085-114">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="61085-115">Windows Servidor, [versão 1803 (Canal Semesanuais)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) ou posterior</span><span class="sxs-lookup"><span data-stu-id="61085-115">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="61085-116">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="61085-116">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="61085-117">Saiba como avaliar as regras de redução de superfície de ataque habilitando o modo de auditoria para testar o recurso diretamente em sua organização.</span><span class="sxs-lookup"><span data-stu-id="61085-117">Learn how to evaluate attack surface reduction rules by enabling audit mode to test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="61085-118">Você também pode visitar o site de [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) cenário de demonstração do Microsoft Defender para Ponto de Extremidade no demo.wd.microsoft.com para confirmar se o recurso está funcionando e ver como ele funciona.</span><span class="sxs-lookup"><span data-stu-id="61085-118">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="61085-119">Usar o modo de auditoria para medir o impacto</span><span class="sxs-lookup"><span data-stu-id="61085-119">Use audit mode to measure impact</span></span>

<span data-ttu-id="61085-120">Habilita as regras de redução de superfície de ataque no modo de auditoria para exibir um registro de aplicativos que teriam sido bloqueados se o recurso estivesse totalmente habilitado.</span><span class="sxs-lookup"><span data-stu-id="61085-120">Enable attack surface reduction rules in audit mode to view a record of apps that would have been blocked if the feature was fully enabled.</span></span> <span data-ttu-id="61085-121">Teste como o recurso funcionará em sua organização para garantir que ele não afeta seus aplicativos de linha de negócios.</span><span class="sxs-lookup"><span data-stu-id="61085-121">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="61085-122">Você também pode ter uma ideia de com que frequência as regras serão a disparar durante o uso normal.</span><span class="sxs-lookup"><span data-stu-id="61085-122">You can also get an idea of how often the rules will fire during normal use.</span></span>

<span data-ttu-id="61085-123">Para habilitar uma regra de redução de superfície de ataque no modo de auditoria, use o seguinte cmdlet do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="61085-123">To enable an attack surface reduction rule in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

<span data-ttu-id="61085-124">Onde `<rule ID>` está um valor GUID da regra de [redução de superfície de ataque](attack-surface-reduction.md#attack-surface-reduction-rules).</span><span class="sxs-lookup"><span data-stu-id="61085-124">Where `<rule ID>` is a [GUID value of the attack surface reduction rule](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

<span data-ttu-id="61085-125">Para habilitar todas as regras de redução de superfície de ataque adicionadas no modo de auditoria, use o seguinte cmdlet do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="61085-125">To enable all the added attack surface reduction rules in audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> <span data-ttu-id="61085-126">Se você quiser auditar totalmente como as regras de redução de superfície de ataque funcionarão em sua organização, você precisará usar uma ferramenta de gerenciamento para implantar essa configuração em dispositivos em sua rede.</span><span class="sxs-lookup"><span data-stu-id="61085-126">If you want to fully audit how attack surface reduction rules will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>

<span data-ttu-id="61085-127">Você também pode usar a Política de Grupo, o Intune ou os provedores de serviços de configuração (CSPs) de gerenciamento de dispositivo móvel (CSPs) para configurar e implantar a configuração.</span><span class="sxs-lookup"><span data-stu-id="61085-127">You can also use Group Policy, Intune, or mobile device management (MDM) configuration service providers (CSPs) to configure and deploy the setting.</span></span> <span data-ttu-id="61085-128">Saiba mais no artigo principal [Regras de redução de superfície de](attack-surface-reduction.md) ataque.</span><span class="sxs-lookup"><span data-stu-id="61085-128">Learn more in the main [Attack surface reduction rules](attack-surface-reduction.md) article.</span></span>

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="61085-129">Revisar eventos de redução de superfície de ataque Windows Visualizador de Eventos</span><span class="sxs-lookup"><span data-stu-id="61085-129">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="61085-130">Para revisar aplicativos que teriam sido bloqueados, abra o Visualizador de Eventos e filtre a ID do Evento 1121 no log Microsoft-Windows-Windows Defender/Operacional.</span><span class="sxs-lookup"><span data-stu-id="61085-130">To review apps that would have been blocked, open Event Viewer and filter for Event ID 1121 in the Microsoft-Windows-Windows Defender/Operational log.</span></span> <span data-ttu-id="61085-131">A tabela a seguir lista todos os eventos de proteção de rede.</span><span class="sxs-lookup"><span data-stu-id="61085-131">The following table lists all network protection events.</span></span>

<span data-ttu-id="61085-132">ID de evento</span><span class="sxs-lookup"><span data-stu-id="61085-132">Event ID</span></span> | <span data-ttu-id="61085-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="61085-133">Description</span></span>
-|-
 <span data-ttu-id="61085-134">5007</span><span class="sxs-lookup"><span data-stu-id="61085-134">5007</span></span> | <span data-ttu-id="61085-135">Evento quando as configurações são alteradas</span><span class="sxs-lookup"><span data-stu-id="61085-135">Event when settings are changed</span></span>
 <span data-ttu-id="61085-136">1121</span><span class="sxs-lookup"><span data-stu-id="61085-136">1121</span></span> | <span data-ttu-id="61085-137">Evento quando uma regra de redução de superfície de ataque dispara no modo de bloqueio</span><span class="sxs-lookup"><span data-stu-id="61085-137">Event when an attack surface reduction rule fires in block mode</span></span>
 <span data-ttu-id="61085-138">1122</span><span class="sxs-lookup"><span data-stu-id="61085-138">1122</span></span> | <span data-ttu-id="61085-139">Evento quando uma regra de redução de superfície de ataque é ativas no modo de auditoria</span><span class="sxs-lookup"><span data-stu-id="61085-139">Event when an attack surface reduction rule fires in audit mode</span></span>

## <a name="customize-attack-surface-reduction-rules"></a><span data-ttu-id="61085-140">Personalizar regras da redução da superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="61085-140">Customize attack surface reduction rules</span></span>

<span data-ttu-id="61085-141">Durante sua avaliação, você pode querer configurar cada regra individualmente ou excluir determinados arquivos e processos de serem avaliados pelo recurso.</span><span class="sxs-lookup"><span data-stu-id="61085-141">During your evaluation, you may wish to configure each rule individually or exclude certain files and processes from being evaluated by the feature.</span></span>

<span data-ttu-id="61085-142">Consulte [Personalizar regras de redução de superfície de](customize-attack-surface-reduction.md) ataque para obter informações sobre como configurar o recurso com ferramentas de gerenciamento, incluindo políticas de Política de Grupo e CSP MDM.</span><span class="sxs-lookup"><span data-stu-id="61085-142">See [Customize attack surface reduction rules](customize-attack-surface-reduction.md) for information on configuring the feature with management tools, including Group Policy and MDM CSP policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="61085-143">Confira também</span><span class="sxs-lookup"><span data-stu-id="61085-143">See also</span></span>

* [<span data-ttu-id="61085-144">Reduzir superfícies de ataque com regras de redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="61085-144">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)
* [<span data-ttu-id="61085-145">Usar o modo de auditoria para avaliar Windows Defender</span><span class="sxs-lookup"><span data-stu-id="61085-145">Use audit mode to evaluate Windows Defender</span></span>](audit-windows-defender.md)
* [<span data-ttu-id="61085-146">Perguntas frequentes sobre a redução da superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="61085-146">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
