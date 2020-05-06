---
title: Pontuação de conformidade da Microsoft
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
description: A pontuação de conformidade da Microsoft ajuda as organizações a simplificar e automatizar avaliações de riscos e sugere ações recomendadas para ajudar a lidar com riscos.
ms.openlocfilehash: 507ff021095dfc0b18cffb6db313009c22ad2693
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046269"
---
# <a name="microsoft-compliance-score-preview"></a>Pontuação de conformidade da Microsoft (visualização)

A [Pontuação de conformidade da Microsoft](https://compliance.microsoft.com/compliancescore) ajuda a simplificar a forma como você gerencia a conformidade e reduz os riscos de conformidade por meio de uma experiência amigável. A pontuação de conformidade está disponível para visualização pública no [centro de conformidade da Microsoft 365](microsoft-365-compliance-center.md).

**Neste artigo:** Leia este artigo para entender qual é a pontuação de conformidade e como configurá-lo para sua organização.

**Saiba mais sobre as atualizações:** Publicamos várias atualizações na versão de abril de 2020. Visite as [notas de versão da Pontuação de conformidade](compliance-score-release-notes.md) para ver as novidades e os problemas conhecidos da versão prévia da Pontuação de conformidade.

## <a name="what-is-compliance-score"></a>O que é a pontuação de conformidade

A pontuação de conformidade da Microsoft é um recurso de visualização no centro de conformidade da Microsoft 365 para ajudá-lo a entender a postura de conformidade da sua organização. Ele calcula uma pontuação baseada em risco medindo seu progresso em ações de conclusão que ajudam a reduzir os riscos relacionados à proteção de dados e aos padrões normativos.

Você pode usar a pontuação de conformidade como uma ferramenta para rastrear todas as avaliações de risco. Ele fornece recursos de fluxo de trabalho para ajudá-lo a concluir com eficiência as avaliações de riscos por meio de uma ferramenta comum.

Se você usa o [gerente de conformidade](compliance-manager-overview.md)no momento, notará que a pontuação de conformidade agora é um recurso autônomo com um design mais simples e fácil de usar para ajudá-lo a gerenciar a conformidade com mais facilidade. 

A página principal de Pontuação de conformidade é seu painel personalizado. Ele mostra sua pontuação atual, ajuda a ver o que precisa de atenção e orienta as ações para melhorar sua pontuação. Seu painel de Pontuação de conformidade terá a seguinte aparência:

![Pontuação de conformidade-painel](../media/compliance-score-dashboard.png "Painel de Pontuação de conformidade")

### <a name="simplified-compliance-management"></a>Gerenciamento de conformidade simplificado

A pontuação de conformidade ajuda a simplificar o gerenciamento de conformidade fornecendo:

- **Avaliações contínuas**: examina automaticamente seus ambientes Microsoft 365 para detectar e monitorar a eficácia dos controles de proteção de dados em seu sistema
- **Ações recomendadas**: oferece recomendações e orientações passo a passo sobre como implementar controles para maximizar sua pontuação
-  **Mapeamento de controle interno**: ajuda você a se manter atualizado com o panorama de conformidade em evolução, fornecendo uma estrutura de controle comum incorporada

> [!IMPORTANT]
> As recomendações da Pontuação de conformidade e do Gerente de conformidade não devem ser interpretadas como garantia de conformidade. Você pode avaliar e validar a eficácia dos controles de clientes por seu ambiente normativo. Esses serviços estão atualmente em versão prévia e sujeitos aos termos e condições nos [termos dos serviços online](https://go.microsoft.com/fwlink/?linkid=2108910). Confira também [orientações de licenciamento da Microsoft 365 para segurança e conformidade](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="relationship-to-compliance-manager"></a>Relação com o Gerenciador de conformidade

Considere a pontuação de conformidade como uma versão simplificada do Gerenciador de conformidade. Embora os dois existam como ferramentas distintas ainda integradas, a pontuação de conformidade facilita o monitoramento de sua postura geral de conformidade e a tomada de etapas para melhorá-lo.

A pontuação de conformidade compartilha o mesmo backend com o gerente de conformidade, portanto, qualquer dado que você já tenha no Gerenciador de conformidade será exibido na pontuação de conformidade.

Algumas funcionalidades permanecem exclusivamente no Gerenciador de conformidade durante a visualização pública, como o gerenciamento de avaliações e a criação de modelos. Recomendamos iniciar todas as atividades de gerenciamento de conformidade na pontuação de conformidade. Ao chegar às funções tratadas pelo gerente de conformidade, você será orientado para essa ferramenta. Por esse motivo, parte desta documentação direciona você aos tópicos do gerente de conformidade.

Saiba mais sobre a relação entre a pontuação de conformidade e o gerente de conformidade nas [notas de versão de nota de conformidade](compliance-score-release-notes.md).

## <a name="understanding-your-score"></a>Noções básicas sobre sua pontuação

A pontuação de conformidade fornece uma pontuação inicial com base na linha de base de proteção de dados da Microsoft 365. Essa linha de base é um conjunto de controles que inclui padrões e normas comuns do setor. Embora essa pontuação seja um bom ponto de partida para avaliar sua postura de conformidade, a pontuação de conformidade torna-se mais poderosa depois que você adiciona avaliações que sejam mais relevantes para sua organização.

Por exemplo, se sua organização pertencer ao setor de serviços financeiros, talvez você queira adicionar a avaliação do FFIEC. Se sua organização pertencer ao setor de saúde, você poderá adicionar a avaliação HIPAA/alta tecnologia. Saiba como [Adicionar avaliações no Gerenciador de conformidade](working-with-compliance-manager.md#assessments).

Saiba mais sobre [como a pontuação de conformidade é calculada e continuamente monitorada](compliance-score-methodology.md).


## <a name="key-components-controls-assessments-templates-groups"></a>Principais componentes: controles, avaliações, modelos, grupos

A pontuação de conformidade usa vários componentes para ajudá-lo a gerenciar suas atividades de conformidade. À medida que você usa a pontuação de conformidade para atribuir, testar e monitorar atividades de conformidade, é útil ter uma compreensão básica dos principais componentes: controles, avaliações, modelos e grupos.

### <a name="controls"></a>Controles

Um controle define como avaliar e gerenciar a configuração do sistema, o processo organizacional e as pessoas responsáveis por atender a um requisito específico de uma política regulamentar, padrão ou interna.

A pontuação de conformidade controla dois tipos de controles:

1. **Controles gerenciados pela Microsoft**: controles para serviços de nuvem da Microsoft, que a Microsoft é responsável por implementar
2. **Controles gerenciados pelo cliente**: controles gerenciados pela sua organização, que você é responsável por implementar
 
### <a name="assessments"></a>Avaliações

Uma avaliação é uma avaliação de um modelo que inicia o processo de Pontuação para sua organização. O grupo de avaliações as ações necessárias para atender aos requisitos de um padrão, regulamento ou legislação. Por exemplo, você pode ter uma avaliação que, quando concluir todas as ações dentro dela, traz suas configurações do Office 365 em linha com os requisitos ISO 27001.

A pontuação de conformidade fornece à sua organização uma avaliação inicial baseada na linha de base de proteção de dados do Microsoft 365. Essa avaliação é uma recomendação para reduzir os riscos de proteção de dados e conformidade ([saiba mais](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)).

As avaliações têm vários componentes:

- **Serviços no escopo**: o conjunto específico de serviços Microsoft aplicável à avaliação
- **Controles gerenciados**pela Microsoft: controles que a Microsoft implementou e testou
- **Controles gerenciados pelo cliente**: controles que você gerencia
- **Pontuação de avaliação**: a porcentagem dos pontos alcançados por meio da conclusão de ações dentro dessa avaliação

> [!NOTE]
> A pontuação de conformidade exibe as avaliações e como elas fatoram em sua pontuação geral. No entanto, durante a visualização pública, você será direcionado ao Gerenciador de conformidade para gerenciar as avaliações.

Exibir instruções detalhadas para [gerenciar avaliações no Gerenciador de conformidade](working-with-compliance-manager.md#assessments).

### <a name="templates"></a>Modelos

A pontuação de conformidade fornece modelos pré-configurados para avaliações. Você também pode personalizar um modelo pré-configurado adicionando seus próprios controles e ações. Por exemplo, você pode criar um modelo para seu controle de processo de negócios ou um modelo para uma proteção de dados regional ou padrão de conformidade que não esteja coberto por um dos modelos pré-configurados. Ao trazer seus próprios modelos para a pontuação de conformidade, você pode controlar não apenas avaliações da nuvem da Microsoft, mas também qualquer outra avaliação de risco no escopo da sua organização.

Os modelos pré-configurados de Pontuação de conformidade são:

1. [Lei de proteção de dados gerais do Brasil (LGPD)](https://go.microsoft.com/fwlink/?linkid=2115387)
2. [Lei de privacidade do consumidor da Califórnia (CCPA)](https://go.microsoft.com/fwlink/?linkid=2108871) (visualização)
3. [A matriz de controles de nuvem CSA (Cloud Security Alliance) 3.0.1](https://go.microsoft.com/fwlink/?linkid=2109076)
4. [RGPD de União Européia](https://go.microsoft.com/fwlink/?linkid=2108870)
5. [Folheto de segurança de informações do FFIEC Financial Federals (Conselho de análise de instituições financeiras)](https://go.microsoft.com/fwlink/?linkid=2109077)
6. [FedRAMP moderado](https://go.microsoft.com/fwlink/?linkid=2108869)
7. [HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078) / de[alta tecnologia](https://go.microsoft.com/fwlink/?linkid=2109079)
8. [IRAP](https://go.microsoft.com/fwlink/?linkid=2113709) / [ISM do governo Australian](https://go.microsoft.com/fwlink/?linkid=2113024) IRAP (versão prévia)
9. [ISO 27001:2013](https://go.microsoft.com/fwlink/?linkid=2109073)
10. [ISO 27018:2014](https://go.microsoft.com/fwlink/?linkid=2109074)
11. [ISO 27701:2019](https://go.microsoft.com/fwlink/?linkid=2113025)
12. [Linha de base de proteção de dados 365 da Microsoft](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)
13. [NIST 800-53 Rev. 4](https://go.microsoft.com/fwlink/?linkid=2109075)
14. [NIST 800-171](https://go.microsoft.com/fwlink/?linkid=2108867)
15. [Estrutura NIST cybersecurity (CSF)](https://go.microsoft.com/fwlink/?linkid=2108868)
16. [SOC 1](https://go.microsoft.com/fwlink/?linkid=2115184)
17. [SOC 2](https://go.microsoft.com/fwlink/?linkid=2115184)

Exibir [instruções detalhadas para a criação de modelos](working-with-compliance-manager.md#templates), que ocorre no Gerenciador de conformidade.

### <a name="groups"></a>Grupos

Os grupos permitem organizar avaliações de forma que seja lógica para você. Por exemplo, você pode optar por agrupar avaliações por ano, padrão de conformidade, serviço, equipes dentro da sua organização ou de alguma outra maneira.

Quando duas avaliações diferentes no mesmo grupo compartilham ações gerenciadas pelo cliente, as atualizações feitas nos detalhes da implementação, teste e status da ação em uma avaliação serão automaticamente sincronizadas com a mesma ação em qualquer outra avaliação do grupo. A sincronização de ações dessa forma unifica as ações de melhoria atribuídas no grupo e reduz o trabalho de duplicação.

Saiba como [criar grupos no Gerenciador de conformidade](working-with-compliance-manager.md#groups). Depois de criar grupos, você pode [filtrar o painel de Pontuação de conformidade](compliance-score-setup.md#filtering-your-dashboard-view) para exibir sua pontuação por um ou mais grupos.

## <a name="next-step-begin-setup"></a>Próxima etapa: iniciar a instalação

Saiba como entrar, configurar permissões e configurar atualizações e modos de exibição de painel na [configuração de Pontuação de conformidade](compliance-score-setup.md).
