---
title: Buscar por dispositivos expostos
description: Saiba como Gerenciamento de Ameaças e Vulnerabilidades pode ser usado para ajudar administradores de segurança, administradores de IT e SecOps a colaborar.
keywords: Cenários do Microsoft Defender para Endpoint-tvm, Microsoft Defender para Ponto de Extremidade, TVM, cenários de TVM, redução da exposição de vulnerabilidades de ameaça &, redução de ameaças e vulnerabilidades, melhoria da configuração de segurança, aumento da Pontuação Segura da Microsoft para Dispositivos, aumento da vulnerabilidade de & da Microsoft Secure Score for Devices, Pontuação Segura da Microsoft para Dispositivos, pontuação de exposição, controles de segurança
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a9a8ebcc89c3009cd93fbb42f2a74bbb9ffcc31b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934088"
---
# <a name="hunt-for-exposed-devices---threat-and-vulnerability-management"></a>Busca por dispositivos expostos - Gerenciamento de Ameaças e Vulnerabilidades

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Ameaça e Gerenciamento de Vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="use-advanced-hunting-to-find-devices-with-vulnerabilities"></a>Usar a busca avançada para encontrar dispositivos com vulnerabilidades

A busca avançada é uma ferramenta de busca de ameaças baseada em consultas que permite explorar até 30 dias de dados brutos. Você pode inspecionar proativamente eventos em sua rede para localizar indicadores e entidades de ameaça. O acesso flexível aos dados permite a busca não restrita por ameaças conhecidas e potenciais. [Saiba mais sobre a busca avançada](advanced-hunting-overview.md)

### <a name="schema-tables"></a>Tabelas de esquema

- [DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) - Inventário de software instalado em dispositivos, incluindo suas informações de versão e status de fim de suporte.

- [DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - Vulnerabilidades de software encontradas em dispositivos e a lista de atualizações de segurança disponíveis que abordam cada vulnerabilidade.

- [DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) - Base de conhecimento de vulnerabilidades publicamente divulgadas, incluindo se o código de exploração está disponível publicamente.

- [DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) - Eventos de avaliação de ameaças e Gerenciamento de Vulnerabilidades, indicando o status de várias configurações de segurança em dispositivos.

- [DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) - Base de conhecimento de várias configurações de segurança usadas pelo Gerenciamento de Vulnerabilidades & Ameaças para avaliar dispositivos; inclui mapeamentos para vários padrões e parâmetros de referência

## <a name="check-which-devices-are-involved-in-high-severity-alerts"></a>Verificar quais dispositivos estão envolvidos em alertas de alta gravidade

1. Vá para **a busca avançada** do painel de navegação à esquerda do Central de Segurança do Microsoft Defender.

2. Role para baixo até os esquemas de busca avançada da TVM para se familiarizar com os nomes das colunas.

3. Insira as seguintes consultas:

```kusto
// Search for devices with High active alerts or Critical CVE public exploit
DeviceTvmSoftwareVulnerabilities
| join kind=inner(DeviceTvmSoftwareVulnerabilitiesKB) on CveId
| where IsExploitAvailable == 1 and CvssScore >= 7
| summarize NumOfVulnerabilities=dcount(CveId),
DeviceName=any(DeviceName) by DeviceId
| join kind =inner(DeviceAlertEvents) on DeviceId  
| summarize NumOfVulnerabilities=any(NumOfVulnerabilities),
DeviceName=any(DeviceName) by DeviceId, AlertId
| project DeviceName, NumOfVulnerabilities, AlertId  
| order by NumOfVulnerabilities desc
```

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral Gerenciamento de Vulnerabilidades ameaça](next-gen-threat-and-vuln-mgt.md)
- [Recomendações de segurança](tvm-security-recommendation.md)
- [APIs](next-gen-threat-and-vuln-mgt.md#apis)
- [Configurar o acesso a dados para Gerenciamento de Ameaças e Vulnerabilidades funções](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)
- [Visão geral da busca avançada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [Todas as tabelas avançadas de busca](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference.md)
