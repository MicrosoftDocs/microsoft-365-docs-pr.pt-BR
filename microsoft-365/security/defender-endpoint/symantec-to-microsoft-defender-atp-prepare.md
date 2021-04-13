---
title: Symantec para o Microsoft Defender para Ponto de Extremidade - Fase 1, Preparação
description: Esta é a Fase 1, Preparar, de migrar da Symantec para o Microsoft Defender para o Ponto de Extremidade.
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
- m365solution-symantecmigrate
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 8c8f91448415bc1e9490706ee23bd8cae7f51a63
ms.sourcegitcommit: 72ae1b49e7a3d3199272fcb4c39f5daec0d66f1a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51698239"
---
# <a name="migrate-from-symantec---phase-1-prepare-for-your-migration"></a>Migrar da Symantec - Fase 1: Preparar-se para sua migração

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|![Fase 1: Preparar](images/phase-diagrams/prepare.png)<br/>Fase 1: Preparar |[![Fase 2: Configurar](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[Fase 2: Configurar](symantec-to-microsoft-defender-atp-setup.md) |[![Fase 3: Integrar](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[Fase 3: Integrar](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
|*Você está aqui!*| | |


**Bem-vindo à fase preparar [a migração da Symantec para o Microsoft Defender para o Ponto de Extremidade.](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)** 

Essa fase de migração inclui as seguintes etapas:
1. [Obter o Microsoft Defender para Ponto de Extremidade](#get-microsoft-defender-for-endpoint).
2. [Conceda acesso ao Centro de Segurança do Microsoft Defender.](#grant-access-to-the-microsoft-defender-security-center)
3. [Configure as configurações de proxy de dispositivo e conectividade com a Internet.](#configure-device-proxy-and-internet-connectivity-settings)

## <a name="get-microsoft-defender-for-endpoint"></a>Obter o Microsoft Defender para Ponto de Extremidade

Para começar, você deve ter o Microsoft Defender para Ponto de Extremidade, com licenças atribuídas e provisionadas.

1. Comprar ou experimentar o Microsoft Defender para Ponto de Extremidade hoje. [Visite o Microsoft Defender for Endpoint para iniciar uma avaliação gratuita ou solicitar uma citação.](https://aka.ms/mdatp) 
2. Verifique se suas licenças estão provisionadas corretamente. [Verifique o estado da licença.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#check-license-state)
3. Como administrador global ou administrador de segurança, configurar sua instância de nuvem dedicada do Microsoft Defender para Ponto de Extremidade. Consulte [Configuração do Microsoft Defender para Ponto de Extremidade: Configuração de locatário](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#tenant-configuration).
4. Se os pontos de extremidade (como dispositivos) em sua organização usarem um proxy para acessar a Internet, consulte [Microsoft Defender for Endpoint setup: Network configuration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#network-configuration).
 
Neste ponto, você está pronto para conceder acesso aos administradores de segurança e operadores de segurança que usarão o Centro de Segurança do Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 

> [!NOTE]
> O Centro de Segurança do Microsoft Defender às vezes é conhecido como o portal do Microsoft Defender para Ponto de Extremidade. 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>Conceder acesso ao Centro de Segurança do Microsoft Defender

O Centro de Segurança do Microsoft Defender ( ) é onde você acessa e configura recursos e [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) recursos do Microsoft Defender para o Ponto de Extremidade. Para saber mais, confira [Visão geral do Centro de Segurança do Microsoft Defender.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

As permissões para o Centro de Segurança do Microsoft Defender podem ser concedidas usando permissões básicas ou controle de acesso baseado em função (RBAC). Recomendamos o uso do RBAC para que você tenha controle mais granular sobre permissões.

1. Planeje as funções e permissões para seus administradores de segurança e operadores de segurança. Consulte [Controle de acesso baseado em função](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/prepare-deployment#role-based-access-control).
2. Configurar e configurar o RBAC. Recomendamos usar [o Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) para configurar o RBAC, especialmente se sua organização estiver usando uma combinação de dispositivos Windows 10, macOS, iOS e Android. Consulte [configurando o RBAC usando o Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).<br/>
   Se sua organização exigir um método diferente do Intune, escolha uma das seguintes opções:
    - [Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [Gerenciamento avançado de política de grupo](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm)
    - [Windows Admin Center](https://docs.microsoft.com/windows-server/manage/windows-admin-center/overview)
3. Conceda acesso ao Centro de Segurança do Microsoft Defender. (Precisa de ajuda? Consulte [Gerenciar acesso ao portal usando RBAC](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)).

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Configurar configurações de proxy de dispositivo e conectividade com a Internet

Para habilitar a comunicação entre seus dispositivos e o Microsoft Defender para Ponto de Extremidade, configure configurações de proxy e internet. A tabela a seguir inclui links para recursos que você pode usar para configurar suas configurações de proxy e internet para vários sistemas operacionais e recursos:

|Recursos  | Sistema operacional | Recursos |
|:----|:----|:---|
|[Detecção e resposta do ponto de extremidade](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information/) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 ou posterior](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)  |[Configurar configurações de proxy de máquina e conectividade com a Internet](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet) |
|EDR |- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/>- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows 7 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[Configurar configurações de conectividade de proxy e internet](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS: <br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave) <br/>- 10,13 (High Sierra)  |[Microsoft Defender para Ponto de Extremidade no macOS: Conexões de rede](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|[Microsoft Defender Antivírus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information/) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 ou posterior](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) <br/>- [Windows Server 2016](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-2016) |[Configurar e validar as conexões de rede do Microsoft Defender Antivírus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)<br/> |
|Antivírus |macOS: <br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave) <br/>- 10,13 (High Sierra) |[Microsoft Defender para Ponto de Extremidade no Mac: conexões de rede](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|Antivírus |Linux: <br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS ou LTS superior<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Microsoft Defender para Ponto de Extremidade no Linux: conexões de rede](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux#network-connections)  |

## <a name="next-step"></a>Próxima etapa

**Parabéns**! Você concluiu **a fase Preparar** a migração da [Symantec para o Microsoft Defender para o Ponto de Extremidade!](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)
- [Prossiga para configurar o Microsoft Defender para o Ponto de Extremidade](symantec-to-microsoft-defender-atp-setup.md).
