---
title: Integração Windows 10 dispositivos para o Microsoft Defender para Ponto de Extremidade por meio da Política de Grupo
description: Use a Política de Grupo para implantar o pacote de configuração em Windows 10 dispositivos para que eles sejam integrados ao serviço.
keywords: configurar dispositivos usando a política de grupo, o gerenciamento de dispositivos, configurar o Microsoft Defender para dispositivos de ponto de extremidade, a integração do Microsoft Defender para dispositivos de ponto de extremidade, a política de grupo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 24b24c634eac7ee125810d96587c9c1e209b6491
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286952"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a>Integração Windows 10 usando a Política de Grupo 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- Política de Grupo
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)

> [!NOTE]
> Para usar atualizações de Política de Grupo (GP) para implantar o pacote, você deve estar Windows Server 2008 R2 ou posterior.
>
> Para o Windows Server 2019, talvez seja necessário substituir o NT AUTHORITY\Well-Known-System-Account por NT AUTHORITY\SYSTEM do arquivo XML que a preferência de Política de Grupo cria.

## <a name="onboard-devices-using-group-policy"></a>Dispositivos integrados usando Política de Grupo

[![Imagem do PDF mostrando os vários caminhos de implantação](images/onboard-gp.png)](images/onboard-gp.png#lightbox)

Confira o [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) ou [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) para ver os vários caminhos na implantação do Defender para o Ponto de Extremidade.

1. Abra o arquivo de pacote de configuração da GP .zip (*WindowsDefenderATPOnboardingPackage.zip*) que você baixou do assistente de integração do serviço. Você também pode obter o pacote de [Central de Segurança do Microsoft Defender](https://securitycenter.windows.com/):

    1. No painel de navegação, selecione **Configurações**  >  **Integração**.

    1. Selecione Windows 10 como o sistema operacional.

    1. No campo **Método de implantação,** selecione **Política de grupo**.

    1. Clique **em Baixar pacote** e salve o .zip arquivo.

2. Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que pode ser acessado pelo dispositivo. Você deve ter uma pasta chamada *OptionalParamsPolicy* e o *arquivo WindowsDefenderATPOnboardingScript.cmd*.

3. Abra o [Console de Gerenciamento de Política](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) de Grupo (GPMC), clique com o botão direito do mouse no Objeto de Política de Grupo (GPO) que você deseja configurar e clique em **Editar**.

4. No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração** do computador, **Preferências** e configurações **do painel de controle.**

5. Clique com o botão direito do mouse em **Tarefas Agendadas,** aponte para **Novo** e clique em Tarefa Imediata (Pelo menos **Windows 7)**.

6. Na janela **Tarefa** aberta, vá para a **guia** Geral. Em **Opções de segurança,** **clique em Alterar Usuário ou Grupo** e digite SISTEMA e clique em Verificar **Nomes,** em **seguida, OK**. NT AUTHORITY\SYSTEM aparece como a conta de usuário que a tarefa executará como.

7. Selecione **Executar se o usuário está conectado ou não** e marque a caixa de seleção Executar com privilégios **mais** altos.

8. Vá até a guia **Ações** e clique em **Novo...** Verifique se **Iniciar um programa** está selecionado no **campo** Ação. Insira o nome do arquivo e o local do *arquivo WindowsDefenderATPOnboardingScript.cmd* compartilhado.

9. Clique **em OK** e feche as janelas do GPMC abertas.

> [!TIP]
> Após a integração do dispositivo, você pode optar por executar um teste de detecção para verificar se o dispositivo está corretamente conectado ao serviço. Para obter mais informações, [consulte Execute a detection test on a newly onboarded Defender for Endpoint device](run-detection-test.md).

## <a name="additional-defender-for-endpoint-configuration-settings"></a>Configurações adicionais do Defender para Ponto de Extremidade
Para cada dispositivo, você pode determinar se amostras podem ser coletadas do dispositivo quando uma solicitação é feita por meio Central de Segurança do Microsoft Defender enviar um arquivo para análise profunda.

Você pode usar a Política de Grupo (GP) para definir configurações, como configurações para o compartilhamento de exemplo usado no recurso de análise profunda.

### <a name="configure-sample-collection-settings"></a>Configurar configurações de coleção de exemplos

1. Em seu dispositivo de gerenciamento de GP, copie os seguintes arquivos do pacote de configuração:

    - Copie _AtpConfiguration.admx_ em _C: \\ Windows \\ PolicyDefinitions_

    - Copiar _AtpConfiguration.adml_ em _C: \\ Windows \\ PolicyDefinitions \\ en-US_

    Se você estiver usando um Armazenamento Central para Modelos [Administrativos](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)de Política de Grupo, copie os seguintes arquivos do pacote de configuração:

    - Copiar _AtpConfiguration.admx_ em _\\ \\ \<forest.root\> \\ Políticas SysVol \\ \<forest.root\> \\ \\ PolicyDefinitions_

    - Copiar _AtpConfiguration.adml_ em _\\ \\ \<forest.root\> \\ Políticas SysVol \\ \<forest.root\> \\ \\ PolicyDefinitions \\ en-US_

2. Abra o [Console de Gerenciamento de Política de Grupo](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11), clique com o botão direito do mouse no GPO que você deseja configurar e clique em **Editar**.

3. No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do computador**.

4. Clique **em Políticas** e, em **seguida, modelos administrativos.**

5. Clique **Windows componentes e,** **em seguida, Windows Defender SmartScreen**.

6. Escolha habilitar ou desabilitar o compartilhamento de exemplo de seus dispositivos.

> [!NOTE]
> Se você não definir um valor, o valor padrão será habilitar a coleção de exemplos.

## <a name="other-recommended-configuration-settings"></a>Outras configurações recomendadas

### <a name="update-endpoint-protection-configuration"></a>Atualizar a configuração de proteção do ponto de extremidade

Depois de configurar o script de integração, continue editando a mesma política de grupo para adicionar configurações de proteção de ponto de extremidade. Execute as edições de política de grupo de um sistema que Windows 10 ou o Server 2019 para garantir que você tenha todos os recursos de Microsoft Defender Antivírus necessários. Talvez seja necessário fechar e reabrir o objeto de política de grupo para registrar as configurações do Defender ATP.

Todas as políticas estão localizadas em `Computer Configuration\Policies\Administrative Templates` .

**Local da política:** \Windows Components\Windows Defender ATP

Política | Setting
:---|:---
Enable\Disable Sample collection| Habilitado - verificado "Habilitar coleta de exemplo em máquinas"

<br>

**Local da política:** \Windows Components\Microsoft Defender Antivírus

Política | Setting
:---|:---
Configurar a detecção para aplicativos potencialmente indesejados | Habilitado, Bloqueado

<br>

**Local da política:** \Windows Components\Microsoft Defender Antivírus\MAPS

Política | Setting
:---|:---
Ingressar no Microsoft MAPS | MAPAs avançados e habilitados
Enviar amostras de arquivo quando uma análise posterior for necessária | Habilitado, Enviar amostras seguras

<br>

**Local da política:** \Windows Components\Microsoft Defender Antivírus\Proteção em tempo real

Política | Setting
:---|:---
Desativar a proteção em tempo real|Desabilitado
Ativar o monitoramento de comportamento|Habilitado
Examinar todos os arquivos e anexos baixados|Habilitado
Monitorar atividades de arquivo e programa em seu computador|Habilitado

<br>

**Local da política:** \Windows Components\Microsoft Defender Antivírus\Scan

Essas configurações configuram verificações periódicas do ponto de extremidade. Recomendamos a realização de uma verificação rápida semanal, permitindo desempenho.

Política | Setting 
:---|:---
Verifique a inteligência de segurança de vírus e spyware mais recente antes de executar uma verificação agendada |Habilitado

<br>

**Local da política:** \Windows Components\Microsoft Defender Antivírus\Microsoft Defender Exploit Guard\Redução de Superfície de Ataque

Obter a lista atual de GUIDs de redução de superfície de ataque de Personalizar regras de redução [de superfície de ataque](customize-attack-surface-reduction.md)

1. Abra a **política Configurar Redução de Superfície de** Ataque.

1. Selecione **Habilitado**.

1. Selecione o **botão Mostrar.**

1. Adicione cada GUID no campo **Nome do** Valor com um Valor de 2.

   Isso configurará cada um deles apenas para auditoria.

   ![Imagem da configuração de redução de superfície de ataque](images/asr-guid.png)

Política | Setting
:---|:---
Configurar acesso controlado a pastas| Habilitado, Modo de Auditoria

## <a name="offboard-devices-using-group-policy"></a>Dispositivos offboard usando a Política de Grupo

Por motivos de segurança, o pacote usado para dispositivos offboard expirará 30 dias após a data em que foi baixado. Os pacotes de offboard expirados enviados para um dispositivo serão rejeitados. Ao baixar um pacote de offboard, você será notificado sobre a data de expiração dos pacotes e ele também será incluído no nome do pacote.

> [!NOTE]
> As políticas de integração e de offboard não devem ser implantadas no mesmo dispositivo ao mesmo tempo, caso contrário, isso causará colisões imprevisíveis.

1. Obter o pacote de offboard de [Central de Segurança do Microsoft Defender](https://securitycenter.windows.com/):

    1. No painel de navegação, selecione **Configurações**  >  **Offboarding**.

    1. Selecione Windows 10 como o sistema operacional.

    1. No campo **Método de implantação,** selecione **Política de grupo**.

    1. Clique **em Baixar pacote** e salve o .zip arquivo.

2. Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que pode ser acessado pelo dispositivo. Você deve ter um arquivo chamado *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

3. Abra o [Console de Gerenciamento de Política](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) de Grupo (GPMC), clique com o botão direito do mouse no Objeto de Política de Grupo (GPO) que você deseja configurar e clique em **Editar**.

4. No Editor **de Gerenciamento de Política de Grupo,** vá para Configuração do **computador,** **Preferências** e configurações **do painel de controle.**

5. Clique com o botão direito do mouse **em Tarefas agendadas,** aponte para **Novo** e clique em **Tarefa Imediata.**

6. Na janela **Tarefa** aberta, vá para a **guia** Geral. Escolha a conta de usuário do SISTEMA local (BUILTIN\SYSTEM) em **Opções de segurança.**

7. Selecione **Executar se o usuário está conectado ou não** e marque a caixa de seleção Executar com privilégios **mais** altos.

8. Vá até a guia **Ações** e clique em **Novo...**. Verifique se **Iniciar um programa** está selecionado no **campo** Ação. Insira o nome do arquivo e o local do arquivo  *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* compartilhado.

9. Clique **em OK** e feche as janelas do GPMC abertas.

> [!IMPORTANT]
> O offboard faz com que o dispositivo pare de enviar dados do sensor para o portal, mas os dados do dispositivo, incluindo a referência a todos os alertas que ele teve, serão mantidos por até 6 meses.

## <a name="monitor-device-configuration"></a>Monitorar a configuração do dispositivo

Com a Política de Grupo, não há uma opção para monitorar a implantação de políticas nos dispositivos. O monitoramento pode ser feito diretamente no portal ou usando as diferentes ferramentas de implantação.

## <a name="monitor-devices-using-the-portal"></a>Monitorar dispositivos usando o portal

1. Vá para [Central de Segurança do Microsoft Defender](https://securitycenter.windows.com/).
2. Clique **em Lista de dispositivos**.
3. Verifique se os dispositivos estão aparecendo.

> [!NOTE]
> Pode levar vários dias para que os dispositivos comecem a ser exibidos na lista **Dispositivos.** Isso inclui o tempo necessário para que as políticas sejam distribuídas para o dispositivo, o tempo necessário para o usuário fazer o login e o tempo necessário para que o ponto de extremidade comece a relatar.

## <a name="related-topics"></a>Tópicos relacionados

- [Integração Windows 10 dispositivos usando Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel](configure-endpoints-mdm.md)
- [Integrar dispositivos Windows 10 usando um script local](configure-endpoints-script.md)
- [Dispositivos integrados de VDI (Virtual Desktop Infrastructure) não persistente](configure-endpoints-vdi.md)
- [Executar um teste de detecção em um Microsoft Defender recém-integrado para dispositivos de ponto de extremidade](run-detection-test.md)
- [Solucionar problemas de integração do Microsoft Defender para pontos de extremidade](troubleshoot-onboarding.md)
