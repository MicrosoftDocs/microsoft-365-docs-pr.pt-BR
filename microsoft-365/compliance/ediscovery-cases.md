---
title: Gerenciar ocorrências de Descoberta Eletrônica no Centro de Conformidade e Segurança
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 8dd335ab-29d0-41c3-8dd8-9f7c7481e60c
description: Use o centro de conformidade de & de segurança para criar e gerenciar casos de descoberta eletrônica em sua organização. Você pode atribuir Membros ao caso, colocar os locais de conteúdo em espera, executar pesquisas de conteúdo associadas ao caso e exportar os resultados da pesquisa. Você também pode preparar dados de caso para análise adicional na descoberta eletrônica avançada do Office 365.
ms.openlocfilehash: 6cc0cb0a709463be0e624162555dd221564b4dd3
ms.sourcegitcommit: 570ad1c7c334476ecec00dc355dfe52e8c2bb87b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2020
ms.locfileid: "41862101"
---
# <a name="manage-ediscovery-cases-in-the-security--compliance-center"></a>Gerenciar ocorrências de Descoberta Eletrônica no Centro de Conformidade e Segurança

Você pode usar casos de descoberta eletrônica no centro de conformidade no Office 365 e no Microsoft 365 para controlar quem pode criar, acessar e gerenciar casos de descoberta eletrônica em sua organização. Se sua organização tiver uma assinatura do Office 365 e5, você também poderá usar casos de descoberta eletrônica para analisar os resultados da pesquisa usando a descoberta eletrônica avançada do Office 365.
  
Uma ocorrência de Descoberta Eletrônica permite a você adicionar membros a uma ocorrência, controlar que tipos de ações os membros dessa ocorrência específica podem realizar, colocar em retenção locais de conteúdo relevantes para um caso jurídico e associar várias Pesquisas de Conteúdo com uma única ocorrência. Você também pode exportar os resultados de qualquer pesquisa de conteúdo associada a um caso ou preparar resultados de pesquisa para análise na descoberta eletrônica avançada. As ocorrências de Descoberta Eletrônica são uma boa maneira de limitar quem tem acesso às Pesquisas de Conteúdo e aos resultados da pesquisa de um caso jurídico específico na sua organização.
  
Use o fluxo de trabalho a seguir para configurar e usar casos de descoberta eletrônica no centro de conformidade e segurança & e descoberta eletrônica avançada.

[Step 1: Assign eDiscovery permissions to potential case members](#step-1-assign-ediscovery-permissions-to-potential-case-members)

[Etapa 2: criar um novo caso](#step-2-create-a-new-case)

[Etapa 3: adicionar membros a uma ocorrência](#step-3-add-members-to-a-case)

[Etapa 4: colocar os locais de conteúdo em espera](#step-4-place-content-locations-on-hold)

[Etapa 5: criar e executar uma pesquisa de conteúdo associada a uma ocorrência](#step-5-create-and-run-a-content-search-associated-with-a-case)

[Etapa 6: exportar os resultados de uma pesquisa de conteúdo associada a uma ocorrência](#step-6-export-the-results-of-a-content-search-associated-with-a-case)

[Etapa 7: preparar resultados de pesquisa para descoberta eletrônica avançada](#step-7-prepare-search-results-for-advanced-ediscovery)

[Etapa 8: ir para o caso na descoberta eletrônica avançada](#step-8-go-to-the-case-in-advanced-ediscovery)

[Opcion Etapa 9: fechar uma ocorrência](#optional-step-9-close-a-case)

[Opcion Etapa 10: abrir novamente uma ocorrência fechada](#optional-step-10-re-open-a-closed-case)

[Mais informações](#more-information)
  
## <a name="step-1-assign-ediscovery-permissions-to-potential-case-members"></a>Etapa 1: atribuir permissões de Descoberta Eletrônica para possíveis membros da ocorrência

A primeira etapa é atribuir as permissões relacionadas à descoberta eletrônica apropriadas às pessoas para que você possa adicioná-las a um caso de descoberta eletrônica na etapa 2. Você precisa ser membro do grupo de função gerenciamento da organização (ou receber a função de gerenciamento de função) no centro de conformidade & segurança para atribuir permissões de descoberta eletrônica. A lista a seguir descreve os grupos de função relacionados à descoberta eletrônica no centro de conformidade de & de segurança. 
  
- **Revisor.** Esse grupo de função tem as permissões mais restritivas relacionadas a Descoberta Eletrônica. O principal objetivo desse grupo de função é permitir que os membros exibam e acessem dados de ocorrência no [Office 365 descoberta eletrônica avançada](office-365-advanced-ediscovery.md) (também conhecido como *descoberta eletrônica avançada v1*). Os membros desse grupo só podem ver e abrir a lista de casos na página **descoberta eletrônica** no centro de conformidade de & de segurança do qual eles são membros. Depois que o usuário acessa um caso no centro de segurança e conformidade, ele pode clicar em **alternar para descoberta eletrônica avançada** para acessar e analisar os dados do caso na descoberta eletrônica avançada. Eles não podem criar casos, adicionar membros a uma ocorrência, criar isenções, criar pesquisas, Visualizar resultados de pesquisa, exportar resultados de pesquisa ou preparar resultados para descoberta eletrônica avançada. 

   > [!NOTE]
   > No momento, os usuários que são membros do grupo de funções revisor não podem acessar dados na [descoberta eletrônica avançada no Microsoft 365](overview-ediscovery-20.md) (também conhecido como *descoberta eletrônica avançada v2*). Para adicionar membros a um caso na descoberta eletrônica avançada v2 para que eles possam revisar os dados do caso, um usuário deve ser membro do grupo de função Gerenciador de descoberta eletrônica.
    
- **Gerenciador de descoberta eletrônica.** Os membros deste grupo de função podem criar e gerenciar ocorrências de Descoberta Eletrônica. Eles podem adicionar e remover membros, colocar os locais de conteúdo em espera, criar e editar pesquisas de conteúdo associadas a uma ocorrência, exportar os resultados de uma pesquisa de conteúdo e preparar resultados de pesquisa para análise na descoberta eletrônica avançada. Há dois subgrupos nesse grupo de funções. A diferença entre esses subgrupos está no escopo.
    
  - **Gerenciador de descoberta eletrônica.** Pode exibir ou gerenciar ocorrências de Descoberta Eletrônica criadas por ele ou das quais ele seja membro. Se outro gerenciador de descoberta eletrônica criar uma ocorrência, mas não adicionar um segundo Gerenciador de descoberta eletrônica como membro desse caso, o segundo Gerenciador de descoberta eletrônica não poderá exibir ou abrir o caso na página **descoberta eletrônica** no centro de conformidade de segurança &. Os gerentes de descoberta eletrônica também podem acessar seus casos na descoberta eletrônica avançada para executar tarefas de análise. 
    
  - **Administrador de descoberta eletrônica *.** Pode executar todas as tarefas de gerenciamento de ocorrências que um Gerente de Descoberta Eletrônica pode fazer. Além disso, um Administrador de Descoberta Eletrônica pode:
    
    - Exibir todas as ocorrências listadas na página **Descoberta Eletrônica**. 
    
    - Gerencie qualquer caso na organização depois que eles se adicionarem como um membro do caso.
    
    - Acessar dados de caso na descoberta eletrônica avançada para qualquer caso na organização.
    
    Consulte a seção [More information](#more-information) para conhecer os motivos pelos quais convém ter um Administrador de Descoberta Eletrônica em sua organização. 
    
> [!IMPORTANT]
> Se uma pessoa não for membro de um destes grupos de função relacionados à descoberta eletrônica ou se não for um membro de um grupo de função atribuído à função revisor, você não poderá adicioná-los como um membro de uma ocorrência de descoberta eletrônica. 

Para obter mais informações sobre permissões de descoberta eletrônica, consulte [atribuir permissões de descoberta eletrônica](assign-ediscovery-permissions.md).
  
 **Para atribuir as permissões de Descoberta Eletrônica:**
  
1. Acesse [https://protection.office.com](https://protection.office.com).
    
2. Entre no Office 365 usando a sua conta corporativa ou de estudante.
    
3. No centro de conformidade & segurança, clique em **permissões**e siga um destes procedimentos com base nas permissões de descoberta eletrônica que você deseja atribuir.
    
    - Para atribuir permissões de revisor, selecione o grupo de função **revisor** e, em seguida, ao lado de **Membros**, clique em **Editar**. Clique **em escolher Membros**, **** clique em Editar ![, clique](media/ITPro-EAC-AddIcon.gif) em Adicionar ícone **Adicionar**, selecione o usuário que você deseja adicionar ao grupo de funções revisor e clique em **Adicionar**.
    
    - Para atribuir permissões de gerente de descoberta eletrônica, selecione o grupo de funções **Gerenciador de descoberta eletrônica** e, em seguida, ao lado de **Gerenciador de descoberta eletrônica**, clique em **Editar** Clique **em escolher o Gerenciador de descoberta eletrônica**, ![clique em](media/ITPro-EAC-AddIcon.gif) **Editar**, em Adicionar ícone * * Adicionar * *, selecione o usuário que você deseja adicionar como um Gerenciador de descoberta eletrônica e clique em **Adicionar**.
    
    - Para atribuir permissões de administrador de descoberta eletrônica, selecione o grupo de função **Gerenciador de descoberta eletrônica** e ao lado de **administrador de descoberta eletrônica**, clique em **Editar**. Clique em **escolher administrador de descoberta eletrônica**, em ![ **Editar**,](media/ITPro-EAC-AddIcon.gif) em Adicionar ícone **Adicionar**, selecione o usuário que você deseja adicionar como administrador de descoberta eletrônica e clique em **Adicionar**.
    
4. Depois de adicionar todos os usuários, clique em **concluído**, clique em **salvar** para salvar as alterações no grupo de função e, em seguida, clique em **Fechar**.

## <a name="step-2-create-a-new-case"></a>Etapa 2: criar um novo caso

A próxima etapa é criar uma ocorrência de descoberta eletrônica. Você deve ser membro do grupo de função Gerente de Descoberta Eletrônica para criar ocorrências de Descoberta Eletrônica. Conforme explicado anteriormente, depois de criar um caso no centro de conformidade com segurança &, você (e outros membros de caso) poderão acessar o mesmo caso na descoberta eletrônica avançada, se sua organização tiver uma assinatura do Office 365 e5.
  
1. Acesse [https://protection.office.com](https://protection.office.com).
    
2. Entre no Office 365 usando a sua conta corporativa ou de estudante.
    
3. No centro de conformidade & segurança, clique em **descoberta** ![eletrônica de **descoberta eletrônica** \> e, em seguida, clique em Adicionar ícone](media/ITPro-EAC-AddIcon.gif) **criar uma ocorrência**.
    
4. Na página **nova ocorrência** , dê um nome à caixa, digite uma descrição opcional e clique em **salvar**. O nome da ocorrência deve ser exclusivo em sua organização.
    
    ![Criar uma ocorrência](media/7f78f83b-1525-4c77-9888-4b6bda1e148d.png)
  
    O novo caso é exibido na lista de casos na página de **descoberta eletrônica** . Você pode passar o cursor do mouse sobre um nome de caso para exibir informações sobre o caso, incluindo o status da ocorrência (**ativa** ou **fechada**), a descrição do caso (que foi criada na etapa anterior) e quando o caso foi alterado por último e quem a alterou.
    
    > [!TIP]
    > Depois de criar um novo caso, você pode renomeá-lo a qualquer momento. Basta clicar no nome do caso na página de **descoberta eletrônica** . Na página **gerenciar este** submenu de caso, altere o nome exibido na caixa em **nome**e salve a alteração. 
  
## <a name="step-3-add-members-to-a-case"></a>Etapa 3: adicionar membros a uma ocorrência

Após criar uma ocorrência, a próxima etapa é adicionar membros à ocorrência. Como explicado anteriormente, somente usuários que são membros dos grupos de função revisor ou Gerenciador de descoberta eletrônica podem ser adicionados como membros da ocorrência. O Gerenciador de descoberta eletrônica que criou o caso é automaticamente adicionado como um membro.
  
1. No centro de conformidade & segurança **, clique em** \> **descoberta** eletrônica eletrônica para exibir a lista de casos em sua organização. 
    
2. Clique no nome do caso para o qual você deseja adicionar membros.
    
    A página **gerenciar esse** submenu de caso é exibida. 
    
    ![Gerenciar uma página de submenu de caso](media/11f35ceb-6c98-4580-a3bc-ad688e9c7af9.png)
  
3. Em **gerenciar Membros**, clique ![em Adicionar](media/ITPro-EAC-AddIcon.gif) ícone **Adicionar** para adicionar membros à ocorrência. 
    
    Você também pode optar por adicionar um grupo de funções ao caso. Em **gerenciar grupos de função**, ![clique em](media/ITPro-EAC-AddIcon.gif) adicionar ícone **Adicionar**.
    
    > [!NOTE]
    > Grupos de função controle quem pode atribuir membros a uma ocorrência de descoberta eletrônica. Isso significa que você só pode atribuir os grupos de função que você é membro de um caso.
    
4. Na lista de pessoas ou grupos de funções que podem ser adicionados como membros do caso, clique na caixa de seleção ao lado dos nomes das pessoas ou grupos de função que você deseja adicionar.
    
    > [!TIP]
    > Se você tiver uma lista grande de pessoas que podem ser adicionadas como membros, use a caixa **Pesquisar** para procurar uma pessoa específica na lista. 
  
5. Depois de selecionar as pessoas ou os grupos de funções a serem adicionados como membros do grupo, clique em **Adicionar**.
    
    Em **gerenciar este caso**, clique em **salvar** para salvar a nova lista de membros de caso. 
    
6. Clique em **salvar** para salvar a nova lista de membros de caso. 
  
## <a name="step-4-place-content-locations-on-hold"></a>Etapa 4: colocar os locais de conteúdo em espera

Você pode usar uma ocorrência de Descoberta Eletrônica para criar retenções e preservar conteúdo que possa ser relevante para a ocorrência. Você pode colocar uma retenção nas caixas de correio e nos sites do OneDrive for Business de pessoas que são responsáveis pelo caso. Você também pode colocar uma retenção na caixa de correio de grupo, site do SharePoint e no OneDrive for Business para um grupo do Office 365. Da mesma forma, você pode colocar uma retenção nas caixas de correio e nos sites associados ao Microsoft Teams ou aos grupos do Yammer. Quando você coloca os locais de conteúdo em espera, o conteúdo é mantido até que você remova o bloqueio do local de conteúdo ou até que você exclua a isenção.

> [!NOTE]
> Depois que você coloca um local de conteúdo em espera, leva até 24 horas para que a retenção entre em vigor. 
>   
Ao criar uma isenção, você tem as seguintes opções para fazer o escopo do conteúdo mantido nos locais de conteúdo especificado:
  
- Você cria uma retenção infinita onde todo o conteúdo é colocado em espera. Como alternativa, você pode criar uma isenção baseada em consulta, onde somente o conteúdo que corresponde a uma consulta de pesquisa é colocado em espera.
    
- Você pode especificar um intervalo de datas para armazenar somente o conteúdo que foi enviado, recebido ou criado dentro desse intervalo de datas. Como alternativa, você pode manter todo o conteúdo independentemente de quando ele foi enviado, recebido ou criado.
    
> [!NOTE]
> Você pode ter no máximo 10.000 políticas de retenção em todos os casos de descoberta eletrônica da sua organização. 
  
Para criar uma retenção para um caso de descoberta eletrônica:
  
1. No centro de conformidade & segurança **, clique em** \> **descoberta** eletrônica eletrônica para exibir a lista de casos em sua organização. 
    
2. Clique em **abrir** ao lado do caso para o qual você deseja criar as isenções. 
    
3. Na **Home** Page do caso, clique na guia **reter** . 
    
    ![Clique na guia reter](media/3fef2db4-36de-4517-a34d-82f47b82d9bf.png)
  
4. Na página **reter** , clique em ![adicionar ícone](media/ITPro-EAC-AddIcon.gif) **criar**.
    
5. Na página **nomear sua suspensão** , dê um nome à isenção. O nome da retenção deve ser exclusivo na sua organização. 
    
    ![Forneça um nome exclusivo para o controle](media/7e15ea63-abd1-4f14-a29c-7ecfb9571d2c.png)
  
6. Opcion Na caixa **Descrição** , adicione uma descrição da isenção. 
    
7. Clique em **Avançar**.
    
8. Escolha os locais de conteúdo que você deseja colocar em espera. Você pode colocar caixas de correio, sites e pastas públicas em espera.
    
    ![Escolher os locais de conteúdo para colocar em espera](media/a59e4265-9151-4dbf-913f-6a4ab8db06b4.png)
  
   a. **Email do Exchange** -clique em **escolher usuários, grupos ou equipes** e, em seguida, clique em **escolher usuários, grupos ou equipes** novamente. para especificar as caixas de correio a serem colocadas em espera. Use a caixa de pesquisa para localizar caixas de correio de usuários e grupos de distribuição (para colocar uma retenção nas caixas de correio dos membros do grupo) para colocar em espera. Você também pode colocar uma retenção na caixa de correio associada para uma equipe da Microsoft, um grupo do Yammer ou um grupo do Office 365. Marque a caixa de seleção usuário, grupo, equipe, clique em **escolher**e em **concluído**.
    
    > [!NOTE]
    > Ao clicar em **escolher usuários, grupos ou equipes** para especificar as caixas de correio que serão colocadas em espera, o seletor de caixa de correio exibido estará vazio. Isso foi desenvolvido para melhorar o desempenho. Para adicionar pessoas a esta lista, digite um nome (no mínimo 3 caracteres) na caixa de pesquisa. 

   b. **Sites do SharePoint** -clique em **escolher sites** e, em seguida, clique em **escolher sites** novamente para especificar o SharePoint e os sites do onedrive for Business para colocar em espera. Digite a URL de cada site que você deseja colocar em retenção. Você também pode adicionar a URL do site do SharePoint para uma equipe da Microsoft, um grupo do Yammer ou um grupo do Office 365. Clique em **escolher**e em **concluído**.
    
    Consulte a seção [mais informações](#more-information) para obter dicas sobre como colocar o Microsoft Teams, os grupos do Yammer e os grupos do Office 365 em espera. 
    
    > [!NOTE]
    > No caso raro em que o UPN (nome principal de usuário) de uma pessoa é alterado, a URL de sua conta do OneDrive também será alterada para incorporar o novo UPN. Se isso acontecer, você terá que modificar a retenção adicionando a nova URL do OneDrive do usuário e removendo a antiga. 
  
   c. **Pastas públicas do Exchange.** Mova o ![controle](media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) de alternância de alternância para a posição **All** para colocar todas as pastas públicas em sua organização do Exchange Online em espera. Você não pode escolher pastas públicas específicas para colocá-las em espera. Deixe a opção de alternância definida como **nenhuma** se você não quiser colocar uma retenção em pastas públicas.
    
9. Quando você terminar de adicionar locais de conteúdo à isenção, clique em **Avançar**.
    
10. Para criar uma retenção baseada em consulta com condições, conclua o seguinte. Caso contrário, clique em **Avançar**
    
    ![Criar uma retenção baseada em consulta com condições](media/d587b58e-d05c-4ac0-b0fe-09019e4f1063.png)
  
    
       a. Na caixa em **palavras-chave**, digite uma consulta de pesquisa na caixa para que apenas o conteúdo que atende aos critérios de pesquisa seja colocado em espera. Você pode especificar palavras-chave, propriedades de mensagem ou propriedades do documento, como nomes de arquivo. Você também pode usar consultas mais complexas que usam um operador Boolean, como **e**, **ou ou** **não**. Se você deixar a caixa de palavras-chave vazia, todo o conteúdo localizado nos locais de conteúdo especificado será colocado em espera.
    
    b. Clique ![em Adicionar](media/ITPro-EAC-AddIcon.gif) ícone **Adicionar condições** para adicionar uma ou mais condições para restringir a consulta de pesquisa para a isenção. Cada condição adiciona uma cláusula à consulta de pesquisa KQL que é criada e executada quando você cria a retenção. Por exemplo, você pode especificar um intervalo de datas para que os documentos de email ou de site criados dentro do intervalo de datas sejam colocados em espera. Uma condição está logicamente conectada à consulta de palavra-chave (especificada na caixa de palavra-chave) pelo operador **AND**. Isso significa que os itens precisam satisfazer a consulta de palavra-chave e a condição a ser colocada em espera.

    Para obter mais informações sobre como criar uma consulta de pesquisa e usar condições, consulte [keyword queries and Search Conditions for Content Search](keyword-queries-and-search-conditions.md).
    
11. Depois de configurar um bloqueio baseado em consulta, clique em **Avançar**.
    
12. Revise suas configurações e clique em **criar esta isenção**.
    
### <a name="hold-statistics"></a>Estatísticas de retenção

Após um tempo, as informações sobre a nova retenção são exibidas no painel de detalhes na página de **isenções** da isenção selecionada. Essas informações incluem o número de caixas de correio e sites em espera e estatísticas sobre o conteúdo que foi colocado em espera, como o número total e o tamanho de itens colocados em retenção e a última vez que as estatísticas de retenção foram calculadas. Essas estatísticas de isenção ajudam você a identificar quanto conteúdo relacionado à ocorrência de descoberta eletrônica está sendo mantido. 
  
![Estatísticas de retenção](media/575cfe0a-9210-4ae4-8df8-65665d66712e.png)
  
Tenha em mente as seguintes coisas em relação a estatísticas de retenção:
  
- O número total de itens em retenção indica o número de itens de todas as fontes de conteúdo que são colocadas em espera. Se você tiver criado uma retenção baseada em consulta, essa estatística indicará o número de itens que correspondem à consulta.
    
- O número de itens em retenção também inclui itens não indexados encontrados nos locais de conteúdo. Se você criar uma retenção baseada em consulta, todos os itens não indexados nos locais de conteúdo são colocados em espera. Isso inclui itens não indexados que não correspondem aos critérios de pesquisa de um bloqueio baseado em consulta e itens não indexados que podem ficar fora de uma condição de intervalo de datas. Isso é diferente do que acontece quando você executa uma pesquisa de conteúdo, na qual os itens não indexados que não correspondem à consulta de pesquisa ou são excluídos por uma condição de intervalo de datas não são incluídos nos resultados da pesquisa. Para obter mais informações sobre itens não indexados, confira [itens parcialmente indexados na pesquisa de conteúdo no Office 365](partially-indexed-items-in-content-search.md).
    
- Você pode obter as estatísticas de retenção mais recentes clicando em **atualizar estatísticas** para executar novamente uma estimativa de pesquisa que calcula o número atual de itens em retenção. Se necessário, clique em **Atualizar**![ícone](media/O365-MDM-Policy-RefreshIcon.gif) de atualização na barra de ferramentas para atualizar as estatísticas de retenção no painel de detalhes. 
    
- É normal para o número de itens em espera aumentar ao longo do tempo, pois os usuários cuja caixa de correio ou site está em espera geralmente estão enviando ou recebendo novas mensagens de email e criando novos documentos do SharePoint e do OneDrive for Business.
    
> [!NOTE]
> Se um site do SharePoint ou uma conta do OneDrive for movido para uma região diferente em um ambiente multigeográfico, as estatísticas desse site não serão incluídas nas estatísticas de retenção. No entanto, o conteúdo do site permanecerá em espera. Além disso, se um site for movido para uma região diferente, a URL exibida na retenção não será atualizada. Você terá que editar a isenção e atualizar a URL. 
  
## <a name="step-5-create-and-run-a-content-search-associated-with-a-case"></a>Etapa 5: criar e executar uma pesquisa de conteúdo associada a uma ocorrência

Depois de criar uma ocorrência de Descoberta Eletrônica e os responsáveis relacionados à ocorrência serem colocados em retenção, você poderá criar e executar uma ou mais Pesquisas de Conteúdo associadas à ocorrência. As pesquisas de conteúdo associadas a um caso não estão listadas na página de **pesquisa** no centro de conformidade & segurança. Isso significa que as pesquisas de conformidade associadas a uma ocorrência só podem ser acessadas por membros da ocorrência que também sejam membros do grupo de função Gerente de Descoberta Eletrônica. 
  
1. No centro de conformidade & segurança **, clique em** \> **descoberta** eletrônica eletrônica para exibir a lista de casos em sua organização. 
    
2. Clique em **abrir** ao lado do caso para o qual você deseja criar uma pesquisa de conteúdo. 
    
3. Na **Home** Page do caso, clique na guia **Pesquisar** . 
    
    ![Guia Pesquisar](media/2e15fe32-1a2e-4588-ad0b-5d96f77cece9.png)
  
4. Na página de **pesquisa** , clique ![em Adicionar](media/ITPro-EAC-AddIcon.gif) ícone **nova pesquisa**. 
    
5. Na página **Nova pesquisa**, você pode adicionar palavras-chave e condições para criar a consulta de pesquisa. 
    
    ![Nova pesquisa](media/0e9954e7-c0ea-4e05-820b-e4b81dc5f81d.png)
  
6. Você pode especificar palavras-chave, propriedades de mensagem, como datas de envio e recebimento, ou propriedades do documento, como nomes de arquivo ou a data em que um documento foi alterado pela última vez. Você pode usar consultas mais complexas que usam um operador Boolean, como **e**, **ou**, **não**, **Near**ou **ONEAR**. Você também pode procurar informações confidenciais (por exemplo, números de seguridade social) em documentos ou pesquisar documentos que foram compartilhados externamente. Se você deixar a caixa de palavras-chave vazia, todo o conteúdo localizado nos locais de conteúdo especificado será incluído nos resultados da pesquisa. 
    
7. Você pode clicar na caixa de seleção **Mostrar lista de palavras-chave** e a palavra-chave tipo a em cada linha. Se você fizer isso, as palavras-chave em cada linha serão conectadas pelo operador **or** na consulta de pesquisa criada. 
    
    ![Lista de palavras-chave](media/29cceb5d-2817-4fc4-b91a-ced1c5824a17.png)
  
    Por que usar a lista de palavras-chave? Para obter estatísticas que mostram quantos itens correspondem a cada palavra-chave. Isso ajudará a identificar rapidamente quais palavras-chave são as mais recentes. Também poderá usar uma frase de palavra-chave (entre parênteses) em uma linha. Para obter mais informações sobre as estatísticas de pesquisa, confira [Exibir estatísticas da palavra-chave para Resultados de Pesquisa de Conteúdo](view-keyword-statistics-for-content-search.md).
    
    Para obter mais informações sobre como usar a lista de palavras-chave, consulte [criando uma consulta de pesquisa](content-search.md#building-a-search-query).
    
8. Em **condições**, adicione condições a uma consulta de pesquisa para restringir uma pesquisa e retornar um conjunto mais refinado de resultados. Cada condição adiciona uma cláusula à consulta de pesquisa KQL que é criada e executada quando você inicia a pesquisa. Uma condição é logicamente conectada à consulta de palavra-chave (especificada na caixa de palavra-chave) pelo operador **AND**. Isso significa que os itens precisam atender à consulta de palavra-chave e à condição para serem incluídos nos resultados. É assim que as condições ajudam a restringir os resultados. 
    
    Para saber mais sobre como criar uma consulta de pesquisa e usar condições, confira [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).
    
9. Em **locais: locais em espera**, escolha os locais de conteúdo que você deseja pesquisar. Você pode pesquisar caixas de correio, sites e pastas públicas na mesma pesquisa.
    
    ![Locais, locais em espera](media/d56398aa-0b20-4500-8e26-494eab92a99f.png)
  
    - **Todos os locais** -Selecione essa opção para pesquisar todos os locais de conteúdo em sua organização. Ao selecionar essa opção, você pode optar por pesquisar todas as caixas de correio do Exchange (que inclui as caixas de correio de todos os grupos do Microsoft Teams, do Yammer e do Office 365), todos os sites do SharePoint e do OneDrive for Business (que inclui os sites para todos os Microsoft Teams, grupos do Yammer e grupos do Office 365) e todas as pastas públicas.
    
    - **Todos os locais em espera.** Selecione essa opção para pesquisar todos os locais de conteúdo que foram colocados em espera no caso. Se o caso contiver várias isenções, os locais de conteúdo de todas as isenções serão pesquisados quando você selecionar essa opção. Além disso, se um local de conteúdo foi colocado em um bloqueio baseado em consulta, somente os itens que estão em retenção serão pesquisados quando você executar a pesquisa de conteúdo que você está criando nesta etapa. Por exemplo, se um usuário foi colocado em um bloqueio de caso baseado em consulta que preserva os itens que foram enviados ou criados antes de uma data específica, somente esses itens seriam pesquisados usando os critérios de pesquisa da pesquisa de conteúdo. Isso é feito conectando-se à consulta de retenção de caso e à consulta de pesquisa de conteúdo por um operador **and** . Consulte a seção [mais informações](#more-information) no final deste artigo para obter mais detalhes sobre como pesquisar o conteúdo do caso. 
    
    - **Locais específicos.** Selecione essa opção para selecionar as caixas de correio e os sites que você deseja pesquisar. Quando você seleciona essa opção e clica em **Modificar**, uma lista de locais é exibida. Você pode optar por pesquisar qualquer um ou todos os usuários, grupos, equipes ou locais de sites.
    
      ![Selecionar locais específicos](media/97469b15-7be1-4aee-be27-f8343636152c.png)
  
      Você também pode optar por pesquisar todas as pastas públicas em sua organização, mas se você selecionar essa opção e pesquisar qualquer local de conteúdo em espera, qualquer consulta de um bloqueio de caso baseado em consulta não será aplicada à consulta de pesquisa. Em outras palavras, todo o conteúdo em um local é pesquisado, e não apenas o conteúdo que é preservado por um bloqueio de caso baseado em consulta.
    
      Você pode remover os locais de conteúdo do caso previamente preenchido ou adicionar novos. Se você escolher essa opção, também terá flexibilidade para pesquisar todos os locais de conteúdo de um serviço específico (como pesquisar todas as caixas de correio do Exchange) ou pode pesquisar locais de conteúdo específicos para um serviço. Você também pode escolher se deseja pesquisar as pastas públicas em sua organização.
    
      Lembre-se destes pontos ao adicionar locais de conteúdo para pesquisa:
    
      - Ao clicar em **escolher usuários, grupos ou equipes** para especificar as caixas de correio a serem pesquisadas, o seletor de caixa de correio exibido estará vazio. Isso foi desenvolvido para melhorar o desempenho. Para adicionar destinatários a essa lista, clique em **escolher usuários, grupos ou equipes**, digite um nome (no mínimo 3 caracteres) na caixa de pesquisa, marque a caixa de seleção ao lado do nome e clique em **escolher**. 
    
      - Você pode adicionar caixas de correio inativas, Microsoft Teams, grupos do Yammer, grupos do Office 365 e grupos de distribuição à lista de caixas de correio a serem pesquisadas. Não há suporte para grupos dinâmicos de distribuição. Se você adicionar o Microsoft Teams, os grupos do Yammer ou os grupos do Office 365, a caixa de correio de grupo ou equipe será pesquisada; as caixas de correio dos membros do grupo não são pesquisadas.
    
      - Para adicionar **sites, clique em escolher sites**, clique em **escolher sites** novamente e digite a URL de cada site que você deseja pesquisar. Você também pode adicionar a URL para o site do SharePoint para uma equipe da Microsoft, um grupo do Yammer ou um grupo do Office 365. 
    
10. Depois de selecionar os locais de conteúdo para pesquisa, clique em **concluído** e, em seguida, clique em **salvar**.
    
11. Na página **nova pesquisa** , clique em **salvar** e digite um nome para a pesquisa. As pesquisas de conteúdo associadas a uma ocorrência devem ter nomes exclusivos na sua organização do Office 365. 
    
12. Clique **em &amp; salvar executar** para salvar as configurações de pesquisa. 
    
13. Insira um nome exclusivo para a pesquisa e clique em **salvar** para iniciar a pesquisa. 
    
    A pesquisa começa. Após um tempo, uma estimativa dos resultados da pesquisa é exibida no painel de detalhes. A previsão inclui o tamanho total e o número de itens que correspondem aos critérios de pesquisa. A estimativa de pesquisa também inclui o número de itens não indexados nos locais de conteúdo que foram pesquisados. O número de itens não indexados que não atendem aos critérios de pesquisa será incluído nas estatísticas de pesquisa exibidas no painel de detalhes. Se um item não indexado corresponder à consulta de pesquisa (porque outras propriedades de mensagem ou de documento atendem aos critérios de pesquisa), ela não será incluída no número estimado de itens não indexados. Se um item não indexado for excluído pelos critérios de pesquisa, ele também não será incluído na estimativa de itens não indexados.
    
  Após a conclusão da pesquisa, você poderá visualizar os resultados. Se necessário, clique em **Atualizar**![ícone](media/O365-MDM-Policy-RefreshIcon.gif) de atualização para atualizar as informações no painel de detalhes. 
    
## <a name="step-6-export-the-results-of-a-content-search-associated-with-a-case"></a>Etapa 6: exportar os resultados de uma pesquisa de conteúdo associada a uma ocorrência

Após uma pesquisa ser executada com êxito, você pode exportar os resultados da pesquisa. Quando você exporta os resultados da pesquisa, os itens da caixa de correio são baixados em arquivos PST ou como mensagens individuais. Quando você exporta conteúdo de sites do SharePoint e do OneDrive for Business, cópias de documentos nativos do Office e outros documentos são exportadas. Um arquivo de manifesto (em formato XML) que contém informações sobre cada resultado de pesquisa também é exportado.
  
Você pode exportar os resultados de uma [única pesquisa associada a um caso](#export-the-results-of-a-single-search-associated-with-a-case) ou pode exportar os resultados de [várias pesquisas associadas a um caso](#export-the-results-of-multiple-searches-associated-with-a-case).
  
### <a name="export-the-results-of-a-single-search-associated-with-a-case"></a>Exportar os resultados de uma única pesquisa associada a uma ocorrência

1. No centro de conformidade & segurança **, clique em** \> **descoberta** eletrônica eletrônica para exibir a lista de casos em sua organização. 
    
2. Clique em **abrir** ao lado do caso para o qual você deseja exportar a pesquisa. 
    
3. Na **Home** Page do caso, clique em **Pesquisar**.
    
4. Na lista de pesquisas do caso, clique na pesquisa para a qual você deseja exportar os resultados da pesquisa, clique ![em exportar resultados](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) da pesquisa **e, em seguida, selecione** **Exportar resultados** na lista suspensa. 
    
    A página **Exportar resultados** é exibida. 
    
    ![Exportar página de resultados](media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    O fluxo de trabalho para exportar os resultados de uma Pesquisa de Conteúdo associada a uma ocorrência é o mesmo que o usado para exportar os resultados da pesquisa para uma pesquisa na página **Pesquisa de Conteúdo**. Para obter instruções detalhadas, confira [Exportar resultados de pesquisa de conteúdo](export-search-results.md).
    
    > [!NOTE]
    > Ao exportar resultados de pesquisa, você tem a opção de habilitar a eliminação de duplicação para que apenas uma cópia de uma mensagem de email seja exportada, embora várias instâncias da mesma mensagem possam ter sido encontradas nas caixas de correio que foram pesquisadas. Para obter mais informações sobre a eliminação de duplicação e como os itens duplicados são identificados, consulte [desduplicação nos resultados da pesquisa de descoberta eletrônica](de-duplication-in-ediscovery-search-results.md). 
  
5. Clique na guia **Exportar** para exibir a lista de trabalhos de exportação que existem para esse caso. 
    
    ![Guia exportar](media/1b84c45e-4ec9-4ecd-9e07-eaf8fc4cc307.png)
  
    Talvez seja necessário clicar em **Atualizar**![ícone](media/O365-MDM-Policy-RefreshIcon.gif) de atualização para atualizar a lista de trabalhos de exportação para que ele mostre o trabalho de exportação que você criou. Os trabalhos de exportação têm o mesmo nome da pesquisa de conteúdo correspondente com **_Export** acrescentados ao final do nome da pesquisa. 
    
6. Clique no trabalho de exportação que você acabou de criar para exibir informações de status no painel de detalhes. Essas informações incluem a porcentagem de itens que foram transferidos para uma área de armazenamento do Azure na nuvem da Microsoft.
    
    Após a transferência de todos os itens, clique em **baixar resultados** para baixar os resultados da pesquisa para o computador local. Para obter mais informações, consulte a etapa 2 nos [resultados da pesquisa de conteúdo de exportação](export-search-results.md)
    
### <a name="export-the-results-of-multiple-searches-associated-with-a-case"></a>Exportar os resultados de várias pesquisas associadas a uma ocorrência

Como alternativa para exportar os resultados de uma única pesquisa de conteúdo associada a uma ocorrência, você pode exportar os resultados de várias pesquisas do mesmo caso em uma única exportação. Exportar os resultados de várias pesquisas é mais rápido e mais fácil do que exportar os resultados uma pesquisa de cada vez.
  
> [!NOTE]
> Você não pode exportar os resultados de várias pesquisas se uma dessas pesquisas foi configurada para pesquisar todo o conteúdo do caso. Só exporte os resultados de várias pesquisas de pesquisas associadas a uma ocorrência de descoberta eletrônica. Não é possível exportar os resultados de várias pesquisas listadas na página de **pesquisa de conteúdo** no centro de conformidade do & de segurança. 
  
1. No centro de conformidade & segurança **, clique em** \> **descoberta** eletrônica eletrônica para exibir a lista de casos em sua organização. 
    
2. Clique em **abrir** ao lado do caso para o qual você deseja exportar os resultados da pesquisa. 
    
3. Na **Home** Page do caso, clique em **Pesquisar**.
    
4. Na lista de pesquisas do caso, selecione duas ou mais pesquisas das quais você deseja exportar os resultados da pesquisa.
    
    > [!NOTE]
    > Para selecionar várias pesquisas, pressione CTRL enquanto clica em cada pesquisa. Ou você pode selecionar várias pesquisas adjacentes clicando na primeira pesquisa, mantendo pressionada a tecla Shift e clicando na última pesquisa. 
  
5. Depois de selecionar as pesquisas, a página **ações em massa** será exibida. 
    
    ![Na página ações em massa, clique em exportar resultados](media/f34e3707-a9c1-494f-91a4-da1165aa730a.png)
  
    
6. Clique ![em exportar resultados da](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) pesquisa ícone **Exportar resultados**.

7. Na página **Exportar resultados** , atribua um nome exclusivo à exportação, selecione opções de saída e escolha como o conteúdo será exportado. Clique em **Exportar**.
    
    O fluxo de trabalho para exportar os resultados de várias pesquisas de conteúdo associadas a um caso é o mesmo que exportar os resultados da pesquisa para uma única pesquisa. Para obter instruções detalhadas, confira [Exportar resultados de pesquisa de conteúdo](export-search-results.md).
    
    > [!NOTE]
    > Ao exportar resultados de pesquisa de várias pesquisas associadas a um caso, você também tem a opção de habilitar a eliminação de duplicação para que apenas uma cópia de uma mensagem de email seja exportada, embora várias instâncias da mesma mensagem possam ter sido encontradas no caixas de correio que foram pesquisadas em uma ou mais pesquisas. Para obter mais informações sobre a eliminação de duplicação e como os itens duplicados são identificados, consulte [desduplicação nos resultados da pesquisa de descoberta eletrônica](de-duplication-in-ediscovery-search-results.md). 
  
8. Depois de iniciar a exportação, clique na guia **Exportar** para exibir a lista de trabalhos de exportação para esse caso. 
    
    ![Guia exportar, várias pesquisas](media/b9505e1b-559f-4a8c-96b3-a3f734753926.png)
  
    Talvez seja necessário clicar em **Atualizar** ![ícone](media/O365-MDM-Policy-RefreshIcon.gif) de atualização para atualizar a lista de trabalhos de exportação para exibir o trabalho de exportação que você criou. As pesquisas que foram incluídas no trabalho de exportação são listadas na coluna **pesquisas** . 
    
8. Clique no trabalho de exportação que você acabou de criar para exibir informações de status no painel de detalhes. Essas informações incluem a porcentagem de itens que foram transferidos para uma área de armazenamento do Azure na nuvem da Microsoft.
    
9. Após a transferência de todos os itens, clique em **baixar resultados** para baixar os resultados da pesquisa para o computador local. Para obter mais informações, consulte a etapa 2 em [Exportar resultados de pesquisa de conteúdo](export-search-results.md).
    
#### <a name="more-information-about-exporting-the-results-of-multiple-searches"></a>Mais informações sobre como exportar os resultados de várias pesquisas

- Quando você exporta os resultados de várias pesquisas, as consultas de pesquisa de todas as pesquisas são combinadas usando operadores **ou** e, em seguida, a pesquisa combinada é iniciada. Os resultados estimados da pesquisa combinada são exibidos no painel de detalhes do trabalho de exportação selecionado. Os resultados da pesquisa são transferidos para a área de armazenamento do Azure na nuvem da Microsoft. O status da transferência também é exibido no painel de detalhes. Conforme mencionado anteriormente, após todos os resultados da pesquisa terem sido transferidos, você pode baixá-los para o computador local. 
    
- O número máximo de palavras-chave das consultas de pesquisa para todas as pesquisas que você deseja exportar é 500. (esse é o mesmo limite para uma única pesquisa de conteúdo). Isso ocorre porque o trabalho de exportação combina todas as consultas de pesquisa usando o operador **or** . Se você exceder esse limite, um erro será retornado. Nesse caso, você precisa exportar os resultados de menos pesquisas ou simplificar as consultas de pesquisa das pesquisas que você deseja exportar. 
    
- Os resultados de pesquisa que são exportados são organizados pela fonte de conteúdo em que o item foi encontrado. Isso significa que uma fonte de conteúdo nos resultados da exportação pode ter itens retornados por pesquisas diferentes. Por exemplo, se você optar por exportar mensagens de email em um arquivo PST para cada caixa de correio, o arquivo PST poderá ter resultados de várias pesquisas.
    
- Se o mesmo item de email ou documento do mesmo local de conteúdo for retornado por mais de uma das pesquisas que você exportou, somente uma cópia do item será exportada.
    
- Você não pode editar uma exportação para várias pesquisas após criá-la. Por exemplo, não é possível adicionar ou remover pesquisas da exportação. Você precisa criar um trabalho de exportação para alterar quais resultados de pesquisa são exportados. Após a criação de um trabalho de exportação, você só pode baixar os resultados para um computador, reiniciar a exportação ou excluir o trabalho de exportação.
    
- Se você reiniciar a exportação, as alterações nas consultas das pesquisas que compõem o trabalho de exportação não afetarão os resultados da pesquisa que serão recuperados. Quando você reinicia uma exportação, o mesmo trabalho combinado de consulta de pesquisa que foi executado quando o trabalho de exportação foi criado será executado novamente.
    
- Se você reiniciar uma exportação da página **Exports** em um caso de descoberta eletrônica, os resultados da pesquisa transferidos para a área de armazenamento do Azure substituirão os resultados anteriores. Os resultados anteriores que foram transferidos não estarão disponíveis para download. 
    
- A preparação dos resultados de várias pesquisas de análise na descoberta eletrônica avançada não está disponível. Você só pode preparar os resultados de uma única pesquisa para análise na descoberta eletrônica avançada.

## <a name="step-7-prepare-search-results-for-advanced-ediscovery"></a>Etapa 7: preparar resultados de pesquisa para descoberta eletrônica avançada

Se sua organização tiver uma assinatura do Office 365 e5, você poderá preparar os resultados das pesquisas de conteúdo associadas a um caso para análise na descoberta eletrônica avançada. Depois de preparar os resultados da pesquisa, vá para descoberta eletrônica avançada (veja a [etapa 8: Vá para o caso em descoberta eletrônica avançada](#step-8-go-to-the-case-in-advanced-ediscovery)) e processe os dados de resultado da pesquisa para análise adicional na descoberta eletrônica avançada.
  
Quando você prepara os resultados da pesquisa para descoberta eletrônica avançada, a funcionalidade de reconhecimento óptico de caracteres (OCR extrai automaticamente texto de imagens. O OCR tem suporte para arquivos soltos, anexos de email e imagens incorporadas. Isso permite que você aplique os recursos analíticos de texto de descoberta eletrônica avançada (quase duplicatas, threads de email, temas e codificação de previsão) a qualquer texto em arquivos de imagem.
  
> [!NOTE]
> Para analisar os dados de um usuário usando a descoberta eletrônica avançada, o usuário (o responsáveis dos dados) deve receber uma licença do Office 365 e5. Como alternativa, os usuários com uma licença do Office 365 E1 ou E3 podem receber uma licença autônoma de descoberta eletrônica avançada. Administradores e gerentes de conformidade atribuídos aos casos e usar a descoberta eletrônica avançada para analisar os dados não precisam de uma licença e5. 
  
1. No centro de conformidade & segurança **, clique em** \> **descoberta** eletrônica eletrônica para exibir a lista de casos em sua organização. 
    
2. Clique em **abrir** ao lado do caso em que você deseja preparar os resultados da pesquisa para análise na descoberta eletrônica avançada. 
    
3. Na **Home** Page do caso, clique em **Pesquisar**e selecione a pesquisa.
    
4. No painel de detalhes, clique ![em exportar ícone](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) de resultados de pesquisa **mais**e clique em **preparar para descoberta eletrônica avançada**.
    
    ![Preparar os resultados para descoberta eletrônica avançada](media/b6548ff0-a6e9-42b1-9ae4-5c15146f5690.png)
  
5. Na página **preparar para descoberta eletrônica avançada** , opte por preparar uma das seguintes opções: 
    
    - Todos os itens, excluindo-os com formato não reconhecido, são criptografados ou não foram indexados por outros motivos.
    
    - Todos os itens, incluindo aqueles que possuem formato não reconhecido, são criptografados ou não foram indexados por outros motivos.
    
    - Apenas os itens que têm um formato irreconhecível, são criptografados ou não foram indexados por outros motivos.
    
6. Opcion Clique na caixa de seleção **incluir versões para arquivos do SharePoint** . 
    
7. Clique em **Preparar**.
    
    Os resultados da pesquisa estão preparados para análise com descoberta eletrônica avançada.
    
8. Clique em **fechar** para fechar o painel de detalhes. 
    
## <a name="step-8-go-to-the-case-in-advanced-ediscovery"></a>Etapa 8: ir para o caso na descoberta eletrônica avançada

Após criar uma ocorrência no centro de conformidade & segurança, você poderá ir para o mesmo caso na descoberta eletrônica avançada.
  
Para ir a um caso na Descoberta Eletrônica Avançada:
  
1. No centro de conformidade & segurança **, clique em** \> **descoberta** eletrônica eletrônica para exibir a lista de casos em sua organização. 
    
2. Clique em **abrir** ao lado do caso para o qual você deseja ir na descoberta eletrônica avançada. 
    
3. Na **Home** Page do caso, clique em **alternar para descoberta eletrônica avançada**.
    
    ![Selecione alternar para descoberta eletrônica avançada](media/d7e31558-e79c-4782-b841-2b735568a576.png)
  
    A barra de progresso **conectando-se à descoberta eletrônica avançada** é exibida. Quando você estiver conectado à descoberta eletrônica avançada, uma lista de contêineres será exibida na página. 
    
    ![Barra de progresso do eDiscorvery avançado](media/4a84273d-765b-44b8-9006-c20e810ea393.png)
  
    Esses contêineres representam os resultados de pesquisa que você preparou para análise na descoberta eletrônica avançada na etapa 7. O nome do contêiner tem o mesmo nome que a pesquisa de conteúdo no caso do centro de conformidade & segurança. Os contêineres na lista são aqueles que você preparou. Se um usuário diferente preparou resultados de pesquisa para descoberta eletrônica avançada, os contêineres correspondentes não serão incluídos na lista.
    
4. Para carregar os dados de resultado de pesquisa de um contêiner para o caso na descoberta eletrônica avançada, selecione um contêiner e clique em **processo**.
    
    Para obter informações sobre como processar contêineres, consulte [executar o módulo de processo e carregar dados na descoberta eletrônica avançada do Office 365](run-the-process-module-and-load-data-in-advanced-ediscovery.md).
    
> [!TIP]
> Clique em **alternar para descoberta eletrônica** para voltar para o mesmo caso no centro de conformidade de & de segurança. 
  
## <a name="optional-step-9-close-a-case"></a>Opcion Etapa 9: fechar uma ocorrência

Quando o caso ou a investigação legal suportados por uma ocorrência de descoberta eletrônica estiver concluído, você poderá fechar o caso. Veja o que acontece quando você fecha um caso:
  
- Se o caso contiver qualquer local de conteúdo em espera, essas isenções serão desativadas. Isso pode resultar na exclusão ou limpeza permanente do conteúdo, seja pelo usuário ou por um processo automatizado, como uma política de exclusão.
    
- O fechamento de um caso desativa apenas as suspensões que estão associadas a esse caso. Se outras isenções forem colocadas em um local de conteúdo (como uma retenção de litígio. uma política de preservação, ou uma retenção de um caso de descoberta eletrônica diferente, essas isenções ainda serão mantidas.
    
- O caso ainda está listado na página descoberta eletrônica no centro de conformidade de & de segurança. Os detalhes, isenções, pesquisas e membros de um caso fechado são mantidos.
    
- Você pode editar uma ocorrência após ela ser fechada. Por exemplo, você pode adicionar ou remover membros, criar pesquisas, exportar resultados de pesquisa e preparar o resultado da pesquisa para análise na descoberta eletrônica avançada. A principal diferença entre casos ativos e fechados é que a retenção é desativada quando um caso é fechado.
    
Para fechar uma ocorrência:
  
1. No centro de conformidade & segurança **, clique em** \> **descoberta** eletrônica eletrônica para exibir a lista de casos em sua organização. 
    
2. Clique no nome do caso que você deseja fechar.
    
    A página **gerenciar esse** submenu de caso é exibida. 
    
3. Em **gerenciar o status**de caso ![, clique em Remover](media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) o **caso de fechamento**do botão de inspeção.
    
    Um aviso é exibido dizendo que as suspensões associadas ao caso serão desativadas.
    
4. Clique em **Sim** para fechar o caso. 
    
    O status da página **gerenciar esse** submenu de caso é alterado de **ativo** para **encerramento**.
    
5. Feche a página **gerenciar este caso** . 
    
6. Na página **descoberta eletrônica** , clique ![em atualizar](media/O365-MDM-Policy-RefreshIcon.gif) ícone **Atualizar** para atualizar o status da ocorrência fechada. Pode levar até 60 minutos para que o processo de fechamento seja concluído. 
    
    Quando o processo estiver concluído, o status da ocorrência será alterado para **fechado** na página de **descoberta eletrônica** . Clique no nome do caso novamente para exibir a página **gerenciar este caso** , que contém informações sobre quando o caso foi fechado e quem o fechou. 
     
## <a name="optional-step-10-re-open-a-closed-case"></a>Opcion Etapa 10: abrir novamente uma ocorrência fechada

Quando você reabrir um caso, qualquer bloqueio que estava no lugar quando o caso foi fechado não será restabelecido automaticamente. Depois que o caso for reaberto, você precisará ir até a página de **retenção** e ativar as isenções anteriores. Para ativar uma retenção, selecione-a e clique em **ativá-la** no painel de detalhes. 
  
1. No centro de conformidade & segurança **, clique em** \> **descoberta** eletrônica eletrônica para exibir a lista de casos em sua organização. 
    
2. Clique no nome do caso que você deseja reabrir.
    
    A página **gerenciar esse** submenu de caso é exibida. 
    
3. Em **gerenciar o status de caso**, clique em **reabrir caso**.
    
    Um aviso é exibido dizendo que as suspensões que estavam associadas ao caso em que foram fechadas não serão ativadas automaticamente.
    
4. Clique em **Sim** para reabrir a ocorrência. 
    
    O status da página **gerenciar esse** submenu de caso é alterado de **fechado** para **ativo**.
    
5. Feche a página **gerenciar este caso** . 
    
6. Na página **descoberta eletrônica** , clique ![em atualizar](media/O365-MDM-Policy-RefreshIcon.gif) ícone **Atualizar** para atualizar o status do caso reaberto. Pode levar até 60 minutos para que o processo de reabertura seja concluído. 
    
    Quando o processo estiver concluído, o status da ocorrência será alterado para **ativo** na página de **descoberta eletrônica** . 
  
## <a name="optional-step-11-delete-a-case"></a>Opcion Etapa 11: excluir uma ocorrência

Você também pode excluir casos ativos e fechados. Quando você exclui um caso, todas as pesquisas e exportações no caso são excluídas e removidas da lista de casos na página **descoberta eletrônica** no centro de conformidade de & de segurança. Não é possível abrir novamente um caso excluído. 

Antes de poder excluir uma ocorrência (se ela está ativa ou fechada), você deve primeiro excluir *todas as* isenções associadas à ocorrência. Isso inclui a exclusão de isenções com o status **desativado**. 

Para excluir uma retenção:

1. Vá para a guia **isenções** , caso você queira excluir.

2. Clique na isenção que você deseja excluir.

3. Na página do menu suspenso, clique em **excluir isenção**.

Para excluir uma ocorrência:

1. No centro de conformidade & segurança **, clique em** \> **descoberta** eletrônica eletrônica para exibir a lista de casos em sua organização. 
    
2. Clique no nome do caso que você deseja excluir.

3. Em **gerenciar status de caso** na página de submenu, clique em **excluir caso**.

Se o caso que você está tentando excluir ainda contiver isenções, você receberá uma mensagem de erro. Você terá que excluir todas as suspensões associadas à ocorrência e, em seguida, tentar excluir a ocorrência novamente.

## <a name="more-information"></a>Mais informações

- **Há limites para casos de descoberta eletrônica ou isenções associados a uma ocorrência de descoberta eletrônica?** A tabela a seguir lista os limites de ocorrências de descoberta eletrônica e isenções de caso.
    
  |**Descrição do limite**|**Limite**|
  |:-----|:-----|
  |Número máximo de casos para uma organização  <br/> |Sem limite  <br/> |
  |Número máximo de isenções de caso para uma organização  <br/> |10.000  <br/> |
  |Número máximo de caixas de correio em uma única retenção de caso  <br/> |1.000  <br/> |
  |Número máximo de sites do SharePoint e do OneDrive for Business em uma única retenção de caso  <br/> |100  <br/> |
   
- **E os casos que foram criados na página de gerenciamento de casos na descoberta eletrônica avançada?** Você pode acessar uma lista de casos de descoberta eletrônica avançada mais antigas clicando no link na parte inferior da página de **descoberta eletrônica** no centro de conformidade de & de segurança. No entanto, para fazer qualquer trabalho em um caso mais antigo, você precisa entrar em contato com o suporte do Office 365 e solicitar que o caso seja movido para uma nova ocorrência de descoberta eletrônica no centro de conformidade de & de segurança. 
    
- **Por que criar um Administrador de Descoberta Eletrônica? ** Conforme explicado anteriormente, um Administrador de Descoberta Eletrônica é membro do grupo de funções Gerente de Descoberta Eletrônica e pode ver e acessar todas as ocorrências de Descoberta Eletrônica em sua organização. A capacidade de acessar todas as ocorrências de Descoberta Eletrônica tem duas finalidades importantes:
    
  - se uma pessoa que é o único membro de um ocorrência de Descoberta Eletrônica sair de sua organização, ninguém (incluindo os membros do grupo de funções Gerenciamento da organização ou outro membro do grupo de funções Gerente de Descoberta Eletrônica) poderá acessar essa ocorrência de Descoberta Eletrônica, pois não é membro de uma ocorrência. Nessa situação, não haveria um modo de acessar os dados na ocorrência. No entanto, como um administrador de descoberta eletrônica pode acessar todos os casos de descoberta eletrônica na organização, eles podem ver o caso no centro de conformidade de & de segurança e adicioná-los ou outro gerenciador de descoberta eletrônica como membro do caso.
    
  - Como um administrador de descoberta eletrônica pode exibir e acessar todos os casos de descoberta eletrônica, eles podem auditar e supervisionar todos os casos e pesquisas de conteúdo associadas. Isso pode ajudar a evitar o uso indevido de Pesquisas de Conteúdo ou de ocorrências de Descoberta Eletrônica. Além disso, como os Administradores de Descoberta Eletrônica podem acessar informações possivelmente confidenciais nos resultados de uma Pesquisa de Conteúdo, você deve limitar o número de pessoas com a função de Administrador de Descoberta Eletrônica.
    
    Por fim, como explicado anteriormente, os administradores de descoberta eletrônica no centro de conformidade do & de segurança são automaticamente adicionados como administradores na descoberta eletrônica avançada. Isso significa que uma pessoa que é um administrador de descoberta eletrônica pode executar tarefas administrativas em descoberta eletrônica avançada, como configurar usuários, criar ocorrências e adicionar dados a ocorrências.
    
- **Quais são os requisitos de licenciamento para colocar os locais de conteúdo em espera?** Em geral, as organizações precisam de uma assinatura do Office 365 E3 ou superior para colocar os locais de conteúdo em espera. Para colocar caixas de correio em espera, uma licença do Exchange Online Plan 2 é necessária para a caixa de correio que você deseja colocar em espera.
    
- **O que mais você deve saber sobre a pesquisa de todo o conteúdo do caso na etapa 5?** Conforme explicado anteriormente, você pode pesquisar os locais de conteúdo que foram colocados em espera no caso. Ao fazer isso, somente o conteúdo que corresponde aos critérios de retenção é a pesquisa. Se não houver nenhum critério de espera, todo o conteúdo será pesquisado. Se o conteúdo estiver em uma retenção baseada em consulta, somente o conteúdo que corresponde aos critérios de espera (do bloqueio colocado na etapa 4) e o critério de pesquisa (da pesquisa na etapa 5) será retornado com os resultados da pesquisa.
    
    Aqui estão alguns outros pontos a serem lembrados ao pesquisar todo o conteúdo do caso:
    
  - Se um local de conteúdo fizer parte de várias isenções dentro do mesmo caso, as consultas de retenção serão combinadas por um operador **or** quando você pesquisar esse local de conteúdo usando a opção de conteúdo de todos os casos. Da mesma forma, se um local de conteúdo fizer parte de duas isenções diferentes, onde uma delas é baseada em consulta e a outra é um bloqueio infinito (onde todo o conteúdo é colocado em espera), todo o conteúdo será pesquisado por causa da isenção. 
    
  - Se uma pesquisa de conteúdo for para um caso e você a configurou para pesquisar todo o conteúdo do caso e, em seguida, alterar uma retenção (adicionando ou removendo um local de conteúdo ou alterando a consulta de retenção), a configuração de pesquisa será atualizada com essas alterações. No entanto, é necessário executar novamente a pesquisa após a alteração da retenção para atualizar os resultados da pesquisa.
    
  - Se a retenção de vários casos for colocada em um local de conteúdo em uma ocorrência de descoberta eletrônica e você selecionar a pesquisa de todo o conteúdo do caso, o número máximo de palavras-chave para essa consulta de pesquisa será de 500. Isso ocorre porque a pesquisa de conteúdo combina todas as retenções baseadas em consulta usando o operador **ou** . Se houver mais de 500 palavras-chave nas consultas de retenção combinada e na consulta de pesquisa de conteúdo, todo o conteúdo da caixa de correio será pesquisado, e não apenas esse conteúdo que corresponda a qualquer bloqueio de caso baseado em consulta. 
    
  - Se um caso de retenção tiver um status de **ativação**, você ainda poderá pesquisar os locais de conteúdo do caso enquanto a retenção estiver sendo ativada.
    
  - Conforme mencionado anteriormente, se uma pesquisa estiver configurada para pesquisar todo o conteúdo do caso, não será possível incluir essa pesquisa se você quiser exportar os resultados de várias pesquisas. Se uma pesquisa estiver configurada para pesquisar todo o conteúdo do caso, você terá que exportar os resultados dessa única pesquisa.
    
- **Se uma caixa de correio, site do SharePoint ou uma conta do OneDrive que está em espera for movida para uma região diferente em um ambiente multigeográfico, a retenção ainda será aplicada?** Em todos os casos, o conteúdo em uma caixa de correio, site ou conta do OneDrive ainda será mantido. No entanto, as estatísticas de retenção não incluirão mais itens de um local de conteúdo que tenha sido movido para uma região diferente. Para incluir estatísticas de retenção para um local de conteúdo que tenha sido movido, você deve editar a isenção e atualizar a URL (ou o endereço SMTP de uma caixa de correio) para que o local do conteúdo seja novamente incluído nas estatísticas de retenção. 
    
- **E como colocar uma retenção em grupos do Office 365 e no Microsoft Teams?** O Microsoft Teams é criado em grupos do Office 365. Portanto, colocá-los em espera em um caso de descoberta eletrônica é semelhante. Lembre-se do seguinte ao colocar grupos do Office 365 e do Microsoft Teams em espera. 
    
  - Para colocar o conteúdo localizado nos grupos do Office 365 e no Microsoft Teams em espera, você precisa especificar a caixa de correio e o site do SharePoint que estão associados a um grupo ou a uma equipe.
    
  - Execute o cmdlet **Get-unificado** no Exchange Online para exibir as propriedades de um grupo do Office 365 ou equipe da Microsoft. Essa é uma boa maneira de obter a URL do site que está associado a um grupo do Office 365 ou a uma equipe da Microsoft. Por exemplo, o comando abaixo exibe as propriedades selecionadas para um grupo do Office365 chamado de Equipe de Liderança Sênior: 
    
       ```text
       Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl

       DisplayName            : Senior Leadership Team
       Alias                  : seniorleadershipteam
       PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
       SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
       ```

    > [!NOTE]
    > Para executar o cmdlet **Get-UnifiedGroup**, é preciso ter atribuído a função de Destinatários Somente Leitura no Exchange Online ou ser membro de um grupo de funções atribuído à função de Destinatários Somente Leitura. 
  
  - Quando a caixa de correio de um usuário é pesquisada, qualquer grupo do Office 365 ou Microsoft Team do qual o usuário é membro não será pesquisado. Da mesma forma, quando você coloca um grupo do Office 365 ou um bloqueio de equipe da Microsoft, somente a caixa de correio de grupo e o site de grupo são colocados em espera. As caixas de correio e os sites do OneDrive for Business de membros do grupo não são colocados em espera, a menos que você os adicione explicitamente à isenção. Portanto, se você precisar colocar um grupo do Office 365 ou o Microsoft Team em espera por um motivo legal, considere adicionar as caixas de correio e os sites do OneDrive for Business para membros de grupo e de equipe na mesma isenção.
    
  - Para obter uma lista dos membros de um grupo do Office 365 ou de uma equipe da Microsoft, você pode exibir as propriedades na página **grupos domésticos \> ** no centro de administração do Microsoft 365. Como alternativa, execute o comando a seguir no PowerShell do Exchange Online: 
    
    ```powershell
    Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
    ```

    > [!NOTE]
    > Para executar o cmdlet **Get-UnifiedGroupLinks**, é preciso ter atribuído a função de Destinatários Somente Leitura no Exchange Online ou ser um membro de um grupo de funções atribuído à função Destinatários Somente Leitura. 
  
  - As conversas que fazem parte de um canal do Microsoft Teams são armazenadas na caixa de correio que está associada à equipe da Microsoft. Da mesma forma, os arquivos que os membros da equipe compartilham em um canal são armazenados no site do SharePoint da equipe. Portanto, você precisa colocar a caixa de correio do Microsoft Team e o site do SharePoint em espera para reter conversas e arquivos em um canal.
    
    Como alternativa, as conversas que fazem parte da lista de chat no Microsoft Teams são armazenadas na caixa de correio do usuário que participa do chat. Os arquivos que um usuário compartilha em conversas de chat são armazenados no site do OneDrive for Business do usuário que compartilha o arquivo. Portanto, você precisa colocar as caixas de correio de usuários individuais e os sites do OneDrive for Business em retenção para reter conversas e arquivos na lista de chat. É por isso que é uma boa ideia colocar uma retenção nas caixas de correio dos membros de uma equipe da Microsoft, além de colocar a caixa de correio da equipe (e o site) em espera.
    
    > [!IMPORTANT]
    > Os usuários que participam de conversas que fazem parte da lista de chat no Microsoft Teams devem ter uma caixa de correio do Exchange Online (baseada na nuvem) para reter conversas de chat quando a caixa de correio é colocada em uma descoberta eletrônica. Isso ocorre porque as conversas que fazem parte da lista de chat são armazenadas nas caixas de correio baseadas em nuvem dos participantes do chat. Se um participante de chat não tiver uma caixa de correio do Exchange Online, você não conseguirá reter conversas de chat. Por exemplo, em uma implantação híbrida do Exchange, os usuários com uma caixa de correio local podem conseguir participar de conversas que fazem parte da lista de chat no Microsoft Teams. No entanto, nesse caso, o conteúdo dessas conversas não pode ser retido porque os usuários não têm caixas de correio baseadas em nuvem. 
  
  - Cada equipe do Microsoft ou canal de equipe contém um wiki para anotações e colaboração. O conteúdo Wiki é salvo automaticamente em um arquivo com um formato .mht. Esse arquivo é armazenado na biblioteca de documentos de Dados do Wiki do Teams no site do SharePoint da equipe. Você pode colocar o conteúdo do wiki em espera, colocando o site do SharePoint da equipe em espera.
    
    > [!NOTE]
    > A capacidade de manter o conteúdo do wiki para uma equipe do Microsoft ou um canal de equipe (quando você coloca o site do SharePoint da equipe em espera) foi lançada em 22 de junho de 2017. Se um site de equipe estiver em espera, o conteúdo wiki será retido a partir dessa data. No entanto, se um site de equipe estiver em espera e o conteúdo wiki tiver sido excluído antes de 22 de junho de 2017, o conteúdo wiki não foi mantido. 

- **Como encontrar a URL para os sites do OneDrive for Business?** Para coletar uma lista das URLs para os sites do OneDrive for Business em sua organização para que você possa adicioná-los a uma isenção ou a uma pesquisa associada a uma ocorrência de descoberta eletrônica, consulte [criar uma lista de todos os locais do onedrive em sua organização](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). Esse script neste artigo cria um arquivo de texto que contém uma lista de todos os sites do OneDrive. Para executar esse script, é necessário instalar e usar o Shell de Gerenciamento Online do SharePoint. Não se esqueça de acrescentar a URL do domínio MySite da organização para cada site do OneDrive que você deseja pesquisar. Este é o domínio que contém todos os seus OneDrive; por exemplo, `https://contoso-my.sharepoint.com`. Veja um exemplo de URL para o site do OneDrive de um usuário: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.
