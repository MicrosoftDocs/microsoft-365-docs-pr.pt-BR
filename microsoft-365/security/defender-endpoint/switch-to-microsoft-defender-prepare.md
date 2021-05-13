---
title: Alternar para o Microsoft Defender para Ponto de Extremidade - Preparar
description: Esta é a fase 1, Preparar, para migrar para o Microsoft Defender para o Ponto de Extremidade.
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
- m365solution-migratetomdatp
ms.topic: article
ms.custom: migrationguides
ms.date: 05/11/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 265f32f5a24b982933ac6a876b244b10802cdd60
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345807"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-1-prepare"></a>Alternar para o Microsoft Defender para o Ponto de Extremidade - Fase 1: Preparar

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| ![Fase 1: Preparar](images/phase-diagrams/prepare.png)<br/>Fase 1: Preparar | [![Fase 2: Configurar](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[Fase 2: Configurar](switch-to-microsoft-defender-setup.md) | [![Fase 3: Integrar](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[Fase 3: Integrar](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
|*Você está aqui!*| | |

**Bem-vindo à fase preparar [a mudança para o Microsoft Defender para o Ponto de Extremidade.](switch-to-microsoft-defender-migration.md#the-migration-process)** 

Essa fase de migração inclui as seguintes etapas:

1. [Obter e implantar atualizações nos dispositivos da sua organização](#get-and-deploy-updates-across-your-organizations-devices)

2. [Obter o Microsoft Defender para Ponto de Extremidade](#get-microsoft-defender-for-endpoint).

3. [Conceda acesso ao Central de Segurança do Microsoft Defender](#grant-access-to-the-microsoft-defender-security-center).

4. [Configure as configurações de proxy de dispositivo e conectividade com a Internet.](#configure-device-proxy-and-internet-connectivity-settings)

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>Obter e implantar atualizações nos dispositivos da sua organização

Como prática prática, mantenha os dispositivos e pontos de extremidade da sua organização atualizados. Certifique-se de que sua solução antivírus e proteção de ponto de extremidade existentes está atualizada e que os sistemas operacionais e aplicativos que sua organização também tem as atualizações mais recentes. Fazer isso agora pode ajudar a evitar problemas depois que você migrar para o Microsoft Defender para o Ponto de Extremidade e Microsoft Defender Antivírus.

### <a name="make-sure-your-existing-solution-is-up-to-date"></a>Certifique-se de que sua solução existente está atualizada

Mantenha sua solução de proteção de ponto de extremidade existente atualizada e certifique-se de que os dispositivos da sua organização tenham as atualizações de segurança mais recentes. 

Precisa de ajuda? Consulte a documentação do provedor de soluções.

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a>Certifique-se de que os dispositivos da sua organização estão atualizados

Precisa de ajuda para atualizar os dispositivos da sua organização? Consulte os seguintes recursos:

|SISTEMA OPERACIONAL | Recurso |
|:--|:--|
|Windows |[Microsoft Update](https://www.update.microsoft.com) |
|macOS | [Como atualizar o software em seu Mac](https://support.apple.com/HT201541)|
|iOS |[Atualizar seu iPhone, iPad ou iPod touch](https://support.apple.com/HT204204)|
|Android |[Verifique & atualizar sua versão do Android](https://support.google.com/android/answer/7680439) |
|Linux | [Linux 101: atualizando seu sistema](https://www.linux.com/training-tutorials/linux-101-updating-your-system) |

## <a name="get-microsoft-defender-for-endpoint"></a>Obter o Microsoft Defender para Ponto de Extremidade

Agora que você atualizou os dispositivos da sua organização, a próxima etapa é obter o Microsoft Defender para Ponto de Extremidade, atribuir licenças e garantir que o serviço seja provisionado.

1. Comprar ou experimentar o Microsoft Defender para Ponto de Extremidade hoje. [Inicie uma avaliação gratuita ou solicite uma citação](https://aka.ms/mdatp). 

2. Verifique se suas licenças estão provisionadas corretamente. [Verifique o estado da licença.](production-deployment.md#check-license-state)

3. Como administrador global ou administrador de segurança, configurar sua instância de nuvem dedicada do Microsoft Defender para Ponto de Extremidade. Consulte [Configuração do Microsoft Defender para Ponto de Extremidade: Configuração de locatário](production-deployment.md#tenant-configuration).

4. Se os pontos de extremidade (como dispositivos) em sua organização usarem um proxy para acessar a Internet, consulte [Microsoft Defender for Endpoint setup: Network configuration](production-deployment.md#network-configuration).
 
Neste ponto, você está pronto para conceder acesso aos administradores de segurança e operadores de segurança que usarão o Central de Segurança do Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 

> [!NOTE]
> O Central de Segurança do Microsoft Defender às vezes é conhecido como o portal do Microsoft Defender para Ponto de Extremidade e pode ser acessado em [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) . 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>Conceder acesso ao Central de Segurança do Microsoft Defender

A Central de Segurança do Microsoft Defender ( ) é onde você acessa e configura recursos e recursos [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) do Microsoft Defender para Ponto de Extremidade. Para saber mais, confira [Visão geral do Central de Segurança do Microsoft Defender](use.md).

As permissões para o Central de Segurança do Microsoft Defender podem ser concedidas usando permissões básicas ou controle de acesso baseado em função (RBAC). Recomendamos o uso do RBAC para que você tenha controle mais granular sobre permissões.

1. Planeje as funções e permissões para seus administradores de segurança e operadores de segurança. Consulte [Controle de acesso baseado em função](prepare-deployment.md#role-based-access-control).

2. Configurar e configurar o RBAC. Recomendamos usar [o Intune](/mem/intune/fundamentals/what-is-intune) para configurar o RBAC, especialmente se sua organização estiver usando uma combinação de dispositivos Windows 10, macOS, iOS e Android. Consulte [configurando o RBAC usando o Intune](/mem/intune/fundamentals/role-based-access-control).

    Se sua organização exigir um método diferente do Intune, escolha uma das seguintes opções:

    - [Configuration Manager](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)

    - [Gerenciamento avançado de política de grupo](/microsoft-desktop-optimization-pack/agpm)

    - [Windows Centro de administração](/windows-server/manage/windows-admin-center/overview)

3. Conceda acesso ao Central de Segurança do Microsoft Defender. (Precisa de ajuda? Consulte [Gerenciar acesso ao portal usando RBAC](rbac.md)).

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Configurar configurações de proxy de dispositivo e conectividade com a Internet

Para habilitar a comunicação entre seus dispositivos e o Microsoft Defender para Ponto de Extremidade, configure configurações de proxy e internet. A tabela a seguir inclui links para recursos que você pode usar para configurar suas configurações de proxy e internet para vários sistemas operacionais e recursos:

|Recursos  | Sistema operacional | Recursos |
|--|--|--|
|[Detecção e](overview-endpoint-detection-response.md) resposta do ponto de extremidade (EDR) |[Windows 10](/windows/release-health/release-information) <p>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows Servidor 1803 ou posterior](/windows-server/get-started/whats-new-in-windows-server-1803)  |[Configurar configurações de proxy de máquina e conectividade com a Internet](configure-proxy-internet.md) |
|EDR |[Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <p>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[Configurar configurações de conectividade de proxy e internet](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS: <br/>- 11.3.1 (Big Sur)<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)   |[Microsoft Defender para Ponto de Extremidade no macOS: Conexões de rede](microsoft-defender-endpoint-mac.md#network-connections)  |
|[Microsoft Defender Antivírus](microsoft-defender-antivirus-in-windows-10.md) |[Windows 10](/windows/release-health/release-information) <p>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows Servidor 1803 ou posterior](/windows-server/get-started/whats-new-in-windows-server-1803) <p>[Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) |[Configurar e validar as conexões de rede do Microsoft Defender Antivírus](configure-network-connections-microsoft-defender-antivirus.md)<br/> |
|Antivírus |macOS: <br/>- 11.3.1 (Big Sur)<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave) |[Microsoft Defender para Ponto de Extremidade no macOS: Conexões de rede](microsoft-defender-endpoint-mac.md#network-connections) |
|Antivírus |Linux: <br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS ou LTS superior<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Microsoft Defender para Ponto de Extremidade no Linux: conexões de rede](microsoft-defender-endpoint-linux.md#network-connections) |

## <a name="next-step"></a>Próxima etapa

**Parabéns**! Você concluiu **a fase Preparar** a mudança para o Microsoft Defender para o Ponto de [Extremidade](switch-to-microsoft-defender-migration.md#the-migration-process)!

- [Prossiga para configurar o Microsoft Defender para o Ponto de Extremidade](switch-to-microsoft-defender-setup.md).
