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
ms.openlocfilehash: 73fa3ac2ca15d922a74e1d3ceef6cc74a3bdedca
ms.sourcegitcommit: f70f75b9dd163c00a3c6bc4b9f9b055e90c50367
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2020
ms.locfileid: "43790564"
---
# <a name="microsoft-compliance-manager-preview-release-notes"></a>Notas de versão do Gerenciador de conformidade da Microsoft (prévia)

A visualização pública do Gerenciador de conformidade fornece acesso antecipado às futuras funcionalidades e atualizações. Esta página contém atualizações sobre novos recursos, funcionalidade aprimorada e problemas conhecidos com a versão atual.

Você pode usar a ferramenta [Gerenciador de conformidade](https://servicetrust.microsoft.com/ComplianceManager) no [portal de confiança do serviço](https://servicetrust.microsoft.com) para rastrear, atribuir e verificar as atividades de conformidade regulatória relacionadas aos serviços de nuvem da Microsoft.

## <a name="improved-template-creation-and-update-process"></a>Melhor criação de modelo e processo de atualização

Atualizamos o processo de importação, exportação e modificação de modelos para avaliações. A nova experiência simplificada facilitará a você a reunir suas próprias avaliações em seu fluxo de trabalho e mantê-las atualizadas.

### <a name="the-old-process"></a>O processo antigo

Havia duas maneiras de criar um modelo no Gerenciador de conformidade. Você pode copiar um modelo existente ou importar dados de modelo de uma planilha do Excel para um novo modelo. Na página de **modelos** , selecione **+ Adicionar modelo** para criar um novo modelo de marca, inserindo um nome, selecionando dimensões e carregando um arquivo do Excel com um formato e esquema específicos. Ou você pode marcar a caixa **Copiar de um modelo existente** , selecionar um modelo a ser copiado e verificar as dimensões. Personalização de design o modelo exigia um processo de várias etapas que começou selecionando **Adicionar controle personalizado** após a criação do modelo.

### <a name="the-new-process"></a>O novo processo

Facilitamos a criação de novos modelos. Em um processo de **extensão** de uma etapa, você pode adicionar uma planilha com suas ações e controles a um modelo existente da Microsoft para criar sua própria versão personalizada. Na página **modelos** no Gerenciador de conformidade, selecione **+ Adicionar modelo**. No painel do menu suspenso **modelo** , marque a caixa de seleção **criar extensão a partir do modelo global** . Você pode adicionar personalizações com um novo formato do Excel menos complexo do que o anterior. Esse novo processo substitui a **cópia anterior de um modelo existente** e **adiciona funções de controle personalizadas** .

Cada vez que a avaliação original é atualizada através do processo de controle de versão descrito abaixo, sua avaliação personalizada herdará essas atualizações e manterá seus controles personalizados.

Também é mais fácil modificar seus próprios modelos existentes. Você pode exportar seu modelo, fazer alterações na mesma pasta de trabalho e, em seguida, importá-lo com suas edições salvas.

Veja instruções detalhadas sobre como [criar modelos](working-with-compliance-manager.md#templates) com esse novo processo.

## <a name="versioning-notice-and-control"></a>Controle e aviso de controle de versão

Sua organização recebeu avaliações atualizadas no lançamento de abril de 2020 do gerente de conformidade para ajudá-lo a se alinhar com as atualizações de certificação e conformidade. Em frente, forneceremos uma maneira clara de entender e aceitar todas as atualizações futuras por meio de **alertas de controle de versão**.

Sempre que uma atualização está disponível para o modelo de uma avaliação ou para uma ação de melhoria, um ícone de alerta avisa que uma atualização está pronta. Quando você clica nesse ícone, uma janela pop-up explica a atualização e solicita que você aceite. Selecionar o ícone de alerta revela um painel de submenu que explica a atualização e solicita que você aceite. Saiba mais sobre como [aceitar atualizações para avaliações](working-with-compliance-manager.md#versioning-alerts-for-assessment-updates).

## <a name="common-actions-will-synch-status-across-groups"></a>As ações comuns irão sincronizar o status entre grupos

Se sua organização tiver vários grupos de avaliações, o comportamento das ações **técnicas** (ou seja, ações que afetam toda a organização) foi alterado. Quaisquer ações duplicadas entre grupos foram combinadas em uma única ação. Essa ação única contém todas as anotações e evidências carregadas das versões duplicadas. Com essa alteração, as ações técnicas agora se comportam como faziam quando pertenciam ao mesmo grupo. Todas as alterações feitas na ação em um grupo ou avaliação serão refletidas em todas as instâncias. O **status da implementação**, a **data de implementação**, o status do **teste**e a **data de teste** irão refletir as atualizações mais recentes.

## <a name="language-support"></a>Suporte a idiomas

Agora, o Gerenciador de conformidade está disponível nos seguintes idiomas, além de inglês: Chinês (simplificado), chinês (tradicional), francês, alemão, italiano, japonês, coreano, Português (Brasil), russo e espanhol.

## <a name="known-issues-in-compliance-manager-preview"></a>Problemas conhecidos no gerente de conformidade (visualização)

A seção a seguir aborda problemas conhecidos na versão atual do Gerenciador de conformidade.

### <a name="dimension-values"></a>Valores de dimensão

Como resultado da migração de dados durante a versão de abril de 2020, algumas organizações podem ver um **produto** ou um valor de **certificação** de "Custom" em suas avaliações e modelos. Esse valor foi inserido automaticamente se os campos de **produto** ou de **certificação** estiverem em branco, e não haverá efeito nos fluxos de trabalho de dados.

### <a name="compliance-score"></a>Pontuação de Conformidade

- Para itens de ação marcados como **não no escopo**, a pontuação atribuída ao item de ação não é excluída do cálculo da Pontuação de conformidade. Itens de ação marcados **não no escopo** não aumentam a pontuação de conformidade.

### <a name="secure-score"></a>Classificação de Segurança

- Resultados de pontos de segurança não estão disponíveis para alguns itens de ações em determinadas assinaturas do Microsoft 365 e do Office 365. **Não foi possível detectar** o resultado da Pontuação segura nesses casos.
- Às vezes, os resultados de Pontuação segura são retornados para políticas correspondentes e itens de ação não concluídos.
- Para novos locatários, as atualizações de Pontuação segura de todas as ações são automaticamente ativadas. O administrador global pode definir a opção de atualização contínua de Pontuação segura como desativada, o que desativa as atualizações de todas as ações.
  - **Observação**: quando as organizações implantam pela primeira vez o Microsoft 365 ou o Office 365, leva aproximadamente sete dias para uma pontuação segura para coletar dados completamente e fatorar sua pontuação. Durante esse tempo, definir a opção de atualização contínua de Pontuação segura como **desativado** e definir manualmente uma ação a ser **implementada** contará essa ação em direção à sua pontuação. Após os sete dias iniciais, a ativação da atualização contínua de Pontuação segura habilitará o monitoramento contínuo desse ponto em diante.
- Quando as atualizações de Pontuação segura estiverem ativadas, as ações serão ativamente monitoradas por Pontuação segura, embora a data de teste da ação não seja atualizada para refletir o monitoramento.
- Quando novas avaliações são criadas, as pontuações incluem automaticamente pontuações de controle gerenciado pela Microsoft e integração de Pontuação segura.
- Qualquer ação que não é suportada pela integração de Pontuação segura pode ser implementada manualmente. Uma implementação manual será fatorar a pontuação para o grupo dessa ação.

### <a name="export"></a>Exportar

- O modelo exportar para JSON falha quando o status do modelo é definido como **importado** ou com **aprovação pendente**.

### <a name="supported-browsers"></a>Navegadores com suporte

- As versões mais recentes do Microsoft Edge, do Chrome e do Safari são suportadas.
- Pode haver casos em que os dados atualizados não são exibidos até que seu navegador seja atualizado.
- A versão de visualização do Microsoft Edge não é suportada, mas não tem problemas conhecidos.
- Não há suporte para o Internet Explorer.

### <a name="session-timeout"></a>Tempo limite da sessão

- Quando uma sessão expira, um erro "algo deu errado" pode ser exibido. Para resolver, vá para o [Gerenciador de conformidade](https://servicetrust.microsoft.com/ComplianceManager) e faça login novamente.
