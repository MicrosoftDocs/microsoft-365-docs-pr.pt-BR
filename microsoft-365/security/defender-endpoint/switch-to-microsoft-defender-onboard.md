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
ms.date: 05/20/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 939fea5b815827f5afbe6cdf78fd9335da6337e8
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594056"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a>Alternar para o Microsoft Defender para o Ponto de Extremidade - Fase 3: Onboard

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| [![Fase 1: Preparar3](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[Fase 1: Preparar](switch-to-microsoft-defender-prepare.md) | [![Fase 2: Configurar](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[Fase 2: Configurar](switch-to-microsoft-defender-setup.md) | ![Fase 3: Integrar](images/phase-diagrams/onboard.png)<br/>Fase 3: Integrar |
|--|--|--|
|| |*Você está aqui!* |


**Bem-vindo à Fase 3 [da alternação para o Defender para o Ponto de Extremidade](switch-to-microsoft-defender-migration.md#the-migration-process)**. Essa fase de migração inclui as seguintes etapas:

1. [Dispositivos de integração com o Defender para Ponto de Extremidade](#onboard-devices-to-microsoft-defender-for-endpoint).
2. [Execute um teste de detecção](#run-a-detection-test).
3. [Confirme se Microsoft Defender Antivírus está no modo passivo em seus pontos de extremidade](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints).
4. [Obter atualizações para Microsoft Defender Antivírus](#get-updates-for-microsoft-defender-antivirus).
5. [Desinstale sua solução que não seja da Microsoft.](#uninstall-your-non-microsoft-solution) 
6. [Certifique-se de que o Defender para o Ponto de Extremidade está funcionando corretamente.](#make-sure-defender-for-endpoint-is-working-correctly)

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Dispositivos integrados ao Microsoft Defender para Ponto de Extremidade

1. Vá para o Central de Segurança do Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) e entre.

2. Escolha **Configurações**  >  **Gerenciamento de**  >  **dispositivos Integrando**. 

3. Na lista **Selecionar sistema operacional para iniciar o** processo de integração, selecione um sistema operacional. 

4. Em **Método deployment,** selecione uma opção. Siga os links e os prompts para integrar os dispositivos da sua organização. Precisa de ajuda? Consulte [Métodos de integração](#onboarding-methods) (neste artigo).

### <a name="onboarding-methods"></a>Métodos de integração
 
Os métodos de implantação variam, dependendo do sistema operacional e dos métodos preferenciais. A tabela a seguir lista recursos para ajudá-lo a entrar no Defender for Endpoint:

|Sistemas operacionais  |Métodos  |
|---------|---------|
| Windows 10     | [Política de grupo](configure-endpoints-gp.md)<p>[Configuration Manager](configure-endpoints-sccm.md)<p>[Gerenciamento de dispositivo móvel (Intune)](configure-endpoints-mdm.md)<p>[Script local](configure-endpoints-script.md) <p>**OBSERVAÇÃO**: um script local é adequado para uma prova de conceito, mas não deve ser usado para implantação de produção. Para uma implantação de produção, recomendamos usar a Política de Grupo, Microsoft Endpoint Configuration Manager ou Intune.         |
| Windows 8.1 Enterprise <p>Windows 8.1 Pro <p>Windows 7 sp1 Enterprise <p>Windows 7 sp1 Pro     | [Microsoft Monitoring Agent](onboard-downlevel.md)<p>**OBSERVAÇÃO**: Microsoft Monitoring Agent agora é agente do Azure Log Analytics. Para saber mais, confira [Visão geral do agente do Log Analytics.](/azure/azure-monitor/platform/log-analytics-agent)        |
| Windows Server 2019 e posterior <p>Windows Edição principal do Server 2019 <p>Windows Servidor versão 1803 e posterior | [Script local](configure-endpoints-script.md) <p>[Política de grupo](configure-endpoints-gp.md) <p>[Configuration Manager](configure-endpoints-sccm.md) <p>[System Center Configuration Manager](configure-endpoints-sccm.md) <p>[Scripts de integração VDI para dispositivos não persistentes](configure-endpoints-vdi.md) <p>**OBSERVAÇÃO**: um script local é adequado para uma prova de conceito, mas não deve ser usado para implantação de produção. Para uma implantação de produção, recomendamos usar a Política de Grupo, Microsoft Endpoint Configuration Manager ou Intune.    |
| Windows Server 2016 <p>Windows Server 2012 R2 <p>Windows Server 2008 R2 SP1  | [Central de Segurança do Microsoft Defender](configure-server-endpoints.md)<p>[Azure Defender](/azure/security-center/security-center-wdatp) |
| macOS:<p>11.3.1 (Big Sur) <p>10.15 (Catalina)<p>10.14 (Mojave) | [Dispositivos Windows não integrados](configure-endpoints-non-windows.md)  |
| iOS | [Dispositivos Windows não integrados](configure-endpoints-non-windows.md)  |
| Linux:<p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS ou LTS superior<p>SLES 12+<p>Debian 9+<p>Oracle Linux 7.2 | [Dispositivos Windows não integrados](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>Executar um teste de detecção

Para verificar se seus dispositivos conectados estão conectados corretamente ao Defender para Ponto de Extremidade, você pode executar um teste de detecção.

|Sistema operacional  |Orientação  |
|---------|---------|
| Windows 10 <p>Windows Server 2019 <p>Windows Servidor, versão 1803 <p>Windows Server 2016 <p>Windows Server 2012 R2     | Consulte [Executar um teste de detecção](run-detection-test.md). <p>Visite o site de cenários de demonstração do Defender para Ponto de Extremidade ( ) e experimente um ou mais [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) dos cenários. Por exemplo, experimente o **cenário de demonstração de proteção entregue na** nuvem.    |
| macOS:<p>11.3.1 (Big Sur) <p>10.15 (Catalina)<p>10.14 (Mojave)    | Baixe e use o aplicativo DIY em [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) . <p>Para obter mais informações, [consulte Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md).        |
| Linux:<p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS ou LTS superior<p>SLES 12+<p>Debian 9+<p>Oracle Linux 7.2 | 1. Execute o seguinte comando e procure um resultado de **1**: <br/>`mdatp health --field real_time_protection_enabled`. <p>2. Abra uma janela de Terminal e execute o seguinte comando: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <p>3. Execute o seguinte comando para listar quaisquer ameaças detectadas: <br/>`mdatp threat list`. <p>Para obter mais informações, [consulte Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md). |

## <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints"></a>Confirme se Microsoft Defender Antivírus está no modo passivo em seus pontos de extremidade

Agora que seus pontos de extremidade foram integrados ao Defender para Ponto de Extremidade, sua próxima etapa é garantir Microsoft Defender Antivírus está sendo executado no modo passivo. Você pode usar o Prompt de Comando ou o PowerShell para executar essa tarefa, conforme descrito na tabela a seguir:

| Método  | O que fazer  |
|:-------|:-------|
|Prompt de comando     | 1. Em um Windows, abra o Prompt de Comando como administrador.<p>2. Digite `sc query windefend` e pressione Enter.<p>3. Revise os resultados para confirmar se o Microsoft Defender Antivírus está sendo executado no modo passivo.         |
| PowerShell     | 1. Em um Windows, abra Windows PowerShell como administrador.<p>2. Execute o cmdlet [Get-MpComputerStatus.](/powershell/module/defender/Get-MpComputerStatus) <p>3. Na lista de resultados, procure **AMRunningMode: Modo** Passivo ou **AMRunningMode: Modo Passivo SxS**.    |

> [!NOTE]
> Você pode ver *Windows Defender Antivírus* em vez *de Microsoft Defender Antivírus* em algumas versões do Windows.

### <a name="set-microsoft-defender-antivirus-on-windows-server-to-passive-mode-manually"></a>Definir Microsoft Defender Antivírus no Windows Server para o modo passivo manualmente

Para definir Microsoft Defender Antivírus modo passivo no Windows Server, versão 1803 ou mais recente ou Windows Server 2019, siga estas etapas:

1. Abra o Editor do Registro e navegue até <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. Edite (ou crie) uma entrada DWORD chamada **ForcePassiveMode** e especifique as seguintes configurações:
   - De definir o valor do DWORD como **1**.
   - Em **Base,** selecione **Hexadecimal**.

> [!NOTE]
> Você pode usar outros métodos para definir a chave do Registro, como o seguinte:
>- [Preferência da Política de Grupo](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [Ferramenta Objeto de Política de Grupo Local](/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
>- [Um pacote no Configuration Manager](/mem/configmgr/apps/deploy-use/packages-and-programs)

### <a name="start-microsoft-defender-antivirus-on-windows-server-2016"></a>Iniciar Microsoft Defender Antivírus no Windows Server 2016

Se você estiver usando Windows Server 2016, talvez seja preciso iniciar Microsoft Defender Antivírus manualmente. Você pode fazer isso usando o cmdlet do PowerShell `mpcmdrun.exe -wdenable` no dispositivo.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Obter atualizações para Microsoft Defender Antivírus

Manter Microsoft Defender Antivírus atualizado é fundamental para garantir que seus dispositivos tenham a tecnologia e os recursos mais recentes necessários para proteger contra novas técnicas de malware e ataque, mesmo que o Microsoft Defender Antivírus seja executado no modo passivo. (Consulte [Microsoft Defender Antivírus compatibilidade](microsoft-defender-antivirus-compatibility.md).)

Há dois tipos de atualizações relacionadas à Microsoft Defender Antivírus atualizadas:

- Atualizações de inteligência de segurança
- Atualizações de produtos

Para obter suas atualizações, siga as diretrizes em Gerenciar atualizações [Microsoft Defender Antivírus e aplicar linhas de base.](manage-updates-baselines-microsoft-defender-antivirus.md)

## <a name="uninstall-your-non-microsoft-solution"></a>Desinstalar sua solução que não seja da Microsoft

Se neste ponto você tiver:

- Integramos os dispositivos da sua organização ao Defender para Ponto de Extremidade e 
- Microsoft Defender Antivírus está instalado e habilitado, 

Em seguida, sua próxima etapa é desinstalar sua solução de proteção de ponto de extremidade que não seja da Microsoft. 

Para obter ajuda com essa tarefa, entre em contato com a equipe de suporte técnico do provedor de soluções.

## <a name="make-sure-defender-for-endpoint-is-working-correctly"></a>Certifique-se de que o Defender para o Ponto de Extremidade está funcionando corretamente

Agora que você embarcou no Defender para Ponto de Extremidade e desinstalou sua solução anterior não-Microsoft, a próxima etapa é garantir que o Defender para Ponto de Extremidade funciona corretamente. Uma boa maneira de fazer isso é visitando o site de cenários de demonstração do Defender for Endpoint ( [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) ). Experimente um ou mais dos cenários de demonstração nessa página, incluindo pelo menos o seguinte:

- Proteção fornecida na nuvem
- Aplicativos potencialmente indesejados (PUA)
- Proteção de Rede (NP)

## <a name="next-steps"></a>Próximas etapas

**Parabéns**! Você concluiu sua [migração para o Defender para o Ponto de Extremidade](switch-to-microsoft-defender-migration.md#the-migration-process)! 

- [Visite seu painel de operações de](security-operations-dashboard.md) segurança no Central de Segurança do Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ). 
- [Gerenciar o Defender para Ponto de Extremidade, pós-migração](manage-atp-post-migration.md).
