---
title: Criar e gerenciar ocorrências de Descobertas Avançadas no Microsoft 365
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
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Este artigo descreve como criar e gerenciar casos de Descobertas Avançadas. A primeira etapa é criar uma ocorrência e começar a usar recursos e funcionalidades da Descoberta Avançada.
ms.openlocfilehash: c95994b3706880b40ff6306c02a4bdb5dba7748b
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841588"
---
# <a name="create-and-manage-an-advanced-ediscovery-case"></a>Criar e gerenciar um caso de Descoberta Descoberta Avançada

Depois de configurar a Descoberta Avançada e atribuir permissões aos gerentes de Descoberta [eDiscovery](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions) em sua organização que gerenciarão os casos, a próxima etapa é criar e gerenciar uma ocorrência.

Este artigo também fornece uma visão geral de alto nível do uso de casos para gerenciar o fluxo de trabalho de Descoberta Eletrônico Avançada para uma investigação legal.

## <a name="create-a-case"></a>Criar uma ocorrência

Conclua as etapas a seguir para criar uma ocorrência e adicionar membros. O usuário que cria a ocorrência é adicionado automaticamente como membro.

1. Vá para e entre usando as credenciais da conta de usuário que recebeu [https://compliance.microsoft.com](https://compliance.microsoft.com) permissões de Descoberta Descoberta. Os membros do grupo de função Gerenciamento da Organização também podem criar ocorrências de DescobertaScoberta Avançada.

2. No painel de navegação esquerdo do centro de conformidade do Microsoft 365, clique em Mostrar tudo e clique em Descoberta > **Avançado.**

3. Na página **Descobertas Avançadas,** clique na guia **Casos** e clique em **Criar uma ocorrência.**

4. Na página **desdobre** da ocorrência de Nova Descoberta e, em seguida, digite um número de ocorrência e uma descrição opcionais. O nome da ocorrência deve ser exclusivo em sua organização.

5. Clique **em Salvar** para criar a ocorrência.

   A nova ocorrência é criada e **a guia Configurações** no novo caso é exibida.

6. No & **permissões do** Access na guia  Configurações, clique em **Selecionar** e em **Atualizar.**

7. Clique em **Atualizar**.

8. Na página **Gerenciar esse caso,** em **Gerenciar membros,** clique em **Adicionar** para adicionar membros à ocorrência.

9. Na lista de pessoas, marque a caixa de seleção ao lado dos nomes das pessoas que você deseja adicionar à ocorrência. Conforme explicado anteriormente, certifique-se de que as pessoas que você adicionar ao caso foram atribuídas com as permissões de Descoberta Descoberta apropriadas.

10. Depois de selecionar as pessoas para adicionar como membros da ocorrência, clique em **Adicionar**.

11. Na página **Gerenciar esse caso,** clique em **Salvar** para salvar a nova lista de membros da ocorrência.

12. Clique na **guia Página** Inicial para ir para a home page da ocorrência.

## <a name="manage-the-workflow"></a>Gerenciar o fluxo de trabalho

Para começar a usar a Descoberta Avançada, aqui está um fluxo de trabalho básico que se alinha às práticas comuns [de Descoberta Eletrônico.](advanced-ediscovery-edrm.md) Em cada uma dessas etapas, também destacaremos algumas funcionalidades avançadas de Descoberta Avançada que você pode explorar.

![Fluxo de trabalho de Descoberta Eletrônico Avançada](../media/AeDWorkflow.png)

1. **[Adicione custodiantes](add-custodians-to-case.md) [e fontes de dados não custodial](non-custodial-data-sources.md) ao caso.** A primeira etapa após criar uma ocorrência é adicionar custodiantes. Um *custodiante* é uma pessoa que tem controle administrativo de um documento ou arquivo eletrônico que pode ser relevante para o caso. Além disso, você pode adicionar fontes de dados que não estão associadas a um usuário específico, mas que podem ser relevantes para o caso.

   Aqui estão algumas coisas que acontecem (ou que você pode fazer) ao adicionar custodiantes a uma ocorrência:

   - Os dados na caixa de correio do Exchange do responsável, na conta do OneDrive e em qualquer grupo do Microsoft Teams ou do Yammer dos qual o custodiante é membro podem ser "marcados" como dados custodiais no caso.
  
   - Os dados custodiante são reindexados (por um processo chamado *indexação avançada).* Isso ajuda a otimizar a pesquisa por ele na próxima etapa.
  
   - Você pode colocar em espera os dados custodiante. Isso preserva os dados que podem ser relevantes para o caso durante a investigação.
  
   - Você pode associar outras fontes de dados a um responsável (por exemplo, você pode associar um site do SharePoint ou grupo do Microsoft 365 a um custodiante) para que esses dados possam ser reindexados, colocados em espera e pesquisados, assim como os dados na caixa de correio do custodiante ou na conta do OneDrive.

   - Você pode usar o fluxo [de trabalho de](managing-custodian-communications.md) comunicação na Descoberta Eletrônica Avançada para enviar uma notificação de responsabilidade legal aos responsáveis.

2. **[Pesquisar fontes de dados para dados relevantes para o caso.](collecting-data-for-ediscovery.md)** Depois de adicionar custodiantes e fontes de dados não custodiais a uma ocorrência, use a ferramenta de pesquisa integrado para pesquisar essas fontes de dados em busca de dados que possam ser relevantes para o caso. Você usa palavras-chave, propriedades [](building-search-queries.md) e condições para criar consultas de pesquisa que retornam resultados de pesquisa com os dados que provavelmente são relevantes para o caso. Você também pode:

   - Exibir [estatísticas de pesquisa](search-statistics-in-advanced-ediscovery.md) que podem ajudá-lo a refinar uma consulta de pesquisa para restringir os resultados.

   - Visualize os resultados da pesquisa para verificar rapidamente se os dados relevantes estão sendo encontrados.

   - Revise uma consulta e rerun a pesquisa.

3. **[Adicionar dados a um conjunto de revisão.](add-data-to-review-set.md)** Depois de configurar e verificar se uma pesquisa retorna os dados desejados, a próxima etapa é adicionar os resultados da pesquisa a um conjunto de revisão. Quando você adiciona dados a um conjunto de revisão, os itens são copiados do local original para um local de armazenamento seguro do Azure. Os dados são reindexados novamente para otimize-os para pesquisas completas e rápidas ao analisar e analisar itens no conjunto de revisão. Além disso, você também pode [adicionar dados que não são do Office 365 em um conjunto de revisão.](load-non-office-365-data-into-a-review-set.md)

   Também há um tipo especial de conjunto de revisão ao qual você pode adicionar dados, chamado de conjunto de revisão *de conversa.* Esses tipos de conjuntos de análises fornecem recursos de reconstrução de conversa para reconstruir, revisar e exportar conversas encadeadas como as do Microsoft Teams. Para obter mais informações, [consulte Review conversations in Advanced eDiscovery](conversation-review-sets.md).

4. **Analisar e analisar dados em um conjunto de revisão.** Agora que os dados estão em um conjunto de revisão, você pode usar uma ampla variedade de ferramentas e recursos para exibir e analisar os dados de caso com o objetivo de reduzir o conjunto de dados para o que é mais relevante para o caso que você está investigando. Aqui está uma lista de algumas ferramentas e recursos que você pode usar durante esse processo.

   - [Exibir documentos.](view-documents-in-review-set.md) Isso inclui a exibição dos metadados de cada documento em um conjunto de revisão e a exibição do documento em sua versão nativa ou versão de texto.

   - [Criar consultas e filtros.](review-set-search.md) Você cria consultas de pesquisa usando vários critérios de pesquisa (incluindo a capacidade de pesquisar todas as propriedades de metadados de [arquivo)](document-metadata-fields-in-advanced-ediscovery.md)para refinar e reavante os dados de caso para o que for mais relevante para o caso. Você também pode usar filtros de conjunto de revisão para aplicar rapidamente outras condições aos resultados de uma consulta de pesquisa para refinar ainda mais esses resultados. 

   - [Criar e usar marcas.](tagging-documents.md) Você pode aplicar marcas a documentos em um conjunto de revisão para identificar quais são responsivas (ou não responsivas ao caso) e, em seguida, usar essas marcas ao criar consultas de pesquisa para incluir ou excluir os documentos marcados. Você também pode marcar para determinar quais documentos exportar.

   - [Anotar e reactar documentos.](view-documents-in-review-set.md#annotate-view) Você pode usar a ferramenta de anotação em uma revisão para anotar documentos e reactar conteúdo em documentos como produto comercial. Geramos uma versão em PDF de um documento anotado ou editado durante a revisão para reduzir o risco de exportar a versão nativa não corrigida do documento.

   - [Analisar dados de caso.](analyzing-data-in-review-set.md) A funcionalidade de análise na Descoberta Avançada é poderosa. Depois de executar análises nos dados no conjunto de revisão, realizamos análises como detecção quase duplicada, threading de email e temas que podem ajudar a reduzir o volume de documentos que você precisa analisar. Também geramos um relatório de Análise que resume o resultado da execução da análise. Conforme explicado anteriormente, a execução da análise também executa o modelo de detecção de [privilégio advogado-cliente.](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model)

5. **Exportar e baixar dados de caso.** Uma etapa final após coletar, analisar e analisar dados de caso é exportá-los da Descoberta Avançada para revisão externa ou para revisão por pessoas de fora da equipe de investigação. Exportar dados é um processo de duas etapas. A primeira etapa é [exportar](export-documents-from-review-set.md) dados do conjunto de revisão e copiá-lo para um local de Armazenamento do Azure diferente (um fornecido pela Microsoft ou um gerenciado pela sua organização). Em seguida, use o Azure Storage Explorer [para baixar](download-export-jobs.md) os dados em um computador local. Além dos arquivos de dados exportados, os contém do pacote de exportação também contém um relatório de exportação, um relatório resumido e um relatório de erros.
