---
title: Implantar recursos de proteção contra ameaças em Microsoft 365
description: Obter uma visão geral dos serviços de proteção contra ameaças e recursos de segurança Microsoft 365 E5. Proteja suas contas de usuário, dispositivos, conteúdo de email e muito mais com Microsoft 365 E5.
keywords: microsoft threat protection, defender, setup, advanced threat protection, security, microsoft 365 E5, protect devices
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
audience: ITPro
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 4008f4e0198058e2b13de62c34697e3034d499b2
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583215"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365-e5"></a>Implantar recursos de proteção contra ameaças em Microsoft 365 E5

Esta solução descreve os recursos avançados de proteção contra ameaças Microsoft 365 E5 e por que a proteção contra ameaças é importante. Confira uma visão geral da proteção contra Microsoft 365 E5 e veja como abordar a configuração e a configuração da sua organização.

## <a name="why-threat-protection-is-important"></a>Por que a proteção contra ameaças é importante 

[Malware](/windows/security/threat-protection/intelligence/understanding-malware)e ataques cibernéticos sofisticados, como ameaças [sem arquivo,](/windows/security/threat-protection/intelligence/fileless-threats)são uma ocorrência comum. As empresas precisam proteger a si mesmos e seus clientes com recursos eficazes de segurança de IT. Os ataques cibernéticos podem causar grandes problemas para sua organização, desde perda de confiança até problemas financeiros, tempo de inatividade que ameaçam os negócios e muito mais. Proteger contra ameaças é importante, mas pode ser um desafio determinar onde concentrar o tempo, o esforço e os recursos da sua organização. Microsoft 365 E5 pode ajudar. 

## <a name="threat-protection-in-microsoft-365-e5"></a>Proteção contra ameaças Microsoft 365 E5

As soluções de segurança da Microsoft são integradas aos nossos produtos e serviços. Os recursos de automação e aprendizado de máquina reduzem a carga em suas equipes de segurança para garantir que os itens certos sejam abordados. A força das soluções de segurança da Microsoft se baseia em trilhões de sinais que processam todos os dias em nosso serviço de Segurança [Inteligente Graph](/graph/security-concept-overview). Microsoft 365 soluções de segurança incluem o [Microsoft 365 Defender](../security/defender/microsoft-365-defender.md), uma solução que reúne sinais em seus emails, dados, dispositivos e identidades para pintar uma imagem de ameaças avançadas contra sua organização.

[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) permite proteger sua organização com inteligência adaptável e integrado. Com os recursos de segurança no Microsoft 365 E5, você pode detectar e investigar ameaças avançadas, identidades comprometidas e ações mal-intencionadas em seu ambiente (local e na nuvem).

## <a name="better-protection-with-integration"></a>Melhor proteção com integração

No Microsoft 365 E5, os recursos de proteção contra ameaças são integrados por padrão. Os sinais de cada recurso adicionam força à capacidade geral de detectar e responder a ameaças. O conjunto combinado de recursos oferece a melhor proteção para organizações, especialmente organizações multinacionais, em comparação com a execução de produtos que não são da Microsoft. A imagem a seguir mostra os serviços e recursos de proteção contra ameaças descritos neste artigo.

![Visão geral do Microsoft 365 Defender](../media/deploy-threat-protection/deploy-threat-protection-across-m365-overview.png)

Microsoft 365 O Defender reúne os sinais e os dados em um [centro de Microsoft 365 de segurança unificado.](/microsoft-365/security/defender/overview-security-center) 

> [!div class="mx-imgBorder"]
> ![Ilustração conceitual do painel Microsoft 365 Defender](../media/deploy-threat-protection/deploy-threat-protection-across-m365-mtp.png)

## <a name="deployment-overview"></a>Visão geral de implantação

A ilustração a seguir mostra um caminho recomendado para implantar esses recursos individuais. 

> [!div class="mx-imgBorder"]
> ![Sinais de proteção contra ameaças do M365](../media/deploy-threat-protection/deploy-threat-protection-across-m365.png)

Assista a esse vídeo para obter uma visão geral do processo de implementação.
<br><br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

A tabela a seguir descreve as várias soluções/recursos a ser configuradas e o que elas fazem.

|Etapa |Solução/recursos  |Descrição  |
|--|---------|---------|
| 1 |[Autenticação multifacional e Acesso Condicional](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)     |Proteger contra identidades e dispositivos comprometidos. Comece com essa proteção porque ela é fundamental. A configuração recomendada nesta orientação inclui a Proteção de Identidade do Azure AD como um pré-requisito. Para obter mais informações, consulte [Azure AD Identity Protection](/azure/security/fundamentals/threat-detection#azure-active-directory-identity-protection).     |
| 2 |[Microsoft Defender para Identidade?](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)     |  Uma solução de segurança baseada em nuvem que usa os sinais dos Serviços de Domínio do Active Directory (AD DS) locais para identificar, detectar e investigar ameaças avançadas, identidades comprometidas e ações internas mal-intencionadas direcionadas à sua organização. Concentre-se no Microsoft Defender for Identity em seguida porque protege sua infraestrutura local e de nuvem, não tem dependências ou pré-requisitos e pode fornecer benefícios imediatos de segurança. Para obter mais informações, consulte [O que é Proteção de Identidade?](/azure/active-directory/identity-protection/overview-identity-protection). | 
| 3 |[Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender) |Combina sinais e orquestra recursos em uma única solução. Permite que os profissionais de segurança costurem sinais de ameaça e determinem o escopo completo e o impacto de uma ameaça. Microsoft 365 O Defender faz ações automáticas para impedir ou interromper o ataque e a auto-recuperação de caixas de correio afetadas, pontos de extremidade e identidades de usuário. Para obter mais informações, [consulte Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender). |
| 4  |[Obter o Microsoft Defender para Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)     | Protege sua organização contra ameaças mal-intencionadas colocadas por mensagens de email, links (URLs) e ferramentas de colaboração. Protege contra malware, phishing, spoofing e outros tipos de ataque. A configuração do Microsoft Defender para Office 365 é recomendada porque o controle de alteração, a migração das configurações do sistema incumbente e outras considerações podem levar mais tempo para implantar. Para obter mais informações, consulte [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365).       |
| 5  |[Microsoft Defender para Ponto de Extremidade](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)    | Ajuda a evitar, detectar, investigar e responder a ameaças avançadas entre dispositivos (também chamados de pontos de extremidade). O Defender for Endpoint é uma oferta robusta de proteção contra ameaças. Para obter mais informações, consulte [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint).  |
| 6  |[Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)     | Um agente de segurança de acesso à nuvem para descoberta, investigação e governança. Você pode habilitar Microsoft Cloud App Security início da coleta de dados e insights. Implementar informações e outra proteção direcionada em seus aplicativos SaaS envolve planejamento e pode levar mais tempo. Para obter mais informações, consulte [O que é Cloud App Security?](/cloud-app-security/what-is-cloud-app-security)      | 

> [!TIP]
> Organizações com várias equipes de segurança podem implementar recursos em paralelo. Por exemplo, uma equipe pode configurar o Defender para Office 365 enquanto outra configura o Defender para o Ponto de Extremidade. A configuração não precisa seguir nossa ordem sugerida exatamente. 

## <a name="plan-to-deploy-your-threat-protection-solution"></a>Planejar a implantação da solução de proteção contra ameaças

O diagrama a seguir ilustra o processo de alto nível para implantar recursos de proteção contra ameaças. 

![Processo para implantar recursos de proteção contra ameaças](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png)

Para garantir que sua organização tenha a melhor proteção possível, configurar e [implantar](deploy-threat-protection-configure.md) sua solução de segurança com um processo que inclua as seguintes etapas:

1. [Configurar a autenticação multifacional e políticas de Acesso Condicional.](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Configurar o Microsoft Defender para Identidade](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity).
3. [A Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender).
4. [Configure o Defender para Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365).
5. [Configurar o Microsoft Defender para Ponto de Extremidade](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint).
6. [Configure Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security).
7. [Monitore o status e tome ações](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions).
8. [Treinar usuários](deploy-threat-protection-configure.md#step-8-train-users).

Seus recursos de proteção contra ameaças podem ser configurados em paralelo, portanto, se você tiver várias equipes de segurança de rede responsáveis por serviços diferentes, eles poderão configurar os recursos de proteção da sua organização ao mesmo tempo.

## <a name="next-step"></a>Próxima etapa

Continue a [configurar recursos de proteção contra ameaças em Microsoft 365](deploy-threat-protection-configure.md).


