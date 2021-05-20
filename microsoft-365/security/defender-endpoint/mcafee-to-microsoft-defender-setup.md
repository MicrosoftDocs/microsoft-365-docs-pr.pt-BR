---
title: McAfee para Microsoft Defender para Ponto de Extremidade - Instalação
description: Esta é a fase 2, Instalação, para migrar da McAfee para o Microsoft Defender para o Ponto de Extremidade.
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
- m365solution-mcafeemigrate
- m365solution-scenario
ms.topic: article
ms.custom: migrationguides
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 6fb6f6ccb6b30804788a147ab2db425a88998131
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538010"
---
# <a name="migrate-from-mcafee---phase-2-set-up-microsoft-defender-for-endpoint"></a>Migrar da McAfee - Fase 2: Configurar o Microsoft Defender para Ponto de Extremidade

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Fase 1: Preparar](images/phase-diagrams/prepare.png)](mcafee-to-microsoft-defender-prepare.md)<br/>[Fase 1: Preparar](mcafee-to-microsoft-defender-prepare.md) |![Fase 2: Configurar](images/phase-diagrams/setup.png)<br/>Fase 2: Configurar |[![Fase 3: Integrar](images/phase-diagrams/onboard.png)](mcafee-to-microsoft-defender-onboard.md)<br/>[Fase 3: Integrar](mcafee-to-microsoft-defender-onboard.md) |
|--|--|--|
||*Você está aqui!* | |

**Bem-vindo à fase de instalação [da migração do McAfee Endpoint Security (McAfee) para o Defender para o Ponto de Extremidade.](mcafee-to-microsoft-defender-migration.md#the-migration-process)** Esta fase inclui as seguintes etapas:

1. [Reinstalar ou habilitar Microsoft Defender Antivírus em seus pontos de extremidade.](#reinstall-or-enable-microsoft-defender-antivirus-on-your-endpoints)

2. [Configurar o Defender para o Ponto de Extremidade](#configure-defender-for-endpoint).

3. [Adicione o Microsoft Defender para Ponto de Extremidade à lista de exclusão para McAfee](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-mcafee).

4. [Adicione McAfee à lista de exclusão para Microsoft Defender Antivírus](#add-mcafee-to-the-exclusion-list-for-microsoft-defender-antivirus).

5. [Configurar grupos de dispositivos, coleções de dispositivos e unidades organizacionais.](#set-up-your-device-groups-device-collections-and-organizational-units)

6. [Configurar políticas antimalware e proteção em tempo real.](#configure-antimalware-policies-and-real-time-protection)

## <a name="reinstall-or-enable-microsoft-defender-antivirus-on-your-endpoints"></a>Reinstalar ou habilitar Microsoft Defender Antivírus em seus pontos de extremidade

Em determinadas versões do Windows, Microsoft Defender Antivírus é provavelmente desinstalada ou desabilitada quando sua solução antivírus/antimalware não Microsoft foi instalada. Para obter mais informações, [consulte Microsoft Defender Antivírus compatibilidade](microsoft-defender-antivirus-compatibility.md).

Em Windows clientes, quando uma solução antivírus/antimalware não Microsoft é instalada, o Microsoft Defender Antivírus é desabilitado automaticamente até que esses dispositivos sejam integradas ao Defender para Ponto de Extremidade. Quando os pontos de extremidade do cliente são integradas ao Defender para Ponto de Extremidade, Microsoft Defender Antivírus entra no modo passivo até que a solução antivírus não Microsoft seja desinstalada. Microsoft Defender Antivírus ainda deve ser instalado, mas provavelmente está desabilitado neste ponto do processo de migração. A menos Microsoft Defender Antivírus tenha sido desinstalado, você não precisa tomar nenhuma ação para seus Windows clientes.

Em Windows servidores, quando um antivírus/antimalware não microsoft em instalado, Microsoft Defender Antivírus é desabilitado manualmente (se não desinstalado). As tarefas a seguir ajudam a garantir que Microsoft Defender Antivírus seja instalado e definido como modo passivo no Windows Server.

Esta etapa do processo de migração inclui as seguintes tarefas:
- [Definindo DisableAntiSpyware](#set-disableantispyware-to-false-on-windows-server) como false no Windows Server (somente se necessário)
- [Reinstalando Microsoft Defender Antivírus no Windows Server;](#reinstall-microsoft-defender-antivirus-on-windows-server)
- [Definindo Microsoft Defender Antivírus modo passivo no Windows Server](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server)

### <a name="set-disableantispyware-to-false-on-windows-server"></a>Definir DisableAntiSpyware como false no Windows Server

A [chave do Registro DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) foi usada no passado para desabilitar Microsoft Defender Antivírus e implantar outro produto antivírus, como o McAfee. Em geral, você não deve ter essa chave do Registro em seus Windows dispositivos e pontos de extremidade; no entanto, se você `DisableAntiSpyware` tiver configurado, veja como definir seu valor como false:

1. Em seu Windows servidor, abra Editor do Registro.

2. Navegue até `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`.

3. Nessa pasta, procure uma entrada DWORD chamada **DisableAntiSpyware**.

   - Se você não vir essa entrada, está tudo definido.

   - Se você vir **DisableAntiSpyware,** prossiga para a etapa 4.

4. Clique com o botão direito do mouse no DWORD DisableAntiSpyware e escolha **Modificar**.

5. De definir o valor como `0` . (Isso define o valor da chave do Registro como *false*.)

> [!TIP]
> Para saber mais sobre essa chave do Registro, consulte [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware).

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Reinstalar Microsoft Defender Antivírus no Windows Server

> [!NOTE]
> O procedimento a seguir se aplica apenas a pontos de extremidade ou dispositivos que estão executando as seguintes versões de Windows:
> - Windows Server 2019
> - Windows Servidor, versão 1803 (modo somente núcleo)
> - Windows Server 2016

1. Como administrador local no ponto de extremidade ou dispositivo, abra Windows PowerShell.

2. Execute os seguintes cmdlets do PowerShell: <br/>
   
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <br/>
   
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender` <br/>

   > [!NOTE]
   > Ao usar o comando DISM em uma sequência de tarefas executando o PS, o caminho a seguir para cmd.exe é necessário.
   > Exemplos:
   >
   > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<br/>
   >
   > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>

3. Para verificar Microsoft Defender Antivírus está em execução, use o seguinte cmdlet do PowerShell: <br/>
   
   `Get-Service -Name windefend`

   Procure um status de *Running*.

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Definir Microsoft Defender Antivírus modo passivo no Windows Server

1. Abra o Editor do Registro e navegue até `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection` .

2. Edite (ou crie) uma entrada DWORD chamada **ForcePassiveMode** e especifique as seguintes configurações:

   - De definir o valor do DWORD como `1` .

   - Em Base, selecione **Hexadecimal**.

> [!NOTE]
> Após a integração com o Defender para Ponto de Extremidade, talvez seja preciso definir Microsoft Defender Antivírus modo passivo no Windows Server.

### <a name="are-you-using-windows-server-2016"></a>Você está usando Windows Server 2016?

Se você tiver pontos de extremidade executando Windows Server 2016, não poderá Microsoft Defender Antivírus com uma solução antivírus/antimalware que não seja da Microsoft. Microsoft Defender Antivírus pode ser executado no modo passivo Windows Server 2016. Nesse caso, você precisará desinstalar a solução antivírus/antimalware que não seja da Microsoft e instalar/habilitar Microsoft Defender Antivírus. Para saber mais, confira [compatibilidade da solução antivírus com o Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-compatibility).

Se você estiver usando Windows Server 2016 e estiver com problemas para habilcular Microsoft Defender Antivírus, use o seguinte cmdlet do PowerShell:

`mpcmdrun -wdenable`

Para obter mais informações, [consulte Microsoft Defender Antivírus no Windows Server](microsoft-defender-antivirus-on-windows-server.md).

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Definir Microsoft Defender Antivírus modo passivo no Windows Server

Como sua organização ainda está usando a McAfee, você deve definir Microsoft Defender Antivírus modo passivo. Dessa forma, a McAfee e Microsoft Defender Antivírus podem ser executados lado a lado até que você tenha concluído a integração com o Defender para Ponto de Extremidade.

1. Abra o Editor do Registro e navegue até <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. Edite (ou crie) uma entrada DWORD chamada **ForcePassiveMode** e especifique as seguintes configurações:
   
   - De definir o valor do DWORD como **1**.
   
   - Em **Base,** selecione **Hexadecimal**.

> [!NOTE]
> Você pode usar outros métodos para definir a chave do Registro, como o seguinte:
>- [Preferência da Política de Grupo](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [Um pacote no Configuration Manager](/mem/configmgr/apps/deploy-use/packages-and-programs)

## <a name="configure-defender-for-endpoint"></a>Configurar o Defender para Ponto de Extremidade

Esta etapa do processo de migração envolve a configuração do Defender para o Ponto de Extremidade. Recomendamos o uso do Intune; no entanto, você pode qualquer um dos métodos listados na tabela a seguir:

|Método  |O que fazer  |
|---------|---------|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <p>**OBSERVAÇÃO**: o Intune agora faz parte Microsoft Endpoint Manager. |1. Vá para o centro de administração [Microsoft Endpoint Manager e](https://go.microsoft.com/fwlink/?linkid=2109431) entre.<p>2. Selecione **Perfis**  >  **de Configuração de** Dispositivos e selecione o tipo de perfil que você deseja configurar. <br/>Se você ainda não  criou um tipo de perfil de restrições de dispositivo ou se deseja criar um novo, consulte [Configure device restrictions settings in Microsoft Intune](/intune/device-restrictions-configure).<p>3. Selecione **Propriedades** e selecione **Configurações: Editar**.<p>4. **Expanda Microsoft Defender Antivírus**. <p>5. Habilitar **a proteção entregue na nuvem**.<p>6. No **Prompt users before sample submission** dropdown, select Send all **samples automatically**.<p>7. No menu suspenso **Detectar aplicativos** potencialmente indesejados, selecione **Habilitar** ou **Auditar**.<p>8. Selecione **Revisar + salvar** e, em seguida, escolha **Salvar**.<p>Para obter mais informações sobre perfis de dispositivo do Intune, incluindo como criar e configurar suas configurações, consulte O que são Microsoft Intune [perfis de dispositivo?](/intune/device-profiles).|
|Painel de Controle no Windows     |Siga as diretrizes aqui: [Ativar Microsoft Defender Antivírus](/mem/intune/user-help/turn-on-defender-windows). <p>**OBSERVAÇÃO**: você pode ver *Windows Defender Antivírus* em vez *de Microsoft Defender Antivírus* em algumas versões do Windows.        |
|[Gerenciamento avançado de política de grupo](/microsoft-desktop-optimization-pack/agpm/) <br/>ou<br/>[Console de Gerenciamento de Política de Grupo](use-group-policy-microsoft-defender-antivirus.md)  |1. Vá para `Computer configuration > Administrative templates > Windows components > Microsoft Defender Antivirus` . <p>2. Procure uma política chamada **Desativar Microsoft Defender Antivírus**.<p>3. Escolha **Editar configuração de política** e certifique-se de que a política está desabilitada. Isso permite Microsoft Defender Antivírus. <p>**OBSERVAÇÃO**: você pode ver *Windows Defender Antivírus* em vez *de Microsoft Defender Antivírus* em algumas versões do Windows. |

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-mcafee"></a>Adicionar o Microsoft Defender para Ponto de Extremidade à lista de exclusão da McAfee

Esta etapa do processo de instalação envolve a adição do Defender for Endpoint à lista de exclusão da McAfee e de todos os outros produtos de segurança que sua organização está usando. 

> [!TIP]
> Para obter ajuda para configurar exclusões, consulte a documentação da McAfee, como o seguinte artigo: [McAfee Endpoint Security 10.5.0 - Guia](https://docs.mcafee.com/bundle/endpoint-security-10.5.0-threat-prevention-product-guide-epolicy-orchestrator-windows/page/GUID-71C5FB4B-A143-43E6-8BF0-8B2C16ABE6DA.html)do Produto do Módulo de Prevenção contra Ameaças (McAfee ePolicy Orchestrator) - Windows: Configurando exclusões .

As exclusões específicas a ser configuradas dependem de qual versão do Windows seus pontos de extremidade ou dispositivos estão sendo executados e estão listadas na tabela a seguir:

|SISTEMA OPERACIONAL |Exclusões |
|--|--|
| Windows 10, [versão 1803](/windows/release-health/status-windows-10-1803) ou posterior (Consulte [Windows 10 informações de versão](/windows/release-health/release-information))<p>Windows 10, versão 1703 ou [1709](/windows/release-health/status-windows-10-1709) com [KB4493441](https://support.microsoft.com/help/4493441) instalado <p>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows Servidor, versão 1803](/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<br/>  |
| [Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <p>[Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>[Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<p>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<p>**OBSERVAÇÃO**: onde o Monitoramento de Arquivos Temporários do Host 6\45 pode ser subpastas numeradas diferentes.<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-mcafee-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Adicionar McAfee à lista de exclusões para Microsoft Defender Antivírus

Durante esta etapa do processo de instalação, você adiciona McAfee e suas outras soluções de segurança à lista Microsoft Defender Antivírus exclusão. 

Quando você adiciona [exclusões a Microsoft Defender Antivírus verificações,](configure-exclusions-microsoft-defender-antivirus.md)você deve adicionar exclusões de caminho e processo. 

Você pode escolher entre vários métodos para adicionar suas exclusões Microsoft Defender Antivírus, conforme listado na tabela a seguir:

|Método | O que fazer|
|--|--|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <p>**OBSERVAÇÃO**: o Intune agora faz parte Microsoft Endpoint Manager. |1. Vá para o centro de administração [Microsoft Endpoint Manager e](https://go.microsoft.com/fwlink/?linkid=2109431) entre.<p>2. Selecione **Perfis**  >  **de Configuração de** Dispositivos e selecione o perfil que você deseja configurar.<p>3. Em **Gerenciar**, selecione **Propriedades**. <p>4. Selecione **Configurações: Editar**.<p>5. **Expanda Microsoft Defender Antivírus** e, em seguida, **expanda Microsoft Defender Antivírus Exclusões**.<p>6. Especifique os arquivos e pastas, extensões e processos a ser excluídos Microsoft Defender Antivírus verificações. Para referência, consulte [Microsoft Defender Antivírus exclusões](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions).<p>7. Escolha **Revisar + salvar** e, em seguida, escolha **Salvar**.  |
|[Microsoft Endpoint Configuration Manager](/mem/configmgr/) |1. Usando o [console do Configuration Manager,](/mem/configmgr/core/servers/manage/admin-console)vá para **Ativos** e Conformidade  >  **Endpoint Protection**  >  **Políticas Antimalware** e selecione a política que você deseja modificar. <p>2. Especifique as configurações de exclusão para arquivos e pastas, extensões e processos a ser excluídos Microsoft Defender Antivírus verificações. |
|[Objeto Group Policy](/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](https://technet.microsoft.com/library/cc731212.aspx), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.<p>2. No Editor de Gerenciamento de **Política de Grupo,** acesse **Configuração** do computador e clique em **Modelos Administrativos**.<p>3. Expanda a árvore para Windows **componentes > Microsoft Defender Antivírus > Exclusões**.<br/>**OBSERVAÇÃO**: você pode ver *Windows Defender Antivírus* em vez *de Microsoft Defender Antivírus* em algumas versões do Windows.<p>4. Clique duas vezes na **configuração Exclusões de** Caminho e adicione as exclusões.<br/>- Definir a opção como **Habilitado**.<br/>- Na seção **Opções,** clique em **Mostrar...**.<br/>- Especifique cada pasta em sua própria linha na **coluna Nome do** valor.<br/>- Se você especificar um arquivo, insira um caminho totalmente qualificado para o arquivo, incluindo a letra da unidade, o caminho da pasta, o nome do arquivo e a extensão. Insira **0** na coluna **Valor.**<p>5. Clique em **OK**.<p>6. Clique duas vezes na **configuração Exclusões de** Extensão e adicione as exclusões.<br/>- Definir a opção como **Habilitado**.<br/>- Na seção **Opções,** clique em **Mostrar...**.<br/>- Insira cada extensão de arquivo em sua própria linha na **coluna Nome do** valor.  Insira **0** na coluna **Valor.**<p>7. Clique em **OK**. |
|Objeto de política de grupo local |1. No ponto de extremidade ou dispositivo, abra o Editor de Política de Grupo Local. <p>2. Vá para **Configuração** do Computador  >  **Modelos Administrativos**  >  **Windows Componentes**  >  **Microsoft Defender Antivírus**  >  **Exclusões**. <p>**OBSERVAÇÃO**: você pode ver *Windows Defender Antivírus* em vez *de Microsoft Defender Antivírus* em algumas versões do Windows.<p>3. Especifique seu caminho e exclusões de processo. |
|Chave do Registro |1. Exporte a seguinte chave do Registro: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` .<p>2. Importe a chave do Registro. Aqui estão dois exemplos:<br/>- Caminho local: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- Compartilhamento de rede: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

Lembre-se dos seguintes pontos:

- As exclusões de caminho excluem arquivos específicos e qualquer que seja o acesso a esses arquivos.

- As exclusões de processo excluem o que um processo toca, mas não exclui o processo em si.

- Se você listar cada executável (.exe) como uma exclusão de caminho e uma exclusão de processo, o processo e o que ele toca serão excluídos.

- Listar suas exclusões de processo usando seu caminho completo e não apenas pelo nome. (O método somente nome é menos seguro.)

## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>Configurar grupos de dispositivos, coleções de dispositivos e unidades organizacionais

| Tipo de coleção | O que fazer |
|--|--|
|[Os grupos de](machine-groups.md) dispositivos (anteriormente chamados de grupos de máquinas) permitem que sua equipe de operações de segurança configure recursos de segurança, como investigação e correção automatizadas.<p> Os grupos de dispositivos também são úteis para atribuir acesso a esses dispositivos para que sua equipe de operações de segurança possa realizar ações de correção, se necessário. <p>Os grupos de dispositivos são criados no Central de Segurança do Microsoft Defender. |1. Vá para a Central de Segurança do Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ).<p>2. No painel de navegação à esquerda, escolha **Configurações**  >  **Grupos de** Dispositivo de  >  **Permissões**.  <p>3. Escolha **+ Adicionar grupo de dispositivos**.<p>4. Especifique um nome e uma descrição para o grupo de dispositivos.<p>5. Na lista **Nível de automação,** selecione uma opção. (Recomendamos **Full - correção de ameaças automaticamente**.) Para saber mais sobre os vários níveis de automação, consulte [Como as ameaças são remediadas](automated-investigations.md#how-threats-are-remediated).<p>6. Especifique condições para uma regra correspondente para determinar quais dispositivos pertencem ao grupo de dispositivos. Por exemplo, você pode escolher um domínio, versões do sistema operacional ou até mesmo usar marcas [de dispositivo](machine-tags.md). <p>7. Na guia **Acesso do** usuário, especifique funções que devem ter acesso aos dispositivos incluídos no grupo de dispositivos. <p>8. Escolha **Feito**. |
|[Os conjunto de dispositivos](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) permitem que sua equipe de operações de segurança gerencie aplicativos, implante configurações de conformidade ou instale atualizações de software nos dispositivos de sua organização. <p>Os conjunto de dispositivos são criados usando o [Configuration Manager](/mem/configmgr/). |Siga as etapas em [Criar uma coleção](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create). |
|[As unidades organizacionais](/azure/active-directory-domain-services/create-ou) permitem agrupar logicamente objetos, como contas de usuário, contas de serviço ou contas de computador. Em seguida, você pode atribuir administradores a unidades organizacionais específicas e aplicar a política de grupo para impor configurações direcionadas.<p> As unidades organizacionais são definidas [Azure Active Directory Serviços de Domínio.](/azure/active-directory-domain-services) | Siga as etapas em [Create an Organizational Unit in an Azure Active Directory Domain Services managed domain](/azure/active-directory-domain-services/create-ou). |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>Configurar políticas antimalware e proteção em tempo real

Usando o Configuration Manager e suas coleções de dispositivos, configure suas políticas antimalware.

- Consulte [Create and deploy antimalware policies for Endpoint Protection in Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies).

- Enquanto você cria e configura suas políticas antimalware, revise as configurações de proteção em tempo [real](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) e [habilita](configure-block-at-first-sight-microsoft-defender-antivirus.md)o bloqueio à primeira vista.

> [!TIP]
> Você pode implantar as políticas antes dos dispositivos da sua organização em integração.

## <a name="next-step"></a>Próxima etapa

**Parabéns**! Você concluiu a fase de instalação da [migração da McAfee para o Defender para o Ponto de Extremidade!](mcafee-to-microsoft-defender-migration.md#the-migration-process)

- [Prossiga para a Fase 3: Onboard to Defender for Endpoint](mcafee-to-microsoft-defender-onboard.md)
