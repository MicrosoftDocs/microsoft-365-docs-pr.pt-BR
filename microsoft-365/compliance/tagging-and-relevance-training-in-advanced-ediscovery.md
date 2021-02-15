---
title: Treinamento de Marcação e Relevância na Descoberta Avançada de EDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 8576cc86-d51b-4285-b54b-67184714cc62
ROBOTS: NOINDEX, NOFOLLOW
description: Aprenda as etapas para marcar e trabalhar com um exemplo de treinamento de 40 arquivos durante o estágio de treinamento de Relevância da Descoberta Avançada.
ms.openlocfilehash: ae4a9f2e9fd87fdd0679bbfd8f287b6eaa98e41f
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769216"
---
# <a name="tagging-and-relevance-training-in-advanced-ediscovery"></a>Treinamento de Marcação e Relevância na Descoberta Avançada de EDiscovery
  
Este artigo descreve o procedimento para trabalhar com o módulo de treinamento de relevância na Descoberta Avançada.
  
Depois que a Avaliação é concluída na Descoberta Avançada e você entra no estágio de treinamento de relevância, um exemplo de treinamento de 40 arquivos é trazido para a guia Marca para marcação.
  
## <a name="performing-relevance-training"></a>Executando treinamento de relevância

1. Na **guia \>** Marca de Relevância, o painel Marcação é exibido por padrão no painel esquerdo e os arquivos de exemplo são exibidos, um de cada vez para marcação.

    ![Painel Marca de Relevância](../media/0cf19ab4-b427-4a7f-8749-0f4ed9afaf58.png)
  
    Na guia **Marca,** o nome de exibição do arquivo é mostrado. Isso pode ser o caminho, o assunto do email, o título ou o nome definido pelo usuário. A ID, o caminho do arquivo ou o caminho do texto podem ser copiados clicando com o botão direito do mouse no caminho do arquivo.

    As  estatísticas de marcação da guia Marca mostram o número de exemplo de arquivo (na parte superior do painel esquerdo), o número do arquivo atualmente exibido fora do total de arquivos na amostra (parte inferior do painel direito) e o número total atual de arquivos marcados no exemplo (inferior do painel esquerdo), que muda conforme você marca os arquivos. Isso se aplica a qualquer marcação de Relevância realizada, seja em Avaliação, Treinamento, Catch-up ou Teste.

    Ícones que indicam a existência de comentários, marcas e arquivos de família são exibidos na exibição de arquivo em uma barra acima do arquivo.

2. Determine a relevância do arquivo para o problema de caso e marque o arquivo usando os botões de ícone de opção de marcação ou atalhos de teclado, conforme mostrado na tabela a seguir:

   |**Opção de marcação**|**Descrição**|**Atalho do teclado**|**Atalho de teclado de marcação em massa (para vários problemas)**|
   |-----|-----|-----|-----|
   |R  <br/> |Relevante  <br/> |Z  <br/> |`Shift + Z`  <br/> |
   |NR  <br/> |Não relevante  <br/> |X  <br/> |`Shift + X`  <br/> |
   |Ignorar  <br/> |Ignorar  <br/> |C  <br/> |`Shift + A`  <br/> |
   |||||

   - Quando existem vários problemas para um arquivo, após marcar um problema, a seleção passa para o próximo problema (se existir).  

   - As palavras-chave que foram definidas pelo administrador ou pelo gerente de caso ao realçar palavras-chave (palavras-chave realçadas na configuração de relevância) serão exibidas (em cores especificadas) para ajudar a identificar arquivos relevantes durante a \> marcação. Se uma palavra-chave tiver um sublinhado duplo, ela poderá ser clicada para exibir uma dica de ferramenta com a descrição da palavra-chave.

     Opcionalmente, na guia **Marca,** clique nas **configurações de Marca** para definir as seguintes opções:

      ![Configurações de marca de relevância](../media/533e89fa-7eb4-409e-ab07-f5aab9296dd8.png)
  
   - **Marca em** massa: Use essa opção para  atribuir vários problemas para um arquivo selecionando Tudo para definir a marca do arquivo selecionado para todos os problemas (substitui problemas já marcados) ou selecionando **O** restante para aplicar a marca aos problemas restantes sem marcação. A opção selecionada permanece em vigor para todos os casos desse usuário até que seja alterada por esse usuário (a configuração é por usuário para todos os casos do usuário).

   - **Marca automática:** marque essa caixa de seleção para definir outros problemas de um arquivo como Não relevantes após uma única marcação Relevante.

   - **Avançar automaticamente:** marque essa caixa de seleção para mover a seleção de arquivo exibida para o próximo arquivo ao marcar o último problema ou apenas um problema não marcado.

    Os arquivos ignorados não serão considerados para fins de treinamento de relevância e pontuação de relevância.

3. Comentários de texto livre, associados a um arquivo, podem ser exibidos e editados por meio da opção **Comentário** na lista de lista do painel esquerdo. (opcional)

4. As diretrizes de marcação podem ser **exibidas** selecionando a opção De diretrizes de marcação na lista de lista do painel esquerdo.

5. Depois de concluir a marcação de todos os arquivos na lista e estiver pronto para calcular os resultados, clique em **Calcular**. A **guia** Controlar é exibida.  

## <a name="working-with-the-sample-files-list"></a>Trabalhar com a lista de arquivos de exemplo

A lista de arquivos de exemplo permite que você veja uma lista dos arquivos em um exemplo de treinamento e execute várias ações em um ou mais arquivos. Na **guia** Marca de Relevância, o painel Arquivos de exemplo à esquerda exibe uma lista de arquivos de exemplo para processamento com processos de Avaliação, Treinamento, Recuperação e Inconsistências. \>  
  
1. Na guia **Marca \> de Relevância,** selecione os arquivos de exemplo na lista de lista do painel esquerdo. Os arquivos de exemplo estão listados no painel esquerdo.

    ![Lista de arquivos de exemplo de Marca de Relevância](../media/fd058bdd-645a-4af1-a1eb-bff08581cb18.png)
  
2. Selecione um exemplo ou número de arquivo específico inserindo ou selecionando seu número nas caixas **de** exemplo **ou arquivo.**

   - Um número de sequência de arquivos é listado na coluna esquerda da lista de arquivos exibida na **guia** Marca. Ao clicar no título, a ordem original exibida dos arquivos retorna à sua ordem original.

   - Clicar em uma linha de arquivo exibe seu conteúdo no painel direito.

   - Navegue entre arquivos no exemplo atual usando as opções da barra de menus inferior. Além disso, os atalhos de teclado de navegação estão disponíveis:
  
     - Para ir para o primeiro arquivo no exemplo: `Shift + Ctrl + <`

     - Para ir para o arquivo anterior no exemplo: `Shift + <`

     - Para ir para o próximo arquivo no exemplo: `Shift + >`

     - Para ir para o último arquivo no exemplo: `Shift + Ctrl + >`
