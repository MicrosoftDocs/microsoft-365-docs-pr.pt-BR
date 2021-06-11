---
title: Integrar o Microsoft Defender para Ponto de Extremidade com outras soluções da Microsoft
description: Saiba como o Microsoft Defender for Endpoint se integra a outras soluções da Microsoft, incluindo o Microsoft Defender para Identidade e o Azure Defender.
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: microsoft 365 defender, acesso condicional, office, Microsoft Defender for Endpoint, microsoft defender for identity, microsoft defender for office, Azure Defender, microsoft cloud app security, azure sentinel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: aeb6d93017f138ce898d25f7d76e05cdcf3e90c5
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878563"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a>Microsoft Defender para Ponto de Extremidade e outras soluções da Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a>Integrar com outras soluções da Microsoft

O Microsoft Defender para Ponto de Extremidade integra-se diretamente a várias soluções da Microsoft.

### <a name="azure-defender"></a>Azure Defender
O Microsoft Defender for Endpoint fornece uma solução abrangente de proteção do servidor, incluindo detecção e resposta de ponto de extremidade (EDR) em Windows Servidores.

### <a name="azure-sentinel"></a>Azure Sentinel
O conector do Microsoft Defender para Ponto de Extremidade permite transmitir alertas do Microsoft Defender para Ponto de Extremidade no Azure Sentinel. Isso permitirá que você analise de forma mais abrangente os eventos de segurança em toda a sua organização e crie playbooks para resposta efetiva e imediata.

### <a name="azure-information-protection"></a>Proteção de Informações do Azure
Recentemente, preterimos a integração com a Proteção de Informações do Azure, pois nossos recursos de DLP do Ponto de Extremidade incorporam uma solução aprimorada de descoberta e proteção para dados confidenciais armazenados em dispositivos de ponto de extremidade que facilitam maior visibilidade e integração entre soluções. Isso foi anunciado no [blog a seguir.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555) Recomendamos que os clientes mudem para o uso de DLP do ponto de extremidade.

### <a name="conditional-access"></a>Acesso Condicional
A pontuação de risco de dispositivo dinâmico do Microsoft Defender para Endpoint é integrada à avaliação do Acesso Condicional, garantindo que somente dispositivos seguros tenham acesso aos recursos. 

### <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security
Microsoft Cloud App Security aproveita os sinais de ponto de extremidade do Microsoft Defender para Ponto de Extremidade para permitir visibilidade direta do uso de aplicativos na nuvem, incluindo o uso de serviços de nuvem sem suporte (SHADOW IT) de todos os dispositivos monitorados do Microsoft Defender para Ponto de Extremidade.

### <a name="microsoft-defender-for-identity"></a>Microsoft Defender para Identidade?
Atividades suspeitas são processos em execução em um contexto de usuário. A integração entre o Microsoft Defender para Ponto de Extremidade e o Microsoft Defender para Identidade fornece a flexibilidade de conduzir a investigação de segurança cibernética entre atividades e identidades.

### <a name="microsoft-defender-for-office"></a>Microsoft Defender para Office
[O Defender para Office 365](/office365/securitycompliance/office-365-atp) ajuda a proteger sua organização contra malware em mensagens de email ou arquivos por meio de links Cofre, anexos Cofre, recursos avançados de inteligência anti-phishing e spoof. A integração entre o Microsoft Defender para Office 365 e o Microsoft Defender para Ponto de Extremidade permite que os analistas de segurança acessem o upstream para investigar o ponto de entrada de um ataque. Por meio do compartilhamento de inteligência de ameaças, os ataques podem ser contidos e bloqueados. 

>[!NOTE]
> Os dados do Defender Office 365 são exibidos para eventos nos últimos 30 dias. Para alertas, o Defender para Office 365 dados é exibido com base na primeira hora de atividade. Depois disso, os dados não estarão mais disponíveis no Defender para Office 365.

### <a name="skype-for-business"></a>Skype for Business
A Skype for Business oferece uma maneira para os analistas se comunicarem com um usuário ou proprietário de dispositivo potencialmente comprometido por meio de um botão simples do portal.

## <a name="microsoft-365-defender"></a>Microsoft 365 Defender
Com o Microsoft 365 Defender, o Microsoft Defender para Ponto de Extremidade e várias soluções de segurança da Microsoft formam um pacote unificado de defesa empresarial de pré e pós-violação que se integra de forma nativa no ponto de extremidade, identidade, email e aplicativos para detectar, impedir, investigar e responder automaticamente a ataques sofisticados. 
 
[Saiba mais sobre o Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)


## <a name="related-topics"></a>Tópicos relacionados
- [Configurar a integração e outros recursos avançados](advanced-features.md)
- [Microsoft 365 Visão geral do Defender](/microsoft-365/security/defender/microsoft-threat-protection)
- [Ativar o Microsoft 365 Defender](/microsoft-365/security/defender/mtp-enable)
- [Proteger usuários, dados e dispositivos com Acesso Condicional](conditional-access.md)
