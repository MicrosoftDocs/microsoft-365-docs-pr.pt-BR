---
title: Configurar notificações do Microsoft Defender Antivírus
description: Saiba como configurar e personalizar notificações padrão e adicionais do Microsoft Defender Antivírus nos pontos de extremidade.
keywords: notificações, defender, antivírus, ponto de extremidade, gerenciamento, administrador
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a91da48f27450d6f4a6fd2b9607aa979458ccf71
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765090"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="2bcba-104">Configurar as notificações que aparecem nos pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="2bcba-104">Configure the notifications that appear on endpoints</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2bcba-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="2bcba-105">**Applies to:**</span></span>

- [<span data-ttu-id="2bcba-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2bcba-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="2bcba-107">No Windows 10, as notificações de aplicativos sobre detecção e correção de malware são mais robustas, consistentes e concisas.</span><span class="sxs-lookup"><span data-stu-id="2bcba-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="2bcba-108">As notificações são exibidas nos pontos de extremidade quando as verificações acionadas manualmente e agendadas são concluídas e as ameaças são detectadas.</span><span class="sxs-lookup"><span data-stu-id="2bcba-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="2bcba-109">Essas notificações também aparecem na Central de Notificações **,** e um resumo de verificações e detecções de ameaças aparecem em intervalos de tempo regulares.</span><span class="sxs-lookup"><span data-stu-id="2bcba-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="2bcba-110">Você também pode configurar como as notificações padrão aparecem nos pontos de extremidade, como notificações para reinicialização ou quando uma ameaça foi detectada e remediada.</span><span class="sxs-lookup"><span data-stu-id="2bcba-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="2bcba-111">Configurar as notificações adicionais que aparecem nos pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="2bcba-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="2bcba-112">Você pode configurar a exibição de notificações adicionais, como resumos recentes de detecção de ameaças, no aplicativo segurança do [Windows](microsoft-defender-security-center-antivirus.md) e com a Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="2bcba-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="2bcba-113">No Windows 10, versão 1607, o recurso era chamado notificações aprimoradas e poderia ser configurado em **Windows Settings** Update &   >  **segurança**  >  **Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="2bcba-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="2bcba-114">Nas configurações da Política de Grupo em todas as versões do Windows 10, ela é chamada **de Notificações aprimoradas.**</span><span class="sxs-lookup"><span data-stu-id="2bcba-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2bcba-115">Desabilitar notificações adicionais não desabilitará notificações críticas, como alertas de detecção e correção de ameaças.</span><span class="sxs-lookup"><span data-stu-id="2bcba-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="2bcba-116">**Use o aplicativo segurança do Windows para desabilitar notificações adicionais:**</span><span class="sxs-lookup"><span data-stu-id="2bcba-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="2bcba-117">Abra o aplicativo segurança do Windows clicando no ícone de escudo na barra de tarefas ou pesquisando o menu inicial do **Defender**.</span><span class="sxs-lookup"><span data-stu-id="2bcba-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="2bcba-118">Clique no **&** de proteção contra ameaças (ou o ícone de escudo na barra de **menus** esquerda) e, em seguida, o rótulo de configurações de proteção contra ameaças & vírus:</span><span class="sxs-lookup"><span data-stu-id="2bcba-118">Click the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Captura de tela do rótulo de configurações de proteção contra & vírus no aplicativo segurança do Windows](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="2bcba-120">Role até a **seção Notificações** e clique em **Alterar configurações de notificação**.</span><span class="sxs-lookup"><span data-stu-id="2bcba-120">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="2bcba-121">Deslize a opção para **Off** ou **On** para desabilitar ou habilitar notificações adicionais.</span><span class="sxs-lookup"><span data-stu-id="2bcba-121">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="2bcba-122">**Use a Política de Grupo para desabilitar notificações adicionais:**</span><span class="sxs-lookup"><span data-stu-id="2bcba-122">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="2bcba-123">No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2bcba-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="2bcba-124">No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**</span><span class="sxs-lookup"><span data-stu-id="2bcba-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="2bcba-125">Clique **em Modelos Administrativos**.</span><span class="sxs-lookup"><span data-stu-id="2bcba-125">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="2bcba-126">Expanda a árvore para **componentes do Windows > o Microsoft Defender Antivírus > Reporting**.</span><span class="sxs-lookup"><span data-stu-id="2bcba-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="2bcba-127">Clique duas **vezes em Desativar notificações aprimoradas** e de definir a opção como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="2bcba-127">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="2bcba-128">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2bcba-128">Click **OK**.</span></span> <span data-ttu-id="2bcba-129">Isso impedirá que notificações adicionais apareçam.</span><span class="sxs-lookup"><span data-stu-id="2bcba-129">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="2bcba-130">Configurar notificações padrão em pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="2bcba-130">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="2bcba-131">Você pode usar a Política de Grupo para:</span><span class="sxs-lookup"><span data-stu-id="2bcba-131">You can use Group Policy to:</span></span>

- <span data-ttu-id="2bcba-132">Exibir texto adicional e personalizado nos pontos de extremidade quando o usuário precisar executar uma ação</span><span class="sxs-lookup"><span data-stu-id="2bcba-132">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="2bcba-133">Ocultar todas as notificações nos pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="2bcba-133">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="2bcba-134">Ocultar notificações de reinicialização nos pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="2bcba-134">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="2bcba-135">Ocultar notificações pode ser útil em situações em que você não pode ocultar toda a interface do Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="2bcba-135">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="2bcba-136">Confira [Impedir que os usuários vejam ou interajam com a interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) do usuário do Microsoft Defender Antivírus para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="2bcba-136">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="2bcba-137">Ocultar notificações só ocorrerá nos pontos de extremidade aos quais a política foi implantada.</span><span class="sxs-lookup"><span data-stu-id="2bcba-137">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="2bcba-138">As notificações relacionadas a ações que devem ser tomadas (como uma reinicialização) ainda serão exibidas no painel de monitoramento e relatórios do [Microsoft Endpoint Manager Endpoint Protection.](/configmgr/protect/deploy-use/monitor-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="2bcba-138">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="2bcba-139">Confira [Personalizar o aplicativo de Segurança](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) do Windows para sua organização para obter instruções para adicionar informações de contato personalizadas às notificações que os usuários veem em seus computadores.</span><span class="sxs-lookup"><span data-stu-id="2bcba-139">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="2bcba-140">**Use a Política de Grupo para ocultar notificações:**</span><span class="sxs-lookup"><span data-stu-id="2bcba-140">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="2bcba-141">No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2bcba-141">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="2bcba-142">No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e clique em Modelos **administrativos.**</span><span class="sxs-lookup"><span data-stu-id="2bcba-142">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="2bcba-143">Expanda a árvore para componentes do Windows > interface do Cliente do **Microsoft Defender Antivírus >.**</span><span class="sxs-lookup"><span data-stu-id="2bcba-143">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="2bcba-144">Clique duas vezes **em Suprimir todas as notificações** e de definir a opção como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="2bcba-144">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="2bcba-145">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2bcba-145">Click **OK**.</span></span> <span data-ttu-id="2bcba-146">Isso impedirá que notificações adicionais apareçam.</span><span class="sxs-lookup"><span data-stu-id="2bcba-146">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="2bcba-147">**Use a Política de Grupo para ocultar notificações de reinicialização:**</span><span class="sxs-lookup"><span data-stu-id="2bcba-147">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="2bcba-148">No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2bcba-148">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="2bcba-149">No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**</span><span class="sxs-lookup"><span data-stu-id="2bcba-149">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="2bcba-150">Clique **em Modelos Administrativos**.</span><span class="sxs-lookup"><span data-stu-id="2bcba-150">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="2bcba-151">Expanda a árvore para componentes do Windows > interface do Cliente do **Microsoft Defender Antivírus >.**</span><span class="sxs-lookup"><span data-stu-id="2bcba-151">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="2bcba-152">Clique duas vezes **em Suprime notificações de reinicialização** e de definir a opção **como Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="2bcba-152">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="2bcba-153">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2bcba-153">Click **OK**.</span></span> <span data-ttu-id="2bcba-154">Isso impedirá que notificações adicionais apareçam.</span><span class="sxs-lookup"><span data-stu-id="2bcba-154">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2bcba-155">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2bcba-155">Related topics</span></span>

- [<span data-ttu-id="2bcba-156">Microsoft Defender Antivírus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="2bcba-156">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="2bcba-157">Configurar a interação do usuário final com o Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="2bcba-157">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)