---
title: Revisar conversas na Descoberta Avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Saiba como usar o recurso de Reconstrução de Conversa na Descoberta Avançada para reconstruir, revisar e exportar conversas encadeadas.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bf5c39f567240b58546dbeb353e3e461e9b69e48
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358339"
---
# <a name="review-conversations-in-advanced-ediscovery"></a>Revisar conversas na Descoberta Avançada 

O sistema de mensagens instantâneas é uma maneira conveniente de fazer perguntas, compartilhar ideias ou comunicar-se rapidamente entre grandes públicos. À medida que as plataformas de mensagens instantâneas, como o Microsoft Teams, se tornam fundamentais para a colaboração corporativa, as organizações devem avaliar como seu fluxo de trabalho de Descoberta Eletrônico aborda essas novas formas de comunicação e colaboração. 

O recurso de Reconstrução de Conversa na Descoberta Avançada foi projetado para ajudá-lo a identificar conteúdo contextual e produzir exibições de conversa distintas. Esse recurso permite que você revise com eficiência e rapidez a conclusão de conversas de mensagens instantâneas (também chamadas de conversas encadeadas) geradas em plataformas como o Microsoft Teams.

Com a Reconstrução da Conversa, você pode usar recursos integrados para reconstruir, revisar e exportar conversas encadeadas. Use Advanced eDiscovery Conversation Reconstruction to:

- Preservar metadados exclusivos no nível da mensagem em todas as mensagens de uma conversa.

- Coletar mensagens contextuais em torno dos resultados da pesquisa.

- Revise, anota e reacte conversas encadeadas.

- Exportar mensagens individuais ou conversas encadeadas

## <a name="terminology"></a>Terminologia

Aqui estão algumas definições para ajudá-lo a começar a usar a Reconstrução da Conversa.

- **Mensagens:** Representa a menor unidade de uma conversa. As mensagens podem variar em tamanho, estrutura e metadados. 

- **Conversa:** Representa um grupo de uma ou mais mensagens. Em diferentes aplicativos, as conversas podem ser representadas de maneiras diferentes. Em alguns aplicativos, há uma ação explícita que resulta da resposta a uma mensagem existente. As conversas são formadas explicitamente como resultado dessa ação do usuário. Por exemplo, aqui está uma captura de tela de uma conversa de canal no Microsoft Teams.

   ![Conversa do canal do Microsoft Teams](../media/threadedchat.png)

   Em outros aplicativos (como mensagens de chat 1xN no Teams), não há uma cadeia de resposta formal e, em vez disso, as mensagens aparecem como um "river plano de mensagens" dentro de um único thread. Nesses tipos de aplicativos, as conversas são adiadas de um grupo de mensagens que ocorrem dentro de um determinado tempo. Esse "soft-grouping" de mensagens (em vez de uma cadeia de resposta) representa a conversa "voltar e voltar" sobre um tópico específico de interesse. 

## <a name="step-1-run-a-search"></a>Etapa 1: Executar uma pesquisa

Depois de identificar os custodiantes relevantes e locais de conteúdo, você pode criar uma pesquisa para encontrar conteúdo potencialmente relevante. Na guia **Pesquisas** no caso de Descobertas Avançadas, você pode criar uma pesquisa clicando em Nova pesquisa **e** seguindo o assistente. For information about how you can create a search, build a search query, and view the search results, see [Collect data for a case](create-search-to-collect-data.md).

## <a name="step-2-create-a-conversation-review-set"></a>Etapa 2: Criar um conjunto de revisão de conversa

Em um conjunto de revisão, você pode pesquisar, marcar, anotar e reencenar documentos, mensagens de email e conversas de chat. Na Descoberta Avançada, você pode personalizar sua revisão de conversas, com base em mensagens individuais ou conversas encadeadas. Isso é determinado pelo tipo de conjunto de revisão ao qual você adiciona os resultados da pesquisa criada na Etapa 1. Há dois tipos diferentes de conjuntos de revisão: 
  
  - **Conjuntos de revisão padrão:** As mensagens em conversas são processadas e exibidas como itens individuais. 
  
  -  **Conjuntos de revisão de conversa:** As mensagens em conversas são processadas individualmente, mas exibidas em uma exibição de conversa. Em um conjunto de revisão de conversa, você pode anotar, marcar e reactar mensagens em uma exibição de conversa encadeada. 

Para obter mais informações sobre como revisar e gerenciar conteúdo em um conjunto de revisão, consulte [Gerenciar conjuntos de revisão.](managing-review-sets.md) 

## <a name="step-3-enable-conversation-retrieval-options"></a>Etapa 3: Habilitar opções de recuperação de conversa

Depois de revisar e finalizar a consulta de pesquisa, você poderá adicionar os resultados da pesquisa a um conjunto de revisão. Quando você adiciona os resultados da pesquisa em um conjunto de revisão, os dados originais são copiados para uma área de Armazenamento do Azure para facilitar o processo de análise e revisão. Para obter mais informações sobre como adicionar resultados de pesquisa a um conjunto de revisão, consulte [Adicionar resultados de pesquisa a um conjunto de revisão.](add-data-to-review-set.md) 

Ao adicionar dados de conversas a um conjunto de revisão, você pode usar as opções de recuperação de conversa para expandir sua pesquisa e incluir mensagens contextuais. Depois de definir as opções de recuperação de conversa, as seguintes coisas podem acontecer:

  ![Recuperação de Conversa](../media/messagesandconversations.png)
  
1. Usando uma palavra-chave e uma consulta de intervalo de datas, a pesquisa retornou uma mensagem *3*. Esta mensagem fazia parte de uma conversa maior, ilustrada por *CRC1.* 
  
2. Quando você adiciona os dados em um conjunto de revisão e habilita as opções de recuperação de conversa, a Descoberta Avançada volta e coleta outros itens no *CRC1*. 
  
3. Depois que os itens foram adicionados ao conjunto de revisão, você pode revisar todas as mensagens individuais de *CRC1*. 

Para habilitar a recuperação de conversa:
  
1. Na guia **Pesquisas no** caso de Descobertas Avançadas, selecione  uma pesquisa e clique em Adicionar para revisar definida na página do flyout.
  
2. Selecione um conjunto de revisão existente ou crie um conjunto de revisão. Você pode configurar opções de recuperação ao adicionar resultados de pesquisa a um conjunto de revisão de conversa ou padrão.
  
3. Em **Opções de coleção,** configure as opções de recuperação de conversa para as  fontes de conteúdo que você deseja expandir em sua pesquisa e clique em Adicionar para iniciar o processo.  
  
4. Depois que **o trabalho de conjunto Adicionar a revisão** na guia **Trabalhos** tiver sido concluído, você poderá começar a revisar as conversas.

## <a name="step-4-review-and-export-conversations-in-a-review-set"></a>Etapa 4: Revisar e exportar conversas em um conjunto de revisão

Depois que o conteúdo tiver sido processado e adicionado ao conjunto de revisão, você poderá começar a analisar os dados no conjunto de revisão. Os recursos de revisão são diferentes dependendo se o conteúdo foi adicionado a um conjunto de revisão padrão ou a um conjunto de revisão de conversa. 

### <a name="reviewing-conversations-in-a-standard-review-set"></a>Revendo conversas em um conjunto de revisão padrão

Em um conjunto de revisão padrão, as mensagens são processadas e exibidas como itens individuais, semelhante à forma como são armazenadas em uma pasta da caixa de correio. Nesse fluxo de trabalho, cada mensagem é processada como um item separado. Como resultado, as opções de exportação e resumo threaded não estão disponíveis em um conjunto de revisão padrão. 

  ![Conjunto de revisão padrão](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a>Revendo conversas em um conjunto de revisão de conversa

Em um conjunto de revisão de conversa, mensagens individuais são encadeadas e apresentadas como conversas. Isso permite que você revise e exporte conversas contextuais. 

  ![Conjunto de revisão de conversa](../media/ConversationRSOptions.PNG)

As seções a seguir descrevem a revisão e a exportação de conversas em um conjunto de revisão de conversa.

#### <a name="reviewing-conversations"></a>Revendo conversas

Em um conjunto de revisão de conversa, você pode usar as seguintes opções para facilitar o processo de revisão.

- **Agrupar por conversa:** Reúne mensagens dentro da mesma conversa para ajudar os usuários a simplificar e acelerar o processo de revisão. 

- **Exibição resumida:** Exibe a conversa encadeada. Nessa exibição, você pode ver a conversa inteira e também acessar os metadados de cada mensagem individual.  
  
   - Exibir metadados para mensagens individuais
   
   - Baixar mensagens individuais

- **Exibição de texto:** Fornece o texto extraído para toda a conversa. 

- **Exibição de anotações:** Permite marcar uma exibição encadeada da conversa. Todas as mensagens na conversa compartilham o mesmo documento anotado.

- **Marcação:** Ao exibir conversas em um conjunto de revisão,  você pode exibir e aplicar marcas clicando no painel marcação no painel de codificação.

- **Rerun conversation conversion:** Quando as mensagens são adicionadas a um conjunto de revisão de conversa, um trabalho de conversão é executado automaticamente para criar o resumo encadeado e anotar as exibições. Se o trabalho de Reconstrução da Conversa falhar, você poderá reprisar esse trabalho clicando em Ação **> Criar PDFs** de conversa no conjunto de revisão.

#### <a name="exporting-conversations"></a>Exportando conversas

Em um conjunto de revisão de conversa, você pode definir as seguintes opções para exportar conversas:

![Opções de exportação para conversas](../media/export.png)

a. Opções de metadados

   - **Carregar arquivo:** Os metadados são incluídos para cada mensagem individual, email e documento. Há uma linha para cada mensagem em uma conversa. 

   - **Marcas:** As marcas do seu processo de revisão estão incluídas no arquivo de metadados. As mensagens em uma conversa compartilham as mesmas marcas. 

b. Opções de conversa
  
   - **Arquivos de conversa:** Quando você exporta arquivos de conversa, o exibição anotado é convertido em um arquivo PDF e baixado para a pasta de exportação. As mensagens em um arquivo de conversa apontam para a versão PDF do mesmo arquivo de conversa.  
  
   - **Mensagens de chat individuais:** Quando você exporta mensagens individuais, cada mensagem exclusiva na conversa é exportada como um item autônomo. O arquivo é exportado no mesmo formato em que foi salvo como na caixa de correio. Para uma conversa específica, você recebe vários arquivos .msg. 

     >[!NOTE]
     > Se você aplicou anotações ao arquivo de conversa, essas anotações não serão transferidas para as mensagens individuais. 

c. Outras opções

   - **Gere arquivos de texto para todo o conteúdo exportado:** Gera um arquivo de texto para cada conversa exportada do conjunto de revisão. 

   - **Substitua o conteúdo exportado por PDFs redacionados:** Se os arquivos de conversa redacted são gerados durante o processo de revisão, esses arquivos estarão disponíveis durante a exportação. Você pode decidir se exportará somente os arquivos nativos (não selecionando essa opção) ou se substituirá os arquivos nativos pelas versões redacionadas dos arquivos nativos (selecionando essa opção), que serão exportados como arquivos PDF.

## <a name="more-information"></a>Mais informações

Para saber mais sobre como revisar dados de caso na Descoberta Avançada, consulte os seguintes artigos:

- [Exibir dados de ocorrência](view-documents-in-review-set.md)

- [Analisar dados de ocorrência](analyzing-data-in-review-set.md)

- [Exportar dados de ocorrência](exporting-data-ediscover20.md)
