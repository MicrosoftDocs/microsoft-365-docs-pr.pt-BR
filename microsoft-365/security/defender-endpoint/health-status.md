---
title: Investigar problemas de saúde do agente
description: Saiba mais sobre os valores retornados ao executar o comando de saúde mdatp
keywords: mdatp health, command, health, status, command, onboarding status
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: acc75a931cb14a7aab729c09a7b835fb9f26d1d1
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281049"
---
# <a name="investigate-agent-health-issues"></a>Investigar problemas de saúde do agente

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


A tabela a seguir fornece informações sobre os valores retornados quando você executar o `mdatp health` comando e suas descrições correspondentes.

| Valor | Descrição |
|-|-|
| automatic_definition_update_enabled | True se as atualizações automáticas de definição de antivírus estão habilitadas, caso contrário, false. |
|  cloud_automatic_sample_submission_consent | Nível de envio de exemplo atual. Pode ser um dos seguintes valores:     <br><br>  - **Nenhum**: Nenhum exemplo suspeito é enviado à Microsoft.  <br> <br>     - **Cofre**: Somente amostras suspeitas que não contenham informações de identificação pessoal (PII) são enviadas automaticamente. Esse é o valor padrão para essa configuração.    <br> <br>   - **All**: Todos os exemplos suspeitos são enviados à Microsoft.   |
| cloud_diagnostic_enabled | True se a coleta de dados de diagnóstico opcional estiver habilitada, caso contrário, false. Para obter mais informações relacionadas ao Defender para Ponto de Extremidade e a outros produtos e serviços como Microsoft Defender Antivírus e Windows 10, consulte [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=827576). |
| cloud_enabled | True se a proteção entregue na nuvem estiver habilitada, caso contrário, false. |
| conflicting_applications | Lista de aplicativos possivelmente conflitantes com o Microsoft Defender para Ponto de Extremidade. Essa lista inclui, mas não se limita a outros produtos de segurança e outros aplicativos conhecidos por causar problemas de compatibilidade. |
| definitions_status | Status das definições de antivírus. |
| definitions_updated | Data e hora da última atualização de definição de antivírus. |
| definitions_updated_minutes_ago | Número de minutos desde a última atualização de definição de antivírus. |
| definitions_version | Versão de definição de antivírus. |
| edr_client_version | Versão do cliente EDR em execução no dispositivo. |
| edr_configuration_version | EDR versão de configuração. |
| edr_device_tags | Lista de marcas associadas ao dispositivo. |
| edr_group_ids | ID de grupo à que o dispositivo está associado. |
| edr_machine_id | Identificador de dispositivo usado em Central de Segurança do Microsoft Defender. |
| engine_version | Versão do mecanismo antivírus. |
| healthy | True se o produto estiver íntegre, false caso contrário. |
| licenciado | True se o dispositivo estiver conectado a um locatário, caso contrário, false. |
| log_level | Nível de log atual do produto. |
| machine_guid | Identificador de máquina exclusivo usado pelo componente antivírus. |
| network_protection_status                 | Status do componente de proteção de rede (somente macOS). Pode ser um dos seguintes valores:       <br> <br>- **starting** - Proteção de rede está começando  <br> <br>     - **failed_to_start** - A proteção de rede não pôde ser iniciada devido a um erro   <br> <br>    - **started** - A proteção de rede está em execução no dispositivo     <br> <br>  - **reinicialização** - A proteção de rede está sendo reiniciada no momento   <br> <br>    - **stopping** - Network protection is stopping     <br> <br>  - **stopped** - A proteção de rede não está em execução |
| org_id | Organização à que o dispositivo está internado. Se o dispositivo ainda não estiver conectado a nenhuma organização, ele não estará disponível. Para obter mais informações sobre a integração, consulte [Onboard to Microsoft Defender for Endpoint](onboarding.md). |
| passive_mode_enabled | True se o componente antivírus estiver definido para ser executado no modo passivo, false caso contrário. |
| product_expiration | Data e hora em que a versão atual do produto atinge o fim do suporte. |
| real_time_protection_available | True se o componente de proteção em tempo real estiver íntegre, caso contrário, false. |
| real_time_protection_enabled | True se a proteção antivírus em tempo real estiver habilitada, caso contrário, false. |
| real_time_protection_subsystem | Subsistema usado para servir proteção em tempo real. Se a proteção em tempo real não estiver funcionando conforme o esperado, ela não estará disponível. |
| release_ring | Anel de liberação. Para obter mais informações, consulte   [Deployment rings](deployment-rings.md). |