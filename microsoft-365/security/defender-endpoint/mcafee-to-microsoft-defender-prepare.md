---
title: McAfee para Microsoft Defender para Ponto de Extremidade - Preparar
description: Esta é a fase 1, Preparar, para migrar da McAfee para o Microsoft Defender ATP.
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
- m365solution-mcafeemigrate
- m365solution-scenario
ms.topic: article
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: c87ed20dd1d0c959a9af52fd766d0a34232747b2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052742"
---
# <a name="migrate-from-mcafee---phase-1-prepare-for-your-migration"></a>Migrar da McAfee - Fase 1: Preparar-se para sua migração

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|![Fase 1: Preparar](images/phase-diagrams/prepare.png)<br/>Fase 1: Preparar |[![Fase 2: Configurar](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)<br/>[Fase 2: Configurar](mcafee-to-microsoft-defender-setup.md) |[![Fase 3: Onboard](images/phase-diagrams/onboard.png)](mcafee-to-microsoft-defender-onboard.md)<br/>[Fase 3: Onboard](mcafee-to-microsoft-defender-onboard.md) |
|--|--|--|
|*Você está aqui!*| | |


**Bem-vindo à fase preparar [a migração do McAfee Endpoint Security (McAfee) para o Microsoft Defender para o Ponto de Extremidade.](mcafee-to-microsoft-defender-migration.md#the-migration-process)** 

Essa fase de migração inclui as seguintes etapas:
1. [Obter e implantar atualizações nos dispositivos da sua organização](#get-and-deploy-updates-across-your-organizations-devices)
2. [Obter o Microsoft Defender para Ponto de Extremidade](#get-microsoft-defender-for-endpoint).
3. [Conceda acesso ao Centro de Segurança do Microsoft Defender.](#grant-access-to-the-microsoft-defender-security-center)
4. [Configure as configurações de proxy de dispositivo e conectividade com a Internet.](#configure-device-proxy-and-internet-connectivity-settings)

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>Obter e implantar atualizações nos dispositivos da sua organização

Como prática prática, mantenha os dispositivos e pontos de extremidade da sua organização atualizados. Certifique-se de que sua solução mcAfee Endpoint Security (McAfee) está atualizada e que os sistemas operacionais e aplicativos da sua organização também têm as atualizações mais recentes. Fazer isso agora pode ajudar a evitar problemas mais tarde à medida que você migra para o Microsoft Defender para o Ponto de Extremidade e o Microsoft Defender Antivírus.

### <a name="make-sure-your-mcafee-solution-is-up-to-date"></a>Certifique-se de que sua solução McAfee está atualizada

Mantenha a McAfee atualizada e certifique-se de que os dispositivos da sua organização tenham as atualizações de segurança mais recentes. Precisa de ajuda? Aqui estão alguns recursos da McAfee:

- [Documentação do produto corporativo da McAfee: como funciona a segurança do ponto de extremidade](https://docs.mcafee.com/bundle/endpoint-security-10.7.x-common-product-guide-windows/page/GUID-1207FF39-D1D2-481F-BBD9-E4079112A8DD.html)

- [Artigo técnico do Centro de Conhecimento da McAfee: o Windows Security Center relata incorretamente que o Endpoint Security está desabilitado ao ser executado no Windows 10](https://kc.mcafee.com/corporate/index?page=content&id=KB91830) 

- [Artigo técnico do Centro de Conhecimento da McAfee: o Windows Security Center relata que a Segurança do Ponto de Extremidade está desabilitada quando o Endpoint Security está em execução](https://kc.mcafee.com/corporate/index?page=content&id=KB91428)

- Seu Suporte do McAfee ServicePortal ( [http://mysupport.mcafee.com](http://mysupport.mcafee.com) )

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
> O Centro de Segurança do Microsoft Defender às vezes é conhecido como o portal do Microsoft Defender para Ponto de Extremidade. 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>Conceder acesso ao Centro de Segurança do Microsoft Defender

O Centro de Segurança do Microsoft Defender ( ) é onde você acessa e configura recursos e [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) recursos do Microsoft Defender para o Ponto de Extremidade. Para saber mais, confira [Visão geral do Centro de Segurança do Microsoft Defender.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

As permissões para o Centro de Segurança do Microsoft Defender podem ser concedidas usando permissões básicas ou controle de acesso baseado em função (RBAC). Recomendamos o uso do RBAC para que você tenha controle mais granular sobre permissões.

1. Planeje as funções e permissões para seus administradores de segurança e operadores de segurança. Consulte [Controle de acesso baseado em função](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/prepare-deployment#role-based-access-control).

2. Configurar e configurar o RBAC. Recomendamos usar [o Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) para configurar o RBAC, especialmente se sua organização estiver usando uma combinação de dispositivos Windows 10, macOS, iOS e Android. Consulte [configurando o RBAC usando o Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).

    Se sua organização exigir um método diferente do Intune, escolha uma das seguintes opções:
    - [Gerenciador de configuração](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [Gerenciamento avançado de política de grupo](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm)
    - [Windows Admin Center](https://docs.microsoft.com/windows-server/manage/windows-admin-center/overview)

3. Conceda acesso ao Centro de Segurança do Microsoft Defender. (Precisa de ajuda? Consulte [Gerenciar acesso ao portal usando RBAC](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)).

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Configurar configurações de proxy de dispositivo e conectividade com a Internet

Para habilitar a comunicação entre seus dispositivos e o Microsoft Defender para Ponto de Extremidade, configure configurações de proxy e internet. A tabela a seguir inclui links para recursos que você pode usar para configurar suas configurações de proxy e internet para vários sistemas operacionais e recursos:

|Recursos  | Sistema operacional | Recursos |
|--|--|--|
|[Detecção e resposta do ponto de extremidade](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 ou posterior](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)  |[Configurar configurações de proxy de máquina e conectividade com a Internet](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet) |
|EDR |- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/>- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows 7 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[Configurar configurações de conectividade de proxy e internet](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS: <br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave) <br/>- 10,13 (High Sierra)  |[Microsoft Defender para Ponto de Extremidade para Mac: conexões de rede](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|[Microsoft Defender Antivírus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 ou posterior](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) <br/>- [Windows Server 2016](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-2016) |[Configurar e validar as conexões de rede do Microsoft Defender Antivírus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)<br/> |
|Antivírus |macOS: <br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave) <br/>- 10,13 (High Sierra) |[Microsoft Defender para Ponto de Extremidade para Mac: conexões de rede](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|Antivírus |Linux: <br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS ou LTS superior<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Microsoft Defender para Ponto de Extremidade para Linux: conexões de rede](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux#network-connections) 

## <a name="next-step"></a>Próxima etapa

**Parabéns**! Você concluiu **a fase Preparar** a migração da [McAfee para o Microsoft Defender para o Ponto de Extremidade!](mcafee-to-microsoft-defender-migration.md#the-migration-process)

- [Prossiga para configurar o Microsoft Defender para o Ponto de Extremidade](mcafee-to-microsoft-defender-setup.md).
