---
title: Gerenciar a descoberta de tópicos nos tópicos do Microsoft Viva
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Saiba como administrar a descoberta de tópicos nos tópicos do Microsoft Viva.
ms.openlocfilehash: 36b64433726479dc2a46c809ae9504c6f12f4ab8
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107751"
---
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a>Gerenciar a descoberta de tópicos nos tópicos do Microsoft Viva

Você pode gerenciar as configurações de descoberta de tópicos no [centro de administração do Microsoft 365.](https://admin.microsoft.com) Você deve ser um administrador global ou administrador do SharePoint para executar essas tarefas.

## <a name="to-access-topics-management-settings"></a>Para acessar as configurações de gerenciamento de tópicos:

1. No centro de administração do Microsoft 365, clique em **Configurações** e, em seguida, **nas configurações da organização.**
2. Na guia **Serviços,** clique em Experiências **de Tópico.**

    ![Conectar as pessoas ao conhecimento](../media/admin-org-knowledge-options-completed.png) 

3. Selecione a **guia Descoberta de** Tópico. Consulte as seções a seguir para obter informações sobre cada configuração.

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a>Selecionar fontes de tópicos do SharePoint

Você pode alterar os sites do SharePoint em sua organização que serão rastreados para tópicos.

Se você quiser incluir ou excluir uma lista específica de sites, poderá usar o seguinte modelo .csv:

``` csv
Site name,URL
```

Se você adicionar sites usando o se picker de sites, eles serão adicionados à lista de sites existente para incluir ou excluir. Se você carregar um arquivo .csv, ele substituirá qualquer lista existente. Se você incluiu ou excluiu sites específicos anteriormente, baixe a lista como um arquivo .csv, faça alterações e carregue a nova lista.

Para escolher sites para descoberta de tópicos

1. Na guia **Descoberta de Tópico,** em **Selecionar fontes de tópicos do SharePoint,** selecione **Editar**.
2. Na página **Selecionar fontes de tópicos do SharePoint,** selecione quais sites do SharePoint serão rastreados como fontes para seus tópicos durante a descoberta. Isso inclui:
    - **Todos os sites:** todos os sites do SharePoint em seu locatário. Isso captura sites atuais e futuros.
    - **Todos, exceto sites selecionados:** digite os nomes dos sites que você deseja excluir.  Você também pode carregar uma lista de sites que deseja excluir da descoberta. Os sites criados no futuro serão incluídos como fontes para descoberta de tópicos. 
    - **Somente sites selecionados:** digite os nomes dos sites que você deseja incluir. Você também pode carregar uma lista de sites. Os sites criados no futuro não serão incluídos como fontes para descoberta de tópicos.
    - **Nenhum site:** os tópicos não serão gerados automaticamente ou atualizados com o conteúdo do SharePoint. Os tópicos existentes permanecem no centro de tópicos.

    ![Captura de tela da interface do usuário de fontes de tópicos do SharePoint](../media/k-manage-select-topic-source.png)
   
3. Clique em **Salvar**.

## <a name="exclude-topics-by-name"></a>Excluir tópicos por nome

Você pode excluir tópicos da descoberta carregando uma lista usando um arquivo .csv. Se você excluiu tópicos anteriormente, poderá baixar o .csv, fazer alterações e carregar novamente.

1. On the **Topic discovery** tab, under **Exclude topics**, select **Edit**.
2. Clique **em Excluir tópicos por nome.**
3. Se você precisar criar uma lista, baixe o modelo .csv e adicione os tópicos que deseja excluir (consulte Trabalhando com o modelo *.csv* abaixo). Quando o arquivo estiver pronto, clique **em Procurar** e carregue o arquivo. Se houver uma lista existente, você poderá baixar o .csv que contém a lista.
4. Clique em **Salvar**.

    ![Captura de tela da interface do usuário de tópicos excluídos](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a>Trabalhando com o modelo .csv

Você pode copiar o modelo csv abaixo:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

No modelo CSV, insira as seguintes informações sobre os tópicos que você deseja excluir:

- **Nome:** digite o nome do tópico que você deseja excluir. Há duas maneiras de fazer isso:
    - Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).
    - Parciais: você pode excluir todos os tópicos que têm uma palavra específica.  Por exemplo, *o arco* excluirá  todos os tópicos com o arco de palavras nele, como arco *círculo,* arco *de Arc arc arc ou* arco *de treinamento.* Observe que ele não excluirá tópicos nos quais o texto é incluído como parte de uma palavra, *como* Arquitetura .
- **Significa (opcional)**: se você quiser excluir um acrônimo, digite as palavras que o acrônimo significa.
- **MatchType-Exact/Partial**: digite se o nome digitado foi um *tipo de* combinação exato *ou* parcial.

    ![Excluir tópicos no modelo CSV](../media/exclude-topics-csv.png) 

## <a name="see-also"></a>Confira também

[Gerenciar visibilidade do tópico no Microsoft 365](topic-experiences-knowledge-rules.md)

[Gerenciar permissões de tópico no Microsoft 365](topic-experiences-user-permissions.md)

[Alterar o nome do centro de tópicos no Microsoft 365](topic-experiences-administration.md)
