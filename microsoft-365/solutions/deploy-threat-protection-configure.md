---
title: Etapas para configurar recursos de proteção contra ameaças no Microsoft 365
description: Saiba como implantar recursos e serviços de proteção contra ameaças no Microsoft 365 E5.
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-threatprotection
- m365solution-scenario
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 492db78c9aea881ae05dbc66f5e84ad98629b923
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931981"
---
# <a name="configure-threat-protection-capabilities-across-microsoft-365"></a>Configurar recursos de proteção contra ameaças no Microsoft 365

Siga estas etapas para configurar a proteção contra ameaças no Microsoft 365.


## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>Etapa 1: Configurar a autenticação multifacional e políticas de acesso condicional

[A MFA (autenticação multifatória)](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) exige que os usuários verifiquem sua identidade com uma chamada telefônica ou aplicativo autenticador. [As políticas de acesso](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) condicional definem determinados requisitos que devem ser atendidos para que os usuários acessem aplicativos e dados no Microsoft 365. A MFA e as políticas de acesso condicional funcionam em conjunto para proteger sua organização. Por exemplo, se alguém tentar entrar de um dispositivo móvel usando uma conta que não está habilitada para MFA e uma política de acesso condicional exigir que a MFA entre em vigor, esse usuário será impedido de entrar.  

A Microsoft testou e recomenda um conjunto específico de acesso condicional e políticas relacionadas para proteger o acesso a todos os seus aplicativos SaaS, especialmente o Microsoft 365. As políticas são recomendadas para proteção de linha de base, confidenciais e altamente controladas. Comece implementando as políticas de proteção de linha de base. 


[ ![ Políticas comuns para configurar o acesso a identidades e](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png) 
 [dispositivos. Veja uma versão maior desta imagem](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>Para implementar a proteção de linha de base para o Microsoft 365

![Processo de implantação da proteção de linha de base](../media/solutions-architecture-center/deploy-threat-protection-identity-access-steps.png) 

1. [Configure os pré-requisitos, incluindo o Azure Identity Protection.](../security/office-365-security/identity-access-prerequisites.md)
2. [Configure políticas comuns de identidade e acesso a dispositivos para](../security/office-365-security/identity-access-policies.md) proteção de linha de base.
3. Configurar políticas para [usuários convidados,](../security/office-365-security/identity-access-policies-guest-access.md) [Microsoft Teams,](../security/office-365-security/teams-access-policies.md) [Exchange Online,](../security/office-365-security/secure-email-recommended-policies.md) [SharePoint Online e OneDrive.](../security/office-365-security/sharepoint-file-access-policies.md)

### <a name="more-information-about-protecting-identities"></a>Mais informações sobre a proteção de identidades

- [Configurações de identidade e acesso a dispositivos](../security/office-365-security/microsoft-365-policies-configurations.md)
- [Diretrizes de segurança para o Azure MFA](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-microsoft-defender-for-identity"></a>Etapa 2: Configurar o Microsoft Defender para Identidade

O [Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) é uma solução de segurança baseada em nuvem que funciona com seus sinais locais do [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) para identificar, detectar e investigar ameaças avançadas, identidades comprometidas e ações internas mal-intencionadas direcionadas à sua organização.

O Microsoft Defender for Identity permite que analistas de operações de segurança (SecOps) e profissionais de segurança se esforçam para detectar ataques avançados em ambientes híbridos para:
- Monitore usuários, comportamento de entidade e atividades com análises baseadas em aprendizado.
- Proteger as identidades e credenciais do usuário armazenadas no Active Directory.
- Identificar e investigar atividades suspeitas do usuário e ataques avançados em toda a cadeia de extermínio.
- Fornecer informações claras sobre incidentes em uma linha do tempo simples para triagem rápida.

### <a name="to-set-up-microsoft-defender-for-identity"></a>Para configurar o Microsoft Defender para Identidade

![Processo de implantação do Microsoft Defender para Identidade](../media/solutions-architecture-center/deploy-azure-atp-steps.png) 

1. [Configurar o Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) para proteger seus ambientes principais.
2. Proteja todos os [controladores de domínio e](https://docs.microsoft.com/azure-advanced-threat-protection/atp-sensor-monitoring) [florestas.](https://docs.microsoft.com/azure-advanced-threat-protection/atp-multi-forest)
3. Integre [alertas do Microsoft Defender for Identity ao](https://docs.microsoft.com/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external) fluxo de trabalho de operações de segurança (SecOps).

### <a name="more-information-about-microsoft-defender-for-identity"></a>Mais informações sobre o Microsoft Defender para Identidade

- [O que é o Microsoft Defender para Identidade?](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Vídeo: Introdução ao Microsoft Defender para Identidade](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Implantação do Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-365-defender"></a>Etapa 3: Ativar o Microsoft 365 Defender

[O Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) combina sinais e orquestra recursos em uma única solução. Com a solução integrada do Microsoft 365 Defender, os profissionais de segurança podem unir os sinais de ameaça que cada um desses produtos recebe e determinar o escopo completo e o impacto da ameaça; como ele entrou no ambiente, o que é afetado e como ele está afetando a organização no momento. O Microsoft 365 Defender faz uma ação automática para impedir ou parar o ataque e auto-recuperar caixas de correio afetadas, pontos de extremidade e identidades de usuário.

O Microsoft 365 Defender unifica alertas, incidentes, investigação e resposta automatizadas e busca avançada entre cargas de trabalho (Microsoft Defender para Identidade, Microsoft Defender para Office 365, Microsoft Defender para Ponto de Extremidade e Microsoft Cloud App Security) em um único painel de experiência. Depois de configurar um ou mais dos serviços do Defender para Office 365, a ligue o Microsoft 365 Defender. Novos recursos são adicionados continuamente ao Microsoft 365 Defender; considere optar por receber recursos de visualização.

### <a name="to-set-up-microsoft-365-defender"></a>Para configurar o Microsoft 365 Defender

![Processo de implantação do Microsoft 365 Defender](../media/solutions-architecture-center/deploy-mtp-steps.png) 

1. [Revise os pré-requisitos.](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites)
2. [Ativar o Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)
3. [Opte por recursos de visualização.](https://docs.microsoft.com/microsoft-365/security/mtp/preview)

### <a name="more-information-about-microsoft-365-defender"></a>Mais informações sobre o Microsoft 365 Defender

- [O que é o Microsoft 365 Defender?](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
- [Novidades no Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)

## <a name="step-4-configure-microsoft-defender-for-office-365"></a>Etapa 4: Configurar o Microsoft Defender para Office 365

[O Microsoft Defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) protege sua organização contra ameaças mal-intencionadas em mensagens de email (anexos e URLs), documentos do Office e ferramentas de colaboração. A tabela a seguir lista os recursos e recursos do Microsoft Defender para Office 365 incluídos no Microsoft 365 E5:

|Recursos de configuração, proteção e detecção|Recursos de automação, investigação, correção e educação|
|---|---|
|[Anexos Seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br/>[Links Seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)<br/>[Documentos Seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)<br/>[ATP para SharePoint, OneDrive e Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)<br/>[Anti-phishing no Defender para proteção do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#exclusive-settings-in-atp-anti-phishing-policies)|[Controladores de Ameaças](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-trackers)<br/>[Explorador de Ameaças](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)<br/>[Resposta e investigação automatizadas](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)<br/>[Simulador de Ataque](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulator)|
|

Com o Microsoft Defender para Office 365, as pessoas em sua organização podem se comunicar e colaborar com mais segurança, com proteção contra ameaças para o conteúdo de email e documentos do Office.

### <a name="to-set-up-microsoft-defender-for-office-365"></a>Para configurar o Microsoft Defender para Office 365

![Processo de implantação do Microsoft Defender para Office 365](../media/solutions-architecture-center/deploy-office365-atp-steps.png) 

1. [Configure e configure as políticas do Microsoft Defender para Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)
2. [Exibir e usar seus relatórios do Microsoft Defender para Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)
3. [Usar recursos de investigação e resposta de ameaças.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti)

### <a name="more-information-about-microsoft-defender-for-office-365"></a>Mais informações sobre o Microsoft Defender para Office 365

- [Visão geral do Microsoft Defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)
- [Novidades no Microsoft Defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp)

## <a name="step-5-configure-microsoft-defender-for-endpoint"></a>Etapa 5: Configurar o Microsoft Defender para o Ponto de Extremidade

[O Microsoft Defender para Ponto](https://docs.microsoft.com/windows/security/threat-protection) de Extremidade protege seus dispositivos de organizações (também chamados de pontos de extremidade) contra ameaças cibernéticas, ataques avançados e violações de dados. As equipes de segurança podem ser mais eficientes no gerenciamento da segurança de seus pontos de extremidade. Ferramentas robustas ajudam as organizações a acompanhar os sistemas sem correção usando a detecção de vulnerabilidades com o gerenciamento [de ameaças e vulnerabilidades.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Recursos automatizados de detecção e correção, como redução [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)de superfície de [ataque,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction)proteção de próxima [geração,](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)detecção e resposta do ponto de extremidade e investigação e correção automatizadas ajudam a manter seus dispositivos seguros contra malware. [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) Além desses recursos, os clientes podem receber notificações proativas e consultar especialistas em ameaças da Microsoft sob demanda, como parte do serviço de busca gerenciada de aceitação. 


### <a name="set-up-microsoft-defender-for-endpoint"></a>Configurar o Microsoft Defender para o Ponto de Extremidade

![Processo de implantação do Microsoft Defender para Ponto de Extremidade](../media/solutions-architecture-center/deploy-mdatp-steps.png) 

1. [Prepare o Microsoft Defender para a implantação do ponto de extremidade.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases)
2. [Configurar o Microsoft Defender para implantação de ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection/micros.oft-defender-atp/production-deployment)
3. [Onboard to the Microsoft Defender for Endpoint service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboarding).
4. [Conclua suas principais tarefas administrativas de segurança.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)

### <a name="more-information-about-microsoft-defender-for-endpoint"></a>Mais informações sobre o Microsoft Defender para Ponto de Extremidade

- [Saiba mais sobre o Microsoft Defender para Ponto de Extremidade.](https://docs.microsoft.com/windows/security/threat-protection)
- [Experimente o laboratório de avaliação do Microsoft Defender for Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluation-lab)

## <a name="step-6-configure-microsoft-cloud-app-security"></a>Etapa 6: Configurar o Microsoft Cloud App Security

[O Microsoft Cloud App Security é](https://docs.microsoft.com/cloud-app-security) um Agente de Segurança de Acesso à Nuvem que oferece suporte à coleta de log, conectores de API e proxy reverso. O Microsoft Cloud App Security fornece visibilidade avançada, controle sobre viagens de dados e análises sofisticadas para identificar e combater ameaças cibernéticas em todos os seus serviços de nuvem. Com o Microsoft Cloud App Security, suas operações de segurança podem proteger as informações confidenciais da sua organização, proteger contra ameaças cibernéticas e anomalias, descobrir e monitorar aplicativos que acessam os dados da sua organização e ajudar a garantir que os aplicativos de nuvem da sua organização atendem aos requisitos de conformidade.

### <a name="set-up-microsoft-cloud-app-security"></a>Configurar o Microsoft Cloud App Security

![Processo de implantação do Microsoft Cloud App Security](../media/solutions-architecture-center/deploy-mcas-steps.png) 

1. [Configurar o portal e outros requisitos básicos.](https://docs.microsoft.com/cloud-app-security/general-setup)
2. [Configurar a descoberta na nuvem](https://docs.microsoft.com/cloud-app-security/set-up-cloud-discovery) e [conectar aplicativos.](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps)
3. [Implante o controle de aplicativo de acesso condicional para aplicativos em destaque.](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad)
4. [Use as ferramentas de investigação e painéis.](https://docs.microsoft.com/cloud-app-security/investigate)

### <a name="more-information-about-microsoft-cloud-app-security"></a>Mais informações sobre o Microsoft Cloud App Security

- [Revise os novos recursos e funcionalidades.](https://docs.microsoft.com/cloud-app-security/release-notes)
- [Saiba mais sobre o Microsoft Cloud App Security.](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)

## <a name="step-7-monitor-status-and-take-actions"></a>Etapa 7: Monitorar o status e tomar ações

Depois de configurar e implantar seus serviços e funcionalidades de proteção contra ameaças, sua próxima etapa é monitorar detecções de ameaças e tomar as ações apropriadas. Seu melhor ponto de partida é o centro de segurança do Microsoft 365 ( ), onde você pode monitorar e gerenciar a segurança em suas identidades, dados, dispositivos, aplicativos [https://security.microsoft.com](https://security.microsoft.com) e infraestrutura da Microsoft. 

![Centro de segurança do Microsoft 365](../media/solutions-architecture-center/m365-security-center.png)

O centro de segurança do Microsoft 365 destina-se especificamente a administradores de segurança e equipes de operações de segurança. Na central de segurança do Microsoft 365, você pode:
- Exibir a saúde geral de segurança da sua organização com a [Classificação de Segurança.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)
- [Monitore e veja relatórios](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting) sobre o status de suas identidades, dados, dispositivos, aplicativos e infraestrutura.
- Conecte os pontos em alertas por meio [de incidentes.](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- Use [investigação e correção automatizadas para](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir) lidar com ameaças.
- [Busca proativa por ameaças,](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview)como tentativas de invasão ou atividades de violação que afetem seu email, dados, dispositivos e identidades.
- [Entenda as campanhas e técnicas de ataque](https://docs.microsoft.com/microsoft-365/security/mtp/latest-attack-campaigns) mais recentes com a análise de ameaças.
- ... e muito mais!

### <a name="more-information-about-the-microsoft-365-security-center"></a>Mais informações sobre a central de segurança do Microsoft 365

- [Começar a trabalhar com a central de segurança do Microsoft 365.](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center)
- [Monitorar e exibir relatórios.](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting)
- [Confira os portais de segurança no Microsoft 365.](https://docs.microsoft.com/microsoft-365/security/mtp/portals)

## <a name="step-8-train-users"></a>Etapa 8: Treinar usuários

Os usuários de treinamento podem economizar muito tempo e frustração em suas equipes de operações de segurança e usuários. Os usuários experientes têm menos probabilidade de abrir anexos ou clicar em links em mensagens de email questionáveis, e é mais provável que eles evitem sites suspeitos. 

O Manual da Campanha de [Segurança Cibernética](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) da Escola Demão fornece excelentes orientações sobre como estabelecer uma cultura forte de reconhecimento de segurança em sua organização, incluindo treinamento dos usuários para identificar ataques de phishing. 

O Microsoft 365 fornece os seguintes recursos para ajudar a informar os usuários em sua organização:

|Conceito  |Recursos  |
|---------|---------|
|Microsoft 365     |[Caminhos de aprendizagem personalizáveis](https://docs.microsoft.com/office365/customlearning/) <p>Esses recursos podem ajudá-lo a reunir treinamento para usuários finais em sua organização        |
|Segurança do Microsoft 365 |[Módulo de aprendizagem: proteja sua organização com segurança interna e inteligente do Microsoft 365](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>Este módulo permite descrever como os recursos de segurança do Microsoft 365 funcionam juntos e articular os benefícios desses recursos de segurança. |
|Multi-factor Authentication     | [Verificação em duas etapas: Qual é a página de verificação adicional?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Este artigo ajuda os usuários finais a entender o que é a autenticação multifatare e por que ela está sendo usada em sua organização.    |

Além dessas diretrizes, a Microsoft recomenda que os usuários tomem as ações descritas neste artigo: proteger sua conta e dispositivos [contra hackers e malware.](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx) Essas ações incluem:
- Usando senhas fortes
- Protegendo dispositivos 
- Habilitando recursos de segurança em computadores Com Windows 10 e Mac (para dispositivos não-operacionais)
    
A Microsoft também recomenda que os usuários protejam suas contas de email pessoais seguindo as ações recomendadas nos seguintes artigos:
- [Ajudar a proteger sua Outlook.com de email](https://support.microsoft.com/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [Proteger sua conta do Gmail com verificação em duas etapas](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
