---
title: 'Descoberta e cura de tópicos do Microsoft Viva Topics  '
description: Visão geral de como os tópicos são descobertos.
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: 036dbc4029cc7e8308ad295ccd8b45dc3879a6f8
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453952"
---
# <a name="microsoft-viva-topics-discovery-and-curation"></a>Descoberta e seleção de Tópicos do Microsoft Viva 

Os Tópicos do Viva organizam informações para conhecimento em seu ambiente do Microsoft 365. Todos passamos pela leitura por meio de documentos e páginas de site em que encontramos termos que não estão familiarizados. Muitas vezes, paramos o que estamos fazendo para gastar um tempo valioso procurando mais informações.

Os Tópicos do Viva usam o Microsoft Graph e a AI para identificar **tópicos** em sua organização.  Um tópico é uma frase ou termo que tem um significado específico para a organização e tem recursos relacionados a ele que podem ajudar as pessoas a entender o que é e encontrar mais informações sobre ela. Há vários tipos diferentes de tópicos que serão importantes para sua organização. Inicialmente, os seguintes tipos de tópicos podem ser identificados:
- Project
- Evento
- Organização
- Localização
- Produto
- Trabalho criativo
- Campo de estudo

A IA identifica pessoas e conteúdo conectado ao tópico e, se o suficiente for descoberto, ele se tornará um tópico sugerido. Ele procura identificar as seguintes propriedades e exibi-las em uma **página tópico**:
- Nomes alternativos e/ou acrônimos.
- Uma breve descrição do tópico.
- Pessoas que podem ter conhecimento sobre o tópico.
- Arquivos, páginas e sites relacionados ao tópico.

As propriedades são identificadas dos arquivos e páginas que fazem parte das evidências para identificar o tópico. Nomes alternativos e acrônimos são fonte desses arquivos e páginas. A descrição curta é origem desses arquivos e páginas ou da Internet por meio da Wikipédia. O arquivo de origem, página ou artigo da Wikipédia é referenciado juntamente com as propriedades sugeridas. As pessoas são sugeridas com base em suas contribuições ativas (por exemplo, edições) para os arquivos e páginas. Uma referência à quantidade de contribuições de uma pessoa específica fornece uma dica sobre por que a pessoa foi identificada. Arquivos, páginas e sites são classificados com base em se eles são centrais no tópico, se eles podem dar uma visão geral ou introdução ao tópico. 

Nem todos os tópicos identificados serão úteis para sua organização. Ele pode não ter identificado nenhum dos nomes alternativos corretos, descrições, as pessoas apropriadas ou o conteúdo. Portanto, a capacidade de adicionar tópicos que não são identificados, manter tópicos sugeridos e tópicos de cura é fundamental para melhorar a qualidade dos tópicos que podem ser descobertos em sua organização.

Em seguida, os tópicos do Viva, quando o contexto for apropriado, sugerirão que esses tópicos sejam realçados em todas as páginas de site modernas do SharePoint em seu locatário. O tópico também pode ser referenciado diretamente na página de site moderno do SharePoint por um autor de página. Quando um usuário está curioso para saber mais sobre um tópico, ele pode selecionar o tópico realçado para exibir um **cartão de** resumo tópico que fornece uma breve descrição. E se eles quiserem saber mais, eles podem selecionar um link **de** detalhes de tópico no resumo para abrir a página de tópico detalhada.

![Destaques de tópicos](../media/knowledge-management/saturn.png) </br>

Além disso, os usuários também poderão encontrar tópicos por meio da Pesquisa da Microsoft.

## <a name="topic-curation-and-feedback"></a>Curadoria de tópicos e comentários

Os Tópicos do Viva recebem a contribuição humana para melhorar a qualidade de seus tópicos. Embora inicialmente a AI identifique e sugira tópicos, as edições manualmente feitas para o conteúdo de colaboradores, tópicos adicionados manualmente, confirmação de usuários para propriedades e conteúdo descobertos pela IA e comentários sobre a utilidade dos tópicos são essenciais.

- Os tópicos podem ser revisados pelos **gerentes de conhecimento** em sua organização. O gerente de conhecimento pode revisar tópicos que eles têm permissões para ver. Na página Gerenciar Tópicos na Central de Tópicos, eles podem optar por confirmar tópicos gerados por AI ("tópicos sugeridos") como válidos, rejeitar tópicos para impedir que o conteúdo seja exibido como um tópico, criar tópicos que não foram descobertos pela AI ou identificar tópicos que podem se beneficiar de algumas edições por especialistas em assuntos para serem mais úteis ou precisos. Para obter mais informações, [consulte Manage topics in the Topic center](manage-topics.md).

- Você pode atribuir permissões Criar e *editar tópicos* a qualquer um dos usuários licenciados para que eles possam fazer alterações nos tópicos existentes ou criar novos tópicos. Isso permite que os usuários que têm conhecimento sobre o tópico atualizem a página do tópico diretamente para fazer correções ou adicionar informações adicionais. Eles também podem adicionar novos tópicos que a AI não foi capaz de identificar. Se houver informações suficientes sobre esses tópicos adicionados manualmente e a AI for capaz de identificar esse tipo de tópico, sugestões adicionais da AI podem aprimorar esses tópicos adicionados manualmente. Juntos, os humanos e a IA podem manter o conhecimento preciso ao longo do tempo e não ter esse repouso em uma única pessoa. Para obter mais informações, [consulte Create a new topic and](https://docs.microsoft.com/microsoft-365/knowledge/create-a-topic) Edit a [topic](https://docs.microsoft.com/microsoft-365/knowledge/edit-a-topic).

- Mesmo os usuários que só têm acesso de leitura ao tópico (visualizadores de tópicos) serão solicitados a verificar a utilidade de tópicos específicos. Perguntas de comentários são feitas no **cartão de** resumo tópico para melhorar o valor do tópico e suas informações. Perguntas sobre a qualidade e a utilidade das sugestões de IA são apresentadas aos usuários uma de cada vez. As perguntas incluem:</br>

    1. Se a identificação do tópico na página do SharePoint foi útil. Há uma oportunidade de remover o destaque se ele não for preciso ou útil. Se pessoas suficientes indicarem que um tópico não foi identificado corretamente em uma página específica, esse destaque será removido para todos os usuários. 

    2. Se o tópico sugerido é valioso para a organização. Se pessoas suficientes indicarem que o tópico sugerido é valioso, o tópico é confirmado automaticamente. Como alternativa, se o tópico sugerido não for valioso, o tópico será automaticamente rejeitado. O Gerenciador de Conhecimento pode observar essa atividade no exibição Gerenciar Tópicos.

    3. Se as sugestões de pessoas e recursos são úteis.

    4. Na home page da Central de Tópicos, você pode ver os tópicos em sua organização aos quais você tem uma conexão. Você pode optar por permanecer listado no tópico ou remover a si mesmo. Esse feedback é refletido para todos os que descobrirem este tópico. Consulte [Visão geral da central de](https://docs.microsoft.com/microsoft-365/knowledge/topic-center-overview) tópicos para obter mais detalhes sobre a home page da central de tópicos.

Mesmo com edições humanas, a IA procurará continuamente mais informações sobre tópicos e procurará verificação humana. Por exemplo, se a AI achar que você é uma pessoa que deve ser listada como especialista em um tópico, ela solicitará que você confirme isso. 


## <a name="see-also"></a>Confira também
