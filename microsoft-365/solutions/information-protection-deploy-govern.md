---
title: Controlar informações sujeitas à regulamentação de privacidade de dados
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
- M365solutions
ms.custom: ''
description: Use os rótulos e políticas de retenção da Microsoft 365 para gerenciar dados pessoais no seu ambiente do Microsoft 365.
ms.openlocfilehash: 4c65eafa167d7224c4022d5634ce089952fada19
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695156"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a>Controlar informações sujeitas à regulamentação de privacidade de dados

Os controles de governança de informações podem ser empregados no seu ambiente para ajudar a atender às necessidades de conformidade de privacidade de dados, incluindo um número específico da regulamentação geral de proteção de dados (RGPD), HIPAA-alta (o ato de privacidade do atendimento de saúde dos Estados Unidos), lei de proteção para consumidores da Califórnia (CCPA) e o decreto de proteção de dados Brasil (LGPD). 

Esses controles basicamente enquadram-se nas seguintes áreas de solução:

- Diretivas de retenção
- Rótulos de retenção
- Gerenciamento de registros

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a>Regulamentações de privacidade de dados que afetam os controles de governança de informações

Aqui está uma lista de exemplos de regulamentos de privacidade de dados que podem se relacionar aos controles de governança de informações:

- RGPD artigo (13) (2) (a)
- RGPD artigo (5) (1) (f)
- HIPAA-alta (45 CFR 164.312 (c) (2))
- HIPAA-alta (45 CFR 164.316 (b) (1) (i))
- HIPAA-alta (45 CFR 164.316 (b) (1) (II))
- LGPD artigo 46

Para obter mais informações sobre essas regulamentações, consulte o [artigo sobre como avaliar riscos de privacidade de dados e identificar informações confidenciais](information-protection-deploy-assess.md).

Para o controle de informações, as regulamentações de privacidade de dados normalmente chamam o seguinte:

- Você deve empregar um esquema técnico para retenção e exclusão de dados pessoais armazenados no Microsoft 365.
- Se você for armazenar dados pessoais, informe o assunto sobre quanto tempo os dados serão armazenados, que é uma prática padrão agora em sistemas Web front-end.
- Dados pessoais devem ser protegidos contra processamento acidental, perda ou alteração usando métodos verificáveis.
- Qualquer ação executada em relação a dados pessoais deve ser documentada e essa documentação deve ser mantida por um período especificado.

Como as leis de privacidade de dados não são muito específicas quando se trata de retenção e exclusão de dados, outros fatores precisam ser levados em consideração que podem ditar as diretrizes de controle de informações para informações pessoais armazenadas na sua assinatura do Microsoft 365. Estes são alguns exemplos:

- Expirar as contas de consumo após 5 anos de inatividade e requer a exclusão ou a anonimato dos dados da conta após esse ponto, exigindo orquestração entre o sistema que armazena os dados e fluxos de trabalho relacionados a notificações e outras automação.
- Configurar regras para manter políticas e procedimentos relacionados ao RGPD por três anos após terem sido substituídos, que se alinham com o agendamento de retenção da organização para políticas e procedimentos.
- Manter uma assinatura separada para comunicação com os consumidores por meio de sua organização de suporte. Todas as comunicações de email foram mantidas e excluídas após duas semanas para reduzir qualquer dívida de privacidade no sistema.

Uma pergunta importante a ser respondida é: 

- Quanto tempo as informações que contêm dados pessoais precisam ser mantidas por razões de negócios válidas para evitar as práticas de "mantê-lo para sempre"? Isso deve ser balanceado com as necessidades de retenção para continuidade de negócios.

Independentemente das razões legais e comerciais para manter informações pessoais ou excluí-las, a Microsoft fornece vários recursos para implementar o esquema de governança de dados no Microsoft 365.

## <a name="managing-information-governance-in-microsoft-365"></a>Gerenciando o controle de informações no Microsoft 365

Para começar, consulte [gerenciar governança de informações](../compliance/manage-information-governance.md) e [retenção de dados, exclusão e destruição no Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a>Desenvolver agendas de retenção de dados para contêineres, emails e conteúdo

Lembre-se do seguinte:

- O estabelecimento de um agendamento de retenção de dados para tipos de informações definidos deve ser considerado um pré-requisito para implementar qualquer esquema de retenção ou de exclusão.

- Dado o número de tipos de informação que a maioria das organizações considera importantes e os cronogramas de retenção de registros grandes correspondentes que vão junto com eles, a implementação de uma estratégia de retenção de dados e gerenciamento de registros requer planejamento. 

- A chave para estabelecer uma estratégia de governança de dados efetiva desse tipo é focar nas funções de negócios de prioridade mais alta e os tipos de informações que exigem gerenciamento mais formal. Os exemplos são contratos legais, demonstrativos financeiros e documentação de conformidade normativa. Tente evitar ter um agendamento de retenção separado para cada tipo de informação único. Tente utilizar categorias gerais o máximo possível, por exemplo, com agendas de retenção de sete anos para conteúdo de negócios em geral.

- Depois que os tipos de informações pessoais no ambiente são mais conhecidos, estabeleça agendas de retenção e exclusão para esse tipo de conteúdo e ajuste sua arquitetura de informações para facilitar a governança desse tipo de informação. Por exemplo, isole informações pessoais em sites, bibliotecas ou pastas separadas com acesso controlado.

### <a name="retention-policies"></a>Políticas de retenção

Criar e implantar [políticas de retenção](../compliance/retention-policies.md) para conteúdo em sites que são automaticamente aplicados.

Para privacidade de dados de sites que contenham ou que devam conter dados pessoais, especifique regras de retenção ou exclusão para lidar com padrões organizacionais.

### <a name="retention-labels"></a>Rótulos de retenção

Criar e implantar [Rótulos de retenção](../compliance/labels.md) para conteúdo e email.

Para privacidade de dados de sites, bibliotecas, pastas e emails que contêm ou que devem conter dados pessoais, especifique regras de retenção ou exclusão automáticas para lidar com padrões organizacionais.

### <a name="records-management"></a>Gerenciamento de registros

Criar e implantar rótulos de retenção para gerenciamento de registros com base em um agendamento de retenção de registros e plano de arquivo.

Para a privacidade dos dados, as solicitações de entidades de dados (DSRs) recebidas pelo departamento jurídico são declaradas como um registro e armazenadas indefinidamente para aderir às especificações de retenção de atividade regulamentar.

Consulte estes recursos para obter mais informações: 

- [Gerenciamento de Registros](../compliance/records-management.md)
- [Gerenciador de planos de arquivo](../compliance/file-plan-manager.md)
- [Retenção baseada em eventos para gerenciamento de registros](../compliance/automate-event-driven-retention.md)
- [Disposição do conteúdo](../compliance/disposition-reviews.md)
