---
title: Saiba mais sobre as políticas de retenção E os rótulos para reter ou excluir automaticamente o conteúdo
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Saiba mais sobre as políticas de retenção e os rótulos de retenção que ajudam você a manter o que precisa e excluir o que não.
ms.openlocfilehash: d8b9ff7bea32f489a5cce5f64626908e8ec56fa1
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197334"
---
# <a name="learn-about-retention-policies-and-retention-labels"></a>Saiba mais sobre as políticas de retenção e rótulos de retenção

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

Para a maioria das organizações, o volume e a complexidade dos dados aumentam diariamente, como emails, documentos, mensagens instantâneas e muito mais. O gerenciamento ou controle efetivo dessas informações é importante porque você precisa:
  
- **Estar em conformidade de forma proativa com as regulamentações do setor e as políticas internas** que exigem a retenção do conteúdo por um período mínimo de tempo, por exemplo, a lei Sarbanes-Oxley, que pode exigir que você guarde determinados tipos de conteúdo por sete anos. 

- **Reduzir seu risco em caso de litígio ou violação de segurança** excluindo definitivamente o conteúdo antigo que você não tem mais obrigação de guardar. 
    
- **Ajudar a sua organização a compartilhar conhecimento de maneira eficaz e ser mais ágil** garantindo que seus usuários trabalhem apenas com conteúdo atual e relevante para eles. 
    
As configurações de retenção que você configura podem ajudá-lo a atingir todos esses objetivos. O gerenciamento de conteúdo requer duas ações:
  
- **Reter** conteúdo para que ele não seja excluído permanentemente antes do fim do período de retenção. 
    
- **Excluir** conteúdo permanentemente no final do período de retenção. 
    

Com essas duas ações de retenção, você pode definir as configurações de retenção para os seguintes resultados:

- Reter somente: mantém o conteúdo infinitamente ou por um período de tempo especificado.
- Excluir somente: exclui o conteúdo após um período de tempo especificado.
- Reter e excluir: reter conteúdo por um período de tempo especificado e, em seguida, excluí-lo.

Essas configurações de retenção funcionam com o conteúdo que poupa os demais custos de criação e configuração de armazenamento adicional quando você precisar manter o conteúdo por motivos de conformidade. Além disso, não é necessário implementar processos personalizados para copiar e sincronizar esses dados.

## <a name="how-retention-settings-work-with-content-in-place"></a>Como funcionam as configurações de retenção com conteúdo no local

Quando o conteúdo tiver as configurações de retenção atribuídas a ele, esse conteúdo permanecerá no local original. As pessoas podem continuar a trabalhar com seus documentos ou emails como se nada tivesse mudado. Porém, se elas editarem ou excluírem o conteúdo incluído na política de retenção, uma cópia do conteúdo será retida automaticamente no momento em que você aplicou as configurações de retenção.
  
- Para sites do Microsoft Office SharePoint Online e do OneDrive: a cópia é retida na biblioteca de **Retenção para Preservação**.

- Para as caixas de correio do Exchange: a cópia é mantida na pasta **Itens Recuperáveis**. 

- Para as mensagens do Teams e do Yammer: a cópia é mantida em uma pasta oculta chamada **SubstrateHolds** como uma subpasta na pasta **Itens Recuperáveis** do Exchange.

> [!NOTE]
> A biblioteca de Retenção para Preservação consome armazenamento que não está isento da cota de armazenamento de um site. Pode ser necessário aumentar o armazenamento ao usar configurações de retenção para o SharePoint e os grupos do Microsoft 365.
> 
Esses locais seguros e o conteúdo retido não ficam visíveis para a maioria das pessoas. Na maioria dos casos, as pessoas não precisam saber que o conteúdo está sujeito às configurações de retenção.

Para obter informações mais detalhadas sobre como funcionam as configurações de retenção para diferentes cargas de trabalho, confira os seguintes artigos:

- [Saiba mais sobre retenção para o Microsoft Office SharePoint Online e o OneDrive](retention-policies-sharepoint.md)
- [Saiba mais sobre retenção para o Microsoft Teams](retention-policies-teams.md)
- [Saiba mais sobre retenção no Yammer](retention-policies-yammer.md)
- [Saiba mais sobre a retenção para o Exchange](retention-policies-exchange.md)

## <a name="retention-policies-and-retention-labels"></a>Políticas de retenção e rótulos de retenção

Você pode usar as políticas de retenção e os rótulos de retenção para atribuir as suas configurações de retenção ao conteúdo. 

Use uma política de retenção para atribuir as mesmas configurações de retenção para o conteúdo em um site ou nível de caixa de correio e usar um rótulo de retenção para atribuir configurações de retenção a um nível de item (pasta, documento, email).

Por exemplo, se todos os documentos em um site do Microsoft Office SharePoint Online devem ser mantidos por cinco anos, é mais eficiente fazer isso com uma política de retenção do que aplicar o mesmo rótulo de retenção a todos os documentos nesse site. No entanto, se alguns documentos desse site devem ser mantidos por 5 anos e outros forem retidos por 10 anos, uma política de retenção não poderá fazer isso. Quando você precisar especificar configurações de retenção no nível de item, use os rótulos de retenção. 

Diferentemente das políticas de retenção, as configurações de retenção de rótulos de retenção permanecem com o conteúdo, caso ele seja copiado ou movido para um local diferente do Microsoft 365. Além disso, os rótulos de retenção têm os seguintes recursos para os quais as políticas de retenção não têm suporte: 
 
- Opções para iniciar o período de retenção a partir do momento em que o conteúdo foi rotulado ou com base em um evento, além da idade do conteúdo ou de quando ele foi modificado pela última vez.

- Use [classificadores treináveis](classifier-learn-about.md) para identificar o conteúdo a ser rotulado.

- Aplicar um rótulo padrão para documentos do Microsoft Office SharePoint Online.

- Suporte [revisão de disposição](disposition-reviews.md) para revisar o conteúdo antes de ser permanentemente excluído.

- Marque o conteúdo como um [registro](records-management.md#records) como parte das configurações de rótulo e sempre tenha  [prova de disposição](disposition.md#disposition-of-records) quando o conteúdo é excluído ao fim do período de retenção.

### <a name="retention-policies"></a>Políticas de retenção

As políticas de retenção podem ser aplicadas aos seguintes locais:
- Email do Exchange
- Site do Microsoft Office SharePoint Online
- Contas do OneDrive
- Grupos do Microsoft 365
- Skype for Business
- Pastas públicas do Exchange
- Mensagens do canal do Teams
- Chats do Teams
- Mensagens da comunidade do Yammer
- Mensagens privadas do Yammer

Você pode aplicar uma única política de forma eficaz a vários locais ou a locais ou usuários específicos.
    
Aplicar uma política a todo o conteúdo ou ao conteúdo que atende condições específicas, por exemplo, como palavras-chave ou [tipos de informações confidenciais](sensitive-information-type-entity-definitions.md).

#### <a name="use-preservation-lock-to-comply-with-regulatory-requirements"></a>Usar o Bloqueio de Preservação para atender aos requisitos regulamentares

Algumas organizações talvez precisem cumprir regras definidas por órgãos regulamentadores, como a Regra 17a-4 da Securities and Exchange Commission (SEC), que exige que após uma política de retenção ser ativada, ela não pode ser desativada ou se tornar menos restritiva. 

O Bloqueio de Preservação garante que sua organização possa atender a requisitos regulatórios porque bloqueia uma política de retenção para que ninguém, incluindo o administrador, possa desativar a política, excluir a política ou torná-la menos restritiva.
  
Quando uma política de retenção está bloqueada:

- Ninguém pode desligá-lo
- Locais podem ser adicionados, mas não removidos
- O conteúdo sujeito à política não pode ser modificado ou excluído durante o período de retenção
- Você pode estender um período de retenção, mas não reduzi-lo

Em resumo, uma política de retenção bloqueada pode ser aumentada ou estendida, mas não poderá ser reduzida ou desativada.
  
> [!IMPORTANT]
> Antes de bloquear uma política de retenção, é fundamental que você entenda o impacto e confirme se ela é necessária para a sua organização atender aos requisitos normativos. Os administradores não poderão desabilitar ou excluir uma política de retenção após a aplicação do bloqueio de preservação.

Aplique o Bloqueio de Preservação após a política de retenção ser criada, usando o PowerShell. As instruções estão incluídas em [Criar e configurar políticas de retenção](create-retention-policies.md).

#### <a name="releasing-a-retention-policy"></a>Como liberar uma política de retenção

Desde que sua política de retenção não tenha um Bloqueio de Preservação, você pode desativar ou excluir uma política de retenção a qualquer momento. 

Quando você faz isso, todo o conteúdo do SharePoint ou do OneDrive que está sendo mantido na biblioteca de retenção de preservação não é excluído imediata e permanentemente. Em vez disso, para ajudar a evitar a perda acidental de dados, há um período de cortesia de 30 dias, durante o qual a expiração de conteúdo dessa política não acontece na biblioteca de retenção para preservação para que você possa restaurar todo o conteúdo de lá, se necessário. Além disso, não é possível excluir manualmente esse conteúdo durante o período de cortesia.

Você também pode ativar a política de retenção novamente durante o período de cortesia e nenhum conteúdo será excluído para essa política.

O período de cortesia de 30 dias no SharePoint e no OneDrive corresponde à retenção por atraso de 30 dias no Exchange. Para saber mais, confira [Gerenciar caixas de correios em retenção por atraso](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

### <a name="retention-labels"></a>Rótulos de retenção

Use rótulos de retenção para diferentes tipos de conteúdo que exigem diferentes configurações de retenção. Por exemplo:
  
- Formulários fiscais que precisam ser retidos por um período mínimo de tempo. 
    
- Materiais de imprensa que precisam ser excluídos permanentemente quando atingem uma certa idade. 
    
- Pesquisa competitiva que deve ser retida por um período específico e, em seguida, excluída permanentemente. 
    
- As tarefas de trabalho que devem ser marcadas como um registro para que não possam ser editadas ou excluídas. 
    
Em todos esses casos, os rótulos de retenção permitem aplicar configurações de retenção para controle de governança no nível de item (documento ou email).
  
Com os rótulos de retenção, você pode:
  
- **Habilitar as pessoas em sua organização a aplicar um rótulo manualmente** ao conteúdo no Outlook e Outlook na Web, OneDrive, SharePoint e em grupos do Microsoft 365. Geralmente, os usuários sabem com que tipo de conteúdo estão trabalhando, para que eles possam classificá-lo e ter as configurações de retenção apropriadas aplicadas. 
    
- **Aplique automaticamente os rótulos de retenção ao conteúdo** que corresponder a condições específicas, por exemplo, quando o conteúdo apresenta: 
    - Tipos específicos de informações confidenciais.
    - Palavras-chave específicas que correspondem a uma consulta criada por você.
    - Correspondências padrão para um classificador treinável.

- **Inicie o período de retenção a partir do momento em que o conteúdo foi rotulado** para documentos em sites do Microsoft Office SharePoint Online e contas do OneDrive e para itens de email com exceção dos itens do calendário. Se você aplicar um rótulo de retenção com essa configuração em um item de calendário, o período de retenção será iniciado a partir do momento em que ele for enviado.

- **Iniciar o período de retenção quando um evento ocorrer**, como funcionários saem da organização ou os contratos expiram.

- **Aplique um rótulo de retenção padrão a uma biblioteca de documentos** no SharePoint, de modo que todos os documentos que são armazenados naquele local herdem o rótulo de retenção padrão.

Além disso, os rótulos de retenção são compatíveis com o [gerenciamento de registros](records-management.md) de emails e documentos em todos os aplicativos e serviços da Microsoft 365. Você pode usar um rótulo de retenção para marcar os itens como um registro. Quando isso acontece e o conteúdo permanece no Microsoft 365, o rótulo impõe restrições adicionais ao conteúdo que pode ser necessário por motivos regulatórios. Para saber mais, confira [Comparar restrições para quais ações são permitidas ou bloqueadas](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).

Os rótulos de retenção, diferentemente dos [rótulos de sensibilidade](sensitivity-labels.md), não persistirão se o conteúdo for transferido fora do Microsoft 365.

Não há limite para o número de rótulos de retenção com suporte para um locatário. No entanto, 10.000 é o número máximo de políticas com suporte para um locatário, incluindo as políticas que aplicam os rótulos (políticas de rótulo de retenção e políticas de retenção automática), bem como políticas de retenção.

#### <a name="classifying-content-without-applying-any-actions"></a>Classificação do conteúdo sem aplicar ações

Embora o principal objetivo de rótulos de retenção seja reter ou excluir o conteúdo, você também pode usar os rótulos de retenção sem ativar qualquer retenção ou outras ações. Nesse caso, você pode usar um rótulo de retenção simplesmente como um rótulo de texto, sem aplicar ações.
  
Por exemplo, você pode criar e aplicar um rótulo de retenção chamado "Revisar mais tarde" sem ações e usar esse rótulo para localizar esse conteúdo mais tarde.
  
![Configurações de rótulo para classificar somente](../media/retention-label-retentionoff.png)

#### <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a>Usar um rótulo de retenção como condição em uma política DLP

Você pode especificar um rótulo de retenção como uma condição em uma política de prevenção contra perda de dados (DLP) para documentos no Microsoft Office SharePoint Online. Por exemplo, configure uma política DLP para evitar que os documentos sejam compartilhados fora da organização se eles tiverem um rótulo de retenção especificado aplicado a ele.

Para saber mais, confira [Usar um rótulo de retenção como condição em uma política DLP](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).

#### <a name="retention-labels-and-policies-that-apply-them"></a>Rótulos de retenção e políticas que os aplicam

Os rótulos de retenção são blocos de construção independentes e reutilizáveis. O objetivo principal da política de rótulos de retenção é agrupar um conjunto desses rótulos e especificar os locais em que você deseja que eles sejam exibidos. Em seguida, os administradores e os usuários podem aplicar esses rótulos ao conteúdo desses locais.
  
![Diagrama de rótulos, políticas de rótulos e locais](../media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
Quando você publica rótulos de retenção, eles são incluídos em uma política de rótulo de retenção que os torna disponíveis para administradores e usuários selecionarem:

- Um único rótulo de retenção pode ser incluído em várias políticas de rótulos de retenção.

- As políticas de rótulos de retenção especificam os locais de publicação dos rótulos de retenção.

- Um único local também pode ser incluído em várias políticas de rótulos de retenção.

Além das políticas de rótulo de retenção, você também pode criar uma ou mais políticas de aplicação automática, cada uma com um único rótulo de retenção. Com essa política, um rótulo de retenção é aplicado automaticamente quando as condições especificadas na política são atendidas. 

#### <a name="retention-label-policies-and-locations"></a>Políticas de rótulo de retenção e locais

É possível publicar tipos diferentes de rótulos de retenção em locais diferentes, dependendo do que o rótulo faz.
  
| Se o rótulo de retenção for... | A política de rótulo poderá ser aplicada para... |
|:-----|:-----|
|Publicado para administradores e usuários finais  <br/> |Exchange, SharePoint, OneDrive, Grupos do Microsoft 365  <br/> |
|Aplicada automaticamente com base em tipos de informações confidenciais ou classificadores treináveis  <br/> |Exchange (somente para todas as caixas de correio), SharePoint, OneDrive  <br/> |
|Aplicado automaticamente com base em uma consulta  <br/> |Exchange, SharePoint, OneDrive, Grupos do Microsoft 365  <br/> |
   
No Exchange, os rótulos de retenção de aplicação automática são aplicados somente às mensagens enviadas recentemente (dados em trânsito), não a todos os itens da caixa de correio (dados em repouso). Além disso, os rótulos de retenção de aplicação automática para tipos de informações confidenciais e classificadores treináveis aplicam-se a todas as caixas de correio. Não é possível selecionar caixas de correio específicas.
  
As pastas públicas do Exchange, Skype, Teams e as mensagens do Yammer não oferecem suporte a rótulos de retenção. Para reter e excluir conteúdo desses locais, use políticas de retenção.

#### <a name="only-one-retention-label-at-a-time"></a>Apenas um rótulo de retenção por vez

Um email ou um documento do pode ter apenas um único rótulo de retenção atribuído a ele por vez:
  
- Para rótulos de retenção atribuídos manualmente por administradores ou usuários finais, as pessoas podem remover ou alterar o rótulo de retenção que foi atribuído.
    
- Se o conteúdo tiver um rótulo de aplicação automática atribuído, esse rótulo poderá ser substituído por um rótulo de retenção publicado.
    
- Se o conteúdo tiver um rótulo de retenção publicado, um rótulo de aplicação automática não poderá substituí-lo.
    
- Se houver várias regras que atribuem um rótulo de aplicação automática, e o conteúdo atender às condições das regras, será atribuído o rótulo de retenção da regra mais antiga.
    
Para entender como e por que um rótulo de retenção é aplicado, em vez de outro, é bom compreender a diferença entre atribuir explicitamente ou implicitamente um rótulo:

- Os rótulos de retenção aplicados a uma política de rótulo são explicitamente atribuídos
- Os rótulos de retenção aplicados automaticamente de uma política de aplicação automática são atribuídos implicitamente

Um rótulo de retenção atribuído explicitamente tem precedência sobre um rótulo de retenção atribuído implicitamente. Para saber mais, confira a seção [Os princípios de retenção ou o que tem precedência](retention.md#the-principles-of-retention-or-what-takes-precedence) nesta página.

#### <a name="monitoring-retention-labels"></a>Monitorar rótulos de retenção

No Centro de conformidade do Microsoft 365, use **Classificação de dados** > **Visão geral** para monitorar como seus rótulos de retenção estão sendo usados em seu locatário e identifique onde estão os itens rotulados. Para saber mais, incluindo pré-requisitos importantes, confira [Aprenda sobre seus dados - visão geral de classificação de dados](data-classification-overview.md).

Voce pode fazer uma busca detalhada usando o [explorador de conteúdo](data-classification-content-explorer.md) e [explorador de atividade](data-classification-activity-explorer.md).

> [!TIP]
>Considere o uso de algumas das outras ideias de classificação de dados, como classificadores treináveis e tipos de informações confidenciais, para ajudar você a identificar o conteúdo que pode ser necessário reter, excluir, ou gerenciar como registros.

O Centro de Segurança e Conformidade do Office 365 possui as informações equivalentes de visão geral para rótulos de retenção em **Governança de informações** > **Painel**, e informações detalhadas em **Governança de informações** > **Explorador das atividades de rótulo**. Para saber mais sobre como monitorar os rótulos de retenção deste centro de administração antigo, confira a documentação a seguir:
- [Exibir os relatórios de governança de dados](view-the-data-governance-reports.md)
- [Exibição do uso do rótulo com análises de rótulo](label-analytics.md)
- [Exibir a atividade de rótulos de documentos](view-label-activity-for-documents.md)

#### <a name="using-content-search-to-find-all-content-with-a-specific-retention-label"></a>Usar a Pesquisa de Conteúdo para localizar todo o conteúdo com um rótulo de retenção específico

Depois que os rótulos de retenção são aplicados ao conteúdo, seja por usuários ou aplicados automaticamente, você pode usar a pesquisa de conteúdo para encontrar todos os itens que possuem um rótulo de retenção específico aplicado.

Ao criar uma pesquisa de conteúdo, escolha a condição **Rótulo de retenção** e, em seguida, digite o nome completo do rótulo de retenção ou parte dele e use um caractere curinga. Para saber mais, veja [Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo](keyword-queries-and-search-conditions.md).
  
![Condição do rótulo de retenção](../media/retention-label-condition.png)


## <a name="compare-capabilities-for-retention-policies-and-retention-labels"></a>Comparar recursos para políticas de retenção e rótulos de retenção

Use a tabela a seguir para ajudá-lo a identificar se deseja usar uma política de retenção ou um rótulo de retenção com base em recursos.

|Recursos|Política de retenção |Rótulo de retenção|
|:-----|:-----|:-----|:-----|
|Configurações de retenção que podem reter e excluir, somente reter ou somente excluir |Sim |Sim |
|Cargas de trabalho com suporte: <br />- Exchange <br />- Microsoft Office SharePoint Online <br />- OneDrive <br />- Grupos do Microsoft 365 <br />- Skype for Business <br />- Teams<br />- Yammer|<br /> Sim <br /> Sim <br /> Sim <br /> Sim <br /> Sim <br /> Sim | <br /> Sim, exceto as pastas públicas <br /> Sim <br /> Sim <br /> Sim <br /> Não <br /> Não <br /> Não |
|Retenção aplicada automaticamente | Sim | Sim |
|Retenção aplicada com base em condições <br /> - tipos de informações confidenciais, consultas de KQL, classificadores de treinamento| Não | Sim |
|Retenção aplicada manualmente | Não | Sim |
|Presença da interface de usuário para usuários finais | Não | Sim |
|Persiste se o conteúdo for movido | Não | Sim, no Microsoft 365 |
|Declarar um item como um registro| Não | Sim |
|Iniciar o período de retenção ao rotular ou com base em um evento | Não | Sim |
|Revisão de disposição | Não| Sim |
|Prova de disposição por até 7 anos | Não |Sim, quando o item é declarado um registro|
|Auditoria de atividades administrativas| Sim | Sim|
|Identifique os itens sujeitos à retenção: <br /> - Pesquisa de Conteúdo <br /> - Página de classificação de dados, explorador de conteúdo, explorador de atividades | <br /> Não <br /> Não | <br /> Sim <br /> Sim|

Observe que você pode usar as políticas de retenção e os rótulos de retenção como métodos de retenção complementares. Por exemplo:

1. Você cria e configura uma política de retenção que exclui automaticamente o conteúdo cinco anos após a última modificação, e aplica a política a todas as contas do OneDrive.

2. Você cria e configura um rótulo de retenção que mantém o conteúdo infinitamente e adiciona-o a uma política de rótulo publicada em todas as contas do OneDrive. Você explica aos usuários como aplicar manualmente esse rótulo a documentos específicos que devem ser retirados da exclusão automática se não forem modificados após cinco anos.

Para obter mais informações sobre como as políticas de retenção e os rótulos de retenção funcionam juntos e como determinar o resultado combinado, confira a próxima seção que explica os princípios de retenção e o que tem precedência.

## <a name="the-principles-of-retention-or-what-takes-precedence"></a>Os princípios de retenção ou o que tem precedência?

É possível ou até mesmo provável que o conteúdo tenha várias políticas de retenção e rótulos de retenção aplicados a ele, cada uma com uma ação diferente (reter, excluir ou reter e depois excluir) e o período de retenção. O que tem precedência? 

Em um nível alto, você pode ter a certeza de que a retenção sempre tem precedência sobre a exclusão e, em seguida, o período de retenção mais longo vence. 

No entanto, há mais alguns fatores a serem incluídos na mistura, portanto use o seguinte fluxo para compreender o resultado em que cada nível atua como um disjuntor de cima para baixo: se o resultado for determinado pelo primeiro nível, não será necessário progredir para o próximo nível e assim por diante. Somente se o resultado não puder ser determinado pelas regras para o nível, o fluxo se moverá para baixo até o próximo nível para determinar o resultado para o qual as configurações de retenção têm precedência.

![Diagrama dos princípios de retenção](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
Explicação para os quatro níveis diferentes:
  
1. **A retenção prevalece sobre a exclusão.** Suponha que uma política de retenção esteja configurada para excluir o email do Exchange após três anos, mas que outra política de retenção esteja configurada para manter o email do Exchange por cinco anos e depois excluí-lo. Qualquer conteúdo com três anos será excluído e ocultado dos usuários, mas ainda será mantido na pasta Itens Recuperáveis até que o conteúdo complete cinco anos, quando será permanentemente excluído. 
2. **O período de retenção mais longo prevalece.** Se o conteúdo estiver sujeito a várias configurações de retenção que retêm o conteúdo para diferentes períodos de tempo, o conteúdo será retido até o fim do período de retenção mais longo.
    
3. **A inclusão explícita prevalece sobre a inclusão implícita.** Isso significa que: 
    
    1. Se um rótulo de retenção com configurações de retenção for atribuídos manualmente por um usuário a um item, como um email do Exchange ou um documento do OneDrive, esse rótulo de retenção tem precedência sobre uma política de retenção atribuída no nível do site ou da caixa de correio e um rótulo de retenção padrão atribuído à biblioteca de documentos. Por exemplo, se o rótulo de retenção explícito estiver configurado para reter o conteúdo por dez anos, mas uma política de retenção atribuída ao site está configurada para reter conteúdo por apenas cinco anos, o rótulo de retenção tem precedência. Os rótulos de retenção de aplicação automática são considerados implícitos, não explícitos, pois são aplicados automaticamente pelo Microsoft 365.
    
    2. Se uma política de retenção incluir um local específico, como a caixa de correio de um usuário específico ou conta OneDrive, essa política de retenção terá precedência sobre outra política de retenção que se aplica a caixas de correio de todos os usuários ou contas do OneDrive, mas não incluirá especificamente essa caixa de correio do usuário.
    
4. **O período de exclusão mais curto tem precedência.** Da mesma forma, se o conteúdo estiver sujeito a várias configurações de retenção que excluem conteúdo sem um período de retenção, esse conteúdo será excluído ao fim do período de retenção mais curto. 

Por fim, uma política de retenção ou um rótulo de retenção não pode excluir permanentemente qualquer conteúdo que esteja em espera para Descoberta Eletrônica. Quando a retenção for liberada, o conteúdo estará novamente qualificado para o processo de limpeza no local seguro para a carga de trabalho.

## <a name="auditing-retention-configuration"></a>Configuração de retenção de auditoria

As ações de administrador para as políticas de retenção e os rótulos de retenção são salvas no log de auditoria quando a [auditoria está habilitada](turn-audit-log-search-on-or-off.md). Por exemplo, um evento de auditoria é criado quando uma política de retenção ou um rótulo é criado, configurado ou excluído. Para a lista completa, confira [Política de retenção e atividades do rótulo de retenção](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities).

## <a name="powershell-cmdlets-for-retention-policies-and-retention-labels"></a>Cmdlets do Windows PowerShell para políticas de retenção e rótulos de retenção

Para usar os cmdlets de retenção, primeiro você deve [se conectar ao PowerShell do Centro de Segurança e Conformidade do Office 365](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell). Em seguida, use um dos seguintes cmdlets:

- [Get-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)

- [New-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)

- [Remove-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)

- [Set-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)

- [Enable-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)

- [Get-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)

- [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)

- [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)

- [Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)

- [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)

- [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)

- [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)

- [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)

- [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)

## <a name="use-retention-policies-and-retention-labels-instead-of-older-features"></a>Use as políticas de retenção e os rótulos de retenção em vez de recursos mais antigos

Se você precisar reter ou excluir o conteúdo proativamente no Microsoft 365 para o controle de informações, recomendamos usar as políticas de retenção e os rótulos de retenção em vez dos recursos mais antigos. 
  
Se você usa esses recursos mais antigos, eles continuarão a funcionar lado a lado com as políticas de retenção e os rótulos de retenção. No entanto, recomendamos que, daqui para frente, você use políticas de retenção e rótulos de retenção. Eles fornecem um único mecanismo para gerenciar centralmente a retenção e a exclusão de conteúdo no Microsoft 365.

**Recursos mais antigos do Exchange Online:**

- [Bloqueio In-loco e a Retenção de Litígio](https://go.microsoft.com/fwlink/?linkid=846124) (Retenção de Descoberta Eletrônica) 

- [Como identificar o tipo de retenção de uma caixa de correio do Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md)
    
- [Marcas de retenção e políticas de retenção](https://go.microsoft.com/fwlink/?linkid=846125), também conhecidas como [gerenciamento de registros de mensagens (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (apenas exclusão)
    
Confira também [Baixa das ferramentas de Descoberta Eletrônica herdadas](legacy-ediscovery-retirement.md).


**Recursos mais antigos do SharePoint e do OneDrive:**

- [Adicionar conteúdo a uma ocorrência e colocar fontes em retenção na Descoberta Eletrônica](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center) (Retenção de Descoberta Eletrônica) 
    
- [Políticas de exclusão documento](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (apenas exclusão)
    
- [Como configurar o gerenciamento de registros no local](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (apenas retenção) 
    
- [Usar políticas de fechamento de site e exclusão](https://support.microsoft.com/pt-BR/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (apenas exclusão) 
    
- [Políticas de gerenciamento de informações](intro-to-info-mgmt-policies.md) (apenas exclusão)
     
Se tiver usado anteriormente qualquer um dos bloqueios de descoberta eletrônica para fins de governança de informações, use uma política de retenção para conformidade proativa. Use a Descoberta Eletrônica para apenas bloqueios.
  
### <a name="retention-policies-and-sharepoint-content-type-policies-or-information-management-policies"></a>Políticas de retenção e políticas de tipo de conteúdo do SharePoint ou políticas de gerenciamento de informações

Se você configurou sites do SharePoint para políticas de tipo de conteúdo ou políticas de gerenciamento de informações para reter o conteúdo de uma lista ou biblioteca, essas políticas serão ignoradas enquanto uma política de retenção estiver em vigor. 

## <a name="related-information"></a>Informações relacionadas

- [Limites do SharePoint Online](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [Limites e especificações para o Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [Cumprir com a Regra 17a-4 da SEC](use-exchange-online-to-comply-with-sec-rule-17a-4.md)

## <a name="next-steps"></a>Próximas etapas

Se você estiver pronto para criar políticas de retenção, consulte [Criar e configurar as políticas de retenção](create-retention-policies.md).

Para criar e aplicar rótulos de retenção:
- [Criar rótulos de retenção e aplicá-los em aplicativos](create-apply-retention-labels.md)
- [Aplicar um rótulo de retenção automaticamente ao conteúdo](apply-retention-labels-automatically.md)

