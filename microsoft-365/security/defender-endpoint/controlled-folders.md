---
title: Proteger pastas importantes contra ransomware para não criptografar seus arquivos com acesso controlado a pastas
description: Arquivos em pastas padrão podem ser protegidos contra alterações por aplicativos mal-intencionados. Impedir que ransomware criptografe seus arquivos.
keywords: acesso controlado a pastas, windows 10, windows defender, ransomware, protect, files, folders
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
audience: ITPro
ms.date: 02/03/2021
ms.reviewer: v-maave
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: b937dd41f0296f2cf4102f41f8ab10bd55e1c35d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51200276"
---
# <a name="protect-important-folders-with-controlled-folder-access"></a><span data-ttu-id="c36e2-105">Proteger pastas importantes com acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="c36e2-105">Protect important folders with controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c36e2-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c36e2-106">**Applies to:**</span></span>
- [<span data-ttu-id="c36e2-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c36e2-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c36e2-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c36e2-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="c36e2-109">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="c36e2-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c36e2-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="c36e2-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-controlled-folder-access"></a><span data-ttu-id="c36e2-111">O que é acesso controlado a pastas?</span><span class="sxs-lookup"><span data-stu-id="c36e2-111">What is controlled folder access?</span></span>

<span data-ttu-id="c36e2-112">O acesso controlado a pastas ajuda a proteger seus dados valiosos contra aplicativos mal-intencionados e ameaças, como ransomware.</span><span class="sxs-lookup"><span data-stu-id="c36e2-112">Controlled folder access helps protect your valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="c36e2-113">O acesso controlado a pastas protege seus dados verificando aplicativos em uma lista de aplicativos conhecidos e confiáveis.</span><span class="sxs-lookup"><span data-stu-id="c36e2-113">Controlled folder access protects your data by checking apps against a list of known, trusted apps.</span></span> <span data-ttu-id="c36e2-114">Com suporte nos clientes do Windows Server 2019 e do Windows 10, o acesso controlado a pastas pode ser ligado usando o Aplicativo de Segurança do Windows, o Microsoft Endpoint Configuration Manager ou o Intune (para dispositivos gerenciados).</span><span class="sxs-lookup"><span data-stu-id="c36e2-114">Supported on Windows Server 2019 and Windows 10 clients, controlled folder access can be turned on using the Windows Security App, Microsoft Endpoint Configuration Manager, or Intune (for managed devices).</span></span> 

> [!NOTE]
> <span data-ttu-id="c36e2-115">Os mecanismos de script não são confiáveis e você não pode permitir que eles acessem pastas protegidas controladas.</span><span class="sxs-lookup"><span data-stu-id="c36e2-115">Scripting engines are not trusted and you cannot allow them access to controlled protected folders.</span></span>  <span data-ttu-id="c36e2-116">Por exemplo, o PowerShell não é confiável por acesso controlado a pastas, mesmo que você permita com indicadores [de certificado e arquivo.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates)</span><span class="sxs-lookup"><span data-stu-id="c36e2-116">For example, PowerShell is not trusted by controlled folder access, even if you allow with [certificate and file indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates).</span></span> 

<span data-ttu-id="c36e2-117">O acesso controlado a pastas funciona melhor com o [Microsoft Defender para Ponto](microsoft-defender-endpoint.md)de Extremidade , que fornece relatórios detalhados sobre eventos e blocos de acesso controlado a pastas como parte dos cenários de investigação de [alertas usuais.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="c36e2-117">Controlled folder access works best with [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), which gives you detailed reporting into controlled folder access events and blocks as part of the usual [alert investigation scenarios](investigate-alerts.md).</span></span>

> [!TIP]
> <span data-ttu-id="c36e2-118">Os blocos de acesso controlados a pastas não geram alertas na fila [de alertas.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="c36e2-118">Controlled folder access blocks don't generate alerts in the [Alerts queue](alerts-queue.md).</span></span> <span data-ttu-id="c36e2-119">No entanto, você pode exibir informações sobre blocos de acesso controlados a pastas no exibição de linha do tempo do dispositivo [,](investigate-machines.md)ao usar a busca avançada [ou](advanced-hunting-overview.md)com regras de detecção [personalizadas.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="c36e2-119">However, you can view information about controlled folder access blocks in the [device timeline view](investigate-machines.md), while using [advanced hunting](advanced-hunting-overview.md), or with [custom detection rules](custom-detection-rules.md).</span></span>

## <a name="how-does-controlled-folder-access-work"></a><span data-ttu-id="c36e2-120">Como funciona o acesso controlado a pastas?</span><span class="sxs-lookup"><span data-stu-id="c36e2-120">How does controlled folder access work?</span></span>

<span data-ttu-id="c36e2-121">O acesso controlado a pastas funciona apenas permitindo que aplicativos confiáveis acessem pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="c36e2-121">Controlled folder access works by only allowing trusted apps to access protected folders.</span></span> <span data-ttu-id="c36e2-122">As pastas protegidas são especificadas quando o acesso controlado a pastas é configurado.</span><span class="sxs-lookup"><span data-stu-id="c36e2-122">Protected folders are specified when controlled folder access is configured.</span></span> <span data-ttu-id="c36e2-123">Normalmente, pastas comumente usadas, como as usadas para documentos, imagens, downloads e assim por diante, são incluídas na lista de pastas controladas.</span><span class="sxs-lookup"><span data-stu-id="c36e2-123">Typically, commonly used folders, such as those used for documents, pictures, downloads, and so on, are included in the list of controlled folders.</span></span> 

<span data-ttu-id="c36e2-124">O acesso controlado a pastas funciona com uma lista de aplicativos confiáveis.</span><span class="sxs-lookup"><span data-stu-id="c36e2-124">Controlled folder access works with a list of trusted apps.</span></span> <span data-ttu-id="c36e2-125">Os aplicativos incluídos na lista de softwares confiáveis funcionam conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="c36e2-125">Apps that are included in the list of trusted software work as expected.</span></span> <span data-ttu-id="c36e2-126">Os aplicativos que não estão incluídos na lista são impedidos de fazer alterações nos arquivos dentro de pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="c36e2-126">Apps that are not included in the list are prevented from making any changes to files inside protected folders.</span></span> 

<span data-ttu-id="c36e2-127">Os aplicativos são adicionados à lista com base em sua prevalência e reputação.</span><span class="sxs-lookup"><span data-stu-id="c36e2-127">Apps are added to the list based upon their prevalence and reputation.</span></span> <span data-ttu-id="c36e2-128">Aplicativos altamente predominantes em toda a sua organização e que nunca exibiram nenhum comportamento considerado mal-intencionado são considerados confiáveis.</span><span class="sxs-lookup"><span data-stu-id="c36e2-128">Apps that are highly prevalent throughout your organization and that have never displayed any behavior deemed malicious are considered trustworthy.</span></span> <span data-ttu-id="c36e2-129">Esses aplicativos são adicionados à lista automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c36e2-129">Those apps are added to the list automatically.</span></span>

<span data-ttu-id="c36e2-130">Os aplicativos também podem ser adicionados manualmente à lista confiável usando o Configuration Manager ou o Intune.</span><span class="sxs-lookup"><span data-stu-id="c36e2-130">Apps can also be added manually to the trusted list by using Configuration Manager or Intune.</span></span> <span data-ttu-id="c36e2-131">Ações adicionais, como [adicionar um indicador](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) de arquivo para um aplicativo, podem ser executadas no Console da Central de Segurança.</span><span class="sxs-lookup"><span data-stu-id="c36e2-131">Additional actions, such as [adding a file indicator](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) for an app, can be performed from the Security Center Console.</span></span>

## <a name="why-controlled-folder-access-is-important"></a><span data-ttu-id="c36e2-132">Por que o acesso controlado a pastas é importante</span><span class="sxs-lookup"><span data-stu-id="c36e2-132">Why controlled folder access is important</span></span>

<span data-ttu-id="c36e2-133">O acesso controlado a pastas é especialmente útil para ajudar a proteger seus documentos e informações do [ransomware.](https://www.microsoft.com/wdsi/threats/ransomware)</span><span class="sxs-lookup"><span data-stu-id="c36e2-133">Controlled folder access is especially useful in helping to protect your documents and information from [ransomware](https://www.microsoft.com/wdsi/threats/ransomware).</span></span> <span data-ttu-id="c36e2-134">Em um ataque de ransomware, seus arquivos podem ser criptografados e mantidos como reféns.</span><span class="sxs-lookup"><span data-stu-id="c36e2-134">In a ransomware attack, your files can get encrypted and held hostage.</span></span> <span data-ttu-id="c36e2-135">Com o acesso controlado a pastas no local, uma notificação é exibida no computador onde um aplicativo tentou fazer alterações em um arquivo em uma pasta protegida.</span><span class="sxs-lookup"><span data-stu-id="c36e2-135">With controlled folder access in place, a notification appears on the computer where an app attempted to make changes to a file in a protected folder.</span></span> <span data-ttu-id="c36e2-136">Você pode [personalizar a notificação com](customize-attack-surface-reduction.md#customize-the-notification) os detalhes da empresa e informações de contato.</span><span class="sxs-lookup"><span data-stu-id="c36e2-136">You can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your company details and contact information.</span></span> <span data-ttu-id="c36e2-137">Você também pode habilitar as regras individualmente para personalizar quais técnicas os monitores de recursos.</span><span class="sxs-lookup"><span data-stu-id="c36e2-137">You can also enable the rules individually to customize what techniques the feature monitors.</span></span>

<span data-ttu-id="c36e2-138">As [pastas protegidas incluem](#review-controlled-folder-access-events-in-windows-event-viewer) pastas comuns do sistema (incluindo setores de inicialização) e você pode [adicionar mais pastas](customize-controlled-folders.md#protect-additional-folders).</span><span class="sxs-lookup"><span data-stu-id="c36e2-138">The [protected folders](#review-controlled-folder-access-events-in-windows-event-viewer) include common system folders (including boot sectors), and you can [add more folders](customize-controlled-folders.md#protect-additional-folders).</span></span> <span data-ttu-id="c36e2-139">Você também pode [permitir que os aplicativos](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) lhes dêem acesso às pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="c36e2-139">You can also [allow apps](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) to give them access to the protected folders.</span></span>

<span data-ttu-id="c36e2-140">Você pode usar o [modo de auditoria](audit-windows-defender.md) para avaliar como o acesso controlado a pastas afetaria sua organização se ele estivesse habilitado.</span><span class="sxs-lookup"><span data-stu-id="c36e2-140">You can use [audit mode](audit-windows-defender.md) to evaluate how controlled folder access would impact your organization if it were enabled.</span></span> <span data-ttu-id="c36e2-141">Você também pode visitar o site do [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) Windows Defender de teste no demo.wd.microsoft.com para confirmar se o recurso está funcionando e ver como ele funciona.</span><span class="sxs-lookup"><span data-stu-id="c36e2-141">You can also visit the Windows Defender Test ground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

<span data-ttu-id="c36e2-142">O acesso controlado a pastas é suportado nas seguintes versões do Windows:</span><span class="sxs-lookup"><span data-stu-id="c36e2-142">Controlled folder access is supported on the following versions of Windows:</span></span>
- <span data-ttu-id="c36e2-143">[Windows 10, versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) e posterior</span><span class="sxs-lookup"><span data-stu-id="c36e2-143">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) and later</span></span>
- [<span data-ttu-id="c36e2-144">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c36e2-144">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

## <a name="windows-system-folders-are-protected-by-default"></a><span data-ttu-id="c36e2-145">As pastas do sistema Windows são protegidas por padrão</span><span class="sxs-lookup"><span data-stu-id="c36e2-145">Windows system folders are protected by default</span></span>

<span data-ttu-id="c36e2-146">As pastas do sistema Windows são protegidas por padrão, juntamente com várias outras pastas:</span><span class="sxs-lookup"><span data-stu-id="c36e2-146">Windows system folders are protected by default, along with several other folders:</span></span> 

- `c:\Users\<username>\Documents`
- `c:\Users\Public\Documents`
- `c:\Users\<username>\Pictures`
- `c:\Users\Public\Pictures`
- `c:\Users\Public\Videos`
- `c:\Users\<username>\Videos`
- `c:\Users\<username>\Music`
- `c:\Users\Public\Music`
- `c:\Users\<username>\Favorites`

> [!NOTE]
> <span data-ttu-id="c36e2-147">Você pode configurar pastas adicionais como protegidas, mas não pode remover as pastas do sistema Windows protegidas por padrão.</span><span class="sxs-lookup"><span data-stu-id="c36e2-147">You can configure additional folders as protected, but you cannot remove the Windows system folders that are protected by default.</span></span>

## <a name="requirements-for-controlled-folder-access"></a><span data-ttu-id="c36e2-148">Requisitos para acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="c36e2-148">Requirements for controlled folder access</span></span>

<span data-ttu-id="c36e2-149">O acesso controlado a pastas requer a habilitação da [proteção em tempo real do Microsoft Defender Antivírus.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="c36e2-149">Controlled folder access requires enabling [Microsoft Defender Antivirus real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

## <a name="review-controlled-folder-access-events-in-the-microsoft-defender-security-center"></a><span data-ttu-id="c36e2-150">Revisar eventos de acesso controlado a pastas no Centro de Segurança do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c36e2-150">Review controlled folder access events in the Microsoft Defender Security Center</span></span>

<span data-ttu-id="c36e2-151">O Defender for Endpoint fornece relatórios detalhados sobre eventos e blocos como parte de seus [cenários de investigação de alerta.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="c36e2-151">Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="c36e2-152">Você pode consultar dados do Microsoft Defender para o Ponto de Extremidade usando [a busca avançada](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="c36e2-152">You can query Microsoft Defender for Endpoint data by using [Advanced hunting](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection).</span></span> <span data-ttu-id="c36e2-153">Se você estiver usando o modo [](advanced-hunting-overview.md) [de](audit-windows-defender.md)auditoria, poderá usar a busca avançada para ver como as configurações de acesso controlado a pastas afetariam seu ambiente se elas fossem habilitadas.</span><span class="sxs-lookup"><span data-stu-id="c36e2-153">If you're using [audit mode](audit-windows-defender.md), you can use [advanced hunting](advanced-hunting-overview.md) to see how controlled folder access settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="c36e2-154">Exemplo de consulta:</span><span class="sxs-lookup"><span data-stu-id="c36e2-154">Example query:</span></span>

```PowerShell
DeviceEvents
| where ActionType in ('ControlledFolderAccessViolationAudited','ControlledFolderAccessViolationBlocked')
```

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a><span data-ttu-id="c36e2-155">Revisar eventos de acesso controlado a pastas no Visualizador de Eventos do Windows</span><span class="sxs-lookup"><span data-stu-id="c36e2-155">Review controlled folder access events in Windows Event Viewer</span></span>

<span data-ttu-id="c36e2-156">Você pode revisar o log de eventos do Windows para ver eventos criados quando blocos de acesso controlados a pastas (ou auditorias) um aplicativo:</span><span class="sxs-lookup"><span data-stu-id="c36e2-156">You can review the Windows event log to see events that are created when controlled folder access blocks (or audits) an app:</span></span>

1. <span data-ttu-id="c36e2-157">Baixe o [Pacote de Avaliação](https://aka.ms/mp7z2w) e extraia o arquivo *cfa-events.xml* para um local facilmente acessível no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c36e2-157">Download the [Evaluation Package](https://aka.ms/mp7z2w) and extract the file *cfa-events.xml* to an easily accessible location on the device.</span></span>
2. <span data-ttu-id="c36e2-158">Digite **Visualizador de eventos** no menu Iniciar para abrir o Visualizador de Eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="c36e2-158">Type **Event viewer** in the Start menu to open the Windows Event Viewer.</span></span>
3. <span data-ttu-id="c36e2-159">No painel esquerdo, em **Ações**, selecione **Importar exibição personalizada...**.</span><span class="sxs-lookup"><span data-stu-id="c36e2-159">On the left panel, under **Actions**, select **Import custom view...**.</span></span>
4. <span data-ttu-id="c36e2-160">Navegue até onde você *extraiucfa-events.xml* e selecione-o.</span><span class="sxs-lookup"><span data-stu-id="c36e2-160">Navigate to where you extracted *cfa-events.xml* and select it.</span></span> <span data-ttu-id="c36e2-161">Como alternativa, [copie o XML diretamente](event-views.md).</span><span class="sxs-lookup"><span data-stu-id="c36e2-161">Alternatively, [copy the XML directly](event-views.md).</span></span>
5. <span data-ttu-id="c36e2-162">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c36e2-162">Select **OK**.</span></span>

<span data-ttu-id="c36e2-163">A tabela a seguir mostra eventos relacionados ao acesso controlado a pastas:</span><span class="sxs-lookup"><span data-stu-id="c36e2-163">The following table shows events related to controlled folder access:</span></span>

|<span data-ttu-id="c36e2-164">ID de evento</span><span class="sxs-lookup"><span data-stu-id="c36e2-164">Event ID</span></span> | <span data-ttu-id="c36e2-165">Descrição</span><span class="sxs-lookup"><span data-stu-id="c36e2-165">Description</span></span> |
|:---|:---|
|<span data-ttu-id="c36e2-166">5007</span><span class="sxs-lookup"><span data-stu-id="c36e2-166">5007</span></span> | <span data-ttu-id="c36e2-167">Evento quando as configurações são alteradas</span><span class="sxs-lookup"><span data-stu-id="c36e2-167">Event when settings are changed</span></span> |
|<span data-ttu-id="c36e2-168">1124</span><span class="sxs-lookup"><span data-stu-id="c36e2-168">1124</span></span> | <span data-ttu-id="c36e2-169">Evento de acesso controlado a pastas auditadas</span><span class="sxs-lookup"><span data-stu-id="c36e2-169">Audited controlled folder access event</span></span> | 
|<span data-ttu-id="c36e2-170">1123</span><span class="sxs-lookup"><span data-stu-id="c36e2-170">1123</span></span> | <span data-ttu-id="c36e2-171">Evento de acesso controlado de pasta bloqueado</span><span class="sxs-lookup"><span data-stu-id="c36e2-171">Blocked controlled folder access event</span></span> |

## <a name="view-or-change-the-list-of-protected-folders"></a><span data-ttu-id="c36e2-172">Exibir ou alterar a lista de pastas protegidas</span><span class="sxs-lookup"><span data-stu-id="c36e2-172">View or change the list of protected folders</span></span>

<span data-ttu-id="c36e2-173">Você pode usar o aplicativo segurança do Windows para exibir a lista de pastas protegidas pelo acesso controlado a pastas.</span><span class="sxs-lookup"><span data-stu-id="c36e2-173">You can use the Windows Security app to view the list of folders that are protected by controlled folder access.</span></span> 

1. <span data-ttu-id="c36e2-174">Em seu dispositivo Windows 10, abra o aplicativo segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="c36e2-174">On your Windows 10 device, open the Windows Security app.</span></span>
2. <span data-ttu-id="c36e2-175">Selecione **Proteção contra & contra ameaças.**</span><span class="sxs-lookup"><span data-stu-id="c36e2-175">Select **Virus & threat protection**.</span></span>
3. <span data-ttu-id="c36e2-176">Em **Proteção contra ransomware,** selecione **Gerenciar proteção de ransomware**.</span><span class="sxs-lookup"><span data-stu-id="c36e2-176">Under **Ransomware protection**, select **Manage ransomware protection**.</span></span>
4. <span data-ttu-id="c36e2-177">Se o acesso controlado à pasta estiver desligado, você precisará au acessá-lo.</span><span class="sxs-lookup"><span data-stu-id="c36e2-177">If controlled folder access is turned off, you'll need to turn it on.</span></span> <span data-ttu-id="c36e2-178">Selecione **pastas protegidas**.</span><span class="sxs-lookup"><span data-stu-id="c36e2-178">Select **protected folders**.</span></span>
5. <span data-ttu-id="c36e2-179">Faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="c36e2-179">Do one of the following steps:</span></span>
   - <span data-ttu-id="c36e2-180">Para adicionar uma pasta, selecione **+ Adicionar uma pasta protegida**.</span><span class="sxs-lookup"><span data-stu-id="c36e2-180">To add a folder, select **+ Add a protected folder**.</span></span>
   - <span data-ttu-id="c36e2-181">Para remover uma pasta, selecione-a e selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="c36e2-181">To remove a folder, select it, and then select **Remove**.</span></span> 

> [!NOTE]
> <span data-ttu-id="c36e2-182">[As pastas do sistema do Windows](#windows-system-folders-are-protected-by-default) são protegidas por padrão e você não pode removê-las da lista.</span><span class="sxs-lookup"><span data-stu-id="c36e2-182">[Windows system folders](#windows-system-folders-are-protected-by-default) are protected by default, and you cannot remove them from the list.</span></span>

## <a name="see-also"></a><span data-ttu-id="c36e2-183">Confira também</span><span class="sxs-lookup"><span data-stu-id="c36e2-183">See also</span></span>

- [<span data-ttu-id="c36e2-184">Avaliar o acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="c36e2-184">Evaluate controlled folder access</span></span>](evaluate-controlled-folder-access.md)
- [<span data-ttu-id="c36e2-185">Personalizar o acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="c36e2-185">Customize controlled folder access</span></span>](customize-controlled-folders.md)
- [<span data-ttu-id="c36e2-186">Proteger mais pastas</span><span class="sxs-lookup"><span data-stu-id="c36e2-186">Protect more folders</span></span>](customize-controlled-folders.md#protect-additional-folders)
