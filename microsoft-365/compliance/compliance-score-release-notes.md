---
title: Notas de versão da Pontuação de conformidade da Microsoft
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Notas de versão e problemas conhecidos para a pontuação de conformidade da Microsoft (visualização), um recurso no centro de conformidade do M365 que ajuda a simplificar e automatizar avaliações de risco.
ms.openlocfilehash: dd7c99d2f0a86826be7803dc36e390250a4fc37b
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141546"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a>Notas de versão da Pontuação de conformidade da Microsoft (visualização)

A visualização pública da Pontuação de conformidade da Microsoft fornece acesso antecipado às futuras funcionalidades e atualizações. Verifique esta página com frequência para saber o que há de novo.

A pontuação de conformidade é um novo recurso do [centro de conformidade da Microsoft 365](microsoft-365-compliance-center.md) que calcula uma pontuação baseada em risco, medindo seu progresso em direção à conclusão de ações recomendadas que ajudam a reduzir os riscos de conformidade.

## <a name="new-templates-for-assessments"></a>Novos modelos para avaliações

Novos modelos pré-configurados para avaliações são lançados em produção para a pontuação de conformidade (visualização) à medida que eles se tornam disponíveis. Confira a [lista completa de modelos aqui](compliance-score.md#templates). Os modelos adicionados recentemente incluem:

- Lei de proteção de dados gerais do Brasil (LGPD)
- IRAP/ISM do governo australiano (versão prévia)
- ISO 27701:2019
- SOC 1
- SOC 2

## <a name="improvements-in-managing-assessments"></a>Melhorias no gerenciamento de avaliações

A versão mais recente do Gerenciador de conformidade em abril de 2020 inclui atualizações que simplificam o modo como você cria e personaliza avaliações e as mantém atualizadas. Consulte as [notas de versão do Gerenciador de conformidade](compliance-manager-release-notes.md) para obter detalhes.

## <a name="language-support"></a>Suporte a idiomas

A pontuação de conformidade já está disponível nos seguintes idiomas, além de inglês: Chinês (simplificado), chinês (tradicional), francês, alemão, italiano, japonês, coreano, Português (Brasil), russo e espanhol.

## <a name="common-actions-will-synch-status-across-groups"></a>As ações comuns irão sincronizar o status entre grupos

Se sua organização tiver vários grupos de avaliações, o comportamento das ações **técnicas** (ou seja, ações que afetam toda a organização) foi alterado. Quaisquer ações duplicadas entre grupos foram combinadas em uma única ação. Essa ação única contém todas as anotações e evidências carregadas das versões duplicadas. Com essa alteração, as ações técnicas agora se comportam como faziam quando pertenciam ao mesmo grupo. Todas as alterações feitas na ação em um grupo ou avaliação serão refletidas em todas as instâncias. O **status da implementação**, a **data de implementação**, o status do **teste**e a **Data** de teste irão refletir as atualizações mais recentes.

## <a name="compliance-score-relationship-to-compliance-manager"></a>Relação de Pontuação de conformidade com o Gerenciador de conformidade

Agora, muitas das funções manipuladas no gerente de conformidade podem ser feitas na pontuação de conformidade. No entanto, algumas funções continuam ao vivo no Gerenciador de conformidade. Mantenha esses pontos em mente ao trabalhar com a pontuação de conformidade e o gerente de conformidade durante a visualização pública:

- **Gerenciando avaliações**: os usuários podem exibir avaliações e seus detalhes de status na pontuação de conformidade. No entanto, os usuários podem apenas realizar tarefas de gerenciamento de avaliação no gerente de conformidade ([instruções de exibição](working-with-compliance-manager.md#assessments)). Exemplos dessas tarefas incluem:
    - Criar e copiar avaliações
    - Avaliações de exportação
    - Avaliações de arquivamento
    - Exibir avaliações arquivadas
 - **Criar modelos para avaliações**: 
   - Os usuários devem acessar o Gerenciador de conformidade para criar novos modelos e modificar os [modelos](working-with-compliance-manager.md#templates)existentes. 
   - Ao criar um modelo, você deve incluir as dimensões de **produto** e **certificação** para garantir que seu modelo seja exibido na pontuação de conformidade.
 - **Configuração de permissões**: Pontuação de conformidade os usuários que já tinham permissões no gerente de conformidade precisam de suas permissões definidas no centro de conformidade da Microsoft 365 ([saiba mais](compliance-score-setup.md#set-user-permissions-and-assign-roles)).
- **Transferência de dados**: as organizações com dados no gerente de conformidade verão os dados na pontuação de conformidade, e o mesmo é verdade o contrário.
- **Entrar no Gerenciador de conformidade da Pontuação de conformidade**: se um usuário estiver conectado à pontuação de conformidade e selecionar um link para acessar o Gerenciador de conformidade, o usuário não terá que entrar novamente. Após clicar no link, uma nova guia é aberta no navegador com uma caixa de diálogo. Na seção superior com o cabeçalho, "já é um cliente dos serviços de nuvem da Microsoft? Entre em sua conta, "Selecione o botão **entrar** para entrar automaticamente no Gerenciador de conformidade.

## <a name="known-issues-in-compliance-score-preview"></a>Problemas conhecidos na pontuação de conformidade (visualização)

As seções a seguir abordam problemas conhecidos a serem resolvidos em futuras versões da Pontuação de conformidade.

### <a name="long-load-times-for-non-admin-users"></a>Tempos de carregamento longos para usuários que não são administradores
Nota de conformidade os usuários que possuem funções diferentes de uma função de administrador podem enfrentar tempos de carregamento longos ao tentar uma entrada. A atualização do navegador resolverá esse problema. (Saiba mais sobre as [funções de Pontuação de conformidade](compliance-score-setup.md#set-user-permissions-and-assign-roles).)

### <a name="supported-browsers"></a>Navegadores com suporte

- As versões mais recentes do Microsoft Edge, do Chrome e do Safari são suportadas.
- Os dados atualizados às vezes não aparecem até que seu navegador seja atualizado.
- Não há suporte para o Internet Explorer.
