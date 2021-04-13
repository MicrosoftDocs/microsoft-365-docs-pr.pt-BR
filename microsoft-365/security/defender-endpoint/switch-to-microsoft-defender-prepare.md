---
title: Alternar para o Microsoft Defender para Ponto de Extremidade - Preparar
description: Esta é a fase 1, Preparar, para migrar para o Microsoft Defender para o Ponto de Extremidade.
keywords: migração, proteção avançada contra ameaças do Windows Defender, atp, edr
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
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: de0d5ca756cdd8fe6eaf82968d04d143a098269c
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688064"
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
3. [Conceda acesso ao Centro de Segurança do Microsoft Defender.](#grant-access-to-the-microsoft-defender-security-center)
4. [Configure as configurações de proxy de dispositivo e conectividade com a Internet.](#configure-device-proxy-and-internet-connectivity-settings)

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>Obter e implantar atualizações nos dispositivos da sua organização

Como prática prática, mantenha os dispositivos e pontos de extremidade da sua organização atualizados. Certifique-se de que sua solução antivírus e proteção de ponto de extremidade existentes está atualizada e que os sistemas operacionais e aplicativos que sua organização também tem as atualizações mais recentes. Fazer isso agora pode ajudar a evitar problemas mais tarde à medida que você migra para o Microsoft Defender para o Ponto de Extremidade e o Microsoft Defender Antivírus.

### <a name="make-sure-your-existing-solution-is-up-to-date"></a>Certifique-se de que sua solução existente está atualizada

Mantenha sua solução de proteção de ponto de extremidade existente atualizada e certifique-se de que os dispositivos da sua organização tenham as atualizações de segurança mais recentes. 

Precisa de ajuda? Consulte a documentação do provedor de soluções.

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a>Certifique-se de que os dispositivos da sua organização estão atualizados

Precisa de ajuda para atualizar os dispositivos da sua organização? Consulte os seguintes recursos:

|SISTEMA OPERACIONAL | Resource |
|:--|:--|
|Windows |[Microsoft Update](https://www.update.microsoft.com) |
|macOS | [Como atualizar o software em seu Mac](https://support.apple.com/HT201541)|
|iOS |[Atualizar seu iPhone, iPad ou iPod touch](https://support.apple.com/HT204204)|
|Android |[Verifique & atualizar sua versão do Android](https://support.google.com/android/answer/7680439) |
|Linux | [Linux 101: atualizando seu sistema](https://www.linux.com/training-tutorials/linux-101-updating-your-system) |

## <a name="get-microsoft-defender-for-endpoint"></a>Obter o Microsoft Defender para Ponto de Extremidade

Agora que você atualizou os dispositivos da sua organização, a próxima etapa é obter o Microsoft Defender para Ponto de Extremidade, atribuir licenças e garantir que o serviço seja provisionado.

1. Comprar ou experimentar o Microsoft Defender para Ponto de Extremidade hoje. [Inicie uma avaliação gratuita ou solicite uma citação](https://aka.ms/mdatp). 
2. Verifique se suas licenças estão provisionadas corretamente. [Verifique o estado da licença.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#check-license-state)
3. Como administrador global ou administrador de segurança, configurar sua instância de nuvem dedicada do Microsoft Defender para Ponto de Extremidade. Consulte [Configuração do Microsoft Defender para Ponto de Extremidade: Configuração de locatário](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#tenant-configuration).
4. Se os pontos de extremidade (como dispositivos) em sua organização usarem um proxy para acessar a Internet, consulte [Microsoft Defender for Endpoint setup: Network configuration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#network-configuration).
 
Neste ponto, você está pronto para conceder acesso aos administradores de segurança e operadores de segurança que usarão o Centro de Segurança do Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 

> [!NOTE]
> O Centro de Segurança do Microsoft Defender às vezes é conhecido como o portal do Microsoft Defender para Ponto de Extremidade e pode ser acessado em [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) . 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>Conceder acesso ao Centro de Segurança do Microsoft Defender

O Centro de Segurança do Microsoft Defender ( ) é onde você acessa e configura recursos e [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) recursos do Microsoft Defender para o Ponto de Extremidade. Para saber mais, confira [Visão geral do Centro de Segurança do Microsoft Defender.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

As permissões para o Centro de Segurança do Microsoft Defender podem ser concedidas usando permissões básicas ou controle de acesso baseado em função (RBAC). Recomendamos o uso do RBAC para que você tenha controle mais granular sobre permissões.

1. Planeje as funções e permissões para seus administradores de segurança e operadores de segurança. Consulte [Controle de acesso baseado em função](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/prepare-deployment#role-based-access-control).
2. Configurar e configurar o RBAC. Recomendamos usar [o Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) para configurar o RBAC, especialmente se sua organização estiver usando uma combinação de dispositivos Windows 10, macOS, iOS e Android. Consulte [configurando o RBAC usando o Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).
    Se sua organização exigir um método diferente do Intune, escolha uma das seguintes opções:
    - [Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [Gerenciamento avançado de política de grupo](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm)
    - [Windows Admin Center](https://docs.microsoft.com/windows-server/manage/windows-admin-center/overview)
3. Conceda acesso ao Centro de Segurança do Microsoft Defender. (Precisa de ajuda? Consulte [Gerenciar acesso ao portal usando RBAC](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)).

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Configurar configurações de proxy de dispositivo e conectividade com a Internet

Para habilitar a comunicação entre seus dispositivos e o Microsoft Defender para Ponto de Extremidade, configure configurações de proxy e internet. A tabela a seguir inclui links para recursos que você pode usar para configurar suas configurações de proxy e internet para vários sistemas operacionais e recursos:

|Recursos  | Sistema operacional | Recursos |
|--|--|--|
|[Detecção e resposta do ponto de extremidade](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 ou posterior](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)  |[Configurar configurações de proxy de máquina e conectividade com a Internet](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet) |
|EDR |- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/>- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows 7 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[Configurar configurações de conectividade de proxy e internet](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS: <br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave) <br/>- 10,13 (High Sierra)  |[Microsoft Defender para Ponto de Extremidade no macOS: Conexões de rede](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|[Microsoft Defender Antivírus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 ou posterior](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) <br/>- [Windows Server 2016](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-2016) |[Configurar e validar as conexões de rede do Microsoft Defender Antivírus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)<br/> |
|Antivírus |macOS: <br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave) <br/>- 10,13 (High Sierra) |[Microsoft Defender para Ponto de Extremidade no macOS: Conexões de rede](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|Antivírus |Linux: <br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS ou LTS superior<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Microsoft Defender para Ponto de Extremidade no Linux: conexões de rede](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux#network-connections) |

## <a name="next-step"></a>Próxima etapa

**Parabéns**! Você concluiu **a fase Preparar** a mudança para o Microsoft Defender para o Ponto de [Extremidade](switch-to-microsoft-defender-migration.md#the-migration-process)!

- [Prossiga para configurar o Microsoft Defender para o Ponto de Extremidade](switch-to-microsoft-defender-setup.md).
