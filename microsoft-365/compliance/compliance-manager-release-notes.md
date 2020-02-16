---
title: Notas de versão do Gerenciador de conformidade da Microsoft
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
description: O Gerenciador de conformidade da Microsoft é uma ferramenta de avaliação de riscos gratuita baseada em fluxo de trabalho no portal de confiança do serviço Microsoft. O Gerenciador de conformidade permite que você rastreie, atribua e verifique as atividades de conformidade normativa relacionadas aos serviços em nuvem da Microsoft.
ms.openlocfilehash: 3fc16e92e912676d7aedc861ffe8306d68388c95
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078648"
---
# <a name="release-notes-for-compliance-manager-preview"></a>Notas de versão do Gerenciador de conformidade (visualização)

A visualização pública do Gerenciador de conformidade fornece acesso antecipado às futuras funcionalidades e atualizações.

Você pode usar a ferramenta atualizada do [Gerenciador de conformidade](https://servicetrust.microsoft.com/ComplianceManager) no portal de [confiança do serviço](https://servicetrust.microsoft.com) para rastrear, atribuir e verificar as atividades de conformidade regulatória relacionadas aos serviços de nuvem da Microsoft.

## <a name="whats-new-in-compliance-manager-preview"></a>O que há de novo no Gerenciador de conformidade (versão prévia)

- **Acesso baseado em função ao Gerenciador de conformidade:** A função de **acesso de convidado** padrão foi removida. Para que um usuário acesse o gerente de conformidade, o administrador global deve [atribuir a cada usuário uma permissão](compliance-manager-overview.md#permissions).

- **Nota de conformidade atualizada**: a pontuação de conformidade agora inclui pontuações para ações gerenciadas pela Microsoft. A pontuação aumentará como resultado.

- **Itens de ações:** Os itens de ação agora são itens individuais e muitos incluem coleção de telemetria da API do Microsoft Secure Score Graph. Sempre que possível, as recomendações de ações técnicas agora têm links para a página de configuração aplicável no serviço do Office 365.

- **Gerenciamento de locatário:** Nova interface para gerenciar novos elementos de dados no Gerenciador de conformidade (visualização):
    - **Dimensões:** Exibir, adicionar e personalizar metadados para modelos, avaliações e itens de ação que permitem que você crie pivôs personalizados para filtros.
    - **Proprietários:** Especifique um proprietário para cada item de ação.
    - **Ações do cliente:** Gerencie a lista completa de itens de ações incluídas no Gerenciador de conformidade (visualização) e habilite/desabilite o monitoramento de Pontuação segura para itens de ação integrados à pontuação segura.

## <a name="known-issues-in-compliance-manager-preview"></a>Problemas conhecidos no gerente de conformidade (visualização)

As seções a seguir abordam problemas conhecidos a serem resolvidos em futuras versões do Gerenciador de conformidade.

### <a name="compliance-score"></a>Pontuação de Conformidade

- Para itens de ação marcados como **não no escopo**, a pontuação atribuída ao item de ação não é excluída do cálculo da Pontuação de conformidade. Itens de ação marcados **não no escopo** não aumentam a pontuação de conformidade.

### <a name="secure-score"></a>Classificação de Segurança

- Resultados de pontos de segurança não estão disponíveis para alguns itens de ações em determinadas assinaturas do Microsoft 365 e do Office 365. **Não foi possível detectar** o resultado da Pontuação segura nesses casos.
- Às vezes, os resultados de Pontuação segura são retornados para políticas correspondentes e itens de ação não concluídos.
- Para novos locatários, as atualizações de Pontuação segura para todas as ações são automaticamente ativadas. O administrador global pode definir a opção de atualização contínua de Pontuação segura como desativada, o que desativa as atualizações de todas as ações.
  - **Observação**: quando as organizações implantam pela primeira vez o Microsoft 365 ou o Office 365, leva aproximadamente sete dias para uma pontuação segura para coletar dados completamente e fatorar sua pontuação. Durante esse tempo, definir a opção de atualização contínua de Pontuação segura como **desativado** e definir manualmente uma ação a ser **implementada** contará essa ação em direção à sua pontuação. Após os sete dias iniciais, a ativação da atualização contínua de Pontuação segura habilitará o monitoramento contínuo desse ponto em diante.
- Quando as atualizações de Pontuação segura estiverem ativadas, as ações serão ativamente monitoradas por Pontuação segura, embora a data de teste da ação não seja atualizada para refletir o monitoramento.
- Quando novas avaliações são criadas, as pontuações incluem automaticamente pontuações de controle gerenciado pela Microsoft e integração de Pontuação segura.
- Qualquer ação que não é suportada pela integração de Pontuação segura pode ser implementada manualmente. Uma implementação manual será fatorar a pontuação para o grupo dessa ação.

### <a name="microsoft-managed-controls"></a>Controles gerenciados pela Microsoft

- A data de teste dos controles gerenciados pela Microsoft não aparecerá na interface do usuário, mesmo quando estiver incluída na avaliação. Para ver as informações de data de teste, você deve exportar a avaliação.

### <a name="customization"></a>Personalização

- Adicionar controles personalizados permite adicionar um novo controle a uma família de controles existente, mas não permite que você adicione uma nova família de controle.
- Esta versão não dá suporte à vinculação de itens de ação ou à adição de itens de ações ou controles a uma avaliação.
- Se você criar uma ação personalizada, não será possível editá-la ou excluí-la.

### <a name="control-families-not-shown-in-assessments"></a>Famílias de controle não exibidas em avaliações

- Quando você importa um modelo, todas as avaliações baseadas nesse modelo refletem todas as famílias de controle que fazem parte do modelo. Mas se você adicionar novas famílias de controle ao modelo, qualquer avaliação existente não refletirá as alterações. Somente novas avaliações criadas a partir do modelo atualizado refletem as alterações.

### <a name="templates"></a>Modelos

- Ao criar um modelo, você deve incluir as dimensões de **produto** e **certificação** para garantir que seu modelo seja exibido na pontuação de conformidade.
- Os modelos arquivados são editáveis e não devem ser editáveis.
- Os modelos bloqueados permitem a criação da avaliação quando não deveriam. Bloquear um modelo é destinado a impedir que ele seja usado para criar avaliações.

### <a name="export"></a>Exportar

- O modelo exportar para JSON falha quando o status do modelo é definido como **importado** ou com **aprovação pendente**.

### <a name="supported-browsers"></a>Navegadores com suporte

- As versões mais recentes do Microsoft Edge, do Chrome e do Safari são suportadas.
- Pode haver casos em que os dados atualizados não são exibidos até que seu navegador seja atualizado.
- A versão de visualização do Microsoft Edge não é suportada, mas não tem problemas conhecidos.
- Não há suporte para o Internet Explorer.

### <a name="session-timeout"></a>Tempo limite da sessão

- Quando uma sessão expira, um erro "algo deu errado" pode ser exibido. Para resolver, vá para o [Gerenciador de conformidade](https://servicetrust.microsoft.com/ComplianceManager) e faça login novamente.
 
### <a name="language-support"></a>Suporte a idiomas

- Todos os idiomas não são compatíveis com todas as páginas da Web. Se seu idioma local não é suportado, veja em inglês dos EUA.
