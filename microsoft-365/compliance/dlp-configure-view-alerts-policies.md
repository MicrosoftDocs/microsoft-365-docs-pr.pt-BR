---
title: Configurar e exibir alertas para políticas de prevenção contra perda de dados
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
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
description: Saiba como definir e gerenciar alertas para políticas de prevenção contra perda de dados.
ms.openlocfilehash: ee04f6080edcde86dc39c7f4aa43130223fee8bf
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51750033"
---
# <a name="configure-and-view-alerts-for-data-loss-prevention-polices"></a>Configurar e exibir alertas para as polícias de prevenção contra perda de dados

As políticas de prevenção contra perda de dados (DLP) podem tomar ações de proteção para evitar o compartilhamento não intencional de itens confidenciais. Quando uma ação é realizada em um item sensível, você pode ser notificado configurando alertas para DLP. Este artigo mostra como definir políticas de alerta rich que estão vinculadas às políticas de prevenção contra perda de dados (DLP). Você verá como usar o novo painel de [](https://compliance.microsoft.com/) gerenciamento de alertaS DLP no centro de conformidade Microsoft 365 para exibir alertas, eventos e metadados associados para violações de política DLP.

<!-- LEFT OFF HERE-->

## <a name="features"></a>Recursos

Os seguintes recursos fazem parte disso:

-   Painel de gerenciamento de alertas de DLP : no centro de conformidade do [Microsoft 365,](https://compliance.microsoft.com/)este painel mostra alertas para políticas de **DLP** impostas nas seguintes cargas de trabalho:

    -   Exchange
    -   SharePoint
    -   OneDrive
    -   Teams
    -   Dispositivos
-   **Opções avançadas de configuração de** alerta: essas opções fazem parte do fluxo de autoria de política de DLP. Use-os para criar configurações avançadas de alerta. Você pode criar um alerta de evento único ou um alerta agregado, com base no número de eventos ou no tamanho dos dados vazados.

## <a name="before-you-begin"></a>Antes de começar

Antes de começar, certifique-se de ter os pré-requisitos necessários:

-   Licenciamento para o painel de gerenciamento de alertas de DLP
-   Licenciamento para opções de configuração de alerta
-   Funções

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>Licenciamento para o painel de gerenciamento de alertas DLP

Todos os locatários qualificados para Office 365 DLP podem acessar o novo painel de gerenciamento de alertas DLP. Para começar, você deve estar qualificado para Office 365 DLP para Exchange Online, SharePoint Online e OneDrive for Business. Para obter mais informações sobre os requisitos de licenciamento para Office 365 DLP, consulte Quais licenças fornecem os direitos para um usuário se [beneficiar do serviço?](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).

Os clientes que usam a [DLP](endpoint-dlp-learn-about.md) de ponto de extremidade qualificados para Teams DLP verão seus alertas de política [DLP](dlp-microsoft-teams.md) de ponto de extremidade e alertas de política de DLP do Teams no painel de gerenciamento de alertas DLP.

### <a name="licensing-for-alert-configuration-options"></a>Licenciamento para opções de configuração de alerta

-   **Configuração de** alerta de evento único : organizações que têm uma assinatura E1, F1 ou G1 ou uma assinatura E3 ou G3 podem criar políticas de alerta somente onde um alerta é disparado sempre que uma atividade ocorre.
-   **Configuração de alerta agregado**: Para configurar políticas de alerta agregadas com base em um limite, você deve ter uma das seguintes configurações:
    -   Uma assinatura E5 ou G5
    -   Uma assinatura E1, F1 ou G1 ou uma assinatura E3 ou G3 que inclui um dos seguintes recursos:
        -   Plano 2 de proteção avançada contra ameaças do Office 365
        -   Conformidade do Microsoft 365 E5
        -   Microsoft 365 eDiscovery and Audit add-on license

### <a name="roles"></a>Funções

Se você quiser exibir o painel de gerenciamento de alertaS DLP ou editar as opções de configuração de alerta em uma política de DLP, você deve ser membro de um desses grupos de função:

-   Administrador de Conformidade
-   Administrador de Dados de Conformidade
-   Administrador de Segurança
-   Operador de segurança
-   Leitor de segurança

Para acessar o painel de gerenciamento de alertas DLP, você precisa da função Gerenciar alertas e uma das seguintes funções:

-   Gerenciamento de Conformidade de DLP
-   View-Only gerenciamento de conformidade de DLP

## <a name="alert-configuration-experience"></a>Experiência de configuração de alerta

Se você estiver qualificado [](#licensing-for-alert-configuration-options)para opções de configuração de alerta agregadas, verá as seguintes opções em linha na experiência de autoria de política de DLP.

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Captura de tela mostrando opções para relatórios de incidentes para usuários qualificados para opções de configuração de alerta agregadas." border="false":::

Você pode usar essas opções de configuração de alerta para configurar uma configuração que define a frequência com que uma combinação de regra DLP pode ocorrer antes que um alerta seja disparado. Essa configuração permite configurar uma política para gerar um alerta sempre que uma atividade corresponde às condições da política ou quando um determinado limite é excedido, com base no número de atividades ou com base no volume de dados exfiltrados.

Se você estiver qualificado para opções de configuração de alerta de evento [único,](#licensing-for-alert-configuration-options)você verá a seguinte opção de configuração de alerta na experiência de autoria de política de DLP. Use essa opção para criar um alerta que é gerado sempre que uma combinação de regra de DLP acontece devido a uma atividade do usuário.

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Captura de tela mostrando opções para relatórios de incidentes para usuários qualificados para opções de configuração de alerta de evento único." border="false":::

## <a name="dlp-alert-management-dashboard"></a>Painel de gerenciamento de alertas DLP

Para trabalhar com o painel de gerenciamento de alertas DLP:

1.  No centro [Microsoft 365 de conformidade,](https://www.compliance.microsoft.com)vá para **Prevenção contra Perda de Dados**.

2.  Selecione a **guia Alertas** para exibir o painel de alertas DLP.

    -   Escolha filtros para refinar a lista de alertas. Escolha **Personalizar colunas** para listar as propriedades que você deseja ver. Você também pode optar por classificar os alertas em ordem crescente ou decrescente em qualquer coluna.
    -   Selecione um alerta para ver detalhes:

        :::image type="content" source="../media/alert-details.png" alt-text="Captura de tela mostrando detalhes do alerta no painel de gerenciamento de alertas DLP." border="false":::

1.  Selecione a **guia Eventos** para exibir todos os eventos associados ao alerta. Você pode escolher um evento específico para exibir seus detalhes.
    A tabela a seguir mostra alguns dos detalhes do evento.
    
    | Categoria          | Nome da propriedade                 | Descrição                                                                | Tipos de eventos aplicáveis                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |*Detalhes do evento*||
    |      | Id                            | ID exclusiva associada ao evento                                        | Todos os eventos                               |
    |                   | Localização                      | Carga de trabalho em que o evento foi detectado                                      | Todos os eventos                               |
    |                   | Hora da atividade              | Hora da atividade do usuário que causou a violação de DLP                    | Todos os eventos                               |
    |*Entidades impactadas*||
    |  | Usuário                          | Usuário que causou a violação de DLP                                          | Todos os eventos                               |
    |                   | Nome do host                      | Nome do host do computador em que a violação de DLP foi detectada              | Eventos de dispositivos                           |
    |                   | Endereço IP                    | Endereço IP do computador                                                  | Eventos de dispositivos                           |
    |                   | Caminho do arquivo                     | Caminho absoluto do arquivo envolvido na violação                        | SharePoint, OneDrive e dispositivos |
    |                   | Destinatários de email              | Destinatários do email que violou a política DLP                       | Exchange eventos                          |
    |                   | Assunto do email                 | Assunto do email que violou a política DLP                          | Exchange eventos                          |
    |                   | Anexos de e-mail             | Nomes dos anexos no email que violaram a política DLP         | Exchange eventos                          |
    |                   | Proprietário do site                    | Nome do proprietário do site                                                     | SharePoint e OneDrive eventos           |
    |                   | URL do site                      | URL completa do site SharePoint ou OneDrive site                                | SharePoint e OneDrive eventos           |
    |                   | Arquivo foi criado                  | Hora da criação de arquivos                                                      | SharePoint e OneDrive eventos           |
    |                   | Arquivo modificado pela última vez            | Hora da última modificação do arquivo                                  | SharePoint e OneDrive eventos           |
    |                   | Tamanho do arquivo                     | Tamanho do arquivo                                                           | SharePoint e OneDrive eventos           |
    |                   | Proprietário do arquivo                    | Proprietário do arquivo                                                          | SharePoint e OneDrive eventos           |
    |*Detalhes da política*||
    |     | Política de DLP corresponder            | Nome da política de DLP que foi corresponder                                    | Todos os eventos                               |
    |                   | Regra corresponder                  | Nome da regra DLP na política de DLP que foi corresponder                    | Todos os eventos                               |
    |                   | Tipos de informações confidenciais detectados | Tipos de informações confidenciais que foram detectados como parte da política de DLP | Todos os eventos                               |
    |                   | Medidas tomadas                 | Ações tomadas como parte da política de DLP corresponder                          | Todos os eventos                               |
    |                   | Política de overrode do usuário          | Se o usuário overrode a política por meio da dica de política                | Todos os eventos                               |
    |                   | Substituir texto de justificativa   | Justificativa fornecida para substituir a dica de política                          | Todos os eventos                               |
    
1.  Selecione a **guia Tipos de Informações Confidenciais** para exibir detalhes sobre os tipos de informações confidenciais detectados no conteúdo. Os detalhes incluem confiança e contagem.

2.  Depois de investigar o alerta, escolha **Gerenciar alerta** para alterar o status (**Ativo**, **Investigando,** **Ignorado** ou **Resolvido**). Você também pode adicionar comentários e atribuir o alerta a alguém em sua organização.

    -   Para ver o histórico de gerenciamento de fluxo de trabalho, escolha **Log de gerenciamento.**
    -   Depois de tomar a ação necessária para o alerta, de definir o status do alerta como **Resolvido**.