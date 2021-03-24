---
title: Configurações do fuso horário do Centro de Segurança do Microsoft Defender
description: Use as informações contidas aqui para configurar as configurações do fuso horário do Centro de Segurança do Microsoft Defender e exibir informações de licença.
keywords: configurações, Microsoft Defender, inteligência contra ameaças de segurança cibernética, proteção avançada contra ameaças, fuso horário, utc, hora local, licença
search.product: eADQiWindows 10XVcnh
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 25f2fc979cd6ffe82ba16e1ab870c97cdf4fcfe9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053863"
---
# <a name="microsoft-defender-security-center-time-zone-settings"></a><span data-ttu-id="e89a0-104">Configurações do fuso horário do Centro de Segurança do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e89a0-104">Microsoft Defender Security Center time zone settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e89a0-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e89a0-105">**Applies to:**</span></span>
- [<span data-ttu-id="e89a0-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e89a0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="e89a0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e89a0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)




><span data-ttu-id="e89a0-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="e89a0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e89a0-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="e89a0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-settings-abovefoldlink)

<span data-ttu-id="e89a0-110">Use o **ícone de configurações** de fuso horário do menu fuso horário1 para configurar o fuso ![ horário e exibir informações de ](images/atp-time-zone.png) licença.</span><span class="sxs-lookup"><span data-stu-id="e89a0-110">Use the **Time zone** menu ![Time zone settings icon1](images/atp-time-zone.png) to configure the time zone and view license information.</span></span>

## <a name="time-zone-settings"></a><span data-ttu-id="e89a0-111">Configurações de fuso horário</span><span class="sxs-lookup"><span data-stu-id="e89a0-111">Time zone settings</span></span>
<span data-ttu-id="e89a0-112">O aspecto do tempo é importante na avaliação e análise de ataques cibernéticos percebidos e reais.</span><span class="sxs-lookup"><span data-stu-id="e89a0-112">The aspect of time is important in the assessment and analysis of perceived and actual cyberattacks.</span></span>

<span data-ttu-id="e89a0-113">As investigações cibernéticas geralmente dependem de carimbos de data/hora para reunir a sequência de eventos.</span><span class="sxs-lookup"><span data-stu-id="e89a0-113">Cyberforensic investigations often rely on time stamps to piece together the sequence of events.</span></span> <span data-ttu-id="e89a0-114">É importante que o sistema reflita as configurações corretas do fuso horário.</span><span class="sxs-lookup"><span data-stu-id="e89a0-114">It’s important that your system reflects the correct time zone settings.</span></span>

<span data-ttu-id="e89a0-115">O Microsoft Defender para Ponto de Extremidade pode exibir UTC (Tempo Universal Coordenado) ou hora local.</span><span class="sxs-lookup"><span data-stu-id="e89a0-115">Microsoft Defender for Endpoint can display either Coordinated Universal Time (UTC) or local time.</span></span>

<span data-ttu-id="e89a0-116">A configuração atual do fuso horário é mostrada no menu Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="e89a0-116">Your current time zone setting is shown in the Microsoft Defender for Endpoint menu.</span></span> <span data-ttu-id="e89a0-117">Você pode alterar o fuso horário exibido no menu **Fuso Horário.**</span><span class="sxs-lookup"><span data-stu-id="e89a0-117">You can change the displayed time zone in the **Time zone** menu.</span></span>

![Ícone de configurações de fuso horário2](images/atp-time-zone-menu.png)<span data-ttu-id="e89a0-119">.</span><span class="sxs-lookup"><span data-stu-id="e89a0-119">.</span></span>

### <a name="utc-time-zone"></a><span data-ttu-id="e89a0-120">Fuso horário UTC</span><span class="sxs-lookup"><span data-stu-id="e89a0-120">UTC time zone</span></span>
<span data-ttu-id="e89a0-121">O Microsoft Defender para Ponto de Extremidade usa o tempo UTC por padrão.</span><span class="sxs-lookup"><span data-stu-id="e89a0-121">Microsoft Defender for Endpoint uses UTC time by default.</span></span>

<span data-ttu-id="e89a0-122">Definir o fuso horário do Microsoft Defender para Ponto de Extremidade como UTC exibirá todos os data/hora do sistema (alertas, eventos e outros) em UTC para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="e89a0-122">Setting the Microsoft Defender for Endpoint time zone to UTC will display all system timestamps (alerts, events, and others) in UTC for all users.</span></span> <span data-ttu-id="e89a0-123">Isso pode ajudar os analistas de segurança que trabalham em locais diferentes em todo o mundo a usar os mesmos carimbos de data/hora durante a investigação de eventos.</span><span class="sxs-lookup"><span data-stu-id="e89a0-123">This can help security analysts working in different locations across the globe to use the same time stamps while investigating events.</span></span>

### <a name="local-time-zone"></a><span data-ttu-id="e89a0-124">Fuso horário local</span><span class="sxs-lookup"><span data-stu-id="e89a0-124">Local time zone</span></span>
<span data-ttu-id="e89a0-125">Você pode optar por fazer com que o Microsoft Defender para Ponto de Extremidade use as configurações de fuso horário local.</span><span class="sxs-lookup"><span data-stu-id="e89a0-125">You can choose to have Microsoft Defender for Endpoint use local time zone settings.</span></span> <span data-ttu-id="e89a0-126">Todos os alertas e eventos serão exibidos usando o fuso horário local.</span><span class="sxs-lookup"><span data-stu-id="e89a0-126">All alerts and events will be displayed using your local time zone.</span></span>

<span data-ttu-id="e89a0-127">O fuso horário local é retirado das configurações regionais do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e89a0-127">The local time zone is taken from your device’s regional settings.</span></span> <span data-ttu-id="e89a0-128">Se você alterar suas configurações regionais, o fuso horário do Microsoft Defender para Ponto de Extremidade também mudará.</span><span class="sxs-lookup"><span data-stu-id="e89a0-128">If you change your regional settings, the Microsoft Defender for Endpoint time zone will also change.</span></span> <span data-ttu-id="e89a0-129">Escolher essa configuração significa que os dados de data/hora exibidos no Microsoft Defender para Ponto de Extremidade serão alinhados à hora local para todos os usuários do Microsoft Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="e89a0-129">Choosing this setting means that the timestamps displayed in Microsoft Defender for Endpoint will be aligned to local time for all Microsoft Defender for Endpoint users.</span></span> <span data-ttu-id="e89a0-130">Os analistas localizados em locais globais diferentes agora verão os alertas do Microsoft Defender para Ponto de Extremidade de acordo com suas configurações regionais.</span><span class="sxs-lookup"><span data-stu-id="e89a0-130">Analysts located in different global locations will now see the Microsoft Defender for Endpoint alerts according to their regional settings.</span></span>

<span data-ttu-id="e89a0-131">Escolher usar o horário local pode ser útil se os analistas estão localizados em um único local.</span><span class="sxs-lookup"><span data-stu-id="e89a0-131">Choosing to use local time can be useful if the analysts are located in a single location.</span></span> <span data-ttu-id="e89a0-132">Nesse caso, pode ser mais fácil correlacionar eventos com a hora local, por exemplo, quando um usuário local clicou em um link de email suspeito.</span><span class="sxs-lookup"><span data-stu-id="e89a0-132">In this case it might be easier to correlate events to local time, for example – when a local user clicked on a suspicious email link.</span></span>

### <a name="set-the-time-zone"></a><span data-ttu-id="e89a0-133">Definir o fuso horário</span><span class="sxs-lookup"><span data-stu-id="e89a0-133">Set the time zone</span></span>
<span data-ttu-id="e89a0-134">O fuso horário do Microsoft Defender para Ponto de Extremidade é definido por padrão como UTC.</span><span class="sxs-lookup"><span data-stu-id="e89a0-134">The Microsoft Defender for Endpoint time zone is set by default to UTC.</span></span>
<span data-ttu-id="e89a0-135">A configuração do fuso horário também altera os horários de todos os exibições do Microsoft Defender para Pontos de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="e89a0-135">Setting the time zone also changes the times for all Microsoft Defender for Endpoint views.</span></span>
<span data-ttu-id="e89a0-136">Para definir o fuso horário:</span><span class="sxs-lookup"><span data-stu-id="e89a0-136">To set the time zone:</span></span>

1. <span data-ttu-id="e89a0-137">Clique no **ícone de configurações** de fuso horário do menu Fuso ![ Horário3 ](images/atp-time-zone.png) .</span><span class="sxs-lookup"><span data-stu-id="e89a0-137">Click the **Time zone** menu ![Time zone settings icon3](images/atp-time-zone.png).</span></span>
2. <span data-ttu-id="e89a0-138">Selecione o **indicador UTC de zona de** tempo.</span><span class="sxs-lookup"><span data-stu-id="e89a0-138">Select the **Timezone UTC** indicator.</span></span>
3. <span data-ttu-id="e89a0-139">Selecione **UTC de fuso** horário ou seu fuso horário local, por exemplo -7:00.</span><span class="sxs-lookup"><span data-stu-id="e89a0-139">Select **Timezone UTC** or your local time zone, for example -7:00.</span></span>

### <a name="regional-settings"></a><span data-ttu-id="e89a0-140">Configurações regionais</span><span class="sxs-lookup"><span data-stu-id="e89a0-140">Regional settings</span></span>
<span data-ttu-id="e89a0-141">Para aplicar diferentes formatos de data para o Microsoft Defender para o Ponto de Extremidade, use configurações regionais para o Internet Explorer (IE) e o Microsoft Edge (Edge).</span><span class="sxs-lookup"><span data-stu-id="e89a0-141">To apply different date formats for Microsoft Defender for Endpoint, use regional settings for Internet Explorer (IE) and Microsoft Edge (Edge).</span></span> <span data-ttu-id="e89a0-142">Se você estiver usando outro navegador, como o Google Chrome, siga as etapas necessárias para alterar as configurações de data e hora desse navegador.</span><span class="sxs-lookup"><span data-stu-id="e89a0-142">If you're using another browser such as Google Chrome, follow the required steps to change the time and date settings for that browser.</span></span> 


<span data-ttu-id="e89a0-143">**Internet Explorer (IE) e Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="e89a0-143">**Internet Explorer (IE) and Microsoft Edge**</span></span>

<span data-ttu-id="e89a0-144">O IE e o Microsoft Edge usam **as** configurações Região configuradas na opção **Relógios,** Idioma e Região no painel controle.</span><span class="sxs-lookup"><span data-stu-id="e89a0-144">IE and Microsoft Edge use the **Region** settings configured in the **Clocks, Language, and Region** option in the Control panel.</span></span> 


#### <a name="known-issues-with-regional-formats"></a><span data-ttu-id="e89a0-145">Problemas conhecidos com formatos regionais</span><span class="sxs-lookup"><span data-stu-id="e89a0-145">Known issues with regional formats</span></span>

<span data-ttu-id="e89a0-146">**Formatos de data e hora**</span><span class="sxs-lookup"><span data-stu-id="e89a0-146">**Date and time formats**</span></span><br>
<span data-ttu-id="e89a0-147">Há alguns problemas conhecidos com os formatos de data e hora.</span><span class="sxs-lookup"><span data-stu-id="e89a0-147">There are some known issues with the time and date formats.</span></span> <span data-ttu-id="e89a0-148">Se você configurar suas configurações regionais para algo diferente dos formatos com suporte, o portal pode não refletir corretamente suas configurações.</span><span class="sxs-lookup"><span data-stu-id="e89a0-148">If you configure your regional settings to anything other than the supported formats, the portal may not correctly reflect your settings.</span></span>

<span data-ttu-id="e89a0-149">Os seguintes formatos de data e hora são suportados:</span><span class="sxs-lookup"><span data-stu-id="e89a0-149">The following date and time formats are supported:</span></span>
- <span data-ttu-id="e89a0-150">Formato de data MM/dd/yyyy</span><span class="sxs-lookup"><span data-stu-id="e89a0-150">Date format MM/dd/yyyy</span></span>
- <span data-ttu-id="e89a0-151">Formato de data dd/MM/yyyy</span><span class="sxs-lookup"><span data-stu-id="e89a0-151">Date format dd/MM/yyyy</span></span>
- <span data-ttu-id="e89a0-152">Formato de hora hh:mm:ss (formato de 12 horas)</span><span class="sxs-lookup"><span data-stu-id="e89a0-152">Time format hh:mm:ss (12 hour format)</span></span>

<span data-ttu-id="e89a0-153">No momento, não há suporte para os seguintes formatos de data e hora:</span><span class="sxs-lookup"><span data-stu-id="e89a0-153">The following date and time formats are currently not supported:</span></span>
- <span data-ttu-id="e89a0-154">Formato de data yyyy-MM-dd</span><span class="sxs-lookup"><span data-stu-id="e89a0-154">Date format yyyy-MM-dd</span></span>
- <span data-ttu-id="e89a0-155">Formato de data dd-MMM-yy</span><span class="sxs-lookup"><span data-stu-id="e89a0-155">Date format dd-MMM-yy</span></span>
- <span data-ttu-id="e89a0-156">Formato de data dd/MM/yy</span><span class="sxs-lookup"><span data-stu-id="e89a0-156">Date format dd/MM/yy</span></span>
- <span data-ttu-id="e89a0-157">Formato de data MM/dd/yy</span><span class="sxs-lookup"><span data-stu-id="e89a0-157">Date format MM/dd/yy</span></span>
- <span data-ttu-id="e89a0-158">Formato de data com yy.</span><span class="sxs-lookup"><span data-stu-id="e89a0-158">Date format with yy.</span></span> <span data-ttu-id="e89a0-159">Mostrará somente yyyy.</span><span class="sxs-lookup"><span data-stu-id="e89a0-159">Will only show yyyy.</span></span>
- <span data-ttu-id="e89a0-160">Formato de hora HH:mm:ss (formato de 24 horas)</span><span class="sxs-lookup"><span data-stu-id="e89a0-160">Time format HH:mm:ss (24 hour format)</span></span>

<span data-ttu-id="e89a0-161">**Símbolo decimal usado em números**</span><span class="sxs-lookup"><span data-stu-id="e89a0-161">**Decimal symbol used in numbers**</span></span><br>
<span data-ttu-id="e89a0-162">O símbolo decimal usado é sempre um ponto, mesmo que uma vírgula seja selecionada nas configurações de formato **Números** nas configurações **da** região.</span><span class="sxs-lookup"><span data-stu-id="e89a0-162">Decimal symbol used is always a dot, even if a comma is selected in  the **Numbers** format settings in **Region** settings.</span></span> <span data-ttu-id="e89a0-163">Por exemplo, 15,5K é exibido como 15,5K.</span><span class="sxs-lookup"><span data-stu-id="e89a0-163">For example, 15,5K is displayed as 15.5K.</span></span>


