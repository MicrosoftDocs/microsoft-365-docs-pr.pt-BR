---
title: Remediar emails mal-intencionados que foram entregues no Office 365
author: msfttracyp
ms.author: tracyp
manager: dansimp
ms.topic: article
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection: ''
search.appverid: MET150
description: Correção de ameaças
appliesto:
- Microsoft 365 Defender
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1b32982298a368dc435dad8b6c09188321d099e2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289228"
---
# <a name="remediate-malicious-email-delivered-in-office-365"></a>Correção de emails mal-intencionados entregues no Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 2 do Microsoft Defender para Office 365](office-365-atp.md)

Correção significa tomar uma ação prescrita contra uma ameaça. Emails mal-intencionados enviados para sua organização podem ser limpos pelo sistema, por meio da ZAP (Limpeza Automática Zero Hora) ou por equipes de segurança por meio de ações de correção, como mover para a caixa de *entrada,* ir para lixo *eletrônico,* mover para itens excluídos, exclusão automática ou *exclusão* permanente.  O Microsoft Defender para Office 365 P2/E5 permite que as equipes de segurança remediam ameaças na funcionalidade de colaboração e email por meio de investigação manual e automatizada.

> [!NOTE]
> Para remediar emails mal-intencionados, as equipes de segurança precisam da *função de* pesquisa e limpeza atribuída a elas. A atribuição de função é feita por meio de permissões no centro de conformidade e segurança.

## <a name="what-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar

Os administradores podem tomar as medidas necessárias em emails, mas  para aprovar essas ações,  eles devem ter a função de pesquisa e limpeza atribuída a eles por meio de permissões do Centro de Conformidade e Segurança \> &. Sem a função "pesquisar e limpar" adicionada a um dos grupos de função, eles não poderão executar a ação.

## <a name="manual-and-automated-remediation"></a>Correção manual e automatizada

*A busca* manual ocorre quando as equipes de segurança identificam ameaças manualmente usando os recursos de pesquisa e filtragem no Explorador de Ameaças. A correção manual de email pode ser disparada por meio de qualquer modo de exibição de email (*Malware,* *Phish*, ou Todos os *emails*) depois de identificar um conjunto de emails que precisam ser remediados.

> [!div class="mx-imgBorder"]
> [![Busca manual no Explorador de Ameaças do Office 365 por data.](../../media/tp-RemediationArticle1.png)](../../media/tp-RemediationArticle1.png#lightbox)

As equipes de segurança podem usar o Explorador de Ameaças para selecionar emails de várias maneiras:

- Escolha emails manualmente: use filtros em vários visualizações. Selecione até 100 emails para remediar.

- Seleção de consulta: selecione uma consulta inteira usando o botão selecionar **todos na** parte superior. A mesma consulta também é mostrada nos detalhes de envio de email da central de ações.

- Seleção de consultas com exclusão: às vezes, as equipes de operações de segurança podem querer remediar emails selecionando uma consulta inteira e excluindo determinados emails da consulta manualmente. Para fazer isso, um administrador pode usar a caixa **de** seleção Selecionar tudo e rolar para baixo para excluir emails manualmente. A consulta pode conter no máximo 1.000 emails. O número máximo de exclusões é 100.

Depois que os emails são selecionados por meio do Explorador de Ameaças, você pode iniciar a correção tomando uma ação direta ou enmorando emails para uma ação:

- Aprovação direta: quando ações como mover para a caixa de  *entrada,*  mover para lixo *eletrônico,* mover para itens excluídos *,* exclusão suave ou exclusão permanente são selecionadas pela equipe de segurança que tem as permissões apropriadas e as próximas etapas na correção são seguidas, o processo de correção começa a executar a ação selecionada. Um flyout temporário mostra correção em andamento.

- Aprovação em duas etapas: uma ação "adicionar à correção" pode ser executada por administradores que não têm permissões apropriadas ou que precisam esperar para executar a ação. Nesse caso, os emails direcionados são adicionados a um contêiner de correção. A aprovação é necessária antes que a correção seja executada.

**As ações automatizadas de investigação e** resposta são disparadas por alertas ou por equipes de operações de segurança do Explorador de Ameaças. Isso pode incluir ações de correção recomendadas que devem ser aprovadas por uma equipe de operações de segurança. Essas ações estão incluídas na **guia Ação** na investigação automatizada.

> [!div class="mx-imgBorder"]
> [![Email com malware na página "Com malware" mostrando o tempo de execução da Zap.](../../media/tp-RemediationArticle3.png)](../../media/tp-RemediationArticle3.png#lightbox)

Todas as correções (aprovação direta ou aprovação em duas etapas) que foram criadas no Explorador de Ameaças, bem como ações aprovadas provenientes de investigações automatizadas são exibidas na Central de Ações. Acesse-os por meio do painel de navegação esquerdo em **Revisar** \> **Central de Ações.**

> [!div class="mx-imgBorder"]
> [![A central de ações com uma lista de ameaças por data e gravidade.](../../media/tp-RemediationArticle4.png)](../../media/tp-RemediationArticle4.png#lightbox)

A Central de Ações mostra todas as ações de correção dos últimos 30 dias. As ações realizadas por meio do Explorador de Ameaças são listadas pelo nome fornecido pela equipe de operações de segurança quando a correção foi criada. As ações realizadas por meio de investigações automatizadas têm títulos que começam com o alerta relacionado que disparou a investigação, como "Cluster de email da Zap... ."

Abra qualquer item de correção para exibir detalhes sobre ele, incluindo seu nome, data de criação, descrição, gravidade da ameaça e status. Ele também mostra as duas guias a seguir.

- **Guia envio** de email: exibe o número de emails enviados por meio do Explorador de Ameaças ou investigações automatizadas a serem remediadas. Esses emails podem ser a ação ou não a ação.

  > [!div class="mx-imgBorder"]
  > [![A central de ações com ameaças a actionable e não a actionable.](../../media/tp-RemediationArticle5.png)](../../media/tp-RemediationArticle5.png#lightbox)

  - **A actionable**: emails nos seguintes locais de caixa de correio na nuvem podem ser agidos e movidos:
    - Caixa de Entrada
    - Lixo eletrônico
    - Pasta excluída
    - Pasta excluída de forma suave

      > [!NOTE]
      > Atualmente, apenas um usuário com acesso à caixa de correio pode recuperar itens de uma pasta excluída de forma suave.

  - **Não a actionable:** emails nos seguintes locais não podem ser agidos ou movidos em ações de correção:
    - Quarentena
    - Pasta excluída de forma permanente
    - Local/externo
    - Falhou/suou

  Mensagens suspeitas são categorizadas como corretivas ou não corretivas. Na maioria dos casos, as mensagens corretivas e não corretivas combinam o total de mensagens enviadas. Mas, em casos raros, isso pode não ser verdadeiro. Isso pode acontecer devido a atrasos do sistema, tempos esgotados ou mensagens expiradas. As mensagens expiram com base no período de retenção do Explorador de Ameaças da sua organização.

  A menos que você esteja remediando mensagens antigas após o período de retenção do Explorador de Ameaças da sua organização, é aconselhável tentar remediar itens se você vir inconsistências de número. Para atrasos do sistema, as atualizações de correção são normalmente atualizadas dentro de algumas horas.

  Se o período de retenção de email da sua organização no Explorador de Ameaças for de 30 dias e você estiver remediando emails de 29 a 30 dias, as contagens de envio de email podem nem sempre aumentar. Os emails já podem ter começado a sair do período de retenção.

  Se as correções estão travadas no estado "Em andamento" por um tempo, provavelmente devido a atrasos do sistema. Pode levar algumas horas para ser remediado. Você pode ver variações nas contagens de envio de email, pois alguns dos emails podem não ter sido incluídos na consulta no início da correção devido a atrasos do sistema. É uma boa ideia tentar remediar nesses casos.

  > [!NOTE]
  > Para melhores resultados, a correção deve ser feita em lotes de 50.000 ou menos.

  Somente emails remediados são remediados durante a correção. Emails não remediados não podem ser remediados pelo sistema de email do Office 365, pois eles não são armazenados em caixas de correio na nuvem.

  Os administradores podem realizar ações em emails em quarentena, se necessário, mas esses emails expiram da quarentena se não são limpos manualmente. Os emails colocados em quarentena por causa de conteúdo mal-intencionado não são acessíveis aos usuários, portanto, a equipe de segurança não precisa tomar medidas para eliminar ameaças em quarentena. Se os emails são locais ou externos, o usuário pode ser contatado para tratar do email suspeito. Ou os administradores podem usar servidor de email/ferramentas de segurança separadas para remoção. Esses emails podem ser identificados aplicando o local *de entrega = filtro* externo local no Explorador de Ameaças. Para emails com falha ou descartados, ou emails não acessíveis por usuários, não haverá nenhum email para atenuar, já que esses emails não chegam à caixa de correio.

  A imagem a seguir mostra a aparência de um envio na Central de Ações. Uma correção pode conter vários envios. Se várias ações são aprovadas por meio de uma investigação automatizada, cada ação de email ou cluster de email aparece na mesma correção de um envio diferente.

  > [!div class="mx-imgBorder"]
  > [![Painel do flyout do cluster de email ZAP.](../../media/tp-RemediationArticle6.png)](../../media/tp-RemediationArticle6.png#lightbox)

  Selecione um item de envio de email para mostrar os detalhes dessa correção, como a consulta (quando a correção é disparada por meio de investigações automatizadas ou do Explorador de Ameaças por meio da seleção de uma consulta) e os horários de início e término da correção. Ele também exibe uma lista de mensagens que foram enviadas para correção. À medida que as mensagens sairem do período de retenção do Explorador de Ameaças, as mensagens desaparecerão dessa lista. A lista também mostra mensagens individuais que são remediadas.

- **Logs de** ações: esta guia mostra as mensagens remediadas, incluindo a data aprovada, o administrador que aprovou a ação, a ação, o status e as contagens.

  O status pode ser:

  - **Iniciado:** a correção é disparada.
  - **Na fila:** a correção está na fila para mitigação de emails.
  - **Em andamento:** a mitigação está em andamento.
  - **Concluído:** mitigação em todos os emails remediados concluídos com êxito ou com algumas falhas.
  - **Falha:** nenhuma correção foi bem-sucedida.

  Como apenas emails remediados podem ser remediados, a limpeza de cada email é mostrada como bem-sucedida ou falhou. Do total de emails remediados, mitigações bem-sucedidas e com falha são relatadas.

  - **Sucesso**: a ação desejada em emails remediados foi realizada. Por exemplo: um administrador deseja remover emails de caixas de correio, portanto, o administrador toma a ação de excluir emails de forma simples. Se um email remediado não for encontrado na pasta original após a ação ser realizada, o status será como bem-sucedido.

  - **Falha:** falha na ação desejada em emails remediados. Por exemplo: um administrador deseja remover emails de caixas de correio, portanto, o administrador toma a ação de excluir emails de forma simples. Se um email remediado ainda for encontrado na caixa de correio após a ação ser realizada, o status será como falha.

  Selecione qualquer item no log de ações para exibir detalhes de correção. Se os detalhes dizem "bem-sucedido" ou "não encontrado na caixa de correio", esse item já foi removido da caixa de correio. Às vezes, há um erro de erro de erro durante a correção. Nesses casos, é uma boa ideia tentar a correção.

  No caso de correção de lotes grandes, você também pode exportar as mensagens enviadas para correção por meio de Envio de Email e mensagens que foram remediadas por meio de Logs de Ações. O limite de exportação é aumentado para 100 mil registros.

  A correção é uma ferramenta poderosa para reduzir ameaças e resolver emails suspeitos. Ele ajuda a manter uma organização segura.
