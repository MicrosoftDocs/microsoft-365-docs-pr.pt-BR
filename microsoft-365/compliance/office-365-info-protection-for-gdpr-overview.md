---
title: Visão geral da Proteção de Informações do Office 365 para o GDPR
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Tenha uma visão geral da Proteção de Informações do Office 365 para o GDPR. Saiba como descobrir, classificar, proteger e monitorar dados pessoais.
ms.openlocfilehash: dbb420cce572b2e03260f9f5b1be63e65504276b
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42071150"
---
# <a name="overview-of-office-365-information-protection-for-gdpr"></a>Visão geral da Proteção de Informações do Office 365 para o GDPR

Esta solução demonstra como proteger dados confidenciais armazenados nos serviços do Office 365. Ela inclui recomendações prescritivas para a descoberta, a classificação, a proteção e o monitoramento de dados pessoais. Ela usa o GDPR (Regulamento Geral sobre Proteção de Dados) como exemplo, mas é possível aplicar o mesmo processo para estar em conformidade com vários outros regulamentos.

O GDPR regulamenta a coleta, o armazenamento, o processamento e o compartilhamento de dados pessoais. A grosso modo, o GDPR define dados pessoais como qualquer dado relativo a uma pessoa física identificada ou identificável que seja residente da União Europeia (UE).

Artigo 4 – Definições

> "dados pessoais" são todas as informações relativas a uma pessoa física identificada ou identificável ("titular dos dados"); uma pessoa física identificável é alguém que pode ser identificado, direta ou indiretamente, em especial por referência a um identificador como um nome, um número de identificação, dados de localização, um identificador online ou por um ou mais elementos específicos da identidade física, fisiológica, genética, mental, econômica, cultural ou social dessa pessoa física;

Essa solução se destina a ajudar as organizações a descobrir e proteger os dados pessoais no Office 365 que possam estar sujeitos ao GDPR, mas não é oferecida como uma comprovação de conformidade com o GDPR. A responsabilidade de garantir a conformidade com o GDPR é da própria organização e recomenda-se que ela consulte suas equipes jurídicas e de conformidade ou que busque orientação e consultoria de entidades terceiras especializadas em conformidade.

A [Avaliação do GDPR](https://www.microsoft.com/cyberassessment/en/gdpr/uso365?ls=Email&mkt_tok=eyJpIjoiTTJFeE5USXlOR1EwTWpJMiIsInQiOiJQTmdCYWR5NTlOd3JLWHZlb2NzNldKclQ4ZVBzVmhGeUhoUlFcL1pvSDIyXC9Ka05iTUR1aGpxT0YxQ0FUeGNDOUlkbWZLM1U4SUZWZmEyaGF6XC9ueUxkTHJzZnB3VDRMZlhPdkR4MzRLWkF5ckRNdWwxUkgzXC9yRU8yNkttSHhTb3VpZjNyVlJrNm9TTVZRYU5HR240a0FRPT0ifQ%3D%3D) é uma ferramenta online para uma autoavaliação rápida e sem custo para ajudar sua organização a analisar o nível geral de preparação para cumprir com o GDPR.

## <a name="assess-and-manage-your-compliance-risk"></a>Avaliar e gerenciar o risco de conformidade

A primeira etapa para estar em conformidade com o GDPR é avaliar se ele se aplica à sua organização e, em caso afirmativo, até que ponto. Essa análise inclui entender os dados que a sua organização processa e onde estão localizados.

### <a name="step-1--use-compliance-score-to-view-the-regulation-requirements-and-track-your-progress"></a>Etapa 1: usar a Pontuação de Conformidade para exibir as exigências regulatórias e acompanhar o progresso

A Pontuação de Conformidade fornece ferramentas para acompanhar, implementar e gerenciar os controles de auditoria para ajudar sua organização a estar em conformidade com vários padrões, incluindo o GDPR.

![Use a Pontuação de Conformidade e o Gerenciador de Conformidade para exibir as exigências e acompanhar o progresso](../media/Overview-image1.png)

Para saber mais, consulte os [pontuação de conformidade](compliance-score.md).

### <a name="step-2--use-content-search-and-sensitive-information-types-to-find-personal-data"></a>Etapa 2: usar a Pesquisa de Conteúdo e os tipos de informações confidenciais para encontrar dados pessoais 

Descubra os dados pessoais em seu ambiente que estão sujeitos ao GDPR. Use a Pesquisa de Conteúdo em conjunto com os tipos de informações confidenciais para:

- Localizar e gerar relatórios sobre a localização dos dados pessoais.

- Otimizar os tipos de dados confidenciais e outras consultas para localizar todos os dados pessoais em seu ambiente.

![Use a Pesquisa de Conteúdo e os tipos de informações confidenciais para encontrar dados pessoais](../media/Overview-image2.png)

Os tipos de informações confidenciais definem como o processo automatizado reconhecerá os tipos de informações específicas, como os números de serviço de saúde e de cartões de crédito. Este artigo inclui um conjunto que você pode usar como ponto de partida. Vários outros tipos de informações confidenciais chegarão em breve para os dados pessoais de países da UE.

Para mais informações, confira [Pesquisar e encontrar dados pessoais](search-for-and-find-personal-data.md). 

## <a name="classify-protect-and-monitor-personal-data-in-office-365-and-other-saas-apps"></a>Classificar, proteger e monitorar dados pessoais no Office 365 e em outros aplicativos SaaS

Alguns dos recursos usados para a proteção de informações do Office 365 também podem ser usados para proteger dados confidenciais em outros aplicativos SaaS.

![Classificar, proteger e monitorar dados pessoais](../media/Overview-image3.png)

Esta ilustração é descrita pelo restante desta seção (etapas 3 a 5).

### <a name="step-3--decide-if-you-want-to-use-labels-in-addition-to-sensitive-information-types"></a>Etapa 3: decidir se você deseja usar rótulos junto com os tipos de informações confidenciais

Os tipos de informações confidenciais são uma forma de classificação. Confira [Projetar um esquema de classificação de dados pessoais](architect-a-classification-schema-for-personal-data.md) para decidir se você também deseja implementar rótulos. Para aplicar rótulos, confira [Aplicar rótulos a dados pessoais no Office 365](apply-labels-to-personal-data-in-office-365.md).

Na ilustração, os rótulos e tipos de informações confidenciais funcionam em todo o Office 365. Em breve, será possível usá-los com o Cloud App Security para localizar dados confidenciais em outros aplicativos SaaS, como o Box e o Salesforce.

### <a name="step-4--protect-personal-data-in-office-365"></a>Etapa 4: proteger dados pessoais no Office 365 

A proteção de dados pessoais começa com a prevenção contra perda de dados do Office 365. Há vários outros recursos recomendados para proteger o acesso aos dados pessoais, incluindo a Criptografia de Mensagens do Office 365 para email.

Essas proteções podem ser direcionadas para conjuntos de dados específicos:

- Permissões de nível de site e de biblioteca

- Políticas de compartilhamento externo de nível de site

- Políticas de acesso de dispositivo no nível do site

A proteção de acesso ao Office 365 e a outros serviços de nuvem incluem:

- Proteção à identidade e ao acesso a dispositivos no Enterprise Mobility + Security (EMS)

- Gerenciamento de acesso privilegiado

- Recursos de segurança do Windows 10

Confira mais informações sobre como [Aplicar proteção a dados pessoais no Office 365](apply-protection-to-personal-data-in-office-365.md).

### <a name="step-5--monitor-for-leaks-of-personal-data"></a>Etapa 5: monitorar o vazamento de dados pessoais

Os relatórios de prevenção contra perda de dados do Office 365 oferecem o mais alto nível de detalhamento para o monitoramento de dados confidenciais. É possível configurar alertas automatizados e investigar violações usando o log de auditoria do Office 365. O Cloud App Security estende a outros provedores SaaS a capacidade de localizar e monitorar dados confidenciais. Consulte mais informações sobre essas ferramentas em [Monitorar violações de dados pessoais](/security/office-365-security/monitor-for-leaks-of-personal-data.md).
