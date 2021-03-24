---
title: Microsoft Defender ATP para Mac - extensões do sistema (Visualização)
description: Este artigo contém instruções para tentar a funcionalidade de extensões do sistema do Microsoft Defender ATP para Mac. Essa funcionalidade está atualmente em visualização pública.
keywords: microsoft, defender, atp, mac, kernel, sistema, extensões, catalina
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ROBOTS: noindex,nofollow
ms.technology: mde
ms.openlocfilehash: 8b644e27c5a36d2175ab18ae92424e7c70f39d0f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052891"
---
# <a name="microsoft-defender-for-endpoint-for-mac---system-extensions-public-preview"></a><span data-ttu-id="75e42-105">Microsoft Defender para Ponto de Extremidade para Mac - visualização pública de extensões do sistema)</span><span class="sxs-lookup"><span data-stu-id="75e42-105">Microsoft Defender for Endpoint for Mac - system extensions public preview)</span></span>

<span data-ttu-id="75e42-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="75e42-106">**Applies to:**</span></span>
- [<span data-ttu-id="75e42-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="75e42-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="75e42-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75e42-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="75e42-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="75e42-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="75e42-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="75e42-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="75e42-111">Em alinhamento com a evolução do macOS, estamos preparando um Defender para Endpoint para atualização do Mac que aproveita extensões do sistema em vez de extensões de kernel.</span><span class="sxs-lookup"><span data-stu-id="75e42-111">In alignment with macOS evolution, we are preparing a Defender for Endpoint for Mac update that leverages system extensions instead of kernel extensions.</span></span> <span data-ttu-id="75e42-112">Essa atualização só se aplicará ao macOS Catalina (10.15.4) e versões posteriores do macOS.</span><span class="sxs-lookup"><span data-stu-id="75e42-112">This update will only apply to macOS Catalina (10.15.4) and later versions of macOS.</span></span>

<span data-ttu-id="75e42-113">Essa funcionalidade está atualmente em visualização pública.</span><span class="sxs-lookup"><span data-stu-id="75e42-113">This functionality is currently in public preview.</span></span> <span data-ttu-id="75e42-114">Este artigo descreve como habilitar essa funcionalidade em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="75e42-114">This article describes how to enable this functionality on your device.</span></span> <span data-ttu-id="75e42-115">Você pode experimentar esse recurso localmente em seu próprio dispositivo ou configurá-lo remotamente por meio de uma ferramenta de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="75e42-115">You can try out this feature locally on your own device or configure it remotely through a management tool.</span></span>

<span data-ttu-id="75e42-116">Estas etapas pressuem que você já tenha o Defender para Ponto de Extremidade em execução em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="75e42-116">These steps assume you already have Defender for Endpoint running on your device.</span></span> <span data-ttu-id="75e42-117">Para saber mais, confira [esta página](microsoft-defender-endpoint-mac.md).</span><span class="sxs-lookup"><span data-stu-id="75e42-117">For more information, see [this page](microsoft-defender-endpoint-mac.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="75e42-118">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="75e42-118">Known issues</span></span>

- <span data-ttu-id="75e42-119">Recebemos relatórios da extensão de rede que interfere na extensão Kerberos do SSO da Apple.</span><span class="sxs-lookup"><span data-stu-id="75e42-119">We’ve received reports of the network extension interfering with the Apple SSO Kerberos extension.</span></span>
- <span data-ttu-id="75e42-120">A versão atual do produto ainda instala uma extensão de kernel.</span><span class="sxs-lookup"><span data-stu-id="75e42-120">The current version of the product still installs a kernel extension.</span></span> <span data-ttu-id="75e42-121">A extensão do kernel é usada apenas como um mecanismo de fallback e será removida antes que esse recurso atinja a visualização pública.</span><span class="sxs-lookup"><span data-stu-id="75e42-121">The kernel extension is only used as a fallback mechanism and will be removed before this feature reaches public preview.</span></span>
- <span data-ttu-id="75e42-122">Ainda estamos trabalhando em uma versão de produto que implanta e funciona corretamente no macOS 11 Big Sur.</span><span class="sxs-lookup"><span data-stu-id="75e42-122">We're still working on a product version that deploys and functions properly on macOS 11 Big Sur.</span></span>

## <a name="deployment-prerequisites"></a><span data-ttu-id="75e42-123">Pré-requisitos de implantação</span><span class="sxs-lookup"><span data-stu-id="75e42-123">Deployment prerequisites</span></span>

- <span data-ttu-id="75e42-124">Versão mínima do sistema operacional macOS: **10.15.4**</span><span class="sxs-lookup"><span data-stu-id="75e42-124">Minimum macOS operating system version: **10.15.4**</span></span>
- <span data-ttu-id="75e42-125">Versão mínima do produto: **101.03.73**</span><span class="sxs-lookup"><span data-stu-id="75e42-125">Minimum product version: **101.03.73**</span></span>
- <span data-ttu-id="75e42-126">Seu dispositivo deve estar no canal **de atualização do Insider Fast.**</span><span class="sxs-lookup"><span data-stu-id="75e42-126">Your device must be in the **Insider Fast update channel**.</span></span> <span data-ttu-id="75e42-127">Você pode verificar o canal de atualização usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="75e42-127">You can check the update channel by using the following command:</span></span>

  ```bash
  mdatp health --field release_ring
  ```

  <span data-ttu-id="75e42-128">Se o dispositivo ainda não estiver no canal de atualização do Insider Fast, execute o seguinte comando no Terminal.</span><span class="sxs-lookup"><span data-stu-id="75e42-128">If your device isn't already in the Insider Fast update channel, execute the following command from the Terminal.</span></span> <span data-ttu-id="75e42-129">A atualização de canal entra em vigor na próxima vez que o produto é iniciado (quando a próxima atualização do produto é instalada ou quando o dispositivo é reiniciado).</span><span class="sxs-lookup"><span data-stu-id="75e42-129">The channel update takes effect the next time the product starts (when the next product update is installed, or when the device is rebooted).</span></span>

  ```bash
  defaults write com.microsoft.autoupdate2 ChannelName -string Beta
  ```

  <span data-ttu-id="75e42-130">Como alternativa, se você estiver em um ambiente gerenciado (JAMF ou Intune), poderá configurar o canal de atualização remotamente.</span><span class="sxs-lookup"><span data-stu-id="75e42-130">Alternatively, if you're in a managed environment (JAMF or Intune), you can configure the update channel remotely.</span></span> <span data-ttu-id="75e42-131">Para obter mais informações, [consulte Deploy updates for Microsoft Defender ATP for Mac: Set the channel name](mac-updates.md#set-the-channel-name).</span><span class="sxs-lookup"><span data-stu-id="75e42-131">For more information, see [Deploy updates for Microsoft Defender ATP for Mac: Set the channel name](mac-updates.md#set-the-channel-name).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="75e42-132">Etapas de implantação</span><span class="sxs-lookup"><span data-stu-id="75e42-132">Deployment steps</span></span>

<span data-ttu-id="75e42-133">Siga as etapas de implantação que correspondem ao seu ambiente e ao seu método preferencial de tentar esse recurso.</span><span class="sxs-lookup"><span data-stu-id="75e42-133">Follow the deployment steps that correspond to your environment and your preferred method of trying out this feature.</span></span>

### <a name="manual-deployment"></a><span data-ttu-id="75e42-134">Implantação manual</span><span class="sxs-lookup"><span data-stu-id="75e42-134">Manual deployment</span></span>

#### <a name="approve-the-system-extensions-and-enable-the-network-extension"></a><span data-ttu-id="75e42-135">Aprovar as extensões do sistema e habilitar a extensão de rede</span><span class="sxs-lookup"><span data-stu-id="75e42-135">Approve the system extensions and enable the network extension</span></span>

1. <span data-ttu-id="75e42-136">Depois que todos os pré-requisitos de implantação são atendidos, reinicie o dispositivo para iniciar o processo de aprovação e ativação de extensão do sistema.</span><span class="sxs-lookup"><span data-stu-id="75e42-136">After all deployment prerequisites are met, restart your device to launch the system extension approval and activation process.</span></span>

   <span data-ttu-id="75e42-137">Você verá uma série de prompts do sistema para aprovar as extensões do sistema Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="75e42-137">You'll see a series of system prompts to approve the Defender for Endpoint system extensions.</span></span> <span data-ttu-id="75e42-138">Você deve aprovar **todos os** prompts da série, pois o macOS exige uma aprovação explícita para cada extensão que o Defender para Ponto de Extremidade para Mac instala no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="75e42-138">You must approve **all** prompts from the series, because macOS requires an explicit approval for each extension that Defender for Endpoint for Mac installs on the device.</span></span>
   
   <span data-ttu-id="75e42-139">Para cada aprovação, selecione **Abrir Preferências de Segurança** e, em seguida, selecione **Permitir** para permitir que a extensão do sistema seja executado.</span><span class="sxs-lookup"><span data-stu-id="75e42-139">For each approval, select **Open Security Preferences** and then select **Allow** to allow the system extension to run.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="75e42-140">Você deve fechar e reabrir a janela Segurança de **Preferências** do  >  **Sistema & Privacidade** entre aprovações subsequentes.</span><span class="sxs-lookup"><span data-stu-id="75e42-140">You must close and reopen the **System Preferences** > **Security & Privacy** window between subsequent approvals.</span></span> <span data-ttu-id="75e42-141">Caso contrário, o macOS não exibirá a próxima aprovação.</span><span class="sxs-lookup"><span data-stu-id="75e42-141">Otherwise, macOS will not display the next approval.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="75e42-142">Há um tempo de um minuto antes que o produto volte para a extensão do kernel.</span><span class="sxs-lookup"><span data-stu-id="75e42-142">There is a one-minute timeout before the product falls back to the kernel extension.</span></span> <span data-ttu-id="75e42-143">Isso garante que o dispositivo seja protegido.</span><span class="sxs-lookup"><span data-stu-id="75e42-143">This ensures that the device is protected.</span></span>
   >
   > <span data-ttu-id="75e42-144">Se mais de um minuto estiver em esmaeçamento, reinicie o daemon reiniciando o dispositivo ou usando para disparar `sudo killall -9 wdavdaemon` o fluxo de aprovação novamente.</span><span class="sxs-lookup"><span data-stu-id="75e42-144">If more than one minute elapses, restart the daemon by rebooting the device or by using `sudo killall -9 wdavdaemon` to trigger the approval flow again.</span></span>

   ![Pop-up de aprovação de extensão do sistema](images/mac-system-extension-approval.png)

   ![Janela de aprovação de extensão do sistema](images/mac-system-extension-pref.png)

1. <span data-ttu-id="75e42-147">Depois que as extensões do sistema são aprovadas, o macOS solicita uma aprovação para permitir que o tráfego de rede seja filtrado.</span><span class="sxs-lookup"><span data-stu-id="75e42-147">After the system extensions are approved, macOS prompts for an approval to allow network traffic to be filtered.</span></span> <span data-ttu-id="75e42-148">Clique **em Permitir**.</span><span class="sxs-lookup"><span data-stu-id="75e42-148">Click **Allow**.</span></span>

   ![Pop-up de aprovação de extensão de rede](images/mac-system-extension-filter.png)

#### <a name="grant-full-disk-access-to-the-endpoint-security-system-extension"></a><span data-ttu-id="75e42-150">Conceder acesso em disco completo à extensão do sistema de Segurança do Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="75e42-150">Grant Full Disk Access to the Endpoint Security system extension</span></span>

<span data-ttu-id="75e42-151">Abra a guia Segurança de **Preferências** do Sistema & Privacidade e conceda acesso total em disco à Extensão de Segurança do Ponto de  >    >   Extremidade do **Microsoft Defender.** </span><span class="sxs-lookup"><span data-stu-id="75e42-151">Open the **System Preferences** > **Security & Privacy** > **Privacy** tab and grant **Full Disk Access** to the **Microsoft Defender Endpoint Security Extension**.</span></span>

![Acesso em disco completo para extensão do sistema de Segurança do Ponto de Extremidade](images/mac-system-extension-fda.png)

#### <a name="reboot-your-device"></a><span data-ttu-id="75e42-153">Reiniciar seu dispositivo</span><span class="sxs-lookup"><span data-stu-id="75e42-153">Reboot your device</span></span>

<span data-ttu-id="75e42-154">Para que as alterações entre em vigor, você deve reiniciar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="75e42-154">In order for the changes to take effect, you must reboot your device.</span></span>

#### <a name="verify-that-the-system-extensions-are-running"></a><span data-ttu-id="75e42-155">Verifique se as extensões do sistema estão em execução</span><span class="sxs-lookup"><span data-stu-id="75e42-155">Verify that the system extensions are running</span></span>

<span data-ttu-id="75e42-156">No Terminal, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="75e42-156">From the Terminal, run the following command:</span></span>

```bash
mdatp health --field real_time_protection_subsystem
```

<span data-ttu-id="75e42-157">A saída `endpoint_security_extension` do terminal indica que o produto está usando a funcionalidade de extensões do sistema.</span><span class="sxs-lookup"><span data-stu-id="75e42-157">Terminal output `endpoint_security_extension` indicates the product is using the system extensions functionality.</span></span>

### <a name="managed-deployment"></a><span data-ttu-id="75e42-158">Implantação gerenciada</span><span class="sxs-lookup"><span data-stu-id="75e42-158">Managed deployment</span></span>

<span data-ttu-id="75e42-159">Consulte [Novos perfis de configuração](mac-sysext-policies.md#jamf) para macOS Catalina e versões mais recentes do macOS: JAMF para os novos perfis de configuração que você deve implantar para esse novo recurso.</span><span class="sxs-lookup"><span data-stu-id="75e42-159">Refer to [New configuration profiles for macOS Catalina and newer versions of macOS: JAMF](mac-sysext-policies.md#jamf) for the new configuration profiles you must deploy for this new feature.</span></span>

<span data-ttu-id="75e42-160">Além desses perfis, configure os dispositivos de destino para estar no canal de atualização do Insider Fast, conforme descrito em [Pré-requisitos de implantação.](#deployment-prerequisites)</span><span class="sxs-lookup"><span data-stu-id="75e42-160">In addition to those profiles, make sure to configure the target devices to be in the Insider Fast update channel, as described in [Deployment prerequisites](#deployment-prerequisites).</span></span>

<span data-ttu-id="75e42-161">Em um dispositivo onde todos os pré-requisitos são atendidos e os novos perfis de configuração foram implantados, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="75e42-161">On a device where all prerequisites are met and the new configuration profiles have been deployed, run the following command:</span></span>

```bash
$ mdatp health --field real_time_protection_subsystem
```

<span data-ttu-id="75e42-162">Se esse comando imprimir `endpoint_security_extension` , o produto está usando a funcionalidade de extensões do sistema.</span><span class="sxs-lookup"><span data-stu-id="75e42-162">If this command prints `endpoint_security_extension`, the product is using the system extensions functionality.</span></span>

## <a name="validate-basic-scenarios"></a><span data-ttu-id="75e42-163">Validar cenários básicos</span><span class="sxs-lookup"><span data-stu-id="75e42-163">Validate basic scenarios</span></span>

1. <span data-ttu-id="75e42-164">Teste a detecção do Instituto Europeu para Pesquisa de Antivírus do Computador (EICAR).</span><span class="sxs-lookup"><span data-stu-id="75e42-164">Test European Institute for Computer Antivirus Research (EICAR) detection.</span></span> <span data-ttu-id="75e42-165">Em uma janela terminal, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="75e42-165">From a Terminal window, run the following command:</span></span>

   ```bash
   curl -o eicar.txt https://secure.eicar.org/eicar.com.txt
   ```

   <span data-ttu-id="75e42-166">Verifique se o arquivo EICAR está em quarentena.</span><span class="sxs-lookup"><span data-stu-id="75e42-166">Verify that the EICAR file is quarantined.</span></span> <span data-ttu-id="75e42-167">Você pode verificar o status do arquivo na página Histórico de Proteção na interface do usuário ou em uma linha de comando usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="75e42-167">You can verify the file's status on the Protection History page in the user interface, or from a command line by using the following command:</span></span>

    ```bash
    mdatp threat list
    ```

2. <span data-ttu-id="75e42-168">Teste o cenário de Detecção e Resposta do Ponto de Extremidade (EDR).</span><span class="sxs-lookup"><span data-stu-id="75e42-168">Test the Endpoint Detection and Response (EDR) DIY scenario.</span></span> <span data-ttu-id="75e42-169">Em uma janela de terminal, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="75e42-169">From a terminal window, run the following command:</span></span>

   ```bash
   curl -o "MDATP MacOS DIY.zip" https://aka.ms/mdatpmacosdiy
   ```

   <span data-ttu-id="75e42-170">Valide se dois alertas surgiram no portal na página do computador para cenários EICAR e EDR DIY.</span><span class="sxs-lookup"><span data-stu-id="75e42-170">Validate that two alerts popped up in the portal on the machine page for EICAR and EDR DIY scenarios.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="75e42-171">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="75e42-171">Frequently asked questions</span></span>

- <span data-ttu-id="75e42-172">P: Por que ainda estou vendo `kernel_extension` quando `mdatp health --field real_time_protection_subsystem` corro?</span><span class="sxs-lookup"><span data-stu-id="75e42-172">Q: Why am I still seeing `kernel_extension` when I run `mdatp health --field real_time_protection_subsystem`?</span></span>

    <span data-ttu-id="75e42-173">R: Consulte a seção [Pré-requisitos](#deployment-prerequisites) de implantação e verifique se todos os pré-requisitos foram atendidos.</span><span class="sxs-lookup"><span data-stu-id="75e42-173">A: Refer back to the [Deployment prerequisites](#deployment-prerequisites) section and double-check that all prerequisites are met.</span></span> <span data-ttu-id="75e42-174">Se todos os pré-requisitos são atendidos, reinicie o dispositivo e verifique novamente.</span><span class="sxs-lookup"><span data-stu-id="75e42-174">If all prerequisites are met, restart your device and check again.</span></span>

- <span data-ttu-id="75e42-175">P: Quando o macOS 11 Big Sur será suportado?</span><span class="sxs-lookup"><span data-stu-id="75e42-175">Q: When will macOS 11 Big Sur be supported?</span></span>

    <span data-ttu-id="75e42-176">R: Estamos trabalhando ativamente para adicionar suporte para macOS 11.</span><span class="sxs-lookup"><span data-stu-id="75e42-176">A: We are actively working on adding support for macOS 11.</span></span> <span data-ttu-id="75e42-177">Postaremos mais informações na [página Novidades.](mac-whatsnew.md)</span><span class="sxs-lookup"><span data-stu-id="75e42-177">We will post more information to the [What's new](mac-whatsnew.md) page.</span></span>
