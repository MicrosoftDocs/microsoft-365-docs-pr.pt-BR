---
title: Gerente de conformidade da Microsoft e o RGPD
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: O Gerenciador de conformidade da Microsoft é uma ferramenta de avaliação de riscos gratuita baseada em fluxo de trabalho no portal de confiança do serviço Microsoft. O Gerenciador de conformidade permite que você rastreie, atribua e verifique as atividades de conformidade normativa relacionadas aos serviços em nuvem da Microsoft.
ms.openlocfilehash: 69e6551620fb654cb09d46554e6e3c98b6a2fc60
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595798"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a>Gerente de conformidade da Microsoft e o RGPD

A regulamentação geral de proteção de dados (RGPD), aprovada pela União Européia, pode impactar a estratégia de conformidade e exigir ações específicas para gerenciar as informações do usuário e do cliente usadas no Gerenciador de conformidade.

## <a name="user-privacy-settings"></a>Configurações de privacidade do usuário

Determinadas regulamentações exigem que uma organização seja capaz de excluir dados de histórico do usuário. O Gerenciador de conformidade fornece funções de **configurações de privacidade do usuário** que permitem aos administradores:
  
- [Procurar um usuário](#search-for-a-user)
- [Exportar um relatório do histórico de dados da conta](#export-a-report-of-account-data-history)
- [Excluir o histórico de dados do usuário](#delete-user-data-history)
  
## <a name="search-for-a-user"></a>Procurar um usuário

Para procurar uma conta de usuário:
  
1. Insira o alias de email do usuário (as informações à esquerda do símbolo @) e escolha o nome do domínio na lista de sufixos de domínio à direita. Para organizações com vários domínios registrados, verifique novamente o sufixo de nome de domínio para garantir que ele está correto.

2. Quando o nome de usuário for inserido corretamente, selecione **Pesquisar**.

3. Para contas de usuário não retornadas, a página exibe o **usuário não encontrado**. Verifique as informações do endereço de email do usuário e faça as correções necessárias. Para repetir, selecione **Pesquisar**.

4. Para contas de usuário retornadas, o texto do botão muda de **pesquisa** para **limpo**. Isso indica que a conta de usuário retornada é o contexto operacional para as funções adicionais e que essas funções se aplicam a essa conta de usuário.

5. Para limpar os resultados da pesquisa e pesquisar um usuário diferente, selecione **limpar**.

## <a name="export-a-report-of-account-data-history"></a>Exportar um relatório do histórico de dados da conta

Para cada conta de usuário identificada, você pode gerar um relatório de dependências vinculadas à conta. Essas informações permitem que você reatribua itens de ação abertas ou assegure o acesso a evidências previamente carregadas.
  
 Para gerar e exportar um relatório:
  
1. Selecione **Exportar** para gerar e baixar um relatório dos itens de ação de controle do Gerenciador de conformidade atribuídos atualmente à conta de usuário retornada e a lista de documentos carregados por esse usuário. Se não houver ações atribuídas ou documentos carregados, uma mensagem de erro diz "não há dados para este usuário".

2. O relatório é baixado no plano de fundo da janela ativa do navegador — se você não vir um pop-up de download que deseja verificar o histórico de download do seu navegador.

3. Abra o documento para verificar os dados do relatório.

> [!IMPORTANT]
> Os dados do relatório não são uma lista histórica que mantém e exibe as alterações de estado no histórico de atribuição de itens de ação. O relatório gerado é um instantâneo dos itens de ação de controle atribuídos no momento em que o relatório é executado (carimbo de data e hora gravados no relatório). Por exemplo, qualquer reatribuição subsequente de itens de ação resultará em diferentes dados de relatório de instantâneo se o relatório for gerado novamente para o mesmo usuário.
  
## <a name="delete-user-data-history"></a>Excluir o histórico de dados do usuário

Define todos os itens de ação de controle atribuídos ao usuário retornado como ' não atribuído '. Define o valor **carregado por** para qualquer documento carregado pelo usuário retornado para "removido pelo usuário".
  
Para excluir o item de ação da conta de usuário e o histórico de upload de documentos:
  
1. Selecione **excluir**.

    Uma caixa de diálogo de confirmação é exibida: "*isso remove todas as atribuições de item de ação de controle e o histórico de carregamento do documento para o usuário selecionado. Esta ação é permanente. Tem certeza de que deseja continuar?*"

2. Para continuar, selecione **OK**; caso contrário, selecione **Cancelar**.
