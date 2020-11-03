---
title: Implantar serviços suportados pelo Microsoft 365 defender
description: Saiba mais sobre os serviços de segurança da Microsoft que podem ser integrados pelo Microsoft 365 defender, seus requisitos de licenciamento e procedimentos de implantação
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
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 4a1bed4d6c6688c266b9df8ce36e4b25a0632d68
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843919"
---
# <a name="deploy-supported-services"></a>Implantar serviços com suporte

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[O microsoft 365 defender](microsoft-threat-protection.md) integra vários serviços de segurança da Microsoft para fornecer recursos centralizados de detecção, prevenção e investigação contra ataques sofisticados. Este artigo descreve os serviços com suporte, seus requisitos de licenciamento, as vantagens e limitações associadas à implantação de um ou mais serviços e links para como você pode implantá-los totalmente individualmente.

## <a name="supported-services"></a>Serviços com suporte
Uma licença de segurança do Microsoft 365 e5, E5 Security, a5 ou a5 ou uma combinação válida de licenças fornece acesso aos seguintes serviços compatíveis e o concede a você para usar o Microsoft 365 defender no centro de segurança do Microsoft 365. [Confira requisitos de licenciamento](prerequisites.md#licensing-requirements)

| Serviço com suporte | Descrição |
| ------ | ------ |
| Microsoft Defender para Ponto de Extremidade | Conjunto de pontos de extremidade do Endpoint desenvolvido com base em poderosos sensores comportamentais, análise de nuvem e inteligência de ameaças |
|Microsoft defender para Office 365 | Proteção avançada para seus aplicativos e dados no Office 365, incluindo emails e outras ferramentas de colaboração |
| Microsoft Defender para Identidade | Defesa contra ameaças avançadas, identidades comprometidas e insideres mal-intencionados usando sinais correlatos do Active Directory |
| Segurança no aplicativo na nuvem da Microsoft | Identificar e combater o ciberataques em seus serviços de nuvem da Microsoft e de terceiros |

## <a name="deployed-services-and-functionality"></a>Serviços e funcionalidade implantados
O Microsoft 365 defender oferece melhor visibilidade, correlação e correção à medida que você implanta serviços mais suportados.

### <a name="benefits-of-full-deployment"></a>Benefícios da implantação completa
Para obter os benefícios completos do Microsoft 365 defender, recomendamos implantar todos os serviços com suporte. Estes são alguns dos principais benefícios da implantação completa:
- Os incidentes são identificados e correlacionados com base nos alertas e nos sinais de eventos de todos os sensores disponíveis e recursos de análise específicos de serviços
- Os guias de análise automática de investigação e correção (ar) se aplicam a vários tipos de entidade, incluindo dispositivos, caixas de correio e contas de usuário
- Um esquema de busca avançada mais abrangente pode ser consultado para dados de eventos e entidades de dispositivos, caixas de correio e outras entidades

### <a name="limited-deployment-scenarios"></a>Cenários de implantação limitados
Cada serviço compatível que você implantar fornece um conjunto de sinais brutos extremamente avançado, bem como informações correlacionadas. Enquanto a implantação limitada não faz com que a funcionalidade do Microsoft 365 defender seja desativada, sua capacidade de fornecer visibilidade abrangente em seus pontos de extremidade, aplicativos, dados e identidades é afetada. Ao mesmo tempo, todos os recursos de correção se aplicam apenas às entidades que podem ser gerenciadas pelos serviços implantados.

A tabela a seguir lista como cada serviço suportado fornece dados adicionais, oportunidades de obter informações adicionais, correlacionando os dados e melhores recursos de correção e resposta.

| Serviço | Dados (sinais & informações correlacionadas) | Escopo de resposta de & de correção |
| ------ | ------ | ------ |
| Microsoft Defender para Ponto de Extremidade | – Estados de ponto de extremidade e eventos brutos<br />-Detecções e alertas de ponto de extremidade, incluindo antivírus, EDR, redução da superfície de ataque<br />– Informações sobre arquivos e outras entidades observadas nos pontos de extremidade | Pontos de extremidade |
|Microsoft defender para Office 365 | -Mensagens e Estados de caixa de correio e eventos brutos<br />– Detecções de email, anexos e links | -Caixas de correio<br />-Contas da Microsoft 365 |
| Microsoft Defender para Identidade | -Sinais do Active Directory, incluindo eventos de autenticação<br />-Detecções de comportamento relacionadas à identidade | Identidades |
| Segurança no aplicativo na nuvem da Microsoft | – Detecção de serviços e aplicativos de nuvem não aprovados (Shadow IT)<br />– Exposição de dados para aplicativos em nuvem<br />-Atividade de ameaça associada aos aplicativos de nuvem | Aplicativos em nuvem |

## <a name="deploy-the-services"></a>Implantar os serviços
A implantação de cada serviço normalmente requer o provisionamento para seu locatário e uma configuração inicial. Consulte a tabela a seguir para entender como cada um desses serviços é implantado.

| Serviço | Instruções de provisionamento | Configuração inicial |
| ------ | ------ | ------ |
| Microsoft Defender para Ponto de Extremidade | [Guia de implantação do Microsoft defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *Confira instruções de provisionamento* |
|Microsoft defender para Office 365 | *Nenhum, provisionado com o Office 365* | [Configurar as políticas do Microsoft defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Microsoft Defender para Identidade | [Início rápido: Crie sua instância do Microsoft defender para identidade](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *Confira instruções de provisionamento* |
| Segurança no aplicativo na nuvem da Microsoft | *Nenhum* | [Início rápido: introdução ao Microsoft Cloud app Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

Depois de implantar os serviços com suporte, [ative o Microsoft 365 defender](mtp-enable.md).

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral do Microsoft 365 defender](microsoft-threat-protection.md)
- [Ativar o Microsoft 365 defender](mtp-enable.md)
- [Visão geral do Microsoft defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Visão geral do Microsoft defender para Office 365](../office-365-security/office-365-atp.md)
- [Visão geral do Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Visão geral do Microsoft defender para identidade](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
