---
title: Gerenciar a descoberta de tópicos em Tópicos do Microsoft Viva
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Saiba como administrar a descoberta de tópicos em Tópicos do Microsoft Viva.
ms.openlocfilehash: 53e304dc69ccf2ca6fe01d29f0997c539406b0fe
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768969"
---
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a>Gerenciar a descoberta de tópicos em Tópicos do Microsoft Viva

Você pode gerenciar as configurações de descoberta de tópicos no Centro de administração [do Microsoft 365.](https://admin.microsoft.com) Você deve ser um administrador global ou administrador do SharePoint para executar essas tarefas.

## <a name="to-access-topics-management-settings"></a>Para acessar as configurações de gerenciamento de tópicos:

1. No Centro de administração do Microsoft 365, clique **em Configurações** e em **Configurações de organização.**
2. Na guia **Serviços,** clique em **Experiências de tópico.**

    ![Conectar pessoas ao conhecimento](../media/admin-org-knowledge-options-completed.png) 

3. Selecione a **guia Descoberta de** tópicos. Consulte as seções a seguir para obter informações sobre cada configuração.

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a>Selecionar fontes de tópicos do SharePoint

Você pode alterar os sites do SharePoint em sua organização que serão rastreados para tópicos.

Se quiser incluir ou excluir uma lista específica de sites, use o seguinte modelo .csv:

``` csv
Site name,URL
```

Se você adicionar sites usando o se picker de sites, eles serão adicionados à lista existente de sites para incluir ou excluir. Se você carregar um arquivo .csv, ele substituirá qualquer lista existente. Se você tiver incluído ou excluído sites específicos anteriormente, baixe a lista como um arquivo .csv, faça alterações e carregue a nova lista.

Para escolher sites para descoberta de tópicos

1. Na guia **Descoberta de** tópicos, em Selecionar fontes **de tópicos do SharePoint,** selecione **Editar**.
2. Na página **Selecionar fontes de tópicos do SharePoint,** selecione quais sites do SharePoint serão rastreados como fontes para seus tópicos durante a descoberta. Isso inclui:
    - **Todos os sites**: todos os sites do SharePoint em seu locatário. Isso captura sites atuais e futuros.
    - **Todos, exceto sites selecionados:** Digite os nomes dos sites que você deseja excluir.  Você também pode carregar uma lista de sites que deseja excluir da descoberta. Os sites criados no futuro serão incluídos como fontes para descoberta de tópicos. 
    - **Somente sites selecionados**: Digite os nomes dos sites que você deseja incluir. Você também pode carregar uma lista de sites. Os sites criados no futuro não serão incluídos como fontes para descoberta de tópicos.
    - **Nenhum site**: os tópicos não serão gerados ou atualizados automaticamente com o conteúdo do SharePoint. Os tópicos existentes permanecem no centro de tópicos.

    ![Captura de tela da interface do usuário de fontes de tópicos do SharePoint](../media/k-manage-select-topic-source.png)
   
3. Clique em **Salvar**.

## <a name="exclude-topics-by-name"></a>Excluir tópicos por nome

Você pode excluir tópicos da descoberta carregando uma lista usando um arquivo .csv. Se você tiver excluído tópicos anteriormente, poderá baixar o .csv, fazer alterações e carregar novamente.

1. Na guia **Descoberta de** tópicos, em **Excluir tópicos,** selecione **Editar**.
2. Clique **em Excluir tópicos pelo nome**.
3. Se você precisar criar uma lista, baixe o modelo .csv e adicione os tópicos que deseja excluir (consulte Trabalhando com o modelo *.csv* abaixo). Quando o arquivo estiver pronto, clique em **Procurar** e carregue o arquivo. Se houver uma lista existente, você poderá baixar o .csv que contém a lista.
4. Clique em **Salvar**.

    ![Captura de tela da interface do usuário de tópicos de exclusão](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a>Trabalhando com o modelo .csv

Você pode copiar o modelo csv abaixo:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

No modelo CSV, insira as seguintes informações sobre os tópicos que você deseja excluir:

- **Nome**: digite o nome do tópico que você deseja excluir. Há duas maneiras de fazer isso:
    - Match exato: Você pode excluir o nome exato ou acrônimo (por exemplo, *Contoso* ou *ATL*).
    - Match parcial: você pode excluir todos os tópicos que tenham uma palavra específica nele.  Por exemplo, *o arco* excluirá  todos os tópicos com o arco de palavra nele, como círculo de *arco,* *soldagem* de arco de plasma ou arco *treinamento*. Observe que ele não excluirá tópicos nos quais o texto é incluído como parte de uma palavra, como *Arquitetura*.
- **Significa (opcional)**: Se você quiser excluir um acrônimo, digite as palavras que o acrônimo representa.
- **MatchType-Exact/Partial**: Digite se o nome inserido foi *um tipo de* combinação exato *ou* parcial.

    ![Excluir tópicos no modelo CSV](../media/exclude-topics-csv.png) 

## <a name="see-also"></a>Confira também

[Gerenciar visibilidade de tópicos no Microsoft 365](topic-experiences-knowledge-rules.md)

[Gerenciar permissões de tópico no Microsoft 365](topic-experiences-user-permissions.md)

[Alterar o nome do centro de tópicos no Microsoft 365](topic-experiences-administration.md)
