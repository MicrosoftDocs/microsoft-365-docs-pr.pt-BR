---
title: Integrar dispositivos Windows 10 por meio da Política de Grupo
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
description: Use a Política de Grupo para implantar o pacote de configuração em dispositivos Windows 10 para que eles sejam onboarded ao serviço.
ms.openlocfilehash: a9e91f41b6e86e9f75d79d420c0ee830f1e3acf3
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769384"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a>Integração de dispositivos Windows 10 usando Política de Grupo 

**Aplica-se a:**

- [Prevenção contra perda de dados de ponto de extremidade (DLP) do Microsoft 365](/microsoft-365/compliance/endpoint-dlp-learn-about)
- Política de Grupo

> [!NOTE]
> Para usar atualizações de Política de Grupo (GP) para implantar o pacote, você deve estar no Windows Server 2008 R2 ou posterior.

> Para o Windows Server 2019, talvez seja necessário substituir NT AUTHORITY\Well-Known-System-Account por NT AUTHORITY\SYSTEM do arquivo XML que a preferência de Política de Grupo cria.

## <a name="onboard-devices-using-group-policy"></a>Dispositivos de integração usando a Política de Grupo

1. Abra o arquivo .zip do pacote de configuração da GP *(DeviceComplianceOnboardingPackage.zip)* que você baixou do assistente de integração de serviço. Você também pode obter o pacote no Centro [de Conformidade da Microsoft](https://compliance.microsoft.com/compliancesettings/deviceonboarding)

2. No painel de navegação, selecione **Configurações de**  >  **Integração de Dispositivo.**

3. No campo **Método de implantação,** selecione **Política de grupo.**

4. Clique **em Baixar pacote** e salve o arquivo .zip.

5. Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que possa ser acessado pelo dispositivo. Você deve ter uma pasta chamada *OptionalParamsPolicy* e o arquivo *DeviceComplianceLocalOnboardingScript.cmd*.

6. Abra o [Console de](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) Gerenciamento de Política de Grupo (GPMC), clique com o botão direito do mouse no Objeto de Política de Grupo (GPO) que você deseja configurar e clique em **Editar.**

7. No **Editor de Gerenciamento de Política de** Grupo, vá para **Configuração do** computador, **preferências** e, em seguida, configurações do painel **de controle.**

8. Clique com o botão direito **do** mouse em Tarefas Agendadas, aponte para **Novo** e clique em Tarefa Imediata (pelo menos **Windows 7).**

9. Na janela **Tarefa** que é aberta, vá para a **guia** Geral. Em **Opções de segurança,** **clique em Alterar Usuário ou Grupo** e digite SISTEMA e clique em Verificar **Nomes** e **OK.** NT AUTHORITY\SYSTEM aparece como a conta de usuário como a tarefa será executado.

10. Marque **Executar se o usuário está conectado ou não e** marque a caixa de seleção Executar com privilégios mais **altos.**

11. Vá para a **guia Ações** e clique em **Novo...** **Certifique-se de que Iniciar um** programa está selecionado no **campo** Ação. Insira o nome e o local do arquivo *compartilhado WindowsDefenderATPOnboardingScript.cmd.*

12. Clique **em OK** e feche as janelas abertas do GPMC.


## <a name="offboard-devices-using-group-policy"></a>Desligar dispositivos usando a Política de Grupo
Por motivos de segurança, o pacote usado para dispositivos offboard expirará 30 dias após a data em que foi baixado. Os pacotes de reexenciamento expirados enviados para um dispositivo serão rejeitados. Ao baixar um pacote de descarregamento, você será notificado sobre a data de vencimento dos pacotes e ele também será incluído no nome do pacote.

> [!NOTE]
> As políticas de integração e de transferência não devem ser implantadas no mesmo dispositivo ao mesmo tempo, caso contrário, isso causará colisões imprevisíveis.

1. Obter o pacote de redação do Centro [de Conformidade da Microsoft.](https://compliance.microsoft.com/compliancesettings/deviceonboarding)

2. No painel de navegação, selecione **Configurações**  >  **//Integração de**  >  **dispositivos à rebordagem.**

3. No campo **Método de implantação,** selecione **Política de grupo.**

4. Clique **em Baixar pacote** e salve o arquivo .zip.

5. Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que possa ser acessado pelo dispositivo. Você deve ter um arquivo *chamado DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd.*

6. Abra o [Console de](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) Gerenciamento de Política de Grupo (GPMC), clique com o botão direito do mouse no Objeto de Política de Grupo (GPO) que você deseja configurar e clique em **Editar.**

7. No **Editor de Gerenciamento de Política de** Grupo, vá para a configuração do **computador,** **preferências** e, em seguida, configurações do painel **de controle.**

8. Clique com o botão direito **do mouse em Tarefas** Agendadas, aponte para **Novo** e clique em **Tarefa Imediata.**

9. Na janela **Tarefa** que é aberta, vá para a **guia** Geral. Escolha a conta de usuário do SISTEMA local (BUILTIN\SYSTEM) em **Opções de segurança.**

10. Marque **Executar se o usuário está conectado ou não** e marque a caixa de seleção Executar com privilégios **mais** altos.

11. Vá para a **guia Ações** e clique em **Novo...**. **Certifique-se de que Iniciar um** programa está selecionado no **campo** Ação. Insira o nome e o local do arquivo  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* compartilhado.

12. Clique **em OK** e feche as janelas abertas do GPMC.

> [!IMPORTANT]
> A reação faz com que o dispositivo pare de enviar dados do sensor para o portal, mas os dados do dispositivo.


## <a name="monitor-device-configuration"></a>Monitorar a configuração do dispositivo
Com a Política de Grupo, não há uma opção para monitorar a implantação de políticas nos dispositivos. O monitoramento pode ser feito diretamente no portal ou usando as diferentes ferramentas de implantação.

## <a name="monitor-devices-using-the-portal"></a>Monitorar dispositivos usando o portal
1. Vá para o [Centro de Conformidade da Microsoft.](https://compliance.microsoft.com/)
2. Clique **na lista Dispositivos.**
3. Verifique se os dispositivos estão aparecendo.

> [!NOTE]
> Pode levar vários dias para que os dispositivos comecem a ser mostrados na lista **de dispositivos.** Isso inclui o tempo necessário para que as políticas sejam distribuídas para o dispositivo, o tempo necessário para o usuário fazer o login e o tempo necessário para o ponto de extremidade começar a relatar.


## <a name="related-topics"></a>Tópicos relacionados
- [Integração de dispositivos Windows 10 usando o Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel](dlp-configure-endpoints-mdm.md)
- [Integrar dispositivos Windows 10 usando um script local](dlp-configure-endpoints-script.md)
- [Integrar dispositivos não persistentes de VDI (virtual desktop infrastructure)](dlp-configure-endpoints-vdi.md)
- [Executar um teste de detecção em dispositivos Microsoft Defender ATP recém-integrados](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Solucionar problemas de integração da Proteção Avançada contra Ameaças do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
