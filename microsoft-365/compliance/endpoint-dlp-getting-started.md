---
title: Introdução à prevenção contra perda de dados do Microsoft 365 Endpoint
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Configure a prevenção contra perda de dados de ponto de extremidade do Microsoft 365 para monitorar atividades de arquivo e implementar ações de proteção para esses arquivos para pontos de extremidade.
ms.openlocfilehash: 8dc57bfe395ad76e6b8aef336aaadb2cb7e42f81
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226666"
---
# <a name="get-started-with-endpoint-data-loss-prevention"></a>Introdução à Prevenção contra perda de dados do ponto de extremidade

A prevenção contra perda de dados de ponto de extremidade do Microsoft (Endpoint DLP) faz parte do pacote de recursos de prevenção contra perda de dados (DLP) da Microsoft 365, que você pode usar para descobrir e proteger itens confidenciais em todos os serviços do Microsoft 365. Para obter mais informações sobre todas as ofertas de DLP da Microsoft, consulte [Saiba mais sobre prevenção contra perda de dados](dlp-learn-about-dlp.md). Para saber mais sobre a DLP do ponto de extremidade, confira [Saiba mais sobre a prevenção contra perda de dados do Ponto de extremidade](endpoint-dlp-learn-about.md)

O Microsoft Endpoint DLP permite monitorar dispositivos Windows 10 e detectar quando itens confidenciais são usados e compartilhados. Isso dá a você a visibilidade e o controle necessários para garantir que eles sejam usados e protegidos corretamente, e para ajudar a evitar o comportamento arriscado que possa comprometer.

## <a name="before-you-begin"></a>Antes de começar

### <a name="skusubscriptions-licensing"></a>Licenciamento SKU/assinaturas

Antes de começar a usar o Endpoint DLP, confirme seu [Assinatura do Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) e os complementos. Para acessar e usar a funcionalidade do Endpoint DLP, você deve ter uma dessas assinaturas ou complementos.

- Microsoft 365 E5
- Microsoft 365 A5 (EDU)
- Conformidade do Microsoft 365 E5
- Conformidade do Microsoft 365 A5
- Governança e Proteção de Informações do Microsoft 365 E5
- Governança e Proteção de Informações do Microsoft 365 A5

### <a name="permissions"></a>Permissões

Para habilitar o gerenciamento de dispositivos, a conta que você usa deve ser um membro de qualquer uma das seguintes funções:

- Administrador global
- Administrador de segurança
- Administrador de conformidade

Se você quiser usar uma conta personalizada para exibir as configurações de gerenciamento de dispositivo, deverá estar em uma das seguintes funções:

- Administrador global
- Administrador de conformidade
- Administrador de dados de conformidade
- Leitor global

Se você quiser usar uma conta personalizada para acessar a página de integração/remoção, deverá estar em uma das seguintes funções:

- Administrador global
- Administrador de conformidade

Se você quiser usar uma conta personalizada para ativar/desativar o monitoramento de dispositivo, deverá estar em uma das seguintes funções:

- Administrador global
- Administrador de conformidade

Os dados do Endpoint DLP podem ser exibidos no [Explorador de atividades](data-classification-activity-explorer.md). Há quatro funções que concedem permissão para o explorador de atividades, a conta que você usa para acessar os dados deve ser um membro de qualquer uma delas.

- Administrador global
- Administrador de conformidade
- Administrador de segurança
- Administrador de dados de conformidade

### <a name="prepare-your-endpoints"></a>Preparar seus pontos de extremidade

Certifique-se de que os dispositivos Windows 10 que você pretende implantar o Endpoint DLP atendam a esses requisitos.

1. Deve estar executando o Windows 10 x64 build 1809 ou superior.

2. A Versão do Cliente Antimalware é 4.18.2009.7 ou mais recente. Verifique sua versão atual abrindo o aplicativo Segurança do Windows, selecione o ícone Configurações e, em seguida, selecione Sobre. O número da versão está listado na Versão do Cliente Antimalware. Atualize para a Versão do Cliente Antimalware instalando o Windows Update KB4052623.

   > [!NOTE]
   > Nenhum dos componentes de Segurança do Windows precisa estar ativo, você pode executar o ponto de extremidade da DLP independente do status de segurança do Windows, mas a [proteção em tempo real e o monitor de comportamento devem estar habilitados](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).

3. As seguintes atualizações do Windows foram instaladas.

   > [!NOTE]
   > Essas atualizações não são um pré-requisito para integrar um dispositivo ao Ponto de extremidade da DLP, mas contêm correções para problemas importantes, portanto, devem ser instaladas antes de usar o produto.

   - Para Windows 10 1809 - KB4559003, KB4577069, KB4580390
   - Para Windows 10 1903 ou 1909 - KB4559004, KB4577062, KB4580386
   - Para Windows 10 2004 - KB4568831, KB4577063
   - Para dispositivos que executam o Office 2016 (e nenhuma outra versão do Office) - KB4577063

4. Todos os dispositivos devem um destes:

   - [Ingressado no Active Directory do Azure (Azure AD)](/azure/active-directory/devices/concept-azure-ad-join)
   - [Ingressado no Azure AD Híbrido](/azure/active-directory/devices/concept-azure-ad-join-hybrid)
   - [Registrado no AAD](/azure/active-directory/user-help/user-help-register-device-on-network)

5. Instalar o navegador Microsoft Chromium Edge no dispositivo do ponto de extremidade para impor ações de política para a atividade carregar na nuvem. Confira, [Baixar o novo Microsoft Edge baseado em Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).

6. Se você está no Canal Empresarial Mensal das versões 2004-2008 do Microsoft 365 Apps, há um problema conhecido com o DLP do ponto de extremidade classificando o conteúdo do Office, e você precisa atualizar para a versão 2009 ou posterior. Confira [Histórico de atualização do Microsoft 365 Apps (relacionado por data)](/officeupdates/update-history-microsoft365-apps-by-date) para as versões atuais. Para saber mais sobre esse problema, confira a seção Pacote do Office de [notas de versão do Canal Atual em 2020](/officeupdates/current-channel#version-2010-october-27).

7. Se você tem pontos de extremidade que usam um proxy de dispositivo para se conectar à Internet, siga os procedimentos em [definir as configurações de conexão com a Internet e o proxy do dispositivo para o Endpoint DLP](endpoint-dlp-configure-proxy.md).

## <a name="onboarding-devices-into-device-management"></a>Dispositivos de integração no gerenciamento de dispositivos

Você deve habilitar o monitoramento de dispositivos e encaminhar os pontos de extremidade antes de poder monitorar e proteger itens confidenciais em um dispositivo. Estas ações estão concluídas no portal de conformidade do Microsoft 365.

Se você quiser que os dispositivos integrados ainda não estejam integrados, baixe o script apropriado e distribua-o a esses dispositivos. Siga o [Procedimento de integração de dispositivos](endpoint-dlp-getting-started.md#onboarding-devices).

Se você já tiver dispositivos integrados na [Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection/), eles já serão exibidos na lista dispositivos gerenciados. Siga [Com dispositivos integrados no procedimento Microsoft Defender para Ponto de Extremidade](?source=docs&view=o365-worldwide#with-devices-onboarded-into-microsoft-defender-for-endpoint).

### <a name="onboarding-devices"></a>Dispositivos de integração

Neste cenário de implantação, você integrará dispositivos que ainda não foram integrados e você só deseja monitorar e proteger itens confidenciais contra compartilhamento não intencional em dispositivos Windows 10.

1. Abra o [Centro de conformidade do Microsoft](https://compliance.microsoft.com).

2. Abra a página de configurações do Centro de conformidade e escolha **Integrar dispositivos**.

   > [!div class="mx-imgBorder"]
   > ![habilite o gerenciamento de dispositivos](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

   > [!NOTE]
   > Enquanto a integração de dispositivos geralmente leva cerca de 60 segundos para que seja habilitada, aguarde até 30 minutos antes de se envolver com o suporte da Microsoft.

3. Escolha **Gerenciamento de dispositivos** para abrir a lista **Dispositivos**. A lista estará vazia até você integrar os dispositivos.

4. Escolha **Integração** para iniciar o processo de integração.

5. Escolha a maneira como deseja implantar para esses dispositivos adicionais a partir da lista de **Método de implantação** e **Baixe o pacote**.

   > [!div class="mx-imgBorder"]
   > ![método de implantação](../media/endpoint-dlp-getting-started-3-deployment-method.png)

6. Siga os procedimentos apropriados em [Ferramentas e métodos de integração dos computadores do Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Este link leva você a uma página de destino onde você pode acessar os procedimentos da Proteção Avançada contra Ameaças do Microsoft Defender que correspondem ao pacote de implantação selecionado na etapa 5:

    - Integrar computadores com Windows 10 usando uma política de grupo
    - Integrar computadores com Windows usando o Microsoft Endpoint Configuration Manager
    - Integrar computadores com Windows 10 usando ferramentas de gerenciamento de dispositivo móvel
    - Integrar computadores com Windows 10 usando um script local
    - Integrar computadores VDI (infraestrutura de área de trabalho virtual) não persistente em cenários de sessão única.

Uma vez que o ponto de extremidade está integrado, ele deve estar visível na lista dispositivos e começar a relatar logs de atividades de auditoria para o Explorador de atividades.

> [!NOTE]
> Esta experiência está na imposição da licença. Sem a licença necessária, os dados não estarão visíveis nem acessíveis.

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a>Com dispositivos integrados no Microsoft Defender para Ponto de Extremidade.

Neste cenário, o Microsoft Defender para Ponto de Extremidade já está implantado e há relatórios de pontos de extremidade. Todos esses pontos de extremidade serão exibidos na lista dispositivos gerenciados. Você pode continuar a integrar novos dispositivos no ponto de extremidade DLP para expandir a cobertura usando o[Procedimento de integração de dispositivos](endpoint-dlp-getting-started.md#onboarding-devices).

1. Abra o [Centro de conformidade do Microsoft](https://compliance.microsoft.com).

2. Abra a página de configurações do Centro de conformidade e escolha **Habilitar o monitoramento de dispositivos**.

3. Escolha **Gerenciamento de dispositivos** para abrir a lista **Dispositivos**. Você deverá ver a lista de dispositivos que já estão relatando para o Microsoft Defender para Ponto de Extremidade.

   > [!div class="mx-imgBorder"]
   > ![gerenciamento de dispositivos](../media/endpoint-dlp-getting-started-2-device-management.png)

4. Escolha **Integração**, caso precise integrar dispositivos adicionais.

5. Escolha a maneira como deseja implantar para esses dispositivos adicionais a partir da lista de **Método de implantação** e **Baixe o pacote**.

6. Siga os procedimentos apropriados em [Ferramentas e métodos de integração dos computadores do Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Este link leva você a uma página de destino onde você pode acessar os procedimentos da Proteção Avançada contra Ameaças do Microsoft Defender que correspondem ao pacote de implantação selecionado na etapa 5:
    - Integrar computadores com Windows 10 usando uma política de grupo
    - Integrar computadores com Windows usando o Microsoft Endpoint Configuration Manager
    - Integrar computadores com Windows 10 usando ferramentas de gerenciamento de dispositivo móvel
    - Integrar computadores com Windows 10 usando um script local
    - Integrar computadores não persistentes da VDI (infraestrutura de desktop virtual).

Uma vez que o ponto de extremidade está integrado, ele deve estar visível na tabela **Dispositivos** e começar a relatar logs de atividades de auditoria para o **Explorador de atividades**.

> [!NOTE]
>Esta experiência está na imposição da licença. Sem a licença necessária, os dados não estarão visíveis nem acessíveis.

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a>Exibir alertas de prevenção contra perda de dados (DLP) do ponto de extremidade no painel de Gerenciamento de Alertas de DLP

1. Abra a Página de prevenção contra perda de dados no Centro de conformidade do Microsoft 365 e escolha Alertas.

2. Confira os procedimentos em [Como configurar e exibir alertas para suas políticas de DLP](dlp-configure-view-alerts-policies.md) para exibir alertas das políticas de DLP do ponto de extremidade.

### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a>Exibir dados de Endpoint DLP no explorador de atividades

1. Abra a [Página de classificação de dados](https://compliance.microsoft.com/dataclassification?viewid=overview) do seu domínio no Centro de conformidade do Microsoft 365 e escolha o Explorador de atividades.

2. Confira os procedimentos no [Comece a usar o Explorador de atividades](data-classification-activity-explorer.md) para acessar e filtrar todos os dados dos dispositivos de ponto de extremidade.

   > [!div class="mx-imgBorder"]
   > ![filtro do explorador de atividades para dispositivos de ponto de extremidade](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

## <a name="next-steps"></a>Próximas etapas

Agora que você tem dispositivos integrados e pode exibir os dados de atividade no Explorador de atividades, você está pronto para prosseguir para a próxima etapa na qual você cria políticas DLP que protegem seus itens confidenciais.

- [Usando a Prevenção contra perda de dados de ponto de extremidade](endpoint-dlp-using.md)

## <a name="see-also"></a>Confira também

- [Saiba mais sobre a Prevenção contra perda de dados do ponto de extremidade](endpoint-dlp-learn-about.md)
- [Usar a Prevenção contra perda de dados de ponto de extremidade](endpoint-dlp-using.md)
- [Saiba mais sobre prevenção contra perda de dados](dlp-learn-about-dlp.md)
- [Criar, testar e ajustar uma política DLP](create-test-tune-dlp-policy.md)
- [Começar a usar o Explorador de atividades](data-classification-activity-explorer.md)
- [Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection/)
- [Ferramentas e métodos de integração para computadores Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Assinatura do Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Dispositivos associados ao Microsoft Azure AD](/azure/active-directory/devices/concept-azure-ad-join)
- [Baixar o novo Microsoft Edge baseado em Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
