---
title: Solucionar problemas de instalação do Microsoft Defender ATP para Linux
ms.reviewer: ''
description: Solucionar problemas de instalação do Microsoft Defender ATP para Linux
keywords: microsoft, defender, atp, linux, installation
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
ms.openlocfilehash: 4486b8e9d3fb84c272343ca344a47e49663bb80d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187740"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="8aef9-104">Solucionar problemas de instalação do Microsoft Defender para Ponto de Extremidade para Linux</span><span class="sxs-lookup"><span data-stu-id="8aef9-104">Troubleshoot installation issues for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8aef9-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="8aef9-105">**Applies to:**</span></span>
- [<span data-ttu-id="8aef9-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="8aef9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8aef9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8aef9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8aef9-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="8aef9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8aef9-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="8aef9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="verify-if-installation-succeeded"></a><span data-ttu-id="8aef9-110">Verificar se a instalação foi bem-sucedida</span><span class="sxs-lookup"><span data-stu-id="8aef9-110">Verify if installation succeeded</span></span>

<span data-ttu-id="8aef9-111">Um erro na instalação pode ou não resultar em uma mensagem de erro significativa pelo gerente do pacote.</span><span class="sxs-lookup"><span data-stu-id="8aef9-111">An error in installation may or may not result in a meaningful error message by the package manager.</span></span> <span data-ttu-id="8aef9-112">Para verificar se a instalação foi bem-sucedida, obtenha e verifique os logs de instalação usando:</span><span class="sxs-lookup"><span data-stu-id="8aef9-112">To verify if the installation succeeded, obtain and check the installation logs using:</span></span>

 ```bash
 sudo journalctl | grep 'microsoft-mdatp'  > installation.log
```

```bash
 grep 'postinstall end' installation.log
```

```Output
 microsoft-mdatp-installer[102243]: postinstall end [2020-03-26 07:04:43OURCE +0000] 102216
 ```

<span data-ttu-id="8aef9-113">Uma saída do comando anterior com data e hora corretas de instalação indica sucesso.</span><span class="sxs-lookup"><span data-stu-id="8aef9-113">An output from the previous command with correct date and time of installation indicates success.</span></span>

<span data-ttu-id="8aef9-114">Verifique também [a configuração do](linux-install-manually.md#client-configuration) cliente para verificar a saúde do produto e detectar o arquivo de texto EICAR.</span><span class="sxs-lookup"><span data-stu-id="8aef9-114">Also check the [Client configuration](linux-install-manually.md#client-configuration) to verify the health of the product and detect the EICAR text file.</span></span>

## <a name="make-sure-you-have-the-correct-package"></a><span data-ttu-id="8aef9-115">Certifique-se de ter o pacote correto</span><span class="sxs-lookup"><span data-stu-id="8aef9-115">Make sure you have the correct package</span></span>

<span data-ttu-id="8aef9-116">Lembre-se de que o pacote que você está instalando está correspondendo à distribuição e à versão do host.</span><span class="sxs-lookup"><span data-stu-id="8aef9-116">Please mind that the package you are installing is matching the host distribution and version.</span></span>

| <span data-ttu-id="8aef9-117">pacote</span><span class="sxs-lookup"><span data-stu-id="8aef9-117">package</span></span>                       | <span data-ttu-id="8aef9-118">distribution</span><span class="sxs-lookup"><span data-stu-id="8aef9-118">distribution</span></span>                             |
|-------------------------------|------------------------------------------|
| <span data-ttu-id="8aef9-119">mdatp-rhel8. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="8aef9-119">mdatp-rhel8.Linux.x86_64.rpm</span></span>  | <span data-ttu-id="8aef9-120">Oracle, RHEL e CentOS 8.x</span><span class="sxs-lookup"><span data-stu-id="8aef9-120">Oracle, RHEL and CentOS 8.x</span></span>              |
| <span data-ttu-id="8aef9-121">mdatp-sles12. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="8aef9-121">mdatp-sles12.Linux.x86_64.rpm</span></span> | <span data-ttu-id="8aef9-122">SuSE Linux Enterprise Server 12.x</span><span class="sxs-lookup"><span data-stu-id="8aef9-122">SuSE Linux Enterprise Server 12.x</span></span>        |
| <span data-ttu-id="8aef9-123">mdatp-sles15. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="8aef9-123">mdatp-sles15.Linux.x86_64.rpm</span></span> | <span data-ttu-id="8aef9-124">SuSE Linux Enterprise Server 15.x</span><span class="sxs-lookup"><span data-stu-id="8aef9-124">SuSE Linux Enterprise Server 15.x</span></span>        |
| <span data-ttu-id="8aef9-125">mdatp. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="8aef9-125">mdatp.Linux.x86_64.rpm</span></span>        | <span data-ttu-id="8aef9-126">Oracle, RHEL e CentOS 7.x</span><span class="sxs-lookup"><span data-stu-id="8aef9-126">Oracle, RHEL and CentOS 7.x</span></span>              |
| <span data-ttu-id="8aef9-127">mdatp. Linux.x86_64.deb</span><span class="sxs-lookup"><span data-stu-id="8aef9-127">mdatp.Linux.x86_64.deb</span></span>        | <span data-ttu-id="8aef9-128">Debian e Ubuntu 16.04, 18.04 e 20.04</span><span class="sxs-lookup"><span data-stu-id="8aef9-128">Debian and Ubuntu 16.04, 18.04 and 20.04</span></span> |

<span data-ttu-id="8aef9-129">Para [implantação manual,](linux-install-manually.md)certifique-se de que a versão e o distro corretos foram escolhidos.</span><span class="sxs-lookup"><span data-stu-id="8aef9-129">For [manual deployment](linux-install-manually.md), make sure the correct distro and version had been chosen.</span></span>

## <a name="installation-failed"></a><span data-ttu-id="8aef9-130">Falha na instalação</span><span class="sxs-lookup"><span data-stu-id="8aef9-130">Installation failed</span></span>

<span data-ttu-id="8aef9-131">Verifique se o serviço mdatp está em execução:</span><span class="sxs-lookup"><span data-stu-id="8aef9-131">Check if the mdatp service is running:</span></span>

```bash
systemctl status mdatp
```
```Output
 ● mdatp.service - Microsoft Defender for Endpoint
   Loaded: loaded (/lib/systemd/system/mdatp.service; enabled; vendor preset: enabled)
   Active: active (running) since Thu 2020-03-26 10:37:30 IST; 23h ago
 Main PID: 1966 (wdavdaemon)
    Tasks: 105 (limit: 4915)
   CGroup: /system.slice/mdatp.service
           ├─1966 /opt/microsoft/mdatp/sbin/wdavdaemon
           ├─1967 /opt/microsoft/mdatp/sbin/wdavdaemon
           └─1968 /opt/microsoft/mdatp/sbin/wdavdaemon
 ```

## <a name="steps-to-troubleshoot-if-mdatp-service-isnt-running"></a><span data-ttu-id="8aef9-132">Etapas para solucionar problemas se o serviço mdatp não estiver em execução</span><span class="sxs-lookup"><span data-stu-id="8aef9-132">Steps to troubleshoot if mdatp service isn't running</span></span>

1. <span data-ttu-id="8aef9-133">Verifique se o usuário "mdatp" existe:</span><span class="sxs-lookup"><span data-stu-id="8aef9-133">Check if "mdatp" user exists:</span></span>

    ```bash
    id "mdatp"
    ```

    <span data-ttu-id="8aef9-134">Se não houver saída, execute</span><span class="sxs-lookup"><span data-stu-id="8aef9-134">If there’s no output, run</span></span>

    ```bash
    sudo useradd --system --no-create-home --user-group --shell /usr/sbin/nologin mdatp
    ```

2. <span data-ttu-id="8aef9-135">Tente ativar e reiniciar o serviço usando:</span><span class="sxs-lookup"><span data-stu-id="8aef9-135">Try enabling and restarting the service using:</span></span>

    ```bash
    sudo systemctl enable mdatp
    ```

    ```bash
    sudo systemctl restart mdatp
    ```

3. <span data-ttu-id="8aef9-136">Se mdatp.service não for encontrado ao executar o comando anterior, execute:</span><span class="sxs-lookup"><span data-stu-id="8aef9-136">If mdatp.service isn't found upon running the previous command, run:</span></span>

    ```bash
    sudo cp /opt/microsoft/mdatp/conf/mdatp.service <systemd_path>
    ```

    <span data-ttu-id="8aef9-137">onde ```<systemd_path>``` é ```/lib/systemd/system``` para distribuições Ubuntu e Debian e ```/usr/lib/systemd/system``` para o Rhel, CentOS, Oracle e SLES.</span><span class="sxs-lookup"><span data-stu-id="8aef9-137">where ```<systemd_path>``` is ```/lib/systemd/system``` for Ubuntu and Debian distributions and ```/usr/lib/systemd/system``` for Rhel, CentOS, Oracle and SLES.</span></span>
   <span data-ttu-id="8aef9-138">Em seguida, reprise a etapa 2.</span><span class="sxs-lookup"><span data-stu-id="8aef9-138">Then rerun step 2.</span></span>

4. <span data-ttu-id="8aef9-139">Se as etapas acima não funcionarem, verifique se SELinux está instalado e no modo de imposição.</span><span class="sxs-lookup"><span data-stu-id="8aef9-139">If the above steps don’t work, check if SELinux is installed and in enforcing mode.</span></span> <span data-ttu-id="8aef9-140">Em caso afirmativo, tente defini-lo como permissivo (preferencialmente) ou modo desabilitado.</span><span class="sxs-lookup"><span data-stu-id="8aef9-140">If so, try setting it to permissive (preferably) or disabled mode.</span></span> <span data-ttu-id="8aef9-141">Isso pode ser feito definindo o parâmetro como `SELINUX` "permissivo" ou "desabilitado" no `/etc/selinux/config` arquivo, seguido de reinicialização.</span><span class="sxs-lookup"><span data-stu-id="8aef9-141">It can be done by setting the parameter `SELINUX` to "permissive" or "disabled" in `/etc/selinux/config` file, followed by reboot.</span></span> <span data-ttu-id="8aef9-142">Verifique a página man do selinux para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="8aef9-142">Check the man-page of selinux for more details.</span></span>
<span data-ttu-id="8aef9-143">Agora tente reiniciar o serviço mdatp usando a etapa 2.</span><span class="sxs-lookup"><span data-stu-id="8aef9-143">Now try restarting the mdatp service using step 2.</span></span> <span data-ttu-id="8aef9-144">Reverter a alteração de configuração imediatamente, porém, por motivos de segurança depois de tentar e reiniciar.</span><span class="sxs-lookup"><span data-stu-id="8aef9-144">Revert the configuration change immediately though for security reasons after trying it and reboot.</span></span>

5. <span data-ttu-id="8aef9-145">Se `/opt` o diretório for um link simbólico, crie uma montagem de vinculação para `/opt/microsoft` .</span><span class="sxs-lookup"><span data-stu-id="8aef9-145">If `/opt` directory is a symbolic link, create a bind mount for `/opt/microsoft`.</span></span>

6. <span data-ttu-id="8aef9-146">Verifique se o daemon tem permissão executável.</span><span class="sxs-lookup"><span data-stu-id="8aef9-146">Ensure that the daemon has executable permission.</span></span>

    ```bash
    ls -l /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ```Output
    -rwxr-xr-x 2 root root 15502160 Mar  3 04:47 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    <span data-ttu-id="8aef9-147">Se o daemon não tiver permissões executáveis, torná-lo executável usando:</span><span class="sxs-lookup"><span data-stu-id="8aef9-147">If the daemon doesn't have executable permissions, make it executable using:</span></span>

    ```bash
    sudo chmod 0755 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    <span data-ttu-id="8aef9-148">e repetir a etapa 2.</span><span class="sxs-lookup"><span data-stu-id="8aef9-148">and retry running step 2.</span></span>

7. <span data-ttu-id="8aef9-149">Verifique se o sistema de arquivos que contém o wdavdaemon não está montado com "noexec".</span><span class="sxs-lookup"><span data-stu-id="8aef9-149">Ensure that the file system containing wdavdaemon isn't mounted with "noexec".</span></span>

## <a name="if-mdatp-service-is-running-but-eicar-text-file-detection-doesnt-work"></a><span data-ttu-id="8aef9-150">Se o serviço mdatp estiver em execução, mas a detecção de arquivo de texto EICAR não funcionar</span><span class="sxs-lookup"><span data-stu-id="8aef9-150">If mdatp service is running, but EICAR text file detection doesn't work</span></span>

1. <span data-ttu-id="8aef9-151">Verifique o tipo de sistema de arquivos usando:</span><span class="sxs-lookup"><span data-stu-id="8aef9-151">Check the file system type using:</span></span>

    ```bash
    findmnt -T <path_of_EICAR_file>
    ```

    <span data-ttu-id="8aef9-152">Atualmente, os sistemas de arquivos com suporte para atividades ao acessar estão [listados aqui](microsoft-defender-endpoint-linux.md#system-requirements).</span><span class="sxs-lookup"><span data-stu-id="8aef9-152">Currently supported file systems for on-access activity are listed [here](microsoft-defender-endpoint-linux.md#system-requirements).</span></span> <span data-ttu-id="8aef9-153">Todos os arquivos fora desses sistemas de arquivos não serão verificados.</span><span class="sxs-lookup"><span data-stu-id="8aef9-153">Any files outside these file systems won't be scanned.</span></span>

## <a name="command-line-tool-mdatp-isnt-working"></a><span data-ttu-id="8aef9-154">A ferramenta de linha de comando "mdatp" não está funcionando</span><span class="sxs-lookup"><span data-stu-id="8aef9-154">Command-line tool “mdatp” isn't working</span></span>

1. <span data-ttu-id="8aef9-155">Se a execução da ferramenta de linha de `mdatp` comando der um `command not found` erro, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="8aef9-155">If running the command-line tool `mdatp` gives an error `command not found`, run the following command:</span></span>

    ```bash
    sudo ln -sf /opt/microsoft/mdatp/sbin/wdavdaemonclient /usr/bin/mdatp
    ```

    <span data-ttu-id="8aef9-156">e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="8aef9-156">and try again.</span></span>

    <span data-ttu-id="8aef9-157">Se nenhuma das etapas acima ajudar, colete os logs de diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="8aef9-157">If none of the above steps help, collect the diagnostic logs:</span></span>

    ```bash
    sudo mdatp diagnostic create
    ```

    ```Output
    Diagnostic file created: <path to file>
    ```

    <span data-ttu-id="8aef9-158">O caminho para um arquivo zip que contém os logs será exibido como uma saída.</span><span class="sxs-lookup"><span data-stu-id="8aef9-158">Path to a zip file that contains the logs will be displayed as an output.</span></span> <span data-ttu-id="8aef9-159">Entre em contato com nosso suporte ao cliente com esses logs.</span><span class="sxs-lookup"><span data-stu-id="8aef9-159">Reach out to our customer support with these logs.</span></span>