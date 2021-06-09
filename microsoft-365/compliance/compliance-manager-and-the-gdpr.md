---
title: Microsoft Compliance Manager e o RGPD
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
description: O Microsoft Compliance Manager é uma ferramenta gratuita de avaliação de risco baseada em fluxo de trabalho no Portal de Confiança do Serviço Microsoft. O Gerenciador de Conformidade permite rastrear, atribuir e verificar atividades de conformidade regulamentar relacionadas aos serviços de nuvem da Microsoft.
ms.openlocfilehash: 69e6551620fb654cb09d46554e6e3c98b6a2fc60
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595798"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a>Microsoft Compliance Manager e o RGPD

O RGPD (Regulamento Geral de Proteção de Dados) aprovado pela União Europeia pode afetar sua estratégia de conformidade e autorizar ações específicas para gerenciar informações de usuários e clientes usadas no Gerenciador de Conformidade.

## <a name="user-privacy-settings"></a>Configurações de privacidade do usuário

Determinados regulamentos exigem que uma organização seja capaz de excluir dados de histórico do usuário. O Gerenciador de Conformidade **fornece Configurações** de Privacidade do Usuário que permitem que os administradores:
  
- [Procurar um usuário](#search-for-a-user)
- [Exportar um relatório do histórico de dados da conta](#export-a-report-of-account-data-history)
- [Excluir o histórico de dados do usuário](#delete-user-data-history)
  
## <a name="search-for-a-user"></a>Procurar um usuário

Para procurar uma conta de usuário:
  
1. Insira o alias de email do usuário (as informações à esquerda do símbolo @) e escolha o nome de domínio na lista de sufixos de domínio à direita. Para organizações com vários domínios registrados, verifique duas vezes o sufixo de nome de domínio para garantir que ele esteja correto.

2. Quando você tiver o nome de usuário inserido corretamente, selecione **Pesquisar**.

3. Para contas de usuário não retornadas, a página exibe **Usuário não encontrado**. Verifique as informações de endereço de email do usuário e faça correções conforme necessário. Para repetir, selecione **Pesquisar**.

4. Para contas de usuário retornadas, o texto do botão muda de **Pesquisa** para **Limpar**. Isso indica que a conta de usuário retornada é o contexto operacional para as funções adicionais e que essas funções se aplicam a essa conta de usuário.

5. Para limpar os resultados da pesquisa e procurar um usuário diferente, selecione **Limpar**.

## <a name="export-a-report-of-account-data-history"></a>Exportar um relatório do histórico de dados da conta

Para cada conta de usuário identificada, você pode gerar um relatório de dependências vinculadas à conta. Essas informações permitem reatribuir itens de ação abertos ou garantir o acesso às evidências carregadas anteriormente.
  
 Para gerar e exportar um relatório:
  
1. Selecione **Exportar** para gerar e baixar um relatório dos Itens de Ação de controle do Gerenciador de Conformidade atualmente atribuídos à conta de usuário retornada e a lista de documentos carregados por esse usuário. Se não houver ações atribuídas ou documentos carregados, uma mensagem de erro informa "Sem dados para esse usuário".

2. O relatório baixa no plano de fundo da janela do navegador ativo — se você não vir um pop-up de download que deseja verificar o histórico de download do navegador.

3. Abra o documento para verificar os dados do relatório.

> [!IMPORTANT]
> Os dados do relatório não são uma lista histórica que mantém e exibe alterações de estado no histórico de atribuição do Item de Ação. O relatório gerado é um instantâneo dos Itens de Ação de controle atribuídos no momento em que o relatório é executado (data e carimbo de data e hora gravados no relatório). Por exemplo, qualquer reatribuição subsequente de Itens de Ação resultará em dados de relatório de instantâneo diferentes se o relatório for gerado novamente para o mesmo usuário.
  
## <a name="delete-user-data-history"></a>Excluir o histórico de dados do usuário

Define todos os itens de ação de controle atribuídos ao usuário retornado como 'não atribuído'. Define o **valor carregado por** todos os documentos carregados pelo usuário retornado como 'usuário removido'.
  
Para excluir o Item de Ação da conta de usuário e o histórico de carregamento de documentos:
  
1. Selecione **Excluir**.

    Uma caixa de diálogo de confirmação é exibida: " Isso remove todas as atribuições de Item de Ação de controle e o histórico de carregamento do documento *para o usuário selecionado. Essa ação é permanente. Tem certeza de que deseja continuar?*"

2. Para continuar, **selecione OK,** caso contrário, **selecione Cancelar**.
