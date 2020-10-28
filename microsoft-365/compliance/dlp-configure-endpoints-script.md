---
title: Dispositivos integrados do Windows 10 usando um script local
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
description: Use um script local para implantar o pacote de configuração nos dispositivos de modo que eles sejam incluídos no serviço.
ms.openlocfilehash: 74152f9488623d39e32ee4e47a452bd1daea28c7
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769390"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a>Dispositivos integrados do Windows 10 usando um script local

**Aplica-se a:**

- [Prevenção de perda de dados do Microsoft 365 EndPoint (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)

Você também pode manualmente embutir dispositivos individuais na prevenção de perda de dados de ponto de extremidade da Microsoft 365. Você pode querer fazer isso primeiro ao testar o serviço antes de confirmar a integração de todos os dispositivos em sua rede.

> [!IMPORTANT]
> Este script foi otimizado para uso em até 10 dispositivos.
>
> Para implantar em escala, use [outras opções de implantação](dlp-configure-endpoints.md). Por exemplo, você pode implantar um script de integração em mais de 10 dispositivos em produção com o script disponível em [dispositivos Windows 10 integrados usando a política de grupo](dlp-configure-endpoints-gp.md).

## <a name="onboard-devices"></a>Dispositivos integrados
 
1.  Abra o arquivo. zip do pacote de configuração GP ( *DeviceComplianceOnboardingPackage.zip* ) que você baixou a partir do assistente de integração de serviço. Você também pode obter o pacote do [centro de conformidade da Microsoft](https://compliance.microsoft.com)

2. No painel de navegação, selecione **Settings**  >  **integração do dispositivo** de configurações.

3. No campo **método de implantação** , selecione **script local** .

4. Clique em **baixar pacote** e salve o arquivo. zip.
  
5. Extraia o conteúdo do pacote de configuração para um local no dispositivo que você deseja integrar (por exemplo, a área de trabalho). Você deve ter um arquivo chamado *DeviceOnboardingScript. cmd* .

6.  Abra um prompt de linha de comando com privilégios elevados no dispositivo e execute o script:

7.  Vá para **Iniciar** e digite **cmd** .

8.  Clique com o botão direito do mouse em **prompt de comando** e selecione **Executar como administrador** .

![Menu iniciar janela apontando para executar como administrador](../media/dlp-run-as-admin.png)

9.  Digite o local do arquivo de script. Se você copiou o arquivo para a área de trabalho, digite: *%USERPROFILE%\Desktop\WindowsDefenderATPOnboardingScript.cmd*

10.  Pressione a tecla **Enter** ou clique em **OK** .

Para obter informações sobre como você pode validar manualmente se o dispositivo está em conformidade e relata corretamente os dados do sensor, confira [solucionar problemas de integração da proteção avançada contra ameaças do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).

## <a name="offboard-devices-using-a-local-script"></a>Dispositivos externamente usando um script local
Por motivos de segurança, o pacote usado para os dispositivos do externamente expirará 30 dias após a data em que foi baixado. Os pacotes de remoção expirados enviados para um dispositivo serão rejeitados. Ao baixar um pacote de remoção, você será notificado sobre a data de expiração dos pacotes e ele também será incluído no nome do pacote.

> [!NOTE]
> As políticas de integração e remoção não devem ser implantadas no mesmo dispositivo ao mesmo tempo, caso contrário, isso causará colisões imprevisíveis.

1. Obter o pacote de remoção do [centro de conformidade da Microsoft](https://compliance.microsoft.com)

2. No painel de navegação, selecione **configurações** de  >  **remoção de dispositivo** .

3. No campo **método de implantação** , selecione **script local** .

4. Clique em **baixar pacote** e salve o arquivo. zip.

5. Extraia o conteúdo do arquivo. zip para um local compartilhado e somente leitura que possa ser acessado pelos dispositivos. Você deve ter um arquivo chamado *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* .

6.  Abra um prompt de linha de comando com privilégios elevados no dispositivo e execute o script:

7.  Vá para **Iniciar** e digite **cmd** .

8.  Clique com o botão direito do mouse em **prompt de comando** e selecione **Executar como administrador** .

![Menu iniciar janela apontando para executar como administrador](../media/dlp-run-as-admin.png)

9.  Digite o local do arquivo de script. Se você copiou o arquivo para a área de trabalho, digite: *%userprofile%\desktop\ WindowsDefenderATPOffboardingScript_valid_until_YYYY-mm-dd. cmd*

10.  Pressione a tecla **Enter** ou clique em **OK** .

> [!IMPORTANT]
> A remoção faz com que o dispositivo pare de enviar dados de sensor para o Portal.


## <a name="monitor-device-configuration"></a>Monitorar a configuração do dispositivo
Você pode seguir as diferentes etapas de verificação no [solucionar problemas de integração] (( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) para verificar se o script foi concluído com êxito e se o agente está em execução.

O monitoramento também pode ser feito diretamente no portal ou usando as diferentes ferramentas de implantação.

### <a name="monitor-devices-using-the-portal"></a>Monitorar dispositivos usando o portal
1. Vá para [o centro de conformidade da Microsoft 365](https://compliance.microsoft.com).

2. Escolha **configurações**  >  dispositivos de **integração de dispositivos**  >  **Devices** .

3. Verifique se os dispositivos estão aparecendo.


## <a name="related-topics"></a>Tópicos relacionados
- [Dispositivos Windows 10 integrados usando a política de grupo](dlp-configure-endpoints-gp.md)
- [Dispositivos Windows 10 integrados usando o Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Dispositivos do Windows 10 integrados usando ferramentas de gerenciamento de dispositivos móveis](dlp-configure-endpoints-mdm.md)
- [Dispositivos não persistentes de infraestrutura de área de trabalho virtual (VDI)](dlp-configure-endpoints-vdi.md)
- [Executar um teste de detecção em um dispositivo Microsoft defender ATP recentemente integrado](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Solucionar problemas de integração com a proteção avançada contra ameaças do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
