---
title: Como relatar falsos positivos ou falsos negativos no AIR na proteção contra ameaças da Microsoft
description: Algo estava perdido ou foi detectado incorretamente pelo ar na proteção contra ameaças da Microsoft? Saiba como enviar falsos positivos ou falsos negativos para a Microsoft para análise.
keywords: automatizado, investigação, alerta, gatilho, ação, correção, falso positivo, falso negativo
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: d62f10cdf9805cdcfae7ba5bd5381ca589d1297c
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2020
ms.locfileid: "41260189"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Como relatar falsos positivos/negativos em recursos de investigação e resposta automatizados

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Os [recursos de investigação e resposta automatizados](mtp-autoir.md) na proteção contra ameaças da Microsoft perdem ou detectam incorretamente algo? Você pode relatá-la à Microsoft ou ajustar seus alertas (se necessário). Use a tabela a seguir como uma guia: 


|Item  |Detectado por  |Como relatá-lo  |
|---------|---------|---------|
|Mensagem de email <br/>Anexo de email <br/>URL em uma mensagem de email ou em um arquivo do Office      |[Proteção Avançada contra Ameaças do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[Enviar spam, phishing, URLs e arquivos suspeitos à Microsoft para a verificação do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|Arquivo ou aplicativo em um dispositivo    |[Proteção Avançada contra Ameaças do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection)         |[Enviar um arquivo para a Microsoft para análise de malware](https://www.microsoft.com/wdsi/filesubmission)         |
|Alerta disparado por uso legítimo <br/>Alerta incorreto    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> ou <br/>[Detecção avançada de ameaças do Azure](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Gerenciar alertas no portal do Cloud app Security](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |


## <a name="next-steps"></a>Próximas etapas

- [Aprovar ou rejeitar ações relacionadas a investigações e respostas automatizadas](mtp-autoir-actions.md)
- [Saiba mais sobre a Central de Ações](mtp-action-center.md)
- [Faça buscas proativas por ameaças com a busca avançada da Proteção contra Ameaças da Microsoft](advanced-hunting-overview.md)
