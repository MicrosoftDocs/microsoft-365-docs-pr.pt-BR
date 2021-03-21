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
ms.openlocfilehash: 62c2386ac8f9c5b31650df8be2c2a411d8b75959
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928431"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a>Governe informações sujeitas à regulamentação de privacidade de dados

Os controles de governança de informações podem ser empregados em seu ambiente para ajudar a atender às necessidades de conformidade de privacidade de dados, incluindo um número específico do RGPD (Regulamento Geral de Proteção de Dados), HIPAA-HITECH (a lei de privacidade de saúde dos Estados Unidos), a Lei de Proteção do Consumidor da Califórnia (CCPA) e a Lei de Proteção de Dados do Brasil (LGPD). 

Esses controles se enquadram principalmente nas seguintes áreas de solução:

- Diretivas de retenção
- Rótulos de retenção
- Gerenciamento de registros

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a>Regulamentos de privacidade de dados que impactam controles de governança de informações

Aqui está um exemplo de listagem de regulamentos de privacidade de dados que podem estar relacionados aos controles de governança de informações:

- Artigo RGPD (13)(2)(a)
- Artigo RGPD (5)(1)(f)
- HIPAA-HITECH (45 CFR 164.312(c)(2))
- HIPAA-HITECH (45 CFR 164.316(b)(1)(i))
- HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))
- Artigo 46 do LGPD

Para obter mais informações sobre esses regulamentos, consulte o artigo avaliar riscos de privacidade de dados e [identificar informações confidenciais.](information-protection-deploy-assess.md)

Para governança de informações, os regulamentos de privacidade de dados normalmente chamam o seguinte:

- Você deve empregar um esquema técnico para retenção e exclusão de dados pessoais armazenados no Microsoft 365.
- Se você vai armazenar dados pessoais, informe o assunto de quanto tempo os dados serão armazenados, que é uma prática padrão agora em sistemas Web front-end.
- Os dados pessoais devem ser protegidos contra processamento acidental, perda ou alteração usando métodos verificáveis.
- Qualquer ação executada contra dados pessoais deve ser documentada e essa documentação deve ser mantida por um período especificado.

Como os regulamentos de privacidade de dados não são muito específicos quando se trata de retenção e exclusão de dados, outros fatores precisam ser considerados que podem ditar diretrizes de governança de informações para informações pessoais armazenadas em sua assinatura do Microsoft 365. Veja alguns exemplos:

- O apagamento das contas de consumidor após 5 anos de inatividade e requer exclusão ou anonimização dos dados da conta após esse ponto, exigindo a orquestração entre o sistema que armazenará os dados e fluxos de trabalho relacionados a notificações e outras automações.
- Configurar regras para manter políticas e procedimentos relacionados ao RGPD por três anos após a superação, que se alinha ao cronograma de retenção da organização para políticas e procedimentos.
- Mantendo uma assinatura separada para se comunicar com os consumidores por meio de sua organização de suporte. Todas as comunicações de email foram mantidas e excluídas após duas semanas para reduzir qualquer acúmulo de dívidas de privacidade no sistema.

Uma pergunta importante a ser respondeda é: 

- Por quanto tempo as informações que contêm dados pessoais precisam ser mantidas por motivos comerciais válidos para evitar práticas de "mantê-los para sempre"? Isso deve ser balanceado com as necessidades de retenção para a continuidade dos negócios.

Independentemente dos motivos legais e comerciais para manter informações pessoais ou excluí-los, a Microsoft fornece vários recursos para implementar seu esquema de governança de dados no Microsoft 365.

## <a name="managing-information-governance-in-microsoft-365"></a>Gerenciando a governança de informações no Microsoft 365

Para começar, consulte [Manage information governance and](../compliance/manage-information-governance.md) Data [Retention, Deletion and Destruction in Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a>Desenvolver agendamentos de retenção de dados para contêineres, email e conteúdo

Lembre-se do seguinte:

- O estabelecimento de um cronograma de retenção de dados para tipos de informações definidos deve ser considerado um pré-requisito para implementar qualquer esquema de retenção ou exclusão.

- Dado o número de tipos de informações que a maioria das organizações considera importantes e os agendamentos de retenção de registros grandes correspondentes que acompanham eles, implementar uma estratégia de gerenciamento de registros e retenção de dados requer planejamento. 

- A chave para estabelecer uma estratégia eficaz de governança de dados desse tipo é se concentrar nas funções comerciais de maior prioridade e nos tipos de informações que exigem gerenciamento mais formal. Exemplos são contratos legais, demonstrações financeiras e documentação de conformidade regulamentar. Tente evitar ter um cronograma de retenção separado para cada tipo de informação. Tente utilizar categorias gerais o máximo possível, por exemplo, com agendamentos de retenção de 7 anos para conteúdo comercial geral.

- Depois que os tipos de informações pessoais em seu ambiente são mais conhecidos, estabeleça cronogramas de retenção e exclusão para esse tipo de conteúdo e ajuste sua arquitetura de informações para facilitar a governança desse tipo de informação. Por exemplo, isole informações pessoais em sites, bibliotecas ou pastas separados com acesso controlado.

### <a name="retention-policies-and-retention-labels"></a>Políticas de retenção e rótulos de retenção

Use [políticas de retenção e rótulos](../compliance/retention.md) de retenção para reter ou excluir conteúdo no Microsoft 365 que contém ou deve conter dados pessoais.

### <a name="records-management"></a>Gerenciamento de registros

Use rótulos de retenção que declarem um registro de conteúdo para implementar [uma](../compliance/records-management.md) solução de gerenciamento de registros para dados no Microsoft 365.

Para privacidade de dados, as solicitações de entidades de dados (DSRs) recebidas pelo departamento jurídico são declaradas um registro e podem ser armazenadas indefinidamente ou descartadas com prova, para aderir às especificações de retenção de atividades regulamentares.