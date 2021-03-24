---
title: Integrar dispositivos Windows 10 usando um script local
description: Use um script local para implantar o pacote de configuração em dispositivos para que eles sejam integrados ao serviço.
keywords: configurar dispositivos usando um script local, gerenciamento de dispositivos, configurar dispositivos Windows ATP, configurar o Microsoft Defender para dispositivos de ponto de extremidade
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
ms.technology: mde
ms.openlocfilehash: 77473df9cc3e0e98efac8eaacd0a51b551bc3258
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054311"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a>Integrar dispositivos Windows 10 usando um script local

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

Você também pode fazer a integração manual de dispositivos individuais no Defender for Endpoint. Você pode querer fazer isso primeiro ao testar o serviço antes de se comprometer a integração de todos os dispositivos em sua rede.

> [!IMPORTANT]
> Esse script foi otimizado para uso em até 10 dispositivos.
>
> Para implantar em escala, use [outras opções de implantação.](configure-endpoints.md) Por exemplo, você pode implantar um script de integração em mais de 10 dispositivos em produção com o script disponível em dispositivos [Do Windows 10](configure-endpoints-gp.md)de integração usando a Política de Grupo .

## <a name="onboard-devices"></a>Dispositivos de integração 

[![Imagem do PDF mostrando os vários caminhos de implantação](images/onboard-script.png)](images/onboard-script.png#lightbox)


Confira o [PDF ou](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  o  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) para ver os vários caminhos na implantação do Defender para o Ponto de Extremidade. 


1.  Abra o arquivo .zip do pacote de configuração da GP (*WindowsDefenderATPOnboardingPackage.zip*) que você baixou do assistente de integração do serviço. Você também pode obter o pacote do [Centro de Segurança do Microsoft Defender](https://securitycenter.windows.com/):

    1. No painel de navegação, selecione **Configurações**  >  **Integração**.

    1. Selecione Windows 10 como o sistema operacional.

    1. No campo **Método de Implantação,** selecione **Script Local**.

    1. Clique **em Baixar pacote** e salve o arquivo .zip.

  
2.  Extraia o conteúdo do pacote de configuração para um local no dispositivo que você deseja integrar (por exemplo, a Área de Trabalho). Você deve ter um arquivo chamado *WindowsDefenderATPOnboardingScript.cmd*.

3.  Abra um prompt de linha de comando elevada no dispositivo e execute o script:

    1.  Vá para **Iniciar** e digite **cmd**.

    1.  Clique com o botão direito do mouse em **Prompt de Comando** e selecione **Executar como administrador**.

        ![Menu Iniciar janela apontando para Executar como administrador](images/run-as-admin.png)

4.  Digite o local do arquivo de script. Se você copiou o arquivo para a área de trabalho, *digite: %userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*

5.  Pressione a **tecla Enter** ou clique em **OK**.

Para obter informações sobre como você pode validar manualmente se o dispositivo é compatível e relata corretamente os dados do sensor, consulte Solução de problemas de integração do Microsoft Defender para Ponto [de Extremidade.](troubleshoot-onboarding.md)


>[!TIP]
> Após a integração do dispositivo, você pode optar por executar um teste de detecção para verificar se um dispositivo está corretamente conectado ao serviço. Para obter mais informações, [consulte Run a detection test on a newly onboarded Microsoft Defender for Endpoint endpoint endpoint endpoint](run-detection-test.md).

## <a name="configure-sample-collection-settings"></a>Configurar configurações de coleção de exemplos
Para cada dispositivo, você pode definir um valor de configuração para determinar se amostras podem ser coletadas do dispositivo quando uma solicitação é feita por meio do Centro de Segurança do Microsoft Defender para enviar um arquivo para análise profunda.

Você pode configurar manualmente a configuração de compartilhamento de exemplo no dispositivo usando *regedit* ou criando e executando um *arquivo .reg.*  

A configuração é definida por meio da seguinte entrada de chave do Registro:

```console
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
Onde:<br>
Tipo de nome é um D-WORD. <br>
Os valores possíveis são:
- 0 - não permite o compartilhamento de exemplo deste dispositivo
- 1 - permite o compartilhamento de todos os tipos de arquivo deste dispositivo

O valor padrão caso a chave do Registro não exista é 1.


## <a name="offboard-devices-using-a-local-script"></a>Dispositivos offboard usando um script local
Por motivos de segurança, o pacote usado para dispositivos offboard expirará 30 dias após a data em que foi baixado. Os pacotes de offboard expirados enviados para um dispositivo serão rejeitados. Ao baixar um pacote de offboard, você será notificado sobre a data de expiração dos pacotes e ele também será incluído no nome do pacote.

> [!NOTE]
> As políticas de integração e de offboard não devem ser implantadas no mesmo dispositivo ao mesmo tempo, caso contrário, isso causará colisões imprevisíveis.

1. Obter o pacote de offboarding do [Centro de Segurança do Microsoft Defender](https://securitycenter.windows.com/):

    1. No painel de navegação, selecione **Configurações**  >  **offboarding**.

    1. Selecione Windows 10 como o sistema operacional.

    1. No campo **Método de Implantação,** selecione **Script Local**.

    1. Clique **em Baixar pacote** e salve o arquivo .zip.

2. Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que pode ser acessado pelos dispositivos. Você deve ter um arquivo chamado *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

3.  Abra um prompt de linha de comando elevada no dispositivo e execute o script:

    1.  Vá para **Iniciar** e digite **cmd**.

    1.  Clique com o botão direito do mouse em **Prompt de Comando** e selecione **Executar como administrador**.

        ![Menu Iniciar janela apontando para Executar como administrador](images/run-as-admin.png)

4.  Digite o local do arquivo de script. Se você copiou o arquivo para a área de trabalho, *digite: %userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*

5.  Pressione a **tecla Enter** ou clique em **OK**.

> [!IMPORTANT]
> O offboard faz com que o dispositivo pare de enviar dados do sensor para o portal, mas os dados do dispositivo, incluindo a referência a todos os alertas que ele teve, serão mantidos por até 6 meses.


## <a name="monitor-device-configuration"></a>Monitorar a configuração do dispositivo
Você pode seguir as diferentes etapas de verificação na solução [de](troubleshoot-onboarding.md) problemas de integração para verificar se o script foi concluído com êxito e se o agente está em execução.

O monitoramento também pode ser feito diretamente no portal ou usando as diferentes ferramentas de implantação.

### <a name="monitor-devices-using-the-portal"></a>Monitorar dispositivos usando o portal
1. Vá para o Centro de Segurança do Microsoft Defender.

2. Clique **em Lista de dispositivos**.

3. Verifique se os dispositivos estão aparecendo.


## <a name="related-topics"></a>Tópicos relacionados
- [Integração de dispositivos Windows 10 usando a Política de Grupo](configure-endpoints-gp.md)
- [Integração de dispositivos Windows 10 usando o Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel](configure-endpoints-mdm.md)
- [Integrar dispositivos não persistentes de VDI (virtual desktop infrastructure)](configure-endpoints-vdi.md)
- [Executar um teste de detecção em um dispositivo recém-integrado do Microsoft Defender para Ponto de Extremidade](run-detection-test.md)
- [Solucionar problemas de integração do Microsoft Defender para pontos de extremidade](troubleshoot-onboarding.md)
