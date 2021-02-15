---
title: Integrar dispositivo Windows 10 usando o Configuration Manager
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
description: Use o Configuration Manager para implantar o pacote de configuração em dispositivos para que eles sejam onboarded ao serviço.
ms.openlocfilehash: ea1b0cba10dc3e7120192e0c0ee87e2e354f1cc2
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769391"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a>Integrar dispositivo Windows 10 usando o Configuration Manager

**Aplica-se a:**

- [Prevenção contra perda de dados de ponto de extremidade (DLP) do Microsoft 365](/microsoft-365/compliance/endpoint-dlp-learn-about)
- Gerenciador de Configurações do System Center 2012 R2

### <a name="onboard-devices-using-system-center-configuration-manager"></a>Dispositivos integrados usando o System Center Configuration Manager

1. Abra o arquivo .zip do pacote de configuração do Configuration Manager *(DeviceComplianceOnboardingPackage.zip)* que você baixou do assistente de integração de serviço. Você também pode obter o pacote no Centro [de Conformidade da Microsoft.](https://compliance.microsoft.com/)

2. No painel de navegação, selecione **Configurações**  >  **integração de**  >  **dispositivos à integração.**

3. No campo do método **de** implantação, selecione **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602.**
 
4. Selecione **Baixar pacote** e salve o arquivo .zip.

5. Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que possa ser acessado pelos administradores de rede que implantarão o pacote. Você deve ter um arquivo chamado *DeviceComplianceOnboardingScript.cmd*.

6. Implante o pacote seguindo as etapas do artigo Pacotes e Programas no [System Center 2012 R2 Configuration Manager.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))

7. Escolha uma coleção de dispositivos predefinida para implantar o pacote.

> [!NOTE]
> A prevenção contra perda de dados de ponto de extremidade do Microsoft 365 não dá suporte à integração durante a fase [OOBE (Out-Of-Box Experience).](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) Certifique-se de que os usuários concluam a OOBE após executar a instalação ou atualização do Windows.

>[!TIP]
> Após a integração do dispositivo, você pode optar por executar um teste de detecção para verificar se um dispositivo está corretamente onboarded ao serviço. Para obter mais informações, consulte [Executar um teste de detecção em um dispositivo Microsoft Defender ATP recém-integrado.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
>
> Observe que é possível criar uma regra de detecção em um aplicativo do Configuration Manager para verificar continuamente se um dispositivo foi onboarded. Um aplicativo é um tipo de objeto diferente de um pacote e programa.
> Se um dispositivo ainda não estiver onboarded (devido à conclusão do OOBE pendente ou qualquer outro motivo), o Configuration Manager repetirá a integração do dispositivo até que a regra detecte a alteração de status.
> 
> Esse comportamento pode ser realizado criando uma verificação de regra de detecção se o valor do Registro "OnboardingState" (do tipo REG_DWORD) = 1.
> Esse valor do Registro está localizado em "HKLM\SOFTWARE\Microsoft\Proteção Avançada contra Ameaças do Windows\Status".
Para obter mais informações, [consulte Configurar métodos de detecção no System Center 2012 R2 Configuration Manager.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)

### <a name="configure-sample-collection-settings"></a>Definir configurações de coleção de amostras

Para cada dispositivo, você pode definir um valor de configuração para dizer se os exemplos podem ser coletados do dispositivo quando uma solicitação é feita por meio da Central de Segurança do Microsoft Defender para enviar um arquivo para análise profunda.

>[!NOTE]
>Essas definições de configuração geralmente são feitas por meio do Configuration Manager. 

Você pode definir uma regra de conformidade para o item de configuração no Configuration Manager para alterar a configuração de compartilhamento de exemplo em um dispositivo.

Essa regra deve  ser um item de configuração de regra de conformidade que define o valor de uma chave do Registro em dispositivos de destino para garantir que eles sejam compatíveis.

A configuração é definida por meio da seguinte entrada de chave do Registro:

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
Onde:<br>
O tipo de chave é um D-WORD. <br>
Os valores possíveis são:
- 0 - não permite o compartilhamento de amostra deste dispositivo
- 1 - permite o compartilhamento de todos os tipos de arquivo deste dispositivo

O valor padrão caso a chave do Registro não exista é 1.

Para obter mais informações sobre a conformidade do System Center Configuration Manager, consulte Introdução às configurações de conformidade no [System Center 2012 R2 Configuration Manager.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))


## <a name="other-recommended-configuration-settings"></a>Outras definições de configuração recomendadas
Após a integração de dispositivos ao serviço, é importante tirar proveito dos recursos de proteção contra ameaças incluídos, habilitando-os com as seguintes configurações recomendadas.

### <a name="device-collection-configuration"></a>Configuração da coleção de dispositivos
Se você estiver usando o Endpoint Configuration Manager, versão 2002 ou posterior, poderá optar por ampliar a implantação para incluir servidores ou clientes de nível inferior.


### <a name="next-generation-protection-configuration"></a>Configuração de proteção de próxima geração

As seguintes definições de configuração são recomendadas:

**Examinar**

- Verificar dispositivos de armazenamento removível, como unidades USB: Sim

**Proteção em tempo real**

- Habilitar o Monitoramento Comportamental: Sim
- Habilitar a proteção contra aplicativos potencialmente indesejados no download e antes da instalação: Sim

**Serviço de Proteção de Nuvem**

- Tipo de associação do Serviço de Proteção de Nuvem: Associação avançada

**Redução de superfície de ataque** Configure todas as regras disponíveis para Auditoria.

>[!NOTE]
> O bloqueio dessas atividades pode interromper processos empresariais legítimos. A melhor abordagem é definir tudo para auditar, identificar quais são seguros para ativar e, em seguida, ativar essas configurações em pontos de extremidade que não têm detecções de falsos positivos.

**Proteção de rede**

Antes de ativar a proteção de rede no modo de auditoria ou bloqueio, verifique se você instalou a atualização da plataforma antimalware, que pode ser obtida na página [de suporte.](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)


**Acesso controlado a pastas**

Habilita o recurso no modo de auditoria por pelo menos 30 dias. Após esse período, revise as detecções e crie uma lista de aplicativos que têm permissão para gravar em diretórios protegidos.

Para obter mais informações, consulte [Avaliar o acesso controlado a pastas.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access)


## <a name="offboard-devices-using-configuration-manager"></a>Desligar dispositivos usando o Configuration Manager

Por motivos de segurança, o pacote usado para dispositivos offboard expirará 30 dias após a data em que foi baixado. Os pacotes de reexenciamento expirados enviados para um dispositivo serão rejeitados. Ao baixar um pacote de descarregamento, você será notificado sobre a data de vencimento dos pacotes e ele também será incluído no nome do pacote.

> [!NOTE]
> As políticas de integração e de transferência não devem ser implantadas no mesmo dispositivo ao mesmo tempo, caso contrário, isso causará colisões imprevisíveis.

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a>Redução de dispositivos usando a ramificação atual do Microsoft Endpoint Configuration Manager

Se você usar a ramificação atual do Microsoft Endpoint Configuration Manager, consulte [Criar um arquivo de configuração de redução.](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>Desligar dispositivos usando o System Center 2012 R2 Configuration Manager

1. Obter o pacote de redação do Centro [de Conformidade da Microsoft:](https://compliance.microsoft.com/)

2. No painel de navegação, selecione **Configurações**  >   **integração do dispositivo** à >  **rebordagem.**

3. Selecione o Windows 10 como o sistema operacional.

4. No campo do método **de** implantação, selecione **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602.**
    
5. Selecione **Baixar pacote** e salve o arquivo .zip.

6. Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que possa ser acessado pelos administradores de rede que implantarão o pacote. Você deve ter um arquivo *chamado DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd.*

7. Implante o pacote seguindo as etapas do artigo Pacotes e Programas no [System Center 2012 R2 Configuration Manager.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))

8. Escolha uma coleção de dispositivos predefinida para implantar o pacote.

> [!IMPORTANT]
> A reação faz com que o dispositivo pare de enviar dados do sensor para o portal, mas os dados do dispositivo, incluindo a referência a todos os alertas que ele recebeu, serão retidos por até seis meses.


## <a name="monitor-device-configuration"></a>Monitorar a configuração do dispositivo

Se você estiver usando a ramificação atual do Microsoft Endpoint Configuration Manager, use o painel integrado do Microsoft Defender ATP no console do Configuration Manager. Para obter mais informações, consulte [Proteção Avançada contra Ameaças do Microsoft Defender - Monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).

Se você estiver usando o System Center 2012 R2 Configuration Manager, o monitoramento consiste em duas partes:

1. Confirmação de que o pacote de configuração foi implantado corretamente e está em execução (ou foi executado com êxito) nos dispositivos em sua rede.

2. Verificar se os dispositivos estão em conformidade com o serviço de prevenção contra perda de dados do ponto de extremidade do Microsoft 365 (isso garante que o dispositivo possa concluir o processo de integração e continuar a relatar dados para o serviço).

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a>Confirmar se o pacote de configuração foi implantado corretamente

1. No console do Configuration Manager, clique **em Monitoramento** na parte inferior do painel de navegação.

2. Selecione **Visão geral** e **implantações.**

3. Selecione na implantação com o nome do pacote.

4. Revise os indicadores de status **em Estatísticas de Conclusão** e Status do **Conteúdo.**

    Se houver falhas nas implantações (dispositivos com **Status** de Erro **,** Requisitos Não Atendidos ou **Falha),** talvez seja necessário solucionar problemas nos dispositivos. Para obter mais informações, consulte, Solucionar [problemas de integração da Proteção Avançada](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)contra Ameaças do Microsoft Defender.

    ![Configuration Manager mostrando a implantação bem-sucedida sem erros](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a>Verifique se os dispositivos estão em conformidade com o serviço de prevenção contra perda de dados do Ponto de Extremidade do Microsoft 365

Você pode definir uma regra de conformidade para o item de configuração no System Center 2012 R2 Configuration Manager para monitorar sua implantação.

> [!NOTE]
> Este procedimento e entrada do Registro se aplica ao Endpoint DLP, bem como à Proteção Avançada contra Ameaças.

Essa regra deve ser um item *de* configuração de regra de conformidade não corretivo que monitora o valor de uma chave do Registro em dispositivos de destino.

Monitore a seguinte entrada de chave do Registro:
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
Para obter mais informações, [consulte Introdução às configurações de conformidade no System Center 2012 R2 Configuration Manager.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))

## <a name="related-topics"></a>Tópicos relacionados
- [Integração de dispositivos Windows 10 usando Política de Grupo](dlp-configure-endpoints-gp.md)
- [Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel](dlp-configure-endpoints-mdm.md)
- [Integrar dispositivos Windows 10 usando um script local](dlp-configure-endpoints-script.md)
- [Integrar dispositivos não persistentes de VDI (virtual desktop infrastructure)](dlp-configure-endpoints-vdi.md)
- [Executar um teste de detecção em um dispositivo Microsoft Defender ATP recém-integrado](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Solucionar problemas de integração da Proteção Avançada contra Ameaças do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
