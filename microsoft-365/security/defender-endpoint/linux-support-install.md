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
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-for-linux"></a>Solucionar problemas de instalação do Microsoft Defender para Ponto de Extremidade para Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="verify-if-installation-succeeded"></a>Verificar se a instalação foi bem-sucedida

Um erro na instalação pode ou não resultar em uma mensagem de erro significativa pelo gerente do pacote. Para verificar se a instalação foi bem-sucedida, obtenha e verifique os logs de instalação usando:

 ```bash
 sudo journalctl | grep 'microsoft-mdatp'  > installation.log
```

```bash
 grep 'postinstall end' installation.log
```

```Output
 microsoft-mdatp-installer[102243]: postinstall end [2020-03-26 07:04:43OURCE +0000] 102216
 ```

Uma saída do comando anterior com data e hora corretas de instalação indica sucesso.

Verifique também [a configuração do](linux-install-manually.md#client-configuration) cliente para verificar a saúde do produto e detectar o arquivo de texto EICAR.

## <a name="make-sure-you-have-the-correct-package"></a>Certifique-se de ter o pacote correto

Lembre-se de que o pacote que você está instalando está correspondendo à distribuição e à versão do host.

| pacote                       | distribution                             |
|-------------------------------|------------------------------------------|
| mdatp-rhel8. Linux.x86_64.rpm  | Oracle, RHEL e CentOS 8.x              |
| mdatp-sles12. Linux.x86_64.rpm | SuSE Linux Enterprise Server 12.x        |
| mdatp-sles15. Linux.x86_64.rpm | SuSE Linux Enterprise Server 15.x        |
| mdatp. Linux.x86_64.rpm        | Oracle, RHEL e CentOS 7.x              |
| mdatp. Linux.x86_64.deb        | Debian e Ubuntu 16.04, 18.04 e 20.04 |

Para [implantação manual,](linux-install-manually.md)certifique-se de que a versão e o distro corretos foram escolhidos.

## <a name="installation-failed"></a>Falha na instalação

Verifique se o serviço mdatp está em execução:

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

## <a name="steps-to-troubleshoot-if-mdatp-service-isnt-running"></a>Etapas para solucionar problemas se o serviço mdatp não estiver em execução

1. Verifique se o usuário "mdatp" existe:

    ```bash
    id "mdatp"
    ```

    Se não houver saída, execute

    ```bash
    sudo useradd --system --no-create-home --user-group --shell /usr/sbin/nologin mdatp
    ```

2. Tente ativar e reiniciar o serviço usando:

    ```bash
    sudo systemctl enable mdatp
    ```

    ```bash
    sudo systemctl restart mdatp
    ```

3. Se mdatp.service não for encontrado ao executar o comando anterior, execute:

    ```bash
    sudo cp /opt/microsoft/mdatp/conf/mdatp.service <systemd_path>
    ```

    onde ```<systemd_path>``` é ```/lib/systemd/system``` para distribuições Ubuntu e Debian e ```/usr/lib/systemd/system``` para o Rhel, CentOS, Oracle e SLES.
   Em seguida, reprise a etapa 2.

4. Se as etapas acima não funcionarem, verifique se SELinux está instalado e no modo de imposição. Em caso afirmativo, tente defini-lo como permissivo (preferencialmente) ou modo desabilitado. Isso pode ser feito definindo o parâmetro como `SELINUX` "permissivo" ou "desabilitado" no `/etc/selinux/config` arquivo, seguido de reinicialização. Verifique a página man do selinux para obter mais detalhes.
Agora tente reiniciar o serviço mdatp usando a etapa 2. Reverter a alteração de configuração imediatamente, porém, por motivos de segurança depois de tentar e reiniciar.

5. Se `/opt` o diretório for um link simbólico, crie uma montagem de vinculação para `/opt/microsoft` .

6. Verifique se o daemon tem permissão executável.

    ```bash
    ls -l /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ```Output
    -rwxr-xr-x 2 root root 15502160 Mar  3 04:47 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    Se o daemon não tiver permissões executáveis, torná-lo executável usando:

    ```bash
    sudo chmod 0755 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    e repetir a etapa 2.

7. Verifique se o sistema de arquivos que contém o wdavdaemon não está montado com "noexec".

## <a name="if-mdatp-service-is-running-but-eicar-text-file-detection-doesnt-work"></a>Se o serviço mdatp estiver em execução, mas a detecção de arquivo de texto EICAR não funcionar

1. Verifique o tipo de sistema de arquivos usando:

    ```bash
    findmnt -T <path_of_EICAR_file>
    ```

    Atualmente, os sistemas de arquivos com suporte para atividades ao acessar estão [listados aqui](microsoft-defender-endpoint-linux.md#system-requirements). Todos os arquivos fora desses sistemas de arquivos não serão verificados.

## <a name="command-line-tool-mdatp-isnt-working"></a>A ferramenta de linha de comando "mdatp" não está funcionando

1. Se a execução da ferramenta de linha de `mdatp` comando der um `command not found` erro, execute o seguinte comando:

    ```bash
    sudo ln -sf /opt/microsoft/mdatp/sbin/wdavdaemonclient /usr/bin/mdatp
    ```

    e tente novamente.

    Se nenhuma das etapas acima ajudar, colete os logs de diagnóstico:

    ```bash
    sudo mdatp diagnostic create
    ```

    ```Output
    Diagnostic file created: <path to file>
    ```

    O caminho para um arquivo zip que contém os logs será exibido como uma saída. Entre em contato com nosso suporte ao cliente com esses logs.
