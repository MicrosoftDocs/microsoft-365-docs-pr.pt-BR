---
title: Dispositivos Windows 10 integrados por meio da política de grupo
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Use a política de grupo para implantar o pacote de configuração em dispositivos Windows 10 para que eles sejam integrados ao serviço.
ms.openlocfilehash: a9e91f41b6e86e9f75d79d420c0ee830f1e3acf3
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769384"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a>Dispositivos Windows 10 integrados usando a política de grupo 

**Aplica-se a:**

- [Prevenção de perda de dados do Microsoft 365 EndPoint (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)
- Política de Grupo

> [!NOTE]
> Para usar atualizações de política de grupo (GP) para implantar o pacote, você deve estar no Windows Server 2008 R2 ou posterior.

> Para o Windows Server 2019, talvez seja necessário substituir o NT AUTHORITY\Well-Known-System-Account pelo NT AUTHORITY\SYSTEM do arquivo XML que a preferência de política de grupo cria.

## <a name="onboard-devices-using-group-policy"></a>Dispositivos integrados usando a política de grupo

1. Abra o arquivo. zip do pacote de configuração GP ( *DeviceComplianceOnboardingPackage.zip* ) que você baixou a partir do assistente de integração de serviço. Você também pode obter o pacote do [centro de conformidade da Microsoft](https://compliance.microsoft.com/compliancesettings/deviceonboarding)

2. No painel de navegação, selecione **Settings**  >  **integração do dispositivo** de configurações.

3. No campo **método de implantação** , selecione **política de grupo** .

4. Clique em **baixar pacote** e salve o arquivo. zip.

5. Extraia o conteúdo do arquivo. zip para um local compartilhado e somente leitura que possa ser acessado pelo dispositivo. Você deve ter uma pasta chamada *OptionalParamsPolicy* e o arquivo *DeviceComplianceLocalOnboardingScript. cmd* .

6. Abra o GPMC ( [console de gerenciamento de política de grupo](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) ), clique com o botão direito do mouse no objeto de diretiva de grupo (GPO) que você deseja configurar e clique em **Editar** .

7. No **Editor de gerenciamento de política de grupo** , vá para configuração do **computador** , **preferências** e, em seguida, configurações do **painel de controle** .

8. Clique com o botão direito do mouse em **tarefas agendadas** , aponte para **novo** e clique em **tarefa imediata (pelo menos Windows 7)** .

9. Na janela de **tarefas** que é aberta, vá para a guia **geral** . Em **Opções de segurança** , clique em **Alterar usuário ou grupo** e digite System e clique em **verificar nomes** e em **OK** . NT AUTHORITY\SYSTEM será exibido como a conta de usuário na qual a tarefa será executada.

10. Selecione **executar se o usuário está conectado ou não** e marque a caixa de seleção **executar com privilégios mais altos** .

11. Vá até a guia **ações** e clique em **novo..** . Certifique-se de que **Iniciar um programa** está selecionado no campo de **ação** . Insira o nome do arquivo e o local do arquivo *WindowsDefenderATPOnboardingScript. cmd* compartilhado.

12. Clique em **OK** e feche todas as janelas do GPMC abertas.


## <a name="offboard-devices-using-group-policy"></a>Dispositivos externamente usando a política de grupo
Por motivos de segurança, o pacote usado para os dispositivos do externamente expirará 30 dias após a data em que foi baixado. Os pacotes de remoção expirados enviados para um dispositivo serão rejeitados. Ao baixar um pacote de remoção, você será notificado sobre a data de expiração dos pacotes e ele também será incluído no nome do pacote.

> [!NOTE]
> As políticas de integração e remoção não devem ser implantadas no mesmo dispositivo ao mesmo tempo, caso contrário, isso causará colisões imprevisíveis.

1. Obtenha o pacote de remoção do [centro de conformidade da Microsoft](https://compliance.microsoft.com/compliancesettings/deviceonboarding).

2. No painel de navegação, selecione **configurações**  >  **//Device** de  >  **remoção de integração** .

3. No campo **método de implantação** , selecione **política de grupo** .

4. Clique em **baixar pacote** e salve o arquivo. zip.

5. Extraia o conteúdo do arquivo. zip para um local compartilhado e somente leitura que possa ser acessado pelo dispositivo. Você deve ter um arquivo chamado *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* .

6. Abra o GPMC ( [console de gerenciamento de política de grupo](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) ), clique com o botão direito do mouse no objeto de diretiva de grupo (GPO) que você deseja configurar e clique em **Editar** .

7. No **Editor de gerenciamento de política de grupo** , vá para configuração do **computador,** **preferências** e, em seguida, configurações do **painel de controle** .

8. Clique com o botão direito do mouse em **tarefas agendadas** , aponte para **novo** e clique em **tarefa imediata** .

9. Na janela de **tarefas** que é aberta, vá para a guia **geral** . Escolha a conta de usuário do sistema local (BUILTIN\SYSTEM) em **Opções de segurança** .

10. Selecione **executar se o usuário está conectado ou não** e marque a caixa de seleção **executar com privilégios mais altos** .

11. Vá até a guia **ações** e clique em **novo..** .. Certifique-se de que **Iniciar um programa** está selecionado no campo de **ação** . Insira o nome do arquivo e o local do arquivo compartilhado  *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* .

12. Clique em **OK** e feche todas as janelas do GPMC abertas.

> [!IMPORTANT]
> A remoção faz com que o dispositivo pare de enviar dados de sensor para o portal, mas dados do dispositivo.


## <a name="monitor-device-configuration"></a>Monitorar a configuração do dispositivo
Com a política de grupo, não há uma opção para monitorar a implantação de políticas nos dispositivos. O monitoramento pode ser feito diretamente no portal ou usando as diferentes ferramentas de implantação.

## <a name="monitor-devices-using-the-portal"></a>Monitorar dispositivos usando o portal
1. Vá para [o centro de conformidade da Microsoft](https://compliance.microsoft.com/).
2. Clique em lista de **dispositivos** .
3. Verifique se os dispositivos estão aparecendo.

> [!NOTE]
> Pode levar vários dias para os dispositivos começarem a ser exibidos na **lista de dispositivos** . Isso inclui o tempo que leva para que as políticas sejam distribuídas para o dispositivo, o tempo que leva antes que o usuário faça logon e o tempo que leva para o ponto de extremidade para iniciar o relatório.


## <a name="related-topics"></a>Tópicos relacionados
- [Dispositivos Windows 10 integrados usando o Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Dispositivos do Windows 10 integrados usando ferramentas de gerenciamento de dispositivos móveis](dlp-configure-endpoints-mdm.md)
- [Dispositivos integrados do Windows 10 usando um script local](dlp-configure-endpoints-script.md)
- [Dispositivos não persistentes de infraestrutura de área de trabalho virtual (VDI)](dlp-configure-endpoints-vdi.md)
- [Executar um teste de detecção em um dispositivo Microsoft defender ATP recentemente integrado](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Solucionar problemas de integração com a proteção avançada contra ameaças do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
