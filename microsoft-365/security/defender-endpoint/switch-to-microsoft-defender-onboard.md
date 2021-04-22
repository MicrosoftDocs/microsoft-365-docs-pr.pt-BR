---
title: Alternar para o Microsoft Defender para Ponto de Extremidade - Onboard
description: Esta é a fase 3, Onboard, para migrar de uma solução que não seja da Microsoft para o Microsoft Defender para o Ponto de Extremidade.
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
ms.custom: migrationguides
ms.topic: article
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 459a113bb28c4ae0fa7c4d4a0b004ad2badc0da8
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935912"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a>Alternar para o Microsoft Defender para o Ponto de Extremidade - Fase 3: Onboard

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| [![Fase 1: Preparar3](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[Fase 1: Preparar](switch-to-microsoft-defender-prepare.md) | [![Fase 2: Configurar](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[Fase 2: Configurar](switch-to-microsoft-defender-setup.md) | ![Fase 3: Integrar](images/phase-diagrams/onboard.png)<br/>Fase 3: Integrar |
|--|--|--|
|| |*Você está aqui!* |


**Bem-vindo à Fase 3 [da mudança para o Microsoft Defender para Ponto de Extremidade](switch-to-microsoft-defender-migration.md#the-migration-process)**. Essa fase de migração inclui as seguintes etapas:

1. [Dispositivos de integração com o Microsoft Defender para Ponto de Extremidade](#onboard-devices-to-microsoft-defender-for-endpoint).
2. [Execute um teste de detecção](#run-a-detection-test).
3. [Desinstale sua solução que não seja da Microsoft.](#uninstall-your-non-microsoft-solution)
4. [Certifique-se de que o Microsoft Defender para Ponto de Extremidade está no modo ativo](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode).

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Dispositivos integrados ao Microsoft Defender para Ponto de Extremidade

1. Vá para o Centro de Segurança do Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ) e entre.
2. Escolha **Configurações**  >  **Gerenciamento de**  >  **dispositivos Integração**. 
3. Na lista **Selecionar sistema operacional para iniciar o** processo de integração, selecione um sistema operacional. 
4. Em **Método deployment,** selecione uma opção. Siga os links e os prompts para integrar os dispositivos da sua organização. Precisa de ajuda? Consulte [Métodos de integração](#onboarding-methods) (neste artigo).

### <a name="onboarding-methods"></a>Métodos de integração
 
Os métodos de implantação variam, dependendo de qual sistema operacional está selecionado. Consulte os recursos listados na tabela abaixo para obter ajuda com a integração.

|Sistema operacional  |Método  |
|---------|---------|
|Windows 10     |- [Política de Grupo](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp)<br/>- [Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)<br/>- [Gerenciamento de dispositivo móvel (Intune)](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-mdm)<br/>- [Script local](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script) <br/><br/>**OBSERVAÇÃO**: um script local é adequado para uma prova de conceito, mas não deve ser usado para implantação de produção. Para uma implantação de produção, recomendamos usar a Política de Grupo, o Microsoft Endpoint Configuration Manager ou o Intune.         |
|- Windows 8.1 Enterprise <br/>- Windows 8.1 Pro <br/>- Windows 7 SP1 Enterprise <br/>- Windows 7 SP1 Pro     | [Agente de Monitoramento da Microsoft](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-atp)<br/><br/>**OBSERVAÇÃO**: o Agente de Monitoramento da Microsoft agora é o agente do Azure Log Analytics. Para saber mais, confira [Visão geral do agente do Log Analytics.](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)        |
|- Windows Server 2019 e posterior <br/>- Edição principal do Windows Server 2019 <br/>- Windows Server versão 1803 e posterior |- [Script local](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script) <br/>- [Política de Grupo](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp) <br/>- [Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm) <br/>- [System Center Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm#onboard-windows-10-devices-using-earlier-versions-of-system-center-configuration-manager) <br/>- [Scripts de integração VDI para dispositivos não persistentes](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi) <br/><br/>**OBSERVAÇÃO**: um script local é adequado para uma prova de conceito, mas não deve ser usado para implantação de produção. Para uma implantação de produção, recomendamos usar a Política de Grupo, o Microsoft Endpoint Configuration Manager ou o Intune.    |
|- Windows Server 2016 <br/>- Windows Server 2012 R2 <br/>- Windows Server 2008 R2 SP1  |- [Centro de Segurança do Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#option-1-onboard-servers-through-microsoft-defender-security-center)<br/>- [Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-wdatp) |
|macOS<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)<br/>- 10,13 (High Sierra)<br/><br/>iOS<br/><br/>Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS ou LTS superior<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Dispositivos Windows não integrados](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-non-windows)  |

## <a name="run-a-detection-test"></a>Executar um teste de detecção

Para verificar se seus dispositivos conectados estão conectados corretamente ao Microsoft Defender para Ponto de Extremidade, você pode executar um teste de detecção.

|Sistema operacional  |Orientação  |
|---------|---------|
|- Windows 10 <br/>- Windows Server 2019 <br/>- Windows Server, versão 1803 <br/>- Windows Server 2016 <br/>- Windows Server 2012 R2     |Consulte [Executar um teste de detecção](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test). <br/><br/>Visite o site de cenários de demonstração do Microsoft Defender for Endpoint ( ) e experimente um ou mais [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) dos cenários. Por exemplo, experimente o **cenário de demonstração de proteção entregue na** nuvem.         |
|macOS<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)<br/>- 10,13 (High Sierra)     |Baixe e use o aplicativo DIY em [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) . <br/><br/>Para obter mais informações, consulte [Microsoft Defender for Endpoint on macOS](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac).        |
|Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS ou LTS superior<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |1. Execute o seguinte comando e procure um resultado de **1**: <br/>`mdatp health --field real_time_protection_enabled`. <br/><br/>2. Abra uma janela de Terminal e execute o seguinte comando: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <br/><br/>3. Execute o seguinte comando para listar quaisquer ameaças detectadas: <br/>`mdatp threat list`. <br/><br/>Para obter mais informações, consulte [Microsoft Defender for Endpoint on Linux](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-linux). |

## <a name="uninstall-your-non-microsoft-solution"></a>Desinstalar sua solução que não seja da Microsoft

Agora que você insinuou os dispositivos da sua organização no Microsoft Defender para Ponto de Extremidade, sua próxima etapa é desinstalar sua solução de proteção de ponto de extremidade que não seja da Microsoft.

Para obter ajuda com esta etapa, entre em contato com a equipe de suporte técnico do provedor de soluções.

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a>Certifique-se de que o Microsoft Defender para Ponto de Extremidade está no modo ativo

Agora que você desinstalou sua solução de proteção de ponto de extremidade não Microsoft, sua próxima etapa é garantir que o Microsoft Defender Antivírus e o Microsoft Defender para Ponto de Extremidade estão habilitados e no modo ativo.

Para fazer isso, visite o site de cenários de demonstração do Microsoft Defender for Endpoint ( [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) ). Experimente um ou mais dos cenários de demonstração nessa página, incluindo pelo menos o seguinte:
- Proteção fornecida na nuvem
- Aplicativos potencialmente indesejados (PUA)
- Proteção de Rede (NP)

> [!IMPORTANT]
> Se você estiver usando o Windows Server 2016, talvez seja preciso iniciar o Microsoft Defender Antivírus manualmente. Você pode fazer isso usando o cmdlet do PowerShell `mpcmdrun.exe -wdenable` no dispositivo.

## <a name="next-steps"></a>Próximas etapas

**Parabéns**! Você concluiu sua [migração para o Microsoft Defender para o Ponto de Extremidade](switch-to-microsoft-defender-migration.md#the-migration-process)! 

- [Visite seu painel de operações de](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard) segurança no Centro de Segurança do Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 
- [Gerenciar o Microsoft Defender para Ponto de Extremidade, pós-migração](manage-atp-post-migration.md).
