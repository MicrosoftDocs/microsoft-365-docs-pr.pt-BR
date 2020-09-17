---
title: 'Configurar o gerenciamento de conhecimento (versão prévia) '
description: Como configurar o gerenciamento de conhecimento.
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 6f5d014a8f401d9c3489eabb849b9d666444e6aa
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948145"
---
# <a name="set-up-knowledge-management-preview"></a>Configurar o gerenciamento de conhecimento (versão prévia)

> [!Note] 
> O conteúdo deste artigo é para a visualização privada do Project Cortex. [Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).

Você pode usar o centro de administração do Microsoft 365 para configurar e configurar o [Gerenciamento de conhecimento](knowledge-management-overview.md). 

> [!Important]
> É importante planejar a melhor maneira de configurar e configurar o gerenciamento de conhecimento em seu ambiente. Por exemplo, você precisará fazer considerações sobre o seguinte:
- Quais sites do SharePoint você deseja analisar os tópicos.
- Para quais usuários você deseja tornar os tópicos visíveis.
- Quais usuários você deseja dar permissões para gerenciar tópicos no centro de tópicos.
- Quais usuários você deseja dar permissões para criar ou editar tópicos no centro de tópicos.
- Que nome você deseja dar à sua central de tópicos.

> [!Note]
> Você pode achar útil criar grupos de segurança para atribuir aos usuários as permissões necessárias para exibir tópicos, gerenciar tópico e criar e editar tópicos.

Um administrador também pode [fazer alterações nas configurações selecionadas a qualquer momento após a configuração](manage-knowledge-network.md) , por meio das configurações de gerenciamento de conhecimento no centro de administração do Microsoft 365.

## <a name="requirements"></a>Requirements 
Você deve ter permissões de administrador global ou administrador do SharePoint para poder acessar o centro de administração do Microsoft 365 e configurar tarefas de conhecimento organizacional.

## <a name="set-up-your-knowledge-network"></a>Configurar sua rede de conhecimento

Configurar sua rede de conhecimento orienta você por meio do seguinte:

- Descoberta de tópico: selecionar fontes e tópicos de tópico para excluir da descoberta.
- Visibilidade do tópico: selecionar quem pode exibir tópicos como destaques, nas páginas de pesquisa e tópico.
- Permissões de tópico: selecionar quem pode criar, editar e gerenciar tópicos.
- Centro de tópicos: Crie seu centro de tópicos.
- Revisão: Verifique e aplique suas configurações.

Para configurar sua rede de conhecimento:

1. No centro de administração do Microsoft 365 (admin.microsoft.com), selecione **configuração**e, em seguida, exiba a seção de **conhecimento organizacional** .
2. Na seção **conhecimento organizacional** , clique em **conectar pessoas a conhecimento**.<br/>

    ![Conectar pessoas a conhecimento](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. Na página **conectar pessoas a conhecimento** **, clique em introdução para** orientá-lo no processo de instalação.<br/>

    ![Introdução](../media/content-understanding/k-get-started.png) </br>

4. Na página **escolha como a rede de conhecimento pode encontrar tópicos** , você configurará a descoberta de tópicos. Na seção **selecionar fontes de tópicos do SharePoint** , selecione quais sites do SharePoint serão rastreados como fontes para seus tópicos durante a descoberta. Isso inclui:</br>
    a. **Todos os sites**: todos os sites do SharePoint em seu locatário. Isso captura sites atuais e futuros.</br>
    b. **Todos, exceto sites selecionados**: digite os nomes dos sites que você deseja excluir.  Você também pode carregar uma lista de sites que deseja recusar da descoberta. Os sites criados no futuro serão incluídos como fontes para descoberta de tópicos. </br>
    c. **Somente sites selecionados**: digite os nomes dos sites que você deseja incluir. Você também pode carregar uma lista de sites. Os sites criados no futuro não serão incluídos como fontes para descoberta de tópicos. </br>

    ![Escolher como localizar tópicos](../media/content-understanding/ksetup1.png) </br>
   
5. Na seção **excluir tópicos por nome** , você pode optar por incluir nomes de tópicos que não deseja que estejam nos resultados detectados. Use essa configuração para impedir que tópicos confidenciais sejam incluídos como parte da rede de conhecimento. As opções incluem:</br>
    a. **Não excluir nenhum tópico** </br>
    b. **Excluir tópicos por nome**: se você tiver tópicos que não deseja mostrar aos usuários como parte da rede de conhecimento.</br>

    ![Excluir tópicos](../media/content-understanding/topics-excluded-by-name.png) </br>

    #### <a name="how-to-exclude-topics-by-name"></a>Como excluir tópicos por nome    

    Se você precisar excluir tópicos, depois de selecionar **excluir tópicos por nome**, selecione **baixar o modelo. csv**. Use o Excel. Modelo CSV para incluir uma lista de tópicos que você deseja excluir dos resultados da descoberta.

    ![Excluir tópicos no modelo CSV](../media/content-understanding/csv1.png) </br>

    No modelo CSV, insira as seguintes informações sobre os tópicos que você deseja excluir:

    - **Name**: digite o nome do tópico que você deseja excluir. Há duas maneiras de fazer isso:</br>
        - Correspondência exata: você pode incluir o nome exato ou o acrônimo (por exemplo, *contoso* ou *ATL*).</br>
        - Correspondência parcial: você pode excluir todos os tópicos que possuem uma palavra específica.  Por exemplo, o *arco* excluirá todos os tópicos com a palavra *arco* nele, como *círculo de arco*, solda de arco de *plasma*ou arco de *treinamento*. Observe que ele não excluirá tópicos nos quais o texto está incluído como parte de uma palavra, como *arquitetura*.</br>
    - **Expansão (opcional)**: se você deseja excluir um acrônimo, digite as palavras que o acrônimo significa.</br>
    - **MatchType-Exact/partial**: digite se o nome inserido foi um tipo de correspondência *exata* ou *parcial* .</br>

    Depois de concluir e salvar o arquivo de modelo CSV, selecione **procurar** para localizá-lo e selecioná-lo.
    
    Selecione **Avançar**.</br>

6. Na página **quem pode ver os tópicos e onde eles podem vê-los** , você configurará a visibilidade do tópico. Na configuração **quem pode ver os tópicos da configuração de rede de conhecimento** , você escolhe quem terá acesso aos detalhes do tópico, como tópicos realçados, cartões de tópicos, respostas de tópicos em pesquisa e páginas de tópicos. Você pode selecionar:</br>
    a. **Todos em sua organização**</br>
    b. **Apenas pessoas ou grupos de segurança selecionados**</br>
    c. **Ninguém**</br>

    ![Quem pode ver os tópicos](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > Embora essa configuração permita que você selecione qualquer usuário em sua organização, somente os usuários que têm licenças de gerenciamento de conhecimento atribuídas poderão exibir tópicos. 

7. Na página **permissões para gerenciamento de tópicos** , escolha quem poderá criar, editar ou gerenciar tópicos. Na seção **quem pode criar e editar tópicos** , você pode selecionar:</br>
    a. **Todos em sua organização**</br>
    b. **Apenas pessoas ou grupos de segurança selecionados**</br>
8. Na seção **quem pode gerenciar tópicos** , você pode selecionar:</br>
    a. **Todos em sua organização**</br>
    b. **Pessoas ou grupos de segurança selecionados**</br>

    ![Permissões para gerenciamento de tópicos](../media/content-understanding/ksetup3.png) </br>

    Selecione **Avançar**.</br>
9. Na página **criar centro de tópicos** , você pode criar seu site do centro de tópicos no qual as páginas de tópicos podem ser exibidas e os tópicos podem ser gerenciados.  Na caixa **nome da central de tópicos** , digite um nome para o seu centro de tópico. Opcionalmente, você pode digitar uma descrição curta na caixa **Descrição do site** . </br>

Selecione **Avançar**.</br>

   ![Criar centro de conhecimento](../media/content-understanding/ksetup4.png) </br> 

10. Na página **revisão e término** , você pode examinar a configuração selecionada e optar por fazer alterações. Se estiver satisfeito com suas seleções, selecione **Ativar**.

    ![Concluir e revisar](../media/content-understanding/ksetup5.png) </br> 

11. A página **da rede de conhecimento ativada** será exibida, confirmando que o sistema agora vai começar a analisar os sites selecionados para tópicos e criar o site do centro de conhecimento. Selecione **Concluído**.</br>

    ![Activated](../media/content-understanding/ksetup6.png) </br> 

12. Você retornará à página **conectar pessoas para o conhecimento** . Nessa página, você pode selecionar **gerenciar** para fazer quaisquer alterações nas suas definições de configuração. 

    ![Configurações aplicadas](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> Após a instalação, um administrador pode [fazer alterações nas configurações de gerenciamento de conhecimento selecionadas](manage-knowledge-network.md) a qualquer momento, retornando a essa página.


## <a name="see-also"></a>Confira também



  






