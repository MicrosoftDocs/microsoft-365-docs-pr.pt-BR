---
title: 'Trabalhar com tópicos no centro de tópicos (versão prévia) '
description: Como trabalhar com tópicos no centro de tópicos.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 82a1b1990f464a892b8216caa26e0422b093bf37
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948049"
---
# <a name="work-with-topics-in-the-topic-center-preview"></a>Trabalhar com tópicos no centro de tópicos (versão prévia)

> [!Note] 
> O conteúdo deste artigo é para a visualização privada do Project Cortex. [Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).


No centro de tópicos, um gerente de conhecimento pode examinar os tópicos que foram extraídos e descobertos nos locais de origem do SharePoint que você especificou e pode confirmá-los ou rejeitá-los. Um gerente de conhecimento também pode criar e publicar novas páginas de tópico, se uma não foi encontrada no tópico Discovery, ou editar as existentes, caso precisem ser atualizadas.

## <a name="requirements"></a>Requirements

Para trabalhar no centro de tópicos, você precisa ter as permissões necessárias. Seu administrador pode adicionar você durante [a configuração do gerenciamento de conhecimento](set-up-knowledge-network.md)ou novos usuários podem ser [adicionados posteriormente](give-user-permissions-to-the-topic-center.md).

Os usuários do centro de tópicos podem receber dois conjuntos de permissões:

- Criar e editar tópicos: criar novos tópicos ou atualizar conteúdo do tópico, como descrição, documentos e pessoas associadas
- Gerenciar tópicos: Use o painel de gerenciamento de tópicos para analisar os tópicos em toda a organização. Os usuários podem executar ações como os tópicos confirmar e rejeitar


## <a name="review-unconfirmed-topics"></a>Analisar tópicos não confirmados

Na home page do centro de tópicos, os tópicos que foram descobertos em seus locais de origem do SharePoint especificados serão listados na guia não **confirmado** . Um usuário com permissões para gerenciar tópicos pode revisar os tópicos não confirmados e optar por confirmá-los ou rejeitá-los.


Para revisar um tópico não confirmado:

1. Na guia não **confirmada** , selecione o tópico para abrir a página de tópico.</br>

2. Na página tópico, revise a página de tópico e selecione **Editar** se precisar fazer qualquer alteração na página.
3. Na home page do centro de conhecimento, para o tópico selecionado, você pode:</br>
    a. Selecione a opção para confirmar que você deseja manter o tópico.</br>
    b. Selecione o **x** se você quiser rejeitar o tópico.</br>

    Os tópicos confirmados serão removidos da lista não **confirmada** e agora serão exibidos na guia **confirmado** .</br>

    Os tópicos rejeitados serão removidos da lista não **confirmada** e agora serão exibidos na guia **rejeitada ou excluída** .</br>
    
   
## <a name="create-a-new-topic"></a>Criar um novo tópico

Um usuário com permissões criar ou editar tópico pode criar um novo tópico, se necessário. Talvez seja necessário fazer isso se o tópico não foi descoberto por meio de descoberta ou se a tecnologia AI não encontrou evidências suficientes para estabelecer um tópico.

Para criar um novo tópico:
1. Na página central de tópicos, selecione **novo**e, em seguida, selecione **página de tópico**.</br>

    ![Novo tópico](../media/content-understanding/k-new-topic.png) </br>

2. Na página novo tópico, você pode preencher as informações sobre o novo modelo de tópico:</br>
    a. Na seção **nomear este tópico** , digite o nome do novo tópico.</br>
    b. Na seção **nomes alternativos** , digite nomes ou acrônimos que também são usados para referir-se ao tópico.</br>
    c. Na seção **Descrição curta** , digite uma ou duas sentenças descrição do tópico. Este texto será usado para o cartão de tópico associado.</br>
    d. Na seção **pessoas** , digite os nomes dos especialistas no assunto do tópico.</br>
    e. Na seção **arquivos e páginas** , selecione **Adicionar** e, na próxima página, você pode selecionar arquivos associados do onedrive ou páginas do SharePoint Online.</br>
    f. Na seção **sites** , selecione **Adicionar**. No painel  **sites** exibido, selecione os sites associados ao tópico.</br>

    ![Nova página de tópico](../media/content-understanding/k-new-topic-page.png) </br>
3. Se você precisar adicionar outros componentes à página, como texto, imagens, WebParts, links, etc., selecione o ícone de tela no meio da página para localizar e adicioná-los.
    ![Adicionar itens à página](../media/content-understanding/static-icon.png) </br> 

4. Quando terminar, selecione **publicar** para publicar a página de tópico. As páginas de tópicos publicadas serão exibidas na guia **páginas** .

> [!Note] 
> A página do novo tópico é formada por Web Parts que são compatíveis com a *rede de conhecimento*. Isso significa que, como o AI coleta mais informações sobre o tópico, as informações nessas Web Parts serão atualizadas com sugestões para tornar a página mais útil para os usuários.


## <a name="edit-an-existing-topic-page"></a>Editar uma página de tópico existente

As páginas de tópico existentes podem ser encontradas na página **páginas** . 

1. Na página central de tópicos, selecione **páginas**.</br>
2. Na página **páginas** , você verá uma lista de páginas de tópicos. Use a caixa de pesquisa para localizar a página de tópico que você deseja atualizar. Clique no nome da página de tópico que você deseja editar.</br>
3. Na página tópico, selecione **Editar**. </br>
4. Faça as alterações necessárias para a página. Isso inclui atualizações para os seguintes campos:</br>
    a. Nomes alternativos</br>
    b. Descrição</br>
    c. Pessoas</br>
    d. Arquivos e páginas</br>
    e. Sites</br>
    f. Você também pode adicionar itens estáticos à página, como texto, imagens ou link, selecionando o ícone de tela.</br>

5. Selecione **republicar** para salvar suas alterações.

## <a name="see-also"></a>Confira também



  






