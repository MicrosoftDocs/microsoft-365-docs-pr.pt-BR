---
title: Introdução à prevenção contra perda de dados do Microsoft 365 Endpoint
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
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
description: Configure a prevenção contra perda de dados do Microsoft 365 Endpoint para monitorar as atividades de arquivo e implementar ações de proteção para os pontos de extremidade desse arquivo.
ms.openlocfilehash: 6ba3b83d634f946f818890a732a83166f346162d
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073090"
---
# <a name="get-started-with-endpoint-data-loss-prevention"></a>Introdução à Prevenção contra perda de dados do ponto de extremidade

A prevenção contra perda de dados do Microsoft Endpoint (Endpoint DLP) faz parte do pacote de recursos de prevenção contra perda de dados (DLP) do Microsoft 365 que você pode usar para descobrir e proteger itens confidenciais nos serviços do Microsoft 365. Para obter mais informações sobre todas as ofertas de DLP da Microsoft, confira [Visão geral da prevenção contra perda de dados](data-loss-prevention-policies.md). Para saber mais sobre o Endpoint DLP, confira [Saber mais sobre a prevenção contra perda de dados do ponto de extremidade](endpoint-dlp-learn-about.md)

A Prevenção contra perda de dados do Ponto de extremidade da Microsoft permite monitorar dispositivos Windows 10 e detectar quando itens confidenciais são usados ​​e compartilhados. Isso lhe dá a visibilidade e o controle de que você precisa para garantir que eles sejam usados ​​e protegidos adequadamente e para ajudar a prevenir comportamentos de risco que podem comprometê-los.

## <a name="before-you-begin"></a>Antes de começar

### <a name="skusubscriptions-licensing"></a>Licenciamento SKU/assinaturas

Antes de começar a usar a Prevenção contra perda de dados do Ponto de extremidade, você deve confirmar sua [assinatura do Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) e todos os complementos. Para acessar e usar a funcionalidade da DLP do ponto de extremidade, você deve ter uma dessas assinaturas ou complementos.

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

Os dados da Prevenção contra perda de dados do Ponto de extremidade podem ser visualizados no [Explorador de atividades](data-classification-activity-explorer.md). Existem quatro funções que concedem permissão ao explorador de atividades, a conta que você usa para acessar os dados deve ser membro de qualquer uma delas.

- Administrador global
- Administrador de conformidade
- Administrador de segurança
- Administrador de dados de conformidade

### <a name="prepare-your-endpoints"></a>Preparar seus pontos de extremidade

Certifique-se de que os dispositivos Windows 10 que você pretende implantar o Endpoint DLP atendam a esses requisitos.

1. Deve estar executando o Windows 10 x64 build 1809 ou superior.

2. A versão do cliente Antimalware é 4.18.2009.7 ou mais recente. Verifique a versão atual abrindo o aplicativo Segurança do Windows, selecione o ícone Configurações e, em seguida, selecione Sobre. O número da versão está listado em Versão Cliente Antimalware. Atualize para a Versão mais recente do Cliente Antimalware instalando o Windows Update KB4052623. Observação: Nenhum dos componentes de Segurança do Windows precisa estar ativo, você pode executar a Prevenção contra perda de dados do Ponto de extremidade independentemente do status de segurança do Windows.

3. As seguintes Atualizações do Windows são instaladas. Observação: Essas atualizações não são um pré-requisito para integrar um dispositivo a Prevenção contra perda de dados do Ponto de extremidade, mas contêm correções para problemas importantes, portanto, devem ser instaladas antes de usar o produto.

    - Para Windows 10 1809 - KB4559003, KB4577069, KB4580390
    - Para Windows 10 1903 ou 1909 - KB4559004, KB4577062, KB4580386
    - Para Windows 10 2004 - KB4568831, KB4577063
    - Para dispositivos que executam o Office 2016 (e nenhuma outra versão do Office) - KB4577063 

4. Todos os dispositivos devem ser associados ao [Azure Active Directory (Microsoft Azure AD)](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join) ou ingressado no Azure AD Híbrido.

5. Instale o navegador Microsoft Chromium Edge no dispositivo do ponto de extremidade para impor ações de política para o upload para a atividade na nuvem. Confira, [Baixe o novo Microsoft Edge baseado no Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).

6. Se você estiver no Canal Empresarial Mensal do Microsoft 365 Apps versões 2004-2008, há um problema conhecido com a Prevenção contra perda de dados do Ponto de extremidade classificando o conteúdo do Office e você precisa atualizar para a versão 2009 ou posterior. Confira [Histórico de atualizações para aplicativos do Microsoft 365 (listados por data)](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date) para as versões atuais. Para saber mais sobre esse problema, confira a seção do pacote do Office de [Notas de versão para lançamentos do Canal Atual em 2020](https://docs.microsoft.com/officeupdates/current-channel#version-2010-october-27).

## <a name="onboarding-devices-into-device-management"></a>Dispositivos de integração no gerenciamento de dispositivos

Você deve habilitar o monitoramento de dispositivo e integrar os seus pontos de extremidade antes de monitorar e proteger itens confidenciais em um dispositivo. Ambas as ações são realizadas no portal de Conformidade do Microsoft 365.

Quando quiser integrar dispositivos que ainda não foram integrados, você fará o download do script apropriado e o implantará nesses dispositivos. Siga o [Procedimento de dispositivos integrados](endpoint-dlp-getting-started.md#onboarding-devices).

Se você já tiver dispositivos integrados ao [Microsoft Defender para Ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection/), eles já aparecerão na lista de dispositivos gerenciados. Siga o [Procedimento Com dispositivos integrados ao Microsoft Defender para Ponto de Extremidade](endpoint-dlp-getting-started.md#with-devices-onboarded-into-microsoft-defender-for- endpoint).

### <a name="onboarding-devices"></a>Dispositivos de integração

Neste cenário de implantação, você integrará dispositivos que ainda não foram integrados e você só deseja monitorar e proteger itens confidenciais contra compartilhamento não intencional em dispositivos Windows 10.

1. Abra o [Centro de conformidade do Microsoft](https://compliance.microsoft.com).

2. Abra a página de configurações do Centro de conformidade e escolha **Integrar dispositivos**. 

   > [!div class="mx-imgBorder"]
   > ![habilite o gerenciamento de dispositivos](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

   > [!NOTE]
   > Enquanto a integração de dispositivos geralmente leva cerca de 60 segundos para que seja habilitada, aguarde até 30 minutos antes de se envolver com o suporte da Microsoft.

3. Escolha **Gerenciamento de dispositivos** para abrir a lista de **Dispositivos**. A lista ficará vazia até você integrar os dispositivos.

4. Escolha **Integração** para iniciar o processo de integração.

5. Escolha a maneira como deseja implantar para esses dispositivos adicionais a partir da lista de **Método de implantação** e **Baixe o pacote**.

   > [!div class="mx-imgBorder"]
   > ![método de implantação](../media/endpoint-dlp-getting-started-3-deployment-method.png)
   
6. Siga os procedimentos apropriados em [Ferramentas e métodos de integração para máquinas com Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Este link o leva a uma página de aterrissagem onde você pode acessar os procedimentos do Proteção Avançada contra Ameaças do Microsoft Defender que correspondem ao pacote de implantação selecionado na etapa 5:

    - Integrar computadores com Windows 10 usando uma Política de Grupo
    - Integrar computadores com Windows usando o Microsoft Endpoint Configuration Manager
    - Integrar computadores com Windows 10 usando ferramentas de gerenciamento de dispositivo móvel
    - Integrar computadores com Windows 10 usando um script local
    - Integrar computadores não persistentes da VDI (infraestrutura de desktop virtual).

Uma vez que o ponto de extremidade está integrado, ele deve estar visível na lista dispositivos e começar a relatar logs de atividades de auditoria para o Explorador de atividades.

> [!NOTE]
> Esta experiência está sob a aplicação de licença. Sem a licença necessária, os dados não estarão visíveis ou acessíveis.

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a>Com dispositivos integrados do Microsoft Defender para Ponto de Extremidade

Nesse cenário, o Proteção Avançada contra Ameaças do Microsoft Defender já está implantado e há relatórios de pontos de extremidade. Todos esses pontos de extremidade aparecerão na lista de dispositivos gerenciados. Você pode continuar a integrar novos dispositivos na Prevenção contra perda de dados do Ponto de extremidade para expandir a cobertura usando o [Procedimento de integração de dispositivos](endpoint-dlp-getting-started.md#onboarding-devices).

1. Abra o [Centro de conformidade do Microsoft](https://compliance.microsoft.com).

2. Abra a página de configurações do Centro de Conformidade e escolha **Habilitar o monitoramento de dispositivos**.

3. Escolha **Gerenciamento de dispositivos** para abrir a lista de **Dispositivos**. Você deve ver a lista de dispositivos que já estão se relatando ao Proteção Avançada contra Ameaças do Microsoft Defender.

   > [!div class="mx-imgBorder"]
   > ![gerenciamento de dispositivos](../media/endpoint-dlp-getting-started-2-device-management.png)
   
4. Escolha **Integração**, caso precise integrar dispositivos adicionais.

5. Escolha a maneira como deseja implantar para esses dispositivos adicionais a partir da lista de **Método de implantação** e **Baixe o pacote**.

6. Siga os procedimentos apropriados em [Ferramentas e métodos de integração para máquinas com Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Este link o leva a uma página de aterrissagem onde você pode acessar os procedimentos do Proteção Avançada contra Ameaças do Microsoft Defender que correspondem ao pacote de implantação selecionado na etapa 5:

    - Integrar computadores com Windows 10 usando uma Política de Grupo
    - Integrar computadores com Windows usando o Microsoft Endpoint Configuration Manager
    - Integrar computadores com Windows 10 usando ferramentas de gerenciamento de dispositivo móvel
    - Integrar computadores com Windows 10 usando um script local
    - Integrar computadores não persistentes da VDI (infraestrutura de desktop virtual).

Uma vez que o ponto de extremidade está integrado, ele deve estar visível na tabela **Dispositivos** e começar a relatar logs de atividades de auditoria para o **Explorador de atividades**.

> [!NOTE]
>Esta experiência está sob a aplicação de licença. Sem a licença necessária, os dados não estarão visíveis ou acessíveis.

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a>Exibir alertas de Prevenção contra perda de dados (DLP) do Ponto de extremidade no painel de Gerenciamento de Alertas da Prevenção contra perda de dados

1. Abra a Página de prevenção contra perda de dados no Centro de conformidade do Microsoft 365 e escolha Alertas.

2. Confira os procedimentos em [Como configurar e exibir alertas para suas políticas de DLP](dlp-configure-view-alerts-policies.md) para exibir alertas das políticas de DLP do ponto de extremidade.


### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a>Exibir dados de DLP do ponto de extremidade no explorador de atividades

1. Abra a [Página de classificação de dados](https://compliance.microsoft.com/dataclassification?viewid=overview) do seu domínio no Centro de conformidade do Microsoft 365 e escolha o Explorador de atividades.

2. Confira os procedimentos no [Comece a usar o Explorador de atividades](data-classification-activity-explorer.md) para acessar e filtrar todos os dados dos dispositivos de ponto de extremidade.

   > [!div class="mx-imgBorder"]
   > ![filtro do explorador de atividades para dispositivos de ponto de extremidade](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

## <a name="next-steps"></a>Próximos passos
Agora que você tem dispositivos integrados e pode exibir os dados de atividade no Explorador de atividades, você está pronto para prosseguir para a próxima etapa na qual você cria políticas DLP que protegem seus itens confidenciais.

- [Usando a prevenção contra perda de dados do EndPoint (visualização)](endpoint-dlp-using.md)

## <a name="see-also"></a>Confira também

- [Saiba mais sobre a prevenção contra perda de dados do EndPoint (visualização)](endpoint-dlp-learn-about.md)
- [Usando a prevenção contra perda de dados do EndPoint (visualização)](endpoint-dlp-using.md)
- [Visão geral da prevenção contra perda de dados](data-loss-prevention-policies.md)
- [Criar, testar e ajustar uma política DLP](create-test-tune-dlp-policy.md)
- [Começar a usar o Explorador de atividades](data-classification-activity-explorer.md)
- [Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/)
- [Ferramentas e métodos de integração para computadores Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Assinatura do Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Dispositivos associados ao Microsoft Azure AD](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [Baixar o novo Microsoft Edge baseado em Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
