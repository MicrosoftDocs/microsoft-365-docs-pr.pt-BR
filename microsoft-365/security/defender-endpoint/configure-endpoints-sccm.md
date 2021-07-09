---
title: Integrar dispositivo Windows 10 usando o Configuration Manager
description: Use o Gerenciador de Configurações para implantar o pacote de configuração em dispositivos para que os dispositivos sejam integrados ao serviço.
keywords: onboard devices using sccm, device management, configure Microsoft Defender for Endpoint devices
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
ms.date: 02/07/2020
ms.technology: mde
ms.openlocfilehash: d7c319e37fb804ee4dac3b6bff402942bbc2fa79
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339653"
---
# <a name="onboard-the-windows-10-devices-using-configuration-manager"></a>Integrando os Windows 10 usando o Configuration Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Endpoint Configuration Manager branch atual
- Gerenciador de Configurações do System Center 2012 R2

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointssccm-abovefoldlink)

## <a name="supported-client-operating-systems"></a>Sistemas operacionais cliente com suporte

Com base na versão do Configuration Manager que você está executando, os seguintes sistemas operacionais cliente podem ser integrados:

#### <a name="configuration-manager-version-1910-and-prior"></a>Configuration Manager versão 1910 e anterior

- Clientes que executam computadores Windows 10 

#### <a name="configuration-manager-version-2002-and-later"></a>Configuration Manager versão 2002 e posterior

A partir do Configuration Manager versão 2002, você pode integrar os seguintes sistemas operacionais:

- Windows 8.1
- Windows 10
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server 2016, versão 1803 ou posterior
- Windows Server 2019

>[!NOTE]
>Para obter mais informações sobre como Windows Server 2012 R2, Windows Server 2016 e Windows Server 2019, consulte Onboard [Windows servers](configure-server-endpoints.md).



### <a name="onboard-devices-using-system-center-configuration-manager"></a>Dispositivos de integração usando System Center Configuration Manager


[![Imagem do PDF mostrando os vários caminhos de implantação](images/onboard-config-mgr.png)](images/onboard-config-mgr.png#lightbox)


Confira o [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) ou [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) para ver os vários caminhos na implantação do Microsoft Defender para Ponto de Extremidade. 



1. Abra o arquivo de pacote de configuração do Configuration Manager .zip (*WindowsDefenderATPOnboardingPackage.zip*) que você baixou do assistente de integração do serviço. Você também pode obter o pacote do [Microsoft 365 Defender portal](https://security.microsoft.com/):

    1. No painel de navegação, **selecione** Configurações  >  **Endpoints Gerenciamento** de  >    >  **dispositivos Integrando**.
    
    1. Selecione Windows 10 como o sistema operacional.

    1. No campo **método Deployment,** selecione **System Center Configuration Manager 2012/2012 R2/1511/1602**.
    
    1. Selecione **Baixar pacote** e salve o arquivo .zip.

2. Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que pode ser acessado pelos administradores de rede que implantarão o pacote. Você deve ter um arquivo chamado *WindowsDefenderATPOnboardingScript.cmd*.

3. Implante o pacote seguindo as etapas no artigo [Pacotes e Programas no System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))

    a. Escolha uma coleção de dispositivos predefinida para a qual implantar o pacote.

> [!NOTE]
> O Defender for Endpoint não dá suporte à integração durante a fase [OOBE (Experiência](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) De Saída). Certifique-se de que os usuários concluam o OOBE após Windows instalação ou atualização.

>[!TIP]
> Após a integração do dispositivo, você pode optar por executar um teste de detecção para verificar se um dispositivo está corretamente conectado ao serviço. Para obter mais informações, [consulte Execute a detection test on a newly onboarded Defender for Endpoint device](run-detection-test.md).
>
> Observe que é possível criar uma regra de detecção em um aplicativo do Configuration Manager para verificar continuamente se um dispositivo foi internado. Um aplicativo é um tipo diferente de objeto do que um pacote e um programa.
> Se um dispositivo ainda não estiver conectado (devido à conclusão pendente do OOBE ou qualquer outro motivo), o Configuration Manager repetirá a integração do dispositivo até que a regra detecte a alteração de status.
> 
> Esse comportamento pode ser realizado criando uma verificação de regra de detecção se o valor do Registro "OnboardingState" (do tipo REG_DWORD) = 1.
> Esse valor do Registro está localizado em "HKLM\SOFTWARE\Microsoft\Windows Proteção Avançada contra Ameaças\Status".
Para obter mais informações, [consulte Configure Detection Methods in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).

### <a name="configure-sample-collection-settings"></a>Configurar configurações de coleção de exemplos

Para cada dispositivo, você pode definir um valor de configuração para determinar se amostras podem ser coletadas do dispositivo quando uma solicitação é feita por meio Microsoft 365 Defender enviar um arquivo para análise profunda.

>[!NOTE]
>Essas configurações geralmente são feitas por meio do Configuration Manager.

Você pode definir uma regra de conformidade para o item de configuração no Configuration Manager para alterar a configuração de compartilhamento de exemplo em um dispositivo.

Essa regra deve ser um *item de* configuração de regra de conformidade de correção que define o valor de uma chave do Registro em dispositivos direcionados para garantir que eles sejam reclamações.

A configuração é definida por meio da seguinte entrada de chave do Registro:

```console
Path: "HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection"
Name: "AllowSampleCollection"
Value: 0 or 1
```

Onde:<br>
Tipo de chave é um D-WORD. <br>
Os valores possíveis são:
- 0 - não permite o compartilhamento de exemplo deste dispositivo
- 1 - permite o compartilhamento de todos os tipos de arquivo deste dispositivo

O valor padrão caso a chave do Registro não exista é 1.

Para obter mais informações sobre System Center Configuration Manager Conformidade, consulte Introdução às configurações de conformidade [no System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).


## <a name="other-recommended-configuration-settings"></a>Outras configurações recomendadas
Após a integração de dispositivos ao serviço, é importante aproveitar os recursos de proteção contra ameaças incluídos, habilitando-os com as seguintes configurações recomendadas.

### <a name="device-collection-configuration"></a>Configuração do conjunto de dispositivos
Se você estiver usando o Endpoint Configuration Manager, versão 2002 ou posterior, poderá optar por ampliar a implantação para incluir servidores ou clientes de nível inferior.


### <a name="next-generation-protection-configuration"></a>Configuração de proteção de próxima geração
As seguintes configurações são recomendadas:

**Examinar** <br>
- Examinar dispositivos de armazenamento removíveis, como unidades USB: Sim

**Proteção em tempo real** <br>
- Habilitar o Monitoramento Comportamental: Sim
- Habilitar a proteção contra aplicativos potencialmente indesejados no download e antes da instalação: Sim

**Serviço de Proteção na Nuvem**
- Tipo de associação do Serviço de Proteção na Nuvem: Associação avançada

**Redução de superfície de ataque** Configure todas as regras disponíveis para Auditoria.

>[!NOTE]
> O bloqueio dessas atividades pode interromper processos comerciais legítimos. A melhor abordagem é definir tudo para auditoria, identificar quais são seguros para ativar e, em seguida, ativar essas configurações em pontos de extremidade que não têm detecções de falsos positivos.


**Proteção de rede** <br>
Antes de ativar a proteção de rede no modo de auditoria ou bloqueio, verifique se você instalou a atualização da plataforma antimalware, que pode ser obtida na página [de suporte](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).


**Acesso controlado a pastas**<br>
Habilita o recurso no modo de auditoria por pelo menos 30 dias. Após esse período, revise as detecções e crie uma lista de aplicativos que têm permissão para gravar em diretórios protegidos.

Para obter mais informações, consulte [Evaluate controlled folder access](evaluate-controlled-folder-access.md).


## <a name="offboard-devices-using-configuration-manager"></a>Dispositivos offboard usando o Configuration Manager

Por motivos de segurança, o pacote usado para dispositivos offboard expirará 30 dias após a data em que foi baixado. Os pacotes de offboard expirados enviados para um dispositivo serão rejeitados. Ao baixar um pacote de offboard, você será notificado sobre a data de expiração dos pacotes e ele também será incluído no nome do pacote.

> [!NOTE]
> As políticas de integração e de offboard não devem ser implantadas no mesmo dispositivo ao mesmo tempo, caso contrário, isso causará colisões imprevisíveis.

### <a name="offboard-devices-using-microsoft-endpoint-manager-current-branch"></a>Dispositivos de offboard usando Microsoft Endpoint Manager ramificação atual

Se você usar Microsoft Endpoint Manager ramificação atual, consulte [Create an offboarding configuration file](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>Dispositivos de offboard usando System Center 2012 R2 Configuration Manager

1. Obter o pacote de offboard do [Microsoft 365 Defender portal](https://security.microsoft.com/):

    1. No painel de navegação, selecione **Configurações**  >  **Endpoints**  >  **Gerenciamento de**  >   **dispositivos Offboarding**.

    1. Selecione Windows 10 como o sistema operacional.

    1. No campo **método Deployment,** selecione **System Center Configuration Manager 2012/2012 R2/1511/1602**.
    
    1. Selecione **Baixar pacote** e salve o arquivo .zip.

2. Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que pode ser acessado pelos administradores de rede que implantarão o pacote. Você deve ter um arquivo chamado *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

3. Implante o pacote seguindo as etapas no artigo [Pacotes e Programas no System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))

    a. Escolha uma coleção de dispositivos predefinida para a qual implantar o pacote.

> [!IMPORTANT]
> O offboard faz com que o dispositivo pare de enviar dados do sensor para o portal, mas os dados do dispositivo, incluindo a referência a todos os alertas que ele teve, serão mantidos por até 6 meses.


## <a name="monitor-device-configuration"></a>Monitorar a configuração do dispositivo

Se você estiver usando Microsoft Endpoint Manager filial atual, use o painel do Defender para Ponto de Extremidade integrado no console do Configuration Manager. Para obter mais informações, consulte [Defender for Endpoint - Monitor](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).

Se você estiver usando o System Center 2012 R2 Configuration Manager, o monitoramento consiste em duas partes:

1. Confirmar se o pacote de configuração foi implantado corretamente e está sendo executado (ou executado com êxito) nos dispositivos em sua rede.

2. Verificar se os dispositivos estão em conformidade com o serviço Defender para Ponto de Extremidade (isso garante que o dispositivo possa concluir o processo de integração e pode continuar a relatar dados ao serviço).

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a>Confirme se o pacote de configuração foi implantado corretamente

1. No console do Configuration Manager, clique **em Monitoramento** na parte inferior do painel de navegação.

2. Selecione **Visão geral** e **implantações.**

3. Selecione na implantação com o nome do pacote.

4. Revise os indicadores de status **em Estatísticas de Conclusão** e Status de **Conteúdo.**

    Se houver implantações com falha (dispositivos com **status Error**, **Requirements Not Met**, ou **Failed**), talvez seja necessário solucionar problemas dos dispositivos. Para obter mais informações, consulte Solução [de problemas de integração do Microsoft Defender para o Ponto de Extremidade.](troubleshoot-onboarding.md)

    ![Gerenciador de Configurações mostrando implantação bem-sucedida sem erros](images/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-defender-for-endpoint-service"></a>Verifique se os dispositivos estão em conformidade com o serviço do Microsoft Defender para Ponto de Extremidade

Você pode definir uma regra de conformidade para o item de configuração no System Center 2012 R2 Configuration Manager para monitorar sua implantação.

Essa regra deve ser um *item* de configuração de regra de conformidade não corretivo que monitora o valor de uma chave do Registro em dispositivos direcionados.

Monitore a seguinte entrada da chave do Registro:

```console
Path: "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status"
Name: "OnboardingState"
Value: "1"
```

Para obter mais informações, consulte [Introdução às configurações de conformidade no System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).

## <a name="related-topics"></a>Tópicos relacionados
- [Integração Windows 10 usando a Política de Grupo](configure-endpoints-gp.md)
- [Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel](configure-endpoints-mdm.md)
- [Integrar dispositivos Windows 10 usando um script local](configure-endpoints-script.md)
- [Dispositivos integrados de VDI (Virtual Desktop Infrastructure) não persistente](configure-endpoints-vdi.md)
- [Executar um teste de detecção em um dispositivo recém-integrado do Microsoft Defender para Ponto de Extremidade](run-detection-test.md)
- [Solucionar problemas de integração do Microsoft Defender para pontos de extremidade](troubleshoot-onboarding.md)
