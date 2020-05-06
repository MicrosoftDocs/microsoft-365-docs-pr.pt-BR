---
title: Notas de versão para descoberta eletrônica avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Este artigo contém as notas de versão da descoberta eletrônica avançada, incluindo problemas conhecidos, problemas corrigidos e novos recursos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 45a4647856fef0186840ec5465bb9250e5d78de4
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034615"
---
# <a name="release-notes-for-advanced-ediscovery"></a>Notas de versão para descoberta eletrônica avançada

O programa de visualização pública para descoberta eletrônica avançada é a maneira de obter acesso antecipado à funcionalidade e às atualizações futuras. Para obter acesso antecipado aos recursos mais recentes, basta criar e usar uma caixa de descoberta eletrônica avançada no centro de conformidade de & de segurança. Confira [criar um novo caso](create-new-ediscovery-case.md).

## <a name="known-issues"></a>Problemas conhecidos

**Microsoft Forms**

- Os dados correspondentes a um formulário criado antes de 31 de janeiro de 2019 não poderão ser pesquisados ao usar a ferramenta de pesquisa na descoberta eletrônica avançada para pesquisar caixas de correio de responsáveis. Formulários criados após essa data estarão disponíveis para pesquisa.

- Um formulário criado por um usuário ainda pode receber respostas, mesmo depois que o usuário que criou o formulário é excluído. No entanto, os dados correspondentes para essas respostas (que ocorreram depois da exclusão da caixa de correio) não poderão ser pesquisados ao usar a ferramenta de pesquisa na descoberta eletrônica avançada para pesquisar caixas de correio.
 
**Microsoft Sway**

- Se um usuário editar um Sway imediatamente antes da exclusão da conta de usuário para o proprietário desse Sway, essas alterações poderão não ser pesquisadas ao usar a ferramenta de pesquisa na descoberta eletrônica avançada para pesquisar caixas de correio de responsáveis. O Sway bloqueia alterações em um Sway assim que recebe um sinal de que a conta foi excluída. No entanto, há uma pequena chance de que um Sway possa ser editado antes que esse sinal seja recebido.

## <a name="issues-fixed-in-this-release"></a>Problemas corrigidos nesta versão

- DCR: manipulação de exceção para itens não indexados e itens órfãos
- DCR: notificações de bloqueio
- DCR: responsáveis pela descoberta eletrônica

## <a name="whats-new"></a>Novidades

- **Navegação reprojetada no centro de conformidade e segurança &** – a descoberta eletrônica avançada tem uma nova aparência. Use a descoberta eletrônica avançada para gerenciar mais de seu fluxo de trabalho de caso.

- **Gerenciamento de casos** – há suporte adicional para novos tipos de caso. Você também pode selecionar e salvar seus casos recentes e favoritos. Controlar e monitorar a atividade em e entre casos usando novos painéis.

- **Gerenciamento de responsáveis** – adicione e remova usuários como responsáveis por dados em um caso.

- **Integração com o Exchange, o onedrive e o Teams** – adicione automaticamente a caixa de correio de um usuário, a conta do onedrive for Business e os sites do Microsoft Teams a uma ocorrência. 

- **Comunicações de responsáveis** – envie e gerencie notificações de retenção legal em nome da sua organização.

- **Portal de responsáveis** – novo portal para que os responsáveis acessem seus avisos de isenção ativos.

- **Indexação profunda** – Rastreie novamente os itens parcialmente indexados sob demanda.

- **Correção de erro** : corrigir ou baixar erros de processamento; Isso inclui suporte de correção para tipos de arquivo grandes, arquivos protegidos por senha e muito mais. 

- **Melhorias na pesquisa** – crie uma pesquisa identificando os responsáveis e/ou locais.

- **Conjuntos de revisão** – gerencie, rastreie e faça auditoria de conjuntos estáticos de documentos.

- **Revisão** – use um modo de exibição nativo, de texto e quase nativo para revisar os documentos adicionados ao conjunto de análise.

- **Redigir, marcar e anotar** – redigir texto, aplicar marcas e fazer anotações à medida que você revisar documentos.
  
- **Análise com capacidade para análise**– Aproveite a análise de descoberta eletrônica avançada para localizar, Pesquisar e buscar resultados em um conjunto de revisão.

- **Jobs** – rastreie o status de processos de execução longa.

- **Novas atividades de auditoria** – rastrear e exibir novas atividades de auditoria para descoberta eletrônica avançada.
