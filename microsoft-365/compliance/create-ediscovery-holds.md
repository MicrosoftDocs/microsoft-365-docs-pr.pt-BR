---
title: Criar bloqueios de descoberta eletrônica em um caso de descoberta eletrônica principal
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
description: Você pode criar uma retenção associada a uma caixa de descoberta eletrônica principal para preservar o conteúdo que pode ser relevante para uma investigação.
ms.openlocfilehash: 41e5f21d36456eb39999afa71852b169de864356
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412850"
---
# <a name="create-an-ediscovery-hold"></a>Criar uma retenção de Descoberta Eletrônica

Você pode usar um caso de descoberta eletrônica principal para criar isenções para preservar o conteúdo que pode ser relevante para o caso. Você pode colocar uma retenção nas caixas de correio do Exchange e no OneDrive for Business contas de pessoas que você está investigando no caso. Você também pode colocar uma retenção nas caixas de correio e nos sites associados ao Microsoft Teams, aos grupos do Office 365 e aos grupos do Yammer. Quando você coloca os locais de conteúdo em espera, o conteúdo é preservado até que você remova o bloqueio do local de conteúdo ou até que você exclua a isenção.

Após criar uma retenção de descoberta eletrônica, pode levar até 24 horas para que a retenção tenha efeito. 

Ao criar uma isenção, você tem as seguintes opções para escopo o conteúdo que é preservado nos locais de conteúdo especificado:
  
- Você cria uma retenção infinita onde todo o conteúdo é colocado em espera. Como alternativa, você pode criar uma isenção baseada em consulta, onde apenas o conteúdo que corresponde a uma consulta de pesquisa é colocado em espera.

- Você pode especificar um intervalo de datas para preservar somente o conteúdo que foi enviado, recebido ou criado dentro desse intervalo de datas. Como alternativa, você pode manter todo o conteúdo independentemente de quando ele foi enviado, recebido ou criado.

> [!NOTE]
> Você pode ter um máximo de 10.000 de descoberta eletrônica em todos os casos de descoberta eletrônica principal em sua organização.
  
## <a name="how-to-create-an-ediscovery-hold"></a>Como criar uma retenção de descoberta eletrônica

Para criar uma retenção de descoberta eletrônica associada a um caso de descoberta eletrônica principal:
  
1. Acesse [https://compliance.microsoft.com](https://compliance.microsoft.com) e entre usando as credenciais da conta de usuário que receberam as permissões de descoberta eletrônica apropriadas.

2. No painel de navegação esquerdo do centro de conformidade da Microsoft 365, clique em **Mostrar tudo**e, em seguida, clique em **descoberta eletrônica > Core**.

3. Na página de **descoberta eletrônica principal** , selecione o caso para o qual você deseja criar a retenção e clique em **abrir caso**.

4. Na **Home** Page do caso, clique na guia **isenções** .
  
5. Na página **isenções** , clique em **criar**.

6. Na página **nomear o** assistente de retenção, dê um nome à isenção e adicione uma descrição opcional e clique em **Avançar**. O nome da retenção deve ser exclusivo na sua organização.

7. Na página **locais de conteúdo** , escolha os locais de conteúdo que você deseja colocar em espera. Você pode colocar caixas de correio, sites e pastas públicas em espera.

    ![Escolher os locais de conteúdo para colocar em espera](../media/a59e4265-9151-4dbf-913f-6a4ab8db06b4.png)
  
   a. **Locais da caixa de correio** -clique em **escolher usuários, grupos ou equipes** e, em seguida, clique em **escolher usuários, grupos ou equipes** novamente para especificar as caixas de correio a serem colocadas em espera. Use a caixa de pesquisa para localizar caixas de correio de usuários e grupos de distribuição (para colocar uma retenção nas caixas de correio dos membros do grupo) para colocar em espera. Você também pode colocar uma retenção na caixa de correio associada para uma equipe da Microsoft, um grupo do Office 365 ou um grupo do Yammer. Marque a caixa de seleção usuário, grupo, equipe, clique em **escolher**e em **concluído**.

   b. **Locais de sites** -clique em **escolher sites** e clique em **escolher sites** novamente para especificar as contas do SharePoint e do onedrive para colocar em espera. Digite a URL de cada site que você deseja colocar em retenção. Você também pode adicionar a URL do site do SharePoint para uma equipe da Microsoft, um grupo do Office 365 ou um grupo do Yammer. Clique em **escolher**e em **concluído**.
  
   c. **Pastas públicas do Exchange.** Mova o controle de alternância de alternância ![ ](../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) para a posição **All** para colocar todas as pastas públicas em sua organização do Exchange Online em espera. Você não pode escolher pastas públicas específicas para colocá-las em espera. Deixe a opção de alternância definida como **nenhuma** se você não quiser colocar uma retenção em pastas públicas.

8. Quando você terminar de adicionar locais de conteúdo à isenção, clique em **Avançar**.

9. Para criar uma retenção baseada em consulta com condições, conclua o seguinte. Caso contrário, para preservar todo o conteúdo dos locais de conteúdo especificados, clique em **Avançar**

    ![Criar uma retenção baseada em consulta com condições](../media/d587b58e-d05c-4ac0-b0fe-09019e4f1063.png)
  
    a. Na caixa em **palavras-chave**, digite uma consulta de pesquisa para que apenas o conteúdo que atende aos critérios de pesquisa seja preservado. Você pode especificar palavras-chave, propriedades de mensagens de email ou propriedades do documento, como nomes de arquivos. Você também pode usar consultas mais complexas que usam um operador Boolean, como **e**, **ou ou** **não**.

    b. Clique em **Adicionar condições** para adicionar uma ou mais condições para restringir a consulta de pesquisa para a isenção. Cada condição adiciona uma cláusula à consulta de pesquisa KQL que é criada e executada quando você cria a retenção. Por exemplo, você pode especificar um intervalo de datas para que os documentos de email ou de site criados dentro do intervalo de datas sejam colocados em espera. Uma condição é conectada logicamente à consulta de palavra-chave (especificada na caixa **palavras-chave** ) pelo operador **and** . Isso significa que os itens precisam satisfazer a consulta de palavra-chave e a condição a ser preservada.

    Para obter mais informações sobre como criar uma consulta de pesquisa e usar condições, consulte [keyword queries and Search Conditions for Content Search](keyword-queries-and-search-conditions.md).

10. Depois de configurar um bloqueio baseado em consulta, clique em **Avançar**.

11. Revise suas configurações (e edite-as se necessário) e clique em **criar esta isenção**.

## <a name="ediscovery-hold-statistics"></a>Estatísticas de retenção de descoberta eletrônica

Depois de criar uma retenção de descoberta eletrônica, as informações sobre a nova retenção são exibidas na página de submenu da isenção selecionada. Essas informações incluem o número de caixas de correio e sites em espera e estatísticas sobre o conteúdo que foi colocado em espera, como o número total e o tamanho de itens colocados em retenção e a última vez que as estatísticas de retenção foram calculadas. Essas estatísticas de retenção ajudam a identificar a quantidade de conteúdo relacionada ao caso sendo preservado.
  
![Estatísticas de retenção](../media/575cfe0a-9210-4ae4-8df8-65665d66712e.png)
  
Considere as seguintes considerações sobre estatísticas de retenção de descoberta eletrônica:
  
- O número total de itens em retenção indica o número de itens de todas as fontes de conteúdo que são colocadas em espera. Se você tiver criado uma retenção baseada em consulta, essa estatística indicará o número de itens que correspondem à consulta.

- O número de itens em retenção também inclui itens não indexados encontrados nos locais de conteúdo. Se você criar uma retenção baseada em consulta, todos os itens não indexados nos locais de conteúdo são colocados em espera. Isso inclui itens não indexados que não correspondem aos critérios de pesquisa de um bloqueio baseado em consulta e itens não indexados que podem ficar fora de uma condição de intervalo de datas. Isso é diferente do que acontece quando você executa uma pesquisa, na qual os itens não indexados que não correspondem à consulta de pesquisa ou são excluídos por uma condição de intervalo de datas não são incluídos nos resultados da pesquisa. Para obter mais informações sobre itens não indexados, consulte [itens parcialmente indexados](partially-indexed-items-in-content-search.md).

- Você pode obter as estatísticas de retenção mais recentes clicando em **atualizar estatísticas** para executar novamente uma estimativa de pesquisa que calcula o número atual de itens em retenção.

- É normal para o número de itens em espera aumentar ao longo do tempo, pois os usuários cuja caixa de correio ou site está em espera geralmente estão enviando ou recebendo novas mensagens de email e criando novos documentos no SharePoint e no OneDrive.

- Se uma caixa de correio do Exchange, site do SharePoint ou uma conta do OneDrive for movida para uma região diferente em um ambiente multigeográfico, as estatísticas desse site não serão incluídas nas estatísticas de retenção. Mas o conteúdo desses locais ainda será preservado. Além disso, se uma caixa de correio ou site for movido para uma região diferente, o endereço SMTP ou a URL exibida na isenção não serão atualizadas automaticamente. Você terá que editar a isenção e atualizar a URL ou o endereço SMTP para que os locais de conteúdo estejam novamente incluídos nas estatísticas de retenção

## <a name="search-locations-on-ediscovery-hold"></a>Locais de pesquisa em retenção de descoberta eletrônica

Ao [Pesquisar conteúdo](search-for-content-in-core-ediscovery.md) em um caso de descoberta eletrônica principal, você pode configurar rapidamente a pesquisa para pesquisar apenas os locais de conteúdo que foram colocados em um bloqueio associado à ocorrência.

![Locais, locais em espera](../media/d56398aa-0b20-4500-8e26-494eab92a99f.png)

Selecione a opção **locais em espera** para pesquisar todos os locais de conteúdo que foram colocados em espera. Se o caso contiver vários bloqueios de descoberta eletrônica, os locais de conteúdo de todas as isenções serão pesquisados quando você selecionar essa opção. Além disso, se um local de conteúdo foi colocado em um bloqueio baseado em consulta, somente os itens que correspondem à consulta de retenção serão pesquisados quando você executar a pesquisa. Em outras palavras, somente o conteúdo que corresponde aos critérios de retenção e os critérios de pesquisa é retornado com os resultados da pesquisa. Por exemplo, se um usuário foi colocado em um bloqueio de caso baseado em consulta que preserva os itens que foram enviados ou criados antes de uma data específica, somente esses itens seriam pesquisados. Isso é feito conectando-se à consulta de retenção de caso e à consulta de pesquisa por um operador **and** .

Aqui estão alguns outros pontos a serem lembrados ao pesquisar locais em retenção de descoberta eletrônica:

- Se um local de conteúdo fizer parte de várias isenções dentro do mesmo caso, as consultas de retenção serão combinadas por **ou** operadores quando você pesquisar esse local de conteúdo usando a opção de conteúdo todos os casos. Da mesma forma, se um local de conteúdo fizer parte de duas isenções diferentes, onde uma delas é baseada em consulta e a outra é um bloqueio infinito (onde todo o conteúdo é colocado em espera), todo o conteúdo será pesquisado por causa da isenção.

- Se uma pesquisa estiver configurada para pesquisar locais em espera e você alterar um bloqueio de descoberta eletrônica no caso (adicionando ou removendo um local ou alterando uma consulta de retenção), a configuração de pesquisa será atualizada com essas alterações. No entanto, você precisa executar novamente a pesquisa após a alteração da retenção para atualizar os resultados da pesquisa.

- Se várias isenções de descoberta eletrônica forem colocadas em um único local em um caso de descoberta eletrônica e você selecionar para pesquisar locais em espera, o número máximo de palavras-chave para essa consulta de pesquisa será de 500. Isso ocorre porque a pesquisa combina todas as retenções baseadas em consulta usando o operador **or** . Se houver mais de 500 palavras-chave nas consultas de retenção combinada e na consulta de pesquisa, todo o conteúdo da caixa de correio será pesquisado, e não apenas o conteúdo que corresponda às isenções de caso baseados em consulta.
    
- Se um controle de descoberta eletrônica tiver um status de **ativação**, você ainda poderá pesquisar os locais em espera enquanto a retenção estiver sendo ativada.

## <a name="preserve-content-in-microsoft-teams"></a>Preservar conteúdo no Microsoft Teams

As conversas que fazem parte de um canal do Microsoft Teams são armazenadas na caixa de correio que está associada à equipe da Microsoft. Da mesma forma, os arquivos que os membros da equipe compartilham em um canal são armazenados no site do SharePoint da equipe. Portanto, você precisa colocar a caixa de correio da equipe e o site do SharePoint em retenção de descoberta eletrônica para preservar conversas e arquivos em um canal.

Como alternativa, as conversas que fazem parte da lista de chat no Microsoft Teams (chamadas de *1:1 chats* ou *1: N chats de grupo*) são armazenadas nas caixas de correio dos usuários que participam do chat. Os arquivos que os usuários compartilham em conversas de chat são armazenados na conta do OneDrive do usuário que compartilha o arquivo. Portanto, você precisa adicionar as caixas de correio de usuários individuais e as contas do OneDrive a uma retenção de descoberta eletrônica para preservar conversas e arquivos na lista de chat. É uma boa ideia colocar uma retenção nas caixas de correio dos membros de uma equipe da Microsoft, além de colocar a caixa de correio e o site em espera da equipe.

A partir de fevereiro de 2020, ativamos a capacidade de preservar o conteúdo em canais privados. Como os bate-papos de canal privado são armazenados nas caixas de correio dos participantes do bate-papo, colocar uma caixa de correio de usuário em retenção de descoberta eletrônica preservará chats de canal privado. Além disso, se uma caixa de correio de usuário foi colocada em retenção de descoberta eletrônica antes de fevereiro de 2020, a retenção será automaticamente aplicada às mensagens de canal privado armazenadas nessa caixa de correio. A preservação de arquivos compartilhados em canais privados também é suportada.

Para obter mais informações sobre como preservar o conteúdo de equipes, consulte [colocar um usuário ou uma equipe do Microsoft Teams em retenção legal](https://docs.microsoft.com/MicrosoftTeams/legal-hold).
    
> [!IMPORTANT]
> Em uma organização baseada em nuvem, os usuários que participam de conversas que fazem parte da lista de bate-papo no Microsoft Teams devem ter uma caixa de correio do Exchange Online para manter conversas de chat quando a caixa de correio é colocada em retenção de descoberta eletrônica. Isso ocorre porque as conversas que fazem parte da lista de chat são armazenadas nas caixas de correio baseadas em nuvem dos participantes do chat. Se um participante de chat não tiver uma caixa de correio do Exchange Online, você não poderá preservar essas conversas de chat. Por exemplo, em uma implantação híbrida do Exchange, os usuários com uma caixa de correio local podem ser capazes de participar de conversas que fazem parte da lista de chat no Microsoft Teams. Mas nesse caso, o conteúdo dessas conversas não pode ser preservado, pois esses usuários não possuem caixas de correio baseadas em nuvem que podem ser colocadas em espera.
  
Cada equipe ou canal de equipe também contém um wiki para anotações e colaboração. O conteúdo Wiki é salvo automaticamente em um arquivo com um formato .mht. Esse arquivo é armazenado na biblioteca de documentos de Dados do Wiki do Teams no site do SharePoint da equipe. Você pode preservar o conteúdo do wiki adicionando o site do SharePoint da equipe a um bloqueio de descoberta eletrônica.
    
> [!NOTE]
> A capacidade de preservar o conteúdo do wiki para uma equipe ou um canal de equipe (quando você coloca o site do SharePoint da equipe em espera) foi lançado em 22 de junho de 2017. Se um site de equipe estiver em espera, o conteúdo wiki será retido a partir dessa data. No entanto, se um site de equipe estiver em espera e o conteúdo wiki tiver sido excluído antes de 22 de junho de 2017, o conteúdo wiki não foi preservado.

### <a name="office-365-groups"></a>Grupos do Office 365

O Microsoft Teams é criado em grupos do Office 365. Portanto, colocar grupos do Office 365 em retenção de descoberta eletrônica é semelhante a colocar o conteúdo da equipe em espera.

Lembre-se do seguinte ao colocar o Teams e os grupos do Office 365 em uma retenção de descoberta eletrônica:

- Conforme explicado anteriormente, para colocar o conteúdo localizado no Teams e nos grupos do Office 365 em espera, você precisa especificar a caixa de correio e o site do SharePoint que estão associados a um grupo ou a uma equipe.

- Execute o cmdlet **Get-unificado** no [PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) para exibir propriedades para o Teams e grupos do Office 365. Essa é uma boa maneira de obter a URL para o site que está associado a um grupo de equipe ou do Office 365. Por exemplo, o comando abaixo exibe as propriedades selecionadas para um grupo do Office365 chamado de Equipe de Liderança Sênior:

    ```text
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl

    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Para executar o cmdlet **Get-UnifiedGroup**, é preciso ter atribuído a função de Destinatários Somente Leitura no Exchange Online ou ser membro de um grupo de funções atribuído à função de Destinatários Somente Leitura. 
  
- Quando a caixa de correio de um usuário é pesquisada, qualquer equipe ou grupo do Office 365 do qual o usuário é membro não será pesquisado. Da mesma forma, quando você coloca uma equipe ou um grupo do Office 365 em retenção de descoberta eletrônica, somente a caixa de correio de grupo e o site de grupo são colocados em espera. As caixas de correio e os sites do OneDrive for Business de membros do grupo não são colocados em espera, a menos que você os adicione explicitamente ao bloqueio de descoberta eletrônica. Portanto, se você tiver que colocar uma equipe ou um grupo do Office 365 em espera por um motivo legal, considere adicionar as caixas de correio e as contas do OneDrive de membros da equipe ou do grupo na mesma isenção.

- Para obter uma lista dos membros de um grupo Team ou Office 365, você pode exibir as propriedades na página **grupos** no centro de administração do Microsoft 365. Como alternativa, execute o comando a seguir no PowerShell do Exchange Online: 
    
    ```powershell
    Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
    ```

    > [!NOTE]
    > Para executar o cmdlet **Get-UnifiedGroupLinks**, é preciso ter atribuído a função de Destinatários Somente Leitura no Exchange Online ou ser um membro de um grupo de funções atribuído à função Destinatários Somente Leitura.

## <a name="onedrive-accounts"></a>Contas do OneDrive

Para coletar uma lista das URLs para os sites do OneDrive for Business em sua organização para que você possa adicioná-los a uma isenção ou a uma pesquisa associada a uma ocorrência de descoberta eletrônica, consulte [criar uma lista de todos os locais do onedrive em sua organização](https://docs.microsoft.com/onedrive/list-onedrive-urls). O script neste artigo cria um arquivo de texto que contém uma lista de todos os sites do OneDrive em sua organização. Para executar esse script, é necessário instalar e usar o Shell de Gerenciamento Online do SharePoint. Não se esqueça de acrescentar a URL do domínio MySite da organização para cada site do OneDrive que você deseja pesquisar. Este é o domínio que contém todos os seus OneDrive; por exemplo, `https://contoso-my.sharepoint.com`. Veja um exemplo de URL para o site do OneDrive de um usuário: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.

> [!IMPORTANT]
> A URL de uma conta do usuário do OneDrive inclui seu nome de princípio de usuário (por exemplo, `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` ). No caso raro que o UPN de uma pessoa seja alterado, a URL do OneDrive também será alterada para incorporar o novo UPN. Se a conta do OneDrive de um usuário fizer parte de um controle de descoberta eletrônica, o antigo e o respectivo UPN serão alterados, você precisará atualizar a retenção e será necessário atualizar a retenção e adicionar a nova URL do OneDrive do usuário e remover a antiga. Para saber mais, confira [Como as alterações de UPN afetam a URL do OneDrive](https://docs.microsoft.com/onedrive/upn-changes).

## <a name="removing-content-locations-from-an-ediscovery-hold"></a>Removendo locais de conteúdo de um bloqueio de descoberta eletrônica

Depois que uma caixa de correio, um site do SharePoint ou uma conta do OneDrive for removido de uma descoberta eletrônica, uma *retenção de atraso* será aplicada. Isso significa que a remoção real da retenção está atrasada por 30 dias para evitar que os dados sejam excluídos permanentemente (removidos) de um local de conteúdo. Isso dá aos administradores uma oportunidade de Pesquisar ou recuperar conteúdo que será removido depois que uma retenção de descoberta eletrônica for removida. Os detalhes de como o atraso de espera funciona para caixas de correio e sites são diferentes.

- **Caixas de correio:** Uma retenção de atraso é feita em uma caixa de correio na próxima vez que o assistente de pasta gerenciada processa a caixa de correio e detecta que uma retenção de descoberta eletrônica foi removida. Especificamente, uma retenção de atraso é aplicada a uma caixa de correio quando o assistente de pasta gerenciada define uma das seguintes propriedades de caixa de correio como **true**: 

   - **DelayHoldApplied:** Essa propriedade se aplica a conteúdo relacionado a email (gerado por pessoas que usam o Outlook e o Outlook na Web) que está armazenado na caixa de correio de um usuário.

   - **DelayReleaseHoldApplied:** Essa propriedade se aplica a conteúdo baseado em nuvem (gerado por aplicativos que não são do Outlook, como o Microsoft Teams, o Microsoft Forms e o Microsoft Yammer) que é armazenado na caixa de correio de um usuário. Os dados de nuvem gerados por um aplicativo da Microsoft geralmente são armazenados em uma pasta oculta da caixa de correio de um usuário.

   Quando uma espera de atraso é colocada na caixa de correio (quando qualquer uma das propriedades anteriores é definida como **true**), a caixa de correio ainda é considerada em espera por uma duração de retenção ilimitada, como se a caixa de correio estivesse em retenção de litígio. Após 30 dias, o atraso esperado expira e o Microsoft 365 tentará automaticamente remover o atraso de espera (definindo a propriedade DelayHoldApplied ou DelayReleaseHoldApplied como **false**) para que a retenção seja removida. Após qualquer uma dessas propriedades ser definida como **false**, os itens correspondentes marcados para remoção serão removidos na próxima vez que a caixa de correio for processada pelo assistente de pasta gerenciada.

   Para saber mais, confira [Gerenciar caixas de correios em retenção por atraso](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

- **Sites do SharePoint e do onedrive:** Qualquer conteúdo do SharePoint ou do OneDrive que esteja sendo mantido na biblioteca de retenção de preservação não é excluído durante o período de espera de atraso de 30 dias após a remoção de um site de uma descoberta eletrônica. Isso é semelhante ao que acontece quando um site é liberado de uma política de retenção. Além disso, você não pode excluir manualmente esse conteúdo na biblioteca de retenção de preservação durante o período de espera de 30 dias. 

   Para obter mais informações, consulte [liberando uma política de retenção](retention-policies.md#releasing-a-retention-policy).

Uma retenção de atraso também é aplicada aos locais de conteúdo em espera quando você fecha um caso de descoberta eletrônica principal, pois as isenções são desativadas quando um caso é fechado. Para obter mais informações sobre como fechar uma ocorrência, consulte [fechar, reabrir e excluir uma caixa de descoberta eletrônica principal](close-reopen-delete-core-ediscovery-cases.md).

## <a name="ediscovery-hold-limits"></a>limites de retenção de descoberta eletrônica

A tabela a seguir lista os limites de ocorrências de descoberta eletrônica e isenções de caso.
    
  |**Descrição do limite**|**Limite**|
  |:-----|:-----|
  |Número máximo de casos para uma organização  <br/> |Sem limite  <br/> |
  |Número máximo de suspensões de descoberta eletrônica para uma organização  <br/> |10.000  <br/> |
  |Número máximo de caixas de correio em um único bloqueio de descoberta eletrônica  <br/> |1.000  <br/> |
  |Número máximo de sites do SharePoint e do OneDrive for Business em um único bloqueio de descoberta eletrônica  <br/> |100  <br/> |
  |Número máximo de casos exibidos na home page de descoberta eletrônica e o número máximo de itens exibidos nas guias isenções, pesquisas e exportar em um caso. <sup>1</sup> |1.000|
  |||

   > [!NOTE]
   > <sup>1</sup> para exibir uma lista de mais de 1.000 casos, isenções, pesquisas ou exportações, você pode usar o cmdlet do PowerShell de segurança & conformidade do Office 365 correspondente:<br/> [Get-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase) <br/> [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)<br/> [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)<br/> [Get-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)