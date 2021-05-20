---
title: Symantec para o Microsoft Defender para Ponto de Extremidade - Fase 1, Preparação
description: Esta é a Fase 1, Preparar, de migrar da Symantec para o Microsoft Defender para o Ponto de Extremidade.
keywords: migração, Microsoft Defender para Ponto de Extremidade, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-symantecmigrate
ms.topic: article
ms.date: 05/14/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 7fe0eb8adc90c259d31f237082effc80c5e8622c
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537974"
---
# <a name="migrate-from-symantec---phase-1-prepare-for-your-migration"></a>Migrar da Symantec - Fase 1: Preparar-se para sua migração

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|![Fase 1: Preparar](images/phase-diagrams/prepare.png)<br/>Fase 1: Preparar |[![Fase 2: Configurar](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[Fase 2: Configurar](symantec-to-microsoft-defender-atp-setup.md) |[![Fase 3: Integrar](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[Fase 3: Integrar](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
|*Você está aqui!*| | |


**Bem-vindo à fase preparar [a migração da Symantec para o Defender para o Ponto de Extremidade.](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)** 

Essa fase de migração inclui as seguintes etapas:

1. [Atualize os dispositivos da sua organização.](#update-your-organizations-devices)

2. [Obter o Microsoft Defender para Ponto de Extremidade](#get-microsoft-defender-for-endpoint).

3. [Conceda acesso ao Central de Segurança do Microsoft Defender](#grant-access-to-the-microsoft-defender-security-center).

4. [Configurar configurações de proxy de dispositivo e conectividade com a Internet](#configure-device-proxy-and-internet-connectivity-settings)

## <a name="update-your-organizations-devices"></a>Atualizar os dispositivos da sua organização

Como prática prática, mantenha os dispositivos e pontos de extremidade da sua organização atualizados. Certifique-se de que sua solução antivírus e proteção de ponto de extremidade existentes está atualizada e que os sistemas operacionais e aplicativos que sua organização também tem as atualizações mais recentes. Fazer isso agora pode ajudar a evitar problemas mais tarde à medida que você migra para o Defender para o Ponto de Extremidade.

### <a name="make-sure-symantec-is-up-to-date"></a>Certifique-se de que a Symantec está atualizada

Mantenha sua solução de proteção de ponto de extremidade existente atualizada e certifique-se de que os dispositivos da sua organização tenham as atualizações de segurança mais recentes.

Precisa de ajuda? Consulte a documentação da Broadcom: Guia de instalação [e administração da Symantec Endpoint Protection](https://techdocs.broadcom.com/us/en/symantec-security-software/endpoint-security-and-management/endpoint-protection/all.html)

### <a name="make-sure-your-endpoints-are-up-to-date"></a>Certifique-se de que seus pontos de extremidade estão atualizados

Precisa de ajuda para atualizar os dispositivos da sua organização? Consulte os seguintes recursos:


|SISTEMA OPERACIONAL  |Recurso  |
|---------|---------|
|Windows     | [Microsoft Update](https://www.update.microsoft.com/)        |
|macOS     | [Como atualizar o software em seu Mac](https://support.apple.com/HT201541)         |
|iOS     | [Atualizar seu iPhone, iPad ou iPod touch](https://support.apple.com/HT204204)         |
|Android     | [Verifique & atualizar sua versão do Android](https://support.google.com/android/answer/7680439)        |
|Linux     | [Linux 101: atualizando seu sistema](https://www.linux.com/training-tutorials/linux-101-updating-your-system)        |


## <a name="get-microsoft-defender-for-endpoint"></a>Obter o Microsoft Defender para Ponto de Extremidade

Agora que você atualizou os dispositivos da sua organização, a próxima etapa é obter o Defender para o Ponto de Extremidade, atribuir licenças e garantir que o serviço seja provisionado.

1. Compre ou experimente o Defender para Ponto de Extremidade hoje. [Visite o Defender para o Ponto de Extremidade para iniciar uma avaliação gratuita ou solicitar uma citação](https://aka.ms/mdatp). 

2. Verifique se suas licenças estão provisionadas corretamente. [Verifique o estado da licença.](production-deployment.md#check-license-state)

3. Como administrador global ou administrador de segurança, configurar sua instância de nuvem dedicada do Defender para Ponto de Extremidade. Consulte [Configuração do Defender para Ponto de Extremidade: Configuração de locatário](production-deployment.md#tenant-configuration).

4. Se os pontos de extremidade (como dispositivos) em sua organização usarem um proxy para acessar a Internet, consulte [Defender for Endpoint setup: Network configuration](production-deployment.md#network-configuration).
 
Neste ponto, você está pronto para conceder acesso aos administradores de segurança e operadores de segurança que usarão o Central de Segurança do Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 

> [!NOTE]
> O Central de Segurança do Microsoft Defender às vezes é chamado de portal do Defender para Ponto de Extremidade. 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>Conceder acesso ao Central de Segurança do Microsoft Defender

A Central de Segurança do Microsoft Defender ( ) é onde você [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) acessa e configura recursos e recursos do Defender para Ponto de Extremidade. Para saber mais, confira [Visão geral do Central de Segurança do Microsoft Defender](use.md).

As permissões para o Central de Segurança do Microsoft Defender podem ser concedidas usando permissões básicas ou controle de acesso baseado em função (RBAC). Recomendamos o uso do RBAC para que você tenha controle mais granular sobre permissões.

1. Planeje as funções e permissões para seus administradores de segurança e operadores de segurança. Consulte [Controle de acesso baseado em função](prepare-deployment.md#role-based-access-control).

2. Configurar e configurar o RBAC. Recomendamos usar [o Intune](/mem/intune/fundamentals/what-is-intune) para configurar o RBAC, especialmente se sua organização estiver usando uma combinação de dispositivos Windows 10, macOS, iOS e Android. Consulte [configurando o RBAC usando o Intune](/mem/intune/fundamentals/role-based-access-control).

   Se sua organização exigir um método diferente do Intune, escolha uma das seguintes opções:

    - [Configuration Manager](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)

    - [Gerenciamento avançado de política de grupo](/microsoft-desktop-optimization-pack/agpm)

    - [Windows Centro de administração](/windows-server/manage/windows-admin-center/overview)

3. Conceda acesso ao Central de Segurança do Microsoft Defender. (Precisa de ajuda? Consulte [Gerenciar acesso ao portal usando RBAC](rbac.md)).

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Configurar configurações de proxy de dispositivo e conectividade com a Internet

Para habilitar a comunicação entre seus dispositivos e o Defender para Ponto de Extremidade, configure configurações de proxy e internet. A tabela a seguir inclui links para recursos que você pode usar para configurar suas configurações de proxy e internet para vários sistemas operacionais e recursos:

|Recursos  | Sistema operacional | Recursos |
|:----|:----|:---|
|[Detecção e](overview-endpoint-detection-response.md) resposta do ponto de extremidade (EDR) | [Windows 10](/windows/release-health/release-information/) <p> [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows Servidor 1803 ou posterior](/windows-server/get-started/whats-new-in-windows-server-1803)  |[Configurar configurações de proxy de máquina e conectividade com a Internet](configure-proxy-internet.md) |
|EDR | [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <p>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[Configurar configurações de conectividade de proxy e internet](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS: <p>11.3.1 (Big Sur)<p>10.15 (Catalina)<p>10.14 (Mojave) |[Defender para Ponto de Extremidade no macOS: conexões de rede](microsoft-defender-endpoint-mac.md#network-connections) |
|[Microsoft Defender Antivírus](microsoft-defender-antivirus-in-windows-10.md) |[Windows 10](/windows/release-health/release-information/)<p>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows Servidor 1803 ou posterior](/windows-server/get-started/whats-new-in-windows-server-1803)<p>[Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) |[Configurar e validar as conexões de rede do Microsoft Defender Antivírus](configure-network-connections-microsoft-defender-antivirus.md) |
|Antivírus |macOS: <p>11.3.1 (Big Sur)<p>10.15 (Catalina)<p>10.14 (Mojave)  |[Defender para Ponto de Extremidade no Mac: conexões de rede](microsoft-defender-endpoint-mac.md#network-connections) |
|Antivírus |Linux: <p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS ou LTS superior<p>SLES 12+<p>Debian 9+<p>Oracle Linux 7.2 |[Defender para Ponto de Extremidade no Linux: conexões de rede](microsoft-defender-endpoint-linux.md#network-connections)  |

## <a name="next-step"></a>Próxima etapa

**Parabéns**! Você concluiu **a fase Preparar** a [migração da Symantec para o Defender para o Ponto de Extremidade!](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)
- [Prossiga para configurar o Defender para o Ponto de Extremidade](symantec-to-microsoft-defender-atp-setup.md).
