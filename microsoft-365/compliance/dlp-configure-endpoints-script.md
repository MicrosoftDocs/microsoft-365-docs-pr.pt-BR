---
title: Integrar dispositivos Windows 10 usando um script local
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Use um script local para implantar o pacote de configuração em dispositivos para que eles sejam integrados ao serviço.
ms.openlocfilehash: e9efa76af72f9169bdec1acf35d72066ac0a776e
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893302"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a>Integrar dispositivos Windows 10 usando um script local

**Aplica-se a:**

- [Microsoft 365 Prevenção contra perda de dados do ponto de extremidade (DLP)](./endpoint-dlp-learn-about.md)

Você também pode integrar manualmente dispositivos individuais para Microsoft 365 prevenção contra perda de dados do ponto de extremidade. Você pode querer fazer isso primeiro ao testar o serviço antes de se comprometer a integração de todos os dispositivos em sua rede.

> [!IMPORTANT]
> Esse script foi otimizado para uso em até 10 dispositivos.
>
> Para implantar em escala, use [outras opções de implantação.](dlp-configure-endpoints.md) Por exemplo, você pode implantar um script de integração em mais de 10 dispositivos em produção com o script disponível em Windows 10 de integração usando a Política [de Grupo](dlp-configure-endpoints-gp.md).

## <a name="onboard-devices"></a>Dispositivos de integração
 
1.  Abra o arquivo de pacote de configuração da GP .zip (*DeviceComplianceOnboardingPackage.zip*) que você baixou do assistente de integração do serviço. Você também pode obter o pacote do [Centro de Conformidade da Microsoft](https://compliance.microsoft.com)

2. No painel de navegação, **selecione** Configurações  >  **Integração do dispositivo**.

3. No campo **Método de Implantação,** selecione **Script Local**.

4. Clique **em Baixar pacote** e salve o .zip arquivo.
  
5. Extraia o conteúdo do pacote de configuração para um local no dispositivo que você deseja integrar (por exemplo, a Área de Trabalho). Você deve ter um arquivo chamado *DeviceOnboardingScript.cmd*.

6.  Abra um prompt de linha de comando elevada no dispositivo e execute o script:

7.  Vá para **Iniciar** e digite **cmd**.

8.  Clique com o botão direito do mouse em **Prompt de Comando** e selecione **Executar como administrador**.

    ![Menu Iniciar janela apontando para Executar como administrador](../media/dlp-run-as-admin.png)

9.  Digite o local do arquivo de script. Se você copiou o arquivo para a área de trabalho, *digite: %userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*

10.  Pressione a **tecla Enter** ou clique em **OK**.

Para obter informações sobre como você pode validar manualmente se o dispositivo é compatível e relata corretamente os dados do sensor, consulte, Solucionar Proteção Avançada contra Ameaças do Microsoft Defender [problemas de integração](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).

## <a name="offboard-devices-using-a-local-script"></a>Dispositivos offboard usando um script local
Por motivos de segurança, o pacote usado para dispositivos offboard expirará 30 dias após a data em que foi baixado. Os pacotes de offboard expirados enviados para um dispositivo serão rejeitados. Ao baixar um pacote de offboard, você será notificado sobre a data de expiração dos pacotes e ele também será incluído no nome do pacote.

> [!NOTE]
> As políticas de integração e de offboard não devem ser implantadas no mesmo dispositivo ao mesmo tempo, caso contrário, isso causará colisões imprevisíveis.

1. Obter o pacote de offboard do [Centro de Conformidade da Microsoft](https://compliance.microsoft.com)

2. No painel de navegação, selecione **Configurações**  >  **offboard do dispositivo**.

3. No campo **Método de Implantação,** selecione **Script Local**.

4. Clique **em Baixar pacote** e salve o .zip arquivo.

5. Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que pode ser acessado pelos dispositivos. Você deve ter um arquivo chamado *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

6.  Abra um prompt de linha de comando elevada no dispositivo e execute o script:

7.  Vá para **Iniciar** e digite **cmd**.

8.  Clique com o botão direito do mouse em **Prompt de Comando** e selecione **Executar como administrador**.

    ![Menu Iniciar janela apontando para Executar como administrador](../media/dlp-run-as-admin.png)

9.  Digite o local do arquivo de script. Se você copiou o arquivo para a área de trabalho, *digite: %userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*

10.  Pressione a **tecla Enter** ou clique em **OK**.

> [!IMPORTANT]
> O offboard faz com que o dispositivo pare de enviar dados do sensor para o portal.


## <a name="monitor-device-configuration"></a>Monitorar a configuração do dispositivo
Você pode seguir as diferentes etapas de verificação no [Solucionar problemas de integração](( para verificar se o script foi concluído com êxito e https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) se o agente está em execução.

O monitoramento também pode ser feito diretamente no portal ou usando as diferentes ferramentas de implantação.

### <a name="monitor-devices-using-the-portal"></a>Monitorar dispositivos usando o portal
1. Vá para [Microsoft 365 Centro de Conformidade.](https://compliance.microsoft.com)

2. Escolha **Configurações**  >  **dispositivos de integração de**  >  **dispositivos**.

3. Verifique se os dispositivos estão aparecendo.


## <a name="related-topics"></a>Tópicos relacionados
- [Integração Windows 10 usando a Política de Grupo](dlp-configure-endpoints-gp.md)
- [Integração Windows 10 dispositivos usando Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel](dlp-configure-endpoints-mdm.md)
- [Dispositivos integrados de VDI (Virtual Desktop Infrastructure) não persistente](dlp-configure-endpoints-vdi.md)
- [Executar um teste de detecção em um dispositivo recém-integrado do Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Solucionar Proteção Avançada contra Ameaças do Microsoft Defender problemas de integração](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)