---
title: Atribuir permissões de descoberta eletrônica no centro de conformidade & segurança
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
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: Atribua as permissões necessárias para executar tarefas relacionadas à descoberta eletrônica usando o centro de conformidade do & de segurança.
ms.openlocfilehash: 76ec07909fab35dfbead806befe2565f4e2054ae
ms.sourcegitcommit: 21977f5cb6b01aee5cae54979717530b2a31a46a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2020
ms.locfileid: "44411028"
---
# <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>Atribuir permissões de descoberta eletrônica no centro de conformidade & segurança

Se quiser que as pessoas usem qualquer uma das [Ferramentas relacionadas à descoberta eletrônica](ediscovery.md) no centro de conformidade & segurança no Office 365 ou no centro de conformidade da Microsoft 365, você precisa atribuir as permissões apropriadas. A maneira mais fácil de fazer isso é adicionar a pessoa o grupo de função apropriado na página **permissões** no centro de conformidade de & de segurança. Este tópico descreve as permissões necessárias para executar tarefas relacionadas à pesquisa de descoberta eletrônica e conteúdo usando o centro de conformidade do & de segurança.
  
O grupo de função principal relacionado à descoberta eletrônica no centro de conformidade e segurança & é chamado de **Gerenciador de descoberta eletrônica**. Há dois subgrupos dentro desse grupo de funções. 
  
- **gerentes de descoberta** eletrônica: um gerente de descoberta eletrônica pode usar a ferramenta de pesquisa de conteúdo no centro de conformidade do & de segurança para pesquisar locais de conteúdo na organização e realizar várias ações relacionadas à pesquisa, como Visualizar e exportar resultados de pesquisa. Os membros também podem criar e gerenciar casos de descoberta eletrônica principais e casos de descoberta eletrônica avançados, adicionar e remover membros a um caso, criar isenções de caso, executar pesquisas associadas a uma ocorrência e acessar dados de caso. Os gerentes de descoberta eletrônica só podem acessar e gerenciar os casos que criam. Eles não podem acessar ou gerenciar casos criados por outros gerentes de descoberta eletrônica.
  
- **Administradores** de descoberta eletrônica: um administrador de descoberta eletrônica é um membro do grupo de funções Gerenciador de descoberta eletrônica e pode executar as mesmas tarefas relacionadas ao gerenciamento de casos e pesquisa de conteúdo que um gerente de descoberta eletrônica pode executar. Além disso, um Administrador de Descoberta Eletrônica pode:
  
  - Acessar todos os casos listados nas páginas de **descoberta eletrônica** e **descoberta eletrônica avançada** no centro de conformidade do & de segurança.

  - Acessar dados de caso na descoberta eletrônica avançada para qualquer caso na organização.
  
  - Gerencie qualquer caso de descoberta eletrônica após eles se adicionarem como um membro do caso.
  
  Consulte a seção [mais informações](#more-information) por razões pelas quais você pode querer administradores de descoberta eletrônica em sua organização.

> [!NOTE]
> Para analisar os dados de um usuário usando a descoberta eletrônica avançada, o usuário (o responsáveis dos dados) deve receber uma licença do Office 365 E5 ou do Microsoft 365 e5. Como alternativa, os usuários com uma licença do Office 365 E1 ou do Office 365 ou do Microsoft 365 E3 podem ser atribuídos a uma licença de Microsoft 365 E5 Compliance ou Microsoft 365 eDiscovery and Audit Add-on. Administradores, responsáveis pela conformidade ou pessoal legal que são atribuídos a casos como membros e usam a descoberta eletrônica avançada para coletar, exibir e analisar dados não precisam de uma licença e5. Para obter mais informações sobre licenciamento de descoberta eletrônica avançada, confira [introdução à descoberta eletrônica avançada](get-started-with-advanced-ediscovery.md).
  
## <a name="before-you-begin"></a>Antes de começar

- Você precisa ser membro do grupo de função gerenciamento da organização ou receber a função de gerenciamento de função para atribuir permissões de descoberta eletrônica no centro de conformidade de & de segurança.
    
- Você pode usar o cmdlet [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember) no centro de segurança & conformidade para adicionar um grupo de segurança habilitado para email como membro do subgrupo gerenciadores de descoberta eletrônica no grupo de funções Gerenciador de descoberta eletrônica. No entanto, não é possível adicionar um grupo de segurança habilitado para email ao subgrupo administradores de descoberta eletrônica. Para obter detalhes, consulte a seção [mais informações](#more-information) . 
    
## <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>Atribuir permissões de descoberta eletrônica no centro de conformidade & segurança

1. Acesse [https://protection.office.com](https://protection.office.com).
    
2. Entre usando sua conta de trabalho ou da escola.
    
3. No painel esquerdo do centro de segurança e conformidade, selecione **permissões**e marque a caixa de seleção ao lado de **Gerenciador de descoberta eletrônica**.
    
4. Na página do submenu **Gerenciador de descoberta eletrônica** , siga um destes procedimentos com base nas permissões de descoberta eletrônica que você deseja atribuir. 
  
    **Para tornar um usuário um gerente de descoberta eletrônica:** Ao lado de **Gerenciador de descoberta eletrônica**, selecione **Editar**. Na seção **escolher Gerenciador de descoberta eletrônica** , selecione o hiperlink **escolher Gerenciador de descoberta eletrônica** e selecione ![ Adicionar ícone ](../media/ITPro-EAC-AddIcon.gif) **Adicionar**. Selecione o usuário (ou usuários) que você deseja adicionar como um Gerenciador de descoberta eletrônica e selecione **Adicionar**. Quando terminar de adicionar usuários, selecione **concluído**. Em seguida, na página **edição escolha Gerenciador de descoberta eletrônica** , selecione **salvar** para salvar as alterações na associação do Gerenciador de descoberta eletrônica.
  
    **Para tornar um usuário administrador de descoberta eletrônica:** Ao lado de **Gerenciador de descoberta eletrônica**, selecione **Editar**. Na seção **escolher administrador de descoberta eletrônica** , em **Administradores de descoberta eletrônica**, selecione **escolher administrador de descoberta eletrônica**, selecione **editar**e, em seguida, selecione ![ Adicionar ícone ](../media/ITPro-EAC-AddIcon.gif) **Adicionar**. Selecione o usuário (ou usuários) que você deseja adicionar como **administrador de descoberta eletrônica**e, em seguida, **adicione**. Quando terminar de adicionar usuários, selecione **concluído**. Em seguida, na página **edição escolha administrador de descoberta eletrônica** , selecione **salvar** para salvar as alterações na associação do administrador de descoberta eletrônica.
      
> [!NOTE]
> Você também pode usar o cmdlet **Add-eDiscoveryCaseAdmin** para tornar um usuário um administrador de descoberta eletrônica. No entanto, o usuário deve ter a função de gerenciamento de casos atribuída para que você possa usar este cmdlet para torná-los um administrador de descoberta eletrônica. Para obter mais informações, consulte [Add-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkID=798217). 
  
Na página **permissões** no centro de conformidade de & de segurança, você também pode atribuir permissões relacionadas a eDiscovery dos usuários adicionando-as aos grupos de função Administrador de conformidade, gerenciamento de organização e revisor. Para obter uma descrição das funções RBAC relacionadas à descoberta eletrônica atribuídas a cada um desses grupos de função, consulte a seção [funções RBAC relacionadas a descoberta eletrônica](#rbac-roles-related-to-ediscovery) . 

## <a name="rbac-roles-related-to-ediscovery"></a>Funções RBAC relacionadas à descoberta eletrônica

A tabela a seguir lista as funções RBAC relacionadas à descoberta eletrônica no centro de conformidade de & de segurança e indica os grupos de função internos aos quais cada função é atribuída por padrão. 
    
|**Função**|**Administrador de Conformidade**|**Administrador & do Gerenciador de descoberta eletrônica**|**Organization Management**|**Revisor**|
|:-----|:-----:|:-----:|:-----:|:-----:|
|Gerenciamento de casos <br/> |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Comunicação <br/> | <br/> |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Pesquisa de Conformidade <br/> |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Custodian <br/> | <br/> |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Exportar <br/> | <br/> |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Retenção <br/>  |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Visualização <br/>  | <br/> |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Revisão <br/>  | <br/> |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |
|Descriptografia do RMS <br/>  ||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |||
|Pesquisa e limpeza <br/> | <br/> | <br/> |![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> | <br/> | 
||||
  
As seções a seguir descrevem cada uma das funções RBAC relacionadas à descoberta eletrônica listadas na tabela anterior.

### <a name="case-management"></a>Gerenciamento de casos

Essa função permite que os usuários criem, editem, excluam e controlem o acesso aos casos de descoberta eletrônica principal e de descoberta eletrônica avançada no centro de conformidade de & de segurança. Como explicado anteriormente, um usuário deve ter a função de gerenciamento de casos atribuída antes que você possa usar o cmdlet **Add-eDiscoveryCaseAdmin** para torná-los um administrador de descoberta eletrônica.

Para saber mais, confira:

- [Introdução à Descoberta Eletrônica Central](get-started-core-ediscovery.md)

- [Introdução à Descoberta Eletrônica Avançada](get-started-with-advanced-ediscovery.md)

### <a name="communication"></a>Comunicação

Essa função permite que os usuários gerenciem todas as comunicações com os responsáveis identificados em uma ocorrência de descoberta eletrônica avançada. Isso inclui a criação de notificações de bloqueio, retenção de lembretes e escalações para o gerenciamento. O usuário também pode controlar o reconhecimento de responsáveis pelas notificações de espera e gerenciar o acesso ao portal do responsáveis que é usado por cada pessoa para rastrear as comunicações nos casos em que foram identificados como um usuário.

Para obter mais informações, consulte [trabalhar com comunicações na descoberta eletrônica avançada](managing-custodian-communications.md).

### <a name="compliance-search"></a>Pesquisa de Conformidade

Essa função permite que os usuários executem a ferramenta de pesquisa de conteúdo no centro de conformidade & segurança para pesquisar caixas de correio e pastas públicas, sites do SharePoint Online, sites do OneDrive for Business, conversas do Skype for Business, Microsoft 365 Groups e Microsoft Teams e grupos do Yammer. Essa função permite que um usuário obtenha uma estimativa dos resultados da pesquisa e crie relatórios de exportação, mas as funções adicionais são necessárias para iniciar as ações de pesquisa de conteúdo, como visualização, exportação ou exclusão de resultados de pesquisa.

Os usuários atribuídos à função de pesquisa de conformidade, mas não têm a função Preview, podem visualizar os resultados de uma pesquisa na qual a ação de visualização tenha sido iniciada por um usuário ao qual a função de visualização seja atribuída. O usuário sem a função Preview pode visualizar os resultados por até duas semanas após a criação da ação de visualização inicial.

Da mesma forma, os usuários atribuídos à função de pesquisa de conformidade, mas não têm a função de exportação podem baixar os resultados de uma pesquisa na qual a ação de exportação foi iniciada por um usuário ao qual a função de exportação foi atribuída. O usuário sem a função de exportação pode baixar os resultados de uma pesquisa por até duas semanas após a criação da ação de exportação inicial. Depois, eles não podem baixar os resultados, a menos que alguém com a função exportar reinicie a exportação.

Para obter mais informações, consulte [pesquisa de conteúdo no Office 365](content-search.md).

### <a name="custodian"></a>Custodian

Essa função permite que os usuários identifiquem e gerenciem os responsáveis em casos de descoberta eletrônica avançada e usem as informações do Azure Active Directory e de outras fontes para localizar fontes de dados associadas aos responsáveis. O usuário pode associar outras fontes de dados, como caixas de correio, sites do SharePoint e equipes com os responsáveis em um caso. O usuário também pode colocar uma retenção legal nas fontes de dados associadas aos responsáveis para preservar o conteúdo no contexto de uma ocorrência.

Para obter mais informações, consulte [trabalhar com os responsáveis na descoberta eletrônica avançada](managing-custodians.md).

### <a name="export"></a>Exportar

A função permite que os usuários exportem os resultados de uma pesquisa de conteúdo para um computador local. Ele também permite que eles preparam resultados de pesquisa para análise na descoberta eletrônica avançada. 

Para obter mais informações sobre como exportar resultados de pesquisa, consulte [Exportar resultados de pesquisa do centro de conformidade & segurança](export-search-results.md).

### <a name="hold"></a>Retenção

Essa função permite que os usuários coloquem conteúdo em retenção em caixas de correio, pastas públicas, sites, conversas do Skype for Business e grupos do Microsoft 365. Quando o conteúdo está em espera, os proprietários do conteúdo ainda podem modificar ou excluir o conteúdo original, mas o conteúdo será preservado até que a retenção seja removida ou até que a duração da retenção expire. 

Para obter mais informações sobre isenções, consulte:

- [Criar uma retenção na descoberta eletrônica principal](create-ediscovery-holds.md) 

- [Criar uma retenção na descoberta eletrônica avançada](add-custodians-to-case.md#step-4-place-custodians-on-hold)

### <a name="preview"></a>Visualização

Essa função permite que os usuários exibam uma lista de itens que foram retornados de uma pesquisa de conteúdo. Eles também podem abrir e exibir cada item da lista para exibir seu conteúdo.

### <a name="review"></a>Revisão

Essa função permite que os usuários acessem os dados de ocorrência em [descoberta eletrônica avançada (clássico)](office-365-advanced-ediscovery.md) (também conhecido como *descoberta eletrônica v1 avançada*). O principal objetivo dessa função é fornecer aos usuários acesso à descoberta eletrônica avançada (clássico). Os usuários atribuídos a essa função podem ver e abrir a lista de casos na página **descoberta eletrônica** no centro de conformidade de & de segurança do qual eles são membros. Depois que o usuário acessa um caso no centro de conformidade & segurança, ele pode selecionar **alternar para descoberta eletrônica avançada** para acessar e analisar os dados do caso na descoberta eletrônica avançada (clássico). Essa função não permite que o usuário visualize os resultados de uma pesquisa de conteúdo associada ao caso ou outras tarefas de gerenciamento de caso ou de pesquisa de conteúdo.

> [!NOTE]
> No momento, os usuários atribuídos à função de revisão (ou é um membro do grupo de funções revisor) não podem acessar os dados na [descoberta eletrônica avançada no Microsoft 365](overview-ediscovery-20.md) (também conhecido como *descoberta eletrônica avançada v2*). Para adicionar membros a um caso na descoberta eletrônica avançada v2 para que eles possam revisar os dados do caso, um usuário deve ser membro do grupo de função Gerenciador de descoberta eletrônica.

### <a name="rms-decrypt"></a>Descriptografia do RMS

Essa função permite aos usuários descriptografar mensagens de email protegidas por direitos ao exportar resultados de pesquisa ou preparar resultados de pesquisa para análise na descoberta eletrônica avançada. Para obter mais informações sobre como descriptografar resultados de pesquisa durante a exportação, consulte [Exportar resultados de pesquisa de conteúdo](export-search-results.md).

### <a name="search-and-purge"></a>Pesquisa e limpeza

Essa função permite que os usuários realizem a remoção em massa de dados que correspondam aos critérios de uma pesquisa de conteúdo. Para saber mais, confira [Pesquisar e excluir mensagens de email em sua organização](search-for-and-delete-messages-in-your-organization.md). 

## <a name="more-information"></a>Mais informações

- **Por que criar um Administrador de Descoberta Eletrônica? ** Conforme explicado anteriormente, um Administrador de Descoberta Eletrônica é membro do grupo de funções Gerente de Descoberta Eletrônica e pode ver e acessar todas as ocorrências de Descoberta Eletrônica em sua organização. A capacidade de acessar todas as ocorrências de Descoberta Eletrônica tem duas finalidades importantes: 

  - se uma pessoa que é o único membro de um ocorrência de Descoberta Eletrônica sair de sua organização, ninguém (incluindo os membros do grupo de funções Gerenciamento da organização ou outro membro do grupo de funções Gerente de Descoberta Eletrônica) poderá acessar essa ocorrência de Descoberta Eletrônica, pois não é membro de uma ocorrência. Nessa situação, não haveria um modo de acessar os dados na ocorrência. No entanto, como um administrador de descoberta eletrônica pode acessar todos os casos de descoberta eletrônica na organização, eles podem exibir o caso e adicioná-los ou outro gerenciador de descoberta eletrônica como membro do caso.

  - Como um administrador de descoberta eletrônica pode exibir e acessar todos os principais casos de descoberta eletrônica e descoberta eletrônica avançada, eles podem auditar e supervisionar todos os casos e pesquisas de conformidade associadas. Isso pode ajudar a evitar qualquer mau uso de pesquisas de conformidade ou ocorrências de descoberta eletrônica. E como os administradores de eDiscovery podem acessar informações potencialmente confidenciais nos resultados de uma pesquisa de conformidade, você deve limitar o número de pessoas que são administradores de descoberta eletrônica.

- **Posso adicionar um grupo como membro do grupo de função Gerenciador de descoberta eletrônica?** Conforme explicado anteriormente, você pode adicionar um grupo de segurança habilitado para email como um membro do subgrupo gerenciadores de descoberta eletrônica no grupo de função Gerenciador de descoberta eletrônica usando o cmdlet **Add-RoleGroupMember** no PowerShell do centro de conformidade de segurança &. Por exemplo, você pode executar o seguinte comando para adicionar um grupo de segurança habilitado para email ao grupo de funções Gerenciador de descoberta eletrônica. 

  ```powershell
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    Não há suporte para grupos de distribuição do Exchange e grupos do Microsoft 365. Você deve usar um grupo de segurança habilitado para email, que pode ser criado no PowerShell do Exchange Online usando o `New-DistributionGroup -Type Security` comando. Você também pode criar um grupo de segurança habilitado para email (e adicionar membros) no centro de administração do Exchange ou no centro de administração do Microsoft 365. Pode levar até 60 minutos depois de criá-lo para que uma nova segurança habilitada para email esteja disponível para ser adicionada ao grupo de função gerentes de descoberta eletrônica. 

    Além disso, como declarado anteriormente, você não pode tornar um grupo de segurança habilitado para email em um administrador de descoberta eletrônica usando o cmdlet **Add-eDiscoveryCaseAdmin** no PowerShell do centro de conformidade e segurança &. Você só pode adicionar usuários individuais como administradores de descoberta eletrônica.

    Você também não pode adicionar um grupo de segurança habilitado para email como membro de uma ocorrência.
