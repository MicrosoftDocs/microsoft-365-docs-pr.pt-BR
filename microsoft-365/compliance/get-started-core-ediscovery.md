---
title: Introdução aos casos de descoberta eletrônica principal no Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Este artigo descreve como começar a usar a descoberta eletrônica principal no Microsoft 365. Depois de atribuir permissões de descoberta eletrônica e criar uma ocorrência, você pode adicionar membros, criar isenções de descoberta eletrônica e, em seguida, procurar e exportar dados relevantes à sua investigação.
ms.openlocfilehash: 94c85987be4cbc5da7a378abb7ea74294f6fe740
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357909"
---
# <a name="get-started-with-core-ediscovery"></a>Introdução à Descoberta Eletrônica Central

A descoberta eletrônica principal no Microsoft 365 fornece uma ferramenta de descoberta eletrônica básica que as organizações podem usar para pesquisar e exportar conteúdo no Microsoft 365 e no Office 365. Você também pode usar a descoberta eletrônica principal para colocar um controle de descoberta eletrônica em locais de conteúdo, como caixas de correio do Exchange, sites do SharePoint, contas do OneDrive e Microsoft Teams. Nada é necessário para implantar a descoberta eletrônica principal, mas há algumas tarefas de pré-requisito que um administrador de ti e um gerente de descoberta eletrônica precisam concluir para que sua organização possa começar a usar a descoberta eletrônica principal para pesquisar, exportar e preservar o conteúdo.

Este artigo discute as etapas necessárias para configurar a descoberta eletrônica principal. Isso inclui garantir que o licenciamento apropriado seja necessário para acessar a descoberta eletrônica principal e colocar uma descoberta eletrônica em locais de conteúdo, bem como atribuir permissões à equipe de ti, jurídica e de investigação para que eles possam acessar e gerenciar ocorrências. Este artigo também fornece uma visão geral de alto nível do uso de casos para pesquisar e exportar conteúdo.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Etapa 1: verificar e atribuir licenças apropriadas

O licenciamento da descoberta eletrônica principal requer a assinatura apropriada da organização e o licenciamento por usuário.

- **Assinatura da organização:** Para acessar a descoberta eletrônica Core no centro de conformidade da Microsoft 365 ou no centro de conformidade & segurança do Office 365 e usar os recursos de retenção e exportação, sua organização deve ter uma assinatura do Microsoft 365 E3 ou Office 365 E3 ou superior.

- **Licenciamento por usuário:** Para colocar um controle de descoberta eletrônica em caixas de correio e sites, um usuário deve receber uma das seguintes licenças, dependendo da sua assinatura de organização:

  - Uma licença do Microsoft 365 E3 ou do Office 365 E3 ou superior

   OU

  - Licença do Office 365 E1 com uma licença complementar do Exchange Online Plan 2 ou Exchange Online Archiving

  E

  - Licença do Office 365 E1 com uma licença complementar do SharePoint Online plano 2 ou do OneDrive for Business plano 2
  
  Para obter informações sobre como atribuir licenças, consulte [assign licenses to Users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

Para obter informações sobre licenciamento:

- Baixe e veja a solução "descobrir & responder" na [comparação de licenciamento de conformidade da Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx).

- Consulte a [Descrição do serviço centro de conformidade do & de segurança](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).

## <a name="step-2-assign-ediscovery-permissions"></a>Etapa 2: atribuir permissões de descoberta eletrônica

Para acessar o eDiscovery principal ou ser adicionado como um membro de um caso de descoberta eletrônica principal, um usuário deve ter as permissões apropriadas atribuídas. Especificamente, um usuário deve ser adicionado como um membro do grupo de função Gerenciador de descoberta eletrônica no centro de conformidade & segurança do Office 365. Os membros desse grupo de função podem criar e gerenciar casos de descoberta eletrônica principais. Eles podem adicionar e remover membros, colocar uma descoberta eletrônica em usuários, criar e editar pesquisas e exportar conteúdo de um caso de descoberta eletrônica principal.

Conclua as seguintes etapas para adicionar usuários ao grupo de funções Gerenciador de descoberta eletrônica:

1. Acesse [https://protection.office.com/permissions](https://protection.office.com/permissions) e entre usando as credenciais de uma conta de administrador na sua organização do Microsoft 365 ou do Office 365.

2. Na página **permissões** , selecione o grupo de funções **Gerenciador de descoberta eletrônica** .

3. Na página do submenu Gerenciador de descoberta eletrônica, clique em **Editar** ao lado da seção **Gerenciador de descoberta eletrônica** .

4. Na página **escolher Gerenciador de descoberta eletrônica** no assistente editar grupo de funções, clique em **escolher Gerenciador de descoberta**.

5. Clique em **Adicionar** e marque a caixa de seleção de todos os usuários que você deseja adicionar ao grupo de funções.

6. Clique em **Adicionar** para adicionar os usuários selecionados e clique em **concluído**.

7. Clique em **salvar** para adicionar os usuários ao grupo de função e, em seguida, clique em **fechar** para concluir a etapa.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Mais informações sobre o grupo de funções do Gerenciador de descoberta eletrônica

Há dois subgrupos no grupo de função Gerenciador de descoberta eletrônica. A diferença entre esses subgrupos está no escopo.

- **Gerenciador de descoberta eletrônica:** Pode exibir e gerenciar os principais casos de descoberta eletrônica que eles criam ou são membros de. Se outro gerenciador de descoberta eletrônica criar uma ocorrência, mas não adicionar um segundo Gerenciador de descoberta eletrônica como membro desse caso, o segundo Gerenciador de descoberta eletrônica não poderá exibir ou abrir o caso na página de descoberta eletrônica principal no centro de conformidade. Em geral, a maioria das pessoas em sua organização pode ser adicionada ao subgrupo Gerenciador de descoberta eletrônica.

- **administrador de descoberta eletrônica:** Pode executar todas as tarefas de gerenciamento de caso que um gerente de descoberta eletrônica possa fazer. Além disso, um Administrador de Descoberta Eletrônica pode:

  - Exibir todas as ocorrências listadas na página de descoberta eletrônica principal.
  
  - Gerencie qualquer caso na organização depois que eles se adicionarem como um membro do caso.

  - Acessar e exportar dados de caso para qualquer caso na organização.

  Por causa do amplo escopo de acesso, uma organização deve ter apenas alguns administradores que são membros do subgrupo administradores de descoberta eletrônica.

Para obter mais informações sobre permissões de descoberta eletrônica e uma descrição de cada função atribuída ao grupo de funções Gerenciador de descoberta eletrônica, consulte [atribuir permissões de descoberta eletrônica](assign-ediscovery-permissions.md).

## <a name="step-3-create-a-core-ediscovery-case"></a>Etapa 3: criar um caso de descoberta eletrônica principal

A próxima etapa é criar um caso e começar a usar a descoberta eletrônica principal. Conclua as etapas a seguir para criar um caso e adicionar membros. O usuário que cria o caso é automaticamente adicionado como um membro.

1. Acesse [https://compliance.microsoft.com](https://compliance.microsoft.com) e entre usando as credenciais de uma conta de usuário que recebeu as permissões de descoberta eletrônica apropriadas. Os membros do grupo de função gerenciamento da organização também podem criar casos de descoberta eletrônica principais.

2. No painel de navegação esquerdo do centro de conformidade da Microsoft 365, clique em **Mostrar tudo**e, em seguida, clique em **descoberta eletrônica > Core**.

3. Na página de **descoberta eletrônica principal** , clique em **criar uma ocorrência**.

4. Na página **novo** submenu de caso, dê um nome (obrigatório) e, em seguida, digite um número de caso e descrição opcionais. O nome da ocorrência deve ser exclusivo em sua organização.

5. Clique em **salvar** para criar o caso.

   A nova ocorrência é criada e exibida na página de descoberta eletrônica principal. Talvez seja necessário clicar em **Atualizar** para exibir o novo caso. 

## <a name="step-4-optional-add-members-to-a-core-ediscovery-case"></a>Etapa 4 (opcional): adicionar membros a uma caixa de descoberta eletrônica principal

Se você criar uma ocorrência na etapa 3 e for a única pessoa que usará a ocorrência, não será necessário executar essa etapa. Você pode começar a usar o caso para criar bloqueios de descoberta eletrônica, pesquisar conteúdo ou exportar resultados de pesquisa. Execute esta etapa se desejar conceder acesso ao caso a outros usuários (ou grupo de funções).

1. Na página de **descoberta eletrônica principal** no centro de conformidade do Microsoft 365, clique no nome do caso para o qual você deseja adicionar membros.

2. Na página **gerenciar esse** submenu de caso, em **gerenciar Membros**, clique em **Adicionar** para adicionar membros ao caso. 

    Você também pode optar por adicionar o grupo de função como membros de uma ocorrência. Em **gerenciar grupos de função**, clique em **Adicionar**. Você só pode atribuir os grupos de funções dos quais você é membro a um caso. Isso ocorre porque os grupos de função controlam quem pode atribuir membros a uma ocorrência de descoberta eletrônica.

3. Na lista de pessoas ou grupos de funções que podem ser adicionados como membros do caso, clique na caixa de seleção ao lado dos nomes das pessoas (ou grupos de funções) que você deseja adicionar. Se você tiver uma lista grande de pessoas que podem ser adicionadas como membros, use a caixa **Pesquisar** para procurar uma pessoa específica na lista.
  
4. Depois de selecionar as pessoas ou os grupos de funções a serem adicionados como membros do caso, clique em **Adicionar**.

5. Clique em **salvar** para salvar a nova lista de membros de caso.

## <a name="explore-the-core-ediscovery-workflow"></a>Explorar o fluxo de trabalho de descoberta eletrônica principal

Para começar a usar a descoberta eletrônica principal, aqui está um fluxo de trabalho simples de criação de descoberta eletrônica para pessoas de interesse, pesquisando conteúdo que seja relevante para sua investigação e, em seguida, exportando os dados para análise adicional. Em cada uma dessas etapas, também realçaremos algumas funcionalidades estendidas de descoberta eletrônica que podem ser exploradas.

![Fluxo de trabalho de descoberta eletrônica principal](../media/CoreEdiscoveryWorkflow.png)

1. **[Criar uma retenção de descoberta eletrônica](create-ediscovery-holds.md)**. A primeira etapa depois da criação de um caso é colocar uma retenção (também chamada de *descoberta eletrônica*) nos locais de conteúdo das pessoas de interesse em sua investigação. Os locais de conteúdo incluem caixas de correio do Exchange, sites do SharePoint, contas do OneDrive, bem como caixas de correio e sites associados ao Microsoft Teams e grupos do Office 365. Embora esta etapa seja opcional, a criação de uma descoberta eletrônica preserva o conteúdo que pode ser relevante para o caso durante a investigação. Ao criar um controle de descoberta eletrônica, você pode preservar todo o conteúdo em locais de conteúdo específicos ou pode criar um bloqueio baseado em consulta para preservar apenas o conteúdo que corresponde a uma consulta de bloqueio. Além de preservar o conteúdo, outro bom motivo para criar descoberta eletrônica é pesquisar rapidamente os locais de conteúdo em espera (em vez de ter que selecionar cada local para Pesquisar) ao criar e executar pesquisas na próxima etapa. Após concluir sua investigação, você pode liberar qualquer isenção que você criou.

2. **[Pesquisa de conteúdo](search-for-content-in-core-ediscovery.md)**. Após criar as isenções de descoberta eletrônica, use a ferramenta de pesquisa interna para pesquisar os locais de conteúdo em espera. Você também pode pesquisar outros locais de conteúdo para dados que podem ser relevantes para o caso. Você pode criar e executar pesquisas diferentes que estão associadas à ocorrência. Você usa palavras-chave, propriedades e condições para [criar consultas de pesquisa](keyword-queries-and-search-conditions.md) que retornem resultados de pesquisa com os dados que mais provavelmente são relevantes para o caso. Você também pode:

   - Exibir estatísticas de pesquisa que podem ajudá-lo a refinar uma consulta de pesquisa para restringir os resultados.

   - Visualize os resultados da pesquisa para verificar rapidamente se os dados relevantes estão sendo encontrados.

   - Revise uma consulta e execute a pesquisa novamente.

3. **[Exportar e baixar resultados de pesquisa](export-content-in-core-ediscovery.md)**. Depois de Pesquisar e localizar dados relevantes à sua investigação, você poderá exportá-los fora do Office 365 para análise por pessoas de fora da equipe de investigação. A exportação de dados é um processo de duas etapas. A primeira etapa é exportar os resultados de uma pesquisa no caso do Office 365. Isso é feito copiando os resultados de uma pesquisa para um local de armazenamento do Azure fornecido pela Microsoft. A próxima etapa é usar a ferramenta de exportação de descoberta eletrônica para baixar o conteúdo para um computador local. Além dos arquivos de dados exportados, o contém o pacote de exportação também contém um relatório de exportação, um relatório de resumo e um relatório de erros.
