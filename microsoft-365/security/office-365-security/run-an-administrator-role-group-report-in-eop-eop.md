---
title: 'Executar um relatório de grupo de função de administrador no EOP '
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
description: Os administradores podem aprender a executar um relatório de grupo de funções de administrador no Exchange Online Protection (EOP). Este relatório registra quando um administrador adiciona ou remove membros dos grupos de função de administrador, o Microsoft proteção do Exchange Online (EOP) registra cada ocorrência.
ms.openlocfilehash: 59557f6fab2281cd36569b40afcf3e0225bd9347
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441398"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a>Executar um relatório de grupo de função de administrador no EOP

 Quando um administrador adiciona ou remove membros dos grupos de funções de administrador, o Exchange Online Protection (EOP) registra cada ocorrência. Quando você executa um relatório de grupo de funções de administrador no centro de administração do Exchange (Eat), as entradas são exibidas como resultados de pesquisa e incluem os grupos de função afetados, quem alterou a associação do grupo de função e quando e quais foram feitas as atualizações de associação. Use esse relatório para monitorar as alterações nas permissões administrativas atribuídas aos usuários da sua organização.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Tempo estimado para conclusão: 2 minutos

- Para abrir o centro de administração do Exchange, confira [Exchange Admin Center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).

- Para executar este procedimento ou estes procedimentos, você precisa receber permissões. Para ver de que permissões você precisa, consulte o Seção "Relatórios" do tópico [Permissões de recurso no EOP](feature-permissions-in-eop.md).

- Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Está com problemas? Peça ajuda no fórum do [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>Usar o EAC para executar o relatório de grupo de funções de administrador

Execute o relatório do grupo de funções de administrador para localizar as alterações nos grupos de função de gerenciamento em sua organização dentro de um determinado período.

1. No EAC, navegue até **Gerenciamento de conformidade** \> **Auditoria** e escolha **Executar o relatório do grupo de funções do administrador**.

2. Escolha a **Data de início** e a **Data de término**. Por padrão, o relatório procura alterações feitas nos grupos de funções do administrador nas duas últimas semanas.

3. Para exibir as alterações de um grupo de funções específico, clique em **Selecionar grupos de função**. Selecione o grupo de função (ou grupos) na caixa de diálogo subsequente e clique em **OK**. Você também pode deixar o campo em branco para encontrar todos os grupos de função alterados.

4. Clique em **Pesquisar**.

Se quaisquer alterações forem encontradas usando os critérios especificados, elas aparecerão no painel de resultados. Clique em um grupo de função nos resultados da pesquisa para ver as alterações no painel de detalhes.

## <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Se você executou com sucesso um relatório de grupo de funções do administrador, os grupos de funções que foram alterados dentro do intervalo de datas serão exibidos no painel de resultados da pesquisa. Se não houver resultados, nenhuma alteração nos grupos de funções será executada dentro do intervalo de datas especificado. Se julgar que deveria haver resultados, altere o intervalo de dados e execute novamente o relatório.

## <a name="monitor-changes-to-role-group-membership"></a>Monitorar alterações na associação de grupo de funções

Quando os membros são adicionados ou removidos de um grupo de funções, os resultados da pesquisa exibidos no painel de detalhes indicam que a associação de grupo de funções foi atualizada e lista os membros atuais. Os resultados não informam explicitamente qual usuário foi adicionado ou removido.

Para determinar se um usuário foi adicionado ou removido, você terá que comparar duas entradas separadas no relatório. Por exemplo, vamos observar as entradas de log a seguir do grupo de funções de **HelpDesk**:

> 1/27/2018 4:43 PM <br> Administrador <br> Membros atualizados: Administrator;annb,florencef;pilarp <br> 2/06/2018 10:09 AM <br> Administrador <br> Membros atualizados: Administrator;annb;florencef;pilarp;tonip <br> 2/19/2018 2:12 PM <br> Administrador <br> Membros atualizados: Administrator;annb;florencef;tonip

Nesse exemplo, a conta de usuário Administrador fez as seguintes alterações:

- No 2/06/2018, eles adicionaram o usuário tonip.

- No 2/19/2018, eles removeram o usuário pilarp.
