---
title: Começar a trabalhar com os principais casos de Descoberta Desdiscover no Microsoft 365
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
description: Este artigo descreve como começar a usar a Descoberta eDiscoveria principal no Microsoft 365. Depois de atribuir permissões de Descoberta E e criar um caso, você pode adicionar membros, criar regiões de Descoberta e, em seguida, pesquisar e exportar dados relevantes para sua investigação.
ms.openlocfilehash: 4a814b2e0019f86e4a4fc0e26d19df4411402749
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919757"
---
# <a name="get-started-with-core-ediscovery"></a>Introdução à Descoberta Eletrônica Central

O Core eDiscovery no Microsoft 365 fornece uma ferramenta básica de Descoberta Digital que as organizações podem usar para pesquisar e exportar conteúdo no Microsoft 365 e no Office 365. Você também pode usar a Descoberta Eletrônico Principal para colocar uma responsabilidade de Descoberta Eletrônico em locais de conteúdo, como caixas de correio do Exchange, sites do SharePoint, contas do OneDrive e Microsoft Teams. Nada é necessário para implantar a Descoberta Principal, mas há algumas tarefas de pré-requisitos que um administrador de IT e o gerente de Descobertas Online precisam concluir para que sua organização possa começar a usar a Descoberta Básica para pesquisar, exportar e preservar conteúdo.

Este artigo discute as etapas necessárias para configurar a Descoberta Principal da Descoberta e. Isso inclui garantir o licenciamento adequado necessário para acessar a Descoberta Principal e colocar uma responsabilidade de Descoberta eDiscovery em locais de conteúdo, bem como atribuir permissões à equipe de IT, legal e de investigação para que eles possam acessar e gerenciar casos. Este artigo também fornece uma visão geral de alto nível do uso de casos para pesquisar e exportar conteúdo.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Etapa 1: Verificar e atribuir licenças apropriadas

O licenciamento para a Descoberta Interna requer a assinatura da organização apropriada e o licenciamento por usuário.

- **Assinatura da organização:** Para acessar o Core eDiscovery no Centro de conformidade do Microsoft 365 ou no Centro de Conformidade de Segurança & do Office 365 e usar os recursos de responsabilidade e exportação, sua organização deve ter uma assinatura do Microsoft 365 E3 ou office 365 E3 ou superior.

- **Licenciamento por usuário:** Para colocar uma responsabilidade de Descoberta Eletrônico em caixas de correio e sites, um usuário deve receber uma das seguintes licenças, dependendo da assinatura da sua organização:

  - Uma licença do Microsoft 365 E3 ou Office 365 E3 ou superior

   OU

  - Licença do Office 365 E1 com uma licença de complemento do Plano 2 ou Arquivamento do Exchange Online do Exchange Online

  E

  - Licença do Office 365 E1 com uma licença de complemento do Plano 2 do SharePoint Online ou do OneDrive for Business Plan 2
  
  Para obter informações sobre como atribuir licenças, consulte [Assign licenses to users](../admin/manage/assign-licenses-to-users.md).

Para obter informações sobre licenciamento:

- Baixe e consulte a solução "Descobrir & Responder" na Comparação de Licenciamento [de Conformidade do Microsoft 365.](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)

- Consulte a descrição do [serviço & Centro de Conformidade.](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)

## <a name="step-2-assign-ediscovery-permissions"></a>Etapa 2: Atribuir permissões de Descoberta e

Para acessar a Descoberta Interna ou ser adicionado como membro de um caso core de Descoberta eDiscovery, um usuário deve ter as permissões apropriadas. Especificamente, um usuário deve ser adicionado como membro do grupo de funções do Gerenciador de Descobertas Do Office 365 no Centro de Conformidade & Segurança do Office 365. Os membros desse grupo de função podem criar e gerenciar os principais casos de Descoberta eDiscovery. Eles podem adicionar e remover membros, colocar uma responsabilidade de Descoberta EDiscovery em usuários, criar e editar pesquisas e exportar conteúdo de um caso de Descoberta Interna.

Conclua as etapas a seguir para adicionar usuários ao grupo de funções do Gerenciador de Descobertas E:

1. Acesse e entre usando as credenciais de uma conta de administrador em sua organização do [https://protection.office.com/permissions](https://protection.office.com/permissions) Microsoft 365 ou Office 365.

2. Na página **Permissões,** selecione o grupo de função **Gerenciador de** Descobertas.

3. Na página de sobrevoo do Gerenciador de Descobertas e, em Seguida, clique em **Editar** ao lado da **seção Gerenciador de** Descobertas E.

4. Na página **Escolher Gerente de Descoberta Virtual** no assistente editar grupo de funções, clique em Escolher Gerenciador de **Descoberta**.

5. Clique **em Adicionar** e selecione a caixa de seleção para todos os usuários que você deseja adicionar ao grupo de funções.

6. Clique **em Adicionar** para adicionar os usuários selecionados e clique em **Feito**.

7. Clique **em Salvar** para adicionar os usuários ao grupo de funções e clique em **Fechar** para concluir a etapa.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Mais informações sobre o grupo de funções do Gerenciador de Descobertas E

Há dois subgrupos no grupo de funções do Gerenciador de Descobertas. A diferença entre esses subgrupos está no escopo.

- **EDiscovery Manager:** Pode exibir e gerenciar os principais casos de Descoberta EDiscovery dos quais eles criam ou são membros. Se outro Gerenciador de Descobertas De eDiscovery criar um caso, mas não adicionar um segundo Gerenciador de Descobertas Deeconsutórias como membro desse caso, o segundo Gerenciador de Descobertas De eDiscovery não poderá exibir ou abrir o caso na página Descoberta eDiscoveria Principal no centro de conformidade. Em geral, a maioria das pessoas em sua organização pode ser adicionada ao subgrupo do Gerenciador de Descobertas.

- Administrador de Descoberta **e:** Pode executar todas as tarefas de gerenciamento de casos que um Gerenciador de Descobertas Públicas pode fazer. Além disso, um Administrador de Descoberta Eletrônica pode:

  - Exibir todos os casos listados na página Descoberta Principal.
  
  - Gerencie qualquer caso na organização depois que eles se adicionarem como um membro do caso.

  - Acessar e exportar dados de caso para qualquer caso na organização.

  Devido ao amplo escopo de acesso, uma organização deve ter apenas alguns administradores membros do subgrupo Administradores de Descoberta e.

Para obter mais informações sobre permissões de Descoberta E e uma descrição de cada função atribuída ao grupo de funções do Gerenciador de Descobertas E, consulte [Assign eDiscovery permissions](assign-ediscovery-permissions.md).

## <a name="step-3-create-a-core-ediscovery-case"></a>Etapa 3: Criar um caso principal de Descoberta eDiscovery

A próxima etapa é criar uma ocorrência e começar a usar a Descoberta Principal. Conclua as etapas a seguir para criar uma ocorrência e adicionar membros. O usuário que cria a ocorrência é adicionado automaticamente como membro.

1. Acesse e entre usando as credenciais de uma conta de usuário que recebeu as permissões de [https://compliance.microsoft.com](https://compliance.microsoft.com) Descoberta eDiscovery apropriadas. Os membros do grupo de função Gerenciamento da Organização também podem criar principais casos de Descoberta eDiscovery.

2. No painel de navegação esquerdo do centro de conformidade do Microsoft 365, clique em **Mostrar** tudo e clique em **Descoberta > Core**.

3. Na página **Descoberta Principal da Descoberta e,** clique em Criar um **caso**.

4. Na página **Novo caso,** dê ao caso um nome (obrigatório) e digite um número de caso opcional e uma descrição. O nome do caso deve ser exclusivo em sua organização.

5. Clique **em Salvar** para criar o caso.

   O novo caso é criado e exibido na página Descoberta Principal. Talvez seja preciso clicar em **Atualizar** para exibir o novo caso. 

## <a name="step-4-optional-add-members-to-a-core-ediscovery-case"></a>Etapa 4 (opcional): Adicionar membros a um caso de Descoberta Principal de Descoberta e

Se você criar um caso na Etapa 3 e for a única pessoa que usará o caso, não será preciso executar esta etapa. Você pode começar a usar o caso para criar ressarces de Descoberta e, pesquisar conteúdo ou exportar resultados de pesquisa. Execute esta etapa se você quiser dar a outros usuários (ou grupos de funções) acesso ao caso.

1. Na página **Descoberta Principal da** Descoberta e No Centro de conformidade do Microsoft 365, clique no nome do caso ao que você deseja adicionar membros.

2. Na página **Gerenciar o** sub-subsistência desta ocorrência, em **Gerenciar membros,** clique em **Adicionar** para adicionar membros ao caso. 

    Você também pode optar por adicionar grupo de funções como membros de uma ocorrência. Em **Gerenciar grupos de função,** clique em **Adicionar**. Você só pode atribuir os grupos de função dos que você é membro a um caso. Isso ocorre porque os grupos de função controlam quem pode atribuir membros a um caso de Descoberta E.

3. Na lista de pessoas ou grupos de função que podem ser adicionados como membros da ocorrência, clique na caixa de seleção ao lado dos nomes das pessoas (ou grupos de função) que você deseja adicionar. Se você tiver uma lista grande de pessoas  que podem ser adicionadas como membros, use a caixa Pesquisar para pesquisar uma pessoa específica na lista.
  
4. Depois de selecionar as pessoas ou grupos de função a adicionar como membros do caso, clique em **Adicionar**.

5. Clique **em Salvar** para salvar a nova lista de membros da ocorrência.

## <a name="explore-the-core-ediscovery-workflow"></a>Explorar o fluxo de trabalho principal de Descoberta Eletrônico

Para começar a usar a Descoberta Eletrônico principal, aqui está um fluxo de trabalho simples de criação de regiões de Descoberta Eletrônico para pessoas de interesse, a pesquisa de conteúdo relevante para sua investigação e, em seguida, a exportação desses dados para revisão posterior. Em cada uma dessas etapas, também destacaremos algumas funcionalidades de Descoberta eDiscoveria Básica estendidas que você pode explorar.

![Fluxo de trabalho principal de Descoberta Eletrônico](../media/CoreEdiscoveryWorkflow.png)

1. **[Criar uma responsabilidade de Descoberta E.](create-ediscovery-holds.md)** A primeira etapa após a criação de um caso é colocar uma responsabilidade (também chamada de ressarção de *Descoberta* e) nos locais de conteúdo das pessoas de interesse em sua investigação. Os locais de conteúdo incluem caixas de correio do Exchange, sites do SharePoint, contas do OneDrive, bem como caixas de correio e sites associados ao Microsoft Teams e grupos do Office 365. Embora esta etapa seja opcional, a criação de uma isenção de descoberta de eDiscovery preserva o conteúdo que pode ser relevante para o caso durante a investigação. Ao criar uma ressarção de Descoberta e, você pode preservar todo o conteúdo em locais de conteúdo específicos ou criar uma responsabilidade baseada em consulta para preservar apenas o conteúdo que corresponde a uma consulta de espera. Além de preservar o conteúdo, outro bom motivo para criar regiões de Descoberta eDiscovery é pesquisar rapidamente os locais de conteúdo em espera (em vez de ter que selecionar cada local para pesquisar) ao criar e executar pesquisas na próxima etapa. Depois de concluir a investigação, você pode liberar qualquer ressução criada.

2. **[Pesquise o conteúdo](search-for-content-in-core-ediscovery.md)**. Depois de criar regiões de Descoberta eDiscovery, use a ferramenta de pesquisa in-loco para pesquisar os locais de conteúdo em espera. Você também pode pesquisar em outros locais de conteúdo dados que podem ser relevantes para o caso. Você pode criar e executar diferentes pesquisas associadas ao caso. Você usa palavras-chave, propriedades [](keyword-queries-and-search-conditions.md) e condições para criar consultas de pesquisa que retornam resultados de pesquisa com os dados que provavelmente são relevantes para o caso. Você também pode:

   - Exibir estatísticas de pesquisa que podem ajudá-lo a refinar uma consulta de pesquisa para restringir os resultados.

   - Visualize os resultados da pesquisa para verificar rapidamente se os dados relevantes estão sendo encontrados.

   - Revise uma consulta e reprise a pesquisa.

3. **[Exportar e baixar resultados da pesquisa](export-content-in-core-ediscovery.md)**. Depois de pesquisar e encontrar dados relevantes para sua investigação, você pode exportá-los para fora do Office 365 para análise por pessoas fora da equipe de investigação. Exportar dados é um processo de duas etapas. A primeira etapa é exportar os resultados de uma pesquisa no caso de sair do Office 365. Isso é feito copiando os resultados de uma pesquisa para um local de Armazenamento do Azure fornecido pela Microsoft. A próxima etapa é usar a ferramenta Exportar Descoberta Digital para baixar o conteúdo em um computador local. Além dos arquivos de dados exportados, o contém do pacote de exportação também contém um relatório de exportação, um relatório de resumo e um relatório de erro.