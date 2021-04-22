---
title: Implantar o Microsoft Defender para Ponto de Extremidade no Linux com o Puppet
ms.reviewer: ''
description: Descreve como implantar o Microsoft Defender para Ponto de Extremidade no Linux usando o Puppet.
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d54732134e91b87b2639634c365556beda5312b0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934568"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-puppet"></a><span data-ttu-id="8998a-104">Implantar o Microsoft Defender para Ponto de Extremidade no Linux com o Puppet</span><span class="sxs-lookup"><span data-stu-id="8998a-104">Deploy Microsoft Defender for Endpoint on Linux with Puppet</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8998a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="8998a-105">**Applies to:**</span></span>
- [<span data-ttu-id="8998a-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="8998a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8998a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8998a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8998a-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="8998a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8998a-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="8998a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="8998a-110">Este artigo descreve como implantar o Defender para Ponto de Extremidade no Linux usando o Puppet.</span><span class="sxs-lookup"><span data-stu-id="8998a-110">This article describes how to deploy Defender for Endpoint on Linux using Puppet.</span></span> <span data-ttu-id="8998a-111">Uma implantação bem-sucedida requer a conclusão de todas as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="8998a-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="8998a-112">Baixar o pacote de integração</span><span class="sxs-lookup"><span data-stu-id="8998a-112">Download the onboarding package</span></span>](#download-the-onboarding-package)
- [<span data-ttu-id="8998a-113">Criar manifesto do Puppet</span><span class="sxs-lookup"><span data-stu-id="8998a-113">Create Puppet manifest</span></span>](#create-a-puppet-manifest)
- [<span data-ttu-id="8998a-114">Implantação</span><span class="sxs-lookup"><span data-stu-id="8998a-114">Deployment</span></span>](#deployment)
- [<span data-ttu-id="8998a-115">Verificar o status de integração</span><span class="sxs-lookup"><span data-stu-id="8998a-115">Check onboarding status</span></span>](#check-onboarding-status)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="8998a-116">Pré-requisitos e requisitos do sistema</span><span class="sxs-lookup"><span data-stu-id="8998a-116">Prerequisites and system requirements</span></span>

 <span data-ttu-id="8998a-117">Para ver uma descrição dos pré-requisitos e dos requisitos do sistema para a versão de software atual, consulte a página principal do Defender para Ponto de [Extremidade no Linux.](microsoft-defender-endpoint-linux.md)</span><span class="sxs-lookup"><span data-stu-id="8998a-117">For a description of prerequisites and system requirements for the current software version, see [the main Defender for Endpoint on Linux page](microsoft-defender-endpoint-linux.md).</span></span>

<span data-ttu-id="8998a-118">Além disso, para a implantação do Puppet, você precisa estar familiarizado com as tarefas de administração do Puppet, ter o Puppet configurado e saber como implantar pacotes.</span><span class="sxs-lookup"><span data-stu-id="8998a-118">In addition, for Puppet deployment, you need to be familiar with Puppet administration tasks, have Puppet configured, and know how to deploy packages.</span></span> <span data-ttu-id="8998a-119">O Puppet tem muitas maneiras de concluir a mesma tarefa.</span><span class="sxs-lookup"><span data-stu-id="8998a-119">Puppet has many ways to complete the same task.</span></span> <span data-ttu-id="8998a-120">Essas instruções pressupram a disponibilidade de módulos de Puppet com suporte, como *apt para* ajudar a implantar o pacote.</span><span class="sxs-lookup"><span data-stu-id="8998a-120">These instructions assume availability of supported Puppet modules, such as *apt* to help deploy the package.</span></span> <span data-ttu-id="8998a-121">Sua organização pode usar um fluxo de trabalho diferente.</span><span class="sxs-lookup"><span data-stu-id="8998a-121">Your organization might use a different workflow.</span></span> <span data-ttu-id="8998a-122">Consulte a [documentação do Puppet](https://puppet.com/docs) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="8998a-122">Refer to the [Puppet documentation](https://puppet.com/docs) for details.</span></span>

## <a name="download-the-onboarding-package"></a><span data-ttu-id="8998a-123">Baixar o pacote de integração</span><span class="sxs-lookup"><span data-stu-id="8998a-123">Download the onboarding package</span></span>

<span data-ttu-id="8998a-124">Baixe o pacote de integração do Centro de Segurança do Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="8998a-124">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="8998a-125">No Centro de Segurança do Microsoft Defender, acesse **Configurações > Gerenciamento de Dispositivos > Integração**.</span><span class="sxs-lookup"><span data-stu-id="8998a-125">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="8998a-126">No primeiro menu suspenso, selecione **Servidor Linux como** o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="8998a-126">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="8998a-127">No segundo menu suspenso, selecione Sua ferramenta de gerenciamento de configuração **do Linux preferencial** como o método de implantação.</span><span class="sxs-lookup"><span data-stu-id="8998a-127">In the second drop-down menu, select **Your preferred Linux configuration management tool** as the deployment method.</span></span>
3. <span data-ttu-id="8998a-128">Selecione **Baixar pacote de integração**.</span><span class="sxs-lookup"><span data-stu-id="8998a-128">Select **Download onboarding package**.</span></span> <span data-ttu-id="8998a-129">Salve o arquivo como WindowsDefenderATPOnboardingPackage.zip.</span><span class="sxs-lookup"><span data-stu-id="8998a-129">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Captura de tela do Centro de Segurança do Microsoft Defender](images/atp-portal-onboarding-linux-2.png)

4. <span data-ttu-id="8998a-131">Em um prompt de comando, verifique se você tem o arquivo.</span><span class="sxs-lookup"><span data-stu-id="8998a-131">From a command prompt, verify that you have the file.</span></span> 

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
5. <span data-ttu-id="8998a-132">Extraia o conteúdo do arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="8998a-132">Extract the contents of the archive.</span></span>
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-a-puppet-manifest"></a><span data-ttu-id="8998a-133">Criar um manifesto do Puppet</span><span class="sxs-lookup"><span data-stu-id="8998a-133">Create a Puppet manifest</span></span>

<span data-ttu-id="8998a-134">Você precisa criar um manifesto do Puppet para implantar o Defender para Ponto de Extremidade no Linux em dispositivos gerenciados por um servidor Desarmado.</span><span class="sxs-lookup"><span data-stu-id="8998a-134">You need to create a Puppet manifest for deploying Defender for Endpoint on Linux to devices managed by a Puppet server.</span></span> <span data-ttu-id="8998a-135">Este exemplo usa os módulos *apt* e *yumrepo* disponíveis a partir de placas de marionetes e pressupo que os módulos foram instalados em seu servidor Dep. de fantoches.</span><span class="sxs-lookup"><span data-stu-id="8998a-135">This example makes use of the *apt* and *yumrepo* modules available from puppetlabs, and assumes that the modules have been installed on your Puppet server.</span></span>

<span data-ttu-id="8998a-136">Crie as pastas *install_mdatp/arquivos e* *install_mdatp/manifestos* na pasta módulos de sua instalação do Puppet.</span><span class="sxs-lookup"><span data-stu-id="8998a-136">Create the folders *install_mdatp/files* and *install_mdatp/manifests* under the modules folder of your Puppet installation.</span></span> <span data-ttu-id="8998a-137">Essa pasta normalmente está localizada em */etc/puppetlabs/code/environments/production/modules* no servidor Desemterado.</span><span class="sxs-lookup"><span data-stu-id="8998a-137">This folder is typically located in */etc/puppetlabs/code/environments/production/modules* on your Puppet server.</span></span> <span data-ttu-id="8998a-138">Copie o mdatp_onboard.jsno arquivo criado acima para a pasta *install_mdatp/arquivos.*</span><span class="sxs-lookup"><span data-stu-id="8998a-138">Copy the mdatp_onboard.json file created above to the *install_mdatp/files* folder.</span></span> <span data-ttu-id="8998a-139">Criar *um init.pp*</span><span class="sxs-lookup"><span data-stu-id="8998a-139">Create an *init.pp*</span></span> <span data-ttu-id="8998a-140">que contém as instruções de implantação:</span><span class="sxs-lookup"><span data-stu-id="8998a-140">file that contains the deployment instructions:</span></span>

```bash
pwd
```
```Output
/etc/puppetlabs/code/environments/production/modules
```

```bash
tree install_mdatp
```
```Output
install_mdatp
├── files
│   └── mdatp_onboard.json
└── manifests
    └── init.pp
```

### <a name="contents-of-install_mdatpmanifestsinitpp"></a><span data-ttu-id="8998a-141">Conteúdo de `install_mdatp/manifests/init.pp`</span><span class="sxs-lookup"><span data-stu-id="8998a-141">Contents of `install_mdatp/manifests/init.pp`</span></span>

<span data-ttu-id="8998a-142">O Defender para Ponto de Extremidade no Linux pode ser implantado de um dos seguintes canais (denotado abaixo como *[canal]*): *insiders-fast,* *insiders-slow* ou *prod*. Cada um desses canais corresponde a um repositório de software Linux.</span><span class="sxs-lookup"><span data-stu-id="8998a-142">Defender for Endpoint on Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span>

<span data-ttu-id="8998a-143">A escolha do canal determina o tipo e a frequência de atualizações oferecidas ao seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8998a-143">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="8998a-144">Os *dispositivos em insiders-fast* são os primeiros a receber atualizações e novos recursos, seguidos posteriormente por *insiders-slow* e por *último por prod*.</span><span class="sxs-lookup"><span data-stu-id="8998a-144">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

<span data-ttu-id="8998a-145">Para visualizar novos recursos e fornecer comentários antecipados, é recomendável configurar alguns dispositivos em sua empresa para usar *insiders-fast* ou *insiders-slow*.</span><span class="sxs-lookup"><span data-stu-id="8998a-145">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

> [!WARNING]
> <span data-ttu-id="8998a-146">Alternar o canal após a instalação inicial exige que o produto seja reinstalado.</span><span class="sxs-lookup"><span data-stu-id="8998a-146">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="8998a-147">Para alternar o canal do produto: desinstale o pacote existente, configure novamente seu dispositivo para usar o novo canal e siga as etapas deste documento para instalar o pacote no novo local.</span><span class="sxs-lookup"><span data-stu-id="8998a-147">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

<span data-ttu-id="8998a-148">Observe sua distribuição e versão e identifique a entrada mais próxima para ela em `https://packages.microsoft.com/config/` .</span><span class="sxs-lookup"><span data-stu-id="8998a-148">Note your distribution and version and identify the closest entry for it under `https://packages.microsoft.com/config/`.</span></span>

<span data-ttu-id="8998a-149">Nos comandos a seguir, substitua *[distro]* e *[versão]* pela informação que você identificou:</span><span class="sxs-lookup"><span data-stu-id="8998a-149">In the below commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

> [!NOTE]
> <span data-ttu-id="8998a-150">No caso de RedHat, Oracle EL e CentOS 8, substitua *[distro]* por 'rel'.</span><span class="sxs-lookup"><span data-stu-id="8998a-150">In case of RedHat, Oracle EL, and CentOS 8, replace *[distro]* with 'rhel'.</span></span>

```puppet
# Puppet manifest to install Microsoft Defender for Endpoint on Linux.
# @param channel The release channel based on your environment, insider-fast or prod.
# @param distro The Linux distribution in lowercase. In case of RedHat, Oracle EL, and CentOS 8, the distro variable should be 'rhel'.
# @param version The Linux distribution release number, e.g. 7.4.

class install_mdatp (
$channel = 'insiders-fast',
$distro = undef,
$version = undef
){
    case $::osfamily {
        'Debian' : {
            apt::source { 'microsoftpackages' :
                location => "https://packages.microsoft.com/${distro}/${version}/prod",
                release  => $channel,
                repos    => 'main',
                key      => {
                    'id'     => 'BC528686B50D79E339D3721CEB3E94ADBE1229CF',
                    'server' => 'keyserver.ubuntu.com',
                },
            }
        }
        'RedHat' : {
            yumrepo { 'microsoftpackages' :
                baseurl  => "https://packages.microsoft.com/${distro}/${version}/${channel}",
                descr    => "packages-microsoft-com-prod-${channel}",
                enabled  => 1,
                gpgcheck => 1,
                gpgkey   => 'https://packages.microsoft.com/keys/microsoft.asc'
            }
        }
        default : { fail("${::osfamily} is currently not supported.") }
    }

    case $::osfamily {
        /(Debian|RedHat)/: {
            file { ['/etc/opt', '/etc/opt/microsoft', '/etc/opt/microsoft/mdatp']:
                ensure => directory,
                owner  => root,
                group  => root,
                mode   => '0755'
            }

            file { '/etc/opt/microsoft/mdatp/mdatp_onboard.json':
                source  => 'puppet:///modules/install_mdatp/mdatp_onboard.json',
                owner   => root,
                group   => root,
                mode    => '0600',
                require => File['/etc/opt/microsoft/mdatp']
            }

            package { 'mdatp':
                ensure  => 'installed',
                require => File['/etc/opt/microsoft/mdatp/mdatp_onboard.json']
            }
        }
        default : { fail("${::osfamily} is currently not supported.") }
    }
}
```

## <a name="deployment"></a><span data-ttu-id="8998a-151">Implantação</span><span class="sxs-lookup"><span data-stu-id="8998a-151">Deployment</span></span>

<span data-ttu-id="8998a-152">Incluir o manifesto acima em seu site.pp</span><span class="sxs-lookup"><span data-stu-id="8998a-152">Include the above manifest in your site.pp</span></span> <span data-ttu-id="8998a-153">file:</span><span class="sxs-lookup"><span data-stu-id="8998a-153">file:</span></span>

```bash
cat /etc/puppetlabs/code/environments/production/manifests/site.pp
```
```Output
node "default" {
    include install_mdatp
}
```

<span data-ttu-id="8998a-154">Os dispositivos de agente inscritos sondam periodicamente o Servidor de Marionetes e instalam novos perfis de configuração e políticas assim que são detectados.</span><span class="sxs-lookup"><span data-stu-id="8998a-154">Enrolled agent devices periodically poll the Puppet Server and install new configuration profiles and policies as soon as they are detected.</span></span>

## <a name="monitor-puppet-deployment"></a><span data-ttu-id="8998a-155">Monitorar a implantação do Puppet</span><span class="sxs-lookup"><span data-stu-id="8998a-155">Monitor Puppet deployment</span></span>

<span data-ttu-id="8998a-156">No dispositivo agente, você também pode verificar o status de integração executando:</span><span class="sxs-lookup"><span data-stu-id="8998a-156">On the agent device, you can also check the onboarding status by running:</span></span>

```bash
mdatp health
```
```Output
...
licensed                                : true
org_id                                  : "[your organization identifier]"
...
```

- <span data-ttu-id="8998a-157">**licenciado**: isso confirma se o dispositivo está vinculado à sua organização.</span><span class="sxs-lookup"><span data-stu-id="8998a-157">**licensed**: This confirms that the device is tied to your organization.</span></span>

- <span data-ttu-id="8998a-158">**orgId**: este é o identificador da organização do Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="8998a-158">**orgId**: This is your Defender for Endpoint organization identifier.</span></span>

## <a name="check-onboarding-status"></a><span data-ttu-id="8998a-159">Verificar o status de integração</span><span class="sxs-lookup"><span data-stu-id="8998a-159">Check onboarding status</span></span>

<span data-ttu-id="8998a-160">Você pode verificar se os dispositivos foram corretamente integrados criando um script.</span><span class="sxs-lookup"><span data-stu-id="8998a-160">You can check that devices have been correctly onboarded by creating a script.</span></span> <span data-ttu-id="8998a-161">Por exemplo, o script a seguir verifica os dispositivos inscritos para o status de integração:</span><span class="sxs-lookup"><span data-stu-id="8998a-161">For example, the following script checks enrolled devices for onboarding status:</span></span>

```bash
mdatp health --field healthy
```

<span data-ttu-id="8998a-162">O comando acima `1` imprime se o produto está onboarded e funcionando conforme esperado.</span><span class="sxs-lookup"><span data-stu-id="8998a-162">The above command prints `1` if the product is onboarded and functioning as expected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8998a-163">Quando o produto é iniciado pela primeira vez, ele baixa as definições antimalware mais recentes.</span><span class="sxs-lookup"><span data-stu-id="8998a-163">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="8998a-164">Dependendo da conexão com a Internet, isso pode levar até alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="8998a-164">Depending on your Internet connection, this can take up to a few minutes.</span></span> <span data-ttu-id="8998a-165">Durante esse tempo, o comando acima retorna um valor de `0` .</span><span class="sxs-lookup"><span data-stu-id="8998a-165">During this time the above command returns a value of `0`.</span></span>

<span data-ttu-id="8998a-166">Se o produto não estiver saudável, o código de saída (que pode ser verificado `echo $?` por ) indica o problema:</span><span class="sxs-lookup"><span data-stu-id="8998a-166">If the product is not healthy, the exit code (which can be checked through `echo $?`) indicates the problem:</span></span>

- <span data-ttu-id="8998a-167">1 se o dispositivo ainda não estiver conectado.</span><span class="sxs-lookup"><span data-stu-id="8998a-167">1 if the device isn't onboarded yet.</span></span>
- <span data-ttu-id="8998a-168">3 se a conexão com o daemon não puder ser estabelecida.</span><span class="sxs-lookup"><span data-stu-id="8998a-168">3 if the connection to the daemon cannot be established.</span></span>

## <a name="log-installation-issues"></a><span data-ttu-id="8998a-169">Problemas de instalação de log</span><span class="sxs-lookup"><span data-stu-id="8998a-169">Log installation issues</span></span>

 <span data-ttu-id="8998a-170">Para obter mais informações sobre como encontrar o log gerado automaticamente que é criado pelo instalador quando ocorre um [erro,](linux-resources.md#log-installation-issues)consulte Log installation issues .</span><span class="sxs-lookup"><span data-stu-id="8998a-170">For more information on how to find the automatically generated log that is created by the installer when an error occurs, see [Log installation issues](linux-resources.md#log-installation-issues).</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="8998a-171">Atualizações do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="8998a-171">Operating system upgrades</span></span>

<span data-ttu-id="8998a-172">Ao atualizar o sistema operacional para uma nova versão principal, primeiro você deve desinstalar o Defender para o Ponto de Extremidade no Linux, instalar a atualização e, finalmente, reconfigurar o Defender para Ponto de Extremidade no Linux em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8998a-172">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint on Linux, install the upgrade, and finally reconfigure Defender for Endpoint on Linux on your device.</span></span>

## <a name="uninstallation"></a><span data-ttu-id="8998a-173">Desinstalação</span><span class="sxs-lookup"><span data-stu-id="8998a-173">Uninstallation</span></span>

<span data-ttu-id="8998a-174">Criar um módulo *remove_mdatp* semelhante *ao install_mdatp* com o seguinte conteúdo em *init.pp*</span><span class="sxs-lookup"><span data-stu-id="8998a-174">Create a module *remove_mdatp* similar to *install_mdatp* with the following contents in *init.pp*</span></span> <span data-ttu-id="8998a-175">file:</span><span class="sxs-lookup"><span data-stu-id="8998a-175">file:</span></span>

```bash
class remove_mdatp {
    package { 'mdatp':
        ensure => 'purged',
    }
}
```
