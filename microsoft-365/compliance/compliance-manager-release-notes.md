---
title: Notas de versão do Gerenciador de conformidade da Microsoft
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
ms.openlocfilehash: 815862616e1bdbf4b3be1d77de2a541ad703149f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072224"
---
# <a name="release-notes-for-compliance-manager-preview"></a>Notas de versão do Gerenciador de conformidade (visualização)

A visualização pública do Gerenciador de conformidade fornece acesso antecipado às futuras funcionalidades e atualizações.

Você pode usar a ferramenta atualizada do [Gerenciador de conformidade](https://servicetrust.microsoft.com/ComplianceManager) no portal de [confiança do serviço](https://servicetrust.microsoft.com) para rastrear, atribuir e verificar as atividades de conformidade regulatória relacionadas aos serviços de nuvem da Microsoft.

## <a name="whats-new-in-compliance-manager-preview"></a>O que há de novo no Gerenciador de conformidade (versão prévia)

- **Integração com a pontuação segura da Microsoft:** O Gerenciador de conformidade oferece suporte à integração com a [Pontuação segura da Microsoft](../security/mtp/microsoft-secure-score.md) , mapeando as ações gerenciadas pelo cliente para mais de 50 de Pontuação segura. Quando você completa uma ação mapeada na pontuação segura, a ação correspondente do Gerenciador de conformidade é atualizada automaticamente.

- **Importe avaliações personalizadas:** Além das avaliações internas, o Gerenciador de conformidade agora oferece suporte à importação de modelos personalizados. Você pode criar avaliações personalizadas para qualquer produto ou serviço e qualquer padrão ou regulamentação.

- **Itens de ações:** Os itens de ação agora são itens individuais e muitos incluem coleção de telemetria da API do Microsoft Secure Score Graph. Sempre que possível, as recomendações de ações técnicas agora têm links para a página de configuração aplicável no serviço do Office 365.

- **Gerenciamento de locatário:** Nova interface para gerenciar novos elementos de dados no Gerenciador de conformidade (visualização):
    - **Dimensões:** Exibir, adicionar e personalizar metadados para modelos, avaliações e itens de ação que permitem que você crie pivôs personalizados para filtros.
    - **Proprietários:** Especifique um proprietário para cada item de ação.
    - **Ações do cliente:** Gerencie a lista completa de itens de ações incluídas no Gerenciador de conformidade (visualização) e habilite/desabilite o monitoramento de Pontuação segura para itens de ação integrados à pontuação segura.

- **Pontuação de conformidade atualizada**: a metodologia mudou para suportar a sincronização com a pontuação segura da Microsoft. O sistema de Pontuação remove os créditos de controle gerenciados pela Microsoft e se concentra apenas na conclusão dos controles gerenciados pelo cliente.

## <a name="known-issues-in-compliance-manager-preview"></a>Problemas conhecidos no gerente de conformidade (visualização)

As seções a seguir abordam problemas conhecidos a serem resolvidos em futuras versões do Gerenciador de conformidade.

### <a name="compliance-score"></a>Pontuação de conformidade

- Para itens de ação marcados como **não no escopo**, a pontuação atribuída ao item de ação não é excluída do cálculo da Pontuação de conformidade. Itens de ação marcados **não no escopo** não aumentam sua pontuação de conformidade.

### <a name="secure-score"></a>Classificação de Segurança

- Resultados de Pontuação segura não estão disponíveis para alguns itens de ações em determinadas assinaturas do Microsoft 365 e do Office 365. O resultado da Pontuação segura é ' não pôde ser detectado ' nesses casos.
- Às vezes, os resultados de Pontuação segura são retornados para políticas correspondentes e itens de ação não concluídos.

### <a name="microsoft-managed-controls"></a>Controles gerenciados pela Microsoft

- A data de teste dos controles gerenciados pela Microsoft não aparecerá na interface do usuário, mesmo quando estiver incluída na avaliação. Para ver as informações de data de teste, você deve exportar a avaliação.

### <a name="customization"></a>Personalização

- Adicionar controles personalizados permite adicionar um novo controle a uma família de controles existente, mas não permite que você adicione uma nova família de controle.
- Esta versão não dá suporte à vinculação de itens de ação ou à adição de itens de ações ou controles a uma avaliação.
- Se você criar uma ação personalizada, não será possível editá-la ou excluí-la.

### <a name="control-families-not-shown-in-assessments"></a>Famílias de controle não exibidas em avaliações

- Quando você importa um modelo, todas as avaliações baseadas nesse modelo refletem todas as famílias de controle que fazem parte do modelo. Mas se você adicionar novas famílias de controle ao modelo, qualquer avaliação existente não refletirá as alterações. Somente novas avaliações criadas a partir do modelo atualizado refletem as alterações.

### <a name="filters"></a>Filtros

- A filtragem em itens de ação ou controles não produz resultados corretos de forma consistente.

### <a name="templates"></a>Modelos

- Os modelos arquivados são editáveis e não devem ser editáveis.
- Os modelos bloqueados permitem a criação da avaliação, quando não deveriam. Bloquear um modelo é destinado a impedir que ele seja usado para criar avaliações.

### <a name="export"></a>Exportar

- O modelo exportar para JSON falha quando o status do modelo é definido como **importado** ou com **aprovação pendente**.

### <a name="supported-browsers"></a>Navegadores com suporte

- As versões mais recentes do Microsoft Edge, do Chrome e do Safari são suportadas.
- Pode haver casos em que os dados atualizados não aparecem até que seu navegador seja atualizado.
- A versão de visualização do Microsoft Edge não é suportada, mas não tem problemas conhecidos.
- Não há suporte para o Internet Explorer.

### <a name="session-timeout"></a>Tempo limite da sessão

- Quando uma sessão expira, um erro "algo deu errado" pode ser exibido. Para resolver, vá para o [Gerenciador de conformidade](https://servicetrust.microsoft.com/ComplianceManager) e faça login novamente.
 
### <a name="language-support"></a>Suporte a idiomas

- Todos os idiomas não são compatíveis com todas as páginas da Web. Se seu idioma local não é suportado, veja em inglês dos EUA.