---
title: Implantar serviços suportados pelo Microsoft 365 Defender
description: Saiba mais sobre os serviços de segurança da Microsoft que podem ser integrados pelo Microsoft 365 Defender, seus requisitos de licenciamento e procedimentos de implantação
keywords: implantar, licenças, serviços com suporte, provisionamento, configuração da Proteção contra Ameaças da Microsoft, M365, qualificação de licença, Microsoft Defender ATP, MDATP, Office 365 ATP, Azure ATP, Microsoft Cloud App Security, MCAS, proteção avançada contra ameaças, E5, A5, EMS
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 5af58a1c6850619ca08960997a30fe4a81158446
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928957"
---
# <a name="deploy-supported-services"></a>Implantar serviços com suporte

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[O Microsoft 365 Defender integra](microsoft-threat-protection.md) vários serviços de segurança da Microsoft para fornecer recursos centralizados de detecção, prevenção e investigação contra ataques sofisticados. Este artigo descreve os serviços com suporte, seus requisitos de licenciamento, as vantagens e limitações associadas à implantação de um ou mais serviços e links para como você pode implantá-los completamente individualmente.

## <a name="supported-services"></a>Serviços com suporte
Uma licença do Microsoft 365 E5, E5 Security, A5 ou A5 Security ou uma combinação válida de licenças fornece acesso aos seguintes serviços com suporte e permite que você use o Microsoft 365 Defender na central de segurança do Microsoft 365. [Ver requisitos de licenciamento](prerequisites.md#licensing-requirements)

| Serviço com suporte | Descrição |
| ------ | ------ |
| Microsoft Defender para Ponto de Extremidade | Pacote de proteção de ponto de extremidade criado com base em sensores comportamentais avançados, análise de nuvem e inteligência contra ameaças |
|Obter o Microsoft Defender para Office 365 | Proteção avançada para seus aplicativos e dados no Office 365, incluindo email e outras ferramentas de colaboração |
| O que é o Microsoft Defender para Identidade? | Defender-se contra ameaças avançadas, identidades comprometidas e usuários mal-intencionados usando sinais correlacionados do Active Directory |
| Microsoft Cloud App Security | Identificar e combater ameaças cibernéticas em seus serviços de nuvem da Microsoft e de terceiros |

## <a name="deployed-services-and-functionality"></a>Serviços e funcionalidade implantados
O Microsoft 365 Defender oferece melhor visibilidade, correlação e correção à medida que você implanta mais serviços com suporte.

### <a name="benefits-of-full-deployment"></a>Benefícios da implantação completa
Para obter os benefícios completos do Microsoft 365 Defender, recomendamos implantar todos os serviços com suporte. Aqui estão alguns dos principais benefícios da implantação completa:
- Os incidentes são identificados e correlacionados com base em alertas e sinais de evento de todos os sensores disponíveis e recursos de análise específicos do serviço
- Os playbooks de investigação e correção automatizada (AIR) se aplicam a vários tipos de entidade, incluindo dispositivos, caixas de correio e contas de usuário
- Um esquema de busca avançada mais abrangente pode ser consultado para dados de evento e entidade de dispositivos, caixas de correio e outras entidades

### <a name="limited-deployment-scenarios"></a>Cenários de implantação limitada
Cada serviço com suporte implantado fornece um conjunto extremamente rico de sinais brutos, bem como informações correlacionadas. Embora a implantação limitada não cause a redução da funcionalidade do Microsoft 365 Defender, sua capacidade de fornecer visibilidade abrangente em seus pontos de extremidade, aplicativos, dados e identidades é afetada. Ao mesmo tempo, todos os recursos de correção só se aplicam a entidades que podem ser gerenciadas pelos serviços que você implantou.

A tabela a seguir lista como cada serviço com suporte fornece dados adicionais, oportunidades para obter informações adicionais correlacionando os dados e melhores recursos de correção e resposta.

| Serviço | Dados (sinais & informações correlacionadas) | Correção & de resposta |
| ------ | ------ | ------ |
| Microsoft Defender para Ponto de Extremidade | - Estados de ponto de extremidade e eventos brutos<br />- Detecções e alertas de ponto de extremidade, incluindo antivírus, EDR, redução de superfície de ataque<br />- Informações sobre arquivos e outras entidades observadas nos pontos de extremidade | Pontos de extremidade |
|Obter o Microsoft Defender para Office 365 | - Estados de email e caixa de correio e eventos brutos<br />- Detecções de email, anexo e link | - Caixas de correio<br />– Contas do Microsoft 365 |
| O que é o Microsoft Defender para Identidade? | - Sinais do Active Directory, incluindo eventos de autenticação<br />- Detecções comportamentais relacionadas à identidade | Identidades |
| Microsoft Cloud App Security | - Detecção de aplicativos e serviços de nuvem não lançados (sombra de IT)<br />- Exposição de dados a aplicativos de nuvem<br />- Atividade de ameaças associada a aplicativos de nuvem | Aplicativos em nuvem |

## <a name="deploy-the-services"></a>Implantar os serviços
A implantação de cada serviço normalmente requer provisionamento para seu locatário e alguma configuração inicial. Consulte a tabela a seguir para entender como cada um desses serviços são implantados.

| Serviço | Instruções de provisionamento | Configuração inicial |
| ------ | ------ | ------ |
| Microsoft Defender para Ponto de Extremidade | [Guia de implantação do Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *Ver instruções de provisionamento* |
|Obter o Microsoft Defender para Office 365 | *Nenhum, provisionado com o Office 365* | [Configurar politicas do Microsoft Defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| O que é o Microsoft Defender para Identidade? | [Guia de início rápido: criar o Microsoft Defender para a instância de identidade](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *Ver instruções de provisionamento* |
| Microsoft Cloud App Security | *Nenhum* | [Guia de início rápido: começar a trabalhar com o Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

Depois de ter implantado os serviços com suporte, [acionar o Microsoft 365 Defender.](mtp-enable.md)

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral do Microsoft 365 Defender](microsoft-threat-protection.md)
- [Ativar o Microsoft 365 Defender](mtp-enable.md)
- [Visão geral do Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Visão geral do Microsoft Defender para Office 365](../office-365-security/office-365-atp.md)
- [Visão geral do Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Visão geral do Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
