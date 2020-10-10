---
title: Implantar serviços suportados pela proteção contra ameaças da Microsoft
description: Saiba mais sobre os serviços de segurança da Microsoft que podem ser integrados pela proteção contra ameaças da Microsoft, seus requisitos de licenciamento e procedimentos de implantação
keywords: implantar, licenças, serviços com suporte, provisionamento, configuração proteção contra ameaças da Microsoft, M365, elegibilidade da licença, Microsoft defender ATP, MDATP, Office 365 ATP, Azure ATP, Microsoft Cloud app Security, MCAS, proteção avançada contra ameaças, e5, a5, EMS
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 3a5db0b9709a9596ccd6560d7f2e546dd3753332
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413347"
---
# <a name="deploy-supported-services"></a>Implantar serviços com suporte

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

A [proteção contra ameaças da Microsoft](microsoft-threat-protection.md) integra vários serviços de segurança da Microsoft para fornecer recursos centralizados de detecção, prevenção e investigação contra ataques sofisticados. Este artigo descreve os serviços com suporte, seus requisitos de licenciamento, as vantagens e limitações associadas à implantação de um ou mais serviços e links para como você pode implantá-los totalmente individualmente.

## <a name="supported-services"></a>Serviços com suporte
Uma licença de segurança do Microsoft 365 e5, E5 Security, a5 ou a5 ou uma combinação válida de licenças fornece acesso aos seguintes serviços compatíveis e o concede a você para usar a proteção contra ameaças da Microsoft na central de segurança da Microsoft 365. [Confira requisitos de licenciamento](prerequisites.md#licensing-requirements)

| Serviço com suporte | Descrição |
| ------ | ------ |
| O Microsoft Defender ATP | Conjunto de pontos de extremidade do Endpoint desenvolvido com base em poderosos sensores comportamentais, análise de nuvem e inteligência de ameaças |
| Office 365 ATP | Proteção avançada para seus aplicativos e dados no Office 365, incluindo emails e outras ferramentas de colaboração |
| Azure ATP | Defesa contra ameaças avançadas, identidades comprometidas e insideres mal-intencionados usando sinais correlatos do Active Directory |
| Segurança no aplicativo na nuvem da Microsoft | Identificar e combater o ciberataques em seus serviços de nuvem da Microsoft e de terceiros |

## <a name="deployed-services-and-functionality"></a>Serviços e funcionalidade implantados
A proteção contra ameaças da Microsoft oferece melhor visibilidade, correlação e correção à medida que você implanta serviços mais suportados.

### <a name="benefits-of-full-deployment"></a>Benefícios da implantação completa
Para obter os benefícios completos da proteção contra ameaças da Microsoft, recomendamos implantar todos os serviços com suporte. Estes são alguns dos principais benefícios da implantação completa:
- Os incidentes são identificados e correlacionados com base nos alertas e nos sinais de eventos de todos os sensores disponíveis e recursos de análise específicos de serviços
- Os guias de análise automática de investigação e correção (ar) se aplicam a vários tipos de entidade, incluindo dispositivos, caixas de correio e contas de usuário
- Um esquema de busca avançada mais abrangente pode ser consultado para dados de eventos e entidades de dispositivos, caixas de correio e outras entidades

### <a name="limited-deployment-scenarios"></a>Cenários de implantação limitados
Cada serviço compatível que você implantar fornece um conjunto de sinais brutos extremamente avançado, bem como informações correlacionadas. Enquanto a implantação limitada não faz com que a funcionalidade de proteção contra ameaças da Microsoft seja desativada, sua capacidade de fornecer visibilidade abrangente em seus pontos de extremidade, aplicativos, dados e identidades é afetada. Ao mesmo tempo, todos os recursos de correção se aplicam apenas às entidades que podem ser gerenciadas pelos serviços implantados.

A tabela a seguir lista como cada serviço suportado fornece dados adicionais, oportunidades de obter informações adicionais, correlacionando os dados e melhores recursos de correção e resposta.

| Serviço | Dados (sinais & informações correlacionadas) | Escopo de resposta de & de correção |
| ------ | ------ | ------ |
| O Microsoft Defender ATP | – Estados de ponto de extremidade e eventos brutos<br />-Detecções e alertas de ponto de extremidade, incluindo antivírus, EDR, redução da superfície de ataque<br />– Informações sobre arquivos e outras entidades observadas nos pontos de extremidade | Pontos de extremidade |
| Office 365 ATP | -Mensagens e Estados de caixa de correio e eventos brutos<br />– Detecções de email, anexos e links | -Caixas de correio<br />-Contas da Microsoft 365 |
| Azure ATP | -Sinais do Active Directory, incluindo eventos de autenticação<br />-Detecções de comportamento relacionadas à identidade | Identidades |
| Segurança no aplicativo na nuvem da Microsoft | – Detecção de serviços e aplicativos de nuvem não aprovados (Shadow IT)<br />– Exposição de dados para aplicativos em nuvem<br />-Atividade de ameaça associada aos aplicativos de nuvem | Aplicativos em nuvem |

## <a name="deploy-the-services"></a>Implantar os serviços
A implantação de cada serviço normalmente requer o provisionamento para seu locatário e uma configuração inicial. Consulte a tabela a seguir para entender como cada um desses serviços é implantado.

| Serviço | Instruções de provisionamento | Configuração inicial |
| ------ | ------ | ------ |
| O Microsoft Defender ATP | [Guia de implantação do Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *Confira instruções de provisionamento* |
| Office 365 ATP | *Nenhum, provisionado com o Office 365* | [Configurar políticas de ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Azure ATP | [Início rápido: criar sua instância do Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *Confira instruções de provisionamento* |
| Segurança no aplicativo na nuvem da Microsoft | *Nenhum* | [Início rápido: introdução ao Microsoft Cloud app Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

Depois de implantar os serviços com suporte, [ative a proteção contra ameaças da Microsoft](mtp-enable.md).

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral da Proteção contra Ameaças da Microsoft](microsoft-threat-protection.md)
- [Habilitar a Proteção contra Ameaças da Microsoft](mtp-enable.md)
- [Visão geral do Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Visão geral da ATP do Office 365](../office-365-security/office-365-atp.md)
- [Visão geral do Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Visão geral da ATP do Azure](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
