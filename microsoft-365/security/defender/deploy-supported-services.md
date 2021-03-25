---
title: Implantar serviços com suporte do Microsoft 365 Defender
description: Saiba mais sobre os serviços de segurança da Microsoft que podem ser integrados pelo Microsoft 365 Defender, seus requisitos de licenciamento e procedimentos de implantação
keywords: implantar, licenças, serviços com suporte, provisionamento, configuração Microsoft Threat Protection, M365, qualificação de licença, Microsoft Defender ATP, MDATP, Office 365 ATP, Azure ATP, Microsoft Cloud App Security, MCAS, proteção avançada contra ameaças, E5, A5, EMS
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 434c318be404ffb04cac7a05664c8f001bb46507
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198856"
---
# <a name="deploy-supported-services"></a>Implantar serviços com suporte

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[O Microsoft 365 Defender](microsoft-365-defender.md) integra vários serviços de segurança da Microsoft para fornecer recursos centralizados de detecção, prevenção e investigação contra ataques sofisticados. Este artigo descreve os serviços com suporte, seus requisitos de licenciamento, as vantagens e limitações associadas à implantação de um ou mais serviços e links para como você pode implantá-los totalmente individualmente.

## <a name="supported-services"></a>Serviços com suporte
Uma licença de Segurança do Microsoft 365 E5, E5, A5 ou A5 ou uma combinação válida de licenças fornece acesso aos seguintes serviços com suporte e permite que você use o Microsoft 365 Defender no Centro de segurança do Microsoft 365. [Consulte requisitos de licenciamento](prerequisites.md#licensing-requirements)

| Serviço com suporte | Descrição |
| ------ | ------ |
| Microsoft Defender para Ponto de Extremidade | Pacote de proteção de ponto de extremidade criado em torno de sensores comportamentais poderosos, análise de nuvem e inteligência contra ameaças |
|Microsoft Defender para Office 365 | Proteção avançada para seus aplicativos e dados no Office 365, incluindo email e outras ferramentas de colaboração |
| Microsoft Defender para Identidade? | Defender contra ameaças avançadas, identidades comprometidas e insiders mal-intencionados usando sinais correlacionados do Active Directory |
| Microsoft Cloud App Security | Identificar e combater ameaças cibernéticas em seus serviços de nuvem da Microsoft e de terceiros |

## <a name="deployed-services-and-functionality"></a>Serviços e funcionalidade implantados
O Microsoft 365 Defender oferece melhor visibilidade, correlação e correção à medida que você implanta serviços mais suportados.

### <a name="benefits-of-full-deployment"></a>Benefícios da implantação completa
Para obter os benefícios completos do Microsoft 365 Defender, recomendamos implantar todos os serviços com suporte. Aqui estão alguns dos principais benefícios da implantação completa:
- Incidentes são identificados e correlacionados com base em alertas e sinais de evento de todos os sensores disponíveis e recursos de análise específicos do serviço
- As cartilhas de investigação e correção automatizadas (AIR) se aplicam a vários tipos de entidade, incluindo dispositivos, caixas de correio e contas de usuário
- Um esquema de busca avançado mais abrangente pode ser consultado para dados de eventos e entidades de dispositivos, caixas de correio e outras entidades

### <a name="limited-deployment-scenarios"></a>Cenários de implantação limitados
Cada serviço com suporte implantado fornece um conjunto extremamente rico de sinais brutos, bem como informações correlacionadas. Embora a implantação limitada não cause a desativar a funcionalidade do Microsoft 365 Defender, sua capacidade de fornecer visibilidade abrangente em seus pontos de extremidade, aplicativos, dados e identidades é afetada. Ao mesmo tempo, todos os recursos de correção só se aplicam a entidades que podem ser gerenciadas pelos serviços implantados.

A tabela a seguir lista como cada serviço com suporte fornece dados adicionais, oportunidades para obter informações adicionais correlacionando os dados e melhores recursos de correção e resposta.

| Serviço | Dados (sinais & informações correlacionadas) | Remediação & escopo de resposta |
| ------ | ------ | ------ |
| Microsoft Defender para Ponto de Extremidade | - Estados de ponto de extremidade e eventos brutos<br />- Detecções e alertas de ponto de extremidade, incluindo antivírus, EDR, redução de superfície de ataque<br />- Informações sobre arquivos e outras entidades observadas nos pontos de extremidade | Pontos de extremidade |
|Microsoft Defender para Office 365 | - Estados de email e caixa de correio e eventos brutos<br />- Detecções de email, anexo e link | - Caixas de correio<br />- Contas do Microsoft 365 |
| Microsoft Defender para Identidade? | - Sinais do Active Directory, incluindo eventos de autenticação<br />- Detecções comportamentais relacionadas à identidade | Identidades |
| Microsoft Cloud App Security | - Detecção de aplicativos e serviços de nuvem não reacionais (shadow IT)<br />- Exposição de dados a aplicativos de nuvem<br />- Atividade de ameaça associada a aplicativos de nuvem | Aplicativos em nuvem |

## <a name="deploy-the-services"></a>Implantar os serviços
A implantação de cada serviço normalmente requer provisionamento para seu locatário e algumas configurações iniciais. Consulte a tabela a seguir para entender como cada um desses serviços é implantado.

| Serviço | Instruções de provisionamento | Configuração inicial |
| ------ | ------ | ------ |
| Microsoft Defender para Ponto de Extremidade | [Guia de implantação do Microsoft Defender para Ponto de Extremidade](../defender-endpoint/deployment-phases.md) | *Consulte instruções de provisionamento* |
|Microsoft Defender para Office 365 | *Nenhum, provisionado com o Office 365* | [Configurar politicas do Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) |
| Microsoft Defender para Identidade? | [Início rápido: crie sua instância do Microsoft Defender para Identidade](/azure-advanced-threat-protection/install-atp-step1) | *Consulte instruções de provisionamento* |
| Microsoft Cloud App Security | *Nenhum* | [Início rápido: começar com o Microsoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security) |

Depois de ter implantado os serviços com suporte, [acionar o Microsoft 365 Defender](m365d-enable.md).

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral do Microsoft 365 Defender](microsoft-365-defender.md)
- [Ativar o Microsoft 365 Defender](m365d-enable.md)
- [Visão geral do Microsoft Defender para Ponto de Extremidade](../defender-endpoint/microsoft-defender-endpoint.md)
- [Visão geral do Microsoft Defender para Office 365](../office-365-security/defender-for-office-365.md)
- [Visão geral do Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)
- [Visão geral do Microsoft Defender para Identidade](/azure-advanced-threat-protection/what-is-atp)
