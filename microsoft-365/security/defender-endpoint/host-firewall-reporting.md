---
title: Relatórios de firewall de host no Microsoft Defender para Ponto de Extremidade
description: Hospedar e exibir relatórios de firewall no Microsoft 365 de segurança.
keywords: windows defender, firewall
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 0289d6f920fd6ff35fd446f9c2b8c5516883a4d2
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809208"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="9870e-104">Relatórios de firewall de host no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="9870e-104">Host firewall reporting in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9870e-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="9870e-105">**Applies to:**</span></span>
- [<span data-ttu-id="9870e-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="9870e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9870e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9870e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="9870e-108">Se você for um administrador, agora poderá hospedar relatórios de firewall [no Microsoft 365 de segurança.](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="9870e-108">If you are an admin, you can now host firewall reporting to [Microsoft 365 security center](https://security.microsoft.com).</span></span> <span data-ttu-id="9870e-109">Esse recurso permite exibir relatórios de firewall Windows 10 e Windows Server 2019 de um local centralizado.</span><span class="sxs-lookup"><span data-stu-id="9870e-109">This feature enables you to view Windows 10 and Windows Server 2019 firewall reporting from a centralized location.</span></span> 

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9870e-110">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="9870e-110">What do you need to know before you begin?</span></span> 

- <span data-ttu-id="9870e-111">Você deve estar executando Windows 10 ou Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9870e-111">You must be running Windows 10 or Windows Server 2019.</span></span>
- <span data-ttu-id="9870e-112">Para integrar dispositivos para o serviço Microsoft Defender para Ponto de Extremidade, consulte [aqui](onboard-configure.md).</span><span class="sxs-lookup"><span data-stu-id="9870e-112">To onboard devices to the Microsoft Defender for Endpoint service, see [here](onboard-configure.md).</span></span> 
- <span data-ttu-id="9870e-113">Para Microsoft 365 central de segurança começar a receber  os dados, você deve habilitar eventos de auditoria para Windows Defender Firewall com Segurança Avançada:</span><span class="sxs-lookup"><span data-stu-id="9870e-113">For Microsoft 365 security center to start receiving the data, you must enable **Audit Events** for Windows Defender Firewall with Advanced Security:</span></span> 
    - [<span data-ttu-id="9870e-114">Audit Filtering Platform Packet Drop</span><span class="sxs-lookup"><span data-stu-id="9870e-114">Audit Filtering Platform Packet Drop</span></span>](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
    - [<span data-ttu-id="9870e-115">Conexão da Plataforma de Filtragem de Auditoria</span><span class="sxs-lookup"><span data-stu-id="9870e-115">Audit Filtering Platform Connection</span></span>](/windows/security/threat-protection/auditing/audit-filtering-platform-connection) 
- <span data-ttu-id="9870e-116">Habilita esses eventos usando o Editor de Objeto de Política de Grupo, a Política de Segurança Local ou auditpol.exe comandos.</span><span class="sxs-lookup"><span data-stu-id="9870e-116">Enable these events by using Group Policy Object Editor, Local Security Policy, or the auditpol.exe commands.</span></span> <span data-ttu-id="9870e-117">Para obter mais informações, consulte [aqui](/windows/win32/fwp/auditing-and-logging).</span><span class="sxs-lookup"><span data-stu-id="9870e-117">For more information, see [here](/windows/win32/fwp/auditing-and-logging).</span></span> 
    - <span data-ttu-id="9870e-118">Os dois comandos do PowerShell são:</span><span class="sxs-lookup"><span data-stu-id="9870e-118">The two PowerShell commands are:</span></span>
        - <span data-ttu-id="9870e-119">**auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable**</span><span class="sxs-lookup"><span data-stu-id="9870e-119">**auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable**</span></span> 
        - <span data-ttu-id="9870e-120">**auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable**</span><span class="sxs-lookup"><span data-stu-id="9870e-120">**auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable**</span></span> 

## <a name="the-process"></a><span data-ttu-id="9870e-121">O processo</span><span class="sxs-lookup"><span data-stu-id="9870e-121">The process</span></span>
> [!NOTE]
> <span data-ttu-id="9870e-122">Siga as instruções da seção acima e configure corretamente seus dispositivos para a participação inicial da visualização.</span><span class="sxs-lookup"><span data-stu-id="9870e-122">Make sure to follow the instructions from the section above and properly configure your devices for the early preview participation.</span></span>

- <span data-ttu-id="9870e-123">Depois de ativar os eventos, Microsoft 365 central de segurança começará a monitorar os dados.</span><span class="sxs-lookup"><span data-stu-id="9870e-123">After enabling the events, Microsoft 365 security center will start to monitor the data.</span></span>
    - <span data-ttu-id="9870e-124">IP remoto, porta remota, porta local, IP local, nome do computador, Processo entre conexões de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="9870e-124">Remote IP, Remote Port, Local Port, Local IP, Computer Name, Process across inbound and outbound connections.</span></span>
- <span data-ttu-id="9870e-125">Os administradores agora podem ver Windows de firewall de host [aqui](https://security.microsoft.com/firewall).</span><span class="sxs-lookup"><span data-stu-id="9870e-125">Admins can now see Windows host firewall activity [here](https://security.microsoft.com/firewall).</span></span>
    - <span data-ttu-id="9870e-126">Relatórios adicionais podem ser facilitados baixando o [script Relatório Personalizado](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) para monitorar as atividades Windows Defender Firewall usando Power BI.</span><span class="sxs-lookup"><span data-stu-id="9870e-126">Additional reporting can be facilitated by downloading the [Custom Reporting script](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) to monitor the Windows Defender Firewall activities using Power BI.</span></span> 
    - <span data-ttu-id="9870e-127">Pode levar até 12 horas antes que os dados se refletem.</span><span class="sxs-lookup"><span data-stu-id="9870e-127">It can take up to 12 hours before the data is reflected.</span></span>

## <a name="supported-scenarios"></a><span data-ttu-id="9870e-128">Cenários com suporte</span><span class="sxs-lookup"><span data-stu-id="9870e-128">Supported scenarios</span></span>
<span data-ttu-id="9870e-129">Os cenários a seguir são suportados durante o Ring0 Preview.</span><span class="sxs-lookup"><span data-stu-id="9870e-129">The following scenarios are supported during Ring0 Preview.</span></span> 

### <a name="firewall-reporting-in-security-center"></a><span data-ttu-id="9870e-130">Relatórios de firewall no centro de segurança</span><span class="sxs-lookup"><span data-stu-id="9870e-130">Firewall reporting in security center</span></span>

<span data-ttu-id="9870e-131">Aqui estão alguns exemplos das páginas de relatório de firewall.</span><span class="sxs-lookup"><span data-stu-id="9870e-131">Here is a couple of examples of the firewall report pages.</span></span> <span data-ttu-id="9870e-132">Aqui você encontrará um resumo da atividade de entrada, saída e aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9870e-132">Here you will find a summary of inbound, outbound, and application activity.</span></span> <span data-ttu-id="9870e-133">Você pode acessar essa página diretamente acessando https://security.microsoft.com/firewall .</span><span class="sxs-lookup"><span data-stu-id="9870e-133">You can access this page directly by going to https://security.microsoft.com/firewall.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9870e-134">![Página de relatório de firewall do host](\images\host-firewall-reporting-page.png)</span><span class="sxs-lookup"><span data-stu-id="9870e-134">![Host firewall reporting page](\images\host-firewall-reporting-page.png)</span></span>

<span data-ttu-id="9870e-135">Esses relatórios também podem ser acessados acessando a seção **Reports** Security Report Devices (seção) localizada na parte inferior do  >    >   **cartão Conexões de Entrada Bloqueadas do Firewall.**</span><span class="sxs-lookup"><span data-stu-id="9870e-135">These reports can also be accessed by going to **Reports** > **Security Report** > **Devices** (section) located at the bottom of the **Firewall Blocked Inbound Connections** card.</span></span>

### <a name="from-computers-with-a-blocked-connection-to-device"></a><span data-ttu-id="9870e-136">De "Computadores com uma conexão bloqueada" para o dispositivo</span><span class="sxs-lookup"><span data-stu-id="9870e-136">From "Computers with a blocked connection" to device</span></span>

<span data-ttu-id="9870e-137">Os cartões suportam objetos interativos.</span><span class="sxs-lookup"><span data-stu-id="9870e-137">Cards support interactive objects.</span></span> <span data-ttu-id="9870e-138">Você pode detalhar a atividade de um dispositivo clicando no nome do dispositivo, que será lançado em uma nova guia e o levará diretamente para a guia Linha https://securitycenter.microsoft.com **do Tempo do** Dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9870e-138">You can drill into the activity of a device by clicking on the device name, which will launch https://securitycenter.microsoft.com in a new tab, and take you directly to the **Device Timeline** tab.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9870e-139">![Computadores com uma conexão bloqueada](\images\firewall-reporting-blocked-connection.png)</span><span class="sxs-lookup"><span data-stu-id="9870e-139">![Computers with a blocked connection](\images\firewall-reporting-blocked-connection.png)</span></span>

<span data-ttu-id="9870e-140">Agora você pode selecionar a guia **Linha** do Tempo, que lhe dará uma lista de eventos associados a esse dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9870e-140">You can now select the **Timeline** tab, which will give you a list of events associated with that device.</span></span> 

<span data-ttu-id="9870e-141">Depois de clicar no botão **Filtros** no canto superior direito do painel de exibição, selecione o tipo de evento que deseja.</span><span class="sxs-lookup"><span data-stu-id="9870e-141">After clicking on the **Filters** button on the upper right-hand corner of the viewing pane, select the type of event you want.</span></span> <span data-ttu-id="9870e-142">Nesse caso, selecione **Eventos de Firewall** e o painel será filtrado para eventos de Firewall.</span><span class="sxs-lookup"><span data-stu-id="9870e-142">In this case, select **Firewall events** and the pane will be filtered to Firewall events.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9870e-143">![Botão Filtros](\images\firewall-reporting-filters-button.png)</span><span class="sxs-lookup"><span data-stu-id="9870e-143">![Filters button](\images\firewall-reporting-filters-button.png)</span></span>

### <a name="drill-into-advanced-hunting-preview-refresh"></a><span data-ttu-id="9870e-144">Drill into advanced hunting (preview refresh)</span><span class="sxs-lookup"><span data-stu-id="9870e-144">Drill into advanced hunting (preview refresh)</span></span>

<span data-ttu-id="9870e-145">Os relatórios de firewall suportam a furação do cartão diretamente na Busca **Avançada** clicando no **botão Abrir Busca** Avançada.</span><span class="sxs-lookup"><span data-stu-id="9870e-145">Firewall reports support drilling from the card directly into **Advanced Hunting** by clicking the **Open Advanced hunting** button.</span></span> <span data-ttu-id="9870e-146">A consulta será pré-preenchida.</span><span class="sxs-lookup"><span data-stu-id="9870e-146">The query will be pre-populated.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9870e-147">![Abrir botão de busca avançada](\images\firewall-reporting-advanced-hunting.png)</span><span class="sxs-lookup"><span data-stu-id="9870e-147">![Open Advanced hunting button](\images\firewall-reporting-advanced-hunting.png)</span></span>

<span data-ttu-id="9870e-148">A consulta agora pode ser executada e todos os eventos de Firewall relacionados dos últimos 30 dias podem ser explorados.</span><span class="sxs-lookup"><span data-stu-id="9870e-148">The query can now be executed, and all related Firewall events from the last 30 days can be explored.</span></span> 

<span data-ttu-id="9870e-149">Para relatórios adicionais ou alterações personalizadas, a consulta pode ser exportada para Power BI análise adicional.</span><span class="sxs-lookup"><span data-stu-id="9870e-149">For additional reporting, or custom changes, the query can be exported into Power BI for further analysis.</span></span> <span data-ttu-id="9870e-150">Relatórios personalizados podem ser facilitados baixando o [script Relatório Personalizado](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) para monitorar as atividades Windows Defender Firewall usando Power BI.</span><span class="sxs-lookup"><span data-stu-id="9870e-150">Custom reporting can be facilitated by downloading the [Custom Reporting script](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) to monitor the Windows Defender Firewall activities using Power BI.</span></span> 

 