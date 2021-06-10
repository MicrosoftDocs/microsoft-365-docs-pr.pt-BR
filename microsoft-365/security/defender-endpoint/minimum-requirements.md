---
title: Requisitos mínimos para o Microsoft Defender para Ponto de Extremidade
description: Entenda os requisitos e requisitos de licenciamento para integração de dispositivos ao serviço
keywords: requisitos mínimos, licenciamento, tabela de comparação
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ccff6abcfcd1a2da32a8e1614a2de45afed69aef
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842993"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a>Requisitos mínimos para o Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink)


Há alguns requisitos mínimos para a integração de dispositivos ao serviço. Saiba mais sobre os requisitos de licenciamento, hardware e software e outras configurações para os dispositivos de integração ao serviço.

> [!TIP]
> - Saiba mais sobre os aprimoramentos mais recentes no Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).
> - O Defender for Endpoint demonstrou recursos de detecção e ótica líderes do setor na avaliação recente do MITRE. Leitura: [Insights do MITRE ATT&avaliação baseada em CK.](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)

## <a name="licensing-requirements"></a>Requisitos de licenciamento

O Microsoft Defender para Ponto de Extremidade requer uma das seguintes ofertas de licenciamento por volume da Microsoft:

- Windows 10 Enterprise E5
- Windows 10 Education A5
- Microsoft 365 E5 (M365 E5) que inclui Windows 10 Enterprise E5
- Microsoft 365 A5 (M365 A5)
- Microsoft 365 E5 Security
- Segurança 365 A5 da Microsoft
- Microsoft Defender para Ponto de Extremidade

> [!NOTE]
> Os usuários licenciados qualificados podem usar o Microsoft Defender para Ponto de Extremidade em até cinco dispositivos simultâneos.
> O Microsoft Defender para Ponto de Extremidade também está disponível para compra de um Provedor de Soluções na Nuvem (CSP).
> As VMs RDSH não exigem uma licença separada do Defender para Ponto de Extremidade.

O Microsoft Defender para Ponto de Extremidade para servidores requer uma das seguintes opções de licenciamento:

- [Centro de Segurança do Azure com o Azure Defender habilitado](/azure/security-center/security-center-pricing)
- Microsoft Defender para Ponto de Extremidade para Servidor (um por servidor coberto)

> [!NOTE]
> Os clientes podem adquirir licenças de servidor (uma por servidor coberto Ambiente do Sistema Operacional (OSE)) para o Microsoft Defender para Ponto de Extremidade para Servidores se eles têm um mínimo combinado de 50 licenças para uma ou mais das seguintes licenças de usuário:
>
> * Microsoft Defender para Ponto de Extremidade
> * Windows E5/A5
> * Microsoft 365 E5/A5
> * Microsoft 365 E5/Segurança do A5

Para obter informações detalhadas sobre licenciamento, consulte o [site Termos](https://www.microsoft.com/licensing/terms/) do Produto e trabalhe com sua equipe de conta para saber mais sobre os termos e condições.

Para obter mais informações sobre a matriz de recursos em Windows 10 edições, consulte [Compare Windows 10 edições](https://www.microsoft.com/windowsforbusiness/compare).

Para uma tabela de comparação detalhada de Windows 10 de edição comercial, consulte a [comparação PDF](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf).

## <a name="browser-requirements"></a>Requisitos de navegador

O acesso ao Defender para Ponto de Extremidade é feito por meio de um navegador, suportando os seguintes navegadores:

- Microsoft Edge
- Google Chrome

> [!NOTE]
> Embora outros navegadores possam funcionar, os navegadores mencionados são aqueles com suporte.


## <a name="hardware-and-software-requirements"></a>Requisitos de hardware e software

### <a name="supported-windows-versions"></a>Versões Windows com suporte

- Windows 7 sp1 Enterprise ([Requer ESU para suporte](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)
- Windows 7 SP1 Pro ([Requer ESU para suporte](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)
- Windows 8.1 Enterprise
- Windows 8.1 Pro
- Windows 10 Enterprise
- [Windows 10 Enterprise LTSC 2016 (ou posterior)](/windows/whats-new/ltsc/)
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows servidor
  - Windows Server 2008 R2 SP1
  - Windows Server 2012 R2
  - Windows Server 2016
  - Windows Servidor, versão 1803 ou posterior
  - Windows Server 2019
- Área de Trabalho Virtual do Windows

Os dispositivos em sua rede devem estar executando uma dessas edições.

Os requisitos de hardware para o Defender para Ponto de Extremidade em dispositivos são os mesmos para as edições com suporte.

> [!NOTE]
> Máquinas que executam versões móveis Windows (como Windows CE e Windows 10 Mobile) não têm suporte.
>
> Máquinas virtuais que executam Windows 10 Enterprise 2016 LTSB podem encontrar problemas de desempenho se executados em plataformas de virtualização que não são da Microsoft.
>
> Para ambientes virtuais, recomendamos o uso Windows 10 Enterprise LTSC 2019 ou posterior.


### <a name="other-supported-operating-systems"></a>Outros sistemas operacionais com suporte

- [Android](microsoft-defender-endpoint-android.md)
- [iOS](microsoft-defender-endpoint-ios.md)
- [Linux](microsoft-defender-endpoint-linux.md)
- [macOS](microsoft-defender-endpoint-mac.md)

> [!NOTE]
> Você precisará confirmar que as distribuições e versões do Linux do Android, iOS e macOS são compatíveis com o Defender para o Ponto de Extremidade para que a integração funcione.



### <a name="network-and-data-storage-and-configuration-requirements"></a>Requisitos de configuração e armazenamento de rede e dados

Ao executar o assistente de integração pela primeira vez, você deve escolher onde suas informações relacionadas ao Microsoft Defender for Endpoint estão armazenadas: na União Europeia, no Reino Unido ou no datacenter dos Estados Unidos.

> [!NOTE]
> - Não é possível alterar o local de armazenamento de dados após a configuração pela primeira vez.
> - Revise o [Microsoft Defender para armazenamento e](data-storage-privacy.md) privacidade de dados do Ponto de Extremidade para obter mais informações sobre onde e como a Microsoft armazena seus dados.


### <a name="diagnostic-data-settings"></a>Configurações de dados de diagnóstico

> [!NOTE]
> O Microsoft Defender para Ponto de Extremidade não exige nenhum nível de diagnóstico específico, desde que ele seja habilitado.

Certifique-se de que o serviço de dados de diagnóstico está habilitado em todos os dispositivos da sua organização.
Por padrão, esse serviço está habilitado. É uma boa prática verificar para garantir que você obterá dados do sensor deles.

**Use a linha de comando para verificar o tipo Windows 10 de inicialização** do serviço de dados de diagnóstico:

1. Abra um prompt de linha de comando elevada no dispositivo:

   1.  Vá para **Iniciar** e digite **cmd**.

   1.  Clique com o botão direito do mouse em **Prompt de Comando** e selecione **Executar como administrador**.

2. Insira o seguinte comando e pressione **Enter**:

   ```console
   sc qc diagtrack
   ```

   Se o serviço estiver habilitado, o resultado deverá ter a seguinte captura de tela:

   ![Resultado do comando de consulta sc para diagtrack](images/windefatp-sc-qc-diagtrack.png)


Você precisará definir o serviço para iniciar automaticamente se o START_TYPE **não** estiver definido como **AUTO_START**.


**Use a linha de comando para definir o serviço Windows 10 de dados de diagnóstico para iniciar automaticamente:**

1.  Abra um prompt de linha de comando elevada no ponto de extremidade:

    1. Vá para **Iniciar** e digite **cmd**.

    1. Clique com o botão direito do mouse em **Prompt de Comando** e selecione **Executar como administrador**.

2.  Insira o seguinte comando e pressione **Enter**:

    ```console
    sc config diagtrack start=auto
    ```

3.  Uma mensagem de sucesso é exibida. Verifique a alteração inserindo o seguinte comando e pressione **Enter**:

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a>Conectividade com a Internet

A conectividade com a Internet em dispositivos é necessária diretamente ou por proxy.

O sensor Defender para Ponto de Extremidade pode usar uma largura de banda média diária de 5 MB para se comunicar com o serviço de nuvem do Defender para Ponto de Extremidade e relatar dados cibernéticos. Atividades exclusivas, como carregamentos de arquivos e conjunto de pacotes de investigação, não são incluídas nesta largura de banda média diária.

Para obter mais informações sobre configurações de proxy adicionais, consulte [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).

Antes de você entrar em dispositivos, o serviço de dados de diagnóstico deve estar habilitado. O serviço é habilitado por padrão no Windows 10.


## <a name="microsoft-defender-antivirus-configuration-requirement"></a>Microsoft Defender Antivírus requisito de configuração

O agente Defender para Ponto de Extremidade depende da capacidade de Microsoft Defender Antivírus examinar arquivos e fornecer informações sobre eles.

Configure atualizações de inteligência de segurança no Defender para dispositivos de ponto de extremidade, Microsoft Defender Antivírus o antimalware ativo ou não. Para obter mais informações, consulte [Manage Microsoft Defender Antivírus updates and apply baselines](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).

Quando Microsoft Defender Antivírus não é o antimalware ativo em sua organização e você usa o serviço Defender para Ponto de Extremidade, o Microsoft Defender Antivírus entra no modo passivo.

Se a sua organização tiver desligado Microsoft Defender Antivírus por meio de política de grupo ou outros métodos, os dispositivos que estão integrados devem ser excluídos dessa política de grupo.

Se você estiver integrando servidores e Microsoft Defender Antivírus não for o antimalware ativo em seus servidores, o Microsoft Defender Antivírus precisará ser configurado para entrar no modo passivo ou desinstalado. A configuração depende da versão do servidor. Para obter mais informações, [consulte Microsoft Defender Antivírus compatibilidade](/security/defender-endpoint/microsoft-defender-antivirus-compatibility).

> [!NOTE]
> Sua política de grupo regular não se aplica à Proteção contra Adulteração, e as alterações nas configurações Microsoft Defender Antivírus serão ignoradas quando a Proteção contra Adulteração estiver em uso.


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a>Microsoft Defender Antivírus Driver antimalware de início antecipado (ELAM) está habilitado

Se você estiver executando Microsoft Defender Antivírus como o produto antimalware principal em seus dispositivos, o agente Defender para Ponto de Extremidade será aderido com êxito.

Se você estiver executando um cliente antimalware de terceiros e usar soluções de Gerenciamento de Dispositivo Móvel ou Microsoft Endpoint Manager (filial atual), você precisará garantir que o driver Microsoft Defender Antivírus ELAM esteja habilitado. Para obter mais informações, [consulte Ensure that Microsoft Defender Antivírus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).


## <a name="related-topics"></a>Tópicos relacionados

- [Configurar o Microsoft Defender para implantação do Ponto de Extremidade](production-deployment.md)
- [Integração de dispositivos](onboard-configure.md)
