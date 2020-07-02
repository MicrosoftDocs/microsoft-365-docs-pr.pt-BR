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
ms.openlocfilehash: 6678ec03d2cd87a97244acaa55a15483d78dd632
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45022188"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a>Notas de versão da Pontuação de conformidade da Microsoft (visualização)

**Neste artigo:** Esta **página mostra as novidades na** visualização pública da Pontuação de [conformidade da Microsoft](compliance-score.md), que oferece acesso antecipado à nova funcionalidade.

## <a name="assessment-creation-and-management-functionality"></a>Criação e funcionalidade de gerenciamento de avaliação

A versão de junho de 2020 adiciona funcionalidade para que os usuários criem, excluam e gerenciem suas avaliações diretamente na pontuação de conformidade. Anteriormente, todo o gerenciamento de avaliação estava no Gerenciador de conformidade. Quando você criar ou modificar uma avaliação na pontuação de conformidade, as atualizações serão enfeitas no Gerenciador de conformidade. Da mesma forma, qualquer trabalho de avaliação executado no gerente de conformidade será exibido na pontuação de conformidade. Saiba como [gerenciar avaliações na pontuação de conformidade](compliance-score-assessments.md). Observe que a criação e a modificação do modelo ainda são gerenciadas no Gerenciador de conformidade.

## <a name="new-templates-for-assessments"></a>Novos modelos para avaliações

Novos modelos prontos para usar para avaliações são lançados na pontuação de conformidade à medida que eles são disponibilizados. Confira a [lista completa de modelos aqui](compliance-score-templates.md). Recentemente Adicionado:

- Resolução de segurança de informações Dubai (DGISR)

## <a name="compliance-score-relationship-to-compliance-manager"></a>Relação de Pontuação de conformidade com o Gerenciador de conformidade

Agora, muitas das funções manipuladas no gerente de conformidade podem ser feitas na pontuação de conformidade. No entanto, algumas funções continuam ao vivo no Gerenciador de conformidade. Mantenha esses pontos em mente ao trabalhar com a pontuação de conformidade e o gerente de conformidade durante a visualização pública:

 - **Criar modelos para avaliações**: 
   - Os usuários devem acessar o Gerenciador de conformidade para [criar novos modelos e modificar os modelos existentes](working-with-compliance-manager.md#templates).
   - Novos modelos devem incluir dimensões para **produto** e **certificação**.
 - **Configuração de permissões**: Pontuação de conformidade os usuários que já tinham permissões no gerente de conformidade precisam de suas permissões definidas no centro de conformidade da Microsoft 365 ([saiba mais](compliance-score-setup.md#set-user-permissions-and-assign-roles)).
- **Transferência de dados**: as organizações com dados no gerente de conformidade verão os dados na pontuação de conformidade, e o mesmo é verdade o contrário.
- **Entrar no Gerenciador de conformidade da Pontuação de conformidade**: se um usuário estiver conectado à pontuação de conformidade e selecionar um link para acessar o Gerenciador de conformidade, o usuário não terá que entrar novamente. Após clicar no link, uma nova guia é aberta no navegador com uma caixa de diálogo. Na seção superior com o cabeçalho, "já é um cliente dos serviços de nuvem da Microsoft? Entre em sua conta, "Selecione o botão **entrar** para entrar automaticamente no Gerenciador de conformidade.

## <a name="known-issues-in-compliance-score-preview"></a>Problemas conhecidos na pontuação de conformidade (visualização)

As seções a seguir abordam problemas conhecidos a serem resolvidos em futuras versões da Pontuação de conformidade.

### <a name="long-load-times-for-non-admin-users"></a>Tempos de carregamento longos para usuários que não são administradores
Nota de conformidade os usuários que possuem funções diferentes de uma função de administrador podem enfrentar tempos de carregamento longos ao tentar uma entrada. A atualização do navegador resolverá esse problema. Saiba mais sobre as [funções de Pontuação de conformidade](compliance-score-setup.md#set-user-permissions-and-assign-roles).

### <a name="supported-browsers"></a>Navegadores com suporte

- As versões mais recentes do Microsoft Edge, do Chrome e do Safari são suportadas.
- Os dados atualizados às vezes não aparecem até que seu navegador seja atualizado.
- Não há suporte para o Internet Explorer.
