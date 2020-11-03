---
title: Implantar a proteção contra ameaças à segurança de rede no Microsoft 365
description: Saiba como implantar os serviços de proteção contra ameaças e os recursos de segurança de rede de ti no Microsoft 365 e5.
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 2d1316927124b1ce03910190922fa0804853ae4b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845271"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a>Implantar recursos de proteção contra ameaças no Microsoft 365

[Malware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware)e cyberattacks sofisticados, como ameaças de não- [arquivo](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats), são uma ocorrência comum. As empresas precisam se proteger e seus clientes com recursos de segurança de rede de ti eficazes. Esses ataques podem causar sérios problemas para a sua organização, desde uma perda de confiança para o Woes financeiro, tempo de inatividade de ameaças de negócios e muito mais. A proteção contra ameaças é importante, mas pode ser desafiadora para determinar onde concentrar o tempo, esforço e recursos da sua organização. 

As soluções de segurança da Microsoft são incorporadas a nossos produtos e serviços. Recursos de automação e aprendizado de máquina reduzem a carga em suas equipes de segurança para garantir que os itens corretos sejam tratados. E a força das soluções de segurança de rede da Microsoft baseia-se em trilhões de sinais que processamos todos os dias no nosso [gráfico de segurança inteligente](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph). As soluções de segurança da Microsoft 365 incluem o [Microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection), uma solução que reúne sinais em seus emails, dados, dispositivos e identidades para pintar uma imagem de ameaças avançadas contra sua organização.


Assista a esse vídeo para obter uma visão geral do processo de implantação.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

Use este artigo como um guia para implementar sua solução de proteção contra ameaças.

## <a name="threat-protection-in-microsoft-365-e5"></a>Proteção contra ameaças no Microsoft 365 e5

O [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) permite que você proteja sua organização com inteligência integrada e adaptável. Com os recursos de proteção contra ameaças no Microsoft 365 e5, é possível detectar e investigar ameaças avançadas, identidades comprometidas e ações mal-intencionadas em todo o ambiente local e em nuvem.

No Microsoft 365 e5, os recursos de proteção contra ameaças estão integrados por padrão. Os sinais de cada recurso adicionam força à capacidade geral de detectar e responder a ameaças. O conjunto combinado de recursos oferece a melhor proteção para organizações, especialmente organizações multinacionais, em comparação à execução de produtos que não são da Microsoft. A imagem a seguir mostra os serviços e os recursos de proteção contra ameaças no Microsoft 365 E5 descritos neste artigo.

![Visão geral do Microsoft 365 defender](../media/solutions-architecture-center/deploy-threat-protection-across-m365-overview.png)

Assim que você implantar qualquer um dos recursos do defender for Office 365, poderá ativar o Microsoft 365 defender, que traz os sinais e dados juntos em um só lugar. 

![Ilustração conceitual do Microsoft 365 defender Dashboard](../media/solutions-architecture-center/deploy-threat-protection-across-m365-mtp.png)

A ilustração a seguir mostra um caminho recomendado para implantar esses recursos individuais. 

![Sinais de proteção contra ameaças do M365](../media/solutions-architecture-center/deploy-threat-protection-across-m365.png)

|Soluções/recursos  |Descrição  |
|---------|---------|
|Autenticação multifatorial e acesso condicional     |Proteger contra identidades e dispositivos comprometidos. Comece com esta proteção porque é fundamental. A configuração recomendada neste guia inclui a proteção de identidade do Azure AD como pré-requisito.     |
|Microsoft Defender para Identidade     |  Uma solução de segurança baseada em nuvem que aproveita seus sinais do Active Directory local para identificar, detectar e investigar ameaças avançadas, identidades comprometidas e ações mal-intencionadas intencionais direcionadas para sua organização. Concentre-se no Microsoft defender para obter a identidade seguinte porque ela protege sua infraestrutura de nuvem e local, não tem dependências ou pré-requisitos e pode fornecer benefícios imediatos.       | 
|Microsoft defender para Office 365     | Protege sua organização contra ameaças mal-intencionadas, feitas por mensagens de email, links (URLs) e ferramentas de colaboração. Proteções para malware, phishing, falsificação e outros tipos de ataque. A configuração do Microsoft defender para Office 365 é recomendada em seguida porque o controle de alterações, a migração das configurações do sistema responsável e outras considerações podem levar mais tempo para ser implantado. <br><br>Observação: Certifique-se de configurar os recursos de proteção contra ameaças que estão incluídos em todas as assinaturas do Office 365 (proteção do Exchange Online).       |
|Microsoft Defender para Ponto de Extremidade    | Uma plataforma do Endpoint Protection que ajuda a impedir, detectar, investigar e responder a ameaças avançadas.  O defender for Endpoint pode levar algum tempo para implantar, mas a configuração pode ser feita em paralelo com outros recursos.   |
|Segurança no aplicativo na nuvem da Microsoft     |   Um agente de segurança de acesso à nuvem para descoberta, investigação e governança. Você pode habilitar o Microsoft Cloud app Security antecipadamente para começar a coletar dados e insights. Implementar informações e outras proteções direcionadas em seus aplicativos SaaS envolve o planejamento e pode levar mais tempo.       | 

> [!TIP]
> As organizações com várias equipes de segurança podem implementar esses recursos em paralelo.

## <a name="deploy-your-threat-protection-solution"></a>Implantar sua solução de proteção contra ameaças

Para garantir que sua organização tenha a melhor proteção possível, configure e implante sua solução de segurança para incluir as seguintes etapas:

1. [Configurar a autenticação multifator e políticas de acesso condicional](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Configurar o Microsoft defender para identidade](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [Ativar o Microsoft 365 defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [Configurar o defender para Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [Configurar o Microsoft defender para ponto de extremidade](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)
6. [Configurar o Microsoft Cloud app Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [Monitorar o status e realizar ações](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [Treinar usuários](deploy-threat-protection-configure.md#step-8-train-users)

Seus recursos de proteção contra ameaças podem ser configurados em paralelo, portanto, se você tiver várias equipes de segurança de rede responsáveis por diferentes serviços, eles podem configurar os recursos de proteção da sua organização ao mesmo tempo. O diagrama a seguir ilustra o processo de alto nível para a implantação de recursos de proteção contra ameaças. 

![Processo de implantação de recursos de proteção contra ameaças](../media/solutions-architecture-center/deploy-threat-protection-across-m365-grid.png) 


