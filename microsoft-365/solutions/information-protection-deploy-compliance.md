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
description: Saiba como usar o Compliance Score and Compliance Manager para melhorar seu nível de proteção para dados pessoais.
ms.openlocfilehash: 87131ea65661e8285fd7c3b36a87c79b618348d7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918565"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a>Usar o Gerenciador de Conformidade para gerenciar ações de melhoria

O Microsoft Compliance Manager pode ajudá-lo a gerenciar melhorias relacionadas a regulamentos de privacidade de dados, como o [RGPD (Regulamento](/compliance/regulatory/gdpr)Geral de Proteção de Dados da União Europeia), a Lei de Proteção de Consumidor da [Califórnia (CCPA),](/compliance/regulatory/ccpa-faq)a HIPAA-HITECH (Lei de Privacidade de Assistência à Saúde dos EUA) e a LGPD (Lei de Proteção de Dados do Brasil).

Este artigo fornece orientações sobre o uso dessa ferramenta para fins de privacidade de dados.

>[!Note]
>As recomendações do Gerenciador de Conformidade não devem ser interpretadas como uma garantia de conformidade. Você deve avaliar e validar a eficácia dos controles do cliente de acordo com seu ambiente regulatório. Esses serviços estão sujeitos aos termos e condições nos Termos [de Serviços Online.](https://go.microsoft.com/fwlink/?linkid=2108910) Consulte também [Microsoft 365 diretrizes de licenciamento para segurança e conformidade](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)
>

## <a name="getting-started-with-compliance-manager"></a>Iniciando com o Gerenciador de Conformidade

#### <a name="what-is-compliance-manager"></a>O que é o Gerenciador de Conformidade

[O Gerenciador de](../compliance/compliance-manager.md) Conformidade é uma ferramenta de avaliação de risco baseada em fluxo de trabalho no centro de conformidade Microsoft 365 gerenciamento de atividades de conformidade regulamentar relacionadas aos serviços de nuvem da Microsoft. Como parte de sua assinatura Microsoft 365 ou Azure Active Directory (Azure AD), o Gerenciador de Conformidade ajuda você a gerenciar a conformidade regulamentar no modelo de responsabilidade compartilhada para os serviços de nuvem da Microsoft.

**Pronto para usar avaliações**

O Gerenciador de Conformidade fornece modelos pré-construídos para a criação de avaliações alinhadas aos [regulamentos](../compliance/compliance-manager-assessments.md) relacionados à privacidade de dados, como rgpd e HIPAA/HITECH. Os modelos têm mapeamento de controle interno para ajudá-lo a tomar ações de melhoria para atender aos requisitos da regulamentação. Cada avaliação fornece informações sobre os controles que cada regulamentação chama para específico para o serviço de destino, dividido por controles que você gerencia e controla que a Microsoft gerencia. 

Usar um modelo pré-criado ajuda você a começar rapidamente com avaliações de risco. À medida que você se torna mais proficiente no uso do Gerenciador de Conformidade, você pode personalizar um modelo pré-criado adicionando seus próprios controles e ações de melhoria, ou pode criar suas próprias avaliações personalizadas para atender às necessidades da sua organização.

Exibir a [lista completa de modelos de avaliação fornecidos](../compliance/compliance-manager-templates-list.md) pelo Gerenciador de Conformidade.

**Pontuação de conformidade em tempo real**

O Gerenciador de Conformidade também fornece uma pontuação de conformidade que mede seu progresso na conclusão das ações de melhoria recomendadas nos controles. Você pode usar essa pontuação para ajudar a monitorar seu progresso e priorizar ações com base no potencial de reduzir o risco.

#### <a name="use-the-compliance-manager-quickstart-guide"></a>Usar o guia de início rápido do Gerenciador de Conformidade

O [guia de início rápido do Gerenciador](../compliance/compliance-manager-quickstart.md) de Conformidade fornece etapas e links para os principais recursos para ajudá-lo a trabalhar com o Gerenciador de Conformidade:

- [Primeira visita: familiarizar-se com o Gerenciador de Conformidade](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - Trabalhando com seu painel do Gerenciador de Conformidade
    - Noções básicas sobre a pontuação de conformidade
    - Aprender sobre ações de melhoria
    - Noções básicas sobre avaliações e modelos
- [Incrementando: configurar o Gerenciador de Conformidade para gerenciar suas atividades de conformidade](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - Criar e gerenciar sua primeira avaliação
    - Executar a implementação e o teste funcionam em ações de melhoria para concluir controles em suas avaliações
    - Noções básicas sobre como ações diferentes impactam sua pontuação de conformidade
- [Dimensionamento: use a funcionalidade avançada para atender às suas necessidades personalizadas](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - Criando suas avaliações personalizadas para rastrear produtos que não Microsoft 365 produtos
    - Modificar modelos existentes para adicionar ou remover controles
    - Configuração de testes automatizados de ações de melhoria

## <a name="how-your-compliance-score-is-calculated"></a>Como a pontuação de conformidade é calculada

Sua pontuação de conformidade é calculada com base em uma combinação de implementações de controle gerenciadas pelo cliente da Microsoft. Consulte [o cálculo de pontuação de conformidade](../compliance/compliance-score-calculation.md) para uma explicação detalhada.

Os controles são atribuídos a um valor de pontuação com base em se eles são obrigatórios ou discricionários e se são preventivos, detetives ou corretivos. Elas representam coletivamente o risco de não implementá-la em relação a outros controles.

Conforme apresentado no artigo de cálculo de pontuação de conformidade, os controles preventivos têm uma pontuação maior do que as de detetive e corretiva, e os controles obrigatórios têm uma pontuação maior do que as discricionárias.

A interface do usuário do administrador de Pontuação de Conformidade não lista esses parâmetros, nem fornece a capacidade de filtrar por eles. No entanto, se você baixar o modelo associado do Gerenciador de Conformidade, o conjunto de dados resultante lista esses parâmetros para a maioria dos regulamentos.

Para controles técnicos, o Gerenciador de Conformidade atualiza automaticamente a pontuação da ação de melhoria depois que a ação foi implementada e testada com êxito. Outras ações de controle não técnicas, como as que estão operacionais ou relacionadas à documentação, precisam ser registradas manualmente conforme implementado antes da contagem de pontos para &mdash; &mdash; sua pontuação.

Você também está implementando determinadas ações de melhoria para outras finalidades, por exemplo, usando rótulos de retenção por motivos diferentes da conformidade com a regulamentação de privacidade de dados para que você receba crédito por usar esse recurso, mesmo que ele seja usado para outras finalidades, e não parte de uma ação de conformidade &mdash; &mdash; deliberada.

Sua pontuação de conformidade deve ser considerada uma medida relativa para controlar a melhoria em uma escala ampla. Você não deve buscar uma pontuação perfeita.

## <a name="additional-guidance"></a>Orientações adicionais

Aqui estão algumas dicas importantes para usar o Gerenciador de Conformidade para ajudá-lo a atingir a conformidade com a regulamentação de privacidade de dados:

- Cada regulamentação de privacidade de dados tem uma combinação de controles técnicos, especificações de documentação e requisitos operacionais, de processo e de relatórios. Todas elas aparecem nas ações de melhoria.

- Para focalizar a exibição de ações de melhoria para sua  área de interesse, você pode filtrar por tipo de ação na guia Soluções no administrador do Gerenciador de Conformidade. Saiba mais sobre como [filtrar a exibição do painel do Gerenciador de Conformidade.](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view)

- A importância relativa e a prioridade das ações de melhoria identificadas no Gerenciador de Conformidade devem ser consideradas como parte de uma revisão de risco mais ampla, juntamente com o risco de privacidade de dados que você determinou que sua organização precisa gerenciar.

- Mesmo com a agregação de ações de melhoria em vários requisitos regulatórios, se os modelos de avaliação de regulamentação do RGPD, LGPD, CCPA e HIPAA-HITECH forem selecionados, por exemplo, quase 400 ações de melhoria serão listadas no Gerenciador de Conformidade. Para lidar melhor com essa lista longa, use o filtro de ação de melhoria para reduzir o conjunto de resultados para uma lista mais gerenciável.

- O filtro Categories fornece um meio para filtrar ações de melhoria por meio de um grupo lógico, ao qual os artigos Track, Prevent, Protect, Retain e Investigate se alinham a essa solução geral.

- Alguns dos controles listados nas ações de melhoria podem ser considerados mais diretamente vinculados a um artigo regulamentar específico, enquanto outros controles podem ser mais associados indiretamente ao espírito de uma regulamentação e muitas vezes são simplesmente atividades recomendadas ou práticas recomendadas.