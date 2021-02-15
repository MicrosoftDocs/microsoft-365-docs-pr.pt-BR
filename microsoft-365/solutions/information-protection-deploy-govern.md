---
title: Governe informações sujeitas à regulamentação de privacidade de dados
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
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
description: Use rótulos e políticas de retenção do Microsoft 365 para gerenciar dados pessoais em seu ambiente do Microsoft 365.
ms.openlocfilehash: c2a933e556213ae4b78db9dc5f903885df969b27
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377040"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a>Governe informações sujeitas à regulamentação de privacidade de dados

Os controles de governança de informações podem ser empregados em seu ambiente para ajudar a atender às necessidades de conformidade de privacidade de dados, incluindo um número específico do RGPD (Regulamento Geral sobre a Proteção de Dados), HIPAA-HITECH (lei de privacidade de saúde dos Estados Unidos), Lei de Proteção do Consumidor da Califórnia (CCPA) e LGPD (Lei de Proteção de Dados do Brasil). 

Esses controles se enquadram principalmente nas seguintes áreas de solução:

- Diretivas de retenção
- Rótulos de retenção
- Gerenciamento de registros

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a>Regulamentos de privacidade de dados que estão afetando os controles de governança de informações

Aqui está um exemplo de listagem de regulamentações de privacidade de dados que podem estar relacionadas a controles de governança de informações:

- Artigo RGPD (13)(2)(a)
- Artigo RGPD (5)(1)(f)
- HIPAA-HITECH (45 CFR 164.312(c)(2))
- HIPAA-HITECH (45 CFR 164.316(b)(1)(i))
- HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))
- Artigo 46 do LGPD

Para obter mais informações sobre essas regulamentações, consulte o artigo avaliar os riscos de privacidade de dados e [identificar informações confidenciais.](information-protection-deploy-assess.md)

Para governança de informações, as regulamentações de privacidade de dados normalmente chamam o seguinte:

- Você deve empregar um esquema técnico para retenção e exclusão de dados pessoais armazenados no Microsoft 365.
- Se você for armazenar dados pessoais, informe ao assunto por quanto tempo os dados serão armazenados, o que é uma prática padrão agora em sistemas web front-end.
- Os dados pessoais devem ser protegidos contra processamento acidental, perda ou alteração usando métodos verificáveis.
- Qualquer ação executada em relação a dados pessoais deve ser documentada e essa documentação deve ser retida por um período especificado.

Como as regulamentações de privacidade de dados não são muito específicas quando se trata de retenção e exclusão de dados, outros fatores precisam ser levados em consideração que podem ditar diretrizes de governança de informações para informações pessoais armazenadas em sua assinatura do Microsoft 365. Aqui estão alguns exemplos:

- O apagamento de contas de consumidor após 5 anos de inatividade e exige a exclusão ou o anonimato dos dados da conta depois desse ponto, exigindo a orquestração entre o sistema que armazenará os dados e os fluxos de trabalho relacionados a notificações e outras automações.
- Configuração de regras para manter políticas e procedimentos relacionados ao RGPD por três anos após a superação, que se alinha com o cronograma de retenção da organização para políticas e procedimentos.
- Manter uma assinatura separada para se comunicar com os consumidores por meio de sua organização de suporte. Todas as comunicações por email foram retidas e excluídas após duas semanas para reduzir qualquer acúmulo de débitos de privacidade no sistema.

Uma pergunta importante a responder é: 

- Por quanto tempo as informações que contêm dados pessoais precisam ser mantidas por motivos comerciais válidos para evitar práticas "mantê-la para sempre"? Isso deve ser balanceado com as necessidades de retenção para a continuidade dos negócios.

Independentemente dos motivos legais e comerciais para manter informações pessoais ou excluí-los, a Microsoft fornece vários recursos para implementar seu esquema de governança de dados no Microsoft 365.

## <a name="managing-information-governance-in-microsoft-365"></a>Gerenciando a governança de informações no Microsoft 365

Para começar, confira [Gerenciar governança de informações](../compliance/manage-information-governance.md) e retenção, exclusão e destruição de dados no Microsoft [365.](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a>Desenvolver agendamentos de retenção de dados para contêineres, email e conteúdo

Lembre-se do seguinte:

- Estabelecer um cronograma de retenção de dados para tipos de informações definidos deve ser considerado um pré-requisito para implementar qualquer esquema de retenção ou exclusão.

- Considerando o número de tipos de informações que a maioria das organizações considera importantes e os agendamentos de retenção de registros grandes correspondentes que acompanham eles, implementar uma estratégia de gerenciamento de registros e retenção de dados requer planejamento. 

- A chave para estabelecer uma estratégia eficaz de governança de dados desse tipo é focar nas funções comerciais de prioridade mais alta e nos tipos de informações que exigem um gerenciamento mais formal. Exemplos são contratos legais, extratos financeiros e documentação de conformidade regulatória. Tente evitar ter um agendamento de retenção separado para cada tipo de informação. Tente utilizar categorias gerais o máximo possível, por exemplo, com agendamentos de retenção de 7 anos para conteúdo comercial geral.

- Depois que os tipos de informações pessoais em seu ambiente são mais conhecidos, estabeleça agendas de retenção e exclusão para esse tipo de conteúdo e ajuste sua arquitetura de informações para facilitar a governança desse tipo de informação. Por exemplo, isole informações pessoais em sites, bibliotecas ou pastas separados com acesso controlado.

### <a name="retention-policies-and-retention-labels"></a>Políticas de retenção e rótulos de retenção

Use [políticas de retenção e rótulos de](../compliance/retention.md) retenção para reter ou excluir conteúdo no Microsoft 365 que contenha ou que contenha dados pessoais.

### <a name="records-management"></a>Gerenciamento de registros

Use rótulos de retenção que declarem um registro de conteúdo para implementar uma solução [de gerenciamento](../compliance/records-management.md) de registros para dados no Microsoft 365.

Para a privacidade de dados, as solicitações de entidades de dados (DSRs) recebidas pelo departamento jurídico são declaradas um registro e podem ser armazenadas indefinidamente ou descartadas com prova, para cumprir as especificações de retenção de atividades regulamentares.

