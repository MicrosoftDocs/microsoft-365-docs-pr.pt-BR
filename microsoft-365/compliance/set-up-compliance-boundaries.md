---
title: Configurar limites de conformidade para investigações de Descobertas
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
description: Saiba como usar os limites de conformidade para criar limites lógicos que controlam os locais de conteúdo do usuário que um gerente de DescobertaScoberta pode pesquisar no Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 28e61665d286292f8ba301c313fc3d9bb13065c1
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233180"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations"></a>Configurar limites de conformidade para investigações de Descobertas

As orientações neste artigo podem ser aplicadas ao usar a Descoberta Principal ou a Descoberta Avançada para gerenciar investigações.

Os limites de conformidade criam limites lógicos dentro de uma organização que controlam os locais de conteúdo do usuário (como caixas de correio, contas do OneDrive e sites do SharePoint) que os gerentes de Descoberta Eletrônico podem pesquisar. Além disso, os limites de conformidade controlam quem pode acessar ocorrências de Descoberta e usadas para gerenciar as investigações legais, de recursos humanos ou de outras investigações em sua organização. A necessidade de limites de conformidade geralmente é necessária para corporações multinacionais que precisam respeitar os conselho geográficos e as regulamentações e os governos, que geralmente são divididos em agências diferentes. No Microsoft 365, os limites de conformidade ajudam você a atender a esses requisitos ao executar pesquisas de conteúdo e gerenciar investigações com casos de Descobertas e Descobertas.
  
Usamos o exemplo na ilustração a seguir para explicar como funcionam os limites de conformidade.
  
![Os limites de conformidade consistem em filtros de permissões de pesquisa que controlam o acesso a agências e grupos de função de administrador que controlam o acesso a ocorrências de Descobertas](../media/M365_ComplianceBoundary_OrgChart_v2.png)
  
Neste exemplo, a Contoso LTD é uma organização que consiste em duas subsidiárias, Fourth Coffee e Coho Winery. A empresa exige que os agentes e investigadores da Descoberta Eletrônico possam pesquisar apenas as caixas de correio do Exchange, contas do OneDrive e sites do SharePoint em sua agência. Além disso, os gerentes e investigadores de Descobertas e Descobertas Podem ver apenas ocorrências de DescobertaScoberta em sua agência, e eles só podem acessar os casos dos quais são membros. Além disso, neste cenário, os investigadores não podem colocar locais de conteúdo em espera ou exportar conteúdo de uma ocorrência. Veja como os limites de conformidade atendem a esses requisitos.
  
- A funcionalidade de filtragem de permissões de pesquisa na pesquisa de conteúdo controla os locais de conteúdo que os gerentes e investigadores de Descobertas e Descobertas Podem pesquisar. Isso significa que os gerentes e investigadores de Descobertas e Descobertas Na Agência fourth Coffee só podem pesquisar locais de conteúdo na subsidiária Fourth Coffee. A mesma restrição se aplica à subsidiária Coho Winery.

- Os grupos de função fornecem as seguintes funções para limites de conformidade:

  - Controle quem pode ver as ocorrências de Descobertas No Centro de Conformidade e Segurança & Segurança. Isso significa que os gerentes e investigadores de Descobertas e Descobertas Só podem ver os casos de Descoberta eDiscovery em sua agência.

  - Controlar quem pode atribuir membros a uma ocorrência de Descoberta eDiscovery. Isso significa que os gerentes e investigadores de Descobertas EDiscovery só podem atribuir membros a casos dos quais eles próprios são membros.

  - Controlar as tarefas relacionadas à Descoberta e Que os membros podem executar adicionando ou removendo funções que atribuem permissões específicas.

Aqui está o processo para configurar limites de conformidade:
  
[Etapa 1: Identificar um atributo de usuário para definir suas agências](#step-1-identify-a-user-attribute-to-define-your-agencies)

[Etapa 2: Arquivar uma solicitação com o Suporte da Microsoft para sincronizar o atributo de usuário com contas do OneDrive](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[Etapa 3: Criar um grupo de funções para cada agência](#step-3-create-a-role-group-for-each-agency)

[Etapa 4: Criar um filtro de permissões de pesquisa para impor o limite de conformidade](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[Etapa 5: Criar um caso de Descoberta Bancária para investigações dentro da agência](#step-5-create-an-ediscovery-case-for-intra-agency-investigations)

## <a name="before-you-set-up-compliance-boundaries"></a>Antes de configurar os limites de conformidade

Você precisa atender aos seguintes pré-requisitos antes que o atributo do Azure Active Directory (Azure AD) que você identidade (na Etapa 1) possa ser sincronizado com êxito com a conta do OneDrive de um usuário (na Etapa 2):

- Os usuários devem ter uma licença do Exchange Online e uma licença do SharePoint Online atribuídas.

- As caixas de correio do usuário devem ter pelo menos 10 MB de tamanho. Se a caixa de correio de um usuário for menor que 10 MB, o atributo usado para definir suas agências não será sincronizado com a conta do OneDrive do usuário.

- Os limites de conformidade e os atributos usados para criar filtros de permissões de pesquisa exigem que os atributos do Azure Active Directory (Azure AD) sejam sincronizados com as caixas de correio do usuário. Para verificar se os atributos que você deseja usar foram sincronizados, execute o cmdlet [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user) no PowerShell do Exchange Online. A saída desse cmdlet exibe os atributos do Azure AD sincronizados com o Exchange Online.

## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>Etapa 1: Identificar um atributo de usuário para definir suas agências

A primeira etapa é escolher um atributo do Azure AD para usar que definirá suas agências. Esse atributo é usado para criar o filtro de permissões de pesquisa que limita um gerente de Descobertas Descoberta a pesquisar apenas os locais de conteúdo de usuários aos que foram atribuídos um valor específico para esse atributo. Por exemplo, digamos que Contoso decida usar o **atributo Department.** O valor desse atributo para usuários na subsidiária Fourth Coffee seria e o valor para usuários na  `FourthCoffee`  subsidiária Coho Winery seria `CohoWinery` . Na Etapa 4, use esse par  `attribute:value`  (por exemplo, *Department:FourthCoffee*) para limitar os locais de conteúdo do usuário que os gerentes de Descobertas e Podem pesquisar. 
  
Aqui está uma lista de atributos de usuário do Azure AD que você pode usar para limites de conformidade:
  
- Empresa

- CustomAttribute1 - CustomAttribute15

- Departamento

- Escritório

- C (código de país de duas letras) <sup>*</sup>

  > [!NOTE]
  > <sup>*</sup> Esse atributo mapeia para a propriedade CountryOrRegion que é retornada executando o cmdlet **Get-User** no PowerShell do Exchange Online. O cmdlet retorna o nome do país localizado, que é traduzido do código do país de duas letras. Para obter mais informações, consulte a descrição do parâmetro CountryOrRegion no artigo de referência do cmdlet [Set-User.](https://docs.microsoft.com/powershell/module/exchange/set-user)

Embora mais atributos de usuário estão disponíveis, especialmente para caixas de correio do Exchange, os atributos listados acima são os únicos atualmente suportados pelo OneDrive.
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a>Etapa 2: Arquivar uma solicitação com o Suporte da Microsoft para sincronizar o atributo de usuário com contas do OneDrive

A próxima etapa é registrar uma solicitação com o Suporte da Microsoft para sincronizar o atributo do Azure AD que você escolheu na Etapa 1 para todas as contas do OneDrive em sua organização. Após essa sincronização ocorrer, o atributo (e seu valor) que você escolheu na Etapa 1 será mapeado para uma propriedade gerenciada oculta chamada `ComplianceAttribute` . Use esse atributo para criar o filtro de permissões de pesquisa para o OneDrive na Etapa 4.
  
Inclua as seguintes informações ao enviar a solicitação para o suporte da Microsoft:
  
- O nome de domínio padrão da sua organização

- O nome do atributo do Azure AD (da Etapa 1)

- O título ou a descrição a seguir da finalidade da solicitação de suporte: "Habilitar a sincronização do OneDrive for Business com o Azure AD para filtros de segurança de conformidade". Isso ajuda a encaminhar a solicitação para a equipe de engenharia de Descoberta eDiscovery que implementa a solicitação.

Depois que a alteração de engenharia for feita e o atributo for sincronizado com o OneDrive, o Suporte da Microsoft enviará o número do build no qual a alteração foi feita e uma data de implantação estimada. O processo de implantação geralmente leva de 4 a 6 semanas depois que você envia a solicitação de suporte.
  
> [!IMPORTANT]
> Você pode concluir as etapas de 3 a 5 antes da implantação dessa alteração de atributo. Mas a execução de pesquisas de conteúdo não retornará documentos de contas do OneDrive especificadas em um filtro de permissões de pesquisa até que a sincronização de atributos seja implantada.
  
## <a name="step-3-create-a-role-group-for-each-agency"></a>Etapa 3: Criar um grupo de funções para cada agência

A próxima etapa é criar os grupos de função no Centro de Conformidade e Segurança & que se alinhará às suas agências. Recomendamos que você crie um grupo de funções copiando o grupo de Gerentes de Descoberta eDiscovery integrado, adicionando os membros apropriados e removendo funções que podem não ser aplicáveis às suas necessidades. Para obter mais informações sobre funções relacionadas à Descoberta eDiscovery, consulte Atribuir permissões de Descoberta eDiscovery no Centro de Conformidade e Segurança [& Office 365.](assign-ediscovery-permissions.md)
  
Para criar os grupos de função, vá para a página Permissões no Centro de Conformidade e Segurança & e crie um grupo de função para cada equipe em cada agência que usará limites de conformidade e **ocorrências** de Descoberta e Para gerenciar investigações.
  
Usando o cenário de limites de conformidade da Contoso, quatro grupos de função precisam ser criados e os membros apropriados adicionados a cada um deles.
  
- Gerentes da Fourth Coffee eDiscovery

- Investigadores do Quarto Café

- Gerentes de Descoberta eDiscovery da Coho Winery

- Investigadores da Coho Winery
  
Para atender aos requisitos do cenário de limites  de  conformidade da Contoso, você também removeria as funções de Espera e Exportação dos grupos de função de investigadores para impedir que investigadores colocar retém em locais de conteúdo e exportar conteúdo de uma ocorrência.

## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>Etapa 4: Criar um filtro de permissões de pesquisa para impor o limite de conformidade

Depois de criar grupos de função para cada agência, a próxima etapa é criar os filtros de permissões de pesquisa que associam cada grupo de função à sua agência específica e define o limite de conformidade em si. Você precisa criar um filtro de permissões de pesquisa para cada agência. Para obter mais informações sobre como criar filtros de permissões de segurança, consulte [Configurar filtragem de permissões para Pesquisa de Conteúdo.](permissions-filtering-for-content-search.md)
  
Esta é a sintaxe usada para criar um filtro de permissões de pesquisa usado para limites de conformidade.

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_<ComplianceAttribute>  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'" -Action <Action >
```

Aqui está uma descrição de cada parâmetro no comando:
  
- `FilterName`: especifica o nome do filtro. Use um nome que descreva ou identifique a agência em que o filtro é usado.

- `Users`: Especifica os usuários ou grupos que têm esse filtro aplicado às ações de Pesquisa de Conteúdo realizadas. Para limites de conformidade, este parâmetro especifica os grupos de função (criados na Etapa 3) na agência para os que você está criando o filtro. Observe que esse é um parâmetro de vários valores para que você possa incluir um ou mais grupos de função, separados por vírgulas.

- `Filters`: especifica os critérios de pesquisa para o filtro. Para os limites de conformidade, defina os filtros a seguir. Cada uma se aplica a um local de conteúdo. 

    - `Mailbox`: Especifica as caixas de correio que os grupos de função definidos no  `Users` parâmetro podem pesquisar. Para limites de conformidade,  *ComplianceAttribute*  é o mesmo atributo identificado na Etapa 1 e  *AttributeValue*  especifica a agência. Esse filtro permite que os membros do grupo de funções pesquisem apenas as caixas de correio em uma agência específica; por exemplo, `"Mailbox_Department -eq 'FourthCoffee'"` . 

    - `Site`: Especifica as contas do OneDrive que os grupos de função definidos no `Users` parâmetro podem pesquisar. Para o filtro do OneDrive, use a cadeia de caracteres  `ComplianceAttribute` real. Isso mapeia para o mesmo atributo que você identificou na Etapa 1 e que está sincronizado com as contas do OneDrive como resultado da solicitação de suporte que você enviou na Etapa 2; *AttributeValue*  especifica a agência. Esse filtro permite que os membros do grupo de funções pesquisem somente as contas do OneDrive em uma agência específica; por exemplo,  `"Site_ComplianceAttribute -eq 'FourthCoffee'"` .

    - `Site_Path`: especifica os sites do SharePoint que os grupos de função definidos no  `Users` parâmetro podem pesquisar. O  *SharePointURL*  especifica os sites na agência que os membros do grupo de função podem pesquisar. Por exemplo, `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`. Observe que `Site` os `Site_Path` filtros e os filtros são conectados por **um operador -or.**

     > [!NOTE]
     > A sintaxe do parâmetro `Filters` inclui uma lista de *filtros.* Uma lista de filtros é um filtro que inclui um filtro de caixa de correio e um filtro de site separados por vírgula. No exemplo anterior, observe que uma vírgula separa Mailbox_ComplianceAttribute **e** **Site_ComplianceAttribute**: `-Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'"` . Quando esse filtro é processado durante a execução de uma pesquisa de conteúdo, dois filtros de permissões de pesquisa são criados a partir da lista de filtros: um filtro de caixa de correio e um filtro de site. Uma alternativa ao uso de uma lista de filtros seria criar dois filtros de permissões de pesquisa separados para cada agência: um filtro de permissões de pesquisa para o atributo de caixa de correio e um filtro para os atributos do site. Em ambos os casos, os resultados serão os mesmos. Usar uma lista de filtros ou criar filtros de permissões de pesquisa separados é uma questão de preferência.

- `Action`: Especifica o tipo de ação de Pesquisa de Conformidade ao qual o filtro é aplicado. Por exemplo, só aplicaria o filtro quando os membros do grupo de função definido no  `-Action Search` parâmetro `Users` executarem uma pesquisa de conteúdo. Nesse caso, o filtro não seria aplicado ao exportar os resultados da pesquisa. Para limites de conformidade, use  `-Action All` para que o filtro se aplique a todas as ações de pesquisa. 

    Para uma lista das ações de Pesquisa de Conteúdo, consulte a seção "New-ComplianceSecurityFilter" em Configurar filtragem de permissões [para Pesquisa de Conteúdo.](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)

Aqui estão exemplos dos dois filtros de permissões de pesquisa que seriam criados para dar suporte ao cenário de limites de conformidade da Contoso. Esses dois exemplos incluem uma lista de filtros separados por vírgulas, na qual os filtros de caixa de correio e de site são incluídos no mesmo filtro de permissões de pesquisa e são separados por vírgula.
  
### <a name="fourth-coffee"></a>Fourth Coffee

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```

### <a name="coho-winery"></a>Coho Winery

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-intra-agency-investigations"></a>Etapa 5: Criar um caso de Descoberta Pública para investigações dentro da agência

A etapa final é criar um caso principal de Descoberta eDiscovery ou Descoberta Avançada no centro de conformidade do Microsoft 365 e, em seguida, adicionar o grupo de função que você criou na Etapa 3 como um membro da ocorrência. Isso resulta em duas características importantes do uso de limites de conformidade:
  
- Somente os membros do grupo de funções adicionados à ocorrência poderão ver e acessar o caso no Centro de Conformidade e Segurança & Segurança. Por exemplo, se o grupo de funções Quatro Investigadores de Café for o único membro de uma ocorrência, os membros do grupo de função Gerentes de Descoberta eDiscovery Managers da Fourth Coffee (ou membros de qualquer outro grupo de função) não poderão ver ou acessar o caso.

- Quando um membro do grupo de funções atribuído a uma ocorrência executa uma pesquisa associada à ocorrência, ele só poderá pesquisar os locais de conteúdo dentro de sua agência (que é definido pelo filtro de permissões de pesquisa que você criou na Etapa 4).)

Para criar uma ocorrência e atribuir membros:

1. Vá para a **página Descoberta eDiscovery** Principal ou Descoberta Avançada no centro de conformidade do Microsoft 365 e crie uma ocorrência. 

2. Na lista de casos, clique no nome da ocorrência que você criou.

3. In the **Manage this case flyout** page, under **Manage role groups**, click Add ![ icon ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Add**.

    ![Adicionar um grupo de função como membro de uma ocorrência de Descoberta](../media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. Na lista de grupos de função, selecione um dos grupos de função que você criou na Etapa 3 e clique em **Adicionar**.

5. Clique **em** Salvar no **flyout Gerenciar este** caso para salvar a alteração.

> [!NOTE]
Ao adicionar um grupo de função a uma ocorrência, você só pode adicionar os grupos de função dos que você é membro.

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>Pesquisar e exportar conteúdo em ambientes multi-geo

Os filtros de permissões de pesquisa também permitem controlar onde o conteúdo é roteado para exportação e qual datacenter pode ser pesquisado ao pesquisar locais de conteúdo em um ambiente [multi-geo do SharePoint.](https://go.microsoft.com/fwlink/?linkid=860840)
  
- **Exportar resultados de pesquisa:** Você pode exportar os resultados da pesquisa de caixas de correio do Exchange, sites do SharePoint e contas do OneDrive de um datacenter específico. Isso significa que você pode especificar o local do datacenter do qual os resultados da pesquisa serão exportados.

    Use o **parâmetro Region** para cmdlets **New-ComplianceSecurityFilter** ou **Set-ComplianceSecurityFilter** para criar ou alterar o datacenter pelo qual a exportação será roteada.
  
    |**Valor do parâmetro**|**Local do datacenter**|
    |:-----|:-----|
    |NAM  <br/> |América do Norte (datacenters estão nos EUA)  <br/> |
    |EUR  <br/> |Europa  <br/> |
    |APC  <br/> |Pacífico Asiático  <br/> |
    |CAN <br/> |Canadá|
    |||

- **Rotear pesquisas de conteúdo:** Você pode encaminhar as pesquisas de conteúdo de sites do SharePoint e contas do OneDrive para um datacenter satélite. Isso significa que você pode especificar o local do datacenter onde as pesquisas serão executados.

    Use um dos seguintes valores para o parâmetro **Region** para controlar o local do datacenter em que as pesquisas serão executados ao pesquisar sites do SharePoint e contas do OneDrive. 
  
    |**Valor do parâmetro**|**Locais de roteamento de datacenter para o SharePoint**|
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
    |MOS  <br/> |Datacenters na América do Norte |
    |||

   Se você não especificar o parâmetro **Region** para um filtro de permissões de pesquisa, a região principal do SharePoint da organização será pesquisada. Os resultados da pesquisa são exportados para o datacenter mais próximo.

   Para simplificar o conceito, o parâmetro **Region** controla o datacenter usado para pesquisar conteúdo no SharePoint e no OneDrive. Isso não se aplica à pesquisa de conteúdo no Exchange porque as pesquisas de conteúdo do Exchange não estão vinculadas pela localização geográfica dos datacenters. Além disso, o mesmo **valor do** parâmetro Region também pode ditar o datacenter pelo o que as exportações são roteados. Isso geralmente é necessário para controlar a movimentação de dados entre os tabuleiros geográficos.

> [!NOTE]
> Se você estiver usando a Descoberta Avançada, o parâmetro **Region** não controlará a região de onde os dados são exportados. Os dados são exportados do datacenter principal da organização. Além disso, a pesquisa de conteúdo no SharePoint e no OneDrive não está vinculada à localização geográfica dos datacenters. Todos os datacenters são pesquisados. Para obter mais informações sobre a Descoberta Avançada, consulte a Visão Geral da solução de Descoberta Descoberta Avançada no [Microsoft 365.](overview-ediscovery-20.md)

Aqui estão exemplos de como usar o parâmetro **Region** ao criar filtros de permissão de pesquisa para limites de conformidade. Isso pressupo que a subsidiária Fourth Coffee está localizada na América do Norte e que a Coho Winery está na Europa. 
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```

Lembre-se do seguinte ao pesquisar e exportar conteúdo em ambientes multi-geo.
  
- O parâmetro **Região** não controla as pesquisas de caixas de correio do Exchange. Todos os datacenters serão pesquisados quando você pesquisar caixas de correio. Para limitar o escopo do qual as caixas de correio do Exchange são pesquisadas, use o parâmetro **Filters** ao criar ou alterar um filtro de permissões de pesquisa. 

- Se for necessário que um Gerente de Descoberta eDiscovery pesquise em várias regiões do SharePoint, você precisará criar uma conta de usuário diferente para que o gerente de Descobertas Ele use no filtro de permissões de pesquisa para especificar a região onde os sites do SharePoint ou as contas do OneDrive estão localizados. Para obter mais informações sobre como configurar isso, consulte a seção "Pesquisar conteúdo em um ambiente multi-geo do SharePoint" em [Pesquisa de Conteúdo.](content-search.md#searching-for-content-in-a-sharepoint-multi-geo-environment)

- Ao pesquisar conteúdo no SharePoint e no OneDrive, o parâmetro **Region** direciona as pesquisas para a localização principal ou por satélite onde o gerente de Descobertas eDiscovery conduzirá investigações de Descobertas. Se um gerente de Descoberta eDiscovery pesquisar sites do SharePoint e do OneDrive fora da região especificada no filtro de permissões de pesquisa, nenhum resultado de pesquisa será retornado.

- Ao exportar resultados da pesquisa, o conteúdo de todos os locais de conteúdo (incluindo o Exchange, o Skype for Business, o SharePoint, o OneDrive e outros serviços  que você pode pesquisar usando a ferramenta pesquisa de conteúdo) é carregado para o local de armazenamento do Azure no datacenter especificado pelo parâmetro Region. Isso ajuda as organizações a permanecerem em conformidade, não permitindo que o conteúdo seja exportado através de bordas controladas. Se nenhuma região for especificada no filtro de permissões de pesquisa, o conteúdo será carregado no datacenter principal da organização.

- Você pode editar um filtro de permissões de pesquisa existente para adicionar ou alterar a região executando o seguinte comando:

    ```powershell
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```

## <a name="using-compliance-boundaries-for-sharepoint-hub-sites"></a>Usando limites de conformidade para sites do hub do SharePoint

[Os sites de hub do SharePoint](https://docs.microsoft.com/sharepoint/dev/features/hub-site/hub-site-overview) geralmente se alinham com os mesmos limites geográficos ou de agência que os limites de conformidade da Descoberta Online seguem. Isso significa que você pode usar a propriedade de ID do site do hub para criar um limite de conformidade. Para fazer isso, use o cmdlet [Get-SPOHubSite](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spohubsite#examples) no PowerShell do SharePoint Online para obter o SiteId do site do hub e, em seguida, use esse valor para a propriedade de ID do departamento para criar um filtro de permissões de pesquisa.

Use a seguinte sintaxe para criar um filtro de permissões de pesquisa para um site do hub do SharePoint:

```powershell
New-ComplianceSecurityFilter -FilterName <Filter Name> -Users <User or Group> -Filters "Site_Departmentid -eq '{SiteId of hub site}'" -Action ALL
```

Veja um exemplo de como criar um filtro de permissões de pesquisa para um site de hub para a agência Coho Winery:

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Hub Site Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Site_Departmentid -eq '44252d09-62c4-4913-9eb0-a2a8b8d7f863'" -Action ALL
```

## <a name="compliance-boundary-limitations"></a>Limitações de limite de conformidade

Lembre-se das seguintes limitações ao gerenciar casos de Descoberta e investigações que usam limites de conformidade.
  
- Ao criar e executar uma pesquisa, você pode selecionar locais de conteúdo que estão fora da sua agência. No entanto, devido ao filtro de permissões de pesquisa, o conteúdo desses locais não é incluído nos resultados da pesquisa.

- Os limites de conformidade não se aplicam a resções em casos de Descoberta eDiscovery. Isso significa que um gerente de Descoberta eDiscovery em uma agência pode colocar um usuário em uma agência diferente em espera. No entanto, o limite de conformidade será imposto se o gerente de Descoberta eDiscovery pesquisar os locais de conteúdo do usuário que foi colocado em espera. Isso significa que o gerente de Descoberta eDiscovery não poderá pesquisar os locais de conteúdo do usuário, mesmo que ele tenha sido capaz de colocar o usuário em espera.

    Além disso, as estatísticas de espera só se aplicarão a locais de conteúdo na agência.

- Filtros de permissões de pesquisa não são aplicados a pastas públicas do Exchange.

## <a name="more-information"></a>Mais informações

- Se uma caixa de correio for des licenciada ou excluída por software, os atributos do Azure AD não serão mais sincronizados com a caixa de correio. Se uma espera foi colocada na caixa de correio quando ela foi excluída, o conteúdo preservado na caixa de correio ainda está sujeito a um limite de conformidade ou filtro de permissões de pesquisa com base na última vez em que os atributos do Azure AD foram sincronizados antes da caixa de correio ser excluída. 

    Além disso, a sincronização entre a caixa de correio do usuário e a conta do OneDrive encerrará se a caixa de correio for des licenciada ou excluída de forma suave. O último valor carimbado do atributo de conformidade para a conta do OneDrive permanecerá em vigor.

- O atributo de conformidade é sincronizado da caixa de correio do Exchange de um usuário com sua conta do OneDrive a cada sete dias. Conforme mencionado anteriormente, essa sincronização só ocorre quando o usuário recebe uma licença do Exchange Online e do SharePoint Online e a caixa de correio do usuário é de pelo menos 10 MB.

- Se os limites de conformidade e os filtros de permissões de pesquisa são implementados para a caixa de correio de um usuário e para a conta do OneDrive, recomendamos que você não exclua a caixa de correio de um usuário e não a conta do OneDrive. Em outras palavras, se você excluir a caixa de correio de um usuário, também deverá remover a conta do OneDrive do usuário.

- Há situações (como um funcionário em retorno) em que um usuário pode ter duas ou mais contas do OneDrive. Nesses casos, somente a conta principal do OneDrive associada ao usuário no Azure AD será sincronizada.

- Os limites de conformidade e os filtros de permissões de pesquisa dependem de atributos carimbados no conteúdo do Exchange, oneDrive e SharePoint e da indexação subsequente desse conteúdo carimbado. 

- Não recomendamos o uso de filtros de exclusão (como o uso em um filtro de permissões de pesquisa) para um limite de conformidade `-not()` baseado em conteúdo. O uso de um filtro de exclusão poderá ter resultados inesperados se o conteúdo com atributos atualizados recentemente não tiver sido indexado. 

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Quem pode criar e gerenciar filtros de permissões de pesquisa (usando New-ComplianceSecurityFilter e Set-ComplianceSecurityFilter cmdlets)?**
  
Para criar, exibir e modificar filtros de permissões de pesquisa, você precisa ser membro do grupo de funções Gerenciamento da Organização no Centro de Conformidade e Segurança & Segurança.
  
**Se um gerente de Descoberta eDiscovery for atribuído a mais de um grupo de funções que abrange várias agências, como eles pesquisam conteúdo em uma agência ou em outra?**
  
O gerente de Descoberta eDiscovery pode adicionar parâmetros à consulta de pesquisa que restringem a pesquisa a uma agência específica. Por exemplo, se uma organização especificou a propriedade **CustomAttribute10** para diferenciar agências, ela poderá anexar o seguinte à consulta de pesquisa para pesquisar caixas de correio e contas do OneDrive em uma agência específica:  `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>` .
  
**O que acontece se o valor do atributo usado como atributo de conformidade em um filtro de permissões de pesquisa for alterado?**
  
Leva até três dias para um filtro de permissões de pesquisa impor o limite de conformidade se o valor do atributo usado no filtro for alterado. Por exemplo, no cenário da Contoso, digamos que um usuário na agência Fourth Coffee seja transferido para a agência Coho Winery. Como resultado, o valor do atributo **Department** no objeto de usuário é alterado de *FourthCoffee* para *CohoWinery*. Nessa situação, a Descoberta e os investidores da Fourth Coffee obterão resultados de pesquisa para esse usuário por até três dias após a alteração do atributo. Da mesma forma, leva até três dias até que gerentes e investigadores da Coho Winery eDiscovery recebam resultados de pesquisa para o usuário.
  
**Um gerente de Descoberta eDiscovery pode ver o conteúdo de dois limites de conformidade separados?**
  
Sim, isso pode ser feito ao pesquisar caixas de correio do Exchange adicionando o gerente de Descoberta Eletrônico aos grupos de função que têm visibilidade para ambas as agências. No entanto, ao pesquisar sites do SharePoint e contas do OneDrive, um gerente de Descobertas Digitais pode pesquisar conteúdo em limites de conformidade diferentes somente se as agências estão na mesma região ou localização geográfica. **Observação:** Essa limitação para sites não se aplica à Descoberta Avançada porque a pesquisa de conteúdo no SharePoint e no OneDrive não está vinculada pela localização geográfica.
  
**Os filtros de permissões de pesquisa funcionam para retenções de caso de Descoberta e, políticas de retenção do Microsoft 365 ou DLP?**
  
Não, não no momento.
  
**Se eu especificar uma região para controlar onde o conteúdo será exportado, mas não tiver uma organização do SharePoint nessa região, ainda posso pesquisar no SharePoint?**
  
Se a região especificada no filtro de permissões de pesquisa não existir em sua organização, a região padrão será pesquisada.
  
**Qual é o número máximo de filtros de permissões de pesquisa que podem ser criados em uma organização?**
  
Não há limite para o número de filtros de permissões de pesquisa que podem ser criados em uma organização. No entanto, o desempenho da pesquisa será afetado quando houver mais de 100 filtros de permissões de pesquisa. Para manter o número de filtros de permissões de pesquisa em sua organização o menor possível, crie filtros que combinem regras para Exchange, SharePoint e OneDrive em um único filtro de permissões de pesquisa sempre que possível.
