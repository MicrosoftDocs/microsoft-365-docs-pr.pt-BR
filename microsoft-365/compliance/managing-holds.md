---
title: Gerenciar retém na Descoberta Avançada de eDiscovery
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
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Saiba como colocar retém em custodiantes e suas fontes de dados para preservar conteúdo relevante para seu caso de Descoberta Avançada.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f56d12b6d69e56e85f0e7ad37fbf65746a1cff23
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024731"
---
# <a name="manage-holds-in-advanced-ediscovery"></a>Gerenciar retém na Descoberta Avançada de eDiscovery

Você pode usar uma ocorrência de Descoberta Avançada para criar retém para preservar conteúdo que possa ser relevante para o seu caso. Usando os recursos de espera da Descoberta Avançada, você pode colocar retém em custodiantes e suas fontes de dados. Além disso, você pode colocar uma espera não custodial em caixas de correio e sites do OneDrive for Business. Você também pode colocar em espera a caixa de correio do grupo, o site do SharePoint e o site do OneDrive for Business para um Grupo do Microsoft 365. Da mesma forma, você pode colocar uma espera na caixa de correio e no site associados ao Microsoft Teams. Quando você coloca locais de conteúdo em espera, o conteúdo é mantido até que você libere o custodiante, remova um local de dados específico ou exclua totalmente a política de responsabilidade.

## <a name="manage-custodian-based-holds"></a>Gerenciar reter com base em custodiatário

Em alguns casos, você pode ter um conjunto de custodiantes que identificou e decidiu preservar seus dados durante o caso. Na Descoberta Automática Avançada, quando esses custodiantes são colocados em espera, o usuário e suas fontes de dados selecionadas são automaticamente adicionadas a uma política de suspensão custodiante.

Para exibir a política de espera custodiada:

1. No centro de conformidade do Microsoft 365, clique em **Descoberta > Avançado** para exibir a lista de casos em sua organização.

2. Vá para a **guia Fontes** para adicionar custodiantes em seu caso. Para saber como você pode adicionar e colocar custodiantes em espera em um caso de Descoberta Avançada, consulte [Adicionar Custodiantes a uma ocorrência.](add-custodians-to-case.md) Se você já adicionou custodiantes e os colocou em espera, vá para a etapa 3.

3. Vá para a **guia Reter** e clique **em CustodianHold \<HoldId>**.

4. Na página do flyout, você pode ver estatísticas de espera para a política. Você também pode executar ações como aplicar uma consulta à sua espera baseada em custodiatário. For more information about creating a hold query and using conditions, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).

## <a name="manage-non-custodial-holds"></a>Gerenciar retém não custodial

Ao criar uma iseção, você tem as seguintes opções para criar um escopo do conteúdo que é mantido nos locais de conteúdo especificados:

- Você cria uma espera infinita em que todo o conteúdo é colocado em espera. Como alternativa, você pode criar uma isenção baseada em consulta onde apenas o conteúdo que corresponde a uma consulta de pesquisa é colocado em espera.
  
- Você pode especificar um intervalo de datas para conter somente o conteúdo que foi enviado, recebido ou criado dentro desse intervalo de datas. Como alternativa, você pode manter todo o conteúdo, independentemente de quando ele foi enviado, recebido ou criado.

Para criar uma responsabilidade não custodial para um caso de Descoberta Avançada:

1. No centro de conformidade do Microsoft 365, clique em **Descoberta > Avançado** para exibir a lista de casos em sua organização.
  
2. Clique **em** Abrir ao lado do caso em que você deseja criar as retém.
  
3. Na home page do caso, clique na guia **Retém.**
  
4. Na guia **Retém,** clique em **Criar**.
  
5. Na página **Nomear sua espera,** dê um nome à espera. O nome da retenção deve ser exclusivo na sua organização.
 
6. (Opcional) Na caixa **Descrição,** adicione uma descrição da espera.
  
7. Clique em **Avançar**.
  
8. Escolha os locais de conteúdo que você deseja colocar em espera. Você pode colocar caixas de correio, sites e pastas públicas em espera.

   1. **Email do Exchange** - Clique em Escolher **usuários, grupos** ou equipes e clique em Escolher **usuários, grupos** ou equipes novamente para especificar caixas de correio para colocar em espera. Use a caixa de pesquisa para encontrar caixas de correio de usuário e grupos de distribuição (para colocar em espera as caixas de correio de membros do grupo) para colocar em espera. Você também pode colocar uma espera na caixa de correio associada para um Grupo do Microsoft 365 ou um Microsoft Team. Marque o usuário, grupo, caixa de seleção da equipe, clique em **Escolher** e clique em **Feito.**
 
      > [!NOTE]
      > Quando você clica **em Escolher usuários, grupos** ou equipes para especificar caixas de correio para colocar em espera, o seletor de caixa de correio exibido fica vazio. Isso foi desenvolvido para melhorar o desempenho. Para adicionar pessoas a essa lista, digite um nome (no mínimo 3 caracteres) na caixa de pesquisa.

   1. **Sites do SharePoint** - Clique em Escolher **sites** e clique em Escolher **sites** novamente para especificar sites do SharePoint e do OneDrive for Business para colocar em espera. Digite a URL de cada site que você deseja colocar em retenção. Você também pode adicionar a URL do site do SharePoint para um Grupo do Microsoft 365 ou um Microsoft Team. Clique **em Escolher** e em **Done**.
    
      Confira a **seção perguntas frequentes** para ver dicas sobre como colocar os Grupos do Microsoft 365 e o Microsoft Teams em espera.

      > [!NOTE]
      > A URL da conta do OneDrive de um usuário inclui seu nome UPN (nome upn) (por exemplo, `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` ). No caso raro de o UPN de uma pessoa ser alterado, a URL do OneDrive também mudará para incorporar o novo UPN. Se a conta do OneDrive de um usuário faz parte de uma espera sem custodiante e seu UPN é alterado, você precisa atualizar a espera e apontar para a nova URL do OneDrive. Para saber mais, confira [Como as alterações de UPN afetam a URL do OneDrive](https://docs.microsoft.com/onedrive/upn-changes).

   1. **Pastas públicas do Exchange** - Mova o botão de alternância para a posição Todos para colocar todas as pastas públicas em sua organização do Exchange Online em espera. Observe que você não pode escolher pastas públicas específicas para colocar em espera. Deixe o botão de alternância **definido** como Nenhum se você não quiser colocar uma espera em pastas públicas.

9. Quando terminar de adicionar locais de conteúdo à espera, clique em **Próximo.**
  
10. Para criar uma espera baseada em consulta com condições, conclua o seguinte. Caso contrário, basta clicar **em Próximo**.
    
    - Na caixa **Palavras-chave,** digite uma consulta de pesquisa na caixa para que somente o conteúdo que atenda aos critérios de pesquisa seja colocado em espera. Você pode especificar palavras-chave, propriedades da mensagem ou propriedades do documento, como nomes de arquivo. Você também pode usar consultas mais complexas que usam um operador booleano, como AND, OR ou NOT. Se você deixar a caixa de palavra-chave vazia, todo o conteúdo localizado nos locais de conteúdo especificados será colocado em espera.

    - Clique  **em** Adicionar condições para adicionar uma ou mais condições para restringir a consulta de pesquisa para a espera. Cada condição adiciona uma cláusula à consulta de pesquisa KQL que é criada e executado quando você cria a isenção. Por exemplo, você pode especificar um intervalo de datas para que os documentos de email ou site criados dentro do intervalo de datas sejam colocados em espera. Uma condição está logicamente conectada à consulta de palavra-chave (especificada na caixa de palavra-chave) pelo operador AND. Isso significa que os itens devem atender à consulta de palavra-chave e à condição a ser colocada em espera.

     Para obter mais informações sobre como criar uma consulta de pesquisa e usar condições, consulte Consultas de palavra-chave e condições de pesquisa [para Pesquisa de Conteúdo.](https://docs.microsoft.com/office365/SecurityCompliance/keyword-queries-and-search-conditions)

11. Depois de configurar uma espera baseada em consulta, clique em **Próximo.**

12. Revise suas configurações e clique em **Criar esta espera.**

## <a name="view-hold-statistics"></a>Exibir estatísticas de espera

Após algum tempo, as informações sobre a nova iseçamento serão exibidas no painel de detalhes na guia **Retém** para a espera selecionada. Essas informações incluem o número de caixas de correio e sites em espera e estatísticas sobre o conteúdo que foi colocado em espera, como o número total e o tamanho dos itens colocados em espera e a última vez que as estatísticas de espera foram calculadas. Essas estatísticas de isenção ajudam a identificar a grande parte do conteúdo relacionado ao caso de Descoberta eDiscovery que está sendo mantida.

Lembre-se do seguinte sobre estatísticas de espera:

- O número total de itens em espera indica o número de itens de todas as fontes de conteúdo colocadas em espera. Se você criou uma espera baseada em consulta, essa estatística indica o número de itens que corresponderem à consulta.
  
- O número de itens em espera também inclui itens não índicedos encontrados nos locais de conteúdo. Observe que, se você criar uma espera baseada em consulta, todos os itens não índicedos nos locais de conteúdo serão colocados em espera. Isso inclui itens não índicedos que não corresponderem aos critérios de pesquisa de uma espera baseada em consulta e itens não índicedos que podem ficar fora de uma condição de intervalo de datas. Isso é diferente do que acontece quando você executar uma Pesquisa de Conteúdo, na qual itens não índicedos que não corresponderem à consulta de pesquisa ou que são excluídos por uma condição de intervalo de datas não são incluídos nos resultados da pesquisa. Para saber mais sobre itens não indexados, confira Itens parcialmente indexados na Pesquisa de [Conteúdo no Office 365.](partially-indexed-items-in-content-search.md) 

- Você pode obter as estatísticas de espera mais recentes clicando em Estatísticas de atualização para executar uma estimativa de pesquisa que calcula o número atual de itens em espera.

- Se necessário, clique em Atualizar na barra de ferramentas para atualizar as estatísticas de espera no painel de detalhes.

- É normal que o número de itens em espera aumente ao longo do tempo porque os usuários cuja caixa de correio ou site está em espera normalmente estão enviando ou recebendo novas mensagens de email e criando novos documentos do SharePoint e do OneDrive for Business.

- Se um site do SharePoint ou uma conta do OneDrive for movido para uma região diferente em um ambiente multi-geo, as estatísticas desse site não serão incluídas nas estatísticas de isenção. No entanto, o conteúdo no site ainda estará em espera. Além disso, se um site for movido para uma região diferente, a URL exibida no iso não será atualizada. Você terá que editar a espera e atualizar a URL.

## <a name="place-a-hold-on-microsoft-teams-and-office-365-groups"></a>Colocar em espera o Microsoft Teams e grupos do Office 365

O Microsoft Teams foi criado com base nos Grupos do Office 365. Portanto, colocá-los em espera na Descoberta eDiscovery Avançada é muito semelhante. 

- **Como mapear um site adicional do Microsoft 365 Groups ou do Microsoft Teams para um custodiatário? E quanto a colocar uma espera não custodial nos Grupos do Microsoft 365 e no Microsoft Teams?** O Microsoft Teams foi criado com base nos Grupos do Microsoft 365. Portanto, colocá-los em espera em um caso de Descoberta eDiscovery é muito semelhante. Lembre-se do seguinte ao colocar os Grupos do Microsoft 365 e o Microsoft Teams em espera.
  - Para colocar o conteúdo localizado nos Grupos do Microsoft 365 e no Microsoft Teams em espera, você precisa especificar a caixa de correio e o site do SharePoint associados a um grupo ou equipe.
  
  - Execute o cmdlet **Get-UnifiedGroup** no Exchange Online para exibir as propriedades de um Grupo do Microsoft 365 ou do Microsoft Team. Essa é uma boa maneira de obter a URL do site associado a um Grupo do Microsoft 365 ou a um Microsoft Team. Por exemplo, o comando abaixo exibe as propriedades selecionadas para um grupo do Microsoft 365 chamado de Equipe de Liderança Sênior:


    ```console
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Para executar o cmdlet Get-UnifiedGroup, é preciso ter atribuído a função de Destinatários Somente Leitura no Exchange Online ou ser membro de um grupo de funções atribuído à função de Destinatários Somente Leitura.

 - Quando a caixa de correio de um usuário é pesquisada, qualquer Grupo do Microsoft 365 ou Microsoft Team do que o usuário é membro não será pesquisado. Da mesma forma, quando você coloca um grupo do Microsoft 365 ou uma equipe da Microsoft em espera, apenas a caixa de correio do grupo e o site do grupo são colocados em espera; as caixas de correio e os sites do OneDrive for Business dos membros do grupo não são colocados em espera, a menos que você os adicione explicitamente como custodiantes ou coloque suas fontes de dados em espera. Portanto, se você precisar colocar um Grupo do Microsoft 365 ou Uma Equipe da Microsoft em espera por um custodiante específico, considere mapear o site do grupo e a caixa de correio de grupo para o custodiante (consulte Gerenciando custodiantes na Descoberta Eletrônico Avançada). Se o Grupo do Microsoft 365 ou a Equipe da Microsoft não for atribuível a um único custodiante, considere adicionar a origem a uma iserção não custodial. 
 
 - Para obter uma lista dos membros de um Grupo do Microsoft 365 ou do Microsoft Team, você pode exibir as propriedades na página Home > Groups no centro de administração do Microsoft 365. Como alternativa, execute o comando a seguir no PowerShell do Exchange Online:

   ```powershell
   Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
   ```

    > [!NOTE]
    > Para executar o cmdlet **Get-UnifiedGroupLinks**, é preciso ter atribuído a função de Destinatários Somente Leitura no Exchange Online ou ser um membro de um grupo de funções atribuído à função Destinatários Somente Leitura.

- As conversas do canal que fazem parte de um canal do Microsoft Teams são armazenadas na caixa de correio associada à equipe. Da mesma forma, os arquivos que os membros da equipe compartilham em um canal são armazenados no site do SharePoint da equipe. Portanto, você precisa colocar a caixa de correio do Microsoft Team e o site do SharePoint em espera para manter conversas e arquivos em um canal.
  
- Como alternativa, as conversas que fazem parte da lista de Chat no Microsoft Teams são armazenadas na caixa de correio dos usuários que participam do chat.  Os arquivos que um usuário compartilha em conversas de Chat são armazenados no site do OneDrive for Business do usuário que compartilha o arquivo. Portanto, você precisa colocar as caixas de correio de usuários individuais e sites do OneDrive for Business em espera para manter conversas e arquivos na lista de Chat. 
  
- Cada canal do Microsoft Team ou de equipe contém um Wiki para anotações e colaboração. O conteúdo Wiki é salvo automaticamente em um arquivo com um formato .mht. Esse arquivo é armazenado na biblioteca de documentos de Dados do Wiki do Teams no site do SharePoint da equipe. Você pode colocar o conteúdo no Wiki em espera colocando o site do SharePoint da equipe em espera.

  > [!NOTE]
  > A capacidade de reter o conteúdo wiki de uma Equipe da Microsoft ou de um canal de equipe (quando você coloca o site do SharePoint da equipe em espera) foi lançada em 22 de junho de 2017. Se um site de equipe estiver em espera, o conteúdo wiki será retido a partir dessa data. No entanto, se um site de equipe estiver em espera e o conteúdo wiki tiver sido excluído antes de 22 de junho de 2017, o conteúdo wiki não foi mantido.
