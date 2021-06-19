---
title: Configurar limites de conformidade para investigações de Descobertas EDiscovery
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
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: Saiba como usar limites de conformidade para criar limites lógicos que controlam os locais de conteúdo do usuário que um gerente de Descoberta Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 23ff50b9cd0ab0178962f7be9f1cedfbd6a7a1f7
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022337"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations"></a>Configurar limites de conformidade para investigações de Descobertas EDiscovery

As diretrizes neste artigo podem ser aplicadas ao usar a Descoberta Interna ou Advanced eDiscovery gerenciar investigações.

Os limites de conformidade criam limites lógicos em uma organização que controla os locais de conteúdo do usuário (como caixas de correio, contas OneDrive e sites SharePoint) que os gerentes de Descoberta Eletrônico podem pesquisar. Além disso, os limites de conformidade controlam quem pode acessar os casos de Descobertas Escobertas usados para gerenciar as investigações legais, de recursos humanos ou de outras investigações em sua organização. A necessidade de limites de conformidade geralmente é necessária para corporações multi-nacionais que precisam respeitar os tabuleiros geográficos e os regulamentos e para os governos, que geralmente são divididos em agências diferentes. Em Microsoft 365, os limites de conformidade ajudam você a atender a esses requisitos ao executar pesquisas de conteúdo e gerenciar investigações com casos de Descobertas EDiscovery.
  
Usamos o exemplo na ilustração a seguir para explicar como funcionam os limites de conformidade.
  
![Os limites de conformidade consistem em filtros de permissões de pesquisa que controlam o acesso a agências e grupos de funções de administrador que controlam o acesso a casos de Descoberta EDiscovery](../media/M365_ComplianceBoundary_OrgChart_v2.png)
  
Neste exemplo, Contoso LTD é uma organização que consiste em duas subsidiárias, Fourth Coffee e Coho Winery. A empresa exige que os agentes e investigadores de Descoberta Exchange pesquisem apenas as caixas de correio Exchange, contas OneDrive e sites SharePoint em sua agência. Além disso, os gerentes e os investigadores de Descoberta Desdiscovery só podem ver casos de Descoberta eDiscovery em sua agência, e eles só podem acessar os casos dos quais são membros. Além disso, neste cenário, os investigadores não podem colocar locais de conteúdo em espera ou exportar conteúdo de um caso. Veja como os limites de conformidade atendem a esses requisitos.
  
- A funcionalidade de filtragem de permissões de pesquisa de conteúdo controla os locais de conteúdo que os gerentes e investigadores de Descoberta De Descoberta De Conteúdo podem pesquisar. Isso significa que gerenciadores e investigadores da Descoberta Eletrônica na agência Fourth Coffee podem pesquisar apenas locais de conteúdo na subsidiária Fourth Coffee. A mesma restrição se aplica à subsidiária Coho Winery.

- [Os grupos de](assign-ediscovery-permissions.md#rbac-roles-related-to-ediscovery) funções fornecem as seguintes funções para limites de conformidade:

  - Controle quem pode ver os casos de Descoberta Centro de conformidade do Microsoft 365. Isso significa que gerenciadores e investigadores da Descoberta Eletrônica podem ver apenas os casos da Descoberta Eletrônica da sua agência. 

  - Controle quem pode atribuir membros a um caso de Descoberta E. Isso significa que gerenciadores e investigadores da Descoberta Eletrônica podem atribuir apenas membros aos casos dos quais eles mesmos são membros.

  - Controle as tarefas relacionadas à Descoberta e que os membros podem executar adicionando ou removendo funções que atribuem permissões específicas.

Este é o processo de configuração de limites de conformidade:
  
[Etapa 1: identificar um atributo de usuário para definir suas agências](#step-1-identify-a-user-attribute-to-define-your-agencies)

[Etapa 2: Criar um grupo de funções para cada agência](#step-2-create-a-role-group-for-each-agency)

[Etapa 3: Criar um filtro de permissões de pesquisa para impor o limite de conformidade](#step-3-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[Etapa 4: Criar um caso de Descoberta e Para investigações dentro da agência](#step-4-create-an-ediscovery-case-for-intra-agency-investigations)

## <a name="before-you-set-up-compliance-boundaries"></a>Antes de configurar limites de conformidade

- Os usuários devem ter uma licença Exchange Online de usuário. Para verificar isso, use o cmdlet [Get-User](/powershell/module/exchange/get-user) no Exchange Online PowerShell.

## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>Etapa 1: identificar um atributo de usuário para definir suas agências

A primeira etapa é escolher um atributo a ser usado que definirá suas agências. Esse atributo é usado para criar o filtro de permissões de pesquisa que limita um gerente de Descoberta e para pesquisar apenas os locais de conteúdo dos usuários que têm um valor específico para esse atributo. Por exemplo, digamos que a Contoso decida usar o **atributo Department.** O valor para esse atributo para usuários na subsidiária Quarto Café seria e o valor para usuários na  `FourthCoffee`  subsidiária coho Winery seria `CohoWinery` . Na Etapa 3, você usa esse  `attribute:value`  par (por exemplo, *Department:FourthCoffee*) para limitar os locais de conteúdo do usuário que os gerentes de Descobertas Públicas podem pesquisar. 
  
Aqui estão alguns exemplos de atributos de usuário que você pode usar para limites de conformidade:
  
- Empresa

- CustomAttribute1 - CustomAttribute15

- Departamento

- Escritório

- CountryOrRegion (código de país de duas letras)

Para uma lista completa, consulte a lista completa de filtros de caixa de [correio com suporte.](/powershell/exchange/recipientfilter-properties#filterable-recipient-properties)

## <a name="step-2-create-a-role-group-for-each-agency"></a>Etapa 2: Criar um grupo de funções para cada agência

A próxima etapa é criar os grupos de função no Centro de Conformidade & segurança que se alinhará às suas agências. Recomendamos criar um grupo de funções copiando o grupo de gerenciadores internos da Descoberta Eletrônica, adicionando membros adequados e removendo funções que podem não ser aplicáveis as suas necessidades. Para obter mais informações sobre funções relacionadas à Descoberta E, consulte [Assign eDiscovery permissions](assign-ediscovery-permissions.md).
  
Para criar grupos de funções, vá para a página **Permissões** no Centro de Conformidade e Segurança e crie um grupo de funções para cada equipe em cada agência que usará os limites de conformidade e os casos da Descoberta Eletrônica para gerenciar investigações.
  
Usando o cenário de limites de conformidade da Contoso, quatro grupos de funções precisam ser criados e os membros apropriados adicionados a cada um.
  
- Gerenciadores da Descoberta Eletrônica da Fourth Coffee

- Investigadores da Fourth Coffee

- Gerenciadores da Descoberta Eletrônica da Coho Winery

- Investigadores da Coho Winery
  
Para atender aos requisitos do cenário de limites  de  conformidade da Contoso, você também removeria as funções de Remoção e Exportação dos grupos de função de investigadores para impedir que os investigadores colocarem regiões de conteúdo e exportar conteúdo de um caso.

## <a name="step-3-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>Etapa 3: Criar um filtro de permissões de pesquisa para impor o limite de conformidade

Depois de criar grupos de função para cada agência, a próxima etapa é criar os filtros de permissões de pesquisa que associam cada grupo de funções à sua agência específica e define o próprio limite de conformidade. Você precisa criar um filtro de permissões de pesquisa para cada agência. Para obter mais informações sobre como criar filtros de permissões de segurança, consulte [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).
  
Esta é a sintaxe usada para criar um filtro de permissões de pesquisa usado para limites de conformidade.

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "Site_Path -like '<SharePointURL>*'" -Action <Action>
```

Aqui está uma descrição de cada parâmetro no comando:
  
- `FilterName`: Especifica o nome do filtro. Use um nome que descreva ou identifique a agência em que o filtro é usado.

- `Users`: Especifica os usuários ou grupos que têm esse filtro aplicado às ações de pesquisa que executam. Para limites de conformidade, este parâmetro especifica os grupos de função (que você criou na Etapa 3) na agência para a que você está criando o filtro. Observe que este é um parâmetro de vários valores para que você possa incluir um ou mais grupos de função, separados por vírgulas.

- `Filters`: Especifica os critérios de pesquisa do filtro. Para os limites de conformidade, você define os seguintes filtros. Cada uma se aplica a um local de conteúdo.

    - `Mailbox`: Especifica as caixas de correio ou OneDrive contas que os grupos de função definidos no `Users` parâmetro podem pesquisar. Esse filtro permite que os membros do grupo de funções pesquisem apenas as caixas de correio ou OneDrive contas em uma agência específica; por exemplo, `"Mailbox_Department -eq 'FourthCoffee'"` .

    - `Site_Path`: Especifica os sites SharePoint que os grupos de função definidos no `Users` parâmetro podem pesquisar. O  *SharePointURL*  especifica os sites na agência que os membros do grupo de função podem pesquisar. Por exemplo, `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`. Observe que `Site` os `Site_Path` filtros e são conectados por **um operador -ou.**

     > [!NOTE]
     > A sintaxe do `Filters` parâmetro inclui uma lista de *filtros*. Uma lista de filtros é um filtro que inclui um filtro de caixa de correio e um filtro de caminho de site separado por uma vírgula. No exemplo anterior, observe que uma vírgula separa Mailbox_MailboxPropertyName **e** **Site_Path**: `-Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "Site_Path -like '<SharePointURL>*'"` . Quando esse filtro é processado durante a execução de uma pesquisa de conteúdo, dois filtros de permissões de pesquisa são criados a partir da lista de filtros: um filtro de caixa de correio e um SharePoint filtro. Uma alternativa ao uso de uma lista de filtros seria criar dois filtros de permissões de pesquisa separados para cada agência: um filtro de permissões de pesquisa para o atributo de caixa de correio e um filtro para os atributos SharePoint site. Em ambos os casos, os resultados serão os mesmos. Usar uma lista de filtros ou criar filtros de permissões de pesquisa separados é uma questão de preferência.

- `Action`: Especifica o tipo de ação de pesquisa ao qual o filtro é aplicado. Por exemplo, só aplicaria o filtro quando membros do grupo de funções  `-Action Search` definidos no `Users` parâmetro executar uma pesquisa. Nesse caso, o filtro não seria aplicado ao exportar resultados da pesquisa. Para limites de conformidade, use  `-Action All` para que o filtro se aplique a todas as ações de pesquisa. 

    Para ver uma lista das ações de pesquisa, consulte a seção "New-ComplianceSecurityFilter" em [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md#new-compliancesecurityfilter).

Aqui estão exemplos de dois filtros de permissões de pesquisa que seria criado para apoiar o cenário de limites de conformidade da Contoso. Esses dois exemplos incluem uma lista de filtros separados por vírgula, nos quais os filtros de site e caixa de correio estão incluídos no mesmo filtro de permissões de pesquisa e são separados por vírgula.
  
### <a name="fourth-coffee"></a>Quarto Café

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```

### <a name="coho-winery"></a>Vinícola Coho

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-4-create-an-ediscovery-case-for-intra-agency-investigations"></a>Etapa 4: Criar um caso de Descoberta E para investigações dentro da agência

A etapa final é criar um caso core de Descoberta Advanced eDiscovery no Centro de conformidade do Microsoft 365 e, em seguida, adicionar o grupo de função que você criou na Etapa 2 como membro do caso. Isso resulta em duas características importantes do uso de limites de conformidade:
  
- Somente os membros do grupo de função adicionados ao caso poderão ver e acessar o caso no Centro de Conformidade & Segurança. Por exemplo, se o grupo de função Quatro Investigadores de Café for o único membro de um caso, os membros do grupo de função Quatro Gerentes de Descoberta De Café (ou membros de qualquer outro grupo de funções) não poderão ver ou acessar o caso.

- Quando um membro do grupo de função atribuído a um caso executa uma pesquisa associada ao caso, ele só poderá pesquisar os locais de conteúdo em sua agência (que é definido pelo filtro de permissões de pesquisa que você criou na Etapa 3.)

Para criar uma ocorrência e atribuir membros:

1. Vá para a **página Descoberta Básica ou** Advanced eDiscovery no Centro de conformidade do Microsoft 365 e crie uma ocorrência. 

2. Na lista de casos, clique no nome do caso criado.

3. Adicione grupos de função como membros ao caso. Para obter instruções, consulte um dos seguintes artigos:

   - [Adicionar membros a um caso de Descoberta Principal](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)

   - [Adicionar membros a um caso de Descoberta Avançada](add-or-remove-members-from-a-case-in-advanced-ediscovery.md)

> [!NOTE]
> Ao adicionar um grupo de função a um caso, você só pode adicionar os grupos de função dos que você é membro.

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>Pesquisar e exportar conteúdo em ambientes multi-geo

Os filtros de permissões de pesquisa também permitem controlar onde o conteúdo é roteado para exportação e qual datacenter pode ser pesquisado ao pesquisar locais de conteúdo em um ambiente [Multi-Geo do SharePoint.](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)
  
- **Exportar resultados da pesquisa:** Você pode exportar os resultados da pesquisa de caixas de correio do Exchange, sites do SharePoint e contas do OneDrive de um datacenter específico. Isso significa que você pode especificar o local do datacenter do qual os resultados da pesquisa serão exportados.

    Use o parâmetro **Region** para cmdlets **New-ComplianceSecurityFilter** ou **Set-ComplianceSecurityFilter** para criar ou alterar o datacenter pelo qual a exportação será roteada.
  
    |**Valor do parâmetro**|**Local do datacenter**|
    |:-----|:-----|
    |NAM  <br/> |Norte-americano (datacenters estão nos EUA)  <br/> |
    |EUR  <br/> |Europa  <br/> |
    |APC  <br/> |Pacífico Asiático  <br/> |
    |CAN <br/> |Canadá|
    |||

- **Roteia pesquisas de conteúdo:** Você pode rotear as pesquisas de conteúdo de sites do SharePoint e contas do OneDrive para um datacenter via satélite. Isso significa que você pode especificar o local do datacenter onde as pesquisas serão executados.

    Use um dos seguintes valores para o parâmetro **Region** para controlar o local do datacenter em que as pesquisas serão executados ao pesquisar sites do SharePoint e contas do OneDrive. 
  
    |**Valor do parâmetro**|**Locais de roteamento de datacenter para SharePoint**|
    |:-----|:-----|
    |NAM  <br/> |EUA  <br/> |
    |EUR  <br/> |Europa  <br/> |
    |APC  <br/> |Pacífico Asiático  <br/> |
    |CAN  <br/> |EUA  <br/> |
    |AUS  <br/> |Pacífico Asiático  <br/> |
    |KOR  <br/> |Datacenter padrão da organização  <br/> |
    |GBR  <br/> |Europa  <br/> |
    |JPN  <br/> |Pacífico Asiático  <br/> |
    |IND  <br/> |Pacífico Asiático  <br/> |
    |LAM  <br/> |EUA  <br/> |
    |NOR  <br/> |Europa |
    |BRA  <br/> |Datacenters norte-americanos |
    |||

   Se você não especificar o parâmetro **Region** para um filtro de permissões de pesquisa, a região principal do SharePoint da organização será pesquisada. Os resultados da pesquisa são exportados para o datacenter mais próximo.

   Para simplificar o conceito, o parâmetro **Region** controla o datacenter usado para pesquisar conteúdo no SharePoint e no OneDrive. Isso não se aplica à pesquisa de conteúdo no Exchange porque as pesquisas de conteúdo do Exchange não estão vinculadas à localização geográfica dos datacenters. Além disso, o mesmo **valor do** parâmetro Region também pode ditar o datacenter pelo o que as exportações são roteados. Isso geralmente é necessário para controlar a movimentação de dados entre os boarders geográficos.

> [!NOTE]
> Se você estiver usando a Descoberta Técnica Avançada, o parâmetro **Region** não controlará a região de onde os dados são exportados. Os dados são exportados do datacenter principal da organização. Além disso, a pesquisa de conteúdo no SharePoint e no OneDrive não está vinculada à localização geográfica dos datacenters. Todos os datacenters são pesquisados. Para obter mais informações sobre a Descoberta Avançada, consulte [Overview of the Advanced eDiscovery solution in Microsoft 365](overview-ediscovery-20.md).

Aqui estão exemplos de uso do parâmetro **Region** ao criar filtros de permissão de pesquisa para limites de conformidade. Isso pressupo que a subsidiária quarto café está localizada na América do Norte e que Coho Winery está na Europa. 
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'" -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'" -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```

Lembre-se das seguintes coisas ao pesquisar e exportar conteúdo em ambientes multi-geo.
  
- O parâmetro **Região** não controla as pesquisas de caixas de correio do Exchange. Todos os datacenters serão pesquisados quando você pesquisar caixas de correio. Para limitar o escopo do qual as caixas de correio do Exchange são pesquisadas, use o parâmetro **Filters** ao criar ou alterar um filtro de permissões de pesquisa.

- Se for necessário que um Gerenciador de Descobertas Digitais pesquise em várias regiões do SharePoint, você precisará criar uma conta de usuário diferente para que o gerente de Descoberta Digital use no filtro de permissões de pesquisa para especificar a região onde os sites do SharePoint ou contas do OneDrive estão localizados. Para obter mais informações sobre como configurar isso, consulte a seção "Pesquisar conteúdo em um ambiente Multi-Geo do SharePoint" em [Pesquisa de Conteúdo](content-search-reference.md#searching-for-content-in-a-sharepoint-multi-geo-environment).

- Ao pesquisar conteúdo no SharePoint e no OneDrive, o parâmetro **Region** direciona as pesquisas para a localização principal ou por satélite onde o gerente de Descoberta eDiscovery conduzirá investigações de Descoberta e. Se um gerente de Descoberta Externa pesquisar sites do SharePoint e do OneDrive fora da região especificada no filtro de permissões de pesquisa, nenhum resultado de pesquisa será retornado.

- Ao exportar resultados da pesquisa, o conteúdo de todos os locais de conteúdo (incluindo Exchange, Skype for Business, SharePoint, OneDrive e outros serviços que você pode pesquisar usando a ferramenta pesquisa de conteúdo) é carregado para o local de Armazenamento do Azure no datacenter especificado pelo parâmetro **Region.** Isso ajuda as organizações a permanecer em conformidade, não permitindo que o conteúdo seja exportado entre bordas controladas. Se nenhuma região for especificada no filtro de permissões de pesquisa, o conteúdo será carregado no datacenter principal da organização.

- Você pode editar um filtro de permissões de pesquisa existente para adicionar ou alterar a região executando o seguinte comando:

    ```powershell
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```

## <a name="using-compliance-boundaries-for-sharepoint-hub-sites"></a>Usando limites de conformidade para sites de hub do SharePoint

[Os sites de hub](/sharepoint/dev/features/hub-site/hub-site-overview) do SharePoint geralmente se alinham com os mesmos limites geográficos ou de agência que os limites de conformidade da Descoberta Online seguem. Isso significa que você pode usar a propriedade ID do site do hub para criar um limite de conformidade. Para fazer isso, use o cmdlet [Get-SPOHubSite](/powershell/module/sharepoint-online/get-spohubsite#examples) no PowerShell do SharePoint Online para obter o SiteId para o site do hub e, em seguida, use esse valor para a propriedade ID do departamento para criar um filtro de permissões de pesquisa.

Use a sintaxe a seguir para criar um filtro de permissões de pesquisa para um site de hub do SharePoint:

```powershell
New-ComplianceSecurityFilter -FilterName <Filter Name> -Users <User or Group> -Filters "Site_Departmentid -eq '{SiteId of hub site}'" -Action ALL
```

Veja um exemplo de criação de um filtro de permissões de pesquisa para um site de hub para a agência Coho Winery:

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Hub Site Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Site_Departmentid -eq '44252d09-62c4-4913-9eb0-a2a8b8d7f863'" -Action ALL
```

## <a name="compliance-boundary-limitations"></a>Limitações de limite de conformidade

Tenha em mente as seguintes limitações ao gerenciar casos e investigações de Descobertas e Descobertas Que usam limites de conformidade.
  
- Ao criar e executar uma pesquisa, você pode selecionar locais de conteúdo que estão fora da sua agência. No entanto, por causa do filtro das permissões de pesquisa, o conteúdo desses locais não são incluídos nos resultados da pesquisa.

- Os limites de conformidade não se aplicam a resções em casos de Descoberta E. Isso significa que um gerenciador da Descoberta Eletrônica pode colocar um usuário de uma outra agência em retenção. No entanto, o limite de conformidade será imposto se o gerenciador da Descoberta Eletrônica pesquisa os locais de conteúdo do usuário colocado em modo de retenção. Isso significa que o gerenciador da Descoberta Eletrônica não poderá pesquisar os locais de conteúdo do usuário, mesmo se conseguirem colocar o usuário em retenção.

    Além disso, estatísticas de retenção se aplicam somente aos locais de conteúdo na agência.

- Se você tiver atribuído um filtro de permissões de pesquisa (uma caixa de correio ou um filtro de site) e tentar exportar itens não índicedos para uma pesquisa que inclua todos os sites do SharePoint em sua organização, você receberá a seguinte mensagem de erro: `Unable to execute the task. Reason: The scope options UnindexedItemsOnly or BothIndexedandUnindexedItems are not allowed when the executing user has a compliance security filter applied` . Se você tiver atribuído um filtro de permissões de pesquisa e quiser exportar itens nãoindexados do SharePoint, você terá que reprisar a pesquisa e incluir sites específicos do SharePoint para pesquisa. Caso contrário, você só poderá exportar itens indexados de uma pesquisa que inclui todos os sites do SharePoint. Para obter mais informações sobre as opções ao exportar resultados da pesquisa, consulte [Exportar resultados da pesquisa de conteúdo.](export-search-results.md#step-1-prepare-search-results-for-export)

- Filtros de permissões de pesquisa não são aplicados a pastas públicas do Exchange.

## <a name="more-information"></a>Mais informações

- Se uma caixa de correio for des licenciada ou excluída de forma suave, o usuário não será mais considerado dentro do limite de conformidade. Se uma reter foi colocada na caixa de correio quando foi excluída, o conteúdo preservado na caixa de correio ainda está sujeito a um limite de conformidade ou filtro de permissões de pesquisa.

- Se os limites de conformidade e os filtros de permissões de pesquisa são implementados para um usuário, recomendamos que você não exclua a caixa de correio de um usuário e não a conta do OneDrive. Em outras palavras, se você excluir a caixa de correio de um usuário, também deverá remover a conta do OneDrive do usuário, já que o mailbox_RecipientFilter é usado para impor o filtro de permissão de pesquisa para o OneDrive.

- Os limites de conformidade e os filtros de permissões de pesquisa dependem dos atributos que estão sendo carimbados no conteúdo no Exchange, no OneDrive e no SharePoint e na indexação subsequente desse conteúdo carimbado.

- Não recomendamos o uso de filtros de exclusão (como o uso em um filtro de permissões de pesquisa) para um limite `-not()` de conformidade baseado em conteúdo. O uso de um filtro de exclusão pode ter resultados inesperados se o conteúdo com atributos atualizados recentemente não tiver sido indexado.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Quem pode criar e gerenciar filtros de permissões de pesquisa (usando New-ComplianceSecurityFilter e Set-ComplianceSecurityFilter cmdlets)?**
  
Para criar, exibir e modificar filtros de permissões de pesquisa, você precisa ser membro do grupo de funções Gerenciamento da Organização no centro de conformidade do Microsoft 365.
  
**Se um gerente de Descoberta De eDiscovery for atribuído a mais de um grupo de funções que abrange várias agências, como eles pesquisam conteúdo em uma agência ou em outra?**
  
O gerente de Descoberta Desdiscovery pode adicionar parâmetros à consulta de pesquisa que restringem a pesquisa a uma agência específica. Por exemplo, se uma organização especificou a propriedade **CustomAttribute10** para diferenciar agências, elas poderão anexar o seguinte à consulta de pesquisa para caixas de correio de pesquisa e contas do OneDrive em uma agência específica:  `CustomAttribute10:<value>` .
  
**O que acontece se o valor do atributo usado como atributo de conformidade em um filtro de permissões de pesquisa for alterado?**
  
Leva até três dias para um filtro de permissões de pesquisa impor o limite de conformidade se o valor do atributo usado no filtro for alterado. Por exemplo, no cenário Contoso, digamos que um usuário na agência Quarto Café seja transferido para a agência de Vinícola Coho. Como resultado, o valor do atributo **Department** no objeto user é alterado de *FourthCoffee* para *CohoWinery*. Nessa situação, a Descoberta EDiscovery do Quarto Café e os investidores obterão resultados de pesquisa para esse usuário por até três dias após a alteração do atributo. Da mesma forma, leva até três dias para que os gerentes e investigadores de Descoberta e Descoberta De Coho Winery recebam resultados de pesquisa para o usuário.
  
**Um gerente de Descoberta E pode ver o conteúdo de dois limites de conformidade separados?**
  
Sim, isso pode ser feito ao pesquisar caixas de correio do Exchange adicionando o gerente de Descoberta Eletrônico a grupos de funções que têm visibilidade para ambas as agências. No entanto, ao pesquisar sites do SharePoint e contas do OneDrive, um gerente de Descoberta Geográfica pode pesquisar conteúdo em diferentes limites de conformidade somente se as agências estão na mesma região ou localização geográfica. **Observação:** Essa limitação para sites não se aplica à Descoberta Avançada de EDiscovery porque a pesquisa de conteúdo no SharePoint e no OneDrive não está vinculada à localização geográfica.
  
**Os filtros de permissões de pesquisa funcionam para retenções de caso de Descoberta eDiscovery, políticas de retenção do Microsoft 365 ou DLP?**
  
Não, não neste momento.
  
**Se eu especificar uma região para controlar onde o conteúdo é exportado, mas não tenho uma organização do SharePoint nessa região, ainda posso pesquisar no SharePoint?**
  
Se a região especificada no filtro de permissões de pesquisa não existir em sua organização, a região padrão será pesquisada.
  
**Qual é o número máximo de filtros de permissões de pesquisa que podem ser criados em uma organização?**
  
Não há limite para o número de filtros de permissões de pesquisa que podem ser criados em uma organização. No entanto, o desempenho da pesquisa será afetado quando houver mais de 100 filtros de permissões de pesquisa. Para manter o número de filtros de permissões de pesquisa em sua organização o menor possível, crie filtros que combinem regras para Exchange, SharePoint e OneDrive em um único filtro de permissões de pesquisa sempre que possível.
