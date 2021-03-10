---
title: Correção de emails mal-intencionados que foram entregues no Office 365
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
ms.openlocfilehash: 0c52b80ffe30da259672e5862d0fa73a8445aa59
ms.sourcegitcommit: 9adb89206daa075af34a73bcb7e8fb86d7c2919a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/10/2021
ms.locfileid: "50604037"
---
# <a name="remediate-malicious-email-delivered-in-office-365"></a>Correção de emails mal-intencionados entregues no Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 2 do Microsoft Defender para Office 365](office-365-atp.md)

Correção significa tomar uma ação prescrita contra uma ameaça. Emails mal-intencionados enviados para sua organização podem ser limpos pelo sistema, por meio da limpeza automática de zero hora (ZAP) ou por equipes de segurança por meio de ações de correção, como mover para a caixa de *entrada,* mover para lixo *eletrônico,* mover para itens excluídos, exclusão automática *ou* *exclusão difícil*. O Microsoft Defender for Office 365 P2/E5 permite que as equipes de segurança soluçam ameaças em funcionalidades de colaboração e email por meio de investigação manual e automatizada.

> [!NOTE]
> Para correção de emails mal-intencionados, as equipes de segurança precisam da *função de* pesquisa e limpeza atribuída a elas. A atribuição de função é feita por meio de permissões no centro de segurança e conformidade.

## <a name="what-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar

Os administradores podem tomar medidas necessárias em emails, mas, para  obter essas ações  \> **aprovadas,** eles devem ter a função de pesquisa e limpeza atribuída a eles por meio de Permissões do Centro de Conformidade & Segurança. Sem a função "pesquisar e limpar" adicionada a um dos grupos de função, eles não poderão executar a ação.

## <a name="manual-and-automated-remediation"></a>Correção manual e automatizada

*A busca* manual ocorre quando as equipes de segurança identificam ameaças manualmente usando os recursos de pesquisa e filtragem no Explorador de Ameaças. A correção de email manual pode ser disparada por meio de qualquer modo de exibição de email (*Malware,* *Phish*, ou Todos os *emails*) depois de identificar um conjunto de emails que precisam ser remediados.

> [!div class="mx-imgBorder"]
> [![Busca manual no Explorador de Ameaças do Office 365 por data.](../../media/tp-RemediationArticle1.png)](../../media/tp-RemediationArticle1.png#lightbox)

As equipes de segurança podem usar o Explorador de Ameaças para selecionar emails de várias maneiras:

- Escolha emails à mão: use filtros em várias exibições. Selecione até 100 emails para correção.

- Seleção de consulta: selecione uma consulta inteira usando o botão **selecionar todos.** A mesma consulta também é mostrada nos detalhes de envio de email da central de ações.

- Seleção de consultas com exclusão: Às vezes, as equipes de operações de segurança podem querer remediar emails selecionando uma consulta inteira e excluindo determinados emails da consulta manualmente. Para fazer isso, um administrador pode usar a caixa de seleção **Selecionar todos** e rolar para baixo para excluir emails manualmente. A consulta pode conter no máximo 1.000 emails. O número máximo de exclusões é 100.

Depois que os emails são selecionados por meio do Explorador de Ameaças, você pode começar a correção por meio de ações diretas ou filando emails para uma ação:

- Aprovação direta: quando ações como mover para a caixa de  *entrada,* mover para lixo eletrônico, mover para itens excluídos, exclusão suave ou exclusão difícil são selecionadas pela equipe de segurança que têm permissões apropriadas e as próximas etapas na correção são seguidas, o processo de correção começa a executar a ação selecionada.  Um flyout temporário mostra correção em andamento.

- Aprovação em duas etapas: uma ação "adicionar à correção" pode ser tomada por administradores que não têm permissões apropriadas ou que precisam esperar para executar a ação. Nesse caso, os emails direcionados são adicionados a um contêiner de correção. A aprovação é necessária antes da execução da correção.

**As ações automatizadas de investigação e** resposta são disparadas por alertas ou por equipes de operações de segurança do Explorador de Ameaças. Isso pode incluir ações de correção recomendadas que devem ser aprovadas por uma equipe de operações de segurança. Essas ações estão incluídas na guia **Ação** na investigação automatizada.

> [!div class="mx-imgBorder"]
> [![Email com malware na página "Em forma de tiro", mostrando a hora da execução do Zap.](../../media/tp-RemediationArticle3.png)](../../media/tp-RemediationArticle3.png#lightbox)

Todas as correções (aprovação direta ou aprovação em duas etapas) criadas no Explorador de Ameaças, bem como as ações aprovadas provenientes de investigações automatizadas são exibidas no Centro de Ações. Acesse-os por meio do painel de navegação esquerdo em **Review** \> **Action Center**.

> [!div class="mx-imgBorder"]
> [![O centro de ações com uma lista de ameaças por data e gravidade.](../../media/tp-RemediationArticle4.png)](../../media/tp-RemediationArticle4.png#lightbox)

O Centro de Ações mostra todas as ações de correção dos últimos 30 dias. As ações realizadas por meio do Explorador de Ameaças são listadas pelo nome que a equipe de operações de segurança forneceu quando a correção foi criada. As ações realizadas por meio de investigações automatizadas têm títulos que começam com o alerta relacionado que disparou a investigação, como "Cluster de email zap... ."

Abra qualquer item de correção para exibir detalhes sobre ele, incluindo seu nome, data de criação, descrição, gravidade da ameaça e status. Ele também mostra as duas guias a seguir.

- **Guia envio de** email: exibe o número de emails enviados pelo Explorador de Ameaças ou investigações automatizadas a serem remediadas. Esses emails podem ser a ação ou não a actionable.

  > [!div class="mx-imgBorder"]
  > [![O centro de ações com ameaças a actionable e não a actionable.](../../media/tp-RemediationArticle5.png)](../../media/tp-RemediationArticle5.png#lightbox)

  - **A ação**: Os emails nos seguintes locais de caixa de correio de nuvem podem ser agidos e movidos:
    - Caixa de Entrada
    - Lixo eletrônico
    - Pasta excluída
    - Pasta excluída de forma suave

      > [!NOTE]
      > Atualmente, apenas um usuário com acesso à caixa de correio pode recuperar itens de uma pasta excluída de forma suave.

  - **Não agido**: Os emails nos seguintes locais não podem ser agidos ou movidos em ações de correção:
    - Quarentena
    - Pasta excluída com dificuldade
    - Local/externo
    - Falha/ressução

  As mensagens suspeitas são categorizadas como corretivas ou não corretivas. Na maioria dos casos, as mensagens corretivas e não corretivas combinam igual ao total de mensagens enviadas. Mas, em casos raros, isso pode não ser verdadeiro. Isso pode acontecer devido a atrasos do sistema, tempo de espera ou mensagens expiradas. As mensagens expiram com base no período de retenção do Explorador de Ameaças para sua organização.

  A menos que você esteja remediando mensagens antigas após o período de retenção do Explorador de Ameaças da sua organização, é recomendável tentar remediar itens se você vir inconsistências de número. Para atrasos do sistema, as atualizações de correção geralmente são atualizadas dentro de algumas horas.

  Se o período de retenção da sua organização para email no Explorador de Ameaças for de 30 dias e você estiver remediando emails de 29 a 30 dias, as contagens de envio de email nem sempre podem ser acrescentados. Os emails já podem ter começado a sair do período de retenção.

  Se as correções estão presas no estado "Em andamento" por um tempo, provavelmente devido a atrasos do sistema. Pode levar algumas horas para ser remediado. Você pode ver variações nas contagens de envio de email, pois alguns dos emails podem não ter sido incluídos na consulta no início da correção devido a atrasos no sistema. É uma boa ideia tentar remediar nesses casos.

  > [!NOTE]
  > Para melhores resultados, a correção deve ser feita em lotes de 50.000 ou menos.

  Somente emails remediados são agidos durante a correção. Emails não remediados não podem ser remediados pelo sistema de email do Office 365, pois eles não são armazenados em caixas de correio de nuvem.

  Os administradores podem realizar ações em emails em quarentena, se necessário, mas esses emails expiram fora de quarentena se não são limpos manualmente. Emails em quarentena por causa de conteúdo mal-intencionado não são acessíveis pelos usuários, portanto, a equipe de segurança não precisa tomar nenhuma ação para se livrar das ameaças na quarentena. Se os emails são locais ou externos, o usuário pode ser contatado para resolver o email suspeito. Ou os administradores podem usar servidores de email/ferramentas de segurança separados para remoção. Esses emails podem ser identificados aplicando-se o local de entrega *= filtro* externo local no Explorador de Ameaças. Para emails com falha ou redução, ou email não acessível pelos usuários, não haverá nenhum email a ser atenuado, já que esses emails não chegam à caixa de correio.

  A imagem a seguir mostra a aparência de um envio no Centro de Ações. Uma correção pode conter vários envios. Se várias ações são aprovadas por meio de uma investigação automatizada, cada ação de cluster de email ou email aparece na mesma correção que um envio diferente.

  > [!div class="mx-imgBorder"]
  > [![Painel de sobrevoo do cluster de email ZAP.](../../media/tp-RemediationArticle6.png)](../../media/tp-RemediationArticle6.png#lightbox)

  Selecione um item de envio de email para mostrar os detalhes dessa correção, como a consulta (quando a correção é disparada por meio de investigações automatizadas ou do Explorador de Ameaças selecionando uma consulta) e os horários de início e término da correção. Ele também exibe uma lista de mensagens que foram enviadas para correção. À medida que as mensagens sairem do período de retenção do Explorador de Ameaças, as mensagens desaparecem dessa lista. A lista também mostra mensagens individuais que são remediadas.

- **Logs de** ação : esta guia mostra as mensagens remediadas, incluindo a data aprovada, o administrador que aprovou a ação, a ação, o status e as contagens.

  Status pode ser:

  - **Iniciado**: a correção é disparada.
  - **Enroscar**: a correção está em fila para mitigação de emails.
  - **Em andamento**: a mitigação está em andamento.
  - **Concluído**: mitigação em todos os emails remediados concluídos com êxito ou com algumas falhas.
  - **Falha**: nenhuma correção foi bem-sucedida.

  Como apenas emails remediais podem ser agidos, a limpeza de cada email é mostrada como bem-sucedida ou com falha. Do total de emails remediados, mitigações bem-sucedidas e com falha são relatadas.

  - **Sucesso**: a ação desejada em emails remediados foi realizada. Por exemplo: um administrador deseja remover emails de caixas de correio, portanto, o administrador assume a ação de excluir emails de forma suave. Se um email remediado não for encontrado na pasta original após a ação ser realizada, o status será mostrar como bem-sucedido.

  - **Falha**: A ação desejada em emails remediados falhou. Por exemplo: um administrador deseja remover emails de caixas de correio, portanto, o administrador assume a ação de excluir emails de forma suave. Se um email corretável ainda for encontrado na caixa de correio após a ação ser tomada, o status será mostrar como falhou.
  
  - **Já no destino**: a ação desejada já foi realizada no email ou no email já existia no local de destino. Por exemplo: um email foi excluído pelo administrador por meio do Explorer no primeiro dia. Em seguida, emails semelhantes aparecem no dia 2, que são excluídos novamente pelo administrador. Ao selecionar esses emails, o administrador acaba escolhendo alguns emails do primeiro dia que já foram excluídos. Agora, esses emails não serão agidos novamente, eles apenas mostrarão como "já estão no destino", já que nenhuma ação foi tomada sobre eles como eles existiam no local de destino.

  Selecione qualquer item no log de ações para exibir detalhes de correção. Se os detalhes dizem "bem-sucedido" ou "não encontrado na caixa de correio", esse item já foi removido da caixa de correio. Às vezes, há um erro sistêmico durante a correção. Nesses casos, é uma boa ideia tentar a correção novamente.

  No caso de correção de lotes grandes, você também pode exportar as mensagens enviadas para correção por meio de Envio de Email e mensagens que foram remediadas por meio de Logs de Ações. O limite de exportação é aumentado para 100 mil registros.

A equipe de segurança pode levar até 50 correções manuais simultâneas; no entanto, não há um limite definido para ações automatizadas de investigação e resposta.

  A correção é uma ferramenta poderosa para mitigar ameaças e resolver emails suspeitos. Ele ajuda a manter uma organização segura.
