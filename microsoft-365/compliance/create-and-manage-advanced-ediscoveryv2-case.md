---
title: Criar e gerenciar casos de Descoberta Avançada no Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-ediscovery
- m365initiative-compliance
- m365initiative-scenario
search.appverid:
- MOE150
- MET150
description: Este artigo descreve como criar e gerenciar casos de Descoberta Avançada. A primeira etapa é criar uma ocorrência e começar a usar recursos e funcionalidades de Descoberta Avançada.
ms.openlocfilehash: 80cfe31a86060cb3603a101b314273cc67750bd8
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727538"
---
# <a name="create-and-manage-an-advanced-ediscovery-case"></a>Criar e gerenciar um caso de Descoberta Avançada

Depois de configurar a Descoberta Secreta Avançada e atribuir permissões aos gerentes de [Descoberta eDiscovery](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions) em sua organização que gerenciarão casos, a próxima etapa é criar e gerenciar um caso.

Este artigo também fornece uma visão geral de alto nível do uso de casos para gerenciar o fluxo de trabalho de Descoberta Eletrônico Avançada para uma investigação legal.

## <a name="create-a-case"></a>Criar um caso

Conclua as etapas a seguir para criar uma ocorrência e adicionar membros. O usuário que cria a ocorrência é adicionado automaticamente como membro.

1. Acesse e entre usando as credenciais da conta de usuário que foram atribuídas permissões [https://compliance.microsoft.com](https://compliance.microsoft.com) de Descoberta e. Membros do grupo de função Gerenciamento da Organização também podem criar casos de Descoberta Avançada.

2. No painel de navegação esquerdo do centro de conformidade do Microsoft 365, clique em **Mostrar** tudo e clique em **Descoberta > Avançado**.

3. Na página **Descoberta Avançada da Descoberta Online,** clique na guia **Casos** e clique em Criar **um caso**.

4. Na página **Sobrevoo** de caso de Descoberta Nova Descoberta, dê ao caso um nome (necessário) e digite um número de caso opcional e uma descrição. O nome do caso deve ser exclusivo em sua organização.

5. Clique **em Salvar** para criar o caso.

   O novo caso é criado e a guia **Configurações** no novo caso é exibida.

6. No & **de** permissões do Access na  guia Configurações, clique em **Selecionar** e clique em **Atualizar.**

7. Clique em **Atualizar**.

8. Na página **Gerenciar o** sub-subsistência desta ocorrência, em **Gerenciar membros,** clique em **Adicionar** para adicionar membros ao caso.

9. Na lista de pessoas, marque a caixa de seleção ao lado dos nomes das pessoas que você deseja adicionar ao caso. Como explicado anteriormente, certifique-se de que as pessoas que você adicionar ao caso tenham sido atribuídas às permissões de Descoberta eDiscoveria apropriadas.

10. Depois de selecionar as pessoas a adicionar como membros da ocorrência, clique em **Adicionar**.

11. Na página **Gerenciar este caso,** clique em **Salvar** para salvar a nova lista de membros da ocorrência.

12. Clique na **guia Página** Inicial para ir para a home page do caso.

## <a name="manage-the-workflow"></a>Gerenciar o fluxo de trabalho

Para começar a usar a Descoberta Avançada, aqui está um fluxo de trabalho básico que se alinha às práticas comuns [de Descoberta Eletrônico.](advanced-ediscovery-edrm.md) Em cada uma dessas etapas, também destacaremos algumas funcionalidades de Descoberta Avançada Avançada que você pode explorar.

![Fluxo de trabalho avançado de Descoberta Eletrônico](../media/AeDWorkflow.png)

1. **[Adicione os custodiantes](add-custodians-to-case.md) e fontes de dados não [custodiais](non-custodial-data-sources.md) ao caso**. A primeira etapa após a criação de um caso é adicionar custodiantes. Um *custodiante* é uma pessoa que tem controle administrativo de um documento ou arquivo eletrônico que pode ser relevante para o caso. Além disso, você pode adicionar fontes de dados que não estão associadas a um usuário específico, mas que podem ser relevantes para o caso.

   Aqui estão algumas coisas que ocorrem (ou que você pode fazer) quando você adiciona os custodiantes a um caso:

   - Os dados na caixa de correio do Exchange do custodiante, na conta do OneDrive e em qualquer grupo do Microsoft Teams ou do Yammer do qual o custodiante é membro podem ser "marcados" como dados de custodia no caso.
  
   - Os dados custodiados são reindexados (por um processo chamado *indexação avançada*). Isso ajuda a otimizar a pesquisa na próxima etapa.
  
   - Você pode colocar uma espera nos dados de custodiante. Isso preserva dados que podem ser relevantes para o caso durante a investigação.
  
   - Você pode associar outras fontes de dados a um custodiante (por exemplo, você pode associar um site do SharePoint ou o Grupo do Microsoft 365 a um custodiante) para que esses dados possam ser reindexados, colocados em espera e pesquisados, assim como os dados na caixa de correio do custodiante ou na conta do OneDrive.

   - Você pode usar o fluxo [de trabalho](managing-custodian-communications.md) de comunicações na Descoberta Eletrônica Avançada para enviar uma notificação de responsabilidade legal aos custodiantes.

2. **[Pesquisar fontes de dados para dados relevantes para o caso](collecting-data-for-ediscovery.md)**. Depois de adicionar os custodiantes e fontes de dados não custodiais a um caso, use a ferramenta de pesquisa integrado para pesquisar essas fontes de dados em busca de dados que possam ser relevantes para o caso. Você usa palavras-chave, propriedades [](building-search-queries.md) e condições para criar consultas de pesquisa que retornam resultados de pesquisa com os dados que provavelmente são relevantes para o caso. Você também pode:

   - Exibir [estatísticas de pesquisa](search-statistics-in-advanced-ediscovery.md) que podem ajudá-lo a refinar uma consulta de pesquisa para restringir os resultados.

   - Visualize os resultados da pesquisa para verificar rapidamente se os dados relevantes estão sendo encontrados.

   - Revise uma consulta e reprise a pesquisa.

3. **[Adicionar dados a um conjunto de revisão](add-data-to-review-set.md)**. Depois de configurar e verificar se uma pesquisa retorna os dados desejados, a próxima etapa é adicionar os resultados da pesquisa a um conjunto de revisão. Quando você adiciona dados a um conjunto de revisão, os itens são copiados de seu local original para um local de Armazenamento seguro do Azure. Os dados são reindexados novamente para otimisá-los para pesquisas completas e rápidas ao analisar e analisar itens no conjunto de revisão. Além disso, você também pode adicionar dados que não são [do Office 365 a um conjunto de revisão.](load-non-office-365-data-into-a-review-set.md)

   Também há um tipo especial de conjunto de revisão ao qual você pode adicionar dados, chamado de conjunto de revisão *de conversa.* Esses tipos de conjuntos de análises fornecem recursos de reconstrução de conversa para reconstruir, revisar e exportar conversas encadeadas como aquelas no Microsoft Teams. Para obter mais informações, [consulte Review conversations in Advanced eDiscovery](conversation-review-sets.md).

4. **Analisar e analisar dados em um conjunto de revisão.** Agora que os dados estão em um conjunto de revisão, você pode usar uma ampla variedade de ferramentas e recursos para exibir e analisar os dados de caso com o objetivo de reduzir o conjunto de dados para o que é mais relevante para o caso que você está investigando. Aqui está uma lista de algumas ferramentas e recursos que você pode usar durante esse processo.

   - [Exibir documentos](view-documents-in-review-set.md). Isso inclui a exibição dos metadados de cada documento em um conjunto de revisão e a exibição do documento em sua versão nativa ou versão de texto.

   - [Criar consultas e filtros](review-set-search.md). Você cria consultas de pesquisa usando vários critérios de pesquisa (incluindo a capacidade de pesquisar todas as propriedades de [metadados](document-metadata-fields-in-advanced-ediscovery.md)de arquivo ) para refinar ainda mais e excluir os dados de caso para o que é mais relevante para o caso. Você também pode usar filtros de conjunto de revisão para aplicar rapidamente outras condições aos resultados de uma consulta de pesquisa para refinar ainda mais esses resultados. 

   - [Criar e usar marcas](tagging-documents.md). Você pode aplicar marcas a documentos em um conjunto de revisão para identificar quais são responsivos (ou não respondendo ao caso) e, em seguida, usar essas marcas ao criar consultas de pesquisa para incluir ou excluir os documentos marcados. Você também pode marcar para determinar quais documentos serão exportados.

   - [Anotar e redactar documentos](view-documents-in-review-set.md#annotate-view). Você pode usar a ferramenta de anotação em uma revisão para anotar documentos e rediscar o conteúdo em documentos como produto de trabalho. Geramos uma versão em PDF de um documento anotado ou editado durante a revisão para reduzir o risco de exportar a versão nativa não editada do documento.

   - [Analisar dados de caso](analyzing-data-in-review-set.md). A funcionalidade de análise na Descoberta Avançada é poderosa. Depois de executar análises nos dados no conjunto de revisão, realizamos análises como detecção quase duplicada, threading de email e temas que podem ajudar a reduzir o volume de documentos que você precisa revisar. Também geramos relatórios do Analytics que resumem o resultado da execução da análise. Como explicado anteriormente, a execução da análise também executa o modelo de detecção de privilégio [advogado-cliente.](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model)

5. **Exportar e baixar dados de caso.** Uma etapa final após a coleta, revisão e análise de dados de caso é exportá-los para fora da Descoberta Externa avançada para revisão externa ou para revisão por pessoas fora da equipe de investigação. Exportar dados é um processo de duas etapas. A primeira etapa é [exportar](export-documents-from-review-set.md) dados do conjunto de revisão e copiá-lo para um local de Armazenamento do Azure diferente (um fornecido pela Microsoft ou um gerenciado pela sua organização). Em seguida, use o Explorador de Armazenamento do Azure [para baixar](download-export-jobs.md) os dados em um computador local. Além dos arquivos de dados exportados, o contém do pacote de exportação também contém um relatório de exportação, um relatório de resumo e um relatório de erro.
