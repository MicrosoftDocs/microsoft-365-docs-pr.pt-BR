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
- m365initiative-topics
localization_priority: None
ms.openlocfilehash: 435544de1016552c6ce3d39c73f7127223f36331
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107703"
---
# <a name="microsoft-viva-topics-discovery-and-curation"></a>Descoberta e cura de tópicos do Microsoft Viva 

Os Tópicos do Viva organizam informações de conhecimento em seu ambiente do Microsoft 365. Todos já vimos a leitura por meio de documentos e páginas de site em que encontramos termos com os quais não estamos familiarizados. Muitas vezes paramos o que estamos fazendo para gastar pouco tempo procurando por mais informações.

Os tópicos do Viva usam o Microsoft Graph e a IA para **identificar tópicos** em sua organização.  Um tópico é uma frase ou termo que tem um significado específico para a organização e tem recursos relacionados a ela que podem ajudar as pessoas a entender o que são e encontrar mais informações sobre ele. Há vários tipos diferentes de tópicos que serão importantes para sua organização. Inicialmente, os seguintes tipos de tópicos podem ser identificados:
- Project
- Evento
- Organização
- Localização
- Produto
- Trabalho criativo
- Campo de estudo

A IA identifica pessoas e conteúdo conectado ao tópico e, se suficiente for descoberto, ele se tornará um tópico sugerido. Ele procura identificar as seguintes propriedades e exibi-las em uma página **de tópico:**
- Nomes alternativos e/ou acrônimos.
- Uma breve descrição do tópico.
- Pessoas que podem estar experientes sobre o tópico.
- Arquivos, páginas e sites relacionados ao tópico.

As propriedades são identificadas a partir dos arquivos e páginas que fazem parte das evidências para identificar o tópico. Nomes alternativos e acrônimos são origem desses arquivos e páginas. A breve descrição é origem desses arquivos e páginas ou da Internet por meio da Wikipédia. O arquivo de origem, a página ou o artigo da Wikipédia é referenciado junto com as propriedades sugeridas. As pessoas são sugeridas com base em suas contribuições ativas (por exemplo, edições) para os arquivos e páginas. Uma referência à quantidade de contribuições de uma pessoa específica fornece uma dica sobre por que a pessoa foi identificada. Arquivos, páginas e sites são classificados com base em se eles são centrais para o tópico, se eles podem dar uma visão geral ou introdução ao tópico. 

Nem todos os tópicos identificados serão úteis para sua organização. Ele pode não ter identificado nenhum dos nomes alternativos, descrições, pessoas ou conteúdo apropriados corretos. Portanto, a capacidade de adicionar tópicos que não são identificados, manter os tópicos sugeridos e os tópicos de cura é fundamental para melhorar a qualidade dos tópicos que podem ser descobertos em sua organização.

Em seguida, os tópicos do Viva, quando o contexto for apropriado, sugerirão que esses tópicos sejam destacados em todas as páginas de site modernas do SharePoint em seu locatário. O tópico também pode ser referenciado diretamente na página do site moderno do SharePoint por um autor de página. Quando um usuário está curioso para saber mais sobre um tópico,  ele pode selecionar o tópico realçado para exibir um cartão de resumo de Tópico que fornece uma breve descrição. E se eles quiserem saber mais, eles podem selecionar um link **de** detalhes de tópico no resumo para abrir a página de tópico detalhada.

![Destaques de tópico](../media/knowledge-management/saturn.png) </br>

Além disso, os usuários também poderão encontrar tópicos por meio da Pesquisa da Microsoft.

## <a name="topic-curation-and-feedback"></a>Comentários e curação de tópicos

Os Tópicos do Viva são bem-vindos à contribuição humana para melhorar a qualidade de seus tópicos. Embora a IA inicialmente identifique e sugira tópicos, edições feitas manualmente ao conteúdo de colaboradores, tópicos adicionados manualmente, confirmação de usuários para conteúdo e propriedades descobertas por IA e comentários sobre a utilidade dos tópicos são essenciais.

- Os tópicos podem ser revisados pelos **gerentes de conhecimento** em sua organização. O gerente de conhecimento pode revisar os tópicos que eles têm permissão para ver. Na página Gerenciar Tópicos da Central de Tópicos, eles podem optar por confirmar tópicos gerados por IA ("tópicos sugeridos") como válidos, rejeitar tópicos para impedir que o conteúdo seja exibido como um tópico, criar tópicos que não foram descobertos pela IA ou identificar tópicos que possam se beneficiar de algumas edições por especialistas no assunto para serem mais úteis ou precisos. Para obter mais informações, [consulte Gerenciar tópicos na central de tópicos.](manage-topics.md)

- Você pode atribuir permissões criar e *editar tópicos* a qualquer um dos usuários licenciados para que eles possam fazer alterações em tópicos existentes ou criar novos tópicos. Isso permite que os usuários que têm conhecimento sobre o tópico atualizem diretamente a página de tópico para fazer correções ou adicionar informações adicionais. Eles também podem adicionar novos tópicos que a IA não conseguiu identificar. Se houver informações suficientes sobre esses tópicos adicionados manualmente e a IA for capaz de identificar esse tipo de tópico, sugestões adicionais da IA poderão aprimorar esses tópicos adicionados manualmente. Juntos, humanos e ia podem manter o conhecimento preciso ao longo do tempo e não ter esse resto em uma única pessoa. Para obter mais informações, [consulte Criar um novo tópico](https://docs.microsoft.com/microsoft-365/knowledge/create-a-topic) e editar um [tópico.](https://docs.microsoft.com/microsoft-365/knowledge/edit-a-topic)

- Mesmo os usuários que só têm acesso de leitura ao tópico (visualizadores de tópicos) serão solicitados a verificar a utilidade de tópicos específicos. Perguntas sobre comentários são feitas no **cartão de resumo** do tópico para melhorar o valor do tópico e suas informações. Perguntas sobre a qualidade e a utilidade das sugestões de IA são apresentadas aos usuários uma por vez. As perguntas incluem:</br>

    1. Se a identificação do tópico na página do SharePoint foi útil. Há uma oportunidade de remover o destaque se ele não for preciso ou útil. Se pessoas suficientes indicarem que um tópico não foi identificado corretamente em uma página específica, esse destaque eventualmente será removido para todos os usuários. 

    2. Se o tópico sugerido é valioso para a organização. Se pessoas suficientes indicarem que o tópico sugerido é valioso, o tópico será confirmado automaticamente. Como alternativa, se o tópico sugerido não for valioso, o tópico será automaticamente rejeitado. O Gerente de Conhecimento pode observar essa atividade na exibição Gerenciar Tópicos.

    3. Se as sugestões de pessoas e recursos são úteis.

    4. Na home page da Central de Tópicos, você pode ver os tópicos em sua organização aos quais você tem uma conexão. Você pode optar por permanecer listado no tópico ou remover você mesmo. Esses comentários se refletem em todos os usuários que descobrirem esse tópico. Consulte [a visão geral da central de](https://docs.microsoft.com/microsoft-365/knowledge/topic-center-overview) tópicos para obter mais detalhes sobre a home page da central de tópicos.

Mesmo com edições humanas, a IA procurará continuamente mais informações sobre tópicos e procurará por verificação humana. Por exemplo, se a IA achar que você é uma pessoa que deve ser listada como um especialista em um tópico, ele solicitará que você confirme isso. 


## <a name="see-also"></a>Confira também
