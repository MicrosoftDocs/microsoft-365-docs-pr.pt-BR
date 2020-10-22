---
title: Configurar e exibir alertas para políticas de DLP (versão prévia)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 10/15/2020
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Saiba como definir e gerenciar alertas para políticas de DLP.
ms.openlocfilehash: addf46b27575f1a1cc062949aedb7ecdecaf7286
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651445"
---
# <a name="configure-and-view-alerts-for-dlp-polices-preview"></a>Configurar e exibir alertas para políticas DLP (visualização)

Este artigo mostra como definir políticas de alerta avançadas que estão vinculadas às políticas de prevenção de perda de dados (DLP). Você verá como usar o novo painel de gerenciamento de alerta DLP no [centro de conformidade do Microsoft 365](https://compliance.microsoft.com/) para exibir alertas, eventos e metadados associados para violações de política de DLP.

## <a name="features"></a>Recursos

Os seguintes recursos fazem parte desta visualização:

-   **Painel de gerenciamento de alerta DLP**: no [centro de conformidade da Microsoft 365](https://compliance.microsoft.com/), este painel mostra alertas para políticas de DLP que são impostas nas seguintes cargas de trabalho:

    -   Exchange
    -   SharePoint
    -   OneDrive
    -   Teams
    -   Dispositivos
-   **Opções avançadas de configuração de alerta**: essas opções fazem parte do fluxo de criação da política DLP. Use-os para criar configurações de alerta avançadas. Você pode criar um alerta de evento único ou um alerta agregado, com base no número de eventos ou no tamanho dos dados vazados.

## <a name="before-you-begin"></a>Antes de começar

Antes de começar, verifique se você tem os pré-requisitos necessários:

-   Licenciamento para o painel de gerenciamento de alertas DLP
-   Licenciamento para opções de configuração de alerta
-   Funções

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>Licenciamento para o painel de gerenciamento de alerta DLP

Todos os locatários qualificados para o Office 365 DLP podem acessar o novo painel de gerenciamento de alerta DLP. Para começar, você deve estar qualificado para o Office 365 DLP para o Exchange Online, o SharePoint Online e o OneDrive for Business. Para obter mais informações sobre os requisitos de licenciamento do Office 365 DLP, consulte [quais licenças fornecem os direitos para um usuário se beneficiar do serviço?](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).

Os clientes que participam da visualização pública do [Endpoint DLP](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide) ou que estão qualificados para o [Team DLP](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams?view=o365-worldwide) verão seus alertas de política de DLP de ponto de extremidade e alertas de política de DLP do teams no painel de gerenciamento de alerta DLP.

### <a name="licensing-for-alert-configuration-options"></a>Licenciamento para opções de configuração de alerta

-   **Configuração de alerta de evento único**: as organizações que possuem uma assinatura E1, F1 ou G1 ou uma assinatura E3 ou G3 podem criar políticas de alerta somente quando um alerta é acionado sempre que uma atividade ocorre.
-   **Configuração de alerta agregado**: para configurar as políticas de alerta de agregação com base em um limite, você deve ter uma das seguintes configurações:
    -   Uma assinatura E5 ou G5
    -   Uma assinatura E1, F1 ou G1 ou uma assinatura E3 ou G3 que inclui um dos seguintes recursos:
        -   Plano 2 de proteção avançada contra ameaças do Office 365
        -   Conformidade do Microsoft 365 E5
        -   Licença de complemento do Microsoft 365 eDiscovery e auditoria

### <a name="roles"></a>Funções

Se você deseja exibir o painel de gerenciamento de alerta de DLP ou editar as opções de configuração de alerta em uma política de DLP, você deve ser um membro de um destes grupos de função:

-   Administrador de Conformidade
-   Administrador de dados de conformidade
-   Administrador de Segurança
-   Operador de segurança
-   Leitor de segurança

Para acessar o painel de gerenciamento de alerta DLP, você precisa da função Gerenciar alertas e qualquer uma das seguintes funções:

-   Gerenciamento de conformidade de DLP
-   View-Only gerenciamento de conformidade com DLP

## <a name="alert-configuration-experience"></a>Experiência de configuração de alerta

Se você estiver qualificado para obter [as opções de configuração de alerta agregado](#licensing-for-alert-configuration-options), verá as seguintes opções embutidas na experiência de criação de políticas de DLP.

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Captura de tela mostrando opções para relatórios de incidentes para usuários qualificados para as opções de configuração de alerta agregadas." border="false":::

Você pode usar essas opções de configuração de alerta para definir uma configuração que define com que frequência uma correspondência de regra de DLP pode ocorrer antes de um alerta ser acionado. Essa configuração permite que você configure uma política para gerar um alerta sempre que uma atividade corresponder às condições da política ou quando um determinado limite for excedido, com base no número de atividades ou com base no volume de dados do vazadas.

Se você estiver qualificado para [Opções de configuração de alerta de evento único](#licensing-for-alert-configuration-options), você verá a opção de configuração de alerta a seguir na experiência de criação de política de DLP. Use essa opção para criar um alerta que é gerado sempre que uma regra de DLP corresponde a ocorrer devido a uma atividade do usuário.

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Captura de tela mostrando opções para relatórios de incidentes para usuários qualificados para as opções de configuração de alerta agregadas." border="false":::

## <a name="dlp-alert-management-dashboard"></a>Painel de gerenciamento de alerta DLP

Para trabalhar com o painel de gerenciamento de alerta DLP:

1.  No [centro de conformidade da Microsoft 365](https://www.compliance.microsoft.com), vá para **prevenção de perda de dados**.

2.  Selecione a guia **alertas** para exibir o painel alertas de DLP.

    -   Escolha filtros para refinar a lista de alertas. Escolha **Personalizar colunas** para listar as propriedades que você deseja ver. Você também pode optar por classificar os alertas em ordem crescente ou decrescente em qualquer coluna.
    -   Selecione um alerta para ver os detalhes:

        :::image type="content" source="../media/alert-details.png" alt-text="Captura de tela mostrando opções para relatórios de incidentes para usuários qualificados para as opções de configuração de alerta agregadas." border="false":::

1.  Selecione a guia **eventos** para exibir todos os eventos associados ao alerta. Você pode escolher um evento específico para exibir seus detalhes.
    A tabela a seguir mostra alguns dos detalhes do evento.
    
    | Categoria          | Nome da propriedade                 | Descrição                                                                | Tipos de eventos aplicáveis                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |*Detalhes do evento*||
    |      | Id                            | ID exclusiva associada ao evento                                        | Todos os eventos                               |
    |                   | Local                      | Carga de trabalho em que o evento foi detectado                                      | Todos os eventos                               |
    |                   | Hora da atividade              | Hora da atividade do usuário que causou a violação de DLP                    | Todos os eventos                               |
    |*Entidades impactadas*||
    |  | Usuário                          | Usuário que causou a violação de DLP                                          | Todos os eventos                               |
    |                   | Nome do host                      | Nome do host do computador onde a violação de DLP foi detectada              | Eventos de dispositivos                           |
    |                   | Endereço IP                    | Endereço IP do computador                                                  | Eventos de dispositivos                           |
    |                   | Caminho do arquivo                     | Caminho absoluto do arquivo envolvido na violação                        | Eventos do SharePoint, OneDrive e dispositivos |
    |                   | Destinatários de email              | Destinatários do email que violaram a política de DLP                       | Eventos do Exchange                          |
    |                   | Assunto do email                 | Assunto do email que violou a política de DLP                          | Eventos do Exchange                          |
    |                   | Anexos de email             | Nomes dos anexos no email que violaram a política de DLP         | Eventos do Exchange                          |
    |                   | Proprietário do site                    | Nome do proprietário do site                                                     | Eventos do SharePoint e do OneDrive           |
    |                   | URL do site                      | URL completa do site do SharePoint ou do OneDrive                                | Eventos do SharePoint e do OneDrive           |
    |                   | Arquivo foi criado                  | Hora da criação do arquivo                                                      | Eventos do SharePoint e do OneDrive           |
    |                   | Última modificação do arquivo            | Hora da última modificação do arquivo                                  | Eventos do SharePoint e do OneDrive           |
    |                   | Tamanho do arquivo                     | Tamanho do arquivo                                                           | Eventos do SharePoint e do OneDrive           |
    |                   | Proprietário do arquivo                    | Proprietário do arquivo                                                          | Eventos do SharePoint e do OneDrive           |
    |*Detalhes da política*||
    |     | Política de DLP correspondida            | Nome da política de DLP que foi correspondida                                    | Todos os eventos                               |
    |                   | Regra correspondente                  | Nome da regra de DLP na política de DLP que foi correspondida                    | Todos os eventos                               |
    |                   | Tipos de informações confidenciais detectados | Tipos de informações confidenciais que foram detectadas como parte da política de DLP | Todos os eventos                               |
    |                   | Medidas tomadas                 | Ações tomadas como parte da política de DLP correspondente                          | Todos os eventos                               |
    |                   | Política de overrode de usuário          | Se o usuário overrode a política por meio da dica de política                | Todos os eventos                               |
    |                   | Substituir texto de justificação   | Justificativa fornecida para substituir a dica de política                          | Todos os eventos                               |
    
1.  Selecione a guia tipos de informações **confidenciais** para exibir detalhes sobre os tipos de informações confidenciais detectados no conteúdo. Os detalhes incluem confiança e contagem.

2.  Após investigar o alerta, escolha **gerenciar alerta** para alterar o status (**ativo**, **investigando**, **Descartado**ou **resolvido**). Você também pode adicionar comentários e atribuir o alerta a alguém em sua organização.

    -   Para ver o histórico de gerenciamento de fluxo de trabalho, escolha **log de gerenciamento**.
    -   Depois de executar a ação necessária para o alerta, defina o status do alerta como **resolvido**.
