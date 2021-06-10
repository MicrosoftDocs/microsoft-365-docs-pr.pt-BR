---
title: Relatar e solucionar problemas do Microsoft Defender para Regras ASR do Ponto de Extremidade
description: Este tópico descreve como relatar e solucionar problemas do Microsoft Defender for Endpoint ASR Rules
keywords: Regras de redução de superfície de ataque, asr, quadris, sistema de prevenção contra invasões de host, regras de proteção, antiexploit, exploração, prevenção de infecção, microsoft defender para ponto de extremidade
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c043e97d6c02e4f41d000e9ce8cfea4a0950252a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245979"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-atp-asr-rules"></a><span data-ttu-id="1b9b7-104">Relatar e solucionar problemas do Microsoft Defender para regras ASR atp</span><span class="sxs-lookup"><span data-stu-id="1b9b7-104">Report and troubleshoot Microsoft Defender for ATP ASR Rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1b9b7-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="1b9b7-105">**Applies to:**</span></span>

- [<span data-ttu-id="1b9b7-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="1b9b7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="1b9b7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1b9b7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="1b9b7-108">O Microsoft 365 de segurança é a nova interface para monitorar e gerenciar a segurança em suas identidades, dados, dispositivos, aplicativos e infraestrutura da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-108">The Microsoft 365 security center is the new interface for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span> <span data-ttu-id="1b9b7-109">Aqui você pode exibir facilmente a integridade de segurança da sua organização, configurar dispositivos, usuários e aplicativos e exibir alertas para atividades suspeitas.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-109">Here you can easily view the security health of your organization, act to configure devices, users, and apps, and get alerts for suspicious activity.</span></span> <span data-ttu-id="1b9b7-110">O centro de segurança do Microsoft 365 destina-se a administradores e equipes de operações de segurança para gerenciar e proteger melhor sua organização.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-110">The Microsoft 365 security center is intended for security admins and security operations teams to better manage and protect their organization.</span></span> <span data-ttu-id="1b9b7-111">Visite o Microsoft 365 de segurança em https://security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="1b9b7-111">Visit the Microsoft 365 security center at https://security.microsoft.com.</span></span>
<span data-ttu-id="1b9b7-112">No Microsoft 365 de segurança, oferecemos uma olhada completa na configuração e eventos atuais das regras ASR em sua propriedade.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-112">In Microsoft 365 security center, we offer you a complete look at the current ASR rules configuration and events in your estate.</span></span> <span data-ttu-id="1b9b7-113">Observe que seus dispositivos devem estar conectados ao serviço Microsoft Defender for Endpoint para que esses relatórios sejam preenchidos.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-113">Note that your devices must be onboarded into the Microsoft Defender for Endpoint service for these reports to be populated.</span></span>
<span data-ttu-id="1b9b7-114">Aqui está uma captura de tela do centro de segurança Microsoft 365 (em **Report**  >  **Devices Attack** surface  >  **reduction**).</span><span class="sxs-lookup"><span data-stu-id="1b9b7-114">Here's a screenshot from the Microsoft 365 security center (under **Reports** > **Devices** > **Attack surface reduction**).</span></span> <span data-ttu-id="1b9b7-115">No nível do dispositivo, selecione **Configuração** no painel Regras de redução de **superfície de** ataque.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-115">At the device level, select **Configuration** from the **Attack surface reduction rules** pane.</span></span> <span data-ttu-id="1b9b7-116">A tela a seguir é exibida, onde você pode selecionar um dispositivo específico e verificar sua configuração de regra ASR individual.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-116">The following screen is displayed, where you can select a specific device and check its individual ASR rule configuration.</span></span>

:::image type="content" source="images/asrrulesnew.png" alt-text="Tela de regras do ASR":::

## <a name="microsoft-defender-for-endpoint--advanced-hunting"></a><span data-ttu-id="1b9b7-118">Microsoft Defender para Ponto de Extremidade – Busca avançada</span><span class="sxs-lookup"><span data-stu-id="1b9b7-118">Microsoft Defender for Endpoint – Advanced hunting</span></span>

<span data-ttu-id="1b9b7-119">Um dos recursos mais avançados do Microsoft Defender para Ponto de Extremidade é a busca avançada.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-119">One of the most powerful features of Microsoft Defender for Endpoint is advanced hunting.</span></span> <span data-ttu-id="1b9b7-120">Se você não estiver familiarizado com a busca avançada, consulte [proativamente a busca de](advanced-hunting-overview.md)ameaças com a busca avançada.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-120">If you're unfamiliar with advanced hunting, refer [proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

<span data-ttu-id="1b9b7-121">A busca avançada é uma ferramenta de busca de ameaças baseada em consulta (Kusto Query Language) que permite explorar até 30 dias dos dados capturados (brutos), que a Detecção e Resposta do Ponto de Extremidade do MDE (EDR) coleta de todos os seus máquinas.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-121">Advanced hunting is a query-based (Kusto Query Language) threat-hunting tool that lets you explore up to 30 days of the captured (raw) data, that MDE Endpoint Detection and Response (EDR) collects from all your machines.</span></span> <span data-ttu-id="1b9b7-122">Por meio da busca avançada, você pode inspecionar proativamente eventos para localizar indicadores e entidades interessantes.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-122">Through advanced hunting, you can proactively inspect events to locate interesting indicators and entities.</span></span> <span data-ttu-id="1b9b7-123">O acesso flexível aos dados ajuda a busca não restrita por ameaças conhecidas e potenciais.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-123">The flexible access to data helps unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="1b9b7-124">Por meio da busca avançada, é possível extrair informações de regras ASR, criar relatórios e obter informações detalhadas sobre o contexto de uma determinada auditoria de regra ASR ou um evento de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-124">Through advanced hunting, it's possible to extract ASR rules information, create reports, and get in-depth information on the context of a given ASR rule audit or block event.</span></span>

<span data-ttu-id="1b9b7-125">Os eventos de regras ASR estão disponíveis para consulta na tabela DeviceEvents na seção de busca avançada do Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-125">ASR rules events are available to be queried from the DeviceEvents table in the advanced hunting section of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="1b9b7-126">Por exemplo, uma consulta simples como a abaixo pode relatar todos os eventos que têm regras ASR como fonte de dados, nos últimos 30 dias, e as resumirá pela contagem ActionType, que, nesse caso, será o nome de código real da regra ASR.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-126">For example, a simple query such as the one below can report all the events that have ASR rules as data source, for the last 30 days, and will summarize them by the ActionType count, that in this case it will be the actual codename of the ASR rule.</span></span>

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="Consulta de busca avançada":::

:::image type="content" source="images/adv-hunt-sc-2new.png" alt-text="tela de busca avançada":::

<span data-ttu-id="1b9b7-129">Com a busca avançada, você pode moldar as consultas ao seu gosto, para que você possa ver o que está acontecendo, independentemente de você querer identificar algo em uma máquina individual ou deseja extrair informações de todo o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-129">With advanced hunting you can shape the queries to your liking, so that you can see what is happening, regardless of whether you want to pinpoint something on an individual machine, or you want to extract insights from your entire environment.</span></span>

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a><span data-ttu-id="1b9b7-130">Linha do tempo do computador do Microsoft Defender para Endpoint</span><span class="sxs-lookup"><span data-stu-id="1b9b7-130">Microsoft Defender for Endpoint machine timeline</span></span>

<span data-ttu-id="1b9b7-131">Uma alternativa à busca avançada, mas com um escopo mais estreito, é a linha do tempo do computador do Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-131">An alternative to advanced hunting, but with a narrower scope, is the Microsoft Defender for Endpoint machine timeline.</span></span> <span data-ttu-id="1b9b7-132">Você pode exibir todos os eventos coletados de um dispositivo, nos últimos seis meses, no Central de Segurança do Microsoft Defender, indo para a lista Máquinas, selecione um determinado computador e clique na guia Linha do Tempo.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-132">You can view all the collected events of a device, for the past six months, in the Microsoft Defender Security Center, by going to the Machines list, select a given machine, and then click on the Timeline tab.</span></span>

<span data-ttu-id="1b9b7-133">A imagem abaixo é uma captura de tela da exibição Linha do Tempo desses eventos em um determinado ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-133">Pictured below is a screenshot of the Timeline view of these events on a given endpoint.</span></span>  <span data-ttu-id="1b9b7-134">Nesta exibição, você pode filtrar a lista de eventos com base em qualquer um dos Grupos de Eventos no painel direito.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-134">From this view, you can filter the events list based on any of the Event Groups along the right-side pane.</span></span> <span data-ttu-id="1b9b7-135">Você também pode habilitar ou desabilitar eventos Sinalizados e Detalhados durante a exibição de alertas e rolagem pela linha do tempo histórica.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-135">You can also enable or disable Flagged and Verbose events while viewing alerts and scrolling through the historical timeline.</span></span>

:::image type="content" source="images/mic-sec-def-timelinenew.png" alt-text="Linha do tempo do Centro de Segurança do Microsoft Defender":::

## <a name="how-to-troubleshoot-asr-rules"></a><span data-ttu-id="1b9b7-137">Como solucionar problemas de regras ASR?</span><span class="sxs-lookup"><span data-stu-id="1b9b7-137">How to troubleshoot ASR rules?</span></span>

<span data-ttu-id="1b9b7-138">A primeira e mais imediata maneira é verificar localmente, em um dispositivo Windows, quais regras ASR estão habilitadas (e sua configuração) usando os cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-138">The first and most immediate way is to check locally, on a Windows device, which ASR rules are enabled (and their configuration) is by using the PowerShell cmdlets.</span></span>

<span data-ttu-id="1b9b7-139">Aqui estão algumas outras fontes de informações que Windows, para solucionar o impacto e a operação das regras ASR.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-139">Here are a few other sources of information that Windows offers, to troubleshoot ASR rules’ impact and operation.</span></span>

### <a name="querying-which-rules-are-active"></a><span data-ttu-id="1b9b7-140">Consultando quais regras estão ativas</span><span class="sxs-lookup"><span data-stu-id="1b9b7-140">Querying which rules are active</span></span>
<span data-ttu-id="1b9b7-141">Uma das maneiras mais fáceis de determinar se as regras asR já estão habilitadas e, é por meio de um cmdlet do PowerShell, Get-MpPreference.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-141">One of the easiest ways to determine if ASR rules are already enabled—and, is through a PowerShell cmdlet, Get-MpPreference.</span></span>
<span data-ttu-id="1b9b7-142">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="1b9b7-142">Here's an example:</span></span>

:::image type="content" source="images/getmpreferencescriptnew.png" alt-text="obter script mppreference":::

<span data-ttu-id="1b9b7-144">Há várias regras ASR ativas, com ações configuradas diferentes.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-144">There are multiple ASR rules active, with different configured actions.</span></span>

<span data-ttu-id="1b9b7-145">Para expandir as informações acima sobre regras ASR, você pode usar as propriedades **AttackSurfaceReductionRules_Ids** e/ou **AttackSurfaceReductionRules_Actions**.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-145">To expand the above information on ASR rules, you can use the properties **AttackSurfaceReductionRules_Ids** and/or **AttackSurfaceReductionRules_Actions**.</span></span>

<span data-ttu-id="1b9b7-146">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="1b9b7-146">Example:</span></span>

<span data-ttu-id="1b9b7-147">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Ids*</span><span class="sxs-lookup"><span data-stu-id="1b9b7-147">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Ids*</span></span>

:::image type="content" source="images/getmpref-examplenew.png" alt-text="obter exemplo de mpreferência":::

<span data-ttu-id="1b9b7-149">O acima mostra todas as IDs para regras ASR que têm uma configuração diferente de 0 (Não Configurado).</span><span class="sxs-lookup"><span data-stu-id="1b9b7-149">The above shows all the IDs for ASR rules that have a setting different from 0 (Not Configured).</span></span>

<span data-ttu-id="1b9b7-150">A próxima etapa é listar as ações reais (Bloqueio ou Auditoria) com as que cada regra está configurada.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-150">The next step is then to list the actual actions (Block or Audit) that each rule is configured with.</span></span> 

<span data-ttu-id="1b9b7-151">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Actions*</span><span class="sxs-lookup"><span data-stu-id="1b9b7-151">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Actions*</span></span>

:::image type="content" source="images/getmpref-example2new.png" alt-text="obter exemplo de mppreference2":::

### <a name="querying-blocking-and-auditing-events"></a><span data-ttu-id="1b9b7-153">Eventos de bloqueio e auditoria de consulta</span><span class="sxs-lookup"><span data-stu-id="1b9b7-153">Querying blocking and auditing events</span></span>
<span data-ttu-id="1b9b7-154">Os eventos de regra ASR podem ser exibidos no log Windows Defender log.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-154">ASR rule events can be viewed within the Windows Defender log.</span></span>

<span data-ttu-id="1b9b7-155">Para acessá-lo, abra Windows Visualizador de Eventos e navegue até **Aplicativos** e Serviços Logs  >  **microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operacional**.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-155">To access it, open Windows Event Viewer, and browse to **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

:::image type="content" source="images/eventviewerscrnew.png" alt-text="scr do visualizador de eventos":::

## <a name="microsoft-defender-malware-protection-logs"></a><span data-ttu-id="1b9b7-157">Logs de Proteção contra Malware do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1b9b7-157">Microsoft Defender Malware Protection Logs</span></span>
<span data-ttu-id="1b9b7-158">Você também pode exibir eventos de regra por meio da Microsoft Defender Antivírus de linha de comando dedicada, chamada , que pode ser usada para gerenciar e configurar e automatizar tarefas, se `*mpcmdrun.exe*` necessário.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-158">You can also view rule events through the Microsoft Defender Antivirus dedicated command-line tool, called `*mpcmdrun.exe*`, that can be used to manage and configure, and automate tasks if needed.</span></span>

<span data-ttu-id="1b9b7-159">Você pode encontrar esse utilitário em *%ProgramFiles%\Windows Defender\MpCmdRun.exe*.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-159">You can find this utility in *%ProgramFiles%\Windows Defender\MpCmdRun.exe*.</span></span> <span data-ttu-id="1b9b7-160">Você deve executar a partir de um prompt de comando com privilégios elevados (ou seja, executar como Administrador).</span><span class="sxs-lookup"><span data-stu-id="1b9b7-160">You must run it from an elevated command prompt (that is, run as Admin).</span></span>

<span data-ttu-id="1b9b7-161">Para gerar as informações de suporte, digite *MpCmdRun.exe -getfiles*.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-161">To generate the support information, type *MpCmdRun.exe -getfiles*.</span></span> <span data-ttu-id="1b9b7-162">Após algum tempo, vários logs serão empacotados em um arquivo morto (MpSupportFiles.cab) e disponibilizados em *C:\ProgramData\Microsoft\Windows Defender\Support*.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-162">After a while, several logs will be packaged into an archive (MpSupportFiles.cab) and made available in *C:\ProgramData\Microsoft\Windows Defender\Support*.</span></span>

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="logs de proteção contra malware":::

<span data-ttu-id="1b9b7-164">Extraia esse arquivo morto e você terá muitos arquivos disponíveis para fins de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-164">Extract that archive and you'll have many files available for troubleshooting purposes.</span></span>

<span data-ttu-id="1b9b7-165">Os arquivos mais relevantes são os seguinte:</span><span class="sxs-lookup"><span data-stu-id="1b9b7-165">The most relevant files are as follows:</span></span>

- <span data-ttu-id="1b9b7-166">**MPOperationalEvents.txt** - Esse arquivo contém o mesmo nível de informações encontradas no Visualizador de Eventos Windows Defender log Operacional do Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-166">**MPOperationalEvents.txt** - This file contains same level of information found in Event Viewer for Windows Defender’s Operational log.</span></span>
- <span data-ttu-id="1b9b7-167">**MPRegistry.txt** – neste arquivo, você poderá analisar todas as configurações Windows Defender atuais, a partir do momento em que os logs de suporte foram capturados.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-167">**MPRegistry.txt** – In this file you will can analyze all the current Windows Defender configurations, from the moment the support logs were captured.</span></span>
- <span data-ttu-id="1b9b7-168">**MPLog.txt** – Esse log contém informações mais detalhadas sobre todas as ações/operações do Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-168">**MPLog.txt** – This log contains more verbose information about all the actions/operations of the Windows Defender.</span></span>
