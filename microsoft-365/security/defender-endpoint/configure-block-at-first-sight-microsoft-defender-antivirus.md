---
title: Habilite o recurso bloquear à primeira vista para detectar malware em segundos
description: Habilite o recurso bloquear à primeira vista para detectar e bloquear malware em segundos.
keywords: verificar, bloquear à primeira vista, malware, primeira vista, nuvem, defender, antivírus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 06/17/2021
ms.technology: mde
ms.topic: article
ms.openlocfilehash: a6bcc023571e544819ae7f276e6c3af5c1fc1335
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007388"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="07ff8-104">Ativar o recurso bloquear à primeira vista</span><span class="sxs-lookup"><span data-stu-id="07ff8-104">Turn on block at first sight</span></span>

<span data-ttu-id="07ff8-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="07ff8-105">**Applies to:**</span></span>

- [<span data-ttu-id="07ff8-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="07ff8-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="07ff8-107">Este artigo descreve um recurso do antivírus/antimalware conhecido como "bloquear à primeira vista" e descreve como habilitar o recurso bloquear à primeira vista para sua organização.</span><span class="sxs-lookup"><span data-stu-id="07ff8-107">This article describes an antivirus/antimalware feature known as "block at first sight", and describes how to enable block at first sight for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="07ff8-108">Este artigo se destina a administradores corporativos e Profissionais de TI que gerenciam configurações de segurança para organizações.</span><span class="sxs-lookup"><span data-stu-id="07ff8-108">This article is intended for enterprise admins and IT Pros who manage security settings for organizations.</span></span> <span data-ttu-id="07ff8-109">Se você não é um administrador corporativo ou Profissional de TI, mas tem dúvidas sobre o recurso bloquear à primeira vista, consulte a seção [Não sou um administrador corporativo ou Profissional de TI?](#not-an-enterprise-admin-or-it-pro).</span><span class="sxs-lookup"><span data-stu-id="07ff8-109">If you are not an enteprise admin or IT Pro but you have questions about block at first sight, see the [Not an enterprise admin or IT Pro?](#not-an-enterprise-admin-or-it-pro) section.</span></span>

## <a name="what-is-block-at-first-sight"></a><span data-ttu-id="07ff8-110">O que é "bloquear à primeira vista"?</span><span class="sxs-lookup"><span data-stu-id="07ff8-110">What is "block at first sight"?</span></span>

<span data-ttu-id="07ff8-111">Bloquear à primeira vista é um recurso de proteção de última geração contra ameaças que detecta novos malwares e os bloqueia em segundos.</span><span class="sxs-lookup"><span data-stu-id="07ff8-111">Block at first sight is a threat protection feature of next-generation protection that detects new malware and blocks it within seconds.</span></span> <span data-ttu-id="07ff8-112">O recurso bloquear à primeira vista é habilitado quando certas configurações de segurança são habilitadas.</span><span class="sxs-lookup"><span data-stu-id="07ff8-112">Block at first sight is enabled when certain security settings are enabled.</span></span> <span data-ttu-id="07ff8-113">Essas configurações incluem:</span><span class="sxs-lookup"><span data-stu-id="07ff8-113">These settings include:</span></span>

- <span data-ttu-id="07ff8-114">Proteção fornecida pela nuvem;</span><span class="sxs-lookup"><span data-stu-id="07ff8-114">Cloud-delivered protection;</span></span> 
- <span data-ttu-id="07ff8-115">Um tempo limite específico para envio de amostras (por exemplo, 50 segundos); e</span><span class="sxs-lookup"><span data-stu-id="07ff8-115">A specified sample submission timeout (such as 50 seconds); and</span></span> 
- <span data-ttu-id="07ff8-116">Um alto nível de bloqueio de arquivos.</span><span class="sxs-lookup"><span data-stu-id="07ff8-116">A file-blocking level of high.</span></span> 

<span data-ttu-id="07ff8-117">Na maioria das organizações empresariais, as configurações necessárias para habilitar o recurso bloquear à primeira vista são definidas com as implantações do Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="07ff8-117">In most enterprise organizations, the settings needed to enable block at first sight are configured with Microsoft Defender Antivirus deployments.</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="07ff8-118">Como funciona</span><span class="sxs-lookup"><span data-stu-id="07ff8-118">How it works</span></span>

<span data-ttu-id="07ff8-119">Quando o Microsoft Defender Antivirus encontra um arquivo suspeito, mas não detectado, ele consulta nosso back-end de proteção em nuvem.</span><span class="sxs-lookup"><span data-stu-id="07ff8-119">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="07ff8-120">O back-end da nuvem aplica heurística, aprendizado de máquina e análise automatizada do arquivo para determinar se os arquivos são maliciosos ou não são uma ameaça.</span><span class="sxs-lookup"><span data-stu-id="07ff8-120">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="07ff8-121">O Microsoft Defender Antivirus utiliza várias tecnologias de detecção e prevenção para fornecer uma proteção precisa, inteligente e em tempo real.</span><span class="sxs-lookup"><span data-stu-id="07ff8-121">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> 

![Lista de motores AV do Microsoft Defender](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> <span data-ttu-id="07ff8-123">Para saber mais, consulte [ (Blog) Conheça as tecnologias avançadas no núcleo do Microsoft Defender para Ponto de Extremidade para proteção de última geração](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span><span class="sxs-lookup"><span data-stu-id="07ff8-123">To learn more, see [(Blog) Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

## <a name="a-few-things-to-know-about-block-at-first-sight"></a><span data-ttu-id="07ff8-124">Algumas coisas para saber sobre o recurso bloquear à primeira vista</span><span class="sxs-lookup"><span data-stu-id="07ff8-124">A few things to know about block at first sight</span></span>

- <span data-ttu-id="07ff8-125">No Windows 10, versão 1803 ou posterior, o recurso bloquear à primeira vista pode bloquear arquivos executáveis não portáteis (como JS, VBS ou macros) e arquivos executáveis.</span><span class="sxs-lookup"><span data-stu-id="07ff8-125">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) and executable files.</span></span>

- <span data-ttu-id="07ff8-126">O recurso bloquear à primeira vista usa apenas o back-end de proteção em nuvem para arquivos executáveis e arquivos executáveis não portáteis baixados da Internet ou originados da zona da Internet.</span><span class="sxs-lookup"><span data-stu-id="07ff8-126">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="07ff8-127">Um valor do hash do arquivo .exe é verificado por meio do back-end da nuvem para determinar se o arquivo é um arquivo não detectado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="07ff8-127">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

- <span data-ttu-id="07ff8-128">Se o back-end da nuvem não for capaz de fazer uma determinação, o Microsoft Defender Antivirus bloqueará o arquivo e carregará uma cópia para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="07ff8-128">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="07ff8-129">A nuvem realizará mais análises para chegar a uma determinação antes de permitir que o arquivo seja executado ou bloqueado em todos os encontros futuros, dependendo se ela determinará o arquivo como sendo malicioso ou como não sendo uma ameaça.</span><span class="sxs-lookup"><span data-stu-id="07ff8-129">The cloud performs more analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or not a threat.</span></span>

- <span data-ttu-id="07ff8-130">Em muitos casos, esse processo pode reduzir o tempo de resposta para um novo malware de horas para segundos.</span><span class="sxs-lookup"><span data-stu-id="07ff8-130">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

- <span data-ttu-id="07ff8-131">Você pode [especificar por quanto tempo um arquivo deve ser impedido de ser executado](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) enquanto o serviço de proteção baseado em nuvem analisa o arquivo.</span><span class="sxs-lookup"><span data-stu-id="07ff8-131">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="07ff8-132">E você pode [personalizar a mensagem exibida na área de trabalho dos usuários](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) quando um arquivo for bloqueado.</span><span class="sxs-lookup"><span data-stu-id="07ff8-132">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="07ff8-133">Você pode alterar o nome da empresa, informações de contato e URL da mensagem.</span><span class="sxs-lookup"><span data-stu-id="07ff8-133">You can change the company name, contact information, and message URL.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="07ff8-134">Ative o recurso bloquear à primeira vista com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="07ff8-134">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="07ff8-135">O Microsoft Intune agora faz parte do Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="07ff8-135">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="07ff8-136">No Centro de administração do Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navegue até **Dispositivos** > **Perfis de configuração**.</span><span class="sxs-lookup"><span data-stu-id="07ff8-136">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="07ff8-137">Selecione ou crie um perfil usando o tipo de perfil **Restrições do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="07ff8-137">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="07ff8-138">Em **Definições de configuração** para o perfil de restrições de Dispositivo, defina ou confirme as seguintes configurações em **Microsoft Defender Antivirus**:</span><span class="sxs-lookup"><span data-stu-id="07ff8-138">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="07ff8-139">**Proteção fornecida pela nuvem**: Habilitada</span><span class="sxs-lookup"><span data-stu-id="07ff8-139">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="07ff8-140">**Nível de Bloqueio de Arquivo**: Alto</span><span class="sxs-lookup"><span data-stu-id="07ff8-140">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="07ff8-141">**Extensão de tempo para verificação de arquivos pela nuvem**: 50</span><span class="sxs-lookup"><span data-stu-id="07ff8-141">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="07ff8-142">**Avisar os usuários antes do envio da amostra**: Enviar todos os dados sem avisar</span><span class="sxs-lookup"><span data-stu-id="07ff8-142">**Prompt users before sample submission**: Send all data without prompting</span></span>

   :::image type="content" source="../../media/intune-block-at-first-sight.png" alt-text="Bloco de configuração do Intune à primeira vista":::

4. <span data-ttu-id="07ff8-144">Salvar suas configurações.</span><span class="sxs-lookup"><span data-stu-id="07ff8-144">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="07ff8-145">Definir o nível de bloqueio de arquivo como **Alto** aplica um nível forte de detecção.</span><span class="sxs-lookup"><span data-stu-id="07ff8-145">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="07ff8-146">No caso improvável de o bloqueio de arquivos causar uma detecção de falso positivo de arquivos legítimos, sua equipe de operações de segurança pode [restaurar os arquivos em quarentena](./restore-quarantined-files-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="07ff8-146">In the unlikely event that file blocking causes a false positive detection of legitimate files, your security operations team can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="07ff8-147">Para obter mais informações sobre como configurar as restrições do dispositivo Microsoft Defender Antivirus no Intune, consulte [Definir configurações de restrição do dispositivo no Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="07ff8-147">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="07ff8-148">Para obter uma lista de restrições de dispositivo do Microsoft Defender Antivirus no Intune, consulte [Restrição do dispositivo para configurações do Windows 10 (e mais recentes) no Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="07ff8-148">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="07ff8-149">Ative o recurso bloquear à primeira vista com o Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="07ff8-149">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="07ff8-150">Se você está procurando o Gerenciador de Configurações do Microsoft Endpoint, agora ele faz parte do Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="07ff8-150">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="07ff8-151">No Microsoft Endpoint Manager ([ https://endpoint.microsoft.com](https://endpoint.microsoft.com)), vá para **Segurança do ponto de extremidade** > **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="07ff8-151">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="07ff8-152">Selecione uma política existente ou crie uma nova utilizando o tipo de perfil **Microsoft Defender Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="07ff8-152">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="07ff8-153">Defina ou confirme as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="07ff8-153">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="07ff8-154">**Ativar a proteção fornecida pela nuvem**: Sim</span><span class="sxs-lookup"><span data-stu-id="07ff8-154">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="07ff8-155">**Nível de proteção fornecido pela nuvem**: Alto</span><span class="sxs-lookup"><span data-stu-id="07ff8-155">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="07ff8-156">**Tempo limite estendido do Defender Cloud em segundos**: 50</span><span class="sxs-lookup"><span data-stu-id="07ff8-156">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Configurações do recurso bloquear à primeira vista no Endpoint Manager ":::

4. <span data-ttu-id="07ff8-158">Aplique o perfil do Microsoft Defender Antivirus a um grupo, como **Todos os usuários**, **Todos os dispositivos** ou **Todos os usuários e dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="07ff8-158">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="07ff8-159">Ative o recurso bloquear à primeira vista com a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="07ff8-159">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="07ff8-160">Recomendamos o uso do Intune ou do Microsoft Endpoint Manager para ativar o recurso bloquear à primeira vista.</span><span class="sxs-lookup"><span data-stu-id="07ff8-160">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="07ff8-161">No computador de gerenciamento de Política de Grupo, abra o [ Console de Gerenciamento de Política de Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que deseja configurar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="07ff8-161">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="07ff8-162">Usando o **Editor de Gerenciamento de Política de Grupo**, vá até **Configuração do computador** > **Modelos administrativos** > **Componentes do Windows** > **Microsoft Defender Antivirus** > **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="07ff8-162">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="07ff8-163">Na seção MAPS, clique duas vezes em **Configurar o recurso 'Bloquear na primeira vista'**, defina-o como **Ativado** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="07ff8-163">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="07ff8-164">Definir para **Sempre solicitar (0)** diminuirá o estado de proteção do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="07ff8-164">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="07ff8-165">Definir como **Nunca enviar (2)** significa que o recurso bloquear à primeira vista não funcionará.</span><span class="sxs-lookup"><span data-stu-id="07ff8-165">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="07ff8-166">Na seção MAPS, clique duas vezes em **Enviar amostras do arquivo quando uma análise adicional for necessária** e defina-o como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="07ff8-166">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="07ff8-167">Em **Enviar amostras do arquivo quando análises adicionais forem necessárias**, selecione **Enviar todas as amostras** e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="07ff8-167">Under **Send file samples when further analysis is required**, select **Send all samples**, and then select **OK**.</span></span>

5. <span data-ttu-id="07ff8-168">Reimplante seu Objeto de Política de Grupo na sua rede como de costuma.</span><span class="sxs-lookup"><span data-stu-id="07ff8-168">Redeploy your Group Policy Object across your network as you usually do.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a><span data-ttu-id="07ff8-169">Confirme se o recurso bloquear à primeira vista está ativado nos dispositivos clientes individuais</span><span class="sxs-lookup"><span data-stu-id="07ff8-169">Confirm block at first sight is enabled on individual client devices</span></span>

<span data-ttu-id="07ff8-170">Você pode confirmar se o recurso bloquear à primeira vista está habilitado nos dispositivos clientes individuais usando o aplicativo de Segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="07ff8-170">You can confirm that block at first sight is enabled on individual client devices using the Windows Security app.</span></span> <span data-ttu-id="07ff8-171">O recurso bloquear à primeira vista é ativado automaticamente, desde que a **Proteção fornecida pela Nuvem** e o **Envio automático de amostras** estejam ambos ativados.</span><span class="sxs-lookup"><span data-stu-id="07ff8-171">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="07ff8-172">Abra o aplicativo Segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="07ff8-172">Open the Windows Security app.</span></span>

2. <span data-ttu-id="07ff8-173">Selecione **Proteção contra vírus e ameaças** e, em **Configurações de proteção contra vírus e ameaças**, selecione **Gerenciar Configurações**.</span><span class="sxs-lookup"><span data-stu-id="07ff8-173">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   :::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="Captura de tela da etiqueta de configurações de proteção contra vírus e ameaças no aplicativo de Segurança do Windows":::

3. <span data-ttu-id="07ff8-175">Confirme se a **Proteção fornecida pela nuvem** e o **Envio automático de amostra** estão ativados.</span><span class="sxs-lookup"><span data-stu-id="07ff8-175">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="07ff8-176">Se as configurações de pré-requisito forem definidas e implantadas usando a Política de Grupo, as configurações descritas nesta seção ficarão esmaecidas e indisponíveis para uso em pontos de extremidade individuais.</span><span class="sxs-lookup"><span data-stu-id="07ff8-176">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="07ff8-177">As alterações feitas por meio de um Objeto de Política de Grupo devem primeiro ser implantadas em pontos de extremidade individuais antes que a configuração seja atualizada nas configurações do Windows.</span><span class="sxs-lookup"><span data-stu-id="07ff8-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="07ff8-178">Validar se o recurso bloquear à primeira vista está funcionando</span><span class="sxs-lookup"><span data-stu-id="07ff8-178">Validate block at first sight is working</span></span>

<span data-ttu-id="07ff8-179">Para validar se o recurso está funcionando, baixe o [arquivo de exemplo Bloquear à primeira vista](https://demo.wd.microsoft.com/Page/BAFS).</span><span class="sxs-lookup"><span data-stu-id="07ff8-179">To validate that the feature is working, download the [Block at first sight sample file](https://demo.wd.microsoft.com/Page/BAFS).</span></span> <span data-ttu-id="07ff8-180">Para baixar o arquivo, você precisará de uma conta no Azure AD que tenha a função administrador de segurança ou administrador global atribuída.</span><span class="sxs-lookup"><span data-stu-id="07ff8-180">To download the file, you will need an account in Azure AD that has either the Security Administrator or Global Administrator role assigned.</span></span>

<span data-ttu-id="07ff8-181">Para validar se a proteção habilitada para nuvem está funcionando, siga as diretrizes em [Validar conexões entre sua rede e a nuvem](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span><span class="sxs-lookup"><span data-stu-id="07ff8-181">To validate that cloud-enabled protection is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span> 

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="07ff8-182">Desativar o recurso bloquear à primeira vista</span><span class="sxs-lookup"><span data-stu-id="07ff8-182">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="07ff8-183">Desativar o recurso bloquear à primeira vista diminuirá o estado de proteção do(s) seu(s) dispositivo(s) e da sua rede.</span><span class="sxs-lookup"><span data-stu-id="07ff8-183">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="07ff8-184">Você pode optar por desabilitar o recurso bloquear à primeira vista se quiser manter as configurações de pré-requisito sem realmente usar a proteção do recurso bloquear à primeira vista.</span><span class="sxs-lookup"><span data-stu-id="07ff8-184">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="07ff8-185">Você pode desativar temporariamente o recurso bloquear à primeira vista para ver como esse recurso afetará sua rede.</span><span class="sxs-lookup"><span data-stu-id="07ff8-185">You might temporarily turn block at first sight off to see how this feature affects your network.</span></span> <span data-ttu-id="07ff8-186">No entanto, não recomendamos desativar permanentemente a proteção do recurso bloquear à primeira vista.</span><span class="sxs-lookup"><span data-stu-id="07ff8-186">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="07ff8-187">Desativar o recurso bloquear à primeira vista com o Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="07ff8-187">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="07ff8-188">Vá para o Centro de administração do Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) e entre.</span><span class="sxs-lookup"><span data-stu-id="07ff8-188">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="07ff8-189">Vá para **Segurança do ponto de extremidade** > **Antivírus** e selecione a política do Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="07ff8-189">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="07ff8-190">Em **Gerenciar**, escolha **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="07ff8-190">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="07ff8-191">Ao lado de **Definições de configuração**, escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="07ff8-191">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="07ff8-192">Altere uma ou mais das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="07ff8-192">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="07ff8-193">Defina **Ativar proteção fornecida pela nuvem** como **Não** ou **Não configurado**.</span><span class="sxs-lookup"><span data-stu-id="07ff8-193">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="07ff8-194">Defina o **Nível de proteção fornecida pela nuvem** como **Não configurado**.</span><span class="sxs-lookup"><span data-stu-id="07ff8-194">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="07ff8-195">Desmarque a caixa de seleção para **Tempo Limite Estendido do Defender Cloud em Segundos**.</span><span class="sxs-lookup"><span data-stu-id="07ff8-195">Clear the check box for **Defender Cloud Extended Timeout In Seconds**.</span></span>

6. <span data-ttu-id="07ff8-196">Revise e salve suas configurações.</span><span class="sxs-lookup"><span data-stu-id="07ff8-196">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="07ff8-197">Desativar o recurso bloquear à primeira vista com a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="07ff8-197">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="07ff8-198">No computador de gerenciamento de Política de Grupo, abra o [Console de Gerenciamento de Política de Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que deseja configurar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="07ff8-198">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

2. <span data-ttu-id="07ff8-199">Usando o **Editor de Gerenciamento de Política de Grupo** vá para **Configuração do computador** e selecione **Modelos administrativos**.</span><span class="sxs-lookup"><span data-stu-id="07ff8-199">Using the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="07ff8-200">Expanda a árvore por meio dos **Componentes do Windows** > **Microsoft Defender Antivirus** > **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="07ff8-200">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="07ff8-201">Clique duas vezes em **Configurar o recurso 'Bloquear à primeira Vista'** e defina a opção como **Desativado**.</span><span class="sxs-lookup"><span data-stu-id="07ff8-201">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="07ff8-202">Desativar o recurso bloquear à primeira vista não desativa ou altera as políticas de grupo de pré-requisito.</span><span class="sxs-lookup"><span data-stu-id="07ff8-202">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="not-an-enterprise-admin-or-it-pro"></a><span data-ttu-id="07ff8-203">Não é um administrador corporativo ou profissional de TI?</span><span class="sxs-lookup"><span data-stu-id="07ff8-203">Not an enterprise admin or IT Pro?</span></span>

<span data-ttu-id="07ff8-204">Se você não é um administrador corporativo ou profissional de TI, mas tem dúvidas sobre o recurso bloquear à primeira vista, esta seção é para você.</span><span class="sxs-lookup"><span data-stu-id="07ff8-204">If you are not an enterprise admin or IT Pro, but you have questions about block at first sight, this section is for you.</span></span> <span data-ttu-id="07ff8-205">Bloquear à primeira vista é um recurso de proteção contra ameaças que detecta e bloqueia malware em segundos.</span><span class="sxs-lookup"><span data-stu-id="07ff8-205">Block at first sight is a threat protection feature that detects and blocks malware within seconds.</span></span> <span data-ttu-id="07ff8-206">Embora não haja uma configuração específica chamada "Bloquear à primeira vista", o recurso é habilitado quando certas configurações são definidas no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="07ff8-206">Although there isn't a specific setting called "Block at first sight," the feature is enabled when certain settings are configured on your device.</span></span>

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a><span data-ttu-id="07ff8-207">Como gerenciar o recurso bloquear à primeira vista ativado ou desativado em seu próprio dispositivo</span><span class="sxs-lookup"><span data-stu-id="07ff8-207">How to manage block at first sight on or off on your own device</span></span>

<span data-ttu-id="07ff8-208">Se você tiver um dispositivo pessoal que não é gerenciado por uma organização, pode estar se perguntando como ativar ou desativar o recurso bloquear à primeira vista.</span><span class="sxs-lookup"><span data-stu-id="07ff8-208">If you have a personal device that is not managed by an organization, you might be wondering how to turn block at first sight on or off.</span></span> <span data-ttu-id="07ff8-209">Você pode usar o aplicativo Windows Security para gerenciar o recurso bloquear à primeira vista.</span><span class="sxs-lookup"><span data-stu-id="07ff8-209">You can use the Windows Security app to manage block at first sight.</span></span>

1. <span data-ttu-id="07ff8-210">No seu computador com Windows 10, abra o aplicativo Segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="07ff8-210">On your Windows 10 computer, open the Windows Security app.</span></span>

2. <span data-ttu-id="07ff8-211">Select **Proteção contra vírus e ameaças**.</span><span class="sxs-lookup"><span data-stu-id="07ff8-211">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="07ff8-212">Em **Configurações de Proteção contra vírus e ameaças**, selecione **Gerenciar configurações**.</span><span class="sxs-lookup"><span data-stu-id="07ff8-212">Under **Virus & threat protection settings**, select **Manage settings**.</span></span>

4. <span data-ttu-id="07ff8-213">Siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="07ff8-213">Take one of the following steps:</span></span>

   - <span data-ttu-id="07ff8-214">Para ativar o recurso bloquear à primeira vista, certifique-se de que a **Proteção fornecida pela nuvem** e o **Envio automático de amostras** estejam ativados.</span><span class="sxs-lookup"><span data-stu-id="07ff8-214">To enable block at first sight, make sure that both **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

   - <span data-ttu-id="07ff8-215">Para desativar o recurso bloquear à primeira vista, desative **Proteção fornecida pela nuvem** ou **Envio automático de amostras**.</span><span class="sxs-lookup"><span data-stu-id="07ff8-215">To disable block at first sight, turn off **Cloud-delivered protection** or **Automatic sample submission**.</span></span> <br/>
    
     > [!CAUTION]
     > <span data-ttu-id="07ff8-216">Desativar o recurso bloquear à primeira vista reduz o nível de proteção do seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="07ff8-216">Turning off block at first sight lowers the level of protection for your device.</span></span> <span data-ttu-id="07ff8-217">Não recomendamos desabilitar permanentemente o recurso bloquear à primeira vista.</span><span class="sxs-lookup"><span data-stu-id="07ff8-217">We do not recommend permanently disabling block at first sight.</span></span> 


## <a name="see-also"></a><span data-ttu-id="07ff8-218">Confira também</span><span class="sxs-lookup"><span data-stu-id="07ff8-218">See also</span></span>

- [<span data-ttu-id="07ff8-219">Microsoft Defender Antivirus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="07ff8-219">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="07ff8-220">Ativar proteção fornecida pela nuvem</span><span class="sxs-lookup"><span data-stu-id="07ff8-220">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="07ff8-221">Permaneça protegido com a Segurança do Windows</span><span class="sxs-lookup"><span data-stu-id="07ff8-221">Stay protected with Windows Security</span></span>](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)
