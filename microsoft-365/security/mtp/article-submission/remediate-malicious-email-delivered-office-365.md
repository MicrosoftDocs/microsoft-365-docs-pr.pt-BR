---
title: Corrigir emails mal-intencionados que foram entregues no Office 365
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.topic: article
ms.service: Microsoft Threat Protection
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection: ''
search.appverid: MET150
description: Correção de ameaças
appliesto:
- Microsoft Threat Protection
ms.openlocfilehash: eb86c0b8e5368a42daa1002de5ac361613037090
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086686"
---
# <a name="remediate-malicious-email-that-was-delivered-in-office-365"></a>Corrigir emails mal-intencionados que foram entregues no Office 365

Correção significa realizar uma ação inscrita em relação a uma ameaça. Emails maliciosos enviados para sua organização podem ser limpos pelo sistema, por meio de exclusão automática de zero horas ou por equipes de segurança por meio de ações de correção, como mover para a caixa de entrada, mover para o lixo eletrônico, mover para a pasta itens excluídos, exclusão reversível ou exclusão de hardware. Proteção avançada contra ameaças do Office (Office ATP) P2/E5 oferece às equipes de operações de segurança a capacidade de mediar ameaças em emails e problemas de colaboração por meio de buscas manuais e investigações automatizadas.

> [!NOTE]
> Para que as equipes de segurança remediam os emails, eles precisam ter a função de pesquisa e limpeza atribuída a eles. A atribuição de função é feita por meio de permissões no centro de conformidade e segurança. <p>

## <a name="what-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar

Para executar determinadas ações, como exibir cabeçalhos de mensagens ou baixar conteúdo de mensagens de email, você deve ter uma nova função chamada *Preview* adicionada a outro grupo de função apropriado. A tabela a seguir esclarece as funções e permissões necessárias.

|Atividade  |Grupo de função |Função prévia necessária?  |
|---------|---------|---------|
|Usar o explorador de ameaças (e detecções em tempo real) para analisar ameaças     |Administrador Global <br> Administrador de Segurança <br> Leitor de segurança     | Não   |
|Usar o explorador de ameaças (e detecções em tempo real) para exibir cabeçalhos para mensagens de email, bem como para visualizar e baixar mensagens de email em quarentena    |Administrador Global <br> Administrador de Segurança <br>Leitor de segurança   |       Não  |
|Usar o explorador de ameaças para exibir cabeçalhos e baixar mensagens de email entregues a caixas de correio     |Administrador Global <br>Administrador de Segurança <br> Leitor de segurança <br> Preview   |   Sim      |

> [!NOTE]
> *Preview* é uma função e não um grupo de função; a função Preview deve ser adicionada a um grupo de função existente para o Office 365. A função de administrador global é atribuída ao centro de administração do Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) ), e as funções do administrador de segurança e do leitor de segurança são atribuídas no centro de conformidade do & de segurança [https://protection.office.com](https://protection.office.com) . Para saber mais sobre funções e permissões, consulte [permissões no centro de conformidade de & de segurança.](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center?view=o365-worldwide)

> [!NOTE]
> Os administradores podem realizar ações obrigatórias em emails, mas para fazer suas ações aprovadas, eles devem ter a função "pesquisa e limpeza" atribuída a eles por meio do centro de conformidade e segurança > permissões.

## <a name="manual-and-automated-remediation"></a>Correção manual e automatizada

A **caça manual** ocorre quando o Security Teams identifica ameaças manualmente, usando os recursos de pesquisa e filtragem no Gerenciador de ameaças. A correção manual de emails pode ser disparada por qualquer modo de exibição de email (malware, phishing ou todos os emails) após a localização de um conjunto de emails que precisam ser corrigidos.

![Caça manual no Office 365 Threat Explorer por data.](../../../media/tp-RemediationArticle1.png "Explorador de Ameaças")

A seleção de emails pode ser feita de várias maneiras por meio do explorador de ameaças:

1. Escolher emails à mão: isso significa que as equipes de operações de segurança podem usar filtros nos respectivos modos de exibição e selecionar alguns emails do explorador de ameaças que precisam ser corrigidos. O limite superior para selecionar emails é 100 (100). As equipes de operações de segurança não podem selecionar mais de cem emails, manualmente.

2. Seleção de consulta: as equipes de operações de segurança podem selecionar uma consulta inteira usando o botão superior "selecionar tudo". A mesma consulta também é mostrada nos detalhes de envio de mensagens da central de ações.

3. Seleção de consulta com exclusão: pode haver momentos em que as equipes de operações de segurança decidem corrigir emails, selecionando uma consulta inteira e excluindo manualmente alguns emails da consulta. Para fazer isso, um administrador pode usar a caixa de seleção "selecionar tudo" e rolar para baixo para excluir alguns emails, manualmente. O número máximo de emails que a consulta pode conter é 1000 (1.000) e o número máximo de exclusões é 100 (100), neste caso.

Depois que os emails são selecionados no Gerenciador de ameaças, a criação de correções pode começar executando a ação direta ou enfileirar emails para uma ação:

1. Aprovação direta: quando ações como ' mover para a caixa de entrada ', ' mover para o lixo eletrônico ', ' mover para itens excluídos ', ' exclusão reversível ', ' exclusão de hardware ' são selecionadas pelo pessoal de segurança com as permissões apropriadas, e as próximas etapas são seguidas até a criação de correção, o processo de correção começa a executar uma ação selecionada. Um submenu temporário mostra A correção em andamento.

2. Aprovação em duas etapas: a ação "adicionar à correção" pode ser tomada por um administrador que não tem permissões apropriadas ou que precisa esperar mais para executar a ação. Nesse caso, a ação de correção não é executada diretamente. Em vez disso, os emails são adicionados a um contêiner de correção que deve ser aprovado para executar. Até que a correção seja aprovada, o email não será corrigido. Depois que a correção for aprovada, as ações serão realizadas no email.

As ações **automatizadas de investigação e resposta (ar)** são acionadas por alertas ou por equipes de operações de segurança de dentro do explorador de ameaças. Eles podem incluir algumas mediações recomendadas que devem ser aprovadas por equipes de operações de segurança. Essas ações de correção estão incluídas na guia ação dentro da investigação automatizada.  

:::image type="content" source="../../../media/tp-RemediationArticle3.png" alt-text="O email com malware é zapped página mostrando a hora da execução de zap.":::

Toda a mediação (aprovação direta ou aprovação em duas etapas) criada por meio do explorador de ameaças e de ações aprovadas vindas de investigações automatizadas, exibidas na central de ações, que podem ser acessadas por meio da navegação à esquerda em *revisão*da >  **central de ações**.

:::image type="content" source="../../../media/tp-RemediationArticle4.png" alt-text="A central de ações com uma lista de ameaças por data e severidade.":::

A central de ações mostra todas as ações de correção dos últimos 30 dias. As ações realizadas por meio do Explorer são exibidas com o mesmo nome fornecido pelas equipes de operações de segurança quando a correção foi criada. As ações realizadas por meio de investigações automatizadas são exibidas com títulos que começam com o alerta relacionado que disparou a investigação (por exemplo, "zap email cluster...".

Cada item de correção pode ser aberto para exibir detalhes sobre ele. Quando um item de correção é aberto, ele mostra detalhes básicos de correção, o nome de correção, a data de criação, a descrição, a severidade da ameaça e o status. Ele também mostra duas guias. 

1. **Guia envio de email**: Este é o número de emails enviados pelo Gerenciador de ameaças ou investigações automatizadas a serem corrigidos. Esses emails podem ser:

**Acionável**: os emails nos seguintes locais de caixa de correio na nuvem podem ser afetados e movidos, ou seja, qualquer email dentro da categoria remediable pode ser movido de um local para outro:
  - Caixa de Entrada 
  - Desejado  
  - Pasta excluída
  - Pasta de exclusão reversível

>[!NOTE]
> Atualmente, somente um usuário final com acesso à caixa de correio pode recuperar itens de uma pasta de exclusão reversível.

**Não acionável**: os emails nos seguintes locais não podem ser afetados ou movidos como parte das ações de email, ou seja, os emails na categoria não-remediable não podem ser movidos na categoria não remediable nem no remediable. Os locais não-remediable são:

  - Quarentena
  - Pasta excluído duro
  - Local/externo
  - Com falha/Descartado
  
As mensagens suspeitas enviadas são categorizadas como remediable ou não como remediable. Na maioria dos casos, as mensagens remediable e não remediable devem ser adicionadas ao total de mensagens enviadas. No entanto, pode haver casos raros em que as mensagens enviadas não podem ser adicionadas à soma de itens remediable e não remediable e podem ser maiores ou menores do que a contagem total de mensagens enviadas. Isso pode acontecer devido a atrasos do sistema, tempos limite ou mensagens expiradas. As mensagens expiram com base no período de retenção do Explorer para sua organização.

A menos que você esteja corrigindo mensagens antigas após o período de retenção do Explorer da organização, se você vir inconsistências em números, é aconselhável tentar corrigir os itens novamente. Para os atrasos do sistema, as atualizações de correção são normalmente atualizadas dentro de algumas horas.

Se o período de retenção de email de sua organização no Explorer for de 30 dias e você estiver corrigindo os emails com 29-30 dias de retorno, as contagens de envio de emails não poderão ser sempre adicionadas, já que os emails podem ter iniciado o período de retenção.

Se a mediação estiver presa em um estado "em andamento" por algum tempo, provavelmente ocorrerá devido a atrasos no sistema. Pode levar algumas horas para ser corrigida. Pode haver uma variação observada nas contagens de envio de email, já que alguns dos emails não fazem parte da consulta durante o início da correção, devido a atrasos no sistema. É uma boa ideia tentar novamente a correção nesses casos.  

Para obter melhores resultados, a correção deve ser feita em lotes menores de cerca de 50k ou menos emails.  

De todos os emails no envio de emails, os emails do remediable são os únicos que serão afetados durante a correção. Os emails não-remediable não podem ser corrigidos pelo sistema de email do Office 365, já que eles não são armazenados nas caixas de correio na nuvem.

Para emails encontrados em quarentena, os administradores podem ir até a quarentena para executar ações nesses emails, se necessário, mas os emails expirarão em quarentena se não forem removidos manualmente. Os emails em quarentena devido ao conteúdo mal-intencionado não são acessíveis por usuários finais, portanto, a equipe de segurança não precisa realizar qualquer ação específica para se livrar da ameaça em quarentena. Se os emails forem locais ou externos, o usuário final poderá ser contatado para lidar com o email suspeito ou usar ferramentas de segurança e servidor de email separadas para remoção. Esses emails podem ser identificados aplicando-se o local de entrega = filtro de entrada/externo no explorador de ameaças. Para email com falha ou cancelado, ou email não acessível pelo usuário final, não deve haver emails para reduzir, pois eles não chegam à caixa de correio.

É assim que um envio é exibido na central de ações. Uma correção pode conter vários envios. Se várias ações forem aprovadas por meio de uma investigação automatizada, cada ação de email ou de cluster de emails aparecerá na mesma correção que um envio diferente.

:::image type="content" source="../../../media/tp-RemediationArticle6.png" alt-text="Painel de saída do cluster de email de zap.":::

Clicar em um item de envio de email mostrará detalhes dessa correção, como a consulta (quando a correção é disparada por meio de investigações automatizadas ou explorador de ameaças por meio da seleção de uma consulta), hora de início e hora de término, da correção. Também exibe uma lista de mensagens que foram enviadas para correção. À medida que as mensagens saem do período de retenção do Explorer, as mensagens desaparecerão dessa lista. Essa lista também mostra mensagens individuais da lista que são remediable.

2. **Guia logs de ação**: essa guia mostra o resultado de mensagens corrigidas, incluindo detalhes como data aprovadas, Aprovador (administrador que aprovou a ação), ação, status e contagens.  

Status é o status geral da correção. O status pode ser:

  - **Iniciado**: quando uma remediação é acionada.
  - **Na fila**: quando a correção é enfileirada para atenuação de emails.
  - **Em andamento**: quando a mitigação está em andamento.
  - **Concluído**: quando a mitigação de todos os emails do remediable é concluída com êxito ou com algumas falhas. 
  - **Falha**: quando nenhuma correção é bem-sucedida.

Como apenas os emails do remediable podem ser afetados, a limpeza de cada email é examinada como bem-sucedida ou com falha. A partir do total de emails do remediable, expõemos as atenuações com êxito e com falha.

  - **Êxito**: quando a ação desejada em emails do remediable é realizada e corresponde à intenção do administrador. Por exemplo: um administrador deseja remover emails de caixas de correio, para que eles executem a ação de exclusão reversível de emails. Se um email do remediable não for encontrado na pasta original após a ação ser realizada, o status será exibido como bem-sucedido.  

  - **Falha**: quando a ação desejada em emails do remediable falha. Por exemplo: um administrador deseja remover emails de caixas de correio, portanto, ele executa a ação de excluir emails de exclusão temporária. Se um email do remediable ainda for encontrado na caixa de correio, o status será exibido como falha.

Ao clicar em qualquer item no log de ações, o exibe detalhes da correção. Para itens bem-sucedidos, se os detalhes dizem, successful ou não foram encontrados na caixa de correio, isso significa que o item já foi removido da caixa de correio. Às vezes, há falhas que ocorrem devido a um erro do sistema durante a correção e, nesses casos, é uma boa ideia tentar novamente a correção.  

A correção é uma poderosa ferramenta para reduzir as ameaças e lidar com os emails suspeitos. Ele ajuda a manter uma organização segura e segura.  

## <a name="more-info"></a>Mais informações

Vejo<https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered?view=o365-worldwide>