---
title: Microsoft Defender ATP para Linux
ms.reviewer: ''
description: Descreve como instalar e usar o Microsoft Defender ATP para Linux.
keywords: microsoft, defender, atp, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: ce7b15a727ddfa9b0d2bc68b7901f2e79aaf0721
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053585"
---
# <a name="microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="4f983-104">Microsoft Defender para Ponto de Extremidade para Linux</span><span class="sxs-lookup"><span data-stu-id="4f983-104">Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4f983-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="4f983-105">**Applies to:**</span></span>
- [<span data-ttu-id="4f983-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="4f983-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="4f983-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4f983-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4f983-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="4f983-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4f983-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="4f983-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="4f983-110">Este tópico descreve como instalar, configurar, atualizar e usar o Microsoft Defender para Endpoint para Linux.</span><span class="sxs-lookup"><span data-stu-id="4f983-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint for Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="4f983-111">A execução de outros produtos de proteção de ponto de extremidade de terceiros juntamente com o Microsoft Defender para Ponto de Extremidade para Linux provavelmente causará problemas de desempenho e erros imprevisíveis do sistema.</span><span class="sxs-lookup"><span data-stu-id="4f983-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint for Linux is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="4f983-112">Como instalar o Microsoft Defender para Ponto de Extremidade para Linux</span><span class="sxs-lookup"><span data-stu-id="4f983-112">How to install Microsoft Defender for Endpoint for Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="4f983-113">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="4f983-113">Prerequisites</span></span>

- <span data-ttu-id="4f983-114">Acesso ao portal do Centro de Segurança do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4f983-114">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="4f983-115">Distribuição linux usando o [system](https://systemd.io/) manager do sistema</span><span class="sxs-lookup"><span data-stu-id="4f983-115">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="4f983-116">Experiência de nível iniciante em scripts Linux e BASH</span><span class="sxs-lookup"><span data-stu-id="4f983-116">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="4f983-117">Privilégios administrativos no dispositivo (em caso de implantação manual)</span><span class="sxs-lookup"><span data-stu-id="4f983-117">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="4f983-118">Instruções de instalação</span><span class="sxs-lookup"><span data-stu-id="4f983-118">Installation instructions</span></span>

<span data-ttu-id="4f983-119">Há vários métodos e ferramentas de implantação que você pode usar para instalar e configurar o Microsoft Defender para Endpoint para Linux.</span><span class="sxs-lookup"><span data-stu-id="4f983-119">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="4f983-120">Em geral, você precisa seguir as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="4f983-120">In general you need to take the following steps:</span></span>

- <span data-ttu-id="4f983-121">Verifique se você tem uma assinatura do Microsoft Defender para Ponto de Extremidade e se tem acesso ao portal do [Microsoft Defender para Ponto de Extremidade.](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="4f983-121">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="4f983-122">Implante o Microsoft Defender para Ponto de Extremidade para Linux usando um dos seguintes métodos de implantação:</span><span class="sxs-lookup"><span data-stu-id="4f983-122">Deploy Microsoft Defender for Endpoint for Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="4f983-123">A ferramenta de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="4f983-123">The command-line tool:</span></span>
    - [<span data-ttu-id="4f983-124">Implantação manual</span><span class="sxs-lookup"><span data-stu-id="4f983-124">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="4f983-125">Ferramentas de gerenciamento de terceiros:</span><span class="sxs-lookup"><span data-stu-id="4f983-125">Third-party management tools:</span></span>
    - [<span data-ttu-id="4f983-126">Implantar usando a ferramenta de gerenciamento de configuração do Puppet</span><span class="sxs-lookup"><span data-stu-id="4f983-126">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="4f983-127">Implantar usando a ferramenta de gerenciamento de configuração Ansible</span><span class="sxs-lookup"><span data-stu-id="4f983-127">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="4f983-128">Se você tiver alguma falha de instalação, consulte [Troubleshooting installation failures in Microsoft Defender for Endpoint for Linux](linux-support-install.md).</span><span class="sxs-lookup"><span data-stu-id="4f983-128">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint for Linux](linux-support-install.md).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="4f983-129">Requisitos do sistema</span><span class="sxs-lookup"><span data-stu-id="4f983-129">System requirements</span></span>

- <span data-ttu-id="4f983-130">Versões e distribuições de servidor Linux com suporte:</span><span class="sxs-lookup"><span data-stu-id="4f983-130">Supported Linux server distributions and versions:</span></span>

  - <span data-ttu-id="4f983-131">Red Hat Enterprise Linux 7.2 ou superior</span><span class="sxs-lookup"><span data-stu-id="4f983-131">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="4f983-132">CentOS 7.2 ou superior</span><span class="sxs-lookup"><span data-stu-id="4f983-132">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="4f983-133">Ubuntu 16.04 LTS ou LTS superior</span><span class="sxs-lookup"><span data-stu-id="4f983-133">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="4f983-134">Debian 9 ou superior</span><span class="sxs-lookup"><span data-stu-id="4f983-134">Debian 9 or higher</span></span>
  - <span data-ttu-id="4f983-135">SUSE Linux Enterprise Server 12 ou superior</span><span class="sxs-lookup"><span data-stu-id="4f983-135">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="4f983-136">Oracle Linux 7.2 ou superior</span><span class="sxs-lookup"><span data-stu-id="4f983-136">Oracle Linux 7.2 or higher</span></span>

- <span data-ttu-id="4f983-137">Kernel mínimo versão 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="4f983-137">Minimum kernel version 3.10.0-327</span></span>
- <span data-ttu-id="4f983-138">A `fanotify` opção kernel deve estar habilitada</span><span class="sxs-lookup"><span data-stu-id="4f983-138">The `fanotify` kernel option must be enabled</span></span>
  > [!CAUTION]
  > <span data-ttu-id="4f983-139">Não há suporte para executar o Defender para Ponto de Extremidade para Linux lado a lado com outras soluções `fanotify` de segurança baseadas.</span><span class="sxs-lookup"><span data-stu-id="4f983-139">Running Defender for Endpoint for Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="4f983-140">Pode levar a resultados imprevisíveis, incluindo a suspensão do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="4f983-140">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="4f983-141">Espaço em disco: 1 GB</span><span class="sxs-lookup"><span data-stu-id="4f983-141">Disk space: 1GB</span></span>
- <span data-ttu-id="4f983-142">Atualmente, a solução fornece proteção em tempo real para os seguintes tipos de sistema de arquivos:</span><span class="sxs-lookup"><span data-stu-id="4f983-142">The solution currently provides real-time protection for the following file system types:</span></span>

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

<span data-ttu-id="4f983-143">Depois de habilitar o serviço, talvez seja necessário configurar sua rede ou firewall para permitir conexões de saída entre ele e seus pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="4f983-143">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="4f983-144">A estrutura de auditoria ( `auditd` ) deve estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="4f983-144">Audit framework (`auditd`) must be enabled.</span></span>
  >[!NOTE]
  > <span data-ttu-id="4f983-145">Os eventos do sistema capturados por regras adicionadas serão adicionados aos logs de auditoria e poderão afetar a auditoria de host e a `audit.logs` coleção upstream.</span><span class="sxs-lookup"><span data-stu-id="4f983-145">System events captured by rules added to `audit.logs` will add to audit logs and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="4f983-146">Os eventos adicionados pelo Microsoft Defender para Endopoint para Linux serão marcados com `mdatp` chave.</span><span class="sxs-lookup"><span data-stu-id="4f983-146">Events added by Microsoft Defender for Endopoint for Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="4f983-147">Conexões de rede</span><span class="sxs-lookup"><span data-stu-id="4f983-147">Network connections</span></span>

<span data-ttu-id="4f983-148">A planilha baixável a seguir lista os serviços e as URLs associadas às quais sua rede deve ser capaz de se conectar.</span><span class="sxs-lookup"><span data-stu-id="4f983-148">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="4f983-149">Você deve garantir que não haja regras de filtragem de rede ou firewall que negariam o acesso a essas URLs.</span><span class="sxs-lookup"><span data-stu-id="4f983-149">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="4f983-150">Se houver, talvez seja necessário criar uma regra *de* autorização especificamente para elas.</span><span class="sxs-lookup"><span data-stu-id="4f983-150">If there are, you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="4f983-151">**Planilha de lista de domínios**</span><span class="sxs-lookup"><span data-stu-id="4f983-151">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="4f983-152">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="4f983-152">**Description**</span></span>|
|:-----|:-----|
|![Imagem em miniatura da planilha URLs do Microsoft Defender para Endpoint](images/mdatp-urls.png)<br/>  | <span data-ttu-id="4f983-154">Planilha de registros DNS específicos para locais de serviço, localizações geográficas e sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="4f983-154">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="4f983-155">Baixe a planilha aqui.</span><span class="sxs-lookup"><span data-stu-id="4f983-155">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="4f983-156">Para obter uma lista de URL mais específica, consulte [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="4f983-156">For a more specific URL list, see [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="4f983-157">O Defender for Endpoint pode descobrir um servidor proxy usando os seguintes métodos de descoberta:</span><span class="sxs-lookup"><span data-stu-id="4f983-157">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="4f983-158">Proxy transparente</span><span class="sxs-lookup"><span data-stu-id="4f983-158">Transparent proxy</span></span>
- <span data-ttu-id="4f983-159">Configuração de proxy estático manual</span><span class="sxs-lookup"><span data-stu-id="4f983-159">Manual static proxy configuration</span></span>

<span data-ttu-id="4f983-160">Se um proxy ou firewall estiver bloqueando o tráfego anônimo, certifique-se de que o tráfego anônimo seja permitido nas URLs listadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4f983-160">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="4f983-161">Para proxies transparentes, nenhuma configuração adicional é necessária para o Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="4f983-161">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="4f983-162">Para proxy estático, siga as etapas em [Configuração de Proxy Estático Manual](linux-static-proxy-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="4f983-162">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="4f983-163">Pac, WPAD e proxies autenticados não são suportados.</span><span class="sxs-lookup"><span data-stu-id="4f983-163">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="4f983-164">Verifique se apenas um proxy estático ou um proxy transparente está sendo usado.</span><span class="sxs-lookup"><span data-stu-id="4f983-164">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="4f983-165">Os proxies de inspeção e interceptação de SSL também não são suportados por motivos de segurança.</span><span class="sxs-lookup"><span data-stu-id="4f983-165">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="4f983-166">Configure uma exceção para a inspeção SSL e seu servidor proxy passar diretamente os dados do Defender para o Ponto de Extremidade para Linux para as URLs relevantes sem interceptação.</span><span class="sxs-lookup"><span data-stu-id="4f983-166">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint for Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="4f983-167">Adicionar seu certificado de interceptação ao armazenamento global não permitirá interceptação.</span><span class="sxs-lookup"><span data-stu-id="4f983-167">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="4f983-168">Para etapas de solução de problemas, consulte Solucionar problemas de conectividade de nuvem [para o Microsoft Defender para Endpoint para Linux](linux-support-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="4f983-168">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint for Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="4f983-169">Como atualizar o Microsoft Defender para Ponto de Extremidade para Linux</span><span class="sxs-lookup"><span data-stu-id="4f983-169">How to update Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="4f983-170">A Microsoft publica regularmente atualizações de software para melhorar o desempenho, a segurança e fornecer novos recursos.</span><span class="sxs-lookup"><span data-stu-id="4f983-170">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="4f983-171">Para atualizar o Microsoft Defender para Ponto de Extremidade para Linux, consulte [Deploy updates for Microsoft Defender for Endpoint for Linux](linux-updates.md).</span><span class="sxs-lookup"><span data-stu-id="4f983-171">To update Microsoft Defender for Endpoint for Linux, refer to [Deploy updates for Microsoft Defender for Endpoint for Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="4f983-172">Como configurar o Microsoft Defender para Ponto de Extremidade para Linux</span><span class="sxs-lookup"><span data-stu-id="4f983-172">How to configure Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="4f983-173">As diretrizes sobre como configurar o produto em ambientes corporativos estão disponíveis em [Definir preferências](linux-preferences.md)do Microsoft Defender para Ponto de Extremidade para Linux .</span><span class="sxs-lookup"><span data-stu-id="4f983-173">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint for Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="4f983-174">Recursos</span><span class="sxs-lookup"><span data-stu-id="4f983-174">Resources</span></span>

- <span data-ttu-id="4f983-175">Para obter mais informações sobre log, desinstalação ou outros tópicos, consulte [Resources](linux-resources.md).</span><span class="sxs-lookup"><span data-stu-id="4f983-175">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
