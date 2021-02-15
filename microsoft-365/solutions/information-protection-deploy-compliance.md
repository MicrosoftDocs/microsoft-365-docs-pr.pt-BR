---
title: Usar o Gerenciador de Conformidade para gerenciar ações de melhoria
ms.author: chvukosw
author: chvukosw
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Saiba como usar a Pontuação de Conformidade e o Gerenciador de Conformidade para melhorar seu nível de proteção para dados pessoais.
ms.openlocfilehash: f90826795197b392f629eb8eec71b7f27081b697
ms.sourcegitcommit: ccbb405227880f40581c3cdfb974368a29d496f7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48791877"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a>Usar o Gerenciador de Conformidade para gerenciar ações de melhoria

O Microsoft Compliance Manager pode ajudá-lo a gerenciar melhorias relacionadas a regulamentos de privacidade de dados, como o [RGPD (Regulamento](../compliance/gdpr.md)Geral sobre a Proteção de Dados) da União Europeia, a Lei de Proteção do Consumidor da Califórnia [(CCPA),](../compliance/ccpa-faq.md)a HIPAA-HITECH (lei de privacidade de serviços de saúde dos EUA) e a LGPD (Lei de Proteção de Dados do Brasil).

Este artigo fornece orientações sobre o uso dessa ferramenta para fins de privacidade de dados.

>[!Note]
>As recomendações do Gerenciador de Conformidade não devem ser interpretadas como uma garantia de conformidade. Você pode avaliar e validar a eficácia dos controles do cliente em seu ambiente regulatório. Esses serviços estão sujeitos aos termos e condições nos Termos [de Serviços Online.](https://go.microsoft.com/fwlink/?linkid=2108910) Confira também as diretrizes de licenciamento do [Microsoft 365 para segurança e conformidade](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)
>

## <a name="getting-started-with-compliance-manager"></a>Getting started with Compliance Manager

#### <a name="what-is-compliance-manager"></a>O que é o Gerenciador de Conformidade

[O Gerenciador de](../compliance/compliance-manager.md) Conformidade é uma ferramenta de avaliação de risco baseada em fluxo de trabalho no centro de conformidade do Microsoft 365 para gerenciar atividades de conformidade regulamentar relacionadas aos serviços de nuvem da Microsoft. Como parte da sua assinatura do Microsoft 365 ou Azure Active Directory (Azure AD), o Gerenciador de Conformidade ajuda você a gerenciar a conformidade regulamentar dentro do modelo de responsabilidade compartilhada dos serviços de nuvem da Microsoft.

**Pronto para usar avaliações**

O Gerenciador de Conformidade fornece modelos pré-construídos para criar avaliações alinhadas às regulamentações [relacionadas](../compliance/compliance-manager-assessments.md) à privacidade de dados, como RGPD e HIPAA/HITECH. Os modelos têm mapeamento de controle interno para ajudá-lo a tomar ações de melhoria para atender aos requisitos da regulamentação. Cada avaliação fornece informações sobre os controles que cada regulamentação chama para um serviço de destino específico, dividido por controles que você gerencia e controla que a Microsoft gerencia. 

Usar um modelo pré-criado ajuda você a começar rapidamente com avaliações de risco. À medida que você se tornar mais proficiente no uso do Gerenciador de Conformidade, poderá personalizar um modelo pré-criado adicionando seus próprios controles e ações de melhoria, ou pode criar suas próprias avaliações personalizadas para atender às necessidades da sua organização.

Exibir a [lista completa de modelos de avaliação fornecidos](../compliance/compliance-manager-templates-list.md) pelo Gerenciador de Conformidade.

**Pontuação de conformidade em tempo real**

O Gerenciador de Conformidade também fornece uma pontuação de conformidade que mede seu progresso na conclusão de ações de melhoria recomendadas nos controles. Você pode usar essa pontuação para ajudar a monitorar seu progresso e priorizar ações com base no potencial de reduzir o risco.

#### <a name="use-the-compliance-manager-quickstart-guide"></a>Usar o guia de início rápido do Gerenciador de Conformidade

O [guia de início rápido do](../compliance/compliance-manager-quickstart.md) Gerenciador de Conformidade fornece etapas e links completos para os principais recursos para ajudá-lo a trabalhar com o Gerenciador de Conformidade:

- [Primeira visita: familiarizar-se com o Gerenciador de Conformidade](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - Trabalhar com seu painel do Gerenciador de Conformidade
    - Noções básicas sobre a pontuação de conformidade
    - Aprender sobre ações de melhoria
    - Noções básicas sobre avaliações e modelos
- [Aumentando: configure o Gerenciador de Conformidade para gerenciar suas atividades de conformidade](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - Criando e gerenciando sua primeira avaliação
    - Executar a implementação e testar o trabalho em ações de melhoria para concluir os controles em suas avaliações
    - Noções básicas sobre como ações diferentes impactam sua pontuação de conformidade
- [Dimensionamento: use a funcionalidade avançada para atender às suas necessidades personalizadas](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - Criar suas avaliações personalizadas para rastrear produtos que não são do Microsoft 365
    - Modificar modelos existentes para adicionar ou remover controles
    - Configurando testes automatizados de ações de melhoria

## <a name="how-your-compliance-score-is-calculated"></a>Como a pontuação de conformidade é calculada

A pontuação de conformidade é calculada com base em uma combinação das implementações de controle gerenciado pelo cliente e pela Microsoft. Consulte [o cálculo da pontuação de](../compliance/compliance-score-calculation.md) conformidade para uma explicação detalhada.

Os controles são atribuídos com um valor de pontuação com base em se são obrigatórios ou discricionários e se são preventivos, descontivos ou corretivos. Esses coletivamente representam o risco de não implementá-lo em relação a outros controles.

Conforme apresentado no artigo de cálculo da pontuação de conformidade, os controles preventivos têm uma pontuação maior do que a de descontorativa e corretiva, e os controles obrigatórios têm uma pontuação maior do que a discricionária.

A IU de administrador da Pontuação de Conformidade não lista esses parâmetros, nem fornece a capacidade de filtrar por eles. No entanto, se você baixar o modelo associado do Gerenciador de Conformidade, o conjunto de dados resultante lista esses parâmetros para a maioria das regulamentações.

Para controles técnicos, o Gerenciador de Conformidade atualiza automaticamente a pontuação da ação de melhoria depois que a ação é implementada e testada com êxito. Outras ações de controle não técnicas, como aquelas operacionais ou relacionadas à documentação, precisam ser registradas manualmente conforme implementadas antes que os pontos sejam contados em direção &mdash; &mdash; à sua pontuação.

Você também estará implementando determinadas ações de melhoria para outros fins, por exemplo, usando rótulos de retenção por motivos diferentes da conformidade com a regulamentação de privacidade de dados, para que você receba crédito por usar esse recurso, mesmo que ele seja usado para outros fins, e não parte de uma ação deliberada de &mdash; &mdash; conformidade.

Sua pontuação de conformidade deve ser considerada uma medida relativa para controlar a melhoria em larga escala. Você não deve buscar uma pontuação perfeita.

## <a name="additional-guidance"></a>Orientações adicionais

Aqui estão algumas dicas importantes para usar o Gerenciador de Conformidade para ajudá-lo a atingir a conformidade com a regulamentação de privacidade de dados:

- Cada regulamentação de privacidade de dados tem uma combinação de controles técnicos, especificações de documentação e requisitos operacionais, de processo e de relatório. Todas elas aparecem nas ações de melhoria.

- Para concentrar a exibição das ações de melhoria à sua  área de interesse, você pode filtrar por tipo de ação na guia Soluções no administrador do Gerenciador de Conformidade. Saiba mais sobre como [filtrar a exibição do painel do Gerenciador de Conformidade.](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view)

- A importância relativa e a prioridade das ações de melhoria identificadas no Gerenciador de Conformidade devem ser consideradas como parte de uma revisão de risco mais ampla, juntamente com o risco de privacidade de dados que você determinou que sua organização precisa gerenciar.

- Mesmo com a agregação de ações de melhoria em vários requisitos regulatórios, se os modelos de avaliação de regulamentação para RGPD, LGPD, CCPA e HIPAA-HITECH forem selecionados, por exemplo, quase 400 ações de melhoria serão listadas no Gerenciador de Conformidade. Para lidar melhor com essa lista longa, use o filtro de ação de melhoria para reduzir o conjunto de resultados para uma lista mais gerenciável.

- O filtro Categorias fornece um meio para filtrar ações de melhoria por grupo lógico, ao qual os artigos Track, Prevent, Protect, Retain e Investigate nesta solução geral se alinham.

- Alguns dos controles listados nas ações de melhoria podem ser considerados mais diretamente vinculados a um artigo regulatório específico, enquanto outros controles podem ser mais indiretamente associados ao poder de uma regulamentação e muitas vezes são simplesmente atividades recomendadas ou práticas recomendadas.