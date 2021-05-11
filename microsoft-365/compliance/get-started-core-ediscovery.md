---
title: Começar a trabalhar com os principais casos de Descoberta Microsoft 365
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
description: Descreve como começar a usar o Core eDiscovery no Microsoft 365. Depois de atribuir permissões de Descoberta E e criar um caso, você pode adicionar membros, criar regiões de Descoberta e, em seguida, pesquisar e exportar conteúdo relevante para sua investigação.
ms.openlocfilehash: 00506c2f072fff6aa30c7d96bffdc18eb5eda20b
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311011"
---
# <a name="get-started-with-core-ediscovery-in-microsoft-365"></a>Começar a trabalhar com a Descoberta eDiscoveria Básica no Microsoft 365

O Core eDiscovery no Microsoft 365 fornece uma ferramenta básica de Descoberta eDiscovery que as organizações podem usar para pesquisar e exportar conteúdo em Microsoft 365 e Office 365. Você também pode usar o Core eDiscovery para colocar uma responsabilidade de Descoberta Eletrônico em locais de conteúdo, como caixas de correio Exchange, sites SharePoint, contas OneDrive e Microsoft Teams. Nada é necessário para implantar a Descoberta Principal, mas há algumas tarefas de pré-requisitos que um administrador de IT e o gerente de Descobertas Online precisam concluir para que sua organização possa começar a usar a Descoberta Básica para pesquisar, exportar e preservar conteúdo.

Este artigo discute as etapas necessárias para configurar a Descoberta Principal da Descoberta e. Isso inclui garantir o licenciamento adequado necessário para acessar a Descoberta Principal e colocar uma responsabilidade de Descoberta eDiscovery em locais de conteúdo, bem como atribuir permissões à equipe de IT, legal e de investigação para que eles possam acessar e gerenciar casos. Este artigo também fornece uma visão geral de alto nível do uso de casos para pesquisar e exportar conteúdo.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Etapa 1: Verificar e atribuir licenças apropriadas

O licenciamento para a Descoberta Interna requer a assinatura da organização apropriada e o licenciamento por usuário.

- **Assinatura da organização:** Para acessar o Core eDiscovery no centro de conformidade do Microsoft 365 ou no Centro de Conformidade do Office 365 Security & e usar os recursos de espera e exportação, sua organização deve ter uma assinatura Microsoft 365 E3 ou Office 365 E3 ou superior.

- **Licenciamento por usuário:** Para colocar uma responsabilidade de Descoberta Eletrônico em caixas de correio e sites, um usuário deve receber uma das seguintes licenças, dependendo da assinatura da sua organização:

  - Uma Microsoft 365 E3 ou Office 365 E3 ou superior

   OU

  - Office 365 Licença E1 com uma Exchange Online plano 2 ou Arquivamento do Exchange Online de complemento

  E

  - Office 365 Licença E1 com uma licença SharePoint Plano 2 ou OneDrive for Business plano 2 do Plano 2
  
  Para obter informações sobre como atribuir licenças, consulte [Assign licenses to users](../admin/manage/assign-licenses-to-users.md).

Para obter informações sobre licenciamento:

- Baixe e consulte a solução "Descobrir & Responder" na comparação de licenciamento [Microsoft 365 conformidade.](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)

- Consulte a descrição do [serviço & Centro de Conformidade.](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)

## <a name="step-2-assign-ediscovery-permissions"></a>Etapa 2: Atribuir permissões de Descoberta e

Para acessar a Descoberta Interna ou ser adicionado como membro de um caso core de Descoberta eDiscovery, um usuário deve ter as permissões apropriadas. Especificamente, um usuário deve ser adicionado como membro do grupo de funções do Gerenciador de Descobertas Office 365 Segurança & Compliance Center. Os membros desse grupo de função podem criar e gerenciar os principais casos de Descoberta eDiscovery. Eles podem adicionar e remover membros, colocar uma responsabilidade de Descoberta EDiscovery em usuários, criar e editar pesquisas e exportar conteúdo de um caso de Descoberta Interna.

Conclua as etapas a seguir para adicionar usuários ao grupo de funções do Gerenciador de Descobertas E:

1. Acesse e entre usando as credenciais de uma conta de administrador em sua Microsoft 365 [https://protection.office.com/permissions](https://protection.office.com/permissions) ou Office 365 organização.

2. Na página **Permissões,** selecione o grupo de função **Gerenciador de** Descobertas.

3. Na página de sobrevoo do Gerenciador de Descobertas e, em Seguida, clique em **Editar** ao lado da **seção Gerenciador de** Descobertas E.

4. Na página **Escolher Gerente de Descoberta Virtual** no assistente editar grupo de funções, clique em Escolher Gerenciador de **Descoberta**.

5. Clique **em Adicionar** e selecione a caixa de seleção para todos os usuários que você deseja adicionar ao grupo de funções.

6. Clique **em Adicionar** para adicionar os usuários selecionados e clique em **Feito**.

7. Clique **em Salvar** para adicionar os usuários ao grupo de funções e clique em **Fechar** para concluir a etapa.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Mais informações sobre o grupo de funções do Gerenciador de Descobertas E

Há dois subgrupos no grupo de funções do Gerenciador de Descobertas. A diferença entre esses subgrupos está no escopo.

- **EDiscovery Manager**: pode exibir e gerenciar os principais casos de Descoberta eDiscovery dos quais eles criam ou são membros. Se outro Gerenciador de Descobertas De eDiscovery criar um caso, mas não adicionar um segundo Gerenciador de Descobertas Deeconsutórias como membro desse caso, o segundo Gerenciador de Descobertas De eDiscovery não poderá exibir ou abrir o caso na página Descoberta eDiscoveria Principal no centro de conformidade. Em geral, a maioria das pessoas em sua organização pode ser adicionada ao subgrupo do Gerenciador de Descobertas.

- **Administrador de Descoberta e**: pode executar todas as tarefas de gerenciamento de caso que um Gerenciador de Descobertas E pode fazer. Além disso, um Administrador de Descoberta Eletrônica pode:

  - Exibir todos os casos listados na página Descoberta Principal.
  
  - Gerenciar qualquer caso na organização após adicionarem a si mesmos como membros do caso.

  - Acessar e exportar dados de caso de qualquer caso na organização.

  Devido ao amplo escopo de acesso, uma organização deve ter apenas alguns administradores que são membros do subgrupo de Administradores da Descoberta Eletrônica.

Para obter mais informações sobre permissões de Descoberta E e uma descrição de cada função atribuída ao grupo de funções do Gerenciador de Descobertas E, consulte [Assign eDiscovery permissions](assign-ediscovery-permissions.md).

## <a name="step-3-create-a-core-ediscovery-case"></a>Etapa 3: Criar um caso principal de Descoberta eDiscovery

A próxima etapa é criar uma ocorrência e começar a usar a Descoberta Principal. Conclua as etapas a seguir para criar uma ocorrência e adicionar membros. O usuário que cria a ocorrência é adicionado automaticamente como membro.

1. Acesse e entre usando as credenciais de uma conta de usuário que recebeu as permissões de [https://compliance.microsoft.com](https://compliance.microsoft.com) Descoberta eDiscovery apropriadas. Os membros do grupo de função Gerenciamento da Organização também podem criar principais casos de Descoberta eDiscovery.

2. No painel de navegação esquerdo do centro de conformidade Microsoft 365, clique em **Mostrar** tudo e clique em **Descoberta > Core**.

3. Na página **Descoberta Principal da Descoberta e,** clique em Criar um **caso**.

4. Na página **Novo caso,** dê ao caso um nome (obrigatório) e digite uma descrição opcional. O nome do caso deve ser exclusivo em sua organização.

5. Clique **em Salvar** para criar o caso.

   O novo caso é criado e exibido na página Descoberta Principal. Talvez seja preciso clicar em **Atualizar** para exibir o novo caso.

## <a name="step-4-optional-add-members-to-a-core-ediscovery-case"></a>Etapa 4 (opcional): Adicionar membros a um caso de Descoberta Principal de Descoberta e

Se você criar um caso na Etapa 3 e for a única pessoa que usará o caso, não será preciso executar esta etapa. Você pode começar a usar o caso para criar regiões de Descoberta e Descoberta, pesquisar conteúdo e exportar resultados de pesquisa. Execute esta etapa se você quiser dar a outros usuários (ou grupos de funções) acesso ao caso.

1. Na página **Descoberta Principal da** Descoberta Microsoft 365 de conformidade, clique no nome do caso ao que você deseja adicionar membros.

2. Na home page do caso, selecione a guia **Configurações** e selecione **Acessar & permissões**.

3. Na página Subsu & de permissões do **Access,** em **Membros**, clique em **Adicionar** para adicionar membros ao caso.

    Você também pode optar por adicionar grupos de função como membros de uma ocorrência. Em **Grupos de função,** clique em **Adicionar**. Você só pode atribuir os grupos de função dos que você é membro a um caso. Isso ocorre porque os grupos de função controlam quem pode atribuir membros a um caso de Descoberta E.

4. Na lista de pessoas ou grupos de função que podem ser adicionados como membros do caso, clique à esquerda do nome das pessoas (ou grupos de função) que você deseja adicionar. Se você tiver uma lista grande de pessoas ou grupos  de função que podem ser adicionados como membros, use a caixa Pesquisar para pesquisar uma pessoa específica ou grupo de função na lista.
  
5. Depois de selecionar as pessoas ou grupos de função a adicionar como membros do caso, clique em **Salvar** para salvar os novos membros ou grupos de função.

## <a name="explore-the-core-ediscovery-workflow"></a>Explorar o fluxo de trabalho principal de Descoberta Eletrônico

Para começar a usar a Descoberta Eletrônico principal, aqui está um fluxo de trabalho simples de criação de regiões de Descoberta Eletrônico para pessoas de interesse, a pesquisa de conteúdo relevante para sua investigação e, em seguida, a exportação desses dados para revisão posterior. Em cada uma dessas etapas, também destacaremos algumas funcionalidades de Descoberta eDiscoveria Básica estendidas que você pode explorar.

![Fluxo de trabalho principal de Descoberta Eletrônico](../media/CoreEdiscoveryWorkflow.png)

1. **[Criar uma responsabilidade de Descoberta E.](create-ediscovery-holds.md)** A primeira etapa após a criação de um caso é colocar uma responsabilidade (também chamada de ressarção de *Descoberta* e) nos locais de conteúdo das pessoas de interesse em sua investigação. Os locais de conteúdo incluem Exchange caixas de correio, sites SharePoint, contas OneDrive e caixas de correio e sites associados a grupos Microsoft Teams e Office 365. Embora esta etapa seja opcional, a criação de uma isenção de descoberta de eDiscovery preserva o conteúdo que pode ser relevante para o caso durante a investigação. Ao criar uma ressarção de Descoberta e, você pode preservar todo o conteúdo em locais de conteúdo específicos ou criar uma responsabilidade baseada em consulta para preservar apenas o conteúdo que corresponde a uma consulta de espera. Além de preservar o conteúdo, outro bom motivo para criar regiões de Descoberta eDiscovery é pesquisar rapidamente os locais de conteúdo em espera (em vez de ter que selecionar cada local para pesquisar) ao criar e executar pesquisas na próxima etapa. Depois de concluir a investigação, você pode liberar qualquer ressução criada.

2. **[Pesquise o conteúdo](search-for-content-in-core-ediscovery.md)**. Depois de criar regiões de Descoberta eDiscovery, use a ferramenta de pesquisa in-loco para pesquisar os locais de conteúdo em espera. Você também pode pesquisar em outros locais de conteúdo dados que podem ser relevantes para o caso. Você pode criar e executar diferentes pesquisas associadas ao caso. Você usa palavras-chave, propriedades [](keyword-queries-and-search-conditions.md) e condições para criar consultas de pesquisa que retornam resultados de pesquisa com os dados que provavelmente são relevantes para o caso. Você também pode:

   - Exibir estatísticas de pesquisa que podem ajudá-lo a refinar uma consulta de pesquisa para restringir os resultados.

   - Visualize os resultados da pesquisa para verificar rapidamente se os dados relevantes estão sendo encontrados.

   - Revise uma consulta e reprise a pesquisa.

3. **[Exportar e baixar resultados da pesquisa](export-content-in-core-ediscovery.md)**. Depois de pesquisar e encontrar dados relevantes para sua investigação, você pode exportá-los fora do Office 365 para análise por pessoas fora da equipe de investigação. Exportar dados é um processo de duas etapas. A primeira etapa é exportar os resultados de uma pesquisa no caso de Office 365. Isso é feito copiando os resultados de uma pesquisa para um local de Armazenamento do Azure fornecido pela Microsoft. A próxima etapa é usar a ferramenta Exportar Descoberta Digital para baixar o conteúdo em um computador local. Além dos arquivos de dados exportados, o contém do pacote de exportação também contém um relatório de exportação, um relatório de resumo e um relatório de erro.
