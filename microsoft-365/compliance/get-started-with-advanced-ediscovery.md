---
title: Configurar Advanced eDiscovery no Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: Este artigo descreve como configurar o Advanced eDiscovery para que você possa começar a criar e gerenciar casos. Ele também descreve as assinaturas e licenciamento necessários da Microsoft. Depois de concluir algumas etapas rápidas, a Advanced eDiscovery ferramenta estará pronta para uso.
ms.openlocfilehash: be5e5aea03950d28889590004bd796455a71c5be
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341443"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a>Configurar Microsoft 365 Advanced eDiscovery

Advanced eDiscovery no Microsoft 365 fornece um fluxo de trabalho de ponta a ponta para preservar, coletar, analisar, analisar e exportar dados que respondem às investigações internas e externas da sua organização. Nada é necessário para implantar o Advanced eDiscovery, mas há algumas tarefas de pré-requisitos que um administrador de IT e o gerente de Descobertas Online precisam concluir antes que sua organização possa começar a criar e usar Advanced eDiscovery casos para gerenciar suas investigações.

Este artigo discute as etapas a seguir necessárias para configurar Advanced eDiscovery.

![Etapas para configurar Advanced eDiscovery](../media/set-up-advanced-ediscovery.png)

Isso inclui garantir o licenciamento adequado necessário para acessar Advanced eDiscovery e adicionar custodiantes a casos e atribuir permissões à sua equipe legal e de investigação para que eles possam acessar e gerenciar casos.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Etapa 1: Verificar e atribuir licenças apropriadas

O licenciamento para Advanced eDiscovery requer a assinatura da organização apropriada e o licenciamento por usuário. Para ver uma lista de requisitos de licenciamento para Advanced eDiscovery, consulte [Assinaturas e licenciamento.](overview-ediscovery-20.md#subscriptions-and-licensing)

## <a name="step-2-assign-ediscovery-permissions"></a>Etapa 2: Atribuir permissões de Descoberta e

Para acessar Advanced eDiscovery ou adicionado como membro de um caso Advanced eDiscovery, um usuário deve ter as permissões apropriadas. Especificamente, um usuário deve ser adicionado como membro do grupo de funções do Gerenciador de Descobertas e no Centro de Conformidade & Segurança. Os membros desse grupo de funções podem criar e gerenciar Advanced eDiscovery casos. Eles podem adicionar e remover membros, colocar custodiantes e locais de conteúdo em espera, gerenciar notificações de avaliação legal, criar e editar pesquisas associadas em um caso, adicionar resultados de pesquisa a um conjunto de revisão, analisar dados em um conjunto de revisão e exportar e baixar de um caso de Advanced eDiscovery.

Conclua as etapas a seguir para adicionar usuários ao grupo de funções do Gerenciador de Descobertas E:

1. Acesse e entre usando as credenciais de uma conta <https://compliance.microsoft.com/permissions> de administrador em sua Microsoft 365 organização.

2. Na página **Permissões,** selecione o grupo de função **Gerenciador de** Descobertas.

3. Na página de sobrevoo do Gerenciador de Descobertas e, em Seguida, clique em **Editar** ao lado da **seção Gerenciador de** Descobertas E.

4. Na página **Escolher Gerente de** Descoberta Virtual no assistente editar grupo de funções, clique em Escolher Gerenciador de **Descobertas E.**

5. Clique **em Adicionar** e selecione a caixa de seleção para todos os usuários que você deseja adicionar ao grupo de funções.

6. Clique **em Adicionar** para adicionar os usuários selecionados e clique em **Feito**.

7. Clique **em Salvar** para adicionar os usuários ao grupo de funções e clique em **Fechar** para concluir a etapa.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Mais informações sobre o grupo de funções do Gerenciador de Descobertas E

Há dois subgrupos no grupo de funções do Gerenciador de Descobertas. A diferença entre esses subgrupos está no escopo.

- **EDiscovery Manager**: pode exibir e gerenciar os Advanced eDiscovery casos dos quais eles criam ou são membros. Se outro Gerenciador de Descobertas De eDiscovery criar uma ocorrência, mas não adicionar um segundo Gerenciador de Descobertas Deeconsutórias como membro desse caso, o segundo Gerente de Descoberta Desdiscovery não poderá exibir ou abrir o caso na página Advanced eDiscovery no centro de conformidade. Em geral, a maioria das pessoas em sua organização pode ser adicionada ao subgrupo do Gerenciador de Descobertas.

- **Administrador de Descoberta e**: pode executar todas as tarefas de gerenciamento de caso que um Gerenciador de Descobertas E pode fazer. Além disso, um Administrador de Descoberta Eletrônica pode:

  - Exibir todos os casos listados na página Descoberta Eletrônica Avançada.
  
  - Gerenciar qualquer caso na organização após adicionarem a si mesmos como membros do caso.

  - Acessar e exportar dados de caso de qualquer caso na organização.

  Devido ao amplo escopo de acesso, uma organização deve ter apenas alguns administradores que são membros do subgrupo de Administradores da Descoberta Eletrônica.

Para obter mais informações sobre permissões de Descoberta E e uma descrição de cada função atribuída ao grupo de funções do Gerenciador de Descobertas E, consulte [Assign eDiscovery permissions](assign-ediscovery-permissions.md).

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a>Etapa 3: Configurar configurações globais para Advanced eDiscovery

A última etapa a ser concluída antes que as pessoas em sua organização comecem a criar e usar casos é configurar as configurações globais que se aplicam a todos os casos em sua organização. Neste momento, a única configuração global é a detecção de privilégio *advogado-cliente* (mais configurações globais estarão disponíveis no futuro). Essa configuração permite que o modelo de privilégio advogado-cliente seja executado quando você analisa dados em um conjunto de revisão. O modelo usa o aprendizado de máquina para determinar a probabilidade de que um documento contenha conteúdo que seja legal por natureza. Ele também compara os participantes dos documentos com uma lista de advogados (que você envia ao configurar o modelo) para determinar se um documento tem pelo menos um participante que é um advogado.

Para obter mais informações sobre como configurar e usar o modelo de detecção de privilégio advogado-cliente, consulte Configurar a detecção de privilégio [advogado-cliente em Advanced eDiscovery](attorney-privilege-detection.md).

> [!NOTE]
> Esta é uma etapa opcional que você pode executar a qualquer momento. Não implementar o modelo de detecção de privilégio advogado-cliente não o impede de criar e usar Advanced eDiscovery casos.

## <a name="next-steps"></a>Próximas etapas

Depois de configurar Advanced eDiscovery, você estará pronto para [criar um caso](create-and-manage-advanced-ediscoveryv2-case.md).