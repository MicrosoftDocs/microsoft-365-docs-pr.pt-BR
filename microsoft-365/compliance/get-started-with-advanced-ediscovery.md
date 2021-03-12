---
title: Configurar a Descoberta Avançada de EDiscovery no Microsoft 365
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
- m365solution-ediscovery
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Este artigo descreve como configurar a Descoberta Avançada para que você possa começar a criar e gerenciar casos. Ele também descreve as assinaturas e licenciamento necessários da Microsoft. Depois de concluir algumas etapas rápidas, a ferramenta Descoberta Avançada estará pronta para uso.
ms.openlocfilehash: 29a220f36a55a04d1c1a24add03b2e013a5c60ba
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727406"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a>Configurar a Descoberta Avançada do Microsoft 365

A Descoberta Externa Avançada no Microsoft 365 fornece um fluxo de trabalho de ponta [a](overview-ediscovery-20.md#advanced-ediscovery-workflow) ponta para preservar, coletar, analisar, analisar e exportar dados que respondem às investigações internas e externas da sua organização. Nada é necessário para implantar a Descoberta Externa Avançada, mas há algumas tarefas de pré-requisitos que um administrador de IT e o gerente de Descobertas e Descobertas Online precisam concluir para que sua organização possa começar a criar e usar casos de Descoberta Externa Avançada para gerenciar suas investigações.

Este artigo discute as etapas necessárias para configurar a Descoberta Avançada da Descoberta. Isso inclui garantir o licenciamento adequado necessário para acessar a Descoberta Avançada e adicionar custodiantes a casos e atribuir permissões à sua equipe legal e de investigação para que eles possam acessar e gerenciar casos.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Etapa 1: Verificar e atribuir licenças apropriadas

O licenciamento para a Descoberta Avançada exige a assinatura da organização apropriada e o licenciamento por usuário.

- **Assinatura da organização:** Para acessar a Descoberta Digital Avançada no Centro de conformidade do Microsoft 365 ou no Centro de Conformidade & Segurança, sua organização deve ter um dos seguintes:

  - Assinatura do Microsoft 365 E5 ou do Office 365 E5
  
  - Assinatura do Microsoft 365 E3 com complemento de Conformidade E5

  - Assinatura do Microsoft 365 E3 com Complemento de Descoberta e Auditoria do E5

  Se você não tiver um plano existente do Microsoft 365 E5 e quiser experimentar [a](https://www.microsoft.com/microsoft-365/enterprise) Descoberta Avançada, adicione o [Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) à sua assinatura existente ou inscreva-se para uma avaliação do Microsoft 365 E5.

- **Licenciamento por usuário:** Para adicionar um usuário como um custodiante em um caso de Descoberta Antecipada, esse usuário deve ter uma das seguintes licenças, dependendo da assinatura da sua organização:

  - Microsoft 365: os usuários devem ter uma licença do Microsoft 365 E5, uma licença de complemento de Conformidade E5 ou uma licença de complemento de Descoberta e Auditoria E5.

  - Office 365: os usuários devem ter uma licença do Office 365 E5 atribuída.

   Para obter informações sobre como atribuir licenças, consulte [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

> [!NOTE]
> Os usuários só precisam de uma licença E5 (ou a licença de complemento apropriada) para serem adicionados como custodiantes a um caso de Descoberta Avançada. Os administradores de IT, gerentes de Descoberta Digital, advogados, paralegales ou investigadores que usam a Descoberta Digital Avançada para gerenciar casos e revisar dados de caso não precisam de uma licença E5 ou complemento.

## <a name="step-2-assign-ediscovery-permissions"></a>Etapa 2: Atribuir permissões de Descoberta e

Para acessar a Descoberta Interna Avançada ou adicionado como membro de um caso de Descoberta Avançada, um usuário deve ter as permissões apropriadas. Especificamente, um usuário deve ser adicionado como membro do grupo de funções do Gerenciador de Descobertas e no Centro de Conformidade & Segurança. Os membros desse grupo de função podem criar e gerenciar casos de Descoberta Avançada. Eles podem adicionar e remover membros, colocar custodiantes e locais de conteúdo em espera, gerenciar notificações de responsabilidade legal, criar e editar pesquisas associadas em um caso, adicionar resultados de pesquisa a um conjunto de revisão, analisar dados em um conjunto de revisão e exportar e baixar de um caso de Descoberta Avançada.

Conclua as etapas a seguir para adicionar usuários ao grupo de funções do Gerenciador de Descobertas E:

1. Acesse e entre usando as credenciais de uma conta [https://protection.office.com/permissions](https://protection.office.com/permissions) de administrador em sua organização do Microsoft 365.

2. Na página **Permissões,** selecione o grupo de função **Gerenciador de** Descobertas.

3. Na página de sobrevoo do Gerenciador de Descobertas e, em Seguida, clique em **Editar** ao lado da **seção Gerenciador de** Descobertas E.

4. Na página **Escolher Gerente de** Descoberta Virtual no assistente editar grupo de funções, clique em Escolher Gerenciador de **Descobertas E.**

5. Clique **em Adicionar** e selecione a caixa de seleção para todos os usuários que você deseja adicionar ao grupo de funções.

6. Clique **em Adicionar** para adicionar os usuários selecionados e clique em **Feito**.

7. Clique **em Salvar** para adicionar os usuários ao grupo de funções e clique em **Fechar** para concluir a etapa.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Mais informações sobre o grupo de funções do Gerenciador de Descobertas E

Há dois subgrupos no grupo de funções do Gerenciador de Descobertas. A diferença entre esses subgrupos está no escopo.

- **EDiscovery Manager:** Pode exibir e gerenciar os casos de Descoberta Avançada de Que eles criam ou são membros. Se outro Gerenciador de Descobertas De eDiscovery criar uma ocorrência, mas não adicionar um segundo Gerenciador de Descobertas Deeconsutórias como membro desse caso, o segundo Gerenciador de Descobertas Desdiscovery não poderá exibir ou abrir o caso na página Descoberta Avançada da Descoberta Técnica no centro de conformidade. Em geral, a maioria das pessoas em sua organização pode ser adicionada ao subgrupo do Gerenciador de Descobertas.

- Administrador de Descoberta **e:** Pode executar todas as tarefas de gerenciamento de casos que um Gerenciador de Descobertas Públicas pode fazer. Além disso, um Administrador de Descoberta Eletrônica pode:

  - Exibir todos os casos listados na página Descoberta Avançada.
  
  - Gerencie qualquer caso na organização depois que eles se adicionarem como um membro do caso.

  - Acessar e exportar dados de caso para qualquer caso na organização.

  Devido ao amplo escopo de acesso, uma organização deve ter apenas alguns administradores membros do subgrupo Administradores de Descoberta e.

Para obter mais informações sobre permissões de Descoberta E e uma descrição de cada função atribuída ao grupo de funções do Gerenciador de Descobertas E, consulte [Assign eDiscovery permissions](assign-ediscovery-permissions.md).

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a>Etapa 3: Configurar configurações globais para Descoberta Avançada da Descoberta

A última etapa a ser concluída antes que as pessoas em sua organização comecem a criar e usar casos é configurar as configurações globais que se aplicam a todos os casos em sua organização. Neste momento, a única configuração global é a detecção de privilégio *advogado-cliente* (mais configurações globais estarão disponíveis no futuro). Essa configuração permite que o modelo de privilégio advogado-cliente seja executado quando você analisa dados em um conjunto de revisão. O modelo usa o aprendizado de máquina para determinar a probabilidade de que um documento contenha conteúdo que seja legal por natureza. Ele também compara os participantes dos documentos com uma lista de advogados (que você envia ao configurar o modelo) para determinar se um documento tem pelo menos um participante que é um advogado.

Para obter mais informações sobre como configurar e usar o modelo de detecção de privilégio advogado-cliente, consulte Configurar a detecção de privilégio de [cliente-advogado em Descoberta Avançada.](attorney-privilege-detection.md)

> [!NOTE]
> Esta é uma etapa opcional que você pode executar a qualquer momento. Não implementar o modelo de detecção de privilégio advogado-cliente não impede a criação e o uso de casos avançados de Descoberta Automática.

## <a name="next-steps"></a>Próximas etapas

Depois de configurar a Descoberta Avançada, você estará pronto para [criar uma ocorrência.](create-and-manage-advanced-ediscoveryv2-case.md)
