---
title: Configurar limites de conformidade para investigações de Descoberta eletrônica no Office 365
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
description: Use limites de conformidade para criar limites lógicos em uma organização do Office 365 que controla os locais de conteúdo do usuário que um gerente de descoberta eletrônica pode pesquisar. Os limites de conformidade usam filtragem de permissões de pesquisa (também chamados de filtros de segurança de conformidade) para controlar quais caixas de correio, sites do SharePoint e contas do OneDrive podem ser pesquisadas por usuários específicos.
ms.openlocfilehash: 247c2649029d3029bb14ca9873a553f2ef8c356c
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557732"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations-in-office-365"></a>Configurar limites de conformidade para investigações de Descoberta eletrônica no Office 365

As orientações deste artigo podem ser aplicadas ao usar a descoberta eletrônica principal ou a descoberta eletrônica avançada para gerenciar investigações.

Os limites de conformidade criam limites lógicos em uma organização do Office 365 que controlam os locais de conteúdo do usuário (como caixas de correio, sites do SharePoint e contas do OneDrive) que os gerentes de descoberta eletrônica podem pesquisar. Além disso, os limites de conformidade controlam quem pode acessar os casos de descoberta eletrônica usados para gerenciar os recursos jurídicos, humanos ou outras investigações em sua organização. A necessidade de limites de conformidade é geralmente necessária para as empresas multinacionais que precisam respeitar as normas e as regulamentações geográficas e para governos, que geralmente são divididas em diferentes agências. No Office 365, os limites de conformidade o ajudam a atender a esses requisitos ao executar pesquisas de conteúdo e gerenciar investigações com ocorrências de descoberta eletrônica.
  
Usamos o exemplo na ilustração a seguir para explicar como os limites de conformidade funcionam.
  
![Limites de conformidade consistem em filtros de permissão de pesquisa que controlam o acesso a agências e grupos de funções de administrador que controlam o acesso a casos de descoberta eletrônica](../media/5c206cc8-a6eb-4d6b-a3a5-21e158791f9a.png)
  
Neste exemplo, a contoso LTD é uma organização do Office 365 que consiste em duas subsidiárias, Fourth Coffee e Coho Winery. A empresa exige que os gerentes e investigadores de eDiscovery só possam Pesquisar nas caixas de correio do Exchange, contas do OneDrive e sites do SharePoint em sua agência. Além disso, os gerentes e investigadores de descoberta eletrônica só podem ver ocorrências de descoberta eletrônica em suas agências, e eles só podem acessar os casos dos quais eles são membros. Veja aqui como os limites de conformidade atendem a esses requisitos.
  
- A funcionalidade de filtragem de permissões de pesquisa na pesquisa de conteúdo controla os locais de conteúdo que os gerentes de descoberta eletrônica e os investigadores podem pesquisar. Isso significa que os gerentes de descoberta eletrônica e os investigadores no quarto café podem pesquisar apenas os locais de conteúdo na quarta subsidiária. A mesma restrição se aplica à subsidiária Coho Winery.
    
    Grupos de função controlam quem pode ver os casos de descoberta eletrônica no centro de conformidade de & de segurança. Isso significa que os gerentes e investigadores de descoberta eletrônica só podem ver os casos de descoberta eletrônica em suas agências.
    
- Os grupos de função também controlam quem pode atribuir membros a uma ocorrência de descoberta eletrônica. Isso significa que os gerentes de descoberta eletrônica e os investigadores só podem atribuir membros a casos nos quais eles eles mesmos são membros.
    
Este é o processo de configuração dos limites de conformidade:
  
[Etapa 1: identificar um atributo de usuário para definir suas agências](#step-1-identify-a-user-attribute-to-define-your-agencies)

[Etapa 2: arquivar uma solicitação com o suporte da Microsoft para sincronizar o atributo de usuário com as contas do OneDrive](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[Etapa 3: criar um grupo de função para cada agência](#step-3-create-a-role-group-for-each-agency)

[Etapa 4: criar um filtro de permissões de pesquisa para reforçar o limite de conformidade](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[Etapa 5: criar um caso de descoberta eletrônica para investigações dentro da Agência](#step-5-create-an-ediscovery-case-for-intra-agency-investigations)
  
## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>Etapa 1: identificar um atributo de usuário para definir suas agências

A primeira etapa é escolher um atributo do Azure Active Directory para usar que irá definir suas agências. Este atributo é usado para criar o filtro permissões de pesquisa que limita um gerente de descoberta eletrônica para pesquisar apenas os locais de conteúdo de usuários aos quais foram atribuídos um valor específico para este atributo. Por exemplo, digamos que a contoso decida usar o atributo **Department** . O valor desse atributo para os usuários na quarta subsidiária da Fourth Coffee seria `FourthCoffee` e o valor para os usuários da vinícola Coho-subsidiária seria. `CohoWinery` Na etapa 4, você usa esse `attribute:value` par (por exemplo, *Department: fourthcoffee*) para limitar os locais de conteúdo do usuário que os gerentes de descoberta eletrônica podem pesquisar. 
  
Veja a seguir uma lista de atributos de usuário do Azure Active Directory que você pode usar para limites de conformidade:
  
- Empresa
    
- CustomAttribute1 — CustomAttribute15
    
- Departamento
    
- Escritório

- C (código do país de duas letras)
    
Embora mais atributos de usuário estejam disponíveis, particularmente para caixas de correio do Exchange, os atributos listados acima são os únicos com suporte no OneDrive.
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a>Etapa 2: arquivar uma solicitação com o suporte da Microsoft para sincronizar o atributo de usuário com as contas do OneDrive

A próxima etapa é arquivar uma solicitação com o suporte da Microsoft para sincronizar o atributo do Azure Active Directory que você escolheu na etapa 1 para todas as contas do OneDrive em sua organização. Após essa sincronização ocorrer, o atributo (e seu valor) que você escolheu na etapa 1 será mapeado para uma propriedade gerenciada oculta no SharePoint nomeada `ComplianceAttribute`. Use este atributo para criar o filtro de permissões de pesquisa para o OneDrive na etapa 4.
  
Inclua as seguintes informações ao enviar a solicitação para o suporte da Microsoft:
  
- O nome de domínio padrão da sua organização do Office 365
    
- O nome do atributo do Azure Active Directory (da etapa 1)
    
- O seguinte título ou descrição da finalidade da solicitação de suporte: "habilitar a sincronização do OneDrive for Business com o Azure Active Directory para filtros de segurança de conformidade". Isso ajuda a rotear a solicitação para a equipe de engenharia de descoberta eletrônica do Office 365 que implementa a solicitação.
    
Após a alteração da engenharia ser feita e o atributo ser sincronizado com o OneDrive, o suporte da Microsoft lhe enviará o número de compilação que a alteração foi feita e uma data de implantação estimada. O processo de implantação geralmente leva de 4 a 6 semanas após o envio da solicitação de suporte.
  
 **Importante:** Você pode concluir a etapa 3 à etapa 5 antes de a alteração ser implantada. Mas a execução de pesquisas de conteúdo não retornará documentos de sites do OneDrive especificados no filtro permissões de pesquisa até que a alteração seja implantada. 
  
## <a name="step-3-create-a-role-group-for-each-agency"></a>Etapa 3: criar um grupo de função para cada agência

A próxima etapa é criar os grupos de função no centro de conformidade de & de segurança que serão alinhados com suas agências. Recomendamos que você crie um grupo de função, copiando o grupo de gerenciadores de descoberta eletrônica interno, adicionando os membros apropriados e removendo funções que podem não se aplicar às suas necessidades. Para obter mais informações sobre funções relacionadas à descoberta eletrônica, consulte [atribuir permissões de descoberta eletrônica no centro de conformidade & segurança do Office 365](assign-ediscovery-permissions.md).
  
Para criar os grupos de função, acesse a página de **permissões** no centro de conformidade & segurança e crie um grupo de função para cada equipe em cada agência que usará limites de conformidade e casos de descoberta eletrônica para gerenciar investigações. 
  
Usando o cenário de limites de conformidade da Contoso, quatro grupos de função precisam ser criados e os membros apropriados são adicionados a cada um.
  
- Gerentes de descoberta eletrônica da Fourth Coffee
    
- Investigadores da Fourth Coffee
    
- Gerentes de descoberta eletrônica Coho
    
- Investigadores da vinícola Coho
  
## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>Etapa 4: criar um filtro de permissões de pesquisa para reforçar o limite de conformidade

Depois de criar grupos de função para cada agência, a próxima etapa é criar os filtros de permissão de pesquisa que associam cada grupo de função a sua agência específica e definem o limite de conformidade propriamente dito. Você precisa criar um filtro de permissões de pesquisa para cada agência. Para obter mais informações sobre como criar filtros de permissões de segurança, consulte [Configure Permissions Filtering for Content Search](permissions-filtering-for-content-search.md).
  
Veja a sintaxe usada para criar um filtro de permissões de pesquisa usado para limites de conformidade.

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_<ComplianceAttribute>  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'" -Action <Action >
```

Veja a seguir uma descrição de cada parâmetro no comando:
  
-  `FilterName`: Especifica o nome do filtro. Use um nome que descreva ou identifique a agência na qual o filtro é usado. 
    
-  `Users`: Especifica os usuários ou grupos que obtêm esse filtro aplicado às ações de pesquisa de conteúdo que eles executam. Para limites de conformidade, esse parâmetro especifica os grupos de função (que você criou na etapa 3) na agência para a qual você está criando o filtro. Observação Este é um parâmetro de vários valores para que você possa incluir um ou mais grupos de função, separados por vírgulas. 
    
-  `Filters`: Especifica os critérios de pesquisa para o filtro. Para os limites de conformidade, você define os filtros a seguir. Cada uma se aplica a um local de conteúdo. 
    
    -  `Mailbox`: Especifica as caixas de correio que os grupos de função definidos `Users` no parâmetro podem pesquisar. Para limites de conformidade, *complianceattribute* é o mesmo atributo identificado na etapa 1 e *AttributeValue* especifica a agência. Esse filtro permite que os membros do grupo de função pesquisem apenas as caixas de correio em uma agência específica; por exemplo, `"Mailbox_Department -eq 'FourthCoffee'"`. 
    
    -  `Site`: Especifica as contas do OneDrive que os grupos de função definidos `Users` no parâmetro podem pesquisar. Para o filtro do OneDrive, use a cadeia `ComplianceAttribute`de caracteres real. Isso mapeia para o mesmo atributo que você identificou na etapa 1 e que é sincronizado com as contas do OneDrive como resultado da solicitação de suporte que você enviou na etapa 2; *AttributeValue* especifica a agência. Este filtro permite que os membros do grupo de função pesquisem somente as contas do OneDrive em uma agência específica; por exemplo, `"Site_ComplianceAttribute -eq 'FourthCoffee'"`.
    
    -  `Site_Path`: Especifica os sites do SharePoint que os grupos de função definidos `Users` no parâmetro podem pesquisar. O *SharePointURL* especifica os sites na agência que os membros do grupo de funções podem pesquisar. Por exemplo, `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`. Observe que `Site` os `Site_Path` filtros e são conectados por um operador **ou** .
    
     > [!NOTE]
     > A sintaxe do `Filters` parâmetro inclui uma *lista de filtros*. Uma lista de filtros é um filtro que inclui um filtro de caixa de correio e um filtro de site separado por uma vírgula. No exemplo anterior, observe que uma vírgula separa **Mailbox_ComplianceAttribute** e **Site_ComplianceAttribute**: `-Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'"`. Quando esse filtro é processado durante a execução de uma pesquisa de conteúdo, dois filtros de permissão de pesquisa são criados a partir da lista de filtros: um filtro de caixa de correio e um filtro de site. Uma alternativa ao uso de uma lista de filtros seria criar dois filtros de permissões de pesquisa separados para cada agência: um filtro de permissões de pesquisa para o atributo de caixa de correio e um filtro para os atributos de site. Em ambos os casos, os resultados serão os mesmos. O uso de uma lista de filtros ou a criação de filtros de permissões de pesquisa separados é uma questão de preferência.

-  `Action`: Especifica o tipo de ação de pesquisa de conformidade à qual o filtro é aplicado. Por exemplo, `-Action Search` só aplicaria o filtro quando os membros do grupo de função definido no `Users` parâmetro executarem uma pesquisa de conteúdo. Nesse caso, o filtro não será aplicado durante a exportação dos resultados da pesquisa. Para limites de conformidade, `-Action All` use para que o filtro se aplique a todas as ações de pesquisa. 
    
    Para obter uma lista das ações de pesquisa de conteúdo, consulte a seção "New-ComplianceSecurityFilter" em [Configure Permissions Filtering for Content Search](permissions-filtering-for-content-search.md#new-compliancesecurityfilter).

Aqui estão exemplos dos dois filtros de permissões de pesquisa que seriam criados para dar suporte ao cenário de limites de conformidade da contoso. Ambos os exemplos incluem uma lista de filtros separados por vírgulas, nas quais os filtros de caixa de correio e de site estão incluídos no mesmo filtro de permissões de pesquisa e são separados por uma vírgula.
  
 **Fourth Coffee**

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```

 **Coho Winery**

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-intra-agency-investigations"></a>Etapa 5: criar um caso de descoberta eletrônica para investigações dentro da Agência

A etapa final é criar uma ocorrência de descoberta eletrônica no centro de conformidade & segurança e, em seguida, adicionar o grupo de função que você criou na etapa 3 como membro da ocorrência. Isso resulta em duas características importantes de usar limites de conformidade:
  
- Somente os membros do grupo de função adicionado ao caso poderão ver e acessar o caso no centro de conformidade de & de segurança. Por exemplo, se o grupo de funções da Fourth Coffee Investigations for o único membro de um caso, os membros do grupo de função gerentes de descoberta eletrônica da Fourth Coffee (ou membros de qualquer outro grupo de função) não poderão ver ou acessar o caso.
    
- Quando um membro do grupo de função atribuído a uma ocorrência executar uma pesquisa associada ao caso, eles só poderão pesquisar os locais de conteúdo dentro da agência (que é definido pelo filtro de permissões de pesquisa que você criou na etapa 4.)

Para criar um caso e atribuir Membros:

1. Vá para a página de **descoberta eletrônica** ou **descoberta eletrônica avançada** no centro de conformidade de & de segurança e crie uma ocorrência. 

2. Na lista de ocorrências de descoberta eletrônica, clique no nome do caso que você criou.

3. Na página **gerenciar esse** submenu de caso, em **gerenciar grupos**de função ![, clique](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) em Adicionar ícone **Adicionar**.

    ![Adicionar um grupo de função como membro de uma ocorrência de descoberta eletrônica](../media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. Na lista de grupos de função, selecione um dos grupos de função que você criou na etapa 3 e clique em **Adicionar**.

5. Clique em **salvar** no submenu **gerenciar este caso** para salvar a alteração. 

## <a name="compliance-boundary-limitations"></a>Limitações de limite de conformidade

Tenha em mente as seguintes limitações ao gerenciar casos de descoberta eletrônica e investigações que usam limites de conformidade.
  
- Ao criar e executar uma pesquisa, você pode selecionar locais de conteúdo que estão fora da sua agência. No entanto, por causa do filtro de permissões de pesquisa, o conteúdo desses locais não é incluído nos resultados da pesquisa.

- Os limites de conformidade não se aplicam a isenções em casos de descoberta eletrônica. Isso significa que um gerente de descoberta eletrônica em uma agência pode colocar um usuário em uma agência diferente em espera. No entanto, o limite de conformidade será imposto se o Gerenciador de descoberta eletrônica Pesquisar nos locais de conteúdo do usuário que foi colocado em espera. Isso significa que o Gerenciador de descoberta eletrônica não poderá pesquisar os locais de conteúdo do usuário, mesmo que eles possam colocar o usuário em espera.

    Além disso, as estatísticas de retenção só serão aplicadas aos locais de conteúdo na agência.

- Os filtros de permissão de pesquisa não são aplicados às pastas públicas do Exchange.

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>Pesquisando e exportando conteúdo em ambientes multigeográfico

Os filtros de permissões de pesquisa também permitem que você controle onde o conteúdo é encaminhado para exportação e qual datacenter pode ser pesquisado ao pesquisar locais de conteúdo em um [ambiente multigeográfico do SharePoint](https://go.microsoft.com/fwlink/?linkid=860840).
  
- **Exportar resultados de pesquisa:** Você pode exportar os resultados da pesquisa de caixas de correio do Exchange, sites do SharePoint e contas do OneDrive de um Data Center específico. Isso significa que você pode especificar o local do data center de onde os resultados da pesquisa serão exportados.

    Use o parâmetro **Region** para os cmdlets **New-ComplianceSecurityFilter** ou **set-ComplianceSecurityFilter** para criar ou alterar o datacenter ao qual a exportação será roteada.
  
    |**Valor do parâmetro**|**Local do datacenter**|
    |:-----|:-----|
    |NAM  <br/> |América do Norte (os data centers estão nos EUA)  <br/> |
    |EUR  <br/> |Europa  <br/> |
    |APC  <br/> |Pacífico Asiático  <br/> |
    |CAN <br/> |Canadá|
    |||
    
- **Pesquisas de conteúdo de rota:** Você pode rotear as pesquisas de conteúdo de sites do SharePoint e contas do OneDrive para um data center de satélite. Isso significa que você pode especificar o local do datacenter onde as pesquisas serão executadas.
    
    Use um dos seguintes valores para o parâmetro **Region** para controlar o local do Data Center em que pesquisas serão executadas ao pesquisar sites do SharePoint e contas do onedrive. 
  
    |**Valor do parâmetro**|**Locais de roteamento de datacenter para SharePoint**|
    |:-----|:-----|
    |NAM  <br/> |Unidos  <br/> |
    |EUR  <br/> |Europa  <br/> |
    |APC  <br/> |Pacífico Asiático  <br/> |
    |CAN  <br/> |Unidos  <br/> |
    |AUS  <br/> |Pacífico Asiático  <br/> |
    |KOR  <br/> |O datacenter padrão da organização  <br/> |
    |GBR  <br/> |Europa  <br/> |
    |JPN  <br/> |Pacífico Asiático  <br/> |
    |IND  <br/> |Pacífico Asiático  <br/> |
    |LAM  <br/> |Unidos  <br/> |
    |||

   Se você não especificar o parâmetro **Region** para um filtro de permissões de pesquisa, a região padrão do SharePoint da organização será pesquisada. Os resultados da pesquisa são exportados para o datacenter mais próximo.

> [!TIP]
> Para simplificar o conceito, o parâmetro **Region** controla o datacenter que é usado para pesquisar conteúdo no SharePoint e no onedrive. Isso não se aplica à pesquisa de conteúdo no Exchange porque as pesquisas de conteúdo do Exchange não estão associadas à localização geográfica dos datacenters. Além disso, o mesmo valor de parâmetro **Region** também pode ditar o datacenter no qual as exportações são roteadas. Geralmente, isso é necessário para controlar a movimentação de dados entre os inboards geográficas.<br/><br/>Se você estiver usando a descoberta eletrônica avançada, a pesquisa de conteúdo no SharePoint e no OneDrive não será associada à localização geográfica dos datacenters. Todos os datacenters são pesquisados. Para obter mais informações sobre a descoberta eletrônica avançada, confira [visão geral da solução de descoberta eletrônica avançada no Microsoft 365](overview-ediscovery-20.md).

Aqui estão exemplos de como usar o parâmetro **Region** ao criar filtros de permissão de pesquisa para limites de conformidade. Isso pressupõe que a quarta subsidiária de café está localizada na América do Norte e que a Coho Winery está na Europa. 
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```

Tenha em mente as seguintes coisas ao pesquisar e exportar conteúdo em ambientes multigeográfico.
  
- O parâmetro **Região** não controla as pesquisas de caixas de correio do Exchange. Todos os data centers serão pesquisados quando você Pesquisar caixas de correio. Para limitar o escopo do qual as caixas de correio do Exchange são pesquisadas, use o parâmetro **Filters** ao criar ou alterar um filtro de permissões de pesquisa. 
    
- Se for necessário que um gerente de descoberta eletrônica pesquise em várias regiões do SharePoint, você precisará criar uma conta de usuário diferente para o Gerenciador de descoberta eletrônica usar no filtro permissões de pesquisa para especificar a região em que os sites do SharePoint ou o OneDrive as contas estão localizadas. Para obter mais informações sobre como configurar isso, consulte a seção "pesquisando conteúdo em um ambiente multigeográfico do SharePoint" na [pesquisa de conteúdo no Office 365](content-search.md#searching-for-content-in-a-sharepoint-multi-geo-environment).
    
- Ao pesquisar conteúdo no SharePoint e no OneDrive, o parâmetro **Region** direciona as pesquisas para o local principal ou de satélite onde o gerente de descoberta eletrônica conduzirá investigações de descoberta eletrônica. Se um gerente de descoberta eletrônica pesquisa sites do SharePoint e do OneDrive fora da região especificada no filtro permissões de pesquisa, nenhum resultado de pesquisa é retornado. 
    
- Ao exportar os resultados da pesquisa, o conteúdo de todos os locais de conteúdo (incluindo o Exchange, o Skype for Business, o SharePoint, o OneDrive e outros serviços do Office 365 que você pode pesquisar usando a ferramenta de pesquisa de conteúdo) são carregados no local de armazenamento do Azure no datacenter especificado pelo parâmetro **Region** . Isso ajuda as organizações a ficar dentro da conformidade, não permitindo que o conteúdo seja exportado por bordas controladas. Se nenhuma região for especificada no filtro permissões de pesquisa, o conteúdo será carregado para a região padrão da organização. 
    
- Você pode editar um filtro de permissões de pesquisa existente para adicionar ou alterar a região executando o seguinte comando:

    ```powershell
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```

## <a name="frequently-asked-questions"></a>Perguntas frequentes

 **Quem pode criar e gerenciar filtros de permissões de pesquisa (usando os cmdlets New-ComplianceSecurityFilter e Set-ComplianceSecurityFilter)?**
  
Para criar, exibir e modificar filtros de permissões de pesquisa, você precisa ser membro do grupo de função gerenciamento da organização no centro de conformidade de & de segurança.
  
 **Se um gerente de descoberta eletrônica for atribuído a mais de um grupo de função que abrange várias agências, como pesquisará conteúdo em uma agência ou outra?**
  
O Gerenciador de descoberta eletrônica pode adicionar parâmetros à consulta de pesquisa que restringe a pesquisa a uma agência específica. Por exemplo, se uma organização especificou a propriedade **CustomAttribute10** para diferenciar agências, elas podem acrescentar o seguinte à consulta de pesquisa para pesquisar caixas de correio e contas do onedrive em uma agência `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`específica:.
  
 **O que acontece se o valor do atributo usado como atributo de conformidade em um filtro de permissões de pesquisa for alterado?**
  
É necessário até três dias para um filtro de permissões de pesquisa para impor o limite de conformidade se o valor do atributo usado no filtro for alterado. Por exemplo, no cenário da Contoso, vamos supor que um usuário na quarta agência de café seja transferido para a Agência Coho Winery. Como resultado, o valor do atributo **Department** no objeto user é alterado de *fourthcoffee* para *CohoWinery*. Nessa situação, a quarta-Discovery e os investidores de café receberão os resultados de pesquisa desse usuário por até três dias após o atributo ser alterado. Da mesma forma, os gerentes e investigadores de descoberta eletrônica Coho recebem resultados de pesquisa para o usuário. 
  
 **Um gerente de descoberta eletrônica pode ver o conteúdo de dois limites de conformidade separados?**
  
Sim. Isso pode ser feito adicionando o usuário aos grupos de função que têm visibilidade para ambas as agências.
  
 **Os filtros de permissões de pesquisa funcionam para isenções de caso de descoberta eletrônica, políticas de retenção do Office 365 ou DLP?**
  
Não no momento.
  
 **Se eu especificar uma região para controlar onde o conteúdo é exportado, mas não tenho uma organização do SharePoint nessa região, ainda poderei Pesquisar o SharePoint?**
  
Se a região especificada no filtro permissões de pesquisa não existir na sua organização, a região padrão será pesquisada.
  
 **Qual é o número máximo de filtros de permissão de pesquisa que podem ser criados em uma organização?**
  
Não há limite para o número de filtros de permissões de pesquisa que podem ser criados em uma organização. No entanto, o desempenho da pesquisa será afetado quando houver mais de 100 filtros de permissões de pesquisa. Para manter o número de filtros de permissão de pesquisa em sua organização o menor possível, crie filtros que combinem regras para o Exchange, SharePoint e OneDrive em um único filtro de permissões de pesquisa sempre que possível.
