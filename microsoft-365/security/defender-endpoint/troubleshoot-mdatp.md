---
title: Solucionar problemas de serviço do Microsoft Defender para Pontos de Extremidade
description: Encontre soluções e soluções alternativas para problemas conhecidos, como erros de servidor ao tentar acessar o serviço.
keywords: solucionar problemas do Microsoft Defender para ponto de extremidade, solucionar problemas do Windows ATP, erro de servidor, acesso negado, credenciais inválidas, sem dados, portal do painel, permitir, visualizador de eventos
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 112f682836da37ddfb51c103282518ff74563727
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186012"
---
# <a name="troubleshoot-service-issues"></a><span data-ttu-id="234ac-104">Solucionar problemas de serviço</span><span class="sxs-lookup"><span data-stu-id="234ac-104">Troubleshoot service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="234ac-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="234ac-105">**Applies to:**</span></span>
- [<span data-ttu-id="234ac-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="234ac-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="234ac-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="234ac-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="234ac-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="234ac-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="234ac-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="234ac-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="234ac-110">Esta seção aborda problemas que podem surgir à medida que você usa o serviço de Ameaça Avançada do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="234ac-110">This section addresses issues that might arise as you use the Microsoft Defender Advanced Threat service.</span></span>

## <a name="server-error---access-is-denied-due-to-invalid-credentials"></a><span data-ttu-id="234ac-111">Erro do servidor - o acesso é negado devido a credenciais inválidas</span><span class="sxs-lookup"><span data-stu-id="234ac-111">Server error - Access is denied due to invalid credentials</span></span>
<span data-ttu-id="234ac-112">Se você encontrar um erro de servidor ao tentar acessar o serviço, precisará alterar as configurações de cookie do navegador.</span><span class="sxs-lookup"><span data-stu-id="234ac-112">If you encounter a server error when trying to access the service, you’ll need to change your browser cookie settings.</span></span>
<span data-ttu-id="234ac-113">Configure seu navegador para permitir cookies.</span><span class="sxs-lookup"><span data-stu-id="234ac-113">Configure your browser to allow cookies.</span></span>

## <a name="elements-or-data-missing-on-the-portal"></a><span data-ttu-id="234ac-114">Elementos ou dados ausentes no portal</span><span class="sxs-lookup"><span data-stu-id="234ac-114">Elements or data missing on the portal</span></span>
<span data-ttu-id="234ac-115">Se alguns elementos ou dados estão faltando no Centro de Segurança do Microsoft Defender, é possível que as configurações de proxy o bloqueem.</span><span class="sxs-lookup"><span data-stu-id="234ac-115">If some elements or data is missing on Microsoft Defender Security Center it’s possible that proxy settings are blocking it.</span></span>

<span data-ttu-id="234ac-116">Certifique-se de `*.securitycenter.windows.com` que está incluída a lista de autorizações de proxy.</span><span class="sxs-lookup"><span data-stu-id="234ac-116">Make sure that `*.securitycenter.windows.com` is included the proxy allowlist.</span></span>


> [!NOTE]
> <span data-ttu-id="234ac-117">Você deve usar o protocolo HTTPS ao adicionar os seguintes pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="234ac-117">You must use the HTTPS protocol when adding the following endpoints.</span></span>

## <a name="microsoft-defender-for-endpoint-service-shows-event-or-error-logs-in-the-event-viewer"></a><span data-ttu-id="234ac-118">O serviço do Microsoft Defender para Ponto de Extremidade mostra logs de evento ou erro no Visualizador de Eventos</span><span class="sxs-lookup"><span data-stu-id="234ac-118">Microsoft Defender for Endpoint service shows event or error logs in the Event Viewer</span></span>

<span data-ttu-id="234ac-119">Consulte [Review events and errors using Event Viewer](event-error-codes.md) for a list of event IDs that are reported by the Microsoft Defender for Endpoint service.</span><span class="sxs-lookup"><span data-stu-id="234ac-119">See [Review events and errors using Event Viewer](event-error-codes.md) for a list of event IDs that are reported by the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="234ac-120">O artigo também contém etapas de solução de problemas para erros de evento.</span><span class="sxs-lookup"><span data-stu-id="234ac-120">The article also contains troubleshooting steps for event errors.</span></span>

## <a name="microsoft-defender-for-endpoint-service-fails-to-start-after-a-reboot-and-shows-error-577"></a><span data-ttu-id="234ac-121">O serviço do Microsoft Defender para Ponto de Extremidade falha ao iniciar após uma reinicialização e mostra o erro 577</span><span class="sxs-lookup"><span data-stu-id="234ac-121">Microsoft Defender for Endpoint service fails to start after a reboot and shows error 577</span></span>

<span data-ttu-id="234ac-122">Se a integração de dispositivos for concluída com êxito, mas o Microsoft Defender for Endpoint não iniciar após uma reinicialização e mostrar o erro 577, verifique se o Windows Defender não está desabilitado por uma política.</span><span class="sxs-lookup"><span data-stu-id="234ac-122">If onboarding devices successfully completes but Microsoft Defender for Endpoint does not start after a reboot and shows error 577, check that Windows Defender is not disabled by a policy.</span></span>

<span data-ttu-id="234ac-123">Para obter mais informações, consulte [Ensure that Microsoft Defender Antivírus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span><span class="sxs-lookup"><span data-stu-id="234ac-123">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>

## <a name="known-issues-with-regional-formats"></a><span data-ttu-id="234ac-124">Problemas conhecidos com formatos regionais</span><span class="sxs-lookup"><span data-stu-id="234ac-124">Known issues with regional formats</span></span>

<span data-ttu-id="234ac-125">**Formatos de data e hora**</span><span class="sxs-lookup"><span data-stu-id="234ac-125">**Date and time formats**</span></span><br>
<span data-ttu-id="234ac-126">Há alguns problemas conhecidos com os formatos de data e hora.</span><span class="sxs-lookup"><span data-stu-id="234ac-126">There are some known issues with the time and date formats.</span></span> 

<span data-ttu-id="234ac-127">Os seguintes formatos de data são suportados:</span><span class="sxs-lookup"><span data-stu-id="234ac-127">The following date formats are supported:</span></span>
- <span data-ttu-id="234ac-128">MM/dd/yyyy</span><span class="sxs-lookup"><span data-stu-id="234ac-128">MM/dd/yyyy</span></span>
- <span data-ttu-id="234ac-129">dd/MM/yyyy</span><span class="sxs-lookup"><span data-stu-id="234ac-129">dd/MM/yyyy</span></span>

<span data-ttu-id="234ac-130">No momento, não há suporte para os seguintes formatos de data e hora:</span><span class="sxs-lookup"><span data-stu-id="234ac-130">The following date and time formats are currently not supported:</span></span>
- <span data-ttu-id="234ac-131">Formato de data yyyy/MM/dd</span><span class="sxs-lookup"><span data-stu-id="234ac-131">Date format yyyy/MM/dd</span></span>
- <span data-ttu-id="234ac-132">Formato de data dd/MM/yy</span><span class="sxs-lookup"><span data-stu-id="234ac-132">Date format dd/MM/yy</span></span>
- <span data-ttu-id="234ac-133">Formato de data com yy.</span><span class="sxs-lookup"><span data-stu-id="234ac-133">Date format with yy.</span></span> <span data-ttu-id="234ac-134">Mostrará somente yyyy.</span><span class="sxs-lookup"><span data-stu-id="234ac-134">Will only show yyyy.</span></span>
- <span data-ttu-id="234ac-135">O formato de hora HH:mm:ss não tem suporte (não há suporte para o formato AM/PM de 12 horas).</span><span class="sxs-lookup"><span data-stu-id="234ac-135">Time format HH:mm:ss is not supported (the 12 hour AM/PM format is not supported).</span></span> <span data-ttu-id="234ac-136">Há suporte apenas para o formato de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="234ac-136">Only the 24-hour format is supported.</span></span>

<span data-ttu-id="234ac-137">**Uso de vírgulas para indicar mil**</span><span class="sxs-lookup"><span data-stu-id="234ac-137">**Use of comma to indicate thousand**</span></span><br>
<span data-ttu-id="234ac-138">Não há suporte para o uso de vírgulas como separador em números.</span><span class="sxs-lookup"><span data-stu-id="234ac-138">Support of use of comma as a separator in numbers are not supported.</span></span> <span data-ttu-id="234ac-139">Regiões onde um número é separado com uma vírgula para indicar mil, só verão o uso de um ponto como separador.</span><span class="sxs-lookup"><span data-stu-id="234ac-139">Regions where a number is separated with a comma to indicate a thousand, will only see the use of a dot as a separator.</span></span> <span data-ttu-id="234ac-140">Por exemplo, 15,5K é exibido como 15,5K.</span><span class="sxs-lookup"><span data-stu-id="234ac-140">For example, 15,5K is displayed as 15.5K.</span></span>

><span data-ttu-id="234ac-141">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="234ac-141">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="234ac-142">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="234ac-142">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshoot-belowfoldlink)

## <a name="microsoft-defender-for-endpoint-tenant-was-automatically-created-in-europe"></a><span data-ttu-id="234ac-143">O locatário do Microsoft Defender para Ponto de Extremidade foi criado automaticamente na Europa</span><span class="sxs-lookup"><span data-stu-id="234ac-143">Microsoft Defender for Endpoint tenant was automatically created in Europe</span></span>
<span data-ttu-id="234ac-144">Quando você usa o Centro de Segurança do Azure para monitorar servidores, um locatário do Microsoft Defender para Ponto de Extremidade é criado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="234ac-144">When you use Azure Security Center to monitor servers, a Microsoft Defender for Endpoint tenant is automatically created.</span></span> <span data-ttu-id="234ac-145">Os dados do Microsoft Defender para Ponto de Extremidade são armazenados na Europa por padrão.</span><span class="sxs-lookup"><span data-stu-id="234ac-145">The Microsoft Defender for Endpoint data is stored in Europe by default.</span></span>





## <a name="related-topics"></a><span data-ttu-id="234ac-146">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="234ac-146">Related topics</span></span>
- [<span data-ttu-id="234ac-147">Solucionar problemas de integração do Microsoft Defender para pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="234ac-147">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
- [<span data-ttu-id="234ac-148">Revisar eventos e erros usando o Visualizador de Eventos</span><span class="sxs-lookup"><span data-stu-id="234ac-148">Review events and errors using Event Viewer</span></span>](event-error-codes.md)