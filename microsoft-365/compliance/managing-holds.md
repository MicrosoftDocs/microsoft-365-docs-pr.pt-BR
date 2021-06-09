---
title: Gerenciar ressál Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Saiba como colocar retém os custodiantes e suas fontes de dados para preservar conteúdo relevante para seu Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 70390a933de788a6b1190e42b5087b85a175b9a2
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570585"
---
# <a name="manage-holds-in-advanced-ediscovery"></a>Gerenciar ressál Advanced eDiscovery

Você pode usar uma Advanced eDiscovery para criar ressarções para preservar conteúdo que pode ser relevante para o seu caso. Usando os recursos Advanced eDiscovery de espera, você pode colocar retém os custodiantes e suas fontes de dados. Além disso, você pode colocar uma espera não custodial em caixas de correio e OneDrive for Business sites. Você também pode colocar uma responsabilidade na caixa de correio do grupo, SharePoint site e OneDrive for Business site para um Microsoft 365 Group. Da mesma forma, você pode colocar uma espera na caixa de correio e no site que estão associados ao Microsoft Teams. Quando você coloca locais de conteúdo em espera, o conteúdo é mantido até que você libere o custodiante, remova um local de dados específico ou exclua totalmente a política de espera.

## <a name="manage-custodian-based-holds"></a>Gerenciar resgates baseados em custodia

Em alguns casos, você pode ter um conjunto de custodiantes que você identificou e decidiu preservar seus dados durante o caso. Em Advanced eDiscovery, quando esses custodiantes são colocados em espera, o usuário e suas fontes de dados selecionadas são adicionados automaticamente a uma política de suspensão de custodiante.

Para exibir a política de espera custodiada:

1. No centro Microsoft 365 de conformidade, clique em **Descoberta > Avançado** para exibir a lista de casos em sua organização.

2. Vá para a guia **Fontes** para adicionar custodiantes em seu caso. Para saber como adicionar e colocar os custodiantes em espera em um caso de Advanced eDiscovery, consulte [Add Custodians to a case](add-custodians-to-case.md). Se você já adicionou os custodiantes e os colocou em espera, vá para a etapa 3.

3. Vá até a guia **Reter** e clique **em \<HoldId> CustodianHold**.

4. Na página de sobrevoo, você pode ver estatísticas de bloqueio para a política. Você também pode executar ações como aplicar uma consulta à sua espera baseada em custodia. Para obter mais informações sobre como criar uma consulta de espera e usar condições, consulte Consultas de palavra-chave e condições de [pesquisa para Pesquisa de Conteúdo.](keyword-queries-and-search-conditions.md)

## <a name="manage-non-custodial-holds"></a>Gerenciar ressalções não custodiais

Ao criar uma ressarção, você tem as seguintes opções para escopo do conteúdo que é mantido nos locais de conteúdo especificados:

- Você cria uma ressarção infinita em que todo o conteúdo é colocado em espera. Como alternativa, você pode criar uma isenção baseada em consulta, onde somente o conteúdo que corresponde a uma consulta de pesquisa é colocado em espera.
  
- Você pode especificar um intervalo de datas para manter somente o conteúdo enviado, recebido ou criado dentro desse intervalo de datas. Como alternativa, você pode manter todo o conteúdo independentemente de quando ele foi enviado, recebido ou criado.

Para criar uma responsabilidade não custodial para um Advanced eDiscovery caso:

1. No centro Microsoft 365 de conformidade, clique em **Descoberta > Avançado** para exibir a lista de casos em sua organização.
  
2. Clique **em Abrir** ao lado do caso em que você deseja criar os retém.
  
3. Na home page do caso, clique na guia **Retém.**
  
4. Na guia **Retém,** clique em **Criar**.
  
5. Na página **Nome da sua** espera, dê um nome à ressarção. O nome da retenção deve ser exclusivo na sua organização.
 
6. (Opcional) Na caixa **Descrição,** adicione uma descrição da espera.
  
7. Clique em **Avançar**.
  
8. Escolha os locais de conteúdo que você deseja colocar em espera. Você pode colocar caixas de correio, sites e pastas públicas em retenção.

   1. **Exchange email** - Clique em **Escolher usuários,** grupos ou equipes e clique em Escolher **usuários,** grupos ou equipes novamente para especificar caixas de correio para colocar em espera. Use a caixa de pesquisa para localizar caixas de correio de usuário e grupos de distribuição (para colocar em retenção as caixas de correio de membros do grupo) e colocar em espera. Você também pode colocar uma responsabilidade na caixa de correio associada para um Microsoft 365 Group ou uma Equipe da Microsoft. Selecione a caixa de seleção usuário, grupo, equipe, clique em **Escolher** e clique em **Feito**.
 
      > [!NOTE]
      > Quando você clica **em Escolher usuários, grupos** ou equipes para especificar caixas de correio para colocar em espera, o seletor de caixa de correio exibido está vazio. Isso foi desenvolvido para melhorar o desempenho. Para adicionar pessoas a essa lista, digite um nome (no mínimo 3 caracteres) na caixa de pesquisa.

   1. **SharePoint Sites** - Clique em **Escolher sites** e clique em Escolher **sites** novamente para especificar SharePoint e OneDrive for Business sites para colocar em espera. Digite a URL de cada site que você deseja colocar em espera. Você também pode adicionar a URL do site SharePoint para um Microsoft 365 Group ou uma Equipe da Microsoft. Clique **em Escolher** e clique em **Feito**.

      > [!NOTE]
      > A URL da conta de usuário OneDrive inclui o nome principal do usuário (UPN) (por exemplo, `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` ). No caso raro de a UPN de uma pessoa ser alterada, sua URL de OneDrive também será alterada para incorporar o novo UPN. Se a conta de OneDrive de um usuário faz parte de uma responsabilidade não custodial e seu UPN é alterado, você precisa atualizar a responsabilidade e apontar para a nova URL de OneDrive. Para saber mais, confira [Como as alterações de UPN afetam a URL do OneDrive](/onedrive/upn-changes).

   1. **Exchange pastas públicas** - Mova a opção de alternância para a posição Todos para colocar todas as pastas públicas em sua organização Exchange Online em espera. Observe que você não pode escolher pastas públicas específicas para colocar em espera. Deixe a opção de alternância definida como **Nenhuma** se você não quiser colocar uma espera em pastas públicas.

9. Quando terminar de adicionar locais de conteúdo à espera, clique em **Próximo**.
  
10. Para criar uma espera baseada em consulta com condições, conclua o seguinte. Caso contrário, basta clicar em **Next**.
    
    - Na caixa em **Palavras-chave,** digite uma consulta de pesquisa na caixa para que apenas o conteúdo que atende aos critérios de pesquisa seja colocado em espera. Você pode especificar palavras-chave, propriedades de mensagem ou propriedades de documento, como nomes de arquivo. Você também pode usar consultas mais complexas que usam um operador Boolean, como AND, OR ou NOT. Se você deixar a caixa de palavra-chave vazia, todo o conteúdo localizado nos locais de conteúdo especificados será colocado em espera.

    - Clique  **em Adicionar** condições para adicionar uma ou mais condições para restringir a consulta de pesquisa para a espera. Cada condição adiciona uma cláusula à consulta de pesquisa KQL criada e executado quando você cria a isenção. Por exemplo, você pode especificar um intervalo de datas para que os documentos de email ou site criados dentro do intervalo de datas sejam colocados em espera. Uma condição está logicamente conectada à consulta de palavra-chave (especificada na caixa de palavra-chave) pelo operador AND. Isso significa que os itens devem atender à consulta de palavra-chave e à condição a ser colocada em espera.

     Para obter mais informações sobre como criar uma consulta de pesquisa e usar condições, consulte [Keyword queries and search conditions for Content Search](/office365/SecurityCompliance/keyword-queries-and-search-conditions).

11. Depois de configurar uma espera baseada em consulta, clique em **Próximo**.

12. Revise suas configurações e clique em **Criar essa espera.**

## <a name="view-hold-statistics"></a>Exibir estatísticas de espera

Após algum tempo, as informações sobre a nova ressarção serão exibidas no painel de detalhes na guia **Retém** para a espera selecionada. Essas informações incluem o número de caixas de correio e sites em espera e estatísticas sobre o conteúdo colocado em espera, como o número total e o tamanho dos itens colocados em espera e a última vez que as estatísticas de espera foram calculadas. Essas estatísticas de espera ajudam a identificar quanto conteúdo está relacionado ao caso de Descoberta e Está sendo mantido.

Lembre-se das seguintes coisas sobre estatísticas de espera:

- O número total de itens em espera indica o número de itens de todas as fontes de conteúdo colocadas em espera. Se você tiver criado uma ressarção baseada em consulta, essa estatística indicará o número de itens que corresponderão à consulta.
  
- O número de itens em espera também inclui itens não índicedos encontrados nos locais de conteúdo. Observe que, se você criar uma espera baseada em consulta, todos os itens não índicedos nos locais de conteúdo serão colocados em espera. Isso inclui itens nãoindexados que não corresponderem aos critérios de pesquisa de uma espera baseada em consulta e itens não índicedos que podem ficar fora de uma condição de intervalo de datas. Isso é diferente do que acontece quando você executar uma Pesquisa de Conteúdo, na qual itens não indexados que não corresponderem à consulta de pesquisa ou são excluídos por uma condição de intervalo de datas não estão incluídos nos resultados da pesquisa. Para obter mais informações sobre itens não indexados, consulte [Itens parcialmente indexados na Pesquisa](partially-indexed-items-in-content-search.md)de Conteúdo em Office 365 . 

- Você pode obter as estatísticas de espera mais recentes clicando em Atualizar estatísticas para executar uma estimativa de pesquisa que calcula o número atual de itens em espera.

- Se necessário, clique em Atualizar na barra de ferramentas para atualizar as estatísticas de espera no painel de detalhes.

- É normal que o número de itens em espera aumente com o tempo, pois os usuários cuja caixa de correio ou site está em espera geralmente estão enviando ou recebendo novas mensagens de email e criando novos documentos SharePoint e OneDrive for Business.

- Se um site SharePoint ou uma conta OneDrive for movido para uma região diferente em um ambiente multi-geo, as estatísticas desse site não serão incluídas nas estatísticas de espera. No entanto, o conteúdo no site ainda estará em espera. Além disso, se um site for movido para uma região diferente, a URL exibida na espera não será atualizada. Você terá que editar a espera e atualizar a URL.

## <a name="place-a-hold-on-microsoft-teams-and-office-365-groups"></a>Colocar uma espera em grupos Microsoft Teams e Office 365

Microsoft Teams são construídos com base Office 365 Grupos. Portanto, colocá-los em espera Advanced eDiscovery é muito semelhante.

- **Como mapear um site Microsoft 365 Grupos ou Microsoft Teams para um custodiado? E sobre a colocação de uma ressalção não custodial Microsoft 365 Grupos e Microsoft Teams?** Microsoft Teams são criadas com base Microsoft 365 Grupos. Portanto, colocá-los em espera em um caso de Descoberta eDiscovery é muito semelhante. Lembre-se das seguintes coisas ao colocar Microsoft 365 Grupos e Microsoft Teams em espera.
  - Para colocar o conteúdo localizado em Microsoft 365 Grupos e Microsoft Teams em espera, você precisa especificar a caixa de correio e SharePoint site associados a um grupo ou equipe.
  
  - Execute o cmdlet **Get-UnifiedGroup** no Exchange Online para exibir propriedades para um Microsoft 365 Group ou Microsoft Team. Essa é uma boa maneira de obter a URL do site associado a um grupo Microsoft 365 grupo ou uma Equipe da Microsoft. Por exemplo, o comando abaixo exibe as propriedades selecionadas para um grupo do Microsoft 365 chamado de Equipe de Liderança Sênior:


    ```console
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Para executar o cmdlet Get-UnifiedGroup, é preciso ter atribuído a função de Destinatários Somente Leitura no Exchange Online ou ser membro de um grupo de funções atribuído à função de Destinatários Somente Leitura.

 - Quando a caixa de correio de um usuário é pesquisada, qualquer Microsoft 365 Grupo ou Equipe da Microsoft da que o usuário é membro não será pesquisado. Da mesma forma, quando você coloca uma Microsoft 365 de grupo ou da Equipe da Microsoft, somente a caixa de correio de grupo e o site do grupo são colocados em espera; as caixas de correio e OneDrive for Business sites de membros do grupo não serão colocados em espera, a menos que você as adicione explicitamente como custodiantes ou coloque suas fontes de dados em espera. Portanto, se você precisar colocar um grupo Microsoft 365 ou a Equipe da Microsoft em espera para um custodiante específico, considere mapear o site do grupo e a caixa de correio de grupo para o custodiante (Consulte Managing Custodians in Advanced eDiscovery). Se o Microsoft 365 grupo ou a Equipe da Microsoft não for atribuível a um único custodiante, considere adicionar a origem a uma issão não custodial. 
 
 - Para obter uma lista dos membros de um grupo Microsoft 365 ou da Microsoft Team, você pode exibir as propriedades na página Grupos > Home no centro de administração do Microsoft 365. Como alternativa, execute o comando a seguir no PowerShell do Exchange Online:

   ```powershell
   Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
   ```

    > [!NOTE]
    > Para executar o cmdlet **Get-UnifiedGroupLinks**, é preciso ter atribuído a função de Destinatários Somente Leitura no Exchange Online ou ser um membro de um grupo de funções atribuído à função Destinatários Somente Leitura.

- As conversas de canal que fazem parte de um canal Microsoft Teams são armazenadas na caixa de correio associada à Equipe. Da mesma forma, os arquivos que os membros da equipe compartilham em um canal são armazenados no site do SharePoint da equipe. Portanto, você precisa colocar a caixa de correio da Equipe da Microsoft e o site SharePoint em espera para manter conversas e arquivos em um canal.
  
- Como alternativa, as conversas que fazem parte da lista de chat no Microsoft Teams são armazenadas na caixa de correio dos usuários que participam do chat.  Os arquivos que um usuário compartilha em conversas de Chat são armazenados OneDrive for Business site do usuário que compartilha o arquivo. Portanto, você precisa colocar as caixas de correio de usuário individuais e OneDrive for Business sites em espera para manter conversas e arquivos na lista chat. 
  
- Cada microsoft team ou canal de equipe contém um Wiki para anotações e colaboração. O conteúdo Wiki é salvo automaticamente em um arquivo com um formato .mht. Esse arquivo é armazenado na biblioteca de documentos de Dados do Wiki do Teams no site do SharePoint da equipe. Você pode colocar o conteúdo no Wiki em espera, colocando o site do Microsoft Office SharePoint Online da equipe em espera.

  > [!NOTE]
  > A capacidade de reter conteúdo wiki para uma Equipe da Microsoft ou canal de equipe (quando você coloca o site SharePoint de equipe em espera) foi lançada em 22 de junho de 2017. Se um site de equipe estiver em espera, o conteúdo wiki será mantido a partir dessa data. No entanto, se um site de equipe estiver em espera e o conteúdo wiki tiver sido excluído antes de 22 de junho de 2017, o conteúdo wiki não foi mantido.
