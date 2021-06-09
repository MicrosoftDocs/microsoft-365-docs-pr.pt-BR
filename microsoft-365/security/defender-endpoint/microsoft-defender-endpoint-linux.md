---
title: Microsoft Defender para Ponto de Extremidade para Linux
ms.reviewer: ''
description: Descreve como instalar e usar o Microsoft Defender para Ponto de Extremidade no Linux.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
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
ms.technology: mde
ms.openlocfilehash: bd9d42ed85e9a489107a72ccbe841537a7e524d4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843513"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="c7647-104">Microsoft Defender para Ponto de Extremidade para Linux</span><span class="sxs-lookup"><span data-stu-id="c7647-104">Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c7647-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c7647-105">**Applies to:**</span></span>
- [<span data-ttu-id="c7647-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c7647-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c7647-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c7647-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c7647-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="c7647-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c7647-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="c7647-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="c7647-110">Este tópico descreve como instalar, configurar, atualizar e usar o Microsoft Defender para Ponto de Extremidade no Linux.</span><span class="sxs-lookup"><span data-stu-id="c7647-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint on Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="c7647-111">A execução de outros produtos de proteção de ponto de extremidade de terceiros juntamente com o Microsoft Defender para Ponto de Extremidade no Linux provavelmente levará a problemas de desempenho e efeitos colaterais imprevisíveis.</span><span class="sxs-lookup"><span data-stu-id="c7647-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint on Linux is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="c7647-112">Se a proteção de ponto de extremidade que não é da Microsoft for um requisito absoluto em seu ambiente, você ainda poderá aproveitar com segurança o Defender para Ponto de Extremidade na funcionalidade EDR Linux depois de configurar a funcionalidade antivírus para ser executado no modo Passivo [.](linux-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="c7647-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint on Linux EDR functionality after configuring the antivirus functionality to run in [Passive mode](linux-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="c7647-113">Como instalar o Microsoft Defender para Ponto de Extremidade no Linux</span><span class="sxs-lookup"><span data-stu-id="c7647-113">How to install Microsoft Defender for Endpoint on Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="c7647-114">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="c7647-114">Prerequisites</span></span>

- <span data-ttu-id="c7647-115">Acesso ao portal de Central de Segurança do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c7647-115">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="c7647-116">Distribuição linux usando o [system](https://systemd.io/) manager do sistema</span><span class="sxs-lookup"><span data-stu-id="c7647-116">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="c7647-117">Experiência de nível iniciante em scripts Linux e BASH</span><span class="sxs-lookup"><span data-stu-id="c7647-117">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="c7647-118">Privilégios administrativos no dispositivo (em caso de implantação manual)</span><span class="sxs-lookup"><span data-stu-id="c7647-118">Administrative privileges on the device (in case of manual deployment)</span></span>

> [!NOTE]
>  <span data-ttu-id="c7647-119">O Microsoft Defender para Ponto de Extremidade no Linux é independente do [agente OMS.](/azure/azure-monitor/agents/agents-overview#log-analytics-agent)</span><span class="sxs-lookup"><span data-stu-id="c7647-119">Microsoft Defender for Endpoint on Linux agent is independent from [OMS agent](/azure/azure-monitor/agents/agents-overview#log-analytics-agent).</span></span> <span data-ttu-id="c7647-120">O Microsoft Defender para Ponto de Extremidade depende de seu próprio pipeline de telemetria independente.</span><span class="sxs-lookup"><span data-stu-id="c7647-120">Microsoft Defender for Endpoint relies on its own independent telemetry pipeline.</span></span>
> 
> <span data-ttu-id="c7647-121">O Microsoft Defender para Ponto de Extremidade no Linux ainda não está integrado ao Centro de Segurança do Azure.</span><span class="sxs-lookup"><span data-stu-id="c7647-121">Microsoft Defender for Endpoint on Linux is not yet integrated into Azure Security Center.</span></span>



### <a name="installation-instructions"></a><span data-ttu-id="c7647-122">Instruções de instalação</span><span class="sxs-lookup"><span data-stu-id="c7647-122">Installation instructions</span></span>

<span data-ttu-id="c7647-123">Há vários métodos e ferramentas de implantação que você pode usar para instalar e configurar o Microsoft Defender para Ponto de Extremidade no Linux.</span><span class="sxs-lookup"><span data-stu-id="c7647-123">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="c7647-124">Em geral, você precisa seguir as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="c7647-124">In general you need to take the following steps:</span></span>

- <span data-ttu-id="c7647-125">Verifique se você tem uma assinatura do Microsoft Defender para Ponto de Extremidade e se tem acesso ao portal do [Microsoft Defender para Ponto de Extremidade.](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="c7647-125">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="c7647-126">Implante o Microsoft Defender para Ponto de Extremidade no Linux usando um dos seguintes métodos de implantação:</span><span class="sxs-lookup"><span data-stu-id="c7647-126">Deploy Microsoft Defender for Endpoint on Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="c7647-127">A ferramenta de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="c7647-127">The command-line tool:</span></span>
    - [<span data-ttu-id="c7647-128">Implantação manual</span><span class="sxs-lookup"><span data-stu-id="c7647-128">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="c7647-129">Ferramentas de gerenciamento de terceiros:</span><span class="sxs-lookup"><span data-stu-id="c7647-129">Third-party management tools:</span></span>
    - [<span data-ttu-id="c7647-130">Implantar usando a ferramenta de gerenciamento de configuração do Puppet</span><span class="sxs-lookup"><span data-stu-id="c7647-130">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="c7647-131">Implantar usando a ferramenta de gerenciamento de configuração Ansible</span><span class="sxs-lookup"><span data-stu-id="c7647-131">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="c7647-132">Se você tiver alguma falha de instalação, consulte [Troubleshooting installation failures in Microsoft Defender for Endpoint on Linux](linux-support-install.md).</span><span class="sxs-lookup"><span data-stu-id="c7647-132">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint on Linux](linux-support-install.md).</span></span>



### <a name="system-requirements"></a><span data-ttu-id="c7647-133">Requisitos do sistema</span><span class="sxs-lookup"><span data-stu-id="c7647-133">System requirements</span></span>

- <span data-ttu-id="c7647-134">Distribuições de servidor Linux com suporte e versões x64 (AMD64/EM64T) :</span><span class="sxs-lookup"><span data-stu-id="c7647-134">Supported Linux server distributions and x64 (AMD64/EM64T) versions:</span></span>

  - <span data-ttu-id="c7647-135">Red Hat Enterprise Linux 7.2 ou superior</span><span class="sxs-lookup"><span data-stu-id="c7647-135">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="c7647-136">CentOS 7.2 ou superior</span><span class="sxs-lookup"><span data-stu-id="c7647-136">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="c7647-137">Ubuntu 16.04 LTS ou LTS superior</span><span class="sxs-lookup"><span data-stu-id="c7647-137">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="c7647-138">Debian 9 ou superior</span><span class="sxs-lookup"><span data-stu-id="c7647-138">Debian 9 or higher</span></span>
  - <span data-ttu-id="c7647-139">SUSE Linux Enterprise Server 12 ou superior</span><span class="sxs-lookup"><span data-stu-id="c7647-139">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="c7647-140">Oracle Linux 7.2 ou superior</span><span class="sxs-lookup"><span data-stu-id="c7647-140">Oracle Linux 7.2 or higher</span></span>

    > [!NOTE]
    > <span data-ttu-id="c7647-141">As distribuições e as versões que não estão listadas explicitamente não têm suporte (mesmo que sejam derivadas das distribuições oficialmente suportadas).</span><span class="sxs-lookup"><span data-stu-id="c7647-141">Distributions and version that are not explicitly listed are unsupported (even if they are derived from the officially supported distributions).</span></span>


- <span data-ttu-id="c7647-142">Kernel mínimo versão 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="c7647-142">Minimum kernel version 3.10.0-327</span></span>

- <span data-ttu-id="c7647-143">A `fanotify` opção kernel deve estar habilitada</span><span class="sxs-lookup"><span data-stu-id="c7647-143">The `fanotify` kernel option must be enabled</span></span>

  > [!CAUTION]
  > <span data-ttu-id="c7647-144">Não há suporte para executar o Defender para Ponto de Extremidade no Linux lado a lado com outras soluções `fanotify` de segurança baseadas.</span><span class="sxs-lookup"><span data-stu-id="c7647-144">Running Defender for Endpoint on Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="c7647-145">Pode levar a resultados imprevisíveis, incluindo a suspensão do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="c7647-145">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="c7647-146">Espaço em disco: 1 GB</span><span class="sxs-lookup"><span data-stu-id="c7647-146">Disk space: 1 GB</span></span>

- <span data-ttu-id="c7647-147">/opt/microsoft/mdatp/sbin/wdavdaemon requer permissão executável.</span><span class="sxs-lookup"><span data-stu-id="c7647-147">/opt/microsoft/mdatp/sbin/wdavdaemon requires executable permission.</span></span> <span data-ttu-id="c7647-148">Para obter mais informações, consulte "Certifique-se de que o daemon tenha permissão executável" em Solucionar problemas de instalação do [Microsoft Defender para Ponto de](/microsoft-365/security/defender-endpoint/linux-support-install)Extremidade no Linux .</span><span class="sxs-lookup"><span data-stu-id="c7647-148">For more information, see "Ensure that the daemon has executable permission" in [Troubleshoot installation issues for Microsoft Defender for Endpoint on Linux](/microsoft-365/security/defender-endpoint/linux-support-install).</span></span>

- <span data-ttu-id="c7647-149">Memória: 1 GB</span><span class="sxs-lookup"><span data-stu-id="c7647-149">Memory: 1 GB</span></span>

    > [!NOTE]
    > <span data-ttu-id="c7647-150">Verifique se você tem espaço livre em disco no /var.</span><span class="sxs-lookup"><span data-stu-id="c7647-150">Please make sure that you have free disk space in /var.</span></span>

- <span data-ttu-id="c7647-151">Atualmente, a solução fornece proteção em tempo real para os seguintes tipos de sistema de arquivos:</span><span class="sxs-lookup"><span data-stu-id="c7647-151">The solution currently provides real-time protection for the following file system types:</span></span>

  - `btrfs`
  - `ecryptfs`
  - `ext2`
  - `ext3`
  - `ext4`
  - `fuse`
  - `fuseblk`
  - `jfs`
  - `nfs`
  - `overlay`
  - `ramfs`
  - `reiserfs`
  - `tmpfs`
  - `udf`
  - `vfat`
  - `xfs`

<span data-ttu-id="c7647-152">Depois de habilitar o serviço, talvez seja necessário configurar sua rede ou firewall para permitir conexões de saída entre ele e seus pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="c7647-152">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="c7647-153">A estrutura de auditoria ( `auditd` ) deve estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="c7647-153">Audit framework (`auditd`) must be enabled.</span></span>
  > [!NOTE]
  > <span data-ttu-id="c7647-154">Os eventos do sistema capturados por regras `/etc/audit/rules.d/` adicionadas serão adicionados a (s) e poderão afetar a auditoria de host e `audit.log` a coleção upstream.</span><span class="sxs-lookup"><span data-stu-id="c7647-154">System events captured by rules added to `/etc/audit/rules.d/` will add to `audit.log`(s) and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="c7647-155">Os eventos adicionados pelo Microsoft Defender para Ponto de Extremidade no Linux serão marcados com `mdatp` chave.</span><span class="sxs-lookup"><span data-stu-id="c7647-155">Events added by Microsoft Defender for Endpoint on Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="c7647-156">Conexões de rede</span><span class="sxs-lookup"><span data-stu-id="c7647-156">Network connections</span></span>

<span data-ttu-id="c7647-157">A planilha baixável a seguir lista os serviços e as URLs associadas às quais sua rede deve ser capaz de se conectar.</span><span class="sxs-lookup"><span data-stu-id="c7647-157">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="c7647-158">Você deve garantir que não haja regras de filtragem de rede ou firewall que negariam o acesso a essas URLs.</span><span class="sxs-lookup"><span data-stu-id="c7647-158">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="c7647-159">Se houver, talvez seja necessário criar uma regra *de* autorização especificamente para elas.</span><span class="sxs-lookup"><span data-stu-id="c7647-159">If there are, you may need to create an *allow* rule specifically for them.</span></span>

| <span data-ttu-id="c7647-160">Planilha de lista de domínios</span><span class="sxs-lookup"><span data-stu-id="c7647-160">Spreadsheet of domains list</span></span> | <span data-ttu-id="c7647-161">Descrição</span><span class="sxs-lookup"><span data-stu-id="c7647-161">Description</span></span> |
|:-----|:-----|
|![Imagem em miniatura da planilha URLs do Microsoft Defender para Endpoint](images/mdatp-urls.png)<br/>  | <span data-ttu-id="c7647-163">Planilha de registros DNS específicos para locais de serviço, localizações geográficas e sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="c7647-163">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="c7647-164">Baixe a planilha aqui.</span><span class="sxs-lookup"><span data-stu-id="c7647-164">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="c7647-165">Para obter uma lista de URL mais específica, consulte [Configure proxy and internet connectivity settings](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="c7647-165">For a more specific URL list, see [Configure proxy and internet connectivity settings](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="c7647-166">O Defender for Endpoint pode descobrir um servidor proxy usando os seguintes métodos de descoberta:</span><span class="sxs-lookup"><span data-stu-id="c7647-166">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="c7647-167">Proxy transparente</span><span class="sxs-lookup"><span data-stu-id="c7647-167">Transparent proxy</span></span>
- <span data-ttu-id="c7647-168">Configuração de proxy estático manual</span><span class="sxs-lookup"><span data-stu-id="c7647-168">Manual static proxy configuration</span></span>

<span data-ttu-id="c7647-169">Se um proxy ou firewall estiver bloqueando o tráfego anônimo, certifique-se de que o tráfego anônimo seja permitido nas URLs listadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c7647-169">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="c7647-170">Para proxies transparentes, nenhuma configuração adicional é necessária para o Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="c7647-170">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="c7647-171">Para proxy estático, siga as etapas em [Configuração de Proxy Estático Manual](linux-static-proxy-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="c7647-171">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="c7647-172">Pac, WPAD e proxies autenticados não são suportados.</span><span class="sxs-lookup"><span data-stu-id="c7647-172">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="c7647-173">Verifique se apenas um proxy estático ou um proxy transparente está sendo usado.</span><span class="sxs-lookup"><span data-stu-id="c7647-173">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="c7647-174">Os proxies de inspeção e interceptação de SSL também não são suportados por motivos de segurança.</span><span class="sxs-lookup"><span data-stu-id="c7647-174">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="c7647-175">Configure uma exceção para a inspeção SSL e seu servidor proxy passar diretamente os dados do Defender para o Ponto de Extremidade no Linux para as URLs relevantes sem interceptação.</span><span class="sxs-lookup"><span data-stu-id="c7647-175">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint on Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="c7647-176">Adicionar seu certificado de interceptação ao armazenamento global não permitirá interceptação.</span><span class="sxs-lookup"><span data-stu-id="c7647-176">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="c7647-177">Para etapas de solução de problemas, consulte Solucionar problemas de conectividade de nuvem [para o Microsoft Defender para Ponto de Extremidade no Linux](linux-support-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="c7647-177">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="c7647-178">Como atualizar o Microsoft Defender para Ponto de Extremidade no Linux</span><span class="sxs-lookup"><span data-stu-id="c7647-178">How to update Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="c7647-179">A Microsoft publica regularmente atualizações de software para melhorar o desempenho, a segurança e fornecer novos recursos.</span><span class="sxs-lookup"><span data-stu-id="c7647-179">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="c7647-180">Para atualizar o Microsoft Defender para Ponto de Extremidade no Linux, consulte [Deploy updates for Microsoft Defender for Endpoint on Linux](linux-updates.md).</span><span class="sxs-lookup"><span data-stu-id="c7647-180">To update Microsoft Defender for Endpoint on Linux, refer to [Deploy updates for Microsoft Defender for Endpoint on Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="c7647-181">Como configurar o Microsoft Defender para Ponto de Extremidade para Linux</span><span class="sxs-lookup"><span data-stu-id="c7647-181">How to configure Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="c7647-182">As diretrizes sobre como configurar o produto em ambientes corporativos estão disponíveis em [Definir preferências](linux-preferences.md)do Microsoft Defender para Ponto de Extremidade no Linux .</span><span class="sxs-lookup"><span data-stu-id="c7647-182">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint on Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="c7647-183">Recursos</span><span class="sxs-lookup"><span data-stu-id="c7647-183">Resources</span></span>

- <span data-ttu-id="c7647-184">Para obter mais informações sobre log, desinstalação ou outros tópicos, consulte [Resources](linux-resources.md).</span><span class="sxs-lookup"><span data-stu-id="c7647-184">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
