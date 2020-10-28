---
title: Dispositivos integrados do Windows 10 usando o Configuration Manager
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
description: Use o Gerenciador de configurações para implantar o pacote de configuração nos dispositivos para que eles sejam incluídos no serviço.
ms.openlocfilehash: ea1b0cba10dc3e7120192e0c0ee87e2e354f1cc2
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769391"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a>Dispositivos integrados do Windows 10 usando o Configuration Manager

**Aplica-se a:**

- [Prevenção de perda de dados do Microsoft 365 EndPoint (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)
- Gerenciador de Configurações do System Center 2012 R2

### <a name="onboard-devices-using-system-center-configuration-manager"></a>Dispositivos integrados usando o System Center Configuration Manager

1. Abra o arquivo. zip do pacote de configuração do Gerenciador de configurações ( *DeviceComplianceOnboardingPackage.zip* ) que você baixou do assistente de integração de serviço. Você também pode obter o pacote do [centro de conformidade da Microsoft](https://compliance.microsoft.com/).

2. No painel de navegação, selecione integração de integração do dispositivo de **configuração**  >  **Device Onboarding**  >  **Onboarding** .

3. No campo **método de implantação** , selecione **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .
 
4. Selecione **baixar pacote** e salve o arquivo. zip.

5. Extraia o conteúdo do arquivo. zip para um local compartilhado e somente leitura que possa ser acessado pelos administradores de rede que implantarão o pacote. Você deve ter um arquivo chamado *DeviceComplianceOnboardingScript. cmd* .

6. Implante o pacote seguindo as etapas descritas no artigo [pacotes e programas no System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) .

7. Escolha uma coleção de dispositivos predefinida para implantar o pacote.

> [!NOTE]
> O Microsoft 365 Endpoint Data Loss Prevention não dá suporte à integração durante a fase de [experiência inicial (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) . Certifique-se de que os usuários concluem o OOBE após executar a instalação ou atualização do Windows.

>[!TIP]
> Após a integração do dispositivo, você pode optar por executar um teste de detecção para verificar se um dispositivo está corretamente integrado ao serviço. Para obter mais informações, consulte [executar um teste de detecção em um dispositivo ATP do Microsoft defender recentemente integrado](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).
>
> Observe que é possível criar uma regra de detecção em um aplicativo do Gerenciador de configurações para verificar continuamente se um dispositivo foi integrado. Um aplicativo é um tipo diferente de objeto do que um pacote e programa.
> Se um dispositivo ainda não estiver integrado (devido à conclusão do OOBE pendente ou a qualquer outro motivo), o Gerenciador de configurações tentará integrar novamente o dispositivo até que a regra detecte a alteração do status.
> 
> Esse comportamento pode ser feito criando uma regra de detecção verificando se o valor do registro "OnboardingState" (do tipo REG_DWORD) = 1.
> Esse valor do registro está localizado em "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".
Para obter mais informações, consulte [Configure Detection Methods in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).

### <a name="configure-sample-collection-settings"></a>Definir configurações de coleção de amostra

Para cada dispositivo, você pode definir um valor de configuração para indicar se os exemplos podem ser coletados do dispositivo quando uma solicitação é feita por meio da central de segurança do Microsoft defender para enviar um arquivo para análise profunda.

>[!NOTE]
>Essas definições de configuração geralmente são realizadas pelo Configuration Manager. 

Você pode definir uma regra de conformidade para o item de configuração no Gerenciador de configurações para alterar a configuração de compartilhamento de amostra em um dispositivo.

Esta regra deve ser um item de configuração de regra de conformidade de *correção* que define o valor de uma chave de registro em dispositivos de destino para garantir que eles sejam queixas.

A configuração é definida por meio da seguinte entrada de chave do registro:

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
Onde:<br>
O tipo de chave é uma palavra D. <br>
Os valores possíveis são:
- 0-não permitir o compartilhamento de exemplo deste dispositivo
- 1-permite o compartilhamento de todos os tipos de arquivo deste dispositivo

O valor padrão no caso de a chave do registro não existir é 1.

Para obter mais informações sobre a conformidade do System Center Configuration Manager, consulte [Introduction to Compliance Settings in System center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).


## <a name="other-recommended-configuration-settings"></a>Outras definições de configuração recomendadas
Após a integração de dispositivos ao serviço, é importante aproveitar os recursos de proteção contra ameaças incluídos habilitando-os com as seguintes definições de configuração recomendada.

### <a name="device-collection-configuration"></a>Configuração do conjunto de dispositivos
Se você estiver usando o Endpoint Configuration Manager, versão 2002 ou posterior, você pode optar por ampliar a implantação para incluir servidores ou clientes de nível inferior.


### <a name="next-generation-protection-configuration"></a>Configuração de proteção de próxima geração

As definições de configuração a seguir são recomendadas:

**Examinar**

- Examinar dispositivos de armazenamento removíveis, como unidades USB: Sim

**Proteção em tempo real**

- Habilitar monitoramento comportamental: Sim
- Habilitar a proteção contra aplicativos potencialmente indesejados no download e antes da instalação: Sim

**Serviço de proteção de nuvem**

- Tipo de associação do serviço de proteção de nuvem: Associação avançada

**Redução da superfície de ataque** Configure todas as regras disponíveis para auditoria.

>[!NOTE]
> Bloquear essas atividades pode interromper processos de negócios legítimos. A melhor abordagem é definir tudo como auditoria, identificar quais são os que são seguros e, em seguida, habilitar essas configurações em pontos de extremidade que não têm detecções falsas positivas.

**Proteção de rede**

Antes de habilitar a proteção de rede no modo de auditoria ou de bloqueio, verifique se você instalou a atualização da plataforma Antimalware, que pode ser obtida na [página de suporte](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).


**Acesso a pastas controladas**

Habilite o recurso no modo de auditoria por pelo menos 30 dias. Após esse período, revise as detecções e crie uma lista de aplicativos que têm permissão para gravar em diretórios protegidos.

Para obter mais informações, consulte [avaliar acesso a pastas controladas](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).


## <a name="offboard-devices-using-configuration-manager"></a>Dispositivos externamente usando o Configuration Manager

Por motivos de segurança, o pacote usado para os dispositivos do externamente expirará 30 dias após a data em que foi baixado. Os pacotes de remoção expirados enviados para um dispositivo serão rejeitados. Ao baixar um pacote de remoção, você será notificado da data de expiração dos pacotes e ele também será incluído no nome do pacote.

> [!NOTE]
> As políticas de integração e remoção não devem ser implantadas no mesmo dispositivo ao mesmo tempo, caso contrário, isso causará colisões imprevisíveis.

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a>Dispositivos externamente usando a ramificação atual do Microsoft Endpoint Configuration Manager

Se você usar a ramificação atual do Microsoft Endpoint Configuration Manager, confira [criar um arquivo de configuração de remoção](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>Dispositivos externamente usando o Gerenciador de configuração do System Center 2012 R2

1. Obtenha o pacote de remoção do [centro de conformidade da Microsoft](https://compliance.microsoft.com/):

2. No painel de navegação, selecione remoção de configuração de dispositivo de **configurações**  >   **Device onboarding** >  **Offboarding** .

3. Selecione Windows 10 como sistema operacional.

4. No campo **método de implantação** , selecione **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .
    
5. Selecione **baixar pacote** e salve o arquivo. zip.

6. Extraia o conteúdo do arquivo. zip para um local compartilhado e somente leitura que possa ser acessado pelos administradores de rede que implantarão o pacote. Você deve ter um arquivo chamado *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* .

7. Implante o pacote seguindo as etapas descritas no artigo [pacotes e programas no System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) .

8. Escolha uma coleção de dispositivos predefinida para implantar o pacote.

> [!IMPORTANT]
> A remoção faz com que o dispositivo pare de enviar dados de sensor para o portal, mas os dados do dispositivo, incluindo referência a qualquer alerta que tenha tido, serão mantidos por até seis meses.


## <a name="monitor-device-configuration"></a>Monitorar a configuração do dispositivo

Se você estiver usando a ramificação atual do Microsoft Endpoint Configuration Manager, use o painel interno do Microsoft defender ATP no console do Configuration Manager. Para obter mais informações, consulte [Microsoft defender Advanced Threat Protection-monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).

Se você estiver usando o System Center 2012 R2 Configuration Manager, o monitoramento consiste em duas partes:

1. A confirmação do pacote de configuração foi implantada corretamente e está em execução (ou foi executada com êxito) nos dispositivos da sua rede.

2. Verificar se os dispositivos estão em conformidade com o serviço de prevenção de perda de dados de ponto de extremidade do Microsoft 365 (isso garante que o dispositivo possa concluir o processo de integração e que possa continuar a relatar dados para o serviço).

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a>Confirmar se o pacote de configuração foi implantado corretamente

1. No console do Gerenciador de configurações, clique em **monitoramento** na parte inferior do painel de navegação.

2. Selecione **visão geral** e **implantações** .

3. Selecione na implantação com o nome do pacote.

4. Revise os indicadores de status sob **Estatísticas de conclusão** e **status do conteúdo** .

    Se houver falha nas implantações (dispositivos com **erro** , **requisitos não atendidos** ou **status de falha** ), talvez seja necessário solucionar problemas dos dispositivos. Para saber mais, confira [solucionar problemas de integração da proteção avançada contra ameaças do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).

    ![Gerenciador de configurações mostrando uma implantação bem-sucedida sem erros](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a>Verifique se os dispositivos são compatíveis com o serviço de prevenção de perda de dados de ponto de extremidade do Microsoft 365

Você pode definir uma regra de conformidade para o item de configuração no System Center 2012 R2 Configuration Manager para monitorar sua implantação.

> [!NOTE]
> Este procedimento e a entrada do registro se aplicam ao Endpoint DLP, bem como à proteção avançada contra ameaças.

Esta regra deve ser um item de configuração de regra de conformidade de *não correção* que monitora o valor de uma chave do registro em dispositivos de destino.

Monitore a seguinte entrada de chave do registro:
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
Para obter mais informações, consulte [introdução às configurações de conformidade no System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).

## <a name="related-topics"></a>Tópicos relacionados
- [Dispositivos Windows 10 integrados usando a política de grupo](dlp-configure-endpoints-gp.md)
- [Dispositivos do Windows 10 integrados usando ferramentas de gerenciamento de dispositivos móveis](dlp-configure-endpoints-mdm.md)
- [Dispositivos integrados do Windows 10 usando um script local](dlp-configure-endpoints-script.md)
- [Dispositivos não persistentes de infraestrutura de área de trabalho virtual (VDI)](dlp-configure-endpoints-vdi.md)
- [Executar um teste de detecção em um dispositivo Microsoft defender ATP recentemente integrado](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Solucionar problemas de integração com a proteção avançada contra ameaças do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
