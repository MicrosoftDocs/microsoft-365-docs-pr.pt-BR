---
title: Etapas para configurar recursos de proteção contra ameaças em Microsoft 365
description: Use este artigo como um guia para implementar sua solução de proteção contra ameaças. Implantar serviços e recursos de proteção contra ameaças em Microsoft 365 E5.
keywords: solução de segurança, configuração, configuração, Microsoft 365 E5, proteção avançada contra ameaças, defender
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-threatprotection
- m365solution-scenario
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: daa85b406b0fcb56dee55d9f49d39e247d0b6264
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583695"
---
# <a name="configure-threat-protection-capabilities-across-microsoft-365"></a>Configurar recursos de proteção contra ameaças em Microsoft 365

Siga estas etapas para configurar a proteção contra ameaças Microsoft 365.

## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>Etapa 1: Configurar a autenticação multifacional e políticas de Acesso Condicional

[A autenticação multifafatório](/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) exige que os usuários verifiquem sua identidade com uma chamada telefônica ou um aplicativo autenticador. [As políticas de acesso condicional](/azure/active-directory/conditional-access/overview) definem determinados requisitos que devem ser atendidos para que os usuários acessem aplicativos e dados em Microsoft 365. As políticas de Acesso Condicional e MFA trabalham juntas para proteger sua organização. Por exemplo, se alguém tentar entrar em um dispositivo móvel usando uma conta que não está habilitada para MFA e uma política de Acesso Condicional exigir que o MFA entre em vigor, esse usuário será impedido de entrar.  

A Microsoft testou e recomenda um conjunto específico de Acesso Condicional e políticas relacionadas para proteger o acesso a todos os seus aplicativos SaaS, especialmente Microsoft 365. As políticas são recomendadas para proteção de linha de base, sensível e altamente regulamentada. Comece implementando as políticas de proteção de linha de base. 


[ ![ Políticas comuns para configurar identidade e acesso](../media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png) 
 [a dispositivos Consulte uma versão maior dessa imagem](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>Para implementar a proteção de linha de base para Microsoft 365

![Processo para implantar a proteção de linha de base](../media/deploy-threat-protection/deploy-threat-protection-identity-access-steps.png) 

1. [Configure os pré-requisitos, incluindo a Proteção de Identidade do Azure AD.](../security/office-365-security/identity-access-prerequisites.md)
2. [Configure políticas comuns de identidade e acesso a dispositivos](../security/office-365-security/identity-access-policies.md) para proteção de linha de base.
3. Configurar políticas para [usuários convidados,](../security/office-365-security/identity-access-policies-guest-access.md) [Microsoft Teams,](../security/office-365-security/teams-access-policies.md) [Exchange Online](../security/office-365-security/secure-email-recommended-policies.md)e SharePoint Online [e OneDrive](../security/office-365-security/sharepoint-file-access-policies.md).

### <a name="more-information-about-protecting-identities"></a>Mais informações sobre como proteger identidades

- [Configurações de identidade e acesso a dispositivos](../security/office-365-security/microsoft-365-policies-configurations.md)
- [Diretrizes de segurança para o Azure MFA](/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-microsoft-defender-for-identity"></a>Etapa 2: Configurar o Microsoft Defender para Identidade

O [Microsoft Defender for Identity](/defender-for-identity/what-is) é uma solução de segurança baseada em nuvem que funciona com seus sinais locais dos Serviços de Domínio do Active Directory (AD DS) para identificar, detectar e investigar ameaças avançadas, identidades comprometidas e ações internas mal-intencionadas direcionadas à sua organização.

O Microsoft Defender for Identity habilita analistas de operações de segurança (SecOps) e profissionais de segurança com dificuldades para detectar ataques avançados em ambientes híbridos para:
- Monitore usuários, comportamento da entidade e atividades com análises baseadas em aprendizado.
- Proteger as identidades e credenciais do usuário armazenadas no Active Directory.
- Identificar e investigar atividades suspeitas do usuário e ataques avançados em toda a cadeia de extermínio.
- Fornecer informações claras sobre incidentes em uma linha do tempo simples para triagem rápida.

### <a name="to-set-up-microsoft-defender-for-identity"></a>Para configurar o Microsoft Defender para Identidade

![Processo para implantar o Microsoft Defender para Identidade](../media/deploy-threat-protection/deploy-azure-atp-steps.png) 

1. [Configurar o Microsoft Defender para Identidade](/azure-advanced-threat-protection/install-atp-step1) para proteger seus ambientes principais.
2. Proteja todos os [controladores de domínio e](/azure-advanced-threat-protection/atp-sensor-monitoring) [florestas.](/azure-advanced-threat-protection/atp-multi-forest)
3. Integre [alertas do Microsoft Defender para Identidade](/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external) ao fluxo de trabalho de operações de segurança (SecOps).

### <a name="more-information-about-microsoft-defender-for-identity"></a>Mais informações sobre o Microsoft Defender for Identity

- [O que é o Microsoft Defender para Identidade?](/azure-advanced-threat-protection/what-is-atp)
- [Vídeo: Introdução ao Microsoft Defender para Identidade](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Implantação do Microsoft Defender para Identidade](/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-365-defender"></a>Etapa 3: Ativar o Microsoft 365 Defender

[Microsoft 365 Defender](../security/defender/microsoft-365-defender.md) combina sinais e recursos de orquestração em uma única solução. Com a solução integrada Microsoft 365 Defender, os profissionais de segurança podem unir os sinais de ameaça que cada um desses produtos recebe e determinar o escopo completo e o impacto da ameaça; como ele entrou no ambiente, o que ele é afetado e como ele está afetando a organização no momento. Microsoft 365 O Defender toma medidas automáticas para impedir ou interromper o ataque e a auto-recuperação de caixas de correio afetadas, pontos de extremidade e identidades de usuário.

Microsoft 365 O Defender unifica alertas, incidentes, investigação e resposta automatizadas e busca avançada entre cargas de trabalho (Microsoft Defender para Identidade, Microsoft Defender para Office 365, Microsoft Defender para Ponto de Extremidade e Microsoft Cloud App Security) em um único painel de experiência de vidro. Novos recursos são adicionados continuamente ao Microsoft 365 Defender; considere optar por receber recursos de visualização.

### <a name="to-set-up-microsoft-365-defender"></a>Para configurar o Microsoft 365 Defender

![Processo de implantação do Microsoft 365 Defender](../media/deploy-threat-protection/deploy-mtp-steps.png) 

1. [Revise os pré-requisitos](../security/defender/prerequisites.md).
2. [A Microsoft 365 Defender](../security/defender/m365d-enable.md).
3. [Optar por recursos de visualização](../security/defender/preview.md).

### <a name="more-information-about-microsoft-365-defender"></a>Mais informações sobre o Microsoft 365 Defender

- [O que é o Microsoft 365 Defender?](../security/defender/microsoft-365-defender.md)
- [Novidades no Microsoft 365 Defender](../security/defender/whats-new.md)

## <a name="step-4-configure-microsoft-defender-for-office-365"></a>Etapa 4: Configurar o Microsoft Defender para Office 365

[O Microsoft Defender para Office 365](../security/office-365-security/defender-for-office-365.md) protege sua organização contra ameaças mal-intencionadas em mensagens de email (anexos e URLs), Office documentos e ferramentas de colaboração. A tabela a seguir lista o Microsoft Defender Office 365 recursos e recursos que estão incluídos no Microsoft 365 E5:

|Recursos de configuração, proteção e detecção|Recursos de automação, investigação, correção e educação|
|:---|:---|
|[Anexos Seguros](../security/office-365-security/safe-attachments.md)<br/>[Links Seguros](../security/office-365-security/safe-links.md)<br/>[Documentos Seguros](../security/office-365-security/safe-docs.md)<br/>[ATP para SharePoint, OneDrive e Microsoft Teams](../security/office-365-security/mdo-for-spo-odb-and-teams.md)<br/> [Proteção anti-phishing Microsoft 365](../security/office-365-security/anti-phishing-protection.md)|[Controladores de Ameaças](../security/office-365-security/threat-trackers.md)<br/>[Explorador de Ameaças](../security/office-365-security/threat-explorer.md)<br/>[Resposta e investigação automatizadas](../security/office-365-security/office-365-air.md)<br/>[Simulador de Ataque](../security/office-365-security/attack-simulator.md)|
|

Com o Microsoft Defender para Office 365, as pessoas em toda a sua organização podem se comunicar e colaborar com mais segurança, com proteção contra ameaças para o conteúdo de email e Office documentos.

### <a name="to-set-up-microsoft-defender-for-office-365"></a>Para configurar o Microsoft Defender para Office 365

![Processo de implantação do Microsoft Defender para Office 365](../media/deploy-threat-protection/deploy-office365-atp-steps.png) 

1. [Configure e configure o Microsoft Defender para políticas Office 365 .](../security/office-365-security/protect-against-threats.md)
2. [Exibir e usar o Microsoft Defender para Office 365 relatórios](../security/office-365-security/view-reports-for-mdo.md).
3. [Use recursos de investigação e resposta contra ameaças.](../security/office-365-security/office-365-ti.md)

### <a name="more-information-about-microsoft-defender-for-office-365"></a>Mais informações sobre o Microsoft Defender para Office 365

- [Visão geral do Microsoft Defender Office 365 visão geral](../security/office-365-security/defender-for-office-365.md)
- [Novidades do Microsoft Defender para Office 365](../security/office-365-security/whats-new-in-defender-for-office-365.md)

## <a name="step-5-configure-microsoft-defender-for-endpoint"></a>Etapa 5: Configurar o Microsoft Defender para Ponto de Extremidade

[O Microsoft Defender for Endpoint](/windows/security/threat-protection) protege seus dispositivos de organizações (também chamados de pontos de extremidade) contra ameaças cibernéticas, ataques avançados e violações de dados. As equipes de segurança podem ser mais eficientes no gerenciamento da segurança de seus pontos de extremidade. As ferramentas robustas ajudam as organizações a manterem os sistemas nãopatados usando a detecção de vulnerabilidades com o gerenciamento de ameaças [e vulnerabilidades.](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Recursos automatizados de detecção e correção, como redução de superfície de [ataque,](/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction)proteção de próxima [geração,](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) [detecção e resposta de ponto de extremidade](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)e investigação e [correção](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) automatizada ajudam a manter seus dispositivos seguros contra malware. Além desses recursos, os clientes podem receber notificações proativas e consultar o Especialistas em Ameaças da Microsoft sob demanda, como parte do serviço de busca gerenciada de aceitação. 


### <a name="set-up-microsoft-defender-for-endpoint"></a>Configurar o Microsoft Defender para Ponto de Extremidade

![Processo de implantação do Microsoft Defender para Ponto de Extremidade](../media/deploy-threat-protection/deploy-mdatp-steps.png) 

1. [Preparar seu ambiente para o Microsoft Defender para o Ponto de Extremidade](../security/defender-endpoint/deployment-phases.md).
2. [Implantar o Microsoft Defender para o Ponto de Extremidade](../security/defender-endpoint/production-deployment.md).
3. [Onboard to the Microsoft Defender for Endpoint service](../security/defender-endpoint/onboarding.md).
4. [Conclua suas principais tarefas administrativas de segurança.](../security/defender-endpoint/tvm-security-recommendation.md)

### <a name="more-information-about-microsoft-defender-for-endpoint"></a>Mais informações sobre o Microsoft Defender para Ponto de Extremidade

- [Saiba mais sobre o Microsoft Defender para Ponto de Extremidade](../security/defender-endpoint/microsoft-defender-endpoint.md).
- [Experimente o laboratório de avaliação do Microsoft Defender para Ponto de Extremidade.](../security/defender-endpoint/evaluation-lab.md)

## <a name="step-6-configure-microsoft-cloud-app-security"></a>Etapa 6: Configurar Microsoft Cloud App Security

[Microsoft Cloud App Security](/cloud-app-security) é um Agente de Segurança do Cloud Access que oferece suporte a conjunto de log, conectores de API e proxy reverso. Microsoft Cloud App Security fornece visibilidade avançada, controle sobre a viagem de dados e análises sofisticadas para identificar e combater ameaças cibernéticas em todos os seus serviços de nuvem. Com Microsoft Cloud App Security, suas operações de segurança podem proteger as informações confidenciais da sua organização, proteger contra ameaças cibernéticas e anomalias, descobrir e monitorar aplicativos que acessam os dados da sua organização e ajudar a garantir que os aplicativos de nuvem da sua organização atendem aos requisitos de conformidade.

### <a name="set-up-microsoft-cloud-app-security"></a>Configurar Microsoft Cloud App Security

![Processo de implantação de Microsoft Cloud App Security](../media/deploy-threat-protection/deploy-mcas-steps.png) 

1. [Configurar o portal e outros requisitos básicos.](/cloud-app-security/general-setup)
2. [Configurar a descoberta na nuvem](/cloud-app-security/set-up-cloud-discovery) e [conectar aplicativos](/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).
3. [Implantar o Controle de Aplicativo de Acesso Condicional para aplicativos em destaque.](/cloud-app-security/proxy-deployment-aad)
4. [Use as ferramentas de investigação e painéis](/cloud-app-security/investigate).

### <a name="more-information-about-microsoft-cloud-app-security"></a>Mais informações sobre o Microsoft Cloud App Security

- [Revise novos recursos e recursos.](/cloud-app-security/release-notes)
- [Saiba mais sobre Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security).

## <a name="step-7-monitor-status-and-take-actions"></a>Etapa 7: monitorar o status e tomar ações

Depois de configurar e implantar seus serviços e recursos de proteção contra ameaças, a próxima etapa é monitorar detecções de ameaças e tomar as ações apropriadas. Seu melhor ponto de partida é o Microsoft 365 de segurança ( ), onde você pode monitorar e gerenciar a segurança em suas [https://security.microsoft.com](https://security.microsoft.com) identidades, dados, dispositivos, aplicativos e infraestrutura da Microsoft. 

![Central de segurança do Microsoft 365](../media/solutions-architecture-center/m365-security-center.png)

O Microsoft 365 de segurança é destinado a administradores de segurança e equipes de operações de segurança. No centro Microsoft 365 segurança, você pode:
- Exibir a saúde geral da segurança da sua organização com [a Pontuação Segura.](/microsoft-365/security/defender/microsoft-secure-score)
- [Monitore e veja relatórios](../security/defender-endpoint/threat-protection-reports.md) sobre o status de suas identidades, dados, dispositivos, aplicativos e infraestrutura.
- Conexão os pontos em alertas por [meio de incidentes](/microsoft-365/security/defender/incident-queue).
- Use [investigação e correção automatizadas para](../security/defender/m365d-autoir.md) lidar com ameaças.
- [Busca proativamente por ameaças](/microsoft-365/security/defender/advanced-hunting-overview), como tentativas de invasão ou atividades de violação que afetam seus emails, dados, dispositivos e identidades.
- [Entenda as campanhas e](/microsoft-365/security/defender/latest-attack-campaigns) técnicas de ataque mais recentes com análise de ameaças.
- ... e muito mais!

### <a name="more-information-about-the-microsoft-365-security-center"></a>Mais informações sobre o Microsoft 365 de segurança

- [Começar com o centro de Microsoft 365 de segurança](../security/defender/overview-security-center.md).
- [Monitorar e exibir relatórios](../security/defender/overview-security-center.md).
- [Consulte os portais de segurança em Microsoft 365](../security/defender/portals.md).

## <a name="step-8-train-users"></a>Etapa 8: treinar usuários

Os usuários de treinamento podem salvar seus usuários e a equipe de operações de segurança por muito tempo e frustração. Os usuários experientes têm menos probabilidade de abrir anexos ou clicar em links em mensagens de email questionáveis, e é mais provável que eles evitem sites suspeitos. 

O Manual de Campanha de [Segurança](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) Cibernética da Escola De Harvard Kennedy fornece excelentes diretrizes sobre como estabelecer uma forte cultura de reconhecimento de segurança em sua organização, incluindo treinamento para que os usuários identifiquem ataques de phishing. 

Microsoft 365 fornece os seguintes recursos para ajudar a informar os usuários em sua organização:

|Conceito  |Recursos  |
|---------|---------|
|Microsoft 365     |[Caminhos de aprendizado personalizáveis](/office365/customlearning/) <p>Esses recursos podem ajudá-lo a montar o treinamento para usuários finais em sua organização        |
|Segurança do Microsoft 365 |[Módulo de aprendizagem: proteja sua organização com segurança interna e inteligente de Microsoft 365](/learn/modules/security-with-microsoft-365) <p>Esse módulo permite descrever como os recursos de segurança Microsoft 365 funcionam em conjunto e articular os benefícios desses recursos de segurança. |
|Autenticação multifator     | [Verificação em duas etapas: Qual é a página de verificação adicional?](/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Este artigo ajuda os usuários finais a entender o que é a autenticação multifatar e por que ela está sendo usada em sua organização.    |

Além dessas orientações, a Microsoft recomenda que seus usuários tomem as ações descritas neste artigo: Proteger sua conta e dispositivos [contra hackers e malware.](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx) Essas ações incluem:
- Usando senhas fortes
- Protegendo dispositivos 
- Habilitando recursos de segurança em computadores Windows 10 e Mac (para dispositivos sem gestão)
    
A Microsoft também recomenda que os usuários protejam suas contas de email pessoais, seguindo as ações recomendadas nos seguintes artigos:
- [Ajudar a proteger sua conta de email Outlook.com](https://support.microsoft.com/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [Proteger sua conta do Gmail com verificação em duas etapas](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
