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
ms.openlocfilehash: e489d5bece292065ad2e82a7eb9011747733b4f6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053771"
---
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="9975a-104">Solucionar problemas de eventos ausentes ou alertas para o Microsoft Defender para Endpoint para Linux</span><span class="sxs-lookup"><span data-stu-id="9975a-104">Troubleshoot missing events or alerts issues for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9975a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="9975a-105">**Applies to:**</span></span>

- [<span data-ttu-id="9975a-106">Microsoft Defender para Ponto de Extremidade para Linux</span><span class="sxs-lookup"><span data-stu-id="9975a-106">Microsoft Defender for Endpoint for Linux</span></span>](microsoft-defender-endpoint-linux.md)

<span data-ttu-id="9975a-107">Este artigo fornece algumas etapas gerais para reduzir os eventos ou alertas ausentes no portal do centro [de segurança.](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="9975a-107">This article provides some general steps to mitigate missing events or alerts in the [security center](https://securitycenter.windows.com/) portal.</span></span>

<span data-ttu-id="9975a-108">Depois **que o Microsoft Defender for Endpoint** tiver sido instalado corretamente em um dispositivo, uma página de dispositivo _será_ gerada no portal.</span><span class="sxs-lookup"><span data-stu-id="9975a-108">Once **Microsoft Defender for Endpoint** has been installed properly on a device, a _device page_ will be generated in the portal.</span></span> <span data-ttu-id="9975a-109">Você pode revisar todos os eventos gravados na guia linha do tempo na página do dispositivo ou na página de busca avançada.</span><span class="sxs-lookup"><span data-stu-id="9975a-109">You can review all recorded events in the timeline tab in the device page, or in advanced hunting page.</span></span> <span data-ttu-id="9975a-110">Esta seção soluciona os problemas em que alguns ou todos os eventos esperados estão ausentes.</span><span class="sxs-lookup"><span data-stu-id="9975a-110">This section troubleshoots the case of some or all expected events are missing.</span></span>
<span data-ttu-id="9975a-111">Por exemplo, se todos os _eventos CreatedFile_ estão ausentes.</span><span class="sxs-lookup"><span data-stu-id="9975a-111">For instance, if all _CreatedFile_ events are missing.</span></span>

## <a name="missing-network-and-login-events"></a><span data-ttu-id="9975a-112">Eventos de logon e rede ausentes</span><span class="sxs-lookup"><span data-stu-id="9975a-112">Missing network and login events</span></span>

<span data-ttu-id="9975a-113">O Microsoft Defender para Ponto de Extremidade usou `audit` a estrutura do linux para controlar a atividade de rede e logon.</span><span class="sxs-lookup"><span data-stu-id="9975a-113">Microsoft Defender for Endpoint utilized `audit` framework from linux to track network and login activity.</span></span>

1. <span data-ttu-id="9975a-114">Certifique-se de que a estrutura de auditoria está funcionando.</span><span class="sxs-lookup"><span data-stu-id="9975a-114">Make sure audit framework is working.</span></span>

    ```bash
    service auditd status
    ```

    <span data-ttu-id="9975a-115">saída esperada:</span><span class="sxs-lookup"><span data-stu-id="9975a-115">expected output:</span></span>

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

2. <span data-ttu-id="9975a-116">Se `auditd` estiver marcado como interrompido, inicie-o.</span><span class="sxs-lookup"><span data-stu-id="9975a-116">If `auditd` is marked as stopped, start it.</span></span>

    ```bash
    service auditd start
    ```

<span data-ttu-id="9975a-117">**Em sistemas SLES,** a auditoria do SYSCALL em pode ser desabilitada por padrão e pode ser `auditd` contabilada por eventos ausentes.</span><span class="sxs-lookup"><span data-stu-id="9975a-117">**On SLES** systems, SYSCALL auditing in `auditd` might be disabled by default and can be accounted for missing events.</span></span>

1. <span data-ttu-id="9975a-118">Para validar se a auditoria do SYSCALL não está desabilitada, liste as regras de auditoria atuais:</span><span class="sxs-lookup"><span data-stu-id="9975a-118">To validate that SYSCALL auditing is not disabled, list the current audit rules:</span></span>

    ```bash
    sudo auditctl -l
    ```

    <span data-ttu-id="9975a-119">se a linha a seguir estiver presente, remova-a ou edite-a para habilitar o Microsoft Defender para o Ponto de Extremidade a rastrear SYSCALLs específicos.</span><span class="sxs-lookup"><span data-stu-id="9975a-119">if the following line is present, remove it or edit it to enable Microsoft Defender for Endpoint to track specific SYSCALLs.</span></span>

    ```output
    -a task, never
    ```

    <span data-ttu-id="9975a-120">as regras de auditoria estão localizadas em `/etc/audit/rules.d/audit.rules` .</span><span class="sxs-lookup"><span data-stu-id="9975a-120">audit rules are located at `/etc/audit/rules.d/audit.rules`.</span></span>

## <a name="missing-file-events"></a><span data-ttu-id="9975a-121">Eventos de arquivo ausentes</span><span class="sxs-lookup"><span data-stu-id="9975a-121">Missing file events</span></span>

<span data-ttu-id="9975a-122">Os eventos de arquivo são coletados com `fanotify` a estrutura.</span><span class="sxs-lookup"><span data-stu-id="9975a-122">File events are collected with `fanotify` framework.</span></span> <span data-ttu-id="9975a-123">Caso alguns ou todos os eventos de arquivo não sejam, certifique-se de que está habilitado no dispositivo e se o sistema de arquivos `fanotify` [tem suporte](microsoft-defender-endpoint-linux.md#system-requirements).</span><span class="sxs-lookup"><span data-stu-id="9975a-123">In case some or all file events are missing, make sure `fanotify` is enabled on the device and that the file system is [supported](microsoft-defender-endpoint-linux.md#system-requirements).</span></span>

<span data-ttu-id="9975a-124">Listar os sistemas de arquivos no computador com:</span><span class="sxs-lookup"><span data-stu-id="9975a-124">List the filesystems on the machine with:</span></span>

```bash
df -Th
```
