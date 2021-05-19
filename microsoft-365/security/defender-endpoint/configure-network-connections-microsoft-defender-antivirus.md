---
title: Configurar e validar as conexões de rede do Microsoft Defender Antivírus
description: Configure e teste sua conexão com o serviço de proteção Microsoft Defender Antivírus nuvem.
keywords: antivírus, Microsoft Defender Antivírus, antimalware, segurança, defensor, nuvem, agressividade, nível de proteção
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 5e754c2f4b5406d4b91ef624415f3819d3171305
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536017"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a><span data-ttu-id="029d4-104">Configurar e validar as conexões de rede do Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="029d4-104">Configure and validate Microsoft Defender Antivirus network connections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="029d4-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="029d4-105">**Applies to:**</span></span>

- [<span data-ttu-id="029d4-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="029d4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="029d4-107">Para garantir Microsoft Defender Antivírus proteção entregue na nuvem funcione corretamente, você precisa configurar sua rede para permitir conexões entre seus pontos de extremidade e determinados servidores Microsoft.</span><span class="sxs-lookup"><span data-stu-id="029d4-107">To ensure Microsoft Defender Antivirus cloud-delivered protection works properly, you need to configure your network to allow connections between your endpoints and certain Microsoft servers.</span></span> <span data-ttu-id="029d4-108">Este artigo lista as conexões que devem ser permitidas, como o uso de regras de firewall, e fornece instruções para validar sua conexão.</span><span class="sxs-lookup"><span data-stu-id="029d4-108">This article lists the connections that must be allowed, such as by using firewall rules, and provides instructions for validating your connection.</span></span> <span data-ttu-id="029d4-109">Configurar sua proteção corretamente ajuda a garantir que você receba o melhor valor de seus serviços de proteção entregues na nuvem.</span><span class="sxs-lookup"><span data-stu-id="029d4-109">Configuring your protection properly helps ensure that you receive the best value from your cloud-delivered protection services.</span></span>

<span data-ttu-id="029d4-110">Consulte a postagem do blog Alterações importantes no ponto de extremidade [do Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) para obter alguns detalhes sobre a conectividade de rede.</span><span class="sxs-lookup"><span data-stu-id="029d4-110">See the blog post [Important changes to Microsoft Active Protection Services endpoint](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) for some details about network connectivity.</span></span>

> [!TIP]
> <span data-ttu-id="029d4-111">Você também pode visitar o site de demonstração do Microsoft Defender para Ponto de Extremidade [no demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que os seguintes recursos estão funcionando:</span><span class="sxs-lookup"><span data-stu-id="029d4-111">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
>
> - <span data-ttu-id="029d4-112">Proteção fornecida na nuvem</span><span class="sxs-lookup"><span data-stu-id="029d4-112">Cloud-delivered protection</span></span>
> - <span data-ttu-id="029d4-113">Aprendizado rápido (incluindo bloquear à primeira vista)</span><span class="sxs-lookup"><span data-stu-id="029d4-113">Fast learning (including block at first sight)</span></span>
> - <span data-ttu-id="029d4-114">Bloqueio de aplicativo potencialmente indesejado</span><span class="sxs-lookup"><span data-stu-id="029d4-114">Potentially unwanted application blocking</span></span>

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a><span data-ttu-id="029d4-115">Permitir conexões com o serviço Microsoft Defender Antivírus nuvem</span><span class="sxs-lookup"><span data-stu-id="029d4-115">Allow connections to the Microsoft Defender Antivirus cloud service</span></span>

<span data-ttu-id="029d4-116">O Microsoft Defender Antivírus de nuvem oferece proteção rápida e forte para seus pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="029d4-116">The Microsoft Defender Antivirus cloud service provides fast, strong protection for your endpoints.</span></span> <span data-ttu-id="029d4-117">A habilitação do serviço de proteção entregue na nuvem é opcional, no entanto, é altamente recomendável porque fornece proteção importante contra malware em seus pontos de extremidade e em toda a sua rede.</span><span class="sxs-lookup"><span data-stu-id="029d4-117">Enabling the cloud-delivered protection service is optional, however it's highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

> [!NOTE]
> <span data-ttu-id="029d4-118">O Microsoft Defender Antivírus de nuvem é um mecanismo para fornecer proteção atualizada para sua rede e pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="029d4-118">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="029d4-119">Embora seja chamado de serviço de nuvem, ele não é simplesmente proteção para arquivos armazenados na nuvem, em vez disso, usa recursos distribuídos e aprendizado de máquina para fornecer proteção aos seus pontos de extremidade em uma taxa muito mais rápida do que as atualizações tradicionais de inteligência de segurança.</span><span class="sxs-lookup"><span data-stu-id="029d4-119">Although it's called a cloud service, it's not simply protection for files stored in the cloud, rather it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="029d4-120">Consulte [Habilitar](enable-cloud-protection-microsoft-defender-antivirus.md) a proteção entregue na nuvem para obter detalhes sobre como habilitar o serviço com o Intune, Microsoft Endpoint Configuration Manager, Política de Grupo, cmdlets do PowerShell ou em clientes individuais no aplicativo Segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="029d4-120">See [Enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) for details on enabling the service with Intune, Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, or on individual clients in the Windows Security app.</span></span> 

<span data-ttu-id="029d4-121">Depois de habilitar o serviço, talvez seja necessário configurar sua rede ou firewall para permitir conexões entre ele e seus pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="029d4-121">After you've enabled the service, you may need to configure your network or firewall to allow connections between it and your endpoints.</span></span>

<span data-ttu-id="029d4-122">Como sua proteção é um serviço de nuvem, os computadores devem ter acesso à Internet e acessar o Microsoft Defender para Office 365 de aprendizado de máquina.</span><span class="sxs-lookup"><span data-stu-id="029d4-122">Because your protection is a cloud service, computers must have access to the internet and reach the Microsoft Defender for Office 365 machine learning services.</span></span> <span data-ttu-id="029d4-123">Não exclua a URL `*.blob.core.windows.net` de nenhum tipo de inspeção de rede.</span><span class="sxs-lookup"><span data-stu-id="029d4-123">Don't exclude the URL `*.blob.core.windows.net` from any kind of network inspection.</span></span> 

<span data-ttu-id="029d4-124">A tabela a seguir lista os serviços e suas URLs associadas.</span><span class="sxs-lookup"><span data-stu-id="029d4-124">The table below lists the services and their associated URLs.</span></span> <span data-ttu-id="029d4-125">Certifique-se de que não haja regras de filtragem de rede ou firewall negando o acesso a essas URLs, ou talvez seja necessário criar uma regra de autorização especificamente para elas (excluindo a URL `*.blob.core.windows.net` ).</span><span class="sxs-lookup"><span data-stu-id="029d4-125">Make sure that there are no firewall or network filtering rules denying access to these URLs, or you may need to create an allow rule specifically for them (excluding the URL `*.blob.core.windows.net`).</span></span> <span data-ttu-id="029d4-126">Abaixo menção URLs estão usando a porta 443 para comunicação.</span><span class="sxs-lookup"><span data-stu-id="029d4-126">Below mention URLs are using port 443 for communication.</span></span>


| <span data-ttu-id="029d4-127">**Serviço**</span><span class="sxs-lookup"><span data-stu-id="029d4-127">**Service**</span></span>| <span data-ttu-id="029d4-128">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="029d4-128">**Description**</span></span> |<span data-ttu-id="029d4-129">**URL**</span><span class="sxs-lookup"><span data-stu-id="029d4-129">**URL**</span></span> |
| :--: | :-- | :-- |
| <span data-ttu-id="029d4-130">Microsoft Defender Antivírus serviço de proteção entregue na nuvem, também conhecido como Microsoft Active Protection Service (MAPS)</span><span class="sxs-lookup"><span data-stu-id="029d4-130">Microsoft Defender Antivirus cloud-delivered protection service, also referred to as Microsoft Active Protection Service (MAPS)</span></span>|<span data-ttu-id="029d4-131">Usado pela Microsoft Defender Antivírus para fornecer proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="029d4-131">Used by Microsoft Defender Antivirus to provide cloud-delivered protection</span></span>|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| <span data-ttu-id="029d4-132">Serviço de Atualização da Microsoft (MU)</span><span class="sxs-lookup"><span data-stu-id="029d4-132">Microsoft Update Service (MU)</span></span> <br/> <span data-ttu-id="029d4-133">Windows Serviço de Atualização (WU)</span><span class="sxs-lookup"><span data-stu-id="029d4-133">Windows Update Service (WU)</span></span>|  <span data-ttu-id="029d4-134">Inteligência de segurança e atualizações de produtos</span><span class="sxs-lookup"><span data-stu-id="029d4-134">Security intelligence and product updates</span></span>   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> <span data-ttu-id="029d4-135">Para obter detalhes, [consulte Pontos de extremidade de conexão para Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span><span class="sxs-lookup"><span data-stu-id="029d4-135">For details see [Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span></span>|
|<span data-ttu-id="029d4-136">Atualizações de inteligência de segurança Local de Download Alternativo (ADL)</span><span class="sxs-lookup"><span data-stu-id="029d4-136">Security intelligence updates Alternate Download Location (ADL)</span></span>|   <span data-ttu-id="029d4-137">Local alternativo para Microsoft Defender Antivírus atualizações de inteligência de segurança se a inteligência de segurança instalada estiver desa data (7 ou mais dias depois)</span><span class="sxs-lookup"><span data-stu-id="029d4-137">Alternate location for Microsoft Defender Antivirus Security intelligence updates if the installed Security intelligence is out of date (7 or more days behind)</span></span>|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br>  `go.microsoft.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| <span data-ttu-id="029d4-138">Armazenamento de envio de malware</span><span class="sxs-lookup"><span data-stu-id="029d4-138">Malware submission storage</span></span>|<span data-ttu-id="029d4-139">Upload local para arquivos enviados à Microsoft por meio do formulário de envio ou envio automático de amostra</span><span class="sxs-lookup"><span data-stu-id="029d4-139">Upload location for files submitted to Microsoft via the Submission form or automatic sample submission</span></span>    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| <span data-ttu-id="029d4-140">Lista de Revogação de Certificados (CRL)</span><span class="sxs-lookup"><span data-stu-id="029d4-140">Certificate Revocation List (CRL)</span></span>|<span data-ttu-id="029d4-141">Usado por Windows ao criar a conexão SSL com o MAPS para atualizar a CRL</span><span class="sxs-lookup"><span data-stu-id="029d4-141">Used by Windows when creating the SSL connection to MAPS for updating the CRL</span></span>   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| <span data-ttu-id="029d4-142">Loja de Símbolos</span><span class="sxs-lookup"><span data-stu-id="029d4-142">Symbol Store</span></span>|<span data-ttu-id="029d4-143">Usado pelo Microsoft Defender Antivírus para restaurar determinados arquivos críticos durante fluxos de correção</span><span class="sxs-lookup"><span data-stu-id="029d4-143">Used by Microsoft Defender Antivirus to restore certain critical files during remediation flows</span></span>  | `https://msdl.microsoft.com/download/symbols` |
| <span data-ttu-id="029d4-144">Cliente de Telemetria Universal</span><span class="sxs-lookup"><span data-stu-id="029d4-144">Universal Telemetry Client</span></span>| <span data-ttu-id="029d4-145">Usado por Windows para enviar dados de diagnóstico do cliente; Microsoft Defender Antivírus usa telemetria para fins de monitoramento de qualidade do produto</span><span class="sxs-lookup"><span data-stu-id="029d4-145">Used by Windows to send client diagnostic data; Microsoft Defender Antivirus uses telemetry for product quality monitoring purposes</span></span>   | <span data-ttu-id="029d4-146">A atualização usa SSL (Porta TCP 443) para baixar manifestos e carregar dados de diagnóstico para a Microsoft que usa os seguintes pontos de extremidade DNS:   `vortex-win.data.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="029d4-146">The update uses SSL (TCP Port 443) to download manifests and upload diagnostic data to Microsoft that uses the following DNS endpoints:   `vortex-win.data.microsoft.com`</span></span> <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a><span data-ttu-id="029d4-147">Validar conexões entre sua rede e a nuvem</span><span class="sxs-lookup"><span data-stu-id="029d4-147">Validate connections between your network and the cloud</span></span>

<span data-ttu-id="029d4-148">Depois de permitir as URLs listadas acima, você pode testar se você está conectado ao serviço de nuvem Microsoft Defender Antivírus e está relatando corretamente e recebendo informações para garantir que você esteja totalmente protegido.</span><span class="sxs-lookup"><span data-stu-id="029d4-148">After allowing the URLs listed above, you can test if you're connected to the Microsoft Defender Antivirus cloud service and are correctly reporting and receiving information to ensure you're fully protected.</span></span>

<span data-ttu-id="029d4-149">**Use a ferramenta cmdline para validar a proteção entregue na nuvem:**</span><span class="sxs-lookup"><span data-stu-id="029d4-149">**Use the cmdline tool to validate cloud-delivered protection:**</span></span>

<span data-ttu-id="029d4-150">Use o seguinte argumento com o utilitário Microsoft Defender Antivírus linha de comando ( ) para verificar se sua rede pode se comunicar com o serviço Microsoft Defender Antivírus `mpcmdrun.exe` nuvem:</span><span class="sxs-lookup"><span data-stu-id="029d4-150">Use the following argument with the Microsoft Defender Antivirus command-line utility (`mpcmdrun.exe`) to verify that your network can communicate with the Microsoft Defender Antivirus cloud service:</span></span>

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> <span data-ttu-id="029d4-151">Você precisa abrir uma versão de nível de administrador do prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="029d4-151">You need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="029d4-152">Clique com o botão direito do mouse no item no menu Iniciar, clique em **Executar como administrador** e clique em **Sim** no prompt de permissões.</span><span class="sxs-lookup"><span data-stu-id="029d4-152">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span> <span data-ttu-id="029d4-153">Esse comando funcionará apenas Windows 10 versão 1703 ou superior.</span><span class="sxs-lookup"><span data-stu-id="029d4-153">This command will only work on Windows 10, version 1703 or higher.</span></span>

<span data-ttu-id="029d4-154">Para obter mais informações, consulte [Manage Microsoft Defender Antivírus with the mpcmdrun.exe commandline tool](command-line-arguments-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="029d4-154">For more information, see [Manage Microsoft Defender Antivirus with the mpcmdrun.exe commandline tool](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="029d4-155">**Tente baixar um arquivo de malware falso da Microsoft:**</span><span class="sxs-lookup"><span data-stu-id="029d4-155">**Attempt to download a fake malware file from Microsoft:**</span></span>

<span data-ttu-id="029d4-156">Você pode baixar um arquivo de exemplo que Microsoft Defender Antivírus detectar e bloquear se estiver conectado corretamente à nuvem.</span><span class="sxs-lookup"><span data-stu-id="029d4-156">You can download a sample file that Microsoft Defender Antivirus will detect and block if you're properly connected to the cloud.</span></span>

<span data-ttu-id="029d4-157">Baixe o arquivo visitando [https://aka.ms/ioavtest](https://aka.ms/ioavtest) .</span><span class="sxs-lookup"><span data-stu-id="029d4-157">Download the file by visiting [https://aka.ms/ioavtest](https://aka.ms/ioavtest).</span></span>

> [!NOTE]
> <span data-ttu-id="029d4-158">Esse arquivo não é um malware real.</span><span class="sxs-lookup"><span data-stu-id="029d4-158">This file is not an actual piece of malware.</span></span> <span data-ttu-id="029d4-159">É um arquivo falso projetado para testar se você está conectado corretamente à nuvem.</span><span class="sxs-lookup"><span data-stu-id="029d4-159">It's a fake file that is designed to test if you're properly connected to the cloud.</span></span>

<span data-ttu-id="029d4-160">Se você estiver conectado corretamente, você verá uma notificação de Microsoft Defender Antivírus aviso.</span><span class="sxs-lookup"><span data-stu-id="029d4-160">If you're properly connected, you'll see a warning Microsoft Defender Antivirus notification.</span></span>

<span data-ttu-id="029d4-161">Se você estiver usando Microsoft Edge, você também verá uma mensagem de notificação:</span><span class="sxs-lookup"><span data-stu-id="029d4-161">If you're using Microsoft Edge, you'll also see a notification message:</span></span>

![Microsoft Edge informando ao usuário que o malware foi encontrado](images/defender/wdav-bafs-edge.png)

<span data-ttu-id="029d4-163">Uma mensagem semelhante ocorrerá se você estiver usando o Internet Explorer:</span><span class="sxs-lookup"><span data-stu-id="029d4-163">A similar message occurs if you're using Internet Explorer:</span></span>

![Microsoft Defender Antivírus notificação informando ao usuário que o malware foi encontrado](images/defender/wdav-bafs-ie.png)

<span data-ttu-id="029d4-165">Você também verá uma detecção em **Ameaças em quarentena** na seção **Histórico** de verificação no Segurança do Windows aplicativo:</span><span class="sxs-lookup"><span data-stu-id="029d4-165">You'll also see a detection under **Quarantined threats** in the **Scan history** section in the Windows Security app:</span></span>

1. <span data-ttu-id="029d4-166">Abra o Segurança do Windows aplicativo clicando no ícone de escudo na barra de tarefas ou pesquisando o menu inicial do **Defender**.</span><span class="sxs-lookup"><span data-stu-id="029d4-166">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="029d4-167">Selecione o **&** proteção contra ameaças (ou o ícone de escudo na barra de menus esquerda) e, em seguida, o rótulo **De histórico de** verificação:</span><span class="sxs-lookup"><span data-stu-id="029d4-167">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Scan history** label:</span></span>

    ![Captura de tela do rótulo de histórico de verificação no Segurança do Windows app](images/defender/wdav-history-wdsc.png)

3. <span data-ttu-id="029d4-169">Na seção **Ameaças em quarentena,** selecione **Ver histórico completo** para ver o malware falso detectado.</span><span class="sxs-lookup"><span data-stu-id="029d4-169">Under the **Quarantined threats** section, select **See full history** to see the detected fake malware.</span></span>

   > [!NOTE]
   > <span data-ttu-id="029d4-170">As versões Windows 10 versão 1703 têm uma interface de usuário diferente.</span><span class="sxs-lookup"><span data-stu-id="029d4-170">Versions of Windows 10 before version 1703 have a different user interface.</span></span> <span data-ttu-id="029d4-171">Consulte [Microsoft Defender Antivírus no aplicativo Segurança do Windows .](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="029d4-171">See [Microsoft Defender Antivirus in the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

   <span data-ttu-id="029d4-172">O Windows de eventos também mostrará Windows Defender ID do evento cliente [1116](troubleshoot-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="029d4-172">The Windows event log will also show [Windows Defender client event ID 1116](troubleshoot-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="029d4-173">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="029d4-173">Related articles</span></span>

- [<span data-ttu-id="029d4-174">Microsoft Defender Antivirus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="029d4-174">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)

- [<span data-ttu-id="029d4-175">Ativar proteção fornecida pela nuvem</span><span class="sxs-lookup"><span data-stu-id="029d4-175">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="029d4-176">Argumentos de linha de comando</span><span class="sxs-lookup"><span data-stu-id="029d4-176">Command line arguments</span></span>](command-line-arguments-microsoft-defender-antivirus.md)

- [<span data-ttu-id="029d4-177">Alterações importantes no ponto de extremidade do Microsoft Active Protection Services</span><span class="sxs-lookup"><span data-stu-id="029d4-177">Important changes to Microsoft Active Protection Services endpoint</span></span>](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)
