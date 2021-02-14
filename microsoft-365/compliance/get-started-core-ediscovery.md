---
title: Começar a trabalhar com os principais casos de Descoberta e no Microsoft 365
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
description: Este artigo descreve como começar a usar a Descoberta Principal no Microsoft 365. Depois de atribuir permissões de Descoberta e criar uma ocorrência, você pode adicionar membros, criar regiões de Descoberta e, em seguida, pesquisar e exportar dados relevantes à sua investigação.
ms.openlocfilehash: 94c85987be4cbc5da7a378abb7ea74294f6fe740
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357909"
---
# <a name="get-started-with-core-ediscovery"></a>Introdução à Descoberta Eletrônica Central

A Descoberta Principal no Microsoft 365 fornece uma ferramenta básica de Descoberta e Que as organizações podem usar para pesquisar e exportar conteúdo no Microsoft 365 e no Office 365. Você também pode usar a Descoberta Principal para colocar uma descoberta de eDiscovery em locais de conteúdo, como caixas de correio do Exchange, sites do SharePoint, contas do OneDrive e Microsoft Teams. Nada é necessário para implantar a Descoberta Principal, mas há algumas tarefas de pré-requisito que um administrador de IT e gerente de Descobertas Ele precisa concluir antes que sua organização possa começar a usar a Descoberta Principal para pesquisar, exportar e preservar conteúdo.

Este artigo discute as etapas necessárias para configurar a Descoberta Principal. Isso inclui garantir o licenciamento adequado necessário para acessar a Descoberta Principal e colocar uma descoberta de eDiscovery em locais de conteúdo, bem como atribuir permissões à sua equipe de IT, jurídico e de investigação para que eles possam acessar e gerenciar casos. Este artigo também fornece uma visão geral de alto nível do uso de casos para pesquisar e exportar conteúdo.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Etapa 1: Verificar e atribuir licenças apropriadas

O licenciamento para a Descoberta Principal requer a assinatura da organização apropriada e o licenciamento por usuário.

- **Assinatura da organização:** Para acessar a Descoberta Principal no centro de conformidade do Microsoft 365 ou no Centro de Conformidade e Segurança do Office 365 & e usar os recursos de espera e exportação, sua organização deve ter uma assinatura do Microsoft 365 E3 ou Office 365 E3 ou superior.

- **Licenciamento por usuário:** Para colocar uma espera de Descoberta Eletrônico em caixas de correio e sites, um usuário deve receber uma das seguintes licenças, dependendo da assinatura da sua organização:

  - Uma licença do Microsoft 365 E3 ou Office 365 E3 ou superior

   OU

  - Licença do Office 365 E1 com uma licença de complemento do Exchange Online Plano 2 ou arquivamento do Exchange Online

  E

  - Licença do Office 365 E1 com uma licença de complemento do Plano 2 do SharePoint Online ou do OneDrive for Business Plano 2
  
  Para obter informações sobre como atribuir licenças, consulte [Atribuir licenças aos usuários.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

Para obter informações sobre licenciamento:

- Baixe e veja a solução "Descubra & Responder" na Comparação de Licenciamento de Conformidade do [Microsoft 365.](https://docs.microsoft.com/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)

- Consulte a [descrição do serviço & Centro de Conformidade e Segurança.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)

## <a name="step-2-assign-ediscovery-permissions"></a>Etapa 2: Atribuir permissões de Descoberta eDiscovery

Para acessar a Descoberta Principal ou ser adicionado como membro de uma ocorrência de Descoberta e Principal, um usuário deve ter as permissões apropriadas atribuídas. Especificamente, um usuário deve ser adicionado como membro do grupo de funções Gerente de Descobertas Do Centro de Conformidade e Segurança do Office 36 & 5. Os membros desse grupo de função podem criar e gerenciar ocorrências de Descobertas Principais. Eles podem adicionar e remover membros, colocar um eDiscovery em espera em usuários, criar e editar pesquisas e exportar conteúdo de um caso de Descoberta eDiscovery Principal.

Conclua as seguintes etapas para adicionar usuários ao grupo de funções do Gerente de Descobertas e Descobertas:

1. Acesse e entre usando as credenciais de uma conta de administrador em sua organização do [https://protection.office.com/permissions](https://protection.office.com/permissions) Microsoft 365 ou Office 365.

2. Na página **Permissões,** selecione o grupo **de funções do Gerente** de Descobertas.

3. Na página do flyout do Gerenciador de Descobertas Do eDiscovery, clique em **Editar** ao lado da **seção Gerenciador de Descobertas.**

4. Na página **Escolher Gerenciador de Descobertas Do Assistente** para Editar Grupo de Funções, clique em Escolher Gerenciador de **Descoberta.**

5. Clique **em Adicionar** e marque a caixa de seleção de todos os usuários que você deseja adicionar ao grupo de funções.

6. Clique **em Adicionar** para adicionar os usuários selecionados e clique em **Feito.**

7. Clique **em** Salvar para adicionar os usuários ao grupo de funções e clique **em Fechar** para concluir a etapa.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Mais informações sobre o grupo de funções do Gerente de Descobertas

Há dois subgrupos no grupo de funções do Gerente de Descobertas. A diferença entre esses subgrupos está no escopo.

- **Gerente de Descobertas EDiscovery:** Pode exibir e gerenciar os principais casos de Descoberta eDiscovery que eles criam ou dos quais são membros. Se outro Gerente de Descoberta eDiscovery criar uma ocorrência, mas não adicionar um segundo Gerente de Descobertas Como membro desse caso, o segundo Gerente de Descobertas eDiscovery não poderá exibir ou abrir a ocorrência na página Descoberta eDiscovery Principal no centro de conformidade. Em geral, a maioria das pessoas em sua organização pode ser adicionada ao subgrupo Gerente de Descobertas.

- **Administrador de Descobertas EDiscovery:** Pode executar todas as tarefas de gerenciamento de ocorrências que um Gerente de Descobertas Descoberta Pode fazer. Além disso, um Administrador de Descoberta Eletrônica pode:

  - Exibir todos os casos listados na página Descoberta e Principal.
  
  - Gerencie qualquer caso na organização depois de adicionar a si mesmo como um membro da ocorrência.

  - Acessar e exportar dados de ocorrência para qualquer caso na organização.

  Devido ao amplo escopo de acesso, uma organização deve ter apenas alguns administradores que sejam membros do subgrupo Administradores de Descobertas e Descobertas.

Para obter mais informações sobre permissões de Descobertas e uma descrição de cada função atribuída ao grupo de função gerente de Descobertas eDiscovery, consulte Atribuir permissões de [Descoberta eDiscovery](assign-ediscovery-permissions.md).

## <a name="step-3-create-a-core-ediscovery-case"></a>Etapa 3: Criar um caso principal de Descoberta eDiscovery

A próxima etapa é criar uma ocorrência e começar a usar a Descoberta Principal. Conclua as etapas a seguir para criar uma ocorrência e adicionar membros. O usuário que cria a ocorrência é adicionado automaticamente como membro.

1. Vá para e entre usando as credenciais de uma conta de usuário que recebeu [https://compliance.microsoft.com](https://compliance.microsoft.com) as permissões apropriadas de Descoberta eDiscovery. Os membros do grupo de função Gerenciamento da Organização também podem criar casos principais de Descoberta eDiscovery.

2. No painel de navegação esquerdo do centro de conformidade do Microsoft 365, clique em Mostrar tudo e clique em **eDiscovery > Core.**

3. Na página **Descoberta Principal do eDiscovery,** clique **em Criar uma ocorrência.**

4. Na página **Novo caso,** dê à ocorrência um nome (obrigatório) e digite um número de ocorrência e uma descrição opcionais. O nome da ocorrência deve ser exclusivo em sua organização.

5. Clique **em Salvar** para criar a ocorrência.

   A nova ocorrência é criada e exibida na página Descobertas Principais do eDiscovery. Talvez seja preciso clicar em **Atualizar** para exibir a nova ocorrência. 

## <a name="step-4-optional-add-members-to-a-core-ediscovery-case"></a>Etapa 4 (opcional): Adicionar membros a uma ocorrência principal de Descoberta eDiscovery

Se você criar um caso na Etapa 3 e for a única pessoa que usará a ocorrência, não será preciso executar essa etapa. Você pode começar a usar a ocorrência para criar regiões de Descoberta e, em busca de conteúdo, ou exportar resultados de pesquisa. Execute esta etapa se quiser dar a outros usuários (ou grupo de funções) acesso à ocorrência.

1. Na página **Descoberta Principal do** Centro de conformidade do Microsoft 365, clique no nome da ocorrência à que você deseja adicionar membros.

2. Na página **Gerenciar esse caso,** em **Gerenciar membros,** clique em **Adicionar** para adicionar membros à ocorrência. 

    Você também pode optar por adicionar um grupo de funções como membros de uma ocorrência. Em **Gerenciar grupos de função,** clique em **Adicionar**. Você só pode atribuir os grupos de função dos que você é membro de uma ocorrência. Isso ocorre porque os grupos de função controlam quem pode atribuir membros a uma ocorrência de Descoberta eDiscovery.

3. Na lista de pessoas ou grupos de função que podem ser adicionados como membros da ocorrência, clique na caixa de seleção ao lado dos nomes das pessoas (ou grupos de funções) que você deseja adicionar. Se você tiver uma lista grande de pessoas  que podem ser adicionadas como membros, use a caixa De pesquisa para procurar uma pessoa específica na lista.
  
4. Depois de selecionar as pessoas ou grupos de função para adicionar como membros da ocorrência, clique em **Adicionar**.

5. Clique **em Salvar** para salvar a nova lista de membros da ocorrência.

## <a name="explore-the-core-ediscovery-workflow"></a>Explorar o fluxo de trabalho principal de Descoberta Eletrônico

Para começar a usar a Descoberta Eletrônico principal, aqui está um fluxo de trabalho simples de criação de regiões de Descoberta Eletrônico para pessoas de interesse, pesquisa de conteúdo relevante para sua investigação e exportação desses dados para revisão posterior. Em cada uma dessas etapas, também destacaremos algumas funcionalidades de Descobertas Principais estendidas que você pode explorar.

![Fluxo de trabalho principal de Descoberta Eletrônico](../media/CoreEdiscoveryWorkflow.png)

1. **[Criar um eDiscovery hold](create-ediscovery-holds.md)**. A primeira etapa após a criação de um caso é colocar uma isenção (também chamada de isenção de Descoberta *eDiscovery)* nos locais de conteúdo das pessoas de interesse em sua investigação. Os locais de conteúdo incluem caixas de correio do Exchange, sites do SharePoint, contas do OneDrive, bem como caixas de correio e sites associados ao Microsoft Teams e grupos do Office 365. Embora essa etapa seja opcional, a criação de uma isenção de Descoberta e preserva o conteúdo que pode ser relevante para o caso durante a investigação. Ao criar uma responsabilidade de Descoberta eDiscovery, você pode preservar todo o conteúdo em locais de conteúdo específicos ou pode criar uma espera baseada em consulta para preservar apenas o conteúdo que corresponde a uma consulta de responsabilidade. Além de preservar o conteúdo, outro bom motivo para criar regiões de Descoberta eDiscovery é pesquisar rapidamente os locais de conteúdo em espera (em vez de ter que selecionar cada local para pesquisar) ao criar e executar pesquisas na próxima etapa. Depois de concluir a investigação, você pode liberar qualquer espera que criou.

2. **[Pesquise conteúdo.](search-for-content-in-core-ediscovery.md)** Depois de criar regiões de Descoberta eDiscovery, use a ferramenta de pesquisa integrado para pesquisar os locais de conteúdo em espera. Você também pode pesquisar outros locais de conteúdo para dados que possam ser relevantes para o caso. Você pode criar e executar diferentes pesquisas associadas à ocorrência. Você usa palavras-chave, propriedades [](keyword-queries-and-search-conditions.md) e condições para criar consultas de pesquisa que retornam resultados de pesquisa com os dados que provavelmente são relevantes para o caso. Você também pode:

   - Exibir estatísticas de pesquisa que podem ajudá-lo a refinar uma consulta de pesquisa para restringir os resultados.

   - Visualize os resultados da pesquisa para verificar rapidamente se os dados relevantes estão sendo encontrados.

   - Revise uma consulta e rerun a pesquisa.

3. **[Exportar e baixar resultados de pesquisa.](export-content-in-core-ediscovery.md)** Depois de procurar e encontrar dados relevantes à sua investigação, você poderá exportá-los do Office 365 para análise de pessoas de fora da equipe de investigação. Exportar dados é um processo de duas etapas. A primeira etapa é exportar os resultados de uma pesquisa no caso de sair do Office 365. Isso é feito copiando os resultados de uma pesquisa para um local de armazenamento do Azure fornecido pela Microsoft. A próxima etapa é usar a ferramenta Exportação de Descobertas EDiscovery para baixar o conteúdo em um computador local. Além dos arquivos de dados exportados, os contém do pacote de exportação também contém um relatório de exportação, um relatório resumido e um relatório de erros.
