---
title: Usar o Gerenciador de conformidade para gerenciar ações de melhoria
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
description: Saiba como usar a pontuação de conformidade e o Gerenciador de conformidade para melhorar seu nível de proteção para dados pessoais.
ms.openlocfilehash: f90826795197b392f629eb8eec71b7f27081b697
ms.sourcegitcommit: ccbb405227880f40581c3cdfb974368a29d496f7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48791877"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a>Usar o Gerenciador de conformidade para gerenciar ações de melhoria

O gerente de conformidade da Microsoft pode ajudá-lo a gerenciar melhorias relacionadas a regulamentações de privacidade de dados, como o [rgpd (regulamentação geral de proteção de dados](../compliance/gdpr.md)da União Européia), a [Califórnia Consumer Protection Act CCPA)](../compliance/ccpa-faq.md), a HIPAA-alta (lei de privacidade de assistência médica) e a lei de proteção de dados do Brasil (LGPD).

Este artigo fornece orientação sobre o uso desta ferramenta para fins de privacidade de dados.

>[!Note]
>As recomendações do Gerenciador de Conformidade não devem ser interpretadas como uma garantia de conformidade. Você pode avaliar e validar a eficácia dos controles de clientes por seu ambiente normativo. Esses serviços estão sujeitos aos termos e condições nos [termos dos serviços online](https://go.microsoft.com/fwlink/?linkid=2108910). Confira também [orientações de licenciamento da Microsoft 365 para segurança e conformidade](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)
>

## <a name="getting-started-with-compliance-manager"></a>Introdução ao Gerenciador de conformidade

#### <a name="what-is-compliance-manager"></a>O que é gerente de conformidade

O [Gerenciador de conformidade](../compliance/compliance-manager.md) é uma ferramenta de avaliação de riscos baseada em fluxo de trabalho no centro de conformidade da Microsoft 365 para gerenciar atividades de conformidade normativa relacionadas aos serviços de nuvem da Microsoft. Como parte da sua assinatura do Microsoft 365 ou do Azure Active Directory (Azure AD), o Gerenciador de conformidade ajuda a gerenciar a conformidade normativa no modelo de responsabilidade compartilhada para os serviços de nuvem da Microsoft.

**Avaliações prontas para uso**

O Gerenciador de conformidade fornece modelos predefinidos para a [criação de avaliações](../compliance/compliance-manager-assessments.md) alinhadas às normas relacionadas à privacidade dos dados, como RGPD e HIPAA/alta tecnologia. Os modelos têm mapeamento de controle interno para ajudá-lo a tomar ações de melhoria para atender aos requisitos da regulamentação. Cada avaliação fornece informações sobre os controles que cada regulamentação chama para específico para o serviço de destino, dividida por controles que você gerencia e controla o Microsoft gerencia. 

O uso de um modelo predefinido ajuda você a começar rapidamente com as avaliações de risco. À medida que você se torna mais proficiente em usar o Gerenciador de conformidade, é possível personalizar um modelo predefinido adicionando seus próprios controles e ações de melhoria, ou você pode criar suas próprias avaliações personalizadas para atender às necessidades da sua organização.

Exibir a [lista completa de modelos de avaliação](../compliance/compliance-manager-templates-list.md) fornecidos pelo gerente de conformidade.

**Pontuação de conformidade em tempo real**

O Gerenciador de conformidade também fornece uma pontuação de conformidade que mede seu progresso ao concluir as ações de melhoria recomendadas nos controles. Você pode usar essa pontuação para ajudar a monitorar o progresso e Priorizar ações com base em seu potencial para reduzir o risco.

#### <a name="use-the-compliance-manager-quickstart-guide"></a>Usar o guia de início rápido do Gerenciador de conformidade

O guia de [início rápido do Gerenciador de conformidade](../compliance/compliance-manager-quickstart.md) fornece etapas graduadas e links para os principais recursos para ajudá-lo a trabalhar com o Gerenciador de conformidade:

- [Primeira visita: Familiarize-se com o gerente de conformidade](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - Trabalhar com o painel do Gerenciador de conformidade
    - Noções básicas sobre a pontuação de conformidade
    - Aprendendo sobre ações de melhoria
    - Noções básicas sobre avaliações e modelos
- [Crescimento: Configure o Gerenciador de conformidade para gerenciar suas atividades de conformidade](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - Criar e gerenciar sua primeira avaliação
    - Executar a implementação e testar o trabalho em ações de melhoria para concluir controles em suas avaliações
    - Entender como as diferentes ações impactam a pontuação de conformidade
- [Dimensionamento: Use a funcionalidade avançada para atender às suas necessidades personalizadas](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - Criando avaliações personalizadas para acompanhar produtos que não são da Microsoft 365
    - Modificando modelos existentes para adicionar ou remover controles
    - Configurando o teste automatizado de ações de melhoria

## <a name="how-your-compliance-score-is-calculated"></a>Como a pontuação de conformidade é calculada

Sua pontuação de conformidade é calculada com base em uma combinação de implementações de controle da Microsoft e do cliente gerenciado. Veja [cálculo da Pontuação de conformidade](../compliance/compliance-score-calculation.md) para obter uma explicação detalhada.

Os controles recebem um valor de pontuação com base no fato de serem obrigatórios ou discricionários, e se são preventivos, de detecção ou corretivas. Eles representam coletivamente o risco de não implementá-lo em relação a outros controles.

Conforme apresentado no artigo de cálculo da Pontuação de conformidade, os controles preventivos obtêm uma pontuação maior do que a detecção e correções, e os controles obrigatórios recebem uma pontuação maior do que aqueles discricionários.

A pontuação de conformidade o UI de administração não lista esses parâmetros nem oferece a capacidade de filtrá-los. No entanto, se você baixar o modelo associado do gerente de conformidade, o conjunto de dados resultante listará esses parâmetros para a maioria das regulamentações.

Para controles técnicos, o Gerenciador de conformidade atualiza automaticamente a pontuação de ação de melhoria após a ação ser implementada e testada com êxito. Outras ações de controle não-técnicos, como &mdash; as que são operacionais ou relacionadas à documentação &mdash; precisam ser registradas manualmente conforme implementadas antes da contagem de pontos em direção à sua pontuação.

Você também pode implementar algumas ações de aperfeiçoamento para outros fins &mdash; , por exemplo, usando os rótulos de retenção por razões diferentes da conformidade com a regulamentação de privacidade de dados &mdash; , para que você possa obter o crédito de usar esse recurso, mesmo que ele esteja sendo usado para outros fins, e não faça parte de uma ação de conformidade deliberada.

A pontuação de conformidade deve ser considerada uma medida relativa para acompanhar a melhoria em uma escala ampla. Você não deve buscar uma pontuação perfeita.

## <a name="additional-guidance"></a>Orientações adicionais

Aqui estão algumas dicas importantes para usar o Gerenciador de conformidade para ajudá-lo a obter conformidade com normas de privacidade de dados:

- Cada regulamentação de privacidade de dados tem uma combinação de controles técnicos, especificações de documentação e requisitos operacionais, de processo e de relatórios. Todos eles aparecem nas ações de melhoria.

- Para focalizar o modo de exibição de ações de aperfeiçoamento para a sua área de interesse, você pode filtrar por tipo de ação na guia **soluções** no administrador do Gerenciador de conformidade. Saiba mais sobre como [filtrar o modo de exibição do painel do Gerenciador de conformidade](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view).

- A importância relativa e a prioridade das ações de melhoria identificadas no gerente de conformidade devem ser consideradas como parte de uma análise de risco mais ampla, juntamente com o risco de privacidade dos dados que você determinou que sua organização precisa gerenciar.

- Mesmo com a agregação de ações de melhoria em vários requisitos regulatórios, se os modelos de avaliação da regulamentação para RGPD, LGPD, CCPA e HIPAA-alta são selecionados, por exemplo, quase 400 ações de melhoria serão listadas no Gerenciador de conformidade. Para resolver melhor essa lista extensa, use o filtro ação de melhoria para reduzir o conjunto de resultados para uma lista mais gerenciável.

- O filtro de categorias fornece um meio para filtrar ações de aperfeiçoamento por agrupamento lógico, que os artigos rastrear, evitar, proteger, reter e investigar nesta solução geral alinham-se a.

- Alguns dos controles listados nas ações de melhoria podem ser considerados mais diretamente vinculados a um artigo normativo específico, enquanto outros controles podem ser mais indiretamente associados ao espírito de uma regulamentação e muitas vezes são apenas atividades recomendadas ou práticas recomendadas.