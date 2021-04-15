---
title: Começar com o painel de alertas de prevenção contra perda de dados
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
description: Começar a definir e gerenciar alertas para políticas de prevenção contra perda de dados.
ms.openlocfilehash: 7f070dd960cc00ad7899c75117cd2a3fcf679973
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760681"
---
# <a name="get-started-with-the-data-loss-prevention-alert-dashboard"></a>Começar com o painel de alertas de prevenção contra perda de dados

As políticas de prevenção contra perda de dados (DLP) podem tomar ações de proteção para evitar o compartilhamento não intencional de itens confidenciais. Quando uma ação é realizada em um item sensível, você pode ser notificado configurando alertas para DLP. Este artigo mostra como definir políticas de alerta rich que estão vinculadas às políticas de prevenção contra perda de dados (DLP). Você verá como usar o painel de gerenciamento de alertaS [DLP](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) no centro de conformidade do [Microsoft 365](https://compliance.microsoft.com/) para exibir alertas, eventos e metadados associados para violações de política DLP.

Se você for novo em alertas de DLP, revise Saiba mais sobre o [painel de alertas](dlp-alerts-dashboard-learn.md) de prevenção contra perda de dados

## <a name="before-you-begin"></a>Antes de começar

Antes de começar, certifique-se de ter os pré-requisitos necessários:

-   Licenciamento para o painel de gerenciamento de alertas de DLP
-   Licenciamento para opções de configuração de alerta
-   Funções

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>Licenciamento para o painel de gerenciamento de alertas DLP

Todos os locatários qualificados para a DLP do Office 365 podem acessar o painel de gerenciamento de alertas DLP. Para começar, você deve estar qualificado para o Office 365 DLP para Exchange Online, SharePoint Online e OneDrive for Business. Para obter mais informações sobre os requisitos de licenciamento para a DLP do Office 365, consulte Quais licenças fornecem os direitos para um usuário se [beneficiar do serviço?](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).

Os clientes que usam [a DLP](endpoint-dlp-learn-about.md) do Ponto de Extremidade que estão qualificados para a DLP do Teams verão seus alertas de política de [DLP](dlp-microsoft-teams.md) de ponto de extremidade e alertas de política de DLP do Teams no painel de gerenciamento de alertas DLP.

O **recurso de visualização** de conteúdo está disponível apenas para essas licenças:

- Microsoft 365 (E5)
- Office 365 (E5)
- Complemento de Conformidade Avançada (E5)
- Proteção e Governança de Informações do Microsoft 365 E5/A5
- Conformidade com o Microsft 365 E5/A5

### <a name="licensing-for-alert-configuration-options"></a>Licenciamento para opções de configuração de alerta

**Configuração de** alerta de evento único : organizações que têm uma assinatura E1, F1 ou G1 ou uma assinatura E3 ou G3 podem criar políticas de alerta somente onde um alerta é disparado sempre que uma atividade ocorre.

**Configuração de alerta agregada**: Para configurar políticas de alerta agregadas com base em um limite, você deve ter uma destas configurações de licenciamento:

- Uma assinatura E5 ou G5
- Uma assinatura E1, F1 ou G1 ou uma assinatura E3 ou G3 que inclui um dos seguintes recursos:
    - Plano 2 de proteção avançada contra ameaças do Office 365
    - Conformidade do Microsoft 365 E5
    - Licença de complemento descoberta e auditoria do Microsoft 365

### <a name="roles"></a>Funções


Se você quiser exibir o painel de gerenciamento de alertaS DLP ou editar as opções de configuração de alerta em uma política de DLP, você deve ser membro de um desses grupos de função:

- Administrador de Conformidade
- Administrador de Dados de Conformidade
- Administrador de Segurança
- Operador de segurança
- Leitor de segurança

Para acessar o painel de gerenciamento de alertas DLP, você precisa:

- Gerenciar alertas

e uma dessas duas funções:

- Gerenciamento de Conformidade de DLP
- View-Only gerenciamento de conformidade de DLP

Para acessar o recurso de visualização de conteúdo e os recursos de contexto e conteúdo confidenciais associados, você deve ser membro de:

- Grupo de função do Visualizador de Conteúdo do Explorador de Conteúdo

que tem a função de visualizador de conteúdo de classificação de dados pré-atribuída.

## <a name="dlp-alert-configuration"></a>Configuração de alerta DLP

Para saber como configurar um alerta em sua política de DLP, consulte [Where to start with data loss prevention](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention).

### <a name="aggregate-event-alert-configuration"></a>Configuração de alerta de evento agregado

Se sua organização estiver licenciada para opções [de](#licensing-for-alert-configuration-options)configuração de alerta agregada, você verá essas opções ao criar ou editar uma política de DLP.

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Captura de tela mostrando opções para relatórios de incidentes para usuários qualificados para opções de configuração de alerta agregadas." border="false":::

Essa configuração permite configurar uma política para gerar um alerta sempre que uma atividade corresponde às condições da política ou quando um determinado limite é excedido, com base no número de atividades ou com base no volume de dados exfiltrados.

### <a name="single-event-alert-configuration"></a>Configuração de alerta de evento único

Se sua organização estiver licenciada para opções de configuração de alerta de evento [único,](#licensing-for-alert-configuration-options)você verá essas opções ao criar ou editar uma política de DLP. Use essa opção para criar um alerta que é gerado sempre que uma combinação de regra de DLP acontece.

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Captura de tela mostrando opções para relatórios de incidentes para usuários qualificados para opções de configuração de alerta de evento único." border="false":::

## <a name="investigate-a-dlp-alert"></a>Investigar um alerta DLP

Para trabalhar com o painel de gerenciamento de alertas DLP:

1. No Centro de conformidade do [Microsoft 365,](https://www.compliance.microsoft.com)acesse **Prevenção** contra Perda de Dados .
2. Selecione a **guia Alertas** para exibir o painel de alertas DLP.
3. Selecione um alerta para ver detalhes:

:::image type="content" source="../media/alert-details.png" alt-text="Captura de tela mostrando detalhes do alerta no painel de gerenciamento de alertas DLP." border="false":::

4. Selecione a **guia Eventos** para exibir todos os eventos associados ao alerta. Você pode escolher um evento específico para exibir seus detalhes. Para obter uma lista de alguns dos detalhes do evento disponíveis, consulte Learn [about the data loss prevention Alerts dashboard](dlp-alerts-dashboard-learn.md).
5. Selecione **Detalhes** para abrir a página **Visão** Geral do alerta. A página de visão geral fornece um resumo:
    1. do que aconteceu
    1. que realizou as ações que causaram a combinação de política
    1. informações sobre a política de combinação e muito mais 

6. Escolha a **guia Eventos** para acessar:
    1. conteúdo envolvido
    1. tipos de informações confidenciais que corresponderam
    1. metadados

7. Selecione a **guia Tipos de Informações Confidenciais** para exibir detalhes sobre os tipos de informações confidenciais detectados no conteúdo. Os detalhes incluem confiança, contagem e o conteúdo que corresponde ao tipo de informação confidenciais.

8. Depois de investigar o alerta, volte para a guia **Visão** geral, onde você pode gerenciar a triagem e gerenciar a disposição do alerta e adicionar comentários.

- Para ver o histórico de gerenciamento de fluxo de trabalho, escolha **Log de gerenciamento.**
- Depois de tomar a ação necessária para o alerta, de definir o status do alerta como **Resolvido**.

## <a name="see-also"></a>Confira também

- [Saiba mais sobre alertas de prevenção contra perda de dados e o painel de alertas](dlp-alerts-dashboard-learn.md)
- [Criar, testar e ajustar uma política DLP](create-test-tune-dlp-policy.md)