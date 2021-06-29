---
title: Atribuir permissões de Descoberta E no Centro de conformidade do Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: Atribua as permissões necessárias para executar tarefas relacionadas à Descoberta Centro de conformidade do Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 06e75a18c338d2634ae3be93514ee518d9e91860
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194668"
---
# <a name="assign-ediscovery-permissions-in-the-microsoft-365-compliance-center"></a>Atribuir permissões de Descoberta E no Centro de conformidade do Microsoft 365

Se você quiser que as [](ediscovery.md) pessoas usem qualquer uma das ferramentas relacionadas à Descoberta Centro de conformidade do Microsoft 365, você deve atribuir a elas as permissões apropriadas. A maneira mais fácil de fazer isso é adicionar à pessoa o grupo de funções apropriado na página **Permissões** no centro de conformidade. Este tópico descreve as permissões necessárias para executar tarefas de Descoberta e.
  
O grupo de função principal relacionado à Descoberta Centro de conformidade do Microsoft 365 é chamado **de Gerenciador de Descobertas E.** Há dois subgrupos dentro desse grupo de função.
  
- **Gerentes de** Descoberta e - Um Gerente de Descoberta Online pode usar ferramentas de pesquisa de Descoberta eDiscovery para pesquisar locais de conteúdo na organização e executar várias ações relacionadas à pesquisa, como visualização e exportação de resultados de pesquisa. Os membros também podem criar e gerenciar casos no Core eDiscovery e Advanced eDiscovery, adicionar e remover membros a uma ocorrência, criar restituições de caso, executar pesquisas associadas a uma ocorrência e acessar dados de caso. Gerentes de Descoberta Eletrônica só podem acessar e gerenciar os casos que eles criam. Eles não podem acessar ou gerenciar casos criados por outros Gerentes de Descoberta Eletrônica.
  
- **Administradores de Descoberta Eletrônica** - Um Administrador de Descoberta Eletrônica é membro do grupo de função Gerente de Descoberta Eletrônica e pode executar as mesmas tarefas relacionadas ao gerenciamento de casos e pesquisa de conteúdo que um Gerente de Descoberta Eletrônica pode executar. Além disso, um Administrador de Descoberta Eletrônica pode:
  
  - Acesse todos os casos listados nas páginas Descoberta Básica **e** **Advanced eDiscovery** no Centro de conformidade do Microsoft 365.

  - Acessar os dados do processo na Descoberta Eletrônica Avançada de qualquer processo da organização.
  
  - Gerenciar qualquer processo de Descoberta Eletrônica após adicionarem a si mesmos como membro do processo.
  
  Por motivos pelos quais você pode querer Administradores de Descobertas De eDiscovery em sua organização, consulte [Mais informações](#more-information).

> [!NOTE]
> Para analisar os dados de um usuário usando Advanced eDiscovery, o usuário (o custodiante dos dados) deve ter uma licença Office 365 E5 ou Microsoft 365 E5. Como alternativa, os usuários com uma Office 365 E1 ou uma licença de Office 365 ou Microsoft 365 E3 podem ser atribuídos a uma licença de complemento Microsoft 365 E5 Compliance ou Microsoft 365 eDiscovery and Audit. Administradores, responsáveis pela conformidade ou equipe jurídica que são atribuídos a casos como membros e usam o Advanced eDiscovery para coletar, exibir e analisar dados não precisam de uma licença E5. Para obter mais informações sobre Advanced eDiscovery licenciamento, consulte [Assinaturas e licenciamento em Advanced eDiscovery](overview-ediscovery-20.md#subscriptions-and-licensing).
  
## <a name="before-you-assign-permissions"></a>Antes de atribuir permissões

- Você precisa ser membro do grupo de função Gerenciamento da Organização ou ter a função Gerenciamento de Função para atribuir permissões de Descoberta Centro de conformidade do Microsoft 365.

- Você pode usar o cmd & let [Add-RoleGroupMember](/powershell/module/exchange/Add-RoleGroupMember) no Centro de Conformidade e Segurança do PowerShell para adicionar um grupo de segurança habilitado para email como membro do subgrupo Gerentes de Descoberta Eletrônica no grupo de funções do Gerenciador de Descoberta Eletrônica. No entanto, não é possível adicionar um grupo de segurança habilitado para email ao subgrupo Administradores de Descoberta Eletrônico. Para obter detalhes, consulte [Mais informações](#more-information). 
  
## <a name="assign-ediscovery-permissions"></a>Atribuir permissões de Descoberta Eletrônica

1. Vá para <https://compliance.microsoft.com> e entre usando uma conta que pode atribuir permissões.
  
2. No painel esquerdo do Centro de conformidade do Microsoft 365, selecione **Permissões**.

3. Na página **Permissões & Funções,** em Centro **de Conformidade,** clique em **Funções**.

4. Na página **Funções do Centro de** Conformidade, selecione **eDiscovery Manager**.
  
5. Na página **de sobrevoo** do Gerenciador de Descobertas e, em seguida, faça um dos seguintes comentários com base nas permissões de Descoberta eDiscovery que você deseja atribuir.
  
    **Para tornar um usuário um Gerenciador de Descobertas E:** Ao lado **do Gerenciador de Descobertas E,** selecione **Editar**. Na página Escolher o Assistente do Gerenciador de **Descobertas E,** clique em ![ Adicionar Ícone ](../media/ITPro-EAC-AddIcon.gif) **Adicionar**. Selecione o usuário (ou usuários) que você deseja adicionar como um gerente de Descoberta De eDiscovery e selecione **Adicionar**. Quando terminar de adicionar usuários, selecione **Concluído**. Em seguida, na **página Assistente Editar Escolher o Gerenciador** de Descobertas e, em seguida, selecione **Salvar** para salvar as alterações na associação do Gerenciador de Descobertas E.
  
    **Para tornar um usuário um Administrador de Descoberta e:** Ao lado do Administrador de Descoberta **e,** selecione **Editar**. Na página Escolher Administrador de Descoberta **e,** clique ![ em Adicionar Ícone ](../media/ITPro-EAC-AddIcon.gif) **Adicionar**. Selecione o usuário (ou usuários) que você deseja adicionar como Administrador **de Descoberta** e, em seguida,  **Adicionar**. Quando terminar de adicionar usuários, selecione **Concluído**. Em seguida, na **página Editing Choose eDiscovery Administrator** wizard, selecione **Salvar** para salvar as alterações na associação Administrador de Descoberta e.
  
> [!NOTE]
> Você também pode usar o cmdlet **Add-eDiscoveryCaseAdmin** para tornar um usuário um Administrador de Descoberta Eletrônica. No entanto, o usuário deve ter a função de Gerenciamento de Caso para que você possa usar esse cmdlet para torná-lo um Administrador de Descoberta Eletrônica. Para obter mais informações, [consulte Add-eDiscoveryCaseAdmin](/powershell/module/exchange/add-ediscoverycaseadmin). 
  
Na página **Permissões** no Centro de conformidade do Microsoft 365, você também pode atribuir permissões relacionadas à Descoberta eDiscovery dos usuários adicionando-as aos grupos de função Administrador de Conformidade, Gerenciamento da Organização e Revistor. Para uma descrição das funções RBAC relacionadas à Descoberta e atribuídas a cada um desses grupos de função, consulte [RBAC roles related to eDiscovery](#rbac-roles-related-to-ediscovery).

## <a name="rbac-roles-related-to-ediscovery"></a>Funções do RBAC relacionadas à Descoberta EDiscovery

A tabela a seguir lista as funções do RBAC relacionadas à Descoberta Centro de conformidade do Microsoft 365 no Centro de conformidade do Microsoft 365 e indica os grupos de função integrados aos quais cada função é atribuída por padrão.
  
| Função | Administrador de Conformidade | Gerente de Descoberta & Administrador | Gerenciamento da Organização | Revisor |
|:-----|:-----:|:-----:|:-----:|:-----:|
|Gerenciamento de Casos <br/> |![Marca de seleção](../media/checkmark.png) <br/> |![Marca de seleção](../media/checkmark.png) <br/> |![Marca de seleção](../media/checkmark.png) <br/> | <br/> |
|Comunicação <br/> | <br/> |![Marca de seleção](../media/checkmark.png) <br/> | <br/> | <br/> |
|Pesquisa de Conformidade <br/> |![Marca de seleção](../media/checkmark.png) <br/> |![Marca de seleção](../media/checkmark.png) <br/> |![Marca de seleção](../media/checkmark.png) <br/> | <br/> |
|Custodian <br/> | <br/> |![Marca de seleção](../media/checkmark.png) <br/> | <br/> | <br/> |
|Exportar <br/> | <br/> |![Marca de seleção](../media/checkmark.png) <br/> | <br/> | <br/> |
|Retenção <br/>  |![Marca de seleção](../media/checkmark.png) <br/> |![Marca de seleção](../media/checkmark.png) <br/> |![Marca de seleção](../media/checkmark.png) <br/> | <br/> |
|Visualização <br/>  | <br/> |![Marca de seleção](../media/checkmark.png) <br/> | <br/> | <br/> |
|Revisão <br/>  | <br/> |![Marca de seleção](../media/checkmark.png) <br/> | <br/> |![Marca de seleção](../media/checkmark.png) <br/> |
|RMS Decrypt <br/>  ||![Marca de seleção](../media/checkmark.png) <br/> |||
|Pesquisar e limpar <br/> | <br/> | <br/> |![Marca de seleção](../media/checkmark.png)           <br/> | <br/> |
||||
  
As seções a seguir descrevem cada uma das funções RBAC relacionadas à Descoberta e listadas na tabela anterior.

### <a name="case-management"></a>Gerenciamento de Casos

Essa função permite que os usuários criem, editem, excluam e controlem o acesso à Descoberta Advanced eDiscovery Principais no Centro de conformidade do Microsoft 365. Conforme explicado anteriormente, um usuário deve ter a função de Gerenciamento de Caso para que você possa usar o cmdlet **Add-eDiscoveryCaseAdmin para torná-lo** um Administrador de Descoberta Eletrônica.

Para saber mais, confira:

- [Introdução à Descoberta Eletrônica Central](get-started-core-ediscovery.md)

- [Começar a trabalhar com a Descoberta Avançada por Email](get-started-with-advanced-ediscovery.md)

### <a name="communication"></a>Comunicação

Essa função permite que os usuários gerenciem todas as comunicações com os custodiantes identificados em Advanced eDiscovery caso. Isso inclui a criação de notificações de espera, lembretes de espera e escalonamentos para gerenciamento. O usuário também pode rastrear o reconhecimento custodiado de notificações de espera e gerenciar o acesso ao portal custodiado que é usado por cada custodiado para rastrear comunicações para os casos em que foram identificados como custodiadores.

Para obter mais informações, [consulte Trabalhar com comunicações em Advanced eDiscovery](managing-custodian-communications.md).

### <a name="compliance-search"></a>Pesquisa de Conformidade

Essa função permite que os usuários executem Centro de conformidade do Microsoft 365 ferramenta de Pesquisa de Conteúdo no Centro de conformidade do Microsoft 365 para pesquisar caixas de correio e pastas públicas, sites do SharePoint Online, sites OneDrive for Business, conversas Skype for Business, grupos Microsoft 365 e grupos Microsoft Teams e Yammer. Essa função permite que um usuário receba uma estimativa dos resultados da pesquisa e crie relatórios de exportação, mas outras funções são necessárias para iniciar ações de pesquisa de conteúdo, como visualização, exportação ou exclusão de resultados de pesquisa.

Na Pesquisa de Conteúdo e Na Descoberta Principal, os usuários que são atribuídos à função Pesquisa de Conformidade, mas não têm a função Visualização, podem visualizar os resultados de uma pesquisa na qual a ação de visualização foi iniciada por um usuário que recebe a função Visualização. O usuário sem a função Preview pode visualizar os resultados por até duas semanas após a criação da ação de visualização inicial.

Da mesma forma, os usuários da Pesquisa de Conteúdo e da Descoberta Principal que são atribuídos à função Pesquisa de Conformidade, mas não têm a função Exportar, podem baixar os resultados de uma pesquisa na qual a ação de exportação foi iniciada por um usuário que recebe a função Exportar. O usuário sem a função Exportar pode baixar os resultados de uma pesquisa de até duas semanas após a criação da ação de exportação inicial. Depois disso, eles não podem baixar os resultados, a menos que alguém com a função Exportar reinicie a exportação.

O período de carência de duas semanas para visualização e exportação de resultados de pesquisa (sem as funções de pesquisa e exportação correspondentes) não se aplica Advanced eDiscovery. Os usuários devem ter as funções Visualizar e Exportar para visualizar e exportar conteúdo em Advanced eDiscovery.

### <a name="custodian"></a>Custodian

Essa função permite que os usuários identifiquem e gerenciem custodiantes para Advanced eDiscovery casos e usem as informações de Azure Active Directory e outras fontes para encontrar fontes de dados associadas aos custodiantes. O usuário pode associar outras fontes de dados, como caixas de correio, SharePoint sites e Teams com custodiantes em um caso. O usuário também pode colocar uma responsabilidade legal sobre as fontes de dados associadas aos custodiantes para preservar o conteúdo no contexto de um caso.

Para obter mais informações, [consulte Work with custodians in Advanced eDiscovery](managing-custodians.md).

### <a name="export"></a>Exportar

A função permite que os usuários exportem os resultados de uma Pesquisa de Conteúdo para um computador local. Ele também permite preparar resultados de pesquisa para análise em Advanced eDiscovery.

Para obter mais informações sobre como exportar resultados de pesquisa, consulte Exportar resultados de [pesquisa de Centro de conformidade do Microsoft 365](export-search-results.md).

### <a name="hold"></a>Retenção

Essa função permite que os usuários coloquem conteúdo em espera em caixas de correio, pastas públicas, sites, Skype for Business conversas e Microsoft 365 grupos. Quando conteúdo está em espera, os proprietários do conteúdo ainda podem modificar ou excluir o conteúdo original, mas o conteúdo será preservado até que a retenção seja removida ou até que a duração da retenção expire.

Para obter mais informações sobre retém, consulte:

- [Criar uma responsabilidade na Descoberta Principal da Descoberta](create-ediscovery-holds.md) 

- [Criar uma espera no Advanced eDiscovery](add-custodians-to-case.md)

### <a name="preview"></a>Visualização

Essa função permite que os usuários exibirem uma lista de itens retornados de uma Pesquisa de Conteúdo. Também podem abrir e exibir cada item da lista para exibir seu conteúdo.

### <a name="review"></a>Revisão

Essa função permite que os usuários acessem conjuntos de revisão [em Advanced eDiscovery](overview-ediscovery-20.md). Os usuários que são atribuídos a essa função podem ver e abrir a lista de casos na página > **Descoberta > Avançado** no Centro de conformidade do Microsoft 365 dos quais são membros. Depois que o usuário acessar um Advanced eDiscovery, ele poderá selecionar **Revisar conjuntos** para acessar dados de caso. Essa função não permite que o usuário visualize os resultados de uma pesquisa de coleção associada ao caso ou faça outras tarefas de pesquisa ou gerenciamento de caso. Os usuários com essa função só podem acessar os dados em um conjunto de revisão.

### <a name="rms-decrypt"></a>RMS Decrypt

Essa função permite que os usuários visualizem mensagens de email protegidas por direitos ao visualizar os resultados da pesquisa e exportar mensagens de email descriptografadas protegidas por direitos. Essa função também permite que os usuários visualizam (e exportem) um arquivo criptografado com uma tecnologia de criptografia [da Microsoft](encryption.md) quando o arquivo criptografado é anexado a uma mensagem de email incluída nos resultados de uma pesquisa de Descoberta Eletrônico. Além disso, essa função permite que os usuários revisem e consultem anexos de email criptografados adicionados a um conjunto de revisão no Advanced eDiscovery. Para obter mais informações sobre descriptografia na Descoberta eDiscovery, consulte [Decryption in Microsoft 365 eDiscovery tools](ediscovery-decryption.md).

### <a name="search-and-purge"></a>Pesquisar e limpar

Essa função permite que os usuários executem a remoção em massa de dados que coincidem com os critérios de uma pesquisa de conteúdo. Para obter mais informações, consulte [Pesquisar e excluir mensagens de email em sua organização.](search-for-and-delete-messages-in-your-organization.md)

## <a name="more-information"></a>Mais informações

- **Por que criar um Administrador de Descoberta Eletrônica?** Conforme explicado anteriormente, um Administrador de Descoberta Eletrônica é membro do grupo de funções Gerente de Descoberta Eletrônica e pode ver e acessar todas as ocorrências de Descoberta Eletrônica em sua organização. A capacidade de acessar todas as ocorrências de Descoberta Eletrônica tem duas finalidades importantes:

  - se uma pessoa que é o único membro de um ocorrência de Descoberta Eletrônica sair de sua organização, ninguém (incluindo os membros do grupo de funções Gerenciamento da organização ou outro membro do grupo de funções Gerente de Descoberta Eletrônica) poderá acessar essa ocorrência de Descoberta Eletrônica, pois não é membro de uma ocorrência. Nessa situação, não haveria um modo de acessar os dados na ocorrência. Porém, como um Administrador de Descoberta De eDiscovery pode acessar todos os casos de Descoberta Livre na organização, ele pode exibir o caso e adicionar a si mesmo ou a outro gerente de Descoberta eDiscovery como membro do caso.

  - Como um Administrador de Descoberta Externa pode exibir e acessar todos os principais casos de Descoberta e Descoberta Advanced eDiscovery, eles podem auditar e supervisionar todos os casos e pesquisas de conformidade associadas. Isso pode ajudar a evitar qualquer uso indevido de pesquisas de conformidade ou casos de Descoberta Desdiscovery. E como os Administradores de Descobertas ES podem acessar informações potencialmente confidenciais nos resultados de uma pesquisa de conformidade, você deve limitar o número de pessoas que são Administradores de Descoberta e.

- **Posso adicionar um grupo como membro do grupo de funções do Gerenciador de Descobertas Esdiscovery?** Conforme explicado anteriormente, você pode adicionar um grupo de segurança habilitado para email como membro do subgrupo Gerentes de Descoberta Eletrônica no grupo de função Gerenciador de Descoberta Eletrônica usando o cmdlet **Add-RoleGroupMember** no Centro de Conformidade e Segurança & do PowerShell. Por exemplo, você pode executar o seguinte comando para adicionar um grupo de segurança habilitado para email ao grupo de funções do Gerenciador de Descobertas Eletrônicos. 

  ```powershell
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    Exchange grupos de distribuição e Microsoft 365 grupos não são suportados. Você deve usar um grupo de segurança habilitado para email, que pode ser criado Exchange Online PowerShell executando `New-DistributionGroup -Type Security` . Você também pode criar um grupo de segurança habilitado para email (e adicionar membros) no centro de administração Exchange ou no Centro de administração do Microsoft 365. Pode levar até 60 minutos depois de você criar para que uma nova segurança habilitada para email seja disponibilizada para adicionar ao grupo de função Gerentes de Descoberta Eletrônico. 

    Além disso, como mencionado anteriormente, não é possível tornar um grupo de segurança habilitado para email um Administrador de Descoberta Eletrônica usando o cmdlet **Add-eDiscoveryCaseAdmin** no Centro de Conformidade e Segurança & do PowerShell. Você só pode adicionar usuários individuais como Administradores de Descoberta e.

    Você também não pode adicionar um grupo de segurança habilitado para email como membro de uma ocorrência.