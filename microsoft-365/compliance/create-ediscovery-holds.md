---
title: Criar retém de Descoberta e em um caso de Descoberta Principal
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
description: Você pode criar uma responsabilidade associada a um caso core de Descoberta eDiscovery Microsoft 365 preservar conteúdo relevante para uma investigação ou caso jurídico.
ms.openlocfilehash: 61bbe2e8d2713c2960105e2ec4eb4beffcd4306e
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311589"
---
# <a name="create-an-ediscovery-hold"></a>Criar uma retenção de Descoberta Eletrônica

Você pode usar um caso core de Descoberta eDiscovery para criar ressarces para preservar conteúdo que pode ser relevante para o caso. Você pode colocar uma espera nas caixas de correio Exchange e OneDrive for Business contas de pessoas que você está investigando no caso. Você também pode colocar uma espera nas caixas de correio e sites associados a Microsoft Teams, grupos Office 365 e grupos Yammer. Quando você coloca locais de conteúdo em espera, o conteúdo é preservado até que você remova o local do conteúdo da espera ou até que você exclua a remoção.

Depois de criar uma ressarção de Descoberta E, pode levar até 24 horas para que a espera entre em vigor.

Ao criar uma espera, você tem as seguintes opções para escopo do conteúdo preservado nos locais de conteúdo especificados:
  
- Crie uma espera infinita onde todo o conteúdo nos locais especificados é colocado em espera. Como alternativa, você pode criar uma isenção baseada em consulta, em que apenas o conteúdo nos locais especificados que corresponde a uma consulta de pesquisa é colocado em espera.

- Especifique um intervalo de datas para preservar apenas o conteúdo que foi enviado, recebido ou criado dentro desse intervalo de datas. Como alternativa, você pode manter todo o conteúdo em locais especificados, independentemente de quando ele foi enviado, recebido ou criado.
  
## <a name="how-to-create-an-ediscovery-hold"></a>Como criar uma ressarção de Descoberta

Para criar uma ressarcição de Descoberta De eDiscovery associada a um caso core de Descoberta eDiscovery:
  
1. Acesse e entre usando as credenciais da conta de usuário que foram atribuídas às permissões [https://compliance.microsoft.com](https://compliance.microsoft.com) de Descoberta eDiscoveria apropriadas.

2. No painel de navegação esquerdo do centro de conformidade Microsoft 365, clique em **Mostrar** tudo e clique em **Descoberta > Core**.

3. Na página **Descoberta Principal da Descoberta e,** clique no nome da ocorrência em que você deseja criar a responsabilidade.

4. Na página **Inicial** do caso, clique **na** guia Segurar.
  
5. Na página **Espera,** clique em **Criar**.

6. Na página **Nomear seu assistente** de espera, dê um nome à espera e adicione uma descrição opcional e clique em **Próximo**. O nome da retenção deve ser exclusivo na sua organização.

7. Na página **Escolher locais** do assistente, escolha os locais de conteúdo que você deseja colocar em espera. Você pode colocar caixas de correio, sites e pastas públicas em retenção.

    ![Escolher os locais de conteúdo para colocar em espera](../media/eDiscoveryHoldLocations.png)
  
   1. **Caixas de correio do Exchange**: configure o botão de alternância como **Ativado** e, em seguida, clique em **Escolher usuários, grupos ou equipes** para especificar as caixas de correio a colocar em espera. Use a caixa de pesquisa para localizar caixas de correio de usuário e grupos de distribuição (para colocar em retenção as caixas de correio de membros do grupo) e colocar em espera. Você também pode colocar uma responsabilidade na caixa de correio associada para uma Equipe da Microsoft, Office 365 Group e Yammer Group. Para obter mais informações sobre os dados do aplicativo que são preservados quando uma caixa de correio é colocada em espera, consulte Conteúdo armazenado em caixas de correio para [Descoberta Eletrônico](what-is-stored-in-exo-mailbox.md).

   1. **Sites do SharePoint**: configure o botão de alternância como **Ativado** e, em seguida, clique em **Escolher sites** para especificar sites do SharePoint e contas do OneDrive para colocar em espera. Digite a URL de cada site que você deseja colocar em espera. Você também pode adicionar a URL para o site SharePoint para uma Equipe da Microsoft, Office 365 Group ou um Yammer Group.
  
   1. **Pastas públicas do Exchange**: configure o botão de alternância como **Ativado** para colocar todas as pastas públicas em sua organização do Exchange Online em espera. Você não pode escolher pastas públicas específicas para colocar em espera. Deixe o botão de alternância desligado se você não quiser colocar pastas públicas em espera.

   > [!NOTE]
   > Você deve adicionar pelo menos um local de conteúdo à espera. Caso contrário, as estatísticas de espera de DescobertaSubrida mostrarão que nenhum item está em espera.

8. Quando terminar de adicionar locais à espera, clique em **Próximo**.

9. Para criar uma ressarção baseada em consulta usando palavras-chave ou condições, conclua as etapas a seguir. Para preservar todo o conteúdo nos locais de conteúdo especificados, clique em **Próximo**.

    ![Criar uma espera baseada em consulta com palavras-chave e condições](../media/eDiscoveryHoldQuery.png)
  
    1. Na caixa em **Palavras-chave,** digite uma consulta para preservar apenas o conteúdo que corresponde aos critérios de consulta. Você pode especificar palavras-chave, propriedades de mensagem de email ou propriedades do site, como nomes de arquivo. Você também pode usar consultas mais complexas que usam um operador Boolean, como **AND**, **OR** ou **NOT**.

    2. Clique **em Adicionar condição** para adicionar uma ou mais condições para restringir a consulta para a espera. Cada condição adiciona uma cláusula à consulta de pesquisa KQL criada e executado quando você cria a isenção. Por exemplo, você pode especificar um intervalo de datas para que os documentos de email ou site criados dentro do intervalo de datas sejam preservados. Uma condição é conectada logicamente à consulta de  palavra-chave (especificada na caixa Palavras-chave) e a outras condições pelo **operador AND.** Isso significa que os itens devem atender à consulta de palavra-chave e à condição a ser preservada.

    Para obter mais informações sobre como criar uma consulta de pesquisa e usar condições, consulte Consultas de palavra-chave e condições de pesquisa [para eDiscovery](keyword-queries-and-search-conditions.md).

10. Depois de configurar uma espera baseada em consulta, clique em **Próximo**.

11. Revise suas configurações (e edite-as se necessário) e clique em **Enviar**.

## <a name="query-based-holds-placed-on-sites"></a>Retém baseadas em consultas colocadas em sites

Lembre-se das seguintes coisas ao colocar uma espera de Descoberta eDiscovery baseada em consulta em documentos localizados em SharePoint sites:

- Uma responsabilidade baseada em consulta preserva inicialmente todos os documentos em um site por um curto período de tempo após a exclusão. Isso significa que, quando um documento for excluído, ele será movido para a biblioteca de Reter Preservação, mesmo que ele não corresponder aos critérios de espera baseada em consulta. No entanto, documentos excluídos que não corresponderem a uma espera baseada em consulta serão removidos por um trabalho de timer que processa a biblioteca de Preservação de Espera. O trabalho de timer é executado periodicamente e compara todos os documentos na biblioteca de Retenção de Preservação com seus retenções de Descoberta eDiscovery baseada em consulta (e outros tipos de retenção e políticas de retenção). O trabalho de timer exclui os documentos que não corresponderem a uma ressarção baseada em consulta e preserva os documentos que fazem.

- As respeções baseadas em consultas não devem ser usadas para executar a preservação direcionada, como a preservação de documentos em uma pasta ou site específico ou usando outros critérios de espera baseados em local. Fazer isso pode ter resultados não intencionados. Recomendamos usar critérios de espera não baseados em local, como palavras-chave, intervalos de datas ou outras propriedades de documento para preservar documentos do site.

## <a name="ediscovery-hold-statistics"></a>Estatísticas de espera de Descobertas EDiscovery

Depois de criar uma bloqueio de Descoberta eDiscovery, as informações sobre a nova ressalto serão exibidas na página de sobrevoo para a espera selecionada. Essas informações incluem o número de caixas de correio e sites em espera e estatísticas sobre o conteúdo colocado em espera, como o número total e o tamanho dos itens colocados em espera e a última vez que as estatísticas de espera foram calculadas. Essas estatísticas de espera ajudam a identificar a quantidade de conteúdo relacionado ao caso que está sendo preservado.
  
![Estatísticas de espera](../media/eDiscoveryHoldStatistics.png)
  
Lembre-se das seguintes coisas sobre estatísticas de espera de Descobertas EDiscovery:
  
- O número total de itens em espera indica o número de itens de todas as fontes de conteúdo colocadas em espera. Se você tiver criado uma ressarção baseada em consulta, essa estatística indicará o número de itens que corresponderão à consulta.

- O número de itens em espera também inclui itens não índicedos encontrados nos locais de conteúdo. Se você criar uma espera baseada em consulta, todos os itens não índicedos nos locais de conteúdo serão colocados em espera. Isso inclui itens nãoindexados que não corresponderem aos critérios de pesquisa de uma espera baseada em consulta e itens não índicedos que podem ficar fora de uma condição de intervalo de datas. Isso é diferente do que acontece quando você executar uma pesquisa, na qual itens não indexados que não corresponderem à consulta de pesquisa ou são excluídos por uma condição de intervalo de datas não estão incluídos nos resultados da pesquisa. Para obter mais informações sobre itens não indexados, consulte [Itens parcialmente indexados.](partially-indexed-items-in-content-search.md)

- Você pode obter as estatísticas de  espera mais recentes clicando em Atualizar estatísticas para reprisar uma estimativa de pesquisa que calcula o número atual de itens em espera.

- É normal que o número de itens em espera aumente com o tempo, pois os usuários cuja caixa de correio ou site está em espera geralmente estão enviando ou recebendo novas mensagens de email e criando novos documentos no SharePoint e OneDrive.

- Se uma caixa de correio Exchange, um site SharePoint ou uma conta OneDrive for movida para uma região diferente em um ambiente multi-geo, as estatísticas desse site não serão incluídas nas estatísticas de espera. Mas o conteúdo nesses locais ainda será preservado. Além disso, se uma caixa de correio ou site for movido para uma região diferente, o endereço SMTP ou URL exibido na espera não será atualizado automaticamente. Você terá que editar a espera e atualizar a URL ou o endereço SMTP para que os locais de conteúdo sejam novamente incluídos nas estatísticas de espera

## <a name="search-locations-on-ediscovery-hold"></a>Locais de pesquisa em espera de Descoberta e Descoberta

Quando você [procura](search-for-content-in-core-ediscovery.md) conteúdo em um caso de Descoberta Básica, pode configurar rapidamente a pesquisa para apenas pesquisar os locais de conteúdo que foram colocados em uma responsabilidade associada ao caso.

Selecione a **opção Locais em espera** para pesquisar todos os locais de conteúdo que foram colocados em espera. Se o caso contiver vários ressarces de Descoberta e, os locais de conteúdo de todos os ressarces serão pesquisados quando você selecionar essa opção. Além disso, se um local de conteúdo foi colocado em uma espera baseada em consulta, somente os itens que corresponderem à consulta de espera serão pesquisados quando você executar a pesquisa. Em outras palavras, somente o conteúdo que corresponde aos critérios de espera e aos critérios de pesquisa é retornado com os resultados da pesquisa. Por exemplo, se um usuário foi colocado em uma responsabilidade de caso baseada em consulta que preserva itens que foram enviados ou criados antes de uma data específica, somente esses itens serão pesquisados. Isso é feito conectando a consulta de espera de caso e a consulta de pesquisa por um **operador AND.**

Aqui estão algumas outras coisas a ter em mente ao pesquisar locais em espera de Descoberta e:

- Se um local de conteúdo faz parte de várias resções no mesmo caso, as consultas de espera são combinadas por operadores **OR** quando você pesquisa esse local de conteúdo usando a opção de conteúdo de todas as ocorrências. Da mesma forma, se um local de conteúdo faz parte de duas resções diferentes, em que uma é baseada em consulta e a outra é uma isenção infinita (onde todo o conteúdo é colocado em espera), todo o conteúdo é pesquisa por causa da ressarção infinita.

- Se uma pesquisa estiver configurada para locais de pesquisa em espera e, em seguida, você alterar uma remoção de Descoberta Eletrônica no caso (adicionando ou removendo um local ou alterando uma consulta de espera), a configuração de pesquisa será atualizada com essas alterações. No entanto, você precisa reprisar a pesquisa após a alteração da espera para atualizar os resultados da pesquisa.

- Se vários ressarcedores de Descoberta E são colocados em um único local em um caso de Descoberta e você seleciona para pesquisar locais em espera, o número máximo de palavras-chave para essa consulta de pesquisa é 500. Isso porque a pesquisa combina todas as resções baseadas em consulta usando o **operador OR.** Se houver mais de 500 palavras-chave nas consultas de espera combinadas e na consulta de pesquisa, todo o conteúdo da caixa de correio será pesquisado, e não apenas o conteúdo que corresponde à ocorrência baseada em consulta será ressarte.

- Se uma espera de Descoberta De eDiscovery tiver um status de **On (Pendente),** você ainda poderá pesquisar os locais em espera enquanto a espera estiver sendo 100% 100% 1000.

## <a name="preserve-content-in-microsoft-teams"></a>Preservar conteúdo em Microsoft Teams

As conversas que fazem parte de um Microsoft Teams são armazenadas na caixa de correio associada à Equipe da Microsoft. Da mesma forma, os arquivos que os membros da equipe compartilham em um canal são armazenados no site do SharePoint da equipe. Portanto, você precisa colocar a caixa de correio de equipe e o site SharePoint em espera de Descoberta Eletrônico para preservar conversas e arquivos em um canal.

Como alternativa, as conversas que fazem parte da lista chat no Teams (chamadas de *chats 1:1* ou chats de grupo *1:N*) são armazenadas nas caixas de correio dos usuários que participam do chat. E os arquivos que os usuários compartilham em conversas de chat são armazenados OneDrive conta do usuário que compartilha o arquivo. Portanto, você precisa adicionar as caixas de correio de usuário individuais e OneDrive contas a uma responsabilidade de Descoberta Eletrônico para preservar conversas e arquivos na lista de chat. É uma boa ideia colocar em espera as caixas de correio de membros de uma Equipe da Microsoft, além de colocar a caixa de correio e o site de equipe em espera.

> [!NOTE]
> Se sua organização tiver uma implantação híbrida Exchange (ou sua organização sincronizar uma organização local Exchange com o Office 365) e tiver habilitado o Microsoft Teams, os usuários locais poderão usar o aplicativo de chat Teams e participar de chats 1:1 e chats de grupo 1:N. Essas conversas são armazenadas no armazenamento baseado em nuvem associado a um usuário local. Se um usuário local for colocado em uma responsabilidade de Descoberta Teams, o conteúdo de chat Teams no armazenamento baseado em nuvem será preservado. Para obter mais informações, confira [Pesquisar dados de bate-papo do Teams para usuários locais](search-cloud-based-mailboxes-for-on-premises-users.md).

Para obter mais informações sobre como Teams conteúdo, consulte Colocar um usuário [Microsoft Teams ou equipe em espera legal](/MicrosoftTeams/legal-hold).

### <a name="preserve-card-content"></a>Preservar o conteúdo do cartão

Da mesma forma, o conteúdo de cartão gerado por aplicativos em canais Teams, chats 1:1 e chats de grupo 1:N é armazenado em caixas de correio e é preservado quando uma caixa de correio é colocada em uma espera de Descoberta Eletrônico. Um *cartão* é um contêiner de interface de usuário para pequenos pedaços de conteúdo. Os cartões podem ter várias propriedades e anexos e podem incluir botões que disparam ações de cartão. Para obter mais informações, consulte [Cartões](/microsoftteams/platform/task-modules-and-cards/what-are-cards). Como outros conteúdos de equipes, onde o conteúdo do cartão é armazenado é baseado em onde o cartão foi usado. O conteúdo dos cartões usados em um canal Teams é armazenado na caixa de correio do grupo Teams. O conteúdo do cartão para bate-papos individuais e 1xN é armazenado nas caixas de correio dos participantes do bate-papo.

### <a name="preserve-meeting-and-call-information"></a>Preservar informações de reunião e chamada

As informações de resumo para reuniões e chamadas em um canal Teams também são armazenadas nas caixas de correio dos usuários que discam para a reunião ou chamada. Esse conteúdo também é preservado quando uma isenção de Descoberta Eletrônico é colocada em caixas de correio de usuário.

### <a name="preserve-content-in-private-channels"></a>Preservar conteúdo em canais privados

A partir de fevereiro de 2020, também a iniciamos a capacidade de preservar o conteúdo em canais privados. Como os chats de canal privado são armazenados nas caixas de correio dos participantes do chat, colocar uma caixa de correio de usuário em espera de Descoberta Eletrônico preservará chats de canal privado. Além disso, se uma caixa de correio de usuário foi colocada em uma suspensão de Descoberta Automática antes de fevereiro de 2020, a suspensão agora se aplicará automaticamente às mensagens de canal privado armazenadas nessa caixa de correio. A preservação de arquivos compartilhados em canais privados também é suportada.

### <a name="preserve-wiki-content"></a>Preservar conteúdo wiki

Cada equipe ou canal de equipe também contém um Wiki para anotações e colaboração. O conteúdo Wiki é salvo automaticamente em um arquivo com um formato .mht. Esse arquivo é armazenado na biblioteca de documentos de Dados do Wiki do Teams no site do SharePoint da equipe. Você pode preservar o conteúdo wiki adicionando o site de SharePoint da equipe a uma ressarção de Descoberta e.

> [!NOTE]
> A capacidade de preservar o conteúdo wiki para um canal de equipe ou equipe (quando você coloca o site SharePoint da equipe em espera) foi lançada em 22 de junho de 2017. Se um site de equipe estiver em espera, o conteúdo wiki será mantido a partir dessa data. No entanto, se um site de equipe estiver em espera e o conteúdo wiki tiver sido excluído antes de 22 de junho de 2017, o conteúdo wiki não foi preservado.

### <a name="office-365-groups"></a>Grupos do Office 365

Teams é criado com base Office 365 Grupos. Portanto, colocar Office 365 Grupos em espera de Descoberta e é semelhante colocando Teams conteúdo em espera.

Lembre-se das seguintes coisas ao colocar os grupos Teams e Office 365 em uma espera de Descoberta De eDiscovery:

- Conforme explicado anteriormente, para colocar o conteúdo localizado em grupos Teams e Office 365 em espera, você precisa especificar a caixa de correio e SharePoint site associado a um grupo ou equipe.

- Execute o cmdlet **Get-UnifiedGroup** Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) para exibir propriedades para Teams e Office 365 Grupos. Essa é uma boa maneira de obter a URL do site associado a uma equipe ou Office 365 Grupo. Por exemplo, o comando abaixo exibe as propriedades selecionadas para um grupo do Office365 chamado de Equipe de Liderança Sênior:

    ```text
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl

    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Para executar o cmdlet **Get-UnifiedGroup**, é preciso ter atribuído a função de Destinatários Somente Leitura no Exchange Online ou ser membro de um grupo de funções atribuído à função de Destinatários Somente Leitura. 
  
- Quando a caixa de correio de um usuário é pesquisada, qualquer Equipe ou grupo do Office 365 que o usuário é membro não será pesquisado. Da mesma forma, quando você coloca um Team ou Office 365 Group em espera de Descoberta eDiscovery, somente a caixa de correio de grupo e o site de grupo são colocados em espera. As caixas de correio e OneDrive for Business de membros do grupo não são colocadas em espera, a menos que você as adicione explicitamente à responsabilidade de Descoberta Eletrônico. Portanto, se você tiver que colocar uma equipe ou um grupo Office 365 em espera por um motivo legal, considere adicionar as caixas de correio e OneDrive contas de membros da equipe ou grupo na mesma espera.

- Para obter uma lista dos membros de um Team ou Office 365 Group, você pode exibir as propriedades na página **Grupos** no centro de administração Microsoft 365. Como alternativa, execute o comando a seguir no PowerShell do Exchange Online:

    ```powershell
    Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
    ```

    > [!NOTE]
    > Para executar o cmdlet **Get-UnifiedGroupLinks**, é preciso ter atribuído a função de Destinatários Somente Leitura no Exchange Online ou ser um membro de um grupo de funções atribuído à função Destinatários Somente Leitura.

## <a name="preserve-content-in-onedrive-accounts"></a>Preservar conteúdo em OneDrive contas

Para coletar uma lista das URLs para os sites OneDrive for Business em sua organização para que você possa adicioná-los a uma responsabilidade ou pesquisa associada a um caso de Descoberta eDiscovery, consulte Create a list [of all OneDrive locations in](/onedrive/list-onedrive-urls)your organization . O script neste artigo cria um arquivo de texto que contém uma lista de todos os OneDrive sites em sua organização. Para executar esse script, é necessário instalar e usar o Shell de Gerenciamento Online do SharePoint. Não se esqueça de acrescentar a URL do domínio MySite da organização para cada site do OneDrive que você deseja pesquisar. Este é o domínio que contém todos os seus OneDrive; por exemplo, `https://contoso-my.sharepoint.com`. Veja um exemplo de URL para o site do OneDrive de um usuário: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.

> [!IMPORTANT]
> A URL da conta de usuário OneDrive inclui o nome principal do usuário (UPN) (por exemplo, `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` ). No caso raro de a UPN de uma pessoa ser alterada, sua URL de OneDrive também será alterada para incorporar o novo UPN. Se a conta de OneDrive de um usuário faz parte de uma remoção de Descoberta Automática, antiga e sua UPN é alterada, você precisa atualizar a responsabilidade e você terá que atualizar a responsabilidade e adicionar a nova URL de OneDrive do usuário e remover a antiga. Para saber mais, confira [Como as alterações de UPN afetam a URL do OneDrive](/onedrive/upn-changes).

## <a name="removing-content-locations-from-an-ediscovery-hold"></a>Removendo locais de conteúdo de uma remoção de descoberta de ediscovery

Depois que uma caixa de correio, SharePoint site ou uma conta OneDrive for  removida de uma isenção de descoberta de eDiscovery, será aplicado um atraso. Isso significa que a remoção real da responsabilidade é adiada por 30 dias para impedir que os dados são excluídos permanentemente (apagados) de um local de conteúdo. Isso oferece aos administradores a oportunidade de pesquisar ou recuperar o conteúdo que será limpo após a remoção de uma remoção de uma descoberta de eDiscovery. Os detalhes de como a espera de atraso funciona para caixas de correio e sites são diferentes.

- **Caixas de correio:** Uma espera de atraso é colocada em uma caixa de correio na próxima vez que o Assistente de Pasta Gerenciada processa a caixa de correio e detecta que uma remoção de uma remoção de descoberta eletrônico. Especificamente, um atraso é aplicado a uma caixa de correio quando o Assistente de Pasta Gerenciada define uma das seguintes propriedades de caixa de correio como **True**:

   - **DelayHoldApplied:** Essa propriedade se aplica ao conteúdo relacionado a email (gerado por pessoas que usam Outlook e Outlook na Web) que são armazenados na caixa de correio de um usuário.

   - **DelayReleaseHoldApplied:** Essa propriedade se aplica ao conteúdo baseado em nuvem (gerado por aplicativos que não Outlook como Microsoft Teams, Microsoft Forms e Microsoft Yammer) armazenados na caixa de correio de um usuário. Os dados de nuvem gerados por um aplicativo Microsoft geralmente são armazenados em uma pasta oculta na caixa de correio de um usuário.

   Quando um atraso é colocado na caixa de correio (quando uma das propriedades anteriores é definida como **True**), a caixa de correio ainda é considerada em espera por uma duração de espera ilimitada, como se a caixa de correio estivesse em Contencioso. Após 30 dias, a espera de atraso expira e o Microsoft 365 tentará remover automaticamente a espera (definindo a propriedade DelayHoldApplied ou DelayReleaseHoldApplied como **False**) para que a suspensão seja removida. Depois que uma dessas propriedades for definida como **False**, os itens correspondentes marcados para remoção serão limpos na próxima vez que a caixa de correio for processada pelo Assistente de Pasta Gerenciada.

   Para saber mais, confira [Gerenciar caixas de correios em retenção por atraso](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

- **SharePoint e OneDrive sites:** Qualquer SharePoint ou OneDrive conteúdo que está sendo mantido na biblioteca de Reter Preservação não é excluído durante o período de espera de 30 dias depois que um site é removido de uma responsabilidade de Descoberta Virtual. Isso é semelhante ao que acontece quando um site é liberado de uma política de retenção. Além disso, você não pode excluir manualmente esse conteúdo na biblioteca de Preservação de Espera durante o período de espera de 30 dias. 

   Para obter mais informações, [consulte Liberando uma política de retenção](retention.md#releasing-a-policy-for-retention).

Uma espera de atraso também é aplicada a locais de conteúdo em espera quando você fecha um caso de Descoberta Principal de Descoberta e, por isso, as regiões de espera são desligadas quando uma ocorrência é fechada. Para obter mais informações sobre como fechar um caso, consulte [Close, reopen, and delete a Core eDiscovery case](close-reopen-delete-core-ediscovery-cases.md).

## <a name="ediscovery-hold-limits"></a>Limites de espera de Descoberta eDiscovery

A tabela a seguir lista os limites para os casos de Descoberta e de ocorrências.

  | Descrição do limite | Limite |
  |:-----|:-----|
  |Número máximo de casos para uma organização.  <br/> |Sem limite  <br/> |
  |Número máximo de retém descobertas de eDiscovery para uma organização.  <br/> |10.000  <br/> |
  |Número máximo de caixas de correio em uma única parada de Descoberta Eletrônico. Esse limite inclui o total combinado de caixas de correio de usuário e as caixas de correio associadas Microsoft 365 grupos, Microsoft Teams e Yammer Grupos.  <br/> |1.000  <br/> |
  |Número máximo de sites em uma única parada de Descoberta e. Esse limite inclui o total combinado de sites OneDrive for Business, sites SharePoint e os sites associados a grupos Microsoft 365, Microsoft Teams e grupos Yammer.  <br/> |100  <br/> |
  |Número máximo de casos exibidos na home page da Descoberta e o número máximo de itens exibidos nas guias Regiões, Pesquisas e Exportação dentro de uma ocorrência. <sup>1</sup> |1.000|
  |||

   > [!NOTE]
   > <sup>1</sup> Para exibir uma lista de mais de 1.000 casos, retém, pesquisas ou exportações, você pode usar o cmdlet Office 365 Security & Compliance do PowerShell:
   >
   > - [Get-ComplianceCase](/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)
