---
title: Solucionar problemas de eventos ausentes ou alertas para o Microsoft Defender ATP para Linux
description: Solucionar problemas de eventos ausentes ou alertas no Microsoft Defender ATP para Linux.
keywords: microsoft, defender, atp, linux, eventos
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
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5981cb75b4c835390e27d902b5950e3c68305200
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687449"
---
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Solucionar problemas de eventos ausentes ou alertas para o Microsoft Defender para Ponto de Extremidade no Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade no Linux](microsoft-defender-endpoint-linux.md)

Este artigo fornece algumas etapas gerais para reduzir os eventos ou alertas ausentes no portal do centro [de segurança.](https://securitycenter.windows.com/)

Depois **que o Microsoft Defender for Endpoint** tiver sido instalado corretamente em um dispositivo, uma página de dispositivo _será_ gerada no portal. Você pode revisar todos os eventos gravados na guia linha do tempo na página do dispositivo ou na página de busca avançada. Esta seção soluciona os problemas em que alguns ou todos os eventos esperados estão ausentes.
Por exemplo, se todos os _eventos CreatedFile_ estão ausentes.

## <a name="missing-network-and-login-events"></a>Eventos de logon e rede ausentes

O Microsoft Defender para Ponto de Extremidade usou `audit` a estrutura do linux para controlar a atividade de rede e logon.

1. Certifique-se de que a estrutura de auditoria está funcionando.

    ```bash
    service auditd status
    ```

    saída esperada:

    ```output
    ● auditd.service - Security Auditing Service
    Loaded: loaded (/usr/lib/systemd/system/auditd.service; enabled; vendor preset: enabled)
    Active: active (running) since Mon 2020-12-21 10:48:02 IST; 2 weeks 0 days ago
        Docs: man:auditd(8)
            https://github.com/linux-audit/audit-documentation
    Process: 16689 ExecStartPost=/sbin/augenrules --load (code=exited, status=1/FAILURE)
    Process: 16665 ExecStart=/sbin/auditd (code=exited, status=0/SUCCESS)
    Main PID: 16666 (auditd)
        Tasks: 25
    CGroup: /system.slice/auditd.service
            ├─16666 /sbin/auditd
            ├─16668 /sbin/audispd
            ├─16670 /usr/sbin/sedispatch
            └─16671 /opt/microsoft/mdatp/sbin/mdatp_audisp_plugin -d
    ```

2. Se `auditd` estiver marcado como interrompido, inicie-o.

    ```bash
    service auditd start
    ```

**Em sistemas SLES,** a auditoria do SYSCALL em pode ser desabilitada por padrão e pode ser `auditd` contabilada por eventos ausentes.

1. Para validar se a auditoria do SYSCALL não está desabilitada, liste as regras de auditoria atuais:

    ```bash
    sudo auditctl -l
    ```

    se a linha a seguir estiver presente, remova-a ou edite-a para habilitar o Microsoft Defender para o Ponto de Extremidade a rastrear SYSCALLs específicos.

    ```output
    -a task, never
    ```

    as regras de auditoria estão localizadas em `/etc/audit/rules.d/audit.rules` .

## <a name="missing-file-events"></a>Eventos de arquivo ausentes

Os eventos de arquivo são coletados com `fanotify` a estrutura. Caso alguns ou todos os eventos de arquivo não sejam, certifique-se de que está habilitado no dispositivo e se o sistema de arquivos `fanotify` [tem suporte](microsoft-defender-endpoint-linux.md#system-requirements).

Listar os sistemas de arquivos no computador com:

```bash
df -Th
```
