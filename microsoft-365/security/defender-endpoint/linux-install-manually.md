---
title: Implantar o Microsoft Defender para Ponto de Extremidade no Linux manualmente
ms.reviewer: ''
description: Descreve como implantar o Microsoft Defender para Ponto de Extremidade no Linux manualmente a partir da linha de comando.
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
ms.openlocfilehash: c13138f3d80a95dbda3a899507f662c081831d94
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259674"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-manually"></a>Implantar o Microsoft Defender para Ponto de Extremidade no Linux manualmente

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Este artigo descreve como implantar o Microsoft Defender para Ponto de Extremidade no Linux manualmente. Uma implantação bem-sucedida requer a conclusão de todas as seguintes tarefas:

- [Implantar o Microsoft Defender para Ponto de Extremidade no Linux manualmente](#deploy-microsoft-defender-for-endpoint-on-linux-manually)
  - [Pré-requisitos e requisitos do sistema](#prerequisites-and-system-requirements)
  - [Configurar o repositório de software Linux](#configure-the-linux-software-repository)
    - [RHEL e variantes (CentOS e Oracle Linux)](#rhel-and-variants-centos-and-oracle-linux)
    - [SLES e variantes](#sles-and-variants)
    - [Sistemas Ubuntu e Debian](#ubuntu-and-debian-systems)
  - [Instalação do aplicativo](#application-installation)
  - [Baixar o pacote de integração](#download-the-onboarding-package)
  - [Configuração do cliente](#client-configuration)
  - [Script do instalador](#installer-script)
  - [Problemas de instalação de log](#log-installation-issues)
  - [Atualizações do sistema operacional](#operating-system-upgrades)
  - [Desinstalação](#uninstallation)

## <a name="prerequisites-and-system-requirements"></a>Pré-requisitos e requisitos do sistema

Antes de começar, consulte [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md) para obter uma descrição dos pré-requisitos e requisitos do sistema para a versão de software atual.

## <a name="configure-the-linux-software-repository"></a>Configurar o repositório de software Linux

O Defender para Ponto de Extremidade no Linux pode ser implantado de um dos seguintes canais (denotado abaixo como *[canal]*): *insiders-fast,* *insiders-slow* ou *prod*. Cada um desses canais corresponde a um repositório de software Linux. Instruções para configurar seu dispositivo para usar um desses repositórios são fornecidas abaixo.

A escolha do canal determina o tipo e a frequência de atualizações oferecidas ao seu dispositivo. Os *dispositivos em insiders-fast* são os primeiros a receber atualizações e novos recursos, seguidos posteriormente por *insiders-slow* e por *último por prod*.

Para visualizar novos recursos e fornecer comentários antecipados, é recomendável configurar alguns dispositivos em sua empresa para usar *insiders-fast* ou *insiders-slow*.

> [!WARNING]
> Alternar o canal após a instalação inicial exige que o produto seja reinstalado. Para alternar o canal do produto: desinstale o pacote existente, configure novamente seu dispositivo para usar o novo canal e siga as etapas deste documento para instalar o pacote no novo local.

### <a name="rhel-and-variants-centos-and-oracle-linux"></a>RHEL e variantes (CentOS e Oracle Linux)

- Instale `yum-utils` se ainda não estiver instalado:

    ```bash
    sudo yum install yum-utils
    ```

- Observe sua distribuição e versão e identifique a entrada mais próxima (por principal, então secundária) para ela em `https://packages.microsoft.com/config/` . Por exemplo, o RHEL 7.9 está mais próximo de 7,4 do que 8.

    Nos comandos a seguir, substitua *[distro]* e *[versão]* pela informação que você identificou:

    > [!NOTE]
    > No caso do Oracle Linux, substitua *[distro]* por "remos".

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    Por exemplo, se você estiver executando o CentOS 7 e quiser implantar o Defender para Ponto de Extremidade no Linux a partir *do canal prod:*

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/prod.repo
    ```

    Ou se você quiser explorar novos recursos em dispositivos selecionados, talvez queira implantar o MDE para Linux para *canal interno rápido:*

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/insiders-fast.repo
    ```

- Instale a chave pública do Microsoft GPG:

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

- Baixe e faça uso de todos os metadados dos repositórios yum atualmente habilitados:

    ```bash
    yum makecache
    ```

### <a name="sles-and-variants"></a>SLES e variantes

- Observe sua distribuição e versão e identifique a entrada mais próxima(por principal, então secundária) para ela em `https://packages.microsoft.com/config/` .

    Nos comandos a seguir, substitua *[distro]* e *[version]* com as informações identificadas:

    ```bash
    sudo zypper addrepo -c -f -n microsoft-[channel] https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    Por exemplo, se você estiver executando o SLES 12 e quiser implantar o MDE para Linux a partir *do canal prod:*

    ```bash
    sudo zypper addrepo -c -f -n microsoft-prod https://packages.microsoft.com/config/sles/12/prod.repo
    ```

- Instale a chave pública do Microsoft GPG:

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

### <a name="ubuntu-and-debian-systems"></a>Sistemas Ubuntu e Debian

- Instale `curl` se ainda não estiver instalado:

    ```bash
    sudo apt-get install curl
    ```

- Instale `libplist-utils` se ainda não estiver instalado:

    ```bash
    sudo apt-get install libplist-utils
    ```

- Observe sua distribuição e versão e identifique a entrada mais próxima (por principal, então secundária) para ela em `https://packages.microsoft.com/config` .

    No comando abaixo, substitua *[distro]* e *[version]* pela informação que você identificou:

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/[distro]/[version]/[channel].list
    ```

    Por exemplo, se você estiver executando o Ubuntu 18.04 e quiser implantar o MDE para Linux a partir *do canal prod:*

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/ubuntu/18.04/prod.list
    ```

- Instalar a configuração do repositório:

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-[channel].list
    ```
    Por exemplo, se você escolher *canal prod:*

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-prod.list
    ```

- Instale o `gpg` pacote se ainda não estiver instalado:

    ```bash
    sudo apt-get install gpg
    ```

  Se `gpg` não estiver disponível, instale `gnupg` .

- Instale a chave pública do Microsoft GPG:

    ```bash
    curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
    ```

- Instale o driver https se ele ainda não estiver presente:

    ```bash
    sudo apt-get install apt-transport-https
    ```

- Atualize os metadados do repositório:

    ```bash
    sudo apt-get update
    ```

## <a name="application-installation"></a>Instalação do aplicativo

- RHEL e variantes (CentOS e Oracle Linux):

    ```bash
    sudo yum install mdatp
    ```

    Se você tiver vários repositórios da Microsoft configurados em seu dispositivo, poderá ser específico sobre de qual repositório instalar o pacote. O exemplo a seguir mostra como instalar o pacote do canal se você também tiver o canal `production` de repositório configurado neste `insiders-fast` dispositivo. Essa situação pode acontecer se você estiver usando vários produtos Microsoft em seu dispositivo. Dependendo da distribuição e da versão do seu servidor, o alias do repositório pode ser diferente do do exemplo a seguir.

    ```bash
    # list all repositories
    yum repolist
    ```
    ```Output
    ...
    packages-microsoft-com-prod               packages-microsoft-com-prod        316
    packages-microsoft-com-prod-insiders-fast packages-microsoft-com-prod-ins      2
    ...
    ```
    ```bash
    # install the package from the production repository
    sudo yum --enablerepo=packages-microsoft-com-prod install mdatp
    ```

- SLES e variantes:

    ```bash
    sudo zypper install mdatp
    ```

    Se você tiver vários repositórios da Microsoft configurados em seu dispositivo, poderá ser específico sobre de qual repositório instalar o pacote. O exemplo a seguir mostra como instalar o pacote do canal se você também tiver o canal `production` de repositório configurado neste `insiders-fast` dispositivo. Essa situação pode acontecer se você estiver usando vários produtos Microsoft em seu dispositivo.

    ```bash
    zypper repos
    ```

    ```Output
    ...
    #  | Alias | Name | ...
    XX | packages-microsoft-com-insiders-fast | microsoft-insiders-fast | ...
    XX | packages-microsoft-com-prod | microsoft-prod | ...
    ...
    ```
    ```bash
    sudo zypper install packages-microsoft-com-prod:mdatp
    ```

- Sistema Ubuntu e Debian:

    ```bash
    sudo apt-get install mdatp
    ```

    Se você tiver vários repositórios da Microsoft configurados em seu dispositivo, poderá ser específico sobre de qual repositório instalar o pacote. O exemplo a seguir mostra como instalar o pacote do canal se você também tiver o canal `production` de repositório configurado neste `insiders-fast` dispositivo. Essa situação pode acontecer se você estiver usando vários produtos Microsoft em seu dispositivo.

    ```bash
    cat /etc/apt/sources.list.d/*
    ```
    ```Output
    deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/ubuntu/18.04/prod insiders-fast main
    deb [arch=amd64] https://packages.microsoft.com/ubuntu/18.04/prod bionic main
    ```
    ```bash
    sudo apt -t bionic install mdatp
    ```

## <a name="download-the-onboarding-package"></a>Baixar o pacote de integração

Baixe o pacote de integração Central de Segurança do Microsoft Defender:

1. Em Central de Segurança do Microsoft Defender, vá para Configurações > Gerenciamento de **Dispositivos > Integração**.
2. No primeiro menu suspenso, selecione **Servidor Linux como** o sistema operacional. No segundo menu suspenso, selecione Script Local (para até **10 dispositivos)** como o método de implantação.
3. Selecione **Baixar pacote de integração**. Salve o arquivo como WindowsDefenderATPOnboardingPackage.zip.

    ![Central de Segurança do Microsoft Defender captura de tela](images/atp-portal-onboarding-linux.png)

4. Em um prompt de comando, verifique se você tem o arquivo.
    Extraia o conteúdo do arquivo morto:

    ```bash
    ls -l
    ```

    ```Output
    total 8
    -rw-r--r-- 1 test  staff  5752 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```

    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: MicrosoftDefenderATPOnboardingLinuxServer.py
    ```


## <a name="client-configuration"></a>Configuração do cliente

1. Copie MicrosoftDefenderATPOnboardingLinuxServer.py para o dispositivo de destino.

    Inicialmente, o dispositivo cliente não está associado a uma organização. Observe que o *atributo orgId* está em branco:

    ```bash
    mdatp health --field org_id
    ```

2. Execute MicrosoftDefenderATPOnboardingLinuxServer.py e observe que, para executar este comando, você deve ter `python` instalado no dispositivo:

    ```bash
    python MicrosoftDefenderATPOnboardingLinuxServer.py
    ```

3. Verifique se o dispositivo agora está associado à sua organização e relata um identificador de organização válido:

    ```bash
    mdatp health --field org_id
    ```

4. Alguns minutos depois de concluir a instalação, você pode ver o status executando o comando a seguir. Um valor de retorno `1` de notas de que o produto está funcionando conforme o esperado:

    ```bash
    mdatp health --field healthy
    ```

    > [!IMPORTANT]
    > Quando o produto é iniciado pela primeira vez, ele baixa as definições antimalware mais recentes. Dependendo da conexão com a Internet, isso pode levar até alguns minutos. Durante esse tempo, o comando acima retorna um valor de `false` . Você pode verificar o status da atualização de definição usando o seguinte comando:
    > ```bash
    > mdatp health --field definitions_status
    > ```
    > Observe que você também pode precisar configurar um proxy após concluir a instalação inicial. Consulte [Configure Defender for Endpoint on Linux for static proxy discovery: Post-installation configuration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration#post-installation-configuration).

5. Execute um teste de detecção para verificar se o dispositivo está corretamente conectado e relatando ao serviço. Execute as seguintes etapas no dispositivo recém-integrado:

    - Verifique se a proteção em tempo real está habilitada (denotada por um resultado da execução `1` do seguinte comando):

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    - Abra uma janela de Terminal. Copie e execute o seguinte comando:

        ``` bash
        curl -o /tmp/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    - O arquivo deve ter sido colocado em quarentena pelo Defender para Ponto de Extremidade no Linux. Use o seguinte comando para listar todas as ameaças detectadas:

        ```bash
        mdatp threat list
        ```

## <a name="installer-script"></a>Script do instalador

Como alternativa, você pode usar um script de bash do [instalador automatizado](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh) fornecido em nosso [repositório GitHub público.](https://github.com/microsoft/mdatp-xplat/)
O script identifica a distribuição e a versão e configura o dispositivo para puxar o pacote mais recente e instalá-lo.
Você também pode fazer a integração com um script fornecido.

```bash
❯ ./mde_installer.sh --help
usage: basename ./mde_installer.sh [OPTIONS]
Options:
-c|--channel      specify the channel from which you want to install. Default: insiders-fast
-i|--install      install the product
-r|--remove       remove the product
-u|--upgrade      upgrade the existing product
-o|--onboard      onboard/offboard the product with <onboarding_script>
-p|--passive-mode set EPP to passive mode
-t|--tag          set a tag by declaring <name> and <value>. ex: -t GROUP Coders
-m|--min_req      enforce minimum requirements
-w|--clean        remove repo from package manager for a specific channel
-v|--version      print out script version
-h|--help         display help
```

Leia mais [aqui](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation).

## <a name="log-installation-issues"></a>Problemas de instalação de log

Consulte [Log installation issues](linux-resources.md#log-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.

## <a name="operating-system-upgrades"></a>Atualizações do sistema operacional

Ao atualizar o sistema operacional para uma nova versão principal, primeiro você deve desinstalar o Defender para o Ponto de Extremidade no Linux, instalar a atualização e, finalmente, reconfigurar o Defender para Ponto de Extremidade no Linux em seu dispositivo.

## <a name="how-to-migrate-from-insiders-fast-to-production-channel"></a>Como migrar do Insiders-Fast para o canal de produção

1. Desinstale a versão "Insiders-Fast channel" do MDE para Linux.

    ``
    sudo yum remove mdatp
    ``

1. Desabilitar o MDE para linux Insiders-Fast repo  ``
    sudo yum repolist
    ``

    > [!NOTE]
    > A saída deve mostrar "packages-microsoft-com-fast-prod".

    ``
    sudo yum-config-manager --disable packages-microsoft-com-fast-prod
    ``
1. Reimplantar o MDE para Linux usando o "canal de produção".


## <a name="uninstallation"></a>Desinstalação

Consulte [Desinstalar](linux-resources.md#uninstall) para obter detalhes sobre como remover o Defender for Endpoint no Linux de dispositivos cliente.
