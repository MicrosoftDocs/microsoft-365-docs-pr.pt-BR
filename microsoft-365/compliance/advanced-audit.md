---
title: Auditoria Avançada no Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-audit
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: A Auditoria Avançada no Microsoft 365 fornece novos recursos de auditoria para ajudar sua organização com investigações forenses e de conformidade.
ms.openlocfilehash: 3c91a388bc01a5531309b556a5a8532cb2efbaa6
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311711"
---
# <a name="advanced-audit-in-microsoft-365"></a>Auditoria Avançada no Microsoft 365

A [funcionalidade de auditoria unificada](search-the-audit-log-in-security-and-compliance.md) no Microsoft 365 oferece às organizações a visibilidade de vários tipos de atividades auditadas em vários serviços do Microsoft 365. A Auditoria Avançada ajuda as organizações a conduzir investigações forenses e de conformidade ao aumentar a retenção de log de auditoria necessária para conduzir uma investigação, fornecendo acesso a eventos cruciais que ajudam a determinar o escopo do comprometimento e acesso mais rápido à API da Atividade de Gestão do Office 365.

> [!NOTE]
> A Auditoria Avançada está disponível para organizações com uma assinatura do Office 365 E5/A5/G5 ou do Microsoft 365 Enterprise E5/A5/G5. Além disso, uma licença de complemento do Microsoft 365 E5/A5/G5 Compliance ou Descoberta Eletrônica E5/A5/G5 pode ser atribuída aos usuários quando o licenciamento por usuário for necessário para os recursos de Auditoria Avançada, como é o caso da retenção a longo prazo dos logs de auditoria e do acesso a eventos cruciais para investigações. Para obter mais informações sobre licenciamento, consulte:<br/>- [Requisitos de licenciamento da Auditoria Avançada](auditing-solutions-overview.md#licensing-requirements)<br/>- [Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-audit).

Este artigo fornece uma visão geral dos recursos de Auditoria Avançada e mostra como configurar usuários para Auditoria Avançada.

## <a name="long-term-retention-of-audit-logs"></a>Retenção a longo prazo de logs de auditoria

A Auditoria Avançada mantém todos os registros de auditoria do Exchange, SharePoint e Azure Active Directory por um ano. Isso é feito por uma política de retenção de log de auditoria padrão que mantém qualquer registro de auditoria que contenha o valor **Exchange**, **SharePoint** ou **AzureActiveDirectory** da propriedade **Carga de trabalho** (que indica o serviço em que a atividade ocorreu) por um ano. Manter os registros de auditoria por períodos mais longos pode ajudar com investigações de conformidade ou perícia contínua. Para saber mais, confira a seção "Política de retenção de log de auditoria padrão" em [Gerenciar políticas de retenção de log de auditoria](audit-log-retention-policies.md#default-audit-log-retention-policy).

Também estamos lançando o recurso de retenção de logs de auditoria por dez anos. A retenção de logs de auditoria por dez anos ajuda a dar suporte às investigações longas e a responder às obrigações normativas e legais.

> [!NOTE]
> Manter os logs de auditoria por dez anos exige uma licença adicional complementar. Para obter mais informações, confira a seção [Perguntas frequentes sobre Auditoria Avançada](#faqs-for-advanced-audit) desse artigo.

### <a name="audit-log-retention-policies"></a>Políticas de retenção de log de auditoria

Todos os registros de auditoria gerados em outros serviços que não são cobertos pela política de retenção de log de auditoria padrão (descrita na seção anterior) são retidos por 90 dias. Mas agora você pode criar políticas de retenção de logs de auditoria personalizadas para manter outros registros de auditoria por períodos mais longos de até dez anos. Você pode criar uma política para manter registros de auditoria com base em um ou mais dos seguintes critérios:

- O serviço do Microsoft 365 em que as atividades auditadas ocorrem.

- Atividades auditadas específicas.

- O usuário que executa uma atividade auditada.

Você também pode especificar por quanto tempo deseja manter registros de auditoria que correspondam à política e a um nível de prioridade, para que políticas específicas tenham prioridade sobre outras políticas. Observe também que qualquer política de retenção de log de auditoria personalizada terá precedência sobre a política de retenção de auditoria padrão, caso você precise reter registros de auditoria do Exchange, SharePoint ou Azure Active Directory por menos de um ano (ou por até dez anos) para alguns ou todos os usuários em sua organização. Para saber mais, confira [Gerenciar políticas de retenção de log de auditoria](audit-log-retention-policies.md).

## <a name="access-to-crucial-events-for-investigations"></a>Acesso aos eventos cruciais de investigações

A Auditoria Avançada ajuda as organizações a conduzirem investigações forenses e de conformidade, fornecendo acesso a eventos cruciais, como quando os itens de email foram acessados, quando os itens de email foram respondidos e encaminhados, e quando e o que um usuário pesquisava no Exchange Online e no SharePoint Online. Esses eventos cruciais podem ajudá-lo a investigar possíveis violações e a determinar o escopo dos comprometimentos.  A Auditoria Avançada oferece os seguintes eventos cruciais:

- [MailItemsAccessed](#mailitemsaccessed)

- [Send](#send)

- [SearchQueryInitiatedExchange](#searchqueryinitiatedexchange)<sup>*</sup>

- [SearchQueryInitiatedSharePoint](#searchqueryinitiatedsharepoint)<sup>*</sup>

> [!NOTE]
> <sup>*</sup> Neste momento, este evento não está disponível nos ambientes Office 365 e Microsoft 365 Government. Isto inclui ambientes GCC, GCC High, e DoD.

### <a name="mailitemsaccessed"></a>MailItemsAccessed

O evento MailItemsAccessed é uma ação de auditoria da caixa de correio e é acionado quando dados de email é acessado por protocolos de email e clientes de email. A ação MailItemsAccessed pode ajudar os investigadores a identificar violações de dados e determinar o escopo das mensagens que podem ter sido comprometidas. Se um invasor obtiver acesso às mensagens de email, a ação MailItemsAccessed será acionada mesmo se não houver sinal explícito de que as mensagens foram realmente lidas (em outras palavras, o tipo de acesso, como via associação ou sincronização, é registrado no registro de auditoria).

A ação da caixa de correio MailItemsAccessed substitui o MessageBind no log de auditoria da caixa de correio do Exchange Online e fornece os seguintes aprimoramentos:

- O MessageBind era configurável apenas para o tipo de logon do usuário AuditAdmin; não se aplicava a ações de representante ou de proprietário. O MailItemsAccessed se aplica a todos os tipos de logon.

- O MessageBind abrangia apenas o acesso por um cliente de email. Não se aplicava a atividades de sincronização. Os eventos MailItemsAccessed são disparados pelos tipos de acesso de ligação e sincronização.

- As ações MessageBind acionariam a criação de vários registros de auditoria quando a mesma mensagem de email fosse acessada, o que resultava em "ruído" de auditoria. Por outro lado, os eventos MailItemsAccessed são agregados em menos registros de auditoria.

Para obter informações sobre registros de auditoria para atividades MailItemsAccessed, confira [Usar auditoria avançada para investigar contas comprometidas](mailitemsaccessed-forensics-investigations.md).

Para pesquisar registros de auditoria MailItemsAccessed, é possível pesquisar a atividade **Itens da caixa de correio acessados**​​ na lista suspensa **Atividades da caixa de correio do Exchange** na [ferramenta de pesquisa de log de auditoria](search-the-audit-log-in-security-and-compliance.md) no centro de conformidade do Microsoft 365.

![Pesquisar ações MailItemsAccessed na ferramenta de pesquisa de log de auditoria](../media/AdvAudit_MailItemsAccessed.png)

Você também pode executar os comandos [Search-UnifiedAuditLog -Operations MailItemsAccessed](/powershell/module/exchange/search-unifiedauditlog) ou [Search-MailboxAuditLog -Operations MailItemsAccessed](/powershell/module/exchange/search-mailboxauditlog) no PowerShell do Exchange Online.

### <a name="send"></a>Send

O evento Send também é uma ação de auditoria de caixa de correio e é acionado quando um usuário realiza uma das seguintes ações:

- Envia uma mensagem de email

- Responde a uma mensagem de email

- Encaminha uma mensagem de email

Os investigadores podem usar o evento Send para identificar os emails enviados de uma conta comprometida. O registro de auditoria para um evento de Envio contém informações sobre a mensagem, como, por exemplo, quando a mensagem foi enviada, a ID de InternetMessage, o campo assunto e se a mensagem continha anexos. Essas informações de auditoria podem ajudar os investigadores a identificar informações sobre mensagens de email enviadas de uma conta comprometida ou enviadas por um invasor. Além disso, os investigadores podem usar uma ferramenta de Descoberta Eletrônica do Microsoft 365 para procurar a mensagem (usando o campo assunto ou ID da mensagem) para identificar os destinatários para os quais a mensagem foi enviada e o conteúdo real da mensagem enviada.

Para pesquisar os registros de auditoria Send, é possível pesquisar a atividade **Mensagem enviada**​​ na lista suspensa **Atividades da caixa de correio do Exchange** na [ferramenta de pesquisa de log de auditoria](search-the-audit-log-in-security-and-compliance.md) no centro de conformidade do Microsoft 365.

![Pesquisar ações Mensagem enviada na ferramenta de pesquisa de log de auditoria](../media/AdvAudit_SentMessage.png)

Você também pode executar os comandos [Search-UnifiedAuditLog -Operations Send](/powershell/module/exchange/search-unifiedauditlog) ou [Search-MailboxAuditLog -Operations Send](/powershell/module/exchange/search-mailboxauditlog) no PowerShell do Exchange Online.

### <a name="searchqueryinitiatedexchange"></a>SearchQueryInitiatedExchange

O evento SearchQueryInitiatedExchange é disparado quando uma pessoa usa o Outlook para pesquisar itens em uma caixa de correio. Os eventos são disparados quando pesquisas são realizadas nos seguintes ambientes do Outlook:

- Outlook (cliente de área de trabalho)

- Outlook na Web (OWA)

- Outlook para iOS

- Outlook para Android

- Aplicativo Email para Windows 10

Os investigadores podem usar o evento SearchQueryInitiatedExchange para determinar se um invasor que pode ter comprometido uma conta procurou por ou tentou acessar informações confidenciais na caixa de correio. O registro de auditoria para um evento SearchQueryInitiatedExchange contém informações como o texto atual de consulta de pesquisa. O registro de auditoria também indica o ambiente do Outlook onde a pesquisa foi realizada. Examinando as consultas de pesquisa que um invasor pode ter executado, um investigador pode entender melhor a intenção dos dados de email que foi pesquisado.

Para pesquisar os registros de auditoria SearchQueryInitiatedExchange, é possível pesquisar a atividade **Pesquisa de email realizada**​​ na lista suspensa **Atividades de pesquisa** na [ferramenta de pesquisa de log de auditoria](search-the-audit-log-in-security-and-compliance.md) no centro de conformidade.

![Pesquisar ações Pesquisa de email realizada na ferramenta de pesquisa de log de auditoria](../media/AdvAudit_SearchExchange.png)

Você também pode executar o [Search-UnifiedAuditLog – Operations SearchQueryInitiatedExchange](/powershell/module/exchange/search-unifiedauditlog) no PowerShell do Exchange Online.

> [!NOTE]
> Você deve habilitar o SearchQueryInitiatedExchange para ser registrado em log para poder procurar esse evento no log de auditoria. Para obter instruções, confira [Configurar a Auditoria Avançada](set-up-advanced-audit.md#step-2-enable-crucial-events).

### <a name="searchqueryinitiatedsharepoint"></a>SearchQueryInitiatedSharePoint

Semelhante à pesquisa de itens de caixa de correio, o evento SearchQueryInitiatedSharePoint é disparado quando uma pessoa pesquisa itens no SharePoint. Os eventos são disparados quando pesquisas são realizadas nos seguintes tipos de sites do SharePoint:

- Sites iniciais

- Sites de comunicação

- Sites do hub

- Sites associados ao Microsoft Teams

Os investigadores podem usar o evento SearchQueryInitiatedSharePoint para determinar se um invasor tentou localizar (e possivelmente acessar) informações confidenciais no SharePoint. O registro de auditoria para um evento SearchQueryInitiatedSharePoint contém também o texto real da consulta de pesquisa. O registro de auditoria também indica o tipo de site do SharePoint que foi pesquisado. Examinando as consultas de pesquisa que um invasor pode ter executado, um investigador pode entender melhor a intenção e o escopo dos dados do arquivo sendo pesquisado.

Para pesquisar os registros de auditoria SearchQueryInitiatedSharePoint, é possível pesquisar a atividade **Pesquisa SharePoint realizada**​​ na lista suspensa **Atividades de pesquisa** na [ferramenta de pesquisa de log de auditoria](search-the-audit-log-in-security-and-compliance.md) no centro de conformidade.

![Pesquisar ações Pesquisa SharePoint realizada na ferramenta de pesquisa de log de auditoria](../media/AdvAudit_SearchSharePoint.png)

Você também pode executar o [Search-UnifiedAuditLog – Operations SearchQueryInitiatedSharePoint](/powershell/module/exchange/search-unifiedauditlog) no PowerShell do Exchange Online.

> [!NOTE]
> Você deve habilitar o SearchQueryInitiatedSharePoint para ser registrado em log para poder procurar esse evento no log de auditoria. Para obter instruções, confira [Configurar a Auditoria Avançada](set-up-advanced-audit.md#step-2-enable-crucial-events).

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a>Acesso de alta largura de banda à API da Atividade de Gerenciamento do Office 365

As organizações que acessam logs de auditoria por meio da API da Atividade de Gestão do Office 365 foram restritas pelos limites no nível do editor. Isso significa que, para um editor obter dados em nome de vários clientes, o limite foi compartilhado por todos esses clientes.

Com o lançamento da Auditoria Avançada, passamos de um limite de nível de editor para um limite de nível de locatário. O resultado é que todas as organizações terão sua própria cota de largura de banda totalmente alocada para acessar os dados de auditoria. A largura de banda não é um limite estático predefinido. Ela é modelada em uma combinação de fatores, incluindo o número de assentos na organização e o fato de que as organizações E5/A5/G5 terão mais largura de banda do que as organizações que não são E5/A5/G5.

Todas as organizações alocam inicialmente uma linha de base de 2.000 solicitações por minuto. Esse limite aumentará dinamicamente de acordo com a contagem de assentos de uma organização e de sua assinatura de licenciamento. As organizações E5/A5/G5 terão aproximadamente o dobro da largura de banda que as organizações que não são E5/A5/G5. Também haverá limite máximo quanto à largura de banda para proteger a integridade do serviço.

Para mais informações, confira a seção "limitação da API" em [Referência da API de atividade de gerenciamento do Office 365](/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling).

## <a name="faqs-for-advanced-audit"></a>Perguntas frequentes para Auditoria Avançada

**Todo usuário precisa de uma licença E5/A5/G5 para se beneficiar da Auditoria Avançada?**

Para se beneficiar dos recursos da Auditoria Avançada no nível de usuário, o usuário deve ter uma licença E5/A5/G5. Existem alguns recursos que verificarão a licença apropriada para expor o recurso ao usuário. Por exemplo, se você estiver tentando manter os registros de auditoria para um usuário que não tem uma licença apropriada por mais de 90 dias, o sistema retornará uma mensagem de erro.

**Minha organização tem uma assinatura E5/A5/G5. Preciso fazer algo para obter acesso aos registros de auditoria para eventos cruciais?**

Para clientes qualificados e usuários atribuídos à licença apropriada, não há ação para obter acesso a eventos de auditoria cruciais.

**O que acontecerá com os dados do log de auditoria da minha organização se eu criar uma política de retenção de log de auditoria de 10 anos quando o recurso for lançado para disponibilidade geral, mas antes que a licença complementar necessária seja disponibilizada?**

Qualquer dado de registro de auditoria coberto por uma política de retenção de registro de auditoria de 10 anos que você criou após o lançamento do recurso à disponibilidade geral no último trimestre de 2020 será retido por 10 anos. Isto inclui políticas de retenção de logs de auditoria de 10 anos que foram criadas antes que a licença adicional necessária fosse liberada para compra. Entretanto, como a licença de 10 anos de retenção de logs de Auditoria Add On já está disponível, você precisará adquirir e atribuir essas licenças adicionais para quaisquer usuários cujos dados de auditoria estejam cobertos por uma política de retenção de auditoria de 10 anos.

**Os novos eventos da Auditoria Avançada estão disponíveis na API da Atividade de Gestão do Office 365?**

Sim. Desde que os registros de auditoria sejam gerados para os usuários com a licença adequada, será possível acessá-los por meio da API da Atividade de Gestão do Office 365.

**Maior largura de banda significa melhor latência ou SLA mais alto?**

No momento, a alta largura de banda fornece um pipeline melhor, especialmente para organizações com um alto volume de sinais de auditoria e padrões de consumo significativos. Uma maior largura de banda pode levar a uma latência melhor. No entanto, não há um SLA associado à alta largura de banda. As latências padrão são documentadas e essas latências não mudam com o lançamento da Auditoria Avançada.
