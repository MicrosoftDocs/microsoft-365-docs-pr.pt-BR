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
ms.openlocfilehash: bd7b4f78d37feddd7c66322460a6532a77045ba2
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988663"
---
# <a name="advanced-audit-in-microsoft-365"></a>A Auditoria Avançada no Microsoft 365

A [funcionalidade de auditoria unificada](search-the-audit-log-in-security-and-compliance.md) no Microsoft 365 fornece às organizações visibilidade em muitos tipos de atividades auditadas em diversos serviços no Microsoft 365. A Auditoria Avançada ajuda as organizações a conduzir investigações forenses e de conformidade, aumentando a retenção de log de auditoria necessária para conduzir uma investigação, fornecendo acesso a eventos cruciais que ajudam a determinar o escopo de comprometimento e acesso mais rápido à API de Atividade de Gestão do Office 365.

> [!NOTE]
> A Auditoria Avançada está disponível para organizações com uma assinatura do Office 365 E5/G5 ou do Microsoft 365 Enterprise E5/G5. Além disso, uma licença do Microsoft 365 E5 Compliance, ou do complemento de Auditoria e Descoberta Eletrônica do E5 podem ser atribuídos aos usuários quando o licenciamento por usuário for necessário para os recursos de Auditoria Avançada, como é o caso da retenção a longo termo dos logs de auditoria e do acesso a eventos cruciais de investigações. Para mais informações sobre licenciamento, confira [Orientação de licenciamento do Microsoft 365 para segurança e conformidade](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-audit).

Este artigo fornece uma visão geral dos recursos de Auditoria Avançada.

## <a name="long-term-retention-of-audit-logs"></a>Retenção de longo termo de logs de auditoria

A Auditoria Avançada retém todos os registros de auditoria do Exchange, Microsoft Office SharePoint Online e Azure Active Directory por um ano. Isso é realizado por uma política de retenção de log de auditoria padrão que retém qualquer registro de auditoria que contenha o valor de propriedade do **Exchange** , **Microsoft Office SharePoint Online** ou **AzureActiveDirectory** para a **Carga de trabalho** (que indica o serviço em que ocorreu a atividade) por um ano. A retenção de registros de auditoria por períodos mais longos pode ajudar nas investigações forenses ou de conformidade em andamento. Para obter mais informações, confira a seção "Política de retenção de registro de auditoria padrão" em [Gerenciar políticas de retenção de log de auditoria](audit-log-retention-policies.md#default-audit-log-retention-policy).

Também estamos lançando a capacidade de reter logs de auditoria por 10 anos. A retenção de logs de auditoria por 10 anos ajuda a apoiar investigações de longa duração e responder às obrigações regulatórias, legais e internas.

> [!NOTE]
> Reter logs de auditoria por 10 anos exigirá uma licença complementar adicional. Essa nova licença estará disponível no início de 2021. Para obter mais informações, confira a seção [ Perguntas frequentes para Auditoria Avançada ](#faqs-for-advanced-audit) neste artigo.

### <a name="audit-log-retention-policies"></a>Políticas de retenção de log de Auditoria

Todos os registros de auditoria gerados em outros serviços que não são cobertos pela política de retenção de log de auditoria padrão (descrita na seção anterior) são retidos por 90 dias. Mas você pode criar políticas de retenção de log de auditoria personalizadas para reter outros registros de auditoria por períodos mais longos de até 10 anos. Você pode criar uma política para reter registros de auditoria baseado em um ou mais dos seguintes critérios:

- O serviço Microsoft 365 onde ocorrem as atividades auditadas.

- Atividades auditadas específicas.

- O usuário que executa uma atividade auditada.

Você também pode especificar por quanto tempo reter os registros de auditoria que correspondem à política e um nível de prioridade para que políticas específicas tenham prioridade sobre outras políticas. Observe também que qualquer política de retenção de log de auditoria personalizada terá precedência sobre a política de retenção de auditoria padrão caso você precise reter registros de auditoria do Exchange, Microsoft Office SharePoint Online ou Azure Active Directory por menos de um ano (ou por 10 anos) para alguns ou todos os usuários em sua organização. Para obter mais informações, confira [Gerenciar políticas de retenção de log de auditoria ](audit-log-retention-policies.md).

## <a name="access-to-crucial-events-for-investigations"></a>Acesso a eventos cruciais para investigações

A Auditoria Avançada ajuda as organizações a conduzir investigações forenses e de conformidade, fornecendo acesso a eventos cruciais, como quando itens de email foram acessados ​​ou quando itens de email foram respondidos e encaminhados e quando e o que um usuário pesquisou no Exchange Online e no SharePoint Online. Esses eventos cruciais podem ajudá-lo a investigar possíveis violações e determinar o escopo do comprometimento. A Auditoria Avançada fornece os seguintes eventos cruciais:

- [MailItemsAccessed](#mailitemsaccessed)

- [Send](#send)

- [SearchQueryInitiatedExchange](#searchqueryinitiatedexchange)

- [SearchQueryInitiatedSharePoint](#searchqueryinitiatedsharepoint)

### <a name="mailitemsaccessed"></a>MailItemsAccessed

O evento MailItemsAccessed é uma ação de auditoria de caixa de correio e é acionado quando os dados de correio são acessados ​​por protocolos de correio e clientes de correio. A ação MailItemsAccessed pode ajudar os investigadores a identificar violações de dados e determinar o escopo das mensagens que podem ter sido comprometidas. Se um invasor obtiver acesso às mensagens de email, a ação MailItemsAccessed será acionada mesmo se não houver nenhum sinal explícito de que essas mensagens foram realmente lidas (em outras palavras, o tipo de acesso, como vinculação ou sincronização, é registrado no registro de auditoria).

A ação de caixa de correio MailItemsAccessed substitui MessageBind no registro de log de auditoria de caixa de correio no Exchange Online e fornece estas melhorias:

- O MessageBind só era configurável para o tipo de logon do usuário AuditAdmin; ele não se aplicava a ações de delegação ou proprietário. O MailItemsAccessed se aplica a todos os tipos de logon.

- O MessageBind cobria apenas o acesso por um cliente de email. Ele não se aplicava a atividades de sincronização. Os eventos MailItemsAccessed são acionados pelos tipos de acesso de associação e sincronização.

- As ações do MessageBind acionariam a criação de vários registros de auditoria quando a mesma mensagem de email fosse acessada, o que resultava em "ruído" de auditoria. Em contraste, os eventos MailItemsAccessed são agregados em menos registros de auditoria.

Para obter informações sobre registros de auditoria para atividades MailItemsAccessed, confira [Use a Auditoria Avançada para investigar contas comprometidas](mailitemsaccessed-forensics-investigations.md).

Para pesquisar registros de auditoria MailItemsAccessed, é possível pesquisar a atividade **Itens da caixa de correio acessados** ​​ na lista suspensa **Atividades da caixa de correio do Exchange** na [ferramenta de pesquisa de log de auditoria](search-the-audit-log-in-security-and-compliance.md) no centro de conformidade do Microsoft 365.

![Pesquisar ações MailItemsAccessed na ferramenta de pesquisa de log de auditoria](../media/AdvAudit_MailItemsAccessed.png)

Você também pode executar os comandos [Search-UnifiedAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) ou [Search-MailboxAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) no PowerShell do Exchange Online.

### <a name="send"></a>Send

O evento Send também é uma ação de auditoria de caixa de correio e é acionado quando um usuário realiza uma das seguintes ações:

- Envia uma mensagem de email

- Responde a uma mensagem de email

- Encaminhar um email

Os investigadores podem usar o evento Send para identificar o email enviado de uma conta comprometida. O registro de auditoria para um evento Send contém informações sobre a mensagem, como quando a mensagem foi enviada, o ID InternetMessage, a linha de assunto e se a mensagem continha anexos. Essas informações de auditoria podem ajudar os investigadores a identificar informações sobre mensagens de email enviadas de uma conta comprometida ou enviadas por um invasor. Além disso, os investigadores podem usar uma ferramenta de descoberta eletrônica do Microsoft 365 para pesquisar a mensagem (usando a linha de assunto ou ID da mensagem) para identificar os destinatários para os quais a mensagem foi enviada e o conteúdo real da mensagem enviada.

Para pesquisar registros de auditoria de Envio, você pode pesquisar a atividade **mensagem Enviada** na lista suspensa **atividades de caixa de correio do Exchange** na [ ferramenta de pesquisa de registro de auditoria](search-the-audit-log-in-security-and-compliance.md) no Centro de conformidade do Microsoft 365.

![Pesquisar ações Mensagem enviada na ferramenta de pesquisa de log de auditoria](../media/AdvAudit_SentMessage.png)

Você também pode executar os comandos [Search-UnifiedAuditLog -Operations Send](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) ou [Search-MailboxAuditLog -Operations Send](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) no PowerShell do Exchange Online.

### <a name="searchqueryinitiatedexchange"></a>SearchQueryInitiatedExchange

O evento SearchQueryInitiatedExchange é acionado quando uma pessoa usa a barra de Pesquisa do Outlook na Web (OWA) para pesquisar itens em uma caixa de correio. Os investigadores podem usar o evento SearchQueryInitiatedExchange para determinar se um invasor que pode ter comprometido uma conta procurou ou tentou acessar informações confidenciais na caixa de correio. O registro de auditoria para um evento SearchQueryInitiatedExchange contém informações como o texto real da consulta de pesquisa. Observando as consultas de pesquisa que um invasor pode ter realizado, um investigador pode entender melhor a intenção dos dados de email que foram pesquisados.

Para pesquisar registros de auditoria SearchQueryInitiatedExchange, você pode pesquisar a atividade **Pesquisa de email realizada** na lista suspensa **Pesquisar atividades** na [ferramenta de pesquisa de log de auditoria](search-the-audit-log-in-security-and-compliance.md) no centro de conformidade.

![Pesquisar ações Pesquisa de email realizada na ferramenta de pesquisa de log de auditoria](../media/AdvAudit_SearchExchange.png)

Você também pode executar o [Search-UnifiedAuditLog – Operations SearchQueryInitiatedExchange](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) no PowerShell do Exchange Online.

> [!NOTE]
> Você deve executar o comando a seguir no PowerShell do Exchange Online para que os eventos do SearchQueryInitiatedExchange (feitos pelo usuário E5 especificado) sejam incluídos nos resultados de pesquisa de log de auditoria: `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`.

### <a name="searchqueryinitiatedsharepoint"></a>SearchQueryInitiatedSharePoint

Semelhante à pesquisa de itens de caixa de correio, o evento SearchQueryInitiatedSharePoint é acionado quando uma pessoa pesquisa por itens no site inicial do Microsoft Office SharePoint Online para a organização. Os investigadores podem usar o evento SearchQueryInitiatedSharePoint para determinar se um invasor tentou localizar (e possivelmente acessou) informações confidenciais no Microsoft Office SharePoint Online. O registro de auditoria para um evento SearchQueryInitiatedSharePoint contém também o texto real da consulta de pesquisa. Observando as consultas de pesquisa que um invasor pode ter realizado, um investigador pode entender melhor a intenção e o escopo dos dados do arquivo que estão sendo pesquisados.

Para pesquisar registros de auditoria SearchQueryInitiatedSharePoint, você pode pesquisar a atividade de **pesquisa realizada do Microsoft Office SharePoint Online** na lista suspensa **Atividades de pesquisa** na [ ferramenta de pesquisa de log de auditoria](search-the-audit-log-in-security-and-compliance.md) no centro de conformidade.

![Pesquisar ações Pesquisa SharePoint realizada na ferramenta de pesquisa de log de auditoria](../media/AdvAudit_SearchSharePoint.png)

Você também pode executar o [Search-UnifiedAuditLog – Operations SearchQueryInitiatedSharePoint](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) no PowerShell do Exchange Online.

> [!NOTE]
> Você deve executar o comando a seguir no PowerShell do Exchange Online para que os eventos do SearchQueryInitiatedSharePoint (feitos pelo usuário E5 especificado) sejam incluídos nos resultados de pesquisa de log de auditoria: `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`.

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a>Acesso de alta largura de banda à API da Atividade de Gestão do Office 365

As organizações que acessam logs de auditoria por meio da API da Atividade de Gestão do Office 365 foram restringidas por limites de aceleração no nível do fornecedor. Isso significa que, para um fornecedor que extrai dados em nome de vários clientes, o limite foi compartilhado por todos esses clientes.

Com o lançamento do Auditoria Avançada, estamos passando de um limite no nível de fornecedor para um limite no nível de locatário. O resultado é que cada organização obterá sua própria cota de largura de banda totalmente alocada para acessar seus dados de auditoria. A largura de banda não é um limite predefinido estático, mas é modelado em uma combinação de fatores, incluindo o número de usuários na organização e que as organizações E5 obterão mais largura de banda do que as organizações não-E5.

Todas as organizações recebem inicialmente uma linha de base de 2.000 solicitações por minuto. Este limite aumentará dinamicamente dependendo da contagem de usuários de uma organização e sua assinatura de licenciamento. As organizações E5 obterão cerca de duas vezes mais largura de banda do que as organizações não-E5. Haverá também um limite na largura de banda máxima para proteger a integridade do serviço.

Para obter mais informações, confira a seção "Controle de API" na [referência da API da Atividade de Gestão do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling).

## <a name="faqs-for-advanced-audit"></a>Perguntas frequentes para Auditoria Avançada

**Todo usuário precisa de uma licença E5 para se beneficiar da Auditoria Avançada?**

Para se beneficiar dos recursos de Auditoria Avançada em nível de usuário, um usuário precisa ser atribuído a uma licença E5. Existem alguns recursos que verificarão a licença apropriada para expor o recurso para o usuário. Por exemplo, se você estiver tentando reter os registros de auditoria de um usuário ao qual não foi atribuída uma licença E5 por mais de 90 dias, o sistema retornará uma mensagem de erro.

**Minha organização tem uma assinatura E5, preciso fazer algo para obter acesso aos registros de auditoria para eventos cruciais?**

Para clientes qualificados e usuários atribuídos à licença apropriada, não há ação para obter acesso a eventos de auditoria cruciais.

**Quando a nova licença complementar de retenção de log de auditoria de 10 anos estará disponível?**

O novo complemento de retenção de log de auditoria de dez anos estará disponível para compra pelos clientes com assinaturas E5 no início de 2021.

**O que acontecerá com os dados do log de auditoria da minha organização se eu criar uma política de retenção de log de auditoria de dez anos, o recurso for lançado para disponibilidade geral, mas antes da licença complementar necessária estar disponível no início de 2021?**

Todos os dados de log de auditoria cobertos por uma política de retenção de log de auditoria de dez anos que você criar após a disponibilidade geral serão retidos por dez anos. Quando o acréscimo de retenção de log de auditoria de dez anos estiver disponível no início de 2021, será necessário comprar licenças adicionais para usuários que os dados de auditoria estão retidos por uma política de retenção de auditoria existente de dez anos. Além disso, uma vez que a licença de ação esteja disponível no início de 2021, o licenciamento apropriado será aplicado quando você criar uma nova retenção de log de auditoria de dez anos.

**Os novos eventos da Auditoria Avançada estão disponíveis na API da Atividade de Gestão do Office 365?**

Sim. Desde que os registros de auditoria sejam gerados para os usuários com a licença adequada, será possível acessá-los por meio da API da Atividade de Gestão do Office 365.

**Maior largura de banda significa melhor latência ou SLA mais alto?**

Neste momento, a alta largura de banda fornece um pipeline melhor, especialmente para organizações com um alto volume de sinais de auditoria e padrões de consumo significativos. Mais largura de banda pode levar a uma melhor latência. Mas não há um SLA associado à alta largura de banda. As latências padrão são documentadas, e essas latências não mudam com o lançamento da Auditoria Avançada.
