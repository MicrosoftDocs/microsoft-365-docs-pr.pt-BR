---
title: Auditoria Avançada no Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: A Auditoria Avançada no Microsoft 365 fornece novos recursos de auditoria para ajudar sua organização com investigações forenses e de conformidade.
ms.openlocfilehash: 4812f81140bc80a1437c13b7bce38a7ed101592d
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/26/2020
ms.locfileid: "42280150"
---
# <a name="advanced-audit-in-microsoft-365"></a>Auditoria Avançada no Microsoft 365

A [funcionalidade de auditoria unificada](search-the-audit-log-in-security-and-compliance.md) no Microsoft 365 oferece às organizações a visibilidade de vários tipos de atividades auditadas em vários serviços do Microsoft 365. Agora, com o lançamento da Auditoria Avançada no Microsoft 365, estamos adicionando novos recursos de auditoria que podem ajudar sua organização nas investigações forenses e de conformidade.

> [!NOTE]
> A Auditoria Avançada está disponível para organizações com uma assinatura do Office 365 ou Microsoft 365 Enterprise E5. Além disso, uma assinatura de complemento do Microsoft 365 E5 Compliance pode ser atribuída aos usuários quando o licenciamento por usuário for necessário aos recursos de Auditoria avançada, como é o caso da retenção a longo prazo dos logs de auditoria e do acesso a eventos cruciais de investigações.

Este artigo fornece uma visão geral desses recursos de Auditoria Avançada.

## <a name="long-term-retention-of-audit-logs"></a>Retenção a longo prazo de logs de auditoria

A Auditoria Avançada mantém todos os registros de auditoria do Exchange, SharePoint e Azure Active Directory por um ano. Isso é feito por uma política de retenção de log de auditoria padrão que mantém qualquer registro de auditoria que contenha o valor **Exchange**, **SharePoint**ou **AzureActiveDirectory** da propriedade **Carga de trabalho** (que indica o serviço em que a atividade ocorreu) por um ano. Isso pode ajudar nas investigações forenses ou de conformidade em andamento. Para saber mais, confira a seção "Política de retenção de log de auditoria padrão" em [Gerenciar políticas de retenção de log de auditoria](audit-log-retention-policies.md#default-audit-log-retention-policy).

## <a name="audit-log-retention-policies"></a>Políticas de retenção de log de auditoria

Todos os registros de auditoria gerados em outros serviços que não são cobertos pela política de retenção de log de auditoria padrão (descrita na seção anterior) são retidos por 90 dias. No entanto, agora você pode criar políticas de retenção de logs de auditoria personalizadas para manter outros registros de auditoria por até um ano. Você pode criar uma política para manter registros de auditoria com base em um ou mais dos seguintes critérios:

- O serviço do Microsoft 365 em que as atividades auditadas ocorrem

- Atividades auditadas específicas

- O usuário que executa uma atividade auditada

Você também pode especificar por quanto tempo deseja manter registros de auditoria que correspondam à política e a um nível de prioridade, para que políticas específicas tenham prioridade sobre outras políticas. Observe também que qualquer política de retenção de log de auditoria personalizada terá precedência sobre a política de retenção de auditoria padrão, caso você precise reter registros de auditoria do Exchange, SharePoint ou Azure Active Directory por menos de um ano para alguns ou todos os usuários em sua organização. Para saber mais, confira [Gerenciar políticas de retenção de log de auditoria](audit-log-retention-policies.md).

## <a name="access-to-crucial-events-for-investigations"></a>Acesso aos eventos cruciais de investigações

Eventos cruciais de auditoria relacionados à segurança e conformidade são aqueles que podem ajudá-lo a investigar possíveis violações ou outras investigações forenses. O primeiro evento de alto valor que estamos lançando é a ação de auditoria de caixa de correio *MailItemsAccessed*. Esta ação é acionada quando os dados de email são acessados ​​por protocolos e clientes de email. A ação MailItemsAccessed pode ajudar os investigadores a identificar violações de dados e determinar o escopo das mensagens que podem ter sido comprometidas. Se um invasor obtiver acesso às mensagens de email, a ação MailItemsAccessed será acionada mesmo se não houver sinal explícito de que as mensagens foram realmente lidas (em outras palavras, o tipo de acesso, como via associação ou sincronização, é registrado no registro de auditoria).

A nova ação da caixa de correio MailItemsAccessed substitui o MessageBind no log de auditoria da caixa de correio do Exchange Online e fornece os seguintes aprimoramentos:

- O MessageBind era configurável apenas para o tipo de logon do usuário AuditAdmin; não se aplicava a ações de representante ou de proprietário. O MailItemsAccessed se aplica a todos os tipos de logon.

- O MessageBind abrangia apenas o acesso por um cliente de email. Não se aplicava a atividades de sincronização. Os eventos MailItemsAccessed são disparados pelos tipos de acesso de ligação e sincronização.

- As ações MessageBind acionariam a criação de vários registros de auditoria quando a mesma mensagem de email fosse acessada, o que resultava em "ruído" de auditoria. Por outro lado, os eventos MailItemsAccessed são agregados em menos registros de auditoria.

Para obter mais informações sobre o log de auditoria de caixa de correio, confira [Gerenciar a auditoria de caixa de correio](enable-mailbox-auditing.md).

### <a name="search-for-mailitemsaccessed-audit-records"></a>Pesquisar registros de auditoria MailItemsAccessed

Para pesquisar registros de auditoria MailItemsAccessed, é possível pesquisar a atividade **Itens da caixa de correio acessados**​​ na lista suspensa **Atividades da caixa de correio do Exchange** na [ferramenta de pesquisa de log de auditoria](search-the-audit-log-in-security-and-compliance.md) no Centro de Conformidade e Segurança do Office 365.

![Pesquisar ações MailItemsAccessed na ferramenta de pesquisa de log de auditoria](../media/MailItemsAccessedSCC1.png)

Você também pode executar os comandos [Search-UnifiedAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) ou [Search-MailboxAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) no PowerShell do Exchange Online.

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a>Acesso de alta largura de banda à API da Atividade de Gerenciamento do Office 365

As organizações que acessam logs de auditoria por meio da API da Atividade de Gestão do Office 365 foram restritas pelos limites no nível do editor. Isso significa que, para um editor obter dados em nome de vários clientes, o limite foi compartilhado por todos esses clientes.

Com o lançamento da Auditoria Avançada, passamos de um limite de nível de editor para um limite de nível de locatário. O resultado é que todas as organizações terão sua própria cota de largura de banda totalmente alocada para acessar os dados de auditoria. A largura de banda não é um limite estático predefinido, mas é modelada em uma combinação de fatores, incluindo o número de assentos na organização e que as organizações E5 terão mais largura de banda do que as organizações que não são E5.

Todas as organizações alocam inicialmente uma linha de base de 2.000 solicitações por minuto. Esse limite aumentará dinamicamente de acordo com a contagem de assentos de uma organização e de sua assinatura de licenciamento. As organizações E5 terão aproximadamente o dobro da largura de banda que as organizações que não são E5. Também haverá limite máximo quanto à largura de banda para proteger a integridade do serviço.

Para mais informações, confira a seção "limitação da API" em [Referência da API de atividade de gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling).

## <a name="faqs-for-advanced-audit"></a>Perguntas frequentes para Auditoria Avançada

**Onde posso acessar a Auditoria Avançada?**

Depois que a Auditoria Avançada for lançada em sua organização, você poderá criar políticas de retenção de log de auditoria e procurar registros de auditoria MailItemsAccessed usando a ferramenta de pesquisa de log de auditoria no [Centro de Conformidade e Segurança do Office 365](https://protection.office.com). Estamos trabalhando para implantar a Auditoria Avançada no [Centro de Conformidade do Microsoft 365](https://compliance.microsoft.com) nas próximas semanas.

**Todo usuário precisa de uma licença E5 para se beneficiar da Auditoria Avançada?**

Para se beneficiar dos recursos da Auditoria Avançada no nível de usuário, o usuário deve ter uma licença E5. Existem alguns recursos que verificarão a licença apropriada para expor o recurso ao usuário. Por exemplo, se você estiver tentando manter os registros de auditoria para um usuário que não tem uma licença E5 por mais de 90 dias, o sistema retornará uma mensagem de erro.

**Por que não vejo a Auditoria Avançada em minha organização, apesar de termos uma assinatura E5 e usuários com licenças E5 atribuídas?**

É possível que os recursos de Auditoria Avançada (como a capacidade de criar políticas de retenção de log de auditoria e o log de registros de auditoria MailItemsAccessed) não estejam disponíveis em sua organização, mesmo com o licenciamento correto em vigor. Caso esteja acontecendo, é porque o pacote de Auditoria Avançada ainda não foi implementado em sua organização. Esse é um problema de aterramento temporário de licenciamento, que deve ser resolvido para as organizações afetadas nas próximas semanas. Para atenuar esse problema, execute as seguintes etapas para cada usuário E5:

1. No centro de administração do Microsoft 365, acesse **Usuários > Usuários ativos** e selecione um usuário.

2. Na página do submenu de propriedades do usuário, clique em **Licenças e aplicativos**.

3. Expanda a seção **Aplicativos** e siga um destes procedimentos:

   a. Se a caixa de seleção **Auditoria Avançada do Microsoft 365** não estiver selecionada, selecione-a e clique em **Salvar alterações.** Os registros de auditoria para ações MailItemsAccessed para esse usuário devem ser pesquisáveis ​​em 24 horas.

   b. Se a caixa de seleção **Auditoria Avançada do Microsoft 365** estiver selecionada, desmarque-a e clique em **Salvar alterações.** Confira a etapa 4.

4. Se você desmarcou a caixa de seleção na etapa 3, aguarde 60 minutos e repita a etapa 3a para ativar o aplicativo Auditoria Avançada do Microsoft 365.

**O que acontece se minha organização estava na visualização privada para retenção de um ano de registros de auditoria?**

Suas políticas de retenção de auditoria do programa de visualização persistirão, desde que você não as substitua e as altere com políticas personalizadas de retenção de auditoria.

**E se a minha organização quiser reter os logs de auditoria por mais de um ano?**

Estamos explorando opções de como e se podemos fornecer períodos de retenção mais longos para registros de auditoria. Você pode enviar comentários sobre a retenção mais longa de registros de auditoria na [Voz do Usuário do Office 365](https://office365.uservoice.com/forums/289138-office-365-security-compliance?category_id=137187).

**Minha organização tem uma assinatura E5, preciso fazer algo para ter acesso aos registros de auditoria dos eventos MailItemsAccessed?**

Para clientes qualificados, não há ação para obter acesso aos eventos MailItemsAccessed. No entanto, conforme explicado anteriormente neste tópico, a latência causada pelo problema de aterramento de licenciamento pode impedir que os registros de auditoria do evento MailItemsAccessed sejam retornados em uma pesquisa de log de auditoria. Se isso ocorrer, siga as instruções na seção Pesquisar registros de auditoria MailItemsAccessed.

**Pretende lançar outros eventos neste ano?**

Sim, planejamos lançar novos eventos cruciais para as investigações nos próximos meses. Publicaremos informações sobre esses novos eventos no [Mapa do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) à medida que nos aproximamos de uma data de lançamento.

**Os novos eventos da Auditoria Avançada estão disponíveis na API da Atividade de Gerenciamento do Office 365?**

Sim. Desde que os registros de auditoria sejam gerados para os usuários com a licença adequada, você poderá acessá-los por meio da API da Atividade de Gerenciamento do Office 365.

**Maior largura de banda significa melhor latência ou SLA mais alto?**

No momento, a alta largura de banda fornece um pipeline melhor, especialmente para organizações com um alto volume de sinais de auditoria e padrões de consumo significativos. Isso pode levar a uma latência melhor. No entanto, não há um SLA associado à alta largura de banda. As latências padrão são documentadas e não mudam com o lançamento da Auditoria Avançada.
