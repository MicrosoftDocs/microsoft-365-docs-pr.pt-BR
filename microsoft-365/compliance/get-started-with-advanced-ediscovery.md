---
title: Introdução à descoberta eletrônica avançada no Microsoft 365
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
description: Este artigo descreve como começar a usar a descoberta eletrônica avançada no Microsoft 365. Após concluir algumas etapas rápidas, a ferramenta de descoberta eletrônica avançada estará pronta para uso. A primeira etapa é criar uma ocorrência e começar a usar recursos e funcionalidades avançados de descoberta eletrônica.
ms.openlocfilehash: b351524f1bcaa54360d9f7422c0955c5c4a35254
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557901"
---
# <a name="get-started-with-advanced-ediscovery"></a>Introdução à descoberta eletrônica avançada

A descoberta eletrônica avançada no Microsoft 365 fornece um fluxo de trabalho de ponta a ponta para preservar, coletar, analisar, analisar e exportar dados que respondem às investigações internas e externas da sua organização. Nada é necessário para implantar a descoberta eletrônica avançada, mas há algumas tarefas de pré-requisito que um administrador de ti e um gerente de descoberta eletrônica precisam concluir para que sua organização possa começar a criar e usar casos de descoberta eletrônica avançados para gerenciar suas investigações.

Este artigo discute as etapas necessárias para configurar a descoberta eletrônica avançada. Isso inclui garantir que o licenciamento apropriado seja necessário para acessar a descoberta eletrônica avançada e adicionar os responsáveis às ocorrências, bem como atribuir permissões à equipe jurídica e de investigação para que eles possam acessar e gerenciar casos. Este artigo também fornece uma visão geral de alto nível do uso de casos para gerenciar o fluxo de trabalho de descoberta eletrônica avançada de uma investigação legal.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Etapa 1: verificar e atribuir licenças apropriadas

O licenciamento para descoberta eletrônica avançada requer a assinatura apropriada da organização e o licenciamento por usuário.

- **Assinatura da organização:** Para acessar a descoberta eletrônica avançada no centro de conformidade da Microsoft 365 ou no centro de conformidade & segurança do Office 365, sua organização deve ter um dos seguintes:

  - Assinatura do Microsoft 365 E5 ou do Office 365 e5
  
  - Assinatura do Microsoft 365 E3 com complemento de conformidade e5
  
  - Assinatura do Office 365 E3 com complemento de conformidade avançada

  Se você não tiver um plano do Microsoft 365 E5 existente e quiser experimentar a descoberta eletrônica avançada, poderá [Adicionar o microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) à sua assinatura existente do Office 365 ou [inscrever-se para uma avaliação](https://www.microsoft.com/microsoft-365/enterprise) do Microsoft 365 e5.

- **Licenciamento por usuário:** Para adicionar um usuário como um responsáveis em um caso de descoberta eletrônica avançada, esse usuário deve receber uma das seguintes licenças, dependendo da sua assinatura de organização:

  - Microsoft 365: os usuários devem receber uma licença do Microsoft 365 E5 ou uma licença de complemento de conformidade e5.

  - Office 365: os usuários devem receber uma licença do Office 365 E5 ou uma licença avançada de complemento de conformidade.

   Para obter informações sobre como atribuir licenças, consulte [assign licenses to Users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

> [!NOTE]
> Os usuários só precisam de uma licença E5 (ou da licença de complemento adequada) para serem adicionados como responsáveis a uma ocorrência de descoberta eletrônica avançada. Administradores de ti, gerentes de descoberta eletrônica, advogados, paralegais ou investigadores que usam a descoberta eletrônica avançada para gerenciar casos e revisar os dados de casos não precisam de uma licença E5 ou complementar.

## <a name="step-2-assign-ediscovery-permissions"></a>Etapa 2: atribuir permissões de descoberta eletrônica

Para acessar a descoberta eletrônica avançada ou adicionada como um membro de um caso de descoberta eletrônica avançada, um usuário deve ter as permissões apropriadas atribuídas. Especificamente, um usuário deve ser adicionado como um membro do grupo de função Gerenciador de descoberta eletrônica no centro de conformidade & segurança do Office 365. Os membros desse grupo de função podem criar e gerenciar casos de descoberta eletrônica avançados. Eles podem adicionar e remover membros, colocar os responsáveis e os locais de conteúdo em espera, gerenciar notificações de retenção legal, criar e editar pesquisas associadas em um caso, adicionar resultados de pesquisa a um conjunto de revisão, analisar dados em um conjunto de revisão e exportar e baixar de um avançado ocorrência de descoberta eletrônica.

Conclua as seguintes etapas para adicionar usuários ao grupo de funções Gerenciador de descoberta eletrônica:

1. Acesse [https://protection.office.com/permissions](https://protection.office.com/permissions) e entre usando as credenciais de uma conta de administrador na sua organização do Microsoft 365.

2. Na página **permissões** , selecione o grupo de funções **Gerenciador de descoberta eletrônica** .

3. Na página do submenu Gerenciador de descoberta eletrônica, clique em **Editar** ao lado da seção **Gerenciador de descoberta eletrônica** .

4. Na página **escolher Gerenciador de descoberta eletrônica** no assistente editar grupo de funções, clique em **escolher Gerenciador de descoberta**.

5. Clique em **Adicionar** e marque a caixa de seleção de todos os usuários que você deseja adicionar ao grupo de funções.

6. Clique em **Adicionar** para adicionar os usuários selecionados e clique em **concluído**.

7. Clique em **salvar** para adicionar os usuários ao grupo de função e, em seguida, clique em **fechar** para concluir a etapa.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Mais informações sobre o grupo de funções do Gerenciador de descoberta eletrônica

Há dois subgrupos no grupo de função Gerenciador de descoberta eletrônica. A diferença entre esses subgrupos está no escopo.

- **Gerenciador de descoberta eletrônica:** Pode exibir e gerenciar as ocorrências de descoberta eletrônica avançada que criam ou são membros de. Se outro gerenciador de descoberta eletrônica criar uma ocorrência, mas não adicionar um segundo Gerenciador de descoberta eletrônica como membro desse caso, o segundo Gerenciador de descoberta eletrônica não poderá exibir ou abrir o caso na página descoberta eletrônica avançada no centro de conformidade. Em geral, a maioria das pessoas em sua organização pode ser adicionada ao subgrupo Gerenciador de descoberta eletrônica.

- **administrador de descoberta eletrônica:** Pode executar todas as tarefas de gerenciamento de caso que um gerente de descoberta eletrônica possa fazer. Além disso, um Administrador de Descoberta Eletrônica pode:

  - Exibir todas as ocorrências listadas na página descoberta eletrônica avançada.
  
  - Gerencie qualquer caso na organização depois que eles se adicionarem como um membro do caso.

  - Acessar e exportar dados de caso para qualquer caso na organização.

  Por causa do amplo escopo de acesso, uma organização deve ter apenas alguns administradores que são membros do subgrupo administradores de descoberta eletrônica.

Para obter mais informações sobre permissões de descoberta eletrônica e uma descrição de cada função atribuída ao grupo de funções Gerenciador de descoberta eletrônica, consulte [atribuir permissões de descoberta eletrônica no centro de conformidade de & de segurança](assign-ediscovery-permissions.md).

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a>Etapa 3: definir as configurações globais para descoberta eletrônica avançada

A última etapa a ser concluída antes que as pessoas da sua organização comecem a criar e usar casos é definir as configurações globais que se aplicam a todos os casos em sua organização. Neste momento, a única configuração global disponível é a *detecção de privilégio de cliente advogado* (mais configurações globais estarão disponíveis no futuro). Essa configuração permite que o modelo de privilégio de cliente advogado seja executado quando você analisar dados em um conjunto de revisão. O modelo usa o Machine Learning para determinar a probabilidade de que um documento contenha conteúdo legal de natureza. Também compara os participantes de documentos com uma lista de advogados (que você envia ao configurar o modelo) para determinar se um documento tem pelo menos um participante que seja um advogado.

Para obter mais informações sobre como configurar e usar o modelo de detecção de privilégio de cliente advogado, consulte [Configurar detecção de privilégio de cliente do advogado na descoberta eletrônica avançada](attorney-privilege-detection.md).

> [!NOTE]
> Esta é uma etapa opcional que você pode executar a qualquer momento. Não implementar o modelo de detecção de privilégio de cliente advogado não impede que você crie e use casos de descoberta eletrônica avançados.

## <a name="step-4-create-an-advanced-ediscovery-case"></a>Etapa 4: criar uma ocorrência de descoberta eletrônica avançada

A próxima etapa é criar um caso e começar a usar a descoberta eletrônica avançada. Conclua as etapas a seguir para criar um caso e adicionar membros. O usuário que cria o caso é automaticamente adicionado como um membro.

1. Acesse [https://compliance.microsoft.com](https://compliance.microsoft.com) e entre usando as credenciais da conta de usuário que receberam as permissões de descoberta eletrônica apropriadas. Os membros do grupo de função gerenciamento da organização também podem criar casos de descoberta eletrônica avançados.

2. No painel esquerdo do centro de conformidade da Microsoft 365, clique em **Mostrar tudo**e, em seguida, clique em **descoberta eletrônica > avançado**.

3. Na página **descoberta eletrônica avançada** , clique na guia **ocorrências** e, em seguida, clique em **criar uma ocorrência**.

4. Na página novo submenu de **ocorrência de descoberta eletrônica** , dê um nome (obrigatório) e digite um número de caso e descrição opcionais. O nome da ocorrência deve ser exclusivo em sua organização.

5. Clique em **salvar** para criar o caso.

   O novo caso é criado e a guia **configurações** no novo caso é exibida. 

6. No bloco **acesso & permissões** na guia **configurações** , clique em **selecionar**e, em seguida, clique em **Atualizar**.

7. Clique em **Atualizar**.

8. Na página **gerenciar esse** submenu de caso, em **gerenciar Membros**, clique em **Adicionar** para adicionar membros ao caso.

9. Na lista de pessoas, marque a caixa de seleção ao lado dos nomes das pessoas que você deseja adicionar ao caso. Conforme explicado anteriormente, certifique-se de que as pessoas adicionadas ao caso tenham sido atribuídas às permissões de descoberta eletrônica apropriadas.

10. Depois de selecionar as pessoas a serem adicionadas como membros do caso, clique em **Adicionar**.

11. Na página **gerenciar esse** submenu de caso, clique em **salvar** para salvar a nova lista de membros de caso.

12. Clique na guia **página inicial** para ir para a Home Page da caixa.

## <a name="explore-the-advanced-ediscovery-workflow"></a>Explorar o fluxo de trabalho de descoberta eletrônica avançada

Para começar a usar a descoberta eletrônica avançada, aqui está um fluxo de trabalho simples que se alinha às [práticas comuns de descoberta eletrônica](overview-ediscovery-20.md#alignment-with-edrm). Em cada uma dessas etapas, também realçaremos algumas funcionalidades avançadas de descoberta eletrônica que você pode explorar.

![Fluxo de trabalho de descoberta eletrônica avançada](../media/AeDWorkflow.png)

1. **[Adicionar os responsáveis a um caso](add-custodians-to-case.md)**. A primeira etapa depois da criação de um caso é adicionar os responsáveis. Um *funcionário* é uma pessoa com controle administrativo de um documento ou arquivo eletrônico que pode ser relevante para o caso. Veja a seguir algumas coisas que acontecem (ou que você pode fazer) ao adicionar os responsáveis a um caso:

   - Os dados da caixa de correio do Exchange do responsáveis, da conta do OneDrive e de qualquer grupo do Microsoft Teams ou do Yammer para os quais o responsáveis é membro podem ser "marcados" como dados do custodial no caso.
  
   - Os dados dos responsáveis são re-indexados (por um processo chamado *indexação avançada*). Isso ajuda a otimizar a pesquisa para ele na próxima etapa.
  
   - Você pode colocar um bloqueio nos dados dos responsáveis. Isso preserva os dados que podem ser relevantes para o caso durante a investigação.
  
   - Você pode associar outras fontes de dados a um funcionário (por exemplo, você pode associar um site do SharePoint ou um grupo do Office 365 a um funcionário) para que esses dados possam ser reindexados, colocados em retenção e pesquisados, como os dados da caixa de correio ou da conta do OneDrive do responsáveis.

   - Você pode usar o [fluxo de trabalho de comunicações](managing-custodian-communications.md) em descoberta eletrônica avançada para enviar uma notificação de retenção legal para os responsáveis.

2. **[Pesquisar fontes de dados do custodial para dados relevantes para o caso](collecting-data-for-ediscovery.md)**. Após adicionar os responsáveis a um caso, use a ferramenta de pesquisa interna para pesquisar os locais de dados dos responsáveis por dados que podem ser relevantes para o caso. Você usa palavras-chave, propriedades e condições para [criar consultas de pesquisa](building-search-queries.md) que retornem resultados de pesquisa com os dados que mais provavelmente são relevantes para o caso. Você também pode:

   - Exibir [Estatísticas de pesquisa](search-statistics.md) que podem ajudá-lo a refinar uma consulta de pesquisa para restringir os resultados.

   - Visualize os resultados da pesquisa para verificar rapidamente se os dados relevantes estão sendo encontrados.

   - Revise uma consulta e execute a pesquisa novamente.

3. **[Adicione dados a um conjunto de revisão](add-data-to-review-set.md)**. Depois de configurar e verificar se uma pesquisa retorna os dados desejados, a próxima etapa é adicionar os resultados da pesquisa a um conjunto de revisão. Quando você adiciona dados a um conjunto de revisão, os itens são copiados do seu local original para um local seguro de armazenamento do Azure. Os dados são novamente reindexados para otimizá-lo para pesquisas completas e rápidas ao revisar e analisar itens no conjunto de revisão. Além disso, você também pode [Adicionar dados que não sejam do Office 365 em um conjunto de revisão](load-non-office-365-data-into-a-review-set.md).

   Há também um tipo especial de análise configurada para a qual você pode adicionar dados, chamado de *análise de conversa*. Esses tipos de conjuntos de análise fornecem recursos de reconstrução de conversa para reconstruir, revisar e exportar conversas encadeadas como as do Microsoft Teams. Para obter mais informações, consulte [revisar conversas na descoberta eletrônica avançada](conversation-review-sets.md).

4. **Revise e analise os dados em um conjunto de revisão**. Agora que os dados estão em um conjunto de revisão, você pode usar uma ampla variedade de ferramentas e recursos para exibir e analisar os dados de caso com o objetivo de reduzir o conjunto de dados para o que é mais relevante para o caso que está investigando. Veja a seguir uma lista de algumas ferramentas e recursos que você pode usar durante esse processo.

   - [Exibir documentos](view-documents-in-review-set.md). Isso inclui exibir os metadados para cada documento em um conjunto de revisão e exibir o documento em sua versão nativa ou versão de texto.

   - [Criar consultas e filtros](review-set-search.md). Você cria consultas de pesquisa usando uma variedade de critérios de pesquisa (incluindo a capacidade de Pesquisar todas as [Propriedades de metadados do arquivo](document-metadata-fields-in-advanced-ediscovery.md)) para refinar e analisar os dados do caso para o que é mais relevante para o caso. Você também pode usar o configure Set Filters para aplicar rapidamente condições adicionais aos resultados de uma consulta de pesquisa para refinar ainda mais esses resultados. 

   - [Criar e usar marcas](tagging-documents.md). Você pode aplicar marcas a documentos em um conjunto de revisão para identificar quais estão respondendo (ou não respondendo ao caso) e, em seguida, use essas marcas ao criar consultas de pesquisa para incluir ou excluir os documentos marcados. Você também pode marcar para determinar quais documentos serão exportados.

   - [Anotar e redigir documentos](view-documents-in-review-set.md#annotate-view). Você pode usar a ferramenta de anotação em uma revisão para anotar documentos e redigir conteúdo em documentos como produto de trabalho. Geramos uma versão em PDF de um documento anotado ou redigido durante a revisão para reduzir o risco de exportação da versão nativa não redigida do documento.

   - [Analisar dados de caso](analyzing-data-in-review-set.md). A funcionalidade de análise na descoberta eletrônica avançada é poderosa. Depois de executar a análise nos dados no conjunto de revisão, realizamos análises como a detecção de duplicidades, encadeamento de email e temas que podem ajudar a reduzir o volume de documentos que você precisa examinar. Também geramos relatórios de análise que resumem o resultado da execução da análise. Como explicado anteriormente, a execução de análise também executa [o modelo de detecção de privilégio advogado-cliente](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model).

5. **Exportar e baixar dados de caso**. Uma etapa final após coletar, revisar e analisar os dados do caso é exportá-lo para a descoberta eletrônica avançada para análise externa ou para análise por pessoas de fora da equipe de investigação. A exportação de dados é um processo de duas etapas. A primeira etapa é [Exportar](export-documents-from-review-set.md) o conjunto de análise e em um local de armazenamento do Azure diferente (fornecido pela Microsoft ou um gerenciado por sua organização). Em seguida, use o Azure Storage Explorer para [baixar](download-export-jobs.md) os dados para um computador local. Além dos arquivos de dados exportados, o contém o pacote de exportação também contém um relatório de exportação, um relatório de resumo e um relatório de erros.
