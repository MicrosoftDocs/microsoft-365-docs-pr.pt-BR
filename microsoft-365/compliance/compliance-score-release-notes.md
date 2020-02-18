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
ms.openlocfilehash: d89e1415b836e79187c9e484fef72670f828cfbf
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078618"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a>Notas de versão da Pontuação de conformidade da Microsoft (visualização)

A visualização pública da Pontuação de conformidade da Microsoft fornece acesso antecipado às futuras funcionalidades e atualizações. Verifique esta página com frequência para saber o que há de novo.

A pontuação de conformidade é um novo recurso do [centro de conformidade da Microsoft 365](microsoft-365-compliance-center.md) que calcula uma pontuação baseada em risco, medindo seu progresso em direção à conclusão de ações recomendadas que ajudam a reduzir os riscos de conformidade.

## <a name="whats-new"></a>Novidades

### <a name="new-templates-for-assessments"></a>Novos modelos para avaliações

Novos modelos pré-configurados para avaliações são lançados em produção para a pontuação de conformidade (visualização) à medida que eles se tornam disponíveis. Confira a [lista completa de modelos aqui](compliance-score.md#templates). Os modelos adicionados recentemente incluem:

- Lei de proteção de dados gerais do Brasil (LGPD)
- IRAP/ISM do governo australiano (versão prévia)
- ISO 27701:2019
- SOC 1
- SOC 2

### <a name="compliance-score-relationship-to-compliance-manager"></a>Relação de Pontuação de conformidade com o Gerenciador de conformidade

Muitas das funções de conformidade manipuladas no Gerenciador de conformidade agora podem ser feitas na pontuação de conformidade. No entanto, algumas funcionalidades ainda residem apenas no gerente de conformidade, e alguma funcionalidade anterior no Gerenciador de conformidade é alterada durante o período de visualização pública. 

Mantenha esses pontos em mente ao trabalhar com a pontuação de conformidade e o gerente de conformidade durante a visualização pública:

- **Gerenciando avaliações**: os usuários podem exibir avaliações e seus detalhes de status na pontuação de conformidade. No entanto, os usuários só podem executar tarefas de gerenciamento de avaliação no gerente de conformidade ([instruções de exibição](working-with-compliance-manager.md#assessments)) e as tarefas são limitadas ao seguinte:
    - Carregar novas avaliações, mas não modificar as avaliações existentes. Se você precisar modificar uma avaliação existente, será necessário carregar um novo modelo.
    - Avaliações de exportação
    - Avaliações de arquivamento
    - Exibir avaliações arquivadas
 - **Criar modelos para avaliações**: 
   - Os usuários devem acessar o Gerenciador de conformidade para criar novos modelos e exportar modelos existentes. 
   - Os modelos existentes não podem ser personalizados. Leia as instruções de [Gerenciamento de modelos no Gerenciador de conformidade](working-with-compliance-manager.md#templates).
   - Ao criar um modelo, você deve incluir as dimensões de **produto** e **certificação** para garantir que seu modelo seja exibido na pontuação de conformidade.
 - **Definir permissões**: Pontuação de conformidade os usuários que não receberam permissões anteriormente no Gerenciador de conformidade devem ter suas permissões definidas no centro de conformidade da Microsoft 365 ([saiba mais](compliance-score-setup.md#set-user-permissions-and-assign-roles)). Os usuários cujas funções foram definidas anteriormente no gerente de conformidade podem usar o mesmo nível de acesso ao trabalhar em Pontuação de conformidade.
- **Transferência de dados**: as organizações com dados residentes no Gerenciador de conformidade verão os dados na pontuação de conformidade e vice-versa.
- **Entrar no Gerenciador de conformidade da Pontuação de conformidade**: se um usuário estiver conectado à pontuação de conformidade e selecionar um link para acessar o Gerenciador de conformidade, o usuário não terá que entrar novamente. Após clicar no link, uma nova guia é aberta no navegador com uma caixa de diálogo. Na seção superior com o cabeçalho, "já é um cliente dos serviços de nuvem da Microsoft? Entre em sua conta, "Selecione o botão **entrar** para entrar automaticamente no Gerenciador de conformidade.

## <a name="known-issues-in-compliance-score-preview"></a>Problemas conhecidos na pontuação de conformidade (visualização)

As seções a seguir abordam problemas conhecidos a serem resolvidos em futuras versões da Pontuação de conformidade.

### <a name="launch-now-links-in-certain-improvement-actions"></a>Iniciar agora links em algumas ações de aperfeiçoamento

Em determinadas ações de aprimoramento, selecionar o link **Iniciar agora** que aparece sob as instruções de implementação resulta em um erro. Para acessar o destino apropriado, que é o centro de administração do SharePoint, siga estas etapas:

1. Vá para o [centro de administração do Microsoft 365](https://admin.microsoft.com).
2. No menu de navegação à esquerda, selecione **Mostrar tudo**.
3. Em **centros de administração,** selecione **SharePoint**.

Veja a seguir as ações de aperfeiçoamento afetadas, que residem na categoria **proteger informações** :
  - Aplicar criptografia à biblioteca do SharePoint
  - Classificar dados no SharePoint Online
  - Configurar links de compartilhamento externos para expirar
  - Habilitar o controle de versão para bibliotecas de documentos

### <a name="long-load-times-for-non-admin-users"></a>Tempos de carregamento longos para usuários que não são administradores
Nota de conformidade os usuários que possuem funções diferentes de uma função de administrador podem enfrentar tempos de carregamento longos ao tentar uma entrada. A atualização do navegador resolverá esse problema. (Saiba mais sobre as [funções de Pontuação de conformidade](compliance-score-setup.md#set-user-permissions-and-assign-roles).)

### <a name="supported-browsers"></a>Navegadores com suporte

- As versões mais recentes do Microsoft Edge, do Chrome e do Safari são suportadas.
- Pode haver casos em que os dados atualizados não aparecem até que seu navegador seja atualizado.
- A versão de visualização do Microsoft Edge não é suportada, mas não tem problemas conhecidos.
- Não há suporte para o Internet Explorer.
 
### <a name="language-support"></a>Suporte a idiomas

- A pontuação de conformidade só está disponível no inglês dos EUA.
