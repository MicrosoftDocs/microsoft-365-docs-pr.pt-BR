---
title: Symantec para Microsoft Defender para Ponto de Extremidade - Fase 3, Integração
description: Esta é a Fase 3, Integração, de migração da Symantec para o Microsoft Defender para o Ponto de Extremidade
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
ms.openlocfilehash: b42a33d975e1368ad25d4a7102ef44bf8b9824a8
ms.sourcegitcommit: 72ae1b49e7a3d3199272fcb4c39f5daec0d66f1a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51698275"
---
# <a name="migrate-from-symantec---phase-3-onboard-to-microsoft-defender-for-endpoint"></a>Migrar da Symantec - Fase 3: Integração ao Microsoft Defender para Ponto de Extremidade

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Fase 1: Preparar](images/phase-diagrams/prepare.png)](symantec-to-microsoft-defender-atp-prepare.md)<br/>[Fase 1: Preparar](symantec-to-microsoft-defender-atp-prepare.md) |[![Fase 2: Configurar](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[Fase 2: Configurar](symantec-to-microsoft-defender-atp-setup.md) |![Fase 3: Integrar](images/phase-diagrams/onboard.png)<br/>Fase 3: Integrar |
|--|--|--|
|| |*Você está aqui!* |


**Bem-vindo à Fase 3 de [migração da Symantec para o Microsoft Defender para o Ponto de Extremidade.](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)** Essa fase de migração inclui as seguintes etapas:

1. [Dispositivos de integração com o Microsoft Defender para Ponto de Extremidade](#onboard-devices-to-microsoft-defender-for-endpoint).
2. [Execute um teste de detecção](#run-a-detection-test).
3. [Desinstale symantec](#uninstall-symantec).
4. [Certifique-se de que o Microsoft Defender para Ponto de Extremidade está no modo ativo](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode).

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Dispositivos integrados ao Microsoft Defender para Ponto de Extremidade

1. Vá para o Centro de Segurança do Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ) e entre.
2. Escolha **Configurações**  >  **Gerenciamento de**  >  **dispositivos Integração**. 
3. Na lista **Selecionar sistema operacional para iniciar o** processo de integração, selecione um sistema operacional. 
4. Em **Método deployment,** selecione uma opção. Siga os links e os prompts para integrar os dispositivos da sua organização. Precisa de ajuda? Consulte [Métodos de integração](#onboarding-methods) (neste artigo).

### <a name="onboarding-methods"></a>Métodos de integração
 
Os métodos de implantação variam, dependendo de qual sistema operacional está selecionado. Consulte os recursos listados na tabela abaixo para obter ajuda com a integração.

|Sistema operacional  |Method  |
|---------|---------|
|Windows 10     |- [Política de Grupo](configure-endpoints-gp.md)<br/>- [Configuration Manager](configure-endpoints-sccm.md)<br/>- [Gerenciamento de dispositivo móvel (Intune)](configure-endpoints-mdm.md)<br/>- [Script local](configure-endpoints-script.md) <br/><br/>**OBSERVAÇÃO**: um script local é adequado para uma prova de conceito, mas não deve ser usado para implantação de produção. Para uma implantação de produção, recomendamos usar a Política de Grupo, o Microsoft Endpoint Configuration Manager ou o Intune.         |
|- Windows 8.1 Enterprise <br/>- Windows 8.1 Pro <br/>- Windows 7 SP1 Enterprise <br/>- Windows 7 SP1 Pro     | [Agente de Monitoramento da Microsoft](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint)<br/><br/>**OBSERVAÇÃO**: o Agente de Monitoramento da Microsoft agora é o agente do Azure Log Analytics. Para saber mais, confira [Visão geral do agente do Log Analytics.](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)        |
|- Windows Server 2019 e posterior <br/>- Edição principal do Windows Server 2019 <br/>- Windows Server versão 1803 e posterior |- [Script local](configure-endpoints-script.md) <br/>- [Política de Grupo](configure-endpoints-gp.md) <br/>- [Configuration Manager](/configure-endpoints-sccm.md) <br/>- [System Center Configuration Manager](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)<br/>- [Scripts de integração VDI para dispositivos não persistentes](configure-endpoints-vdi.md) <br/><br/>**OBSERVAÇÃO**: um script local é adequado para uma prova de conceito, mas não deve ser usado para implantação de produção. Para uma implantação de produção, recomendamos usar a Política de Grupo, o Microsoft Endpoint Configuration Manager ou o Intune.    |
|- Windows Server 2016 <br/>- Windows Server 2012 R2 <br/>- Windows Server 2008 R2 SP1  |- [Centro de Segurança do Microsoft Defender](configure-server-endpoints.md)<br/>- [Centro de Segurança do Azure](https://docs.microsoft.com/azure/security-center/security-center-wdatp) |
|macOS<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)<br/>- 10,13 (High Sierra)<br/><br/>iOS<br/><br/>Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS ou LTS superior<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Dispositivos Windows não integrados](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>Executar um teste de detecção

Para verificar se seus dispositivos conectados estão conectados corretamente ao Microsoft Defender para Ponto de Extremidade, você pode executar um teste de detecção.

|Sistema operacional  |Orientação  |
|---------|---------|
|- Windows 10 <br/>- Windows Server 2019 <br/>- Windows Server, versão 1803 <br/>- Windows Server 2016 <br/>- Windows Server 2012 R2     |Consulte [Executar um teste de detecção](run-detection-test.md). <br/><br/>Visite o site de cenários de demonstração do Microsoft Defender for Endpoint ( ) e experimente um ou mais [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) dos cenários. Por exemplo, experimente o **cenário de demonstração de proteção entregue na** nuvem.         |
|macOS<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)<br/>- 10,13 (High Sierra)     |Baixe e use o aplicativo DIY em [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) . <br/><br/>Para obter mais informações, consulte [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md).        |
|Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS ou LTS superior<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |1. Execute o seguinte comando e procure um resultado de **1**: <br/>`mdatp health --field real_time_protection_enabled`. <br/><br/>2. Abra uma janela de Terminal e execute o seguinte comando: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <br/><br/>3. Execute o seguinte comando para listar quaisquer ameaças detectadas: <br/>`mdatp threat list`. <br/><br/>Para obter mais informações, consulte [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md). |

## <a name="uninstall-symantec"></a>Desinstalar symantec

Agora que você insinuou os dispositivos da sua organização no Microsoft Defender para Ponto de Extremidade, sua próxima etapa é desinstalar a Symantec.

1. [Desabilite a Proteção contra Adulteração](https://knowledge.broadcom.com/external/article?legacyId=tech192023) na Symantec.
2. Exclua a senha de desinstalação da Symantec:<br/>
   1. Em seus dispositivos Windows, abra o Editor do Registro como administrador.
   2. Vá para `HKEY_LOCAL_MACHINE\SOFTWARE\Symantec\Symantec Endpoint Protection\SMC`.
   3. Procure uma entrada chamada **SmcInstData**. 
   4. Clique com o botão direito do mouse no item e escolha **Excluir**. 
3. Remova symantec de seus dispositivos. Se você precisar de ajuda com isso, consulte a documentação da Broadcom. Aqui estão alguns recursos broadcom: 
   - [Desinstalar a Proteção de Ponto de Extremidade da Symantec](https://knowledge.broadcom.com/external/article/156148/uninstall-symantec-endpoint-protection.html)
   - Dispositivos Windows: [desinstalar manualmente clientes do Endpoint Protection 14 no Windows](https://knowledge.broadcom.com/external/article?articleId=170040)
   - computadores macOS: [Remover software Symantec para Mac usando RemoveSymantecMacFiles](https://knowledge.broadcom.com/external/article?articleId=151387)
   - Dispositivos Linux: [Perguntas frequentes sobre a Proteção de Ponto de Extremidade no Linux](https://knowledge.broadcom.com/external/article?articleId=162054)

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a>Certifique-se de que o Microsoft Defender para Ponto de Extremidade está no modo ativo

Agora que você desinstalou a Symantec, sua próxima etapa é garantir que o Microsoft Defender Antivírus e o Microsoft Defender para Ponto de Extremidade estão habilitados e no modo ativo.

Para fazer isso, visite o site de cenários de demonstração do Microsoft Defender for Endpoint ( [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) ). Experimente um ou mais dos cenários de demonstração nessa página, incluindo pelo menos o seguinte:
- Proteção entregue na nuvem
- Aplicativos potencialmente indesejados (PUA)
- Proteção de Rede (NP)

> [!IMPORTANT]
> Se você estiver usando o Windows Server 2016, talvez seja preciso iniciar o Microsoft Defender Antivírus manualmente. Você pode fazer isso usando o cmdlet do PowerShell `mpcmdrun.exe -wdenable` no dispositivo.

## <a name="next-steps"></a>Próximas etapas

**Parabéns**! Você concluiu sua [migração da Symantec para o Microsoft Defender para o Ponto de Extremidade](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)! 
- [Visite seu painel de operações de](security-operations-dashboard.md) segurança no Centro de Segurança do Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 
- [Gerenciar o Microsoft Defender para Ponto de Extremidade, pós-migração](manage-atp-post-migration.md).
