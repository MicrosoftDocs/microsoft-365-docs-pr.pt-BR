---
title: Configurar a Descoberta Avançada no Microsoft 365
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
search.appverid:
- MOE150
- MET150
description: Este artigo descreve como configurar a Descoberta Avançada para que você possa começar a criar e gerenciar casos. Ele também descreve as assinaturas e o licenciamento necessários da Microsoft. Depois de concluir algumas etapas rápidas, a ferramenta Descoberta Avançada estará pronta para uso.
ms.openlocfilehash: aef5cd2e465306b4401cda66d4ba30c97b9fc8cd
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841172"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a>Configurar a Descoberta Avançada do Microsoft 365

A Descoberta Avançada no Microsoft 365 fornece um fluxo de trabalho de ponta [a](overview-ediscovery-20.md#advanced-ediscovery-workflow) ponta para preservar, coletar, analisar, analisar e exportar dados que respondem às investigações internas e externas da sua organização. Nada é necessário para implantar a Descoberta Avançada, mas há algumas tarefas de pré-requisito que um administrador de IT e gerente de Descobertas Ele precisa concluir antes que sua organização possa começar a criar e usar ocorrências de Descoberta e Avançada para gerenciar suas investigações.

Este artigo discute as etapas necessárias para configurar a Descoberta Avançada. Isso inclui garantir o licenciamento adequado necessário para acessar a Descoberta Avançada e adicionar responsáveis aos casos e atribuir permissões à sua equipe jurídica e de investigação para que eles possam acessar e gerenciar casos.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Etapa 1: Verificar e atribuir licenças apropriadas

O licenciamento para a Descoberta Avançada requer a assinatura da organização apropriada e o licenciamento por usuário.

- **Assinatura da organização:** Para acessar a Descoberta Avançada no centro de conformidade do Microsoft 365 ou no Centro de Conformidade e Segurança &, sua organização deve ter um dos seguintes:

  - Assinatura do Microsoft 365 E5 ou do Office 365 E5
  
  - Assinatura do Microsoft 365 E3 com complemento de Conformidade E5

  - Assinatura do Microsoft 365 E3 com Descoberta e Auditoria do E5

  Se você não tiver um plano existente do Microsoft 365 E5 e quiser experimentar [a](https://www.microsoft.com/microsoft-365/enterprise) Descoberta Avançada, adicione o [Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) à sua assinatura existente ou inscreva-se para uma avaliação do Microsoft 365 E5.

- **Licenciamento por usuário:** Para adicionar um usuário como um custodiante em um caso de Descoberta Antecipada, esse usuário deve ter uma das seguintes licenças, dependendo da sua assinatura de organização:

  - Microsoft 365: os usuários devem ter uma licença do Microsoft 365 E5, uma licença de complemento de Conformidade do E5 ou uma licença de complemento de Descoberta e Auditoria E5.

  - Office 365: os usuários devem ter uma licença do Office 365 E5 atribuída.

   Para obter informações sobre como atribuir licenças, consulte [Atribuir licenças aos usuários.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

> [!NOTE]
> Os usuários só precisam de uma licença E5 (ou a licença de complemento apropriada) para serem adicionados como custodiantes a um caso de Descoberta Avançada. Administradores de IT, gerentes de eDiscovery, advogados, assistentes jurídicos ou investigadores que usam a Descoberta Avançada para gerenciar casos e analisar dados de caso não precisam de uma licença E5 ou complemento.

## <a name="step-2-assign-ediscovery-permissions"></a>Etapa 2: Atribuir permissões de Descoberta eDiscovery

Para acessar a Descoberta Avançada ou adicionado como membro de um caso de Descoberta Avançada, um usuário deve ter as permissões apropriadas. Especificamente, um usuário deve ser adicionado como membro do grupo de função Gerente de Descobertas & Segurança. Os membros desse grupo de função podem criar e gerenciar ocorrências de Descobertas Avançadas. Eles podem adicionar e remover membros, colocar responsáveis e locais de conteúdo em espera, gerenciar notificações de responsabilidade legal, criar e editar pesquisas associadas em um caso, adicionar resultados de pesquisa a um conjunto de revisão, analisar dados em um conjunto de revisão e exportar e baixar de um caso de Descoberta Avançada.

Conclua as seguintes etapas para adicionar usuários ao grupo de funções do Gerente de Descobertas e Descobertas:

1. Acesse e [https://protection.office.com/permissions](https://protection.office.com/permissions) entre usando as credenciais de uma conta de administrador em sua organização do Microsoft 365.

2. Na página **Permissões,** selecione o grupo **de funções do Gerente** de Descobertas.

3. Na página do flyout do Gerenciador de Descobertas Do eDiscovery, clique em **Editar** ao lado da **seção Gerenciador de Descobertas.**

4. Na página **Escolher Gerenciador de Descobertas Do** Assistente de Grupo de Função de Edição, clique em Escolher Gerente de Descoberta **e.**

5. Clique **em Adicionar** e marque a caixa de seleção de todos os usuários que você deseja adicionar ao grupo de funções.

6. Clique **em Adicionar** para adicionar os usuários selecionados e clique em **Feito.**

7. Clique **em** Salvar para adicionar os usuários ao grupo de funções e clique **em Fechar** para concluir a etapa.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Mais informações sobre o grupo de funções do Gerente de Descobertas

Há dois subgrupos no grupo de funções do Gerente de Descobertas. A diferença entre esses subgrupos está no escopo.

- **Gerente de Descobertas EDiscovery:** Pode exibir e gerenciar os casos de Descoberta eDiscovery Avançada que eles criam ou dos quais são membros. Se outro Gerente de Descoberta eDiscovery criar uma ocorrência, mas não adicionar um segundo Gerente de Descobertas Como membro desse caso, o segundo Gerente de Descobertas eDiscovery não poderá exibir ou abrir a ocorrência na página DescobertaScoberta Avançada no centro de conformidade. Em geral, a maioria das pessoas em sua organização pode ser adicionada ao subgrupo Gerente de Descobertas.

- **Administrador de Descobertas EDiscovery:** Pode executar todas as tarefas de gerenciamento de ocorrências que um Gerente de Descobertas Descoberta Pode fazer. Além disso, um Administrador de Descoberta Eletrônica pode:

  - Exibir todos os casos listados na página Descobertas Avançadas.
  
  - Gerencie qualquer caso na organização depois de adicionar a si mesmo como um membro da ocorrência.

  - Acessar e exportar dados de ocorrência para qualquer caso na organização.

  Devido ao amplo escopo de acesso, uma organização deve ter apenas alguns administradores que sejam membros do subgrupo Administradores de Descobertas e Descobertas.

Para obter mais informações sobre permissões de Descobertas e uma descrição de cada função atribuída ao grupo de função gerente de Descobertas eDiscovery, consulte Atribuir permissões de [Descoberta eDiscovery](assign-ediscovery-permissions.md).

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a>Etapa 3: Definir as configurações globais para a Descoberta Avançada

A última etapa a ser concluída antes que as pessoas em sua organização comecem a criar e usar casos é definir configurações globais que se apliquem a todos os casos em sua organização. No momento, a única configuração global é a detecção de privilégio *advogado-cliente* (mais configurações globais estarão disponíveis no futuro). Essa configuração permite que o modelo de privilégio advogado-cliente seja executado quando você analisar dados em um conjunto de revisão. O modelo usa o aprendizado de máquina para determinar a probabilidade de que um documento contenha conteúdo legal por natureza. Ele também compara os participantes dos documentos com uma lista de advogados (que você envia ao configurar o modelo) para determinar se um documento tem pelo menos um participante que seja advogado.

Para obter mais informações sobre como configurar e usar o modelo de detecção de privilégio advogado-cliente, consulte Configurar detecção de privilégio [advogado-cliente](attorney-privilege-detection.md)na Descoberta Automática Avançada.

> [!NOTE]
> Esta é uma etapa opcional que você pode executar a qualquer momento. Não implementar o modelo de detecção de privilégio advogado-cliente não impede que você criar e usar casos de Descoberta Automática Avançada.

## <a name="next-steps"></a>Próximas etapas

Depois de configurar a Descoberta Avançada, você estará pronto para [criar uma ocorrência.](create-and-manage-advanced-ediscoveryv2-case.md)
