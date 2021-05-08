---
title: Symantec para Microsoft Defender para Ponto de Extremidade - Fase 2, Configuração
description: Esta é a Fase 2, Instalação, de migração da Symantec para o Microsoft Defender para o Ponto de Extremidade
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
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 32ed277c87f5cca1a286cc24549dc331774cf03b
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245727"
---
# <a name="migrate-from-symantec---phase-2-set-up-microsoft-defender-for-endpoint"></a>Migrar da Symantec - Fase 2: Configurar o Microsoft Defender para Ponto de Extremidade

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Fase 1: Preparar](images/phase-diagrams/prepare.png)](symantec-to-microsoft-defender-atp-prepare.md)<br/>[Fase 1: Preparar](symantec-to-microsoft-defender-atp-prepare.md) |![Fase 2: Configurar](images/phase-diagrams/setup.png)<br/>Fase 2: Configurar |[![Fase 3: Integrar](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[Fase 3: Integrar](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
||*Você está aqui!* | |


**Bem-vindo à fase de Instalação [da migração da Symantec para o Microsoft Defender para o Ponto de Extremidade.](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)** Esta fase inclui as seguintes etapas:
1. [Habilitar ou reinstalar Microsoft Defender Antivírus (para determinadas versões de Windows)](#enable-or-reinstall-microsoft-defender-antivirus-for-certain-versions-of-windows).
2. [Habilitar Microsoft Defender Antivírus](#enable-microsoft-defender-antivirus).
3. [Obter atualizações para Microsoft Defender Antivírus](#get-updates-for-microsoft-defender-antivirus).
4. [Adicione o Microsoft Defender para Ponto de Extremidade à lista de exclusão da Symantec](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-symantec).
5. [Adicione Symantec à lista de exclusão para Microsoft Defender Antivírus](#add-symantec-to-the-exclusion-list-for-microsoft-defender-antivirus).
6. [Adicione Symantec à lista de exclusão do Microsoft Defender para Ponto de Extremidade](#add-symantec-to-the-exclusion-list-for-microsoft-defender-for-endpoint).
7. [Configurar grupos de dispositivos, coleções de dispositivos e unidades organizacionais.](#set-up-your-device-groups-device-collections-and-organizational-units)
8. [Configurar políticas antimalware e proteção em tempo real.](#configure-antimalware-policies-and-real-time-protection)

## <a name="enable-or-reinstall-microsoft-defender-antivirus-for-certain-versions-of-windows"></a>Habilitar ou reinstalar Microsoft Defender Antivírus (para determinadas versões de Windows)

> [!TIP]
> Se você estiver executando Windows 10, não será necessário executar essa tarefa. Prossiga **[para Habilitar Microsoft Defender Antivírus](#enable-microsoft-defender-antivirus)**.

Em determinadas versões Windows, Microsoft Defender Antivírus pode ter sido desinstalada ou desabilitada. Isso acontece porque Microsoft Defender Antivírus não entra no modo passivo ou desabilitado quando você instala um produto antivírus de terceiros, como o Symantec. Para saber mais, confira [Microsoft Defender Antivírus compatibilidade](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility). 

Agora que você está mudando da Symantec para o Microsoft Defender para o Ponto de Extremidade, você precisará habilitar ou reinstalar Microsoft Defender Antivírus e defini-lo para o modo passivo. 

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Reinstalar Microsoft Defender Antivírus no Windows Server

> [!NOTE]
> O procedimento a seguir se aplica apenas a pontos de extremidade ou dispositivos que estão executando as seguintes versões de Windows:
> - Windows Server 2019
> - Windows Servidor, versão 1803 (modo somente núcleo)
> - Windows Server 2016
> 
> Microsoft Defender Antivírus é criado em Windows 10, mas pode ser desabilitado. Nesse caso, prossiga para [Habilitar Microsoft Defender Antivírus](#enable-microsoft-defender-antivirus).

1. Como administrador local no ponto de extremidade ou dispositivo, abra Windows PowerShell.

1. Execute os seguintes cmdlets do PowerShell:<br/>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <br/>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`

    > [!NOTE]
    > Ao usar o comando DISM em uma sequência de tarefas executando o PS, o caminho a seguir para cmd.exe é necessário.
    > Exemplo:<br/>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<br/>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>

3. Para verificar Microsoft Defender Antivírus está em execução, use o seguinte cmdlet do PowerShell: <br/>
   `Get-Service -Name windefend`

#### <a name="are-you-using-windows-server-2016"></a>Você está usando Windows Server 2016?

Se você estiver usando Windows Server 2016 e estiver com problemas para habilcular Microsoft Defender Antivírus, use o seguinte cmdlet do PowerShell:

`mpcmdrun -wdenable`

> [!TIP]
> Ainda precisa de ajuda? Consulte [Microsoft Defender Antivírus no Windows Server 2016 2019](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-on-windows-server-2016).

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Definir Microsoft Defender Antivírus modo passivo no Windows Server

Como sua organização ainda está usando a Symantec, você deve definir Microsoft Defender Antivírus modo passivo. Dessa forma, a Symantec e o Microsoft Defender Antivírus podem ser executados lado a lado até que você tenha concluído a integração com o Microsoft Defender para Ponto de Extremidade.

1. Abra o Editor do Registro e navegue até <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. Edite (ou crie) uma entrada DWORD chamada **ForceDefenderPassiveMode** e especifique as seguintes configurações:
   - De definir o valor do DWORD como **1**.
   - Em **Base,** selecione **Hexadecimal**.

> [!NOTE]
> Você pode usar outros métodos para definir a chave do Registro, como o seguinte:
>- [Preferência da Política de Grupo](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [Ferramenta Objeto de Política de Grupo Local](/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
>- [Um pacote no Configuration Manager](/mem/configmgr/apps/deploy-use/packages-and-programs)

## <a name="enable-microsoft-defender-antivirus"></a>Habilitar Microsoft Defender Antivírus

Como sua organização tem usado a Symantec como sua solução antivírus principal, Microsoft Defender Antivírus provavelmente está desabilitada nos dispositivos Windows da sua organização. Esta etapa do processo de migração envolve a habilitação Microsoft Defender Antivírus. 

Para habilitar Microsoft Defender Antivírus, recomendamos usar o Intune. No entanto, você pode qualquer um dos métodos listados na tabela a seguir:

|Método  |O que fazer  |
|---------|---------|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**OBSERVAÇÃO**: o Intune agora Microsoft Endpoint Manager. |1. Vá para o centro de administração [Microsoft Endpoint Manager e](https://go.microsoft.com/fwlink/?linkid=2109431) entre.<br/><br/>2. Selecione **Perfis**  >  **de Configuração de** Dispositivos e selecione o tipo de perfil que você deseja configurar. Se você ainda não  criou um tipo de perfil de restrições de dispositivo ou se deseja criar um novo, consulte [Configure device restrictions settings in Microsoft Intune](/intune/device-restrictions-configure).<br/><br/>3. Selecione **Propriedades** e selecione **Configurações: Editar**.<br/><br/>4. **Expanda Microsoft Defender Antivírus**. <br/><br/>5. Habilitar **a proteção entregue na nuvem**.<br/><br/>6. No **Prompt users before sample submission** dropdown, select Send all **samples automatically**.<br/><br/>7. No menu suspenso **Detectar aplicativos** potencialmente indesejados, selecione **Habilitar** ou **Auditar**.<br/><br/>8. Selecione **Revisar + salvar** e, em seguida, escolha **Salvar**.<br/>Para obter mais informações sobre perfis de dispositivo do Intune, incluindo como criar e configurar suas configurações, consulte O que são Microsoft Intune [perfis de dispositivo?](/intune/device-profiles).|
|Painel de Controle no Windows     |Siga as diretrizes aqui: [Ativar Microsoft Defender Antivírus](/mem/intune/user-help/turn-on-defender-windows). <br/>**OBSERVAÇÃO**: você pode ver *Windows Defender Antivírus* em vez *de Microsoft Defender Antivírus* em algumas versões do Windows.        |
|[Gerenciamento avançado de política de grupo](/microsoft-desktop-optimization-pack/agpm/) <br/>ou<br/>[Console de Gerenciamento de Política de Grupo](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  |1. Vá para `Computer configuration > Administrative templates > Windows components > Microsoft Defender Antivirus` . <br/><br/>2. Procure uma política chamada **Desativar Microsoft Defender Antivírus**.<br/><br/>3. Escolha **Editar configuração de política** e certifique-se de que a política está desabilitada. Isso permite Microsoft Defender Antivírus. <br/><br/>**OBSERVAÇÃO**: você pode ver *Windows Defender Antivírus* em vez *de Microsoft Defender Antivírus* em algumas versões do Windows. |

### <a name="verify-that-microsoft-defender-antivirus-is-in-passive-mode"></a>Verifique se Microsoft Defender Antivírus está no modo passivo

Microsoft Defender Antivírus pode ser executado junto com a Symantec se você definir Microsoft Defender Antivírus modo passivo. Você pode usar o Prompt de Comando ou o PowerShell para executar essa tarefa, conforme descrito na tabela a seguir:

|Método  |O que fazer  |
|---------|---------|
|Prompt de comando     |1. Em um Windows, abra o Prompt de Comando como administrador. <br/><br/>2. Digite `sc query windefend` e pressione Enter.<br/><br/>3. Revise os resultados para confirmar se o Microsoft Defender Antivírus está sendo executado no modo passivo.         |
|PowerShell     |1. Em um Windows, abra Windows PowerShell como administrador.<br/><br/>2. Execute o cmdlet [Get-MpComputerStatus.](/powershell/module/defender/Get-MpComputerStatus)<br/> <br/>3. Na lista de resultados, procure **AMRunningMode: Modo** Passivo ou **AMRunningMode: Modo Passivo SxS**.|

> [!NOTE]
> Você pode ver *Windows Defender Antivírus* em vez *de Microsoft Defender Antivírus* em algumas versões do Windows.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Obter atualizações para Microsoft Defender Antivírus

Manter Microsoft Defender Antivírus atualizado é fundamental para garantir que seus dispositivos tenham a tecnologia e os recursos mais recentes necessários para proteger contra novas técnicas de malware e ataque, mesmo que o Microsoft Defender Antivírus seja executado no modo passivo [.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)

Há dois tipos de atualizações relacionadas à Microsoft Defender Antivírus atualizadas:
- Atualizações de inteligência de segurança
- Atualizações de produtos

Para obter suas atualizações, siga as diretrizes em Gerenciar atualizações [Microsoft Defender Antivírus e aplicar linhas de base.](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-symantec"></a>Adicionar o Microsoft Defender para Ponto de Extremidade à lista de exclusão da Symantec

Esta etapa do processo de instalação envolve a adição do Microsoft Defender for Endpoint à lista de exclusão da Symantec e de qualquer outro produto de segurança que sua organização está usando. As exclusões específicas a ser configuradas dependem de qual versão do Windows seus pontos de extremidade ou dispositivos estão sendo executados e estão listadas na tabela a seguir:

|SISTEMA OPERACIONAL |Exclusões |
|--|--|
|- Windows 10, [versão 1803](/windows/release-health/status-windows-10-1803) ou posterior (Consulte [Windows 10 informações de versão](/windows/release-health/release-information))<br/>- Windows 10, versão 1703 ou 1709 com [KB4493441](https://support.microsoft.com/help/4493441) instalado <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Servidor, versão 1803](/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<br/><br/>  |
|- [Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <br/><br/>- [Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/><br/>- [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/><br/>- [Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/><br/>- [Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<br/><br/>**OBSERVAÇÃO**: onde o Monitoramento de Arquivos Temporários do Host 6\45 pode ser subpastas numeradas diferentes.<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-symantec-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Adicionar Symantec à lista de exclusões para Microsoft Defender Antivírus

Durante esta etapa do processo de instalação, adicione a Symantec e suas outras soluções de segurança à lista de Microsoft Defender Antivírus exclusão. 

> [!NOTE]
> Para ter uma ideia de quais processos e serviços serão excluídos, consulte Broadcom's [Processes and services used by Endpoint Protection 14](https://knowledge.broadcom.com/external/article/170706/processes-and-services-used-by-endpoint.html).

Quando você adiciona [exclusões a Microsoft Defender Antivírus verificações,](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)você deve adicionar exclusões de caminho e processo. Lembre-se dos seguintes pontos:
- As exclusões de caminho excluem arquivos específicos e qualquer que seja o acesso a esses arquivos.
- As exclusões de processo excluem o que um processo toca, mas não exclui o processo em si.
- Se você listar cada executável (.exe) como uma exclusão de caminho e uma exclusão de processo, o processo e o que ele toca serão excluídos.
- Listar suas exclusões de processo usando seu caminho completo e não apenas pelo nome. (O método somente nome é menos seguro.)

Você pode escolher entre vários métodos para adicionar suas exclusões Microsoft Defender Antivírus, conforme listado na tabela a seguir:

|Método | O que fazer|
|--|--|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**OBSERVAÇÃO**: o Intune agora Microsoft Endpoint Manager. |1. Vá para o centro de administração [Microsoft Endpoint Manager e](https://go.microsoft.com/fwlink/?linkid=2109431) entre.<br/><br/>2. Selecione **Perfis**  >  **de Configuração de** Dispositivos e selecione o perfil que você deseja configurar.<br/><br/>3. Em **Gerenciar**, selecione **Propriedades**. <br/><br/>4. Selecione **Configurações: Editar**.<br/><br/>5. **Expanda Microsoft Defender Antivírus** e, em seguida, **expanda Microsoft Defender Antivírus Exclusões**.<br/><br/>6. Especifique os arquivos e pastas, extensões e processos a ser excluídos Microsoft Defender Antivírus verificações. Para referência, consulte [Microsoft Defender Antivírus exclusões](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions).<br/><br/>7. Escolha **Revisar + salvar** e, em seguida, escolha **Salvar**.  |
|[Gerenciador de Configuração do Microsoft Endpoint](/mem/configmgr/) |1. Usando o [console do Configuration Manager,](/mem/configmgr/core/servers/manage/admin-console)vá para **Ativos** e Conformidade  >  **Endpoint Protection**  >  **Políticas Antimalware** e selecione a política que você deseja modificar. <br/><br/>2. Especifique as configurações de exclusão para arquivos e pastas, extensões e processos a ser excluídos Microsoft Defender Antivírus verificações. |
|[Objeto Group Policy](/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](https://technet.microsoft.com/library/cc731212.aspx), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.<br/><br/>2. No Editor de Gerenciamento de **Política de Grupo,** acesse **Configuração** do computador e clique em **Modelos Administrativos**.<br/><br/>3. Expanda a árvore para Windows **componentes > Microsoft Defender Antivírus > Exclusões**.<br/>**OBSERVAÇÃO**: você pode ver *Windows Defender Antivírus* em vez *de Microsoft Defender Antivírus* em algumas versões do Windows.<br/><br/>4. Clique duas vezes na **configuração Exclusões de** Caminho e adicione as exclusões.<br/><br/>- Definir a opção como **Habilitado**.<br/><br/>- Na seção **Opções,** clique em **Mostrar...**.<br/><br/>- Especifique cada pasta em sua própria linha na **coluna Nome do** valor.<br/><br/>- Se você especificar um arquivo, insira um caminho totalmente qualificado para o arquivo, incluindo a letra da unidade, o caminho da pasta, o nome do arquivo e a extensão. Insira **0** na coluna **Valor.**<br/><br/>5. Clique em **OK**.<br/><br/>6. Clique duas vezes na **configuração Exclusões de** Extensão e adicione as exclusões.<br/><br/>- Definir a opção como **Habilitado**.<br/><br/>- Na seção **Opções,** clique em **Mostrar...**.<br/><br/>- Insira cada extensão de arquivo em sua própria linha na **coluna Nome do** valor.  Insira **0** na coluna **Valor.**<br/>7. Clique em **OK**. |
|Objeto de política de grupo local |1. No ponto de extremidade ou dispositivo, abra o Editor de Política de Grupo Local. <br/><br/>2. Vá para **Configuração** do Computador  >  **Modelos Administrativos**  >  **Windows Componentes**  >  **Microsoft Defender Antivírus**  >  **Exclusões**. <br/>**OBSERVAÇÃO**: você pode ver *Windows Defender Antivírus* em vez *de Microsoft Defender Antivírus* em algumas versões do Windows.<br/><br/>3. Especifique seu caminho e exclusões de processo. |
|Chave do Registro |1. Exporte a seguinte chave do Registro: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` .<br/><br/>2. Importe a chave do Registro. Aqui estão dois exemplos:<br/>- Caminho local: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- Compartilhamento de rede: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

## <a name="add-symantec-to-the-exclusion-list-for-microsoft-defender-for-endpoint"></a>Adicionar Symantec à lista de exclusão do Microsoft Defender para Ponto de Extremidade

Para adicionar exclusões ao Microsoft Defender para Ponto de Extremidade, crie [indicadores](/microsoft-365/security/defender-endpoint/manage-indicators#create-indicators-for-files).

1. Vá para o Central de Segurança do Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ) e entre.

1. No painel de navegação, **escolha** Configurações  >  **Indicadores de**  >  **Regras**.

1.  Na guia **Hashes de arquivo,** escolha **Adicionar indicador**.

1. Na guia **Indicador,** especifique as seguintes configurações:
   - Hash de arquivo (Precisa de ajuda? Consulte [Encontrar um hash de arquivo usando CMPivot](#find-a-file-hash-using-cmpivot) neste artigo.)
   - Em **Expira em (UTC),** escolha **Nunca**.
   
1. Na guia **Ação,** especifique as seguintes configurações:
   - **Ação de resposta**: **Permitir**
   - Título e descrição

1. Na guia **Escopo,** em **Grupos de dispositivos,** selecione Todos os dispositivos no **meu escopo** ou Selecione **na lista**.

1. Na guia **Resumo,** revise as configurações e clique em **Salvar**.

### <a name="find-a-file-hash-using-cmpivot"></a>Encontre um hash de arquivo usando CMPivot

CMPivot é um utilitário no console para o Configuration Manager. CMPivot fornece acesso ao estado em tempo real dos dispositivos em seu ambiente. Ele executa imediatamente uma consulta em todos os dispositivos conectados no momento na coleção de destino e retorna os resultados. Para saber mais, confira [Visão geral do CMPivot](/mem/configmgr/core/servers/manage/cmpivot-overview).

Para usar CMPivot para obter o hash de arquivo, siga estas etapas:

1. Revise os [pré-requisitos](/mem/configmgr/core/servers/manage/cmpivot#prerequisites).<br/>

2. [Iniciar CMPivot](/mem/configmgr/core/servers/manage/cmpivot#start-cmpivot). 

3. Conexão para o Configuration Manager ( `SCCM_ServerName.DomainName.com` ).

4. Selecione **a guia Consulta.**

5. Na lista **Conjunto de Dispositivos** e escolha **Todos os Sistemas (padrão)**.

6. Na caixa de consulta, digite a seguinte consulta:<br/>
   ```kusto
   File(c:\\windows\\notepad.exe)
   | project Hash
   ```
   
   > [!NOTE]
   > Na consulta acima, *substitua* notepad.exepelo nome do processo de produto de segurança de terceiros. 
   

## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>Configurar grupos de dispositivos, coleções de dispositivos e unidades organizacionais

| Tipo de coleção | O que fazer |
|--|--|
|[Os grupos de](/microsoft-365/security/defender-endpoint/machine-groups) dispositivos (anteriormente chamados de grupos de máquinas) permitem que sua equipe de operações de segurança configure recursos de segurança, como investigação e correção automatizadas.<br/> Os grupos de dispositivos também são úteis para atribuir acesso a esses dispositivos para que sua equipe de operações de segurança possa realizar ações de correção, se necessário. <br/>Os grupos de dispositivos são criados no Central de Segurança do Microsoft Defender. |1. Vá para a Central de Segurança do Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ).<br/><br/>2. No painel de navegação à esquerda, escolha **Configurações**  >  **Grupos de** Dispositivo de  >  **Permissões**.  <br/><br/>3. Escolha **+ Adicionar grupo de dispositivos**.<br/><br/>4. Especifique um nome e uma descrição para o grupo de dispositivos.<br/><br/>5. Na lista **Nível de automação,** selecione uma opção. (Recomendamos **Full - correção de ameaças automaticamente**.) Para saber mais sobre os vários níveis de automação, consulte [Como as ameaças são remediadas](/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated).<br/><br/>6. Especifique condições para uma regra correspondente para determinar quais dispositivos pertencem ao grupo de dispositivos. Por exemplo, você pode escolher um domínio, versões do sistema operacional ou até mesmo usar marcas [de dispositivo](/microsoft-365/security/defender-endpoint/machine-tags).<br/> <br/>7. Na guia **Acesso do** usuário, especifique funções que devem ter acesso aos dispositivos incluídos no grupo de dispositivos. <br/><br/>8. Escolha **Feito**. |
|[Os conjunto de dispositivos](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) permitem que sua equipe de operações de segurança gerencie aplicativos, implante configurações de conformidade ou instale atualizações de software nos dispositivos de sua organização. <br/>Os conjunto de dispositivos são criados usando o [Configuration Manager](/mem/configmgr/). |Siga as etapas em [Criar uma coleção](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create). |
|[As unidades organizacionais](/azure/active-directory-domain-services/create-ou) permitem agrupar logicamente objetos, como contas de usuário, contas de serviço ou contas de computador. Em seguida, você pode atribuir administradores a unidades organizacionais específicas e aplicar a política de grupo para impor configurações direcionadas.<br/> As unidades organizacionais são definidas [Azure Active Directory Serviços de Domínio.](/azure/active-directory-domain-services) | Siga as etapas em [Create an Organizational Unit in an Azure Active Directory Domain Services managed domain](/azure/active-directory-domain-services/create-ou). |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>Configurar políticas antimalware e proteção em tempo real

Usando o Configuration Manager e suas coleções de dispositivos, configure suas políticas antimalware.

- Consulte [Create and deploy antimalware policies for Endpoint Protection in Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies).

- Enquanto você cria e configura suas políticas antimalware, revise as configurações de proteção em tempo [real](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) e [habilita](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)o bloqueio à primeira vista.

> [!TIP]
> Você pode implantar as políticas antes dos dispositivos da sua organização em integração.

## <a name="next-step"></a>Próxima etapa

**Parabéns**! Você concluiu a fase de Instalação de migração da [Symantec para o Microsoft Defender para o Ponto de Extremidade](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)!
- [Prossiga para a Fase 3: Integração ao Microsoft Defender para Ponto de Extremidade](symantec-to-microsoft-defender-atp-onboard.md)
