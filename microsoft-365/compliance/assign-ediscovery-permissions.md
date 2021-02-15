---
title: Atribuir permissões de Descoberta e no Centro de Conformidade & segurança
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
description: Atribua as permissões necessárias para executar tarefas relacionadas à Descoberta e usando o Centro de Conformidade e & Segurança.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4d4be264791c4f3d37d7a88cb3d12d1023b3c347
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759885"
---
# <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>Atribuir permissões de Descoberta e no Centro de Conformidade & segurança

Se você quiser que as [](ediscovery.md) pessoas usem qualquer uma das ferramentas relacionadas à Descoberta Online no Centro de Conformidade do & de Segurança no Office 365 ou no centro de conformidade do Microsoft 365, você deve atribuir as permissões apropriadas. A maneira mais fácil de fazer isso é adicionar a pessoa ao grupo de função apropriado na página **Permissões,** no Centro de Conformidade e Segurança & Segurança. Este tópico descreve as permissões necessárias para executar tarefas relacionadas à Descoberta e à Pesquisa de Conteúdo usando o Centro de Conformidade e Segurança & Segurança.
  
O grupo de função principal relacionado à Descoberta eDiscovery no Centro de & Conformidade e Segurança é chamado de **Gerente de Descobertas e Descobertas.** Há dois subgrupos dentro desse grupo de função.
  
- Gerentes de Descoberta **EDiscovery** - Um Gerente de Descoberta e Pode usar a ferramenta pesquisa de conteúdo no Centro de Conformidade de & segurança para pesquisar locais de conteúdo na organização e executar várias ações relacionadas à pesquisa, como visualizar e exportar resultados de pesquisa. Os membros também podem criar e gerenciar ocorrências na Descoberta Principal e Na Descoberta Avançada, adicionar e remover membros de uma ocorrência, criar remoção de caso, executar pesquisas associadas a uma ocorrência e acessar dados de caso. Os Gerentes de Descobertas Do eDiscovery só podem acessar e gerenciar os casos que criam. Eles não podem acessar ou gerenciar casos criados por outros Gerentes de Descobertas eDiscovery.
  
- Administradores de Descobertas e Descobertas - Um Administrador de Descoberta eDiscovery é membro do grupo de função Gerente de Descobertas e pode executar as mesmas tarefas **relacionadas** ao gerenciamento de caso e pesquisa de conteúdo que um Gerente de Descobertas Descoberta Pode realizar. Além disso, um Administrador de Descoberta Eletrônica pode:
  
  - Acessar todos os casos  que estão listados nas páginas Descobertas e Descobertas Avançadas no Centro de Conformidade & Segurança. 

  - Acessar dados de ocorrência na Descoberta Avançada para qualquer caso na organização.
  
  - Gerencie qualquer caso de Descoberta e Depois de adicionar a si mesmo como um membro da ocorrência.
  
  Por motivos pelos quais você pode querer administradores de descoberta de eDiscovery em sua organização, consulte [Mais informações.](#more-information)

> [!NOTE]
> Para analisar os dados de um usuário usando a Descoberta Avançada, o usuário (o custodiante dos dados) deve ter uma licença do Office 365 E5 ou do Microsoft 365 E5. Como alternativa, os usuários com uma licença do Office 365 E1 ou do Office 365 ou Do Microsoft 365 E3 podem ter uma licença de complemento de Conformidade ou Auditoria do Microsoft 365 E5 ou Decodovery e Audit do Microsoft 365. Administradores, responsáveis pela conformidade ou pessoal jurídico que são atribuídos a casos como membros e usam a Descoberta Avançada para coletar, exibir e analisar dados não precisam de uma licença E5. Para obter mais informações sobre o licenciamento de Descoberta Avançada, consulte [Get started with Advanced eDiscovery](get-started-with-advanced-ediscovery.md).
  
## <a name="confirm-your-roles"></a>Confirmar suas funções

- Você precisa ser membro do grupo de funções Gerenciamento da Organização ou ter a função Gerenciamento de Função atribuída para atribuir permissões de Descoberta eDiscovery no Centro de Conformidade & Segurança.

- Você pode usar o cmd & let [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember) no PowerShell do Centro de Conformidade e Segurança para adicionar um grupo de segurança habilitado para email como membro do subgrupo Gerentes de Descoberta Eletrônica no grupo de função Gerente de Descoberta Eletrônica. No entanto, não é possível adicionar um grupo de segurança habilitado para email ao subgrupo Administradores de Descoberta Eletrônico. Para obter detalhes, consulte [Mais informações.](#more-information) 
  
## <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>Atribuir permissões de Descoberta e no Centro de Conformidade & segurança

1. Acesse [https://protection.office.com](https://protection.office.com).
  
2. Entre usando sua conta de trabalho ou da escola.
  
3. No painel esquerdo do centro de conformidade e segurança, selecione Permissões e marque a caixa de seleção ao lado do **Gerenciador de Descobertas Automáticas.**
  
4. Na página do flyout do Gerenciador de Descobertas **DoeDiscovery,** faça um dos seguintes com base nas permissões de Descoberta eDiscovery que você deseja atribuir.
  
    **Para tornar um usuário um Gerente de DescobertaScoberta:** Ao lado **do Gerente de Descoberta eDiscovery,** selecione **Editar**. Na seção Escolher Gerente de Descoberta **e,** em seguida, selecione o hiperlink Escolher Gerenciador de Descobertas **e,** em seguida, ![ selecione Adicionar Ícone ](../media/ITPro-EAC-AddIcon.gif) **Adicionar.** Selecione o usuário (ou usuários) que você deseja adicionar como um gerente de Descoberta e, em seguida, selecione **Adicionar**. Quando terminar de adicionar usuários, selecione **Concluído.** Em seguida, na página do flyout  **Editing Choose eDiscovery Manager,** selecione Salvar para salvar as alterações na associação do Gerenciador de Descobertas.
  
    **Para tornar um usuário um Administrador de DescobertaScoberta:** Ao lado **do Gerente de Descoberta eDiscovery,** selecione **Editar**. In the **Choose eDiscovery Administrator** section, Under **eDiscovery Administrators**, select **Choose eDiscovery Administrator**, select **Edit**, and then select Add ![ Icon ](../media/ITPro-EAC-AddIcon.gif) **Add**. Selecione o usuário (ou usuários) que você deseja adicionar como Administrador de **Descobertas e,** em seguida,  **Adicione**. Quando terminar de adicionar usuários, selecione **Concluído.** Em seguida, na página Do flyout **Editing Choose eDiscovery Administrator,** selecione **Salvar** para salvar as alterações na associação do Administrador de Descobertas.
  
> [!NOTE]
> Você também pode usar o cmdlet **Add-eDiscoveryCaseAdmin** para tornar um usuário um Administrador de Descoberta Eletrônica. No entanto, o usuário deve ter a função De gerenciamento de ocorrências atribuída antes que você possa usar esse cmdlet para torná-lo um Administrador de Descoberta Eletrônica. Para obter mais informações, [consulte Add-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkID=798217). 
  
Na  página Permissões do Centro de Conformidade & Segurança, você também pode atribuir permissões relacionadas à Descoberta e Aos usuários adicionando-os aos grupos de funções Administrador de Conformidade, Gerenciamento da Organização e Revistor. Para uma descrição das funções RBAC relacionadas à Descoberta e atribuídas a cada um desses grupos de função, consulte as funções do RBAC relacionadas à [Descoberta eDiscovery](#rbac-roles-related-to-ediscovery).

## <a name="rbac-roles-related-to-ediscovery"></a>Funções do RBAC relacionadas à Descoberta e

A tabela a seguir lista as funções RB & AC relacionadas à Descoberta e no Centro de Conformidade e Segurança e indica os grupos de função integrados aos quais cada função é atribuída por padrão.
  
| Função | Administrador de Conformidade | Gerente de Descoberta & Administrador | Gerenciamento de Organização | Revisor |
|:-----|:-----:|:-----:|:-----:|:-----:|
|Gerenciamento de Casos <br/> |![Marca de seleção](../media/checkmark.png) <br/> |![Marca de seleção](../media/checkmark.png) <br/> |![Marca de seleção](../media/checkmark.png) <br/> | <br/> |
|Comunicação <br/> | <br/> |![Marca de seleção](../media/checkmark.png) <br/> | <br/> | <br/> |
|Pesquisa de Conformidade <br/> |![Marca de seleção](../media/checkmark.png) <br/> |![Marca de seleção](../media/checkmark.png) <br/> |![Marca de seleção](../media/checkmark.png) <br/> | <br/> |
|Custodian <br/> | <br/> |![Marca de seleção](../media/checkmark.png) <br/> | <br/> | <br/> |
|Exportar <br/> | <br/> |![Marca de seleção](../media/checkmark.png) <br/> | <br/> | <br/> |
|Retenção <br/>  |![Marca de seleção](../media/checkmark.png) <br/> |![Marca de seleção](../media/checkmark.png) <br/> |![Marca de seleção](../media/checkmark.png) <br/> | <br/> |
|Visualização <br/>  | <br/> |![Marca de seleção](../media/checkmark.png) <br/> | <br/> | <br/> |
|Analisar <br/>  | <br/> |![Marca de seleção](../media/checkmark.png) <br/> | <br/> |![Marca de seleção](../media/checkmark.png) <br/> |
|Descriptografar RMS <br/>  ||![Marca de seleção](../media/checkmark.png) <br/> |||
|Pesquisar e limpar <br/> | <br/> | <br/> |![Marca de seleção](../media/checkmark.png)           <br/> | <br/> |
||||
  
As seções a seguir descrevem cada uma das funções do RBAC relacionadas à Descoberta e listadas na tabela anterior.

### <a name="case-management"></a>Gerenciamento de Casos

Essa função permite que os usuários criem, editem, excluam e controlem o acesso às ocorrências de Descobertas Principais e Descobertas Eletivas Avançadas no Centro de Conformidade e Segurança & Segurança. Conforme explicado anteriormente, um usuário deve ter a função de Gerenciamento de Ocorrências atribuída para que você possa usar o cmdlet **Add-eDiscoveryCaseAdmin para torná-lo** um Administrador de Descoberta Eletrônica.

Para saber mais, confira:

- [Introdução à Descoberta Eletrônica Central](get-started-core-ediscovery.md)

- [Introdução à Descoberta Eletrônica Avançada](get-started-with-advanced-ediscovery.md)

### <a name="communication"></a>Comunicação

Essa função permite que os usuários gerenciem todas as comunicações com os custodiantes identificados em um caso de Descoberta Eletrônica Avançada. Isso inclui a criação de notificações de espera, lembretes de espera e escalonamentos para gerenciamento. O usuário também pode acompanhar a confirmação custodiada de notificações de isenção e gerenciar o acesso ao portal custodiado que é usado por cada responsável para controlar as comunicações para os casos em que foram identificados como um custodiatário.

Para obter mais informações, [consulte Trabalhar com comunicações na Descoberta Eletrônica Avançada.](managing-custodian-communications.md)

### <a name="compliance-search"></a>Pesquisa de Conformidade

Essa função permite que os usuários executem a ferramenta Pesquisa de Conteúdo no Centro de Conformidade e Segurança para pesquisar caixas de correio e pastas públicas, sites do SharePoint Online, sites do OneDrive for Business, conversas do Skype for Business, grupos do Microsoft 365 e Microsoft Teams e grupos do Yammer. & Essa função permite que um usuário receba uma estimativa dos resultados da pesquisa e crie relatórios de exportação, mas funções adicionais são necessárias para iniciar ações de pesquisa de conteúdo, como visualização, exportação ou exclusão de resultados de pesquisa.

Os usuários que têm a função Pesquisa de Conformidade, mas não têm a função Visualização, podem visualizar os resultados de uma pesquisa na qual a ação de visualização foi iniciada por um usuário que recebeu a função Visualização. O usuário sem a função Visualização pode visualizar os resultados por até duas semanas após a criação da ação de visualização inicial.

Da mesma forma, os usuários que têm a função Pesquisa de Conformidade, mas não têm a função Exportar, podem baixar os resultados de uma pesquisa na qual a ação de exportação foi iniciada por um usuário que recebe a função Exportar. O usuário sem a função Exportar pode baixar os resultados de uma pesquisa por até duas semanas após a ação de exportação inicial ter sido criada. Depois disso, eles não poderão baixar os resultados, a menos que alguém com a função Exportar reinicie a exportação.

Para saber mais, confira [Pesquisa de conteúdo no Office 365.](content-search.md)

### <a name="custodian"></a>Custodian

Essa função permite que os usuários identifiquem e gerenciem custodiantes para casos de Descoberta Avançada e usem as informações do Azure Active Directory e de outras fontes para encontrar fontes de dados associadas a custodiantes. O usuário pode associar outras fontes de dados, como caixas de correio, sites do SharePoint e Teams, a custodiantes em uma ocorrência. O usuário também pode colocar uma responsabilidade legal sobre as fontes de dados associadas aos responsáveis para preservar o conteúdo no contexto de um caso.

Para obter mais informações, [consulte Trabalhar com custodiantes na Descoberta eDiscovery Avançada.](managing-custodians.md)

### <a name="export"></a>Exportar

A função permite que os usuários exportem os resultados de uma Pesquisa de Conteúdo para um computador local. Ele também permite que eles preparem os resultados da pesquisa para análise na Descoberta Avançada.

Para obter mais informações sobre como exportar resultados de pesquisa, consulte Exportar resultados de pesquisa do Centro de Conformidade e [& Segurança.](export-search-results.md)

### <a name="hold"></a>Retenção

Essa função permite que os usuários coloquem conteúdo em espera em caixas de correio, pastas públicas, sites, conversas do Skype for Business e grupos do Microsoft 365. Quando o conteúdo está em espera, os proprietários de conteúdo ainda podem modificar ou excluir o conteúdo original, mas o conteúdo será preservado até que a espera seja removida ou até que a duração da espera expire.

Para obter mais informações sobre retém, consulte:

- [Criar uma espera na Descoberta eDiscovery Principal](create-ediscovery-holds.md) 

- [Criar uma espera na Descoberta Avançada](add-custodians-to-case.md)

### <a name="preview"></a>Visualização

Essa função permite que os usuários exibirem uma lista de itens que foram retornados de uma Pesquisa de Conteúdo. Eles também podem abrir e exibir cada item da lista para exibir seu conteúdo.

### <a name="review"></a>Analisar

Essa função permite que os usuários acessem conjuntos de revisão na [Descoberta Avançada.](overview-ediscovery-20.md) Os usuários aos quais essa função foi atribuída podem ver e abrir a lista de ocorrências na página de Descoberta > **Avançado** no centro de conformidade do Microsoft 365 dos quais eles são membros. Depois que o usuário acessar um caso de Descoberta Avançada, ele poderá selecionar Conjuntos **de** revisão para acessar dados de ocorrência. Essa função não permite que o usuário visualize os resultados de uma pesquisa de coleção associada ao caso ou faça outras tarefas de gerenciamento de caso ou pesquisa. Os usuários com essa função só podem acessar os dados em um conjunto de revisão.

### <a name="rms-decrypt"></a>Descriptografar RMS

Essa função permite que os usuários visualizem mensagens de email protegidas por direitos ao visualizar os resultados da pesquisa e exportar mensagens de email descriptografadas protegidas por direitos. Essa função também permite aos usuários exibir (e exportar) um arquivo que é criptografado com uma tecnologia de criptografia da [Microsoft](encryption.md) quando o arquivo criptografado é anexado a uma mensagem de email incluída nos resultados de uma pesquisa de Descoberta Eletrônico. Além disso, essa função permite que os usuários revisem e consultem anexos de email criptografados adicionados a um conjunto de revisão na Descoberta Avançada. Para obter mais informações sobre a descriptografia na Descoberta eDiscovery, consulte Descriptografia nas ferramentas de [Descoberta eDiscovery do Microsoft 365.](ediscovery-decryption.md)

### <a name="search-and-purge"></a>Pesquisar e limpar

Essa função permite que os usuários realizem a remoção em massa de dados que corresponderem aos critérios de uma pesquisa de conteúdo. Para obter mais informações, [consulte Pesquisar e excluir mensagens de email em sua organização.](search-for-and-delete-messages-in-your-organization.md)

## <a name="more-information"></a>Mais informações

- **Por que criar um Administrador de Descoberta Eletrônica?** Conforme explicado anteriormente, um Administrador de Descoberta Eletrônica é membro do grupo de funções Gerente de Descoberta Eletrônica e pode ver e acessar todas as ocorrências de Descoberta Eletrônica em sua organização. A capacidade de acessar todas as ocorrências de Descoberta Eletrônica tem duas finalidades importantes:

  - se uma pessoa que é o único membro de um ocorrência de Descoberta Eletrônica sair de sua organização, ninguém (incluindo os membros do grupo de funções Gerenciamento da organização ou outro membro do grupo de funções Gerente de Descoberta Eletrônica) poderá acessar essa ocorrência de Descoberta Eletrônica, pois não é membro de uma ocorrência. Nessa situação, não haveria um modo de acessar os dados na ocorrência. Porém, como um Administrador de Descoberta eDiscovery pode acessar todos os casos de Descoberta eDiscovery na organização, ele pode exibir a ocorrência e adicionar a si mesmo ou outro gerente de Descoberta eDiscovery como um membro da ocorrência.

  - Como um Administrador de Descobertas EDiscovery pode exibir e acessar todas as ocorrências de Descobertas e Descobertas Principais e Descobertas Avançadas, ele pode auditar e supervisionar todas as ocorrências e pesquisas de conformidade associadas. Isso pode ajudar a evitar o uso indevido de pesquisas de conformidade ou ocorrências de DescobertaScoberta. E como os Administradores de Descobertas Do eDiscovery podem acessar informações potencialmente confidenciais nos resultados de uma pesquisa de conformidade, você deve limitar o número de pessoas que são Administradores de Descobertas.

- **Posso adicionar um grupo como um membro do grupo de função gerente de descoberta de ediscovery?** Conforme explicado anteriormente, você pode adicionar um grupo de segurança habilitado para email como membro do subgrupo Gerentes de Descoberta Eletrônica no grupo de função Gerente de Descoberta Eletrônica usando o cmdlet **Add-RoleGroupMember** no PowerShell do Centro de Conformidade e Segurança do &. Por exemplo, você pode executar o seguinte comando para adicionar um grupo de segurança habilitado para email ao grupo de funções do Gerenciador de Descobertas Eletrônicos. 

  ```powershell
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    Não há suporte para grupos de distribuição do Exchange e grupos do Microsoft 365. Você deve usar um grupo de segurança habilitado para email, que pode criar no PowerShell do Exchange Online `New-DistributionGroup -Type Security` executando. Você também pode criar um grupo de segurança habilitado para email (e adicionar membros) no Centro de administração do Exchange ou no centro de administração do Microsoft 365. Pode levar até 60 minutos depois de você criar para que uma nova segurança habilitada para email seja disponibilizada para ser acrescentada ao grupo de funções Gerentes de Descoberta Eletrônico. 

    Além disso, conforme mencionado anteriormente, não é possível tornar um grupo de segurança habilitado para email um Administrador de Descoberta Eletrônica usando o cmd & let **Add-eDiscoveryCaseAdmin** no PowerShell do Centro de Conformidade e Segurança. Você só pode adicionar usuários individuais como Administradores de Descobertas.

    Você também não pode adicionar um grupo de segurança habilitado para email como membro de uma ocorrência.
