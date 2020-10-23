---
title: Etapas para configurar os recursos de proteção contra ameaças no Microsoft 365
description: Saiba como implantar serviços e recursos de proteção contra ameaças no Microsoft 365 e5.
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-threatprotection
- m365solution-scenario
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 7699b31052ecc1bda33630fcf97e9d43875f4ae3
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681585"
---
# <a name="configure-threat-protection-capabilities-across-microsoft-365"></a>Configurar recursos de proteção contra ameaças no Microsoft 365

Siga estas etapas para configurar a proteção contra ameaças no Microsoft 365.


## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>Etapa 1: configurar as políticas de acesso condicional e de autenticação multifator

A MFA ( [autenticação multifator](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) ) exige que os usuários verifiquem sua identidade com uma chamada telefônica ou um aplicativo autenticador. [As políticas de acesso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) definem determinados requisitos que devem ser atendidos para que os usuários acessem aplicativos e dados no Microsoft 365. As políticas de acesso condicional e MFA trabalham juntas para proteger sua organização. Por exemplo, se alguém tentar entrar a partir de um dispositivo móvel usando uma conta que não está habilitada para MFA, e uma política de acesso condicional exigir que a MFA esteja em vigor, esse usuário será impedido de entrar.  

A Microsoft testou e recomenda um conjunto específico de acesso condicional e políticas relacionadas para proteger o acesso a todos os aplicativos SaaS, especialmente o Microsoft 365. As políticas são recomendadas para proteção de linha de base, confidencial e altamente regulamentada. Comece implementando as políticas de proteção de linha de base. 


[ ![ Políticas comuns para configurar a identidade e o acesso ao dispositivo](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png) 
 [consulte uma versão maior desta imagem](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>Para implementar a proteção de linha de base para o Microsoft 365

![Processo de implantação da proteção de linha de base](../media/solutions-architecture-center/deploy-threat-protection-identity-access-steps.png) 

1. [Configure os pré-requisitos, incluindo a proteção de identidade do Azure](../security/office-365-security/identity-access-prerequisites.md).
2. [Configure as políticas comuns de acesso de dispositivo e identidade](../security/office-365-security/identity-access-policies.md) para a proteção de linha de base.
3. Configure políticas para [usuários convidados](../security/office-365-security/identity-access-policies-guest-access.md), [Microsoft Teams](../security/office-365-security/teams-access-policies.md), [Exchange Online](../security/office-365-security/secure-email-recommended-policies.md)e [SharePoint Online e onedrive](../security/office-365-security/sharepoint-file-access-policies.md).

### <a name="more-information-about-protecting-identities"></a>Mais informações sobre como proteger identidades

- [Configurações de identidade e acesso a dispositivos](../security/office-365-security/microsoft-365-policies-configurations.md)
- [Diretrizes de segurança para o Azure MFA](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-azure-advanced-threat-protection"></a>Etapa 2: configurar a proteção avançada contra ameaças do Azure

A [proteção avançada contra ameaças do Azure](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) (Azure ATP) é uma solução de segurança baseada em nuvem que funciona com seus sinais do [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) local para identificar, detectar e investigar ameaças avançadas, identidades comprometidas e ações mal-intencionadas intencionais direcionadas para sua organização.

O Azure ATP permite que as operações de segurança (SecOps) analistas e profissionais de segurança tenham dificuldade para detectar ataques avançados em ambientes híbridos para:
- Monitorar usuários, comportamento de entidade e atividades com análise baseada em aprendizado.
- Proteger as identidades e credenciais do usuário armazenadas no Active Directory.
- Identificar e investigar atividades suspeitas do usuário e ataques avançados em toda a cadeia de extermínio.
- Fornecer informações claras sobre incidentes em uma linha do tempo simples para triagem rápida.

### <a name="to-set-up-azure-atp"></a>Para configurar a ATP do Azure

![Processo de implantação do Azure ATP](../media/solutions-architecture-center/deploy-azure-atp-steps.png) 

1. [Configure o Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) para proteger seus ambientes principais.
2. Proteger todos os [controladores de domínio](https://docs.microsoft.com/azure-advanced-threat-protection/atp-sensor-monitoring) e [florestas](https://docs.microsoft.com/azure-advanced-threat-protection/atp-multi-forest).
3. Integre os [alertas do Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external) ao seu fluxo de trabalho de operações de segurança (SecOps).

### <a name="more-information-about-azure-atp"></a>Mais informações sobre o Azure ATP

- [O que é o Azure ATP?](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Vídeo: introdução ao Azure ATP](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Implantação do Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-threat-protection"></a>Etapa 3: ativar a proteção contra ameaças da Microsoft

A [proteção contra ameaças da Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) combina sinais e orquestra recursos em uma única solução. Com a solução integrada de proteção contra ameaças da Microsoft, os profissionais de segurança podem unir os sinais de ameaça de que cada um desses produtos recebe e determinam o escopo completo e o impacto da ameaça; como ele entrou no ambiente, o que ele é afetado e como ele está afetando a organização no momento. A proteção contra ameaças da Microsoft realiza ações automáticas para impedir ou interromper o ataque e a AutoCorreção de caixas de correio, pontos de extremidade e identidades de usuários afetados.

A proteção contra ameaças da Microsoft unifica alertas, incidentes, investigação e resposta automatizadas e busca avançada entre cargas de trabalho (Azure ATP, Office 365 ATP, Microsoft defender ATP e Microsoft Cloud app Security) em um único painel de experiência de vidro. Depois de configurar um ou mais serviços avançados de proteção contra ameaças, ative a proteção contra ameaças da Microsoft. Novos recursos são adicionados continuamente à proteção contra ameaças da Microsoft; Considere optar por receber recursos de visualização.

### <a name="to-set-up-microsoft-threat-protection"></a>Para configurar a proteção contra ameaças da Microsoft

![Processo de implantação da proteção contra ameaças da Microsoft](../media/solutions-architecture-center/deploy-mtp-steps.png) 

1. [Examine os pré-requisitos](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites).
2. [Ative a proteção contra ameaças da Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable).
3. [Aceitar recursos de visualização](https://docs.microsoft.com/microsoft-365/security/mtp/preview).

### <a name="more-information-about-microsoft-threat-protection"></a>Mais informações sobre a proteção contra ameaças da Microsoft

- [O que é a Proteção contra Ameaças da Microsoft?](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
- [Novidades da Proteção contra Ameaças da Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)

## <a name="step-4-configure-office-365-advanced-threat-protection"></a>Etapa 4: configurar a proteção avançada contra ameaças do Office 365

A [proteção avançada contra ameaças do office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) protege sua organização contra ameaças mal-intencionadas em mensagens de email (anexos e URLs), documentos do Office e ferramentas de colaboração. A tabela a seguir lista os recursos e recursos de ATP do Office 365 que estão incluídos no Microsoft 365 E5:

|Recursos de configuração, proteção e detecção|Recursos de automação, investigação, correção e educação|
|---|---|
|[Anexos Seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br/>[Links Seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)<br/>[Documentos Seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)<br/>[ATP para SharePoint, OneDrive e Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)<br/>[Proteção antiphishing ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#exclusive-settings-in-atp-anti-phishing-policies)|[Controladores de Ameaças](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-trackers)<br/>[Explorador de Ameaças](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)<br/>[Resposta e investigação automatizadas](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)<br/>[Simulador de Ataque](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulator)|
|

Com o Office 365 ATP, as pessoas em sua organização podem se comunicar e colaborar com mais segurança, com proteção contra ameaças para seus documentos de conteúdo de email e do Office.

### <a name="to-set-up-office-365-atp"></a>Para configurar o Office 365 ATP

![Processo de implantação do Office 365 ATP](../media/solutions-architecture-center/deploy-office365-atp-steps.png) 

1. [Configurar e configurar as políticas de ATP do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).
2. [Exibir e usar seus relatórios de ATP do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp).
3. [Use os recursos de investigação e resposta de ameaças](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti).

### <a name="more-information-about-office-365-atp"></a>Mais informações sobre o Office 365 ATP

- [Visão geral da ATP do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)
- [Novidades na ATP do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp)

## <a name="step-5-configure-microsoft-defender-advanced-threat-protection"></a>Etapa 5: configurar a proteção avançada contra ameaças do Microsoft defender

A [proteção avançada contra ameaças do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft defender ATP) protege seus dispositivos de organização (também chamados de pontos de extremidade) de ciberataques, ataques avançados e violações de dados. As equipes de segurança podem ser mais eficientes no gerenciamento da segurança de seus pontos de extremidade. Ferramentas robustas ajudam as organizações a acompanhar sistemas sem patch usando a detecção de vulnerabilidades com [Gerenciamento de ameaças e vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). Recursos automatizados de detecção e correção, [como redução da superfície de ataque](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction), proteção de [última geração](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10), [detecção e resposta de ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)e [investigação e resolução automatizadas](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) ajudam a manter seus dispositivos seguros contra malware. Além desses recursos, os clientes podem obter notificações proativas e consultar especialistas de ameaças da Microsoft sob demanda, como parte do serviço de busca gerenciado de consentimento. 


### <a name="set-up-microsoft-defender-atp"></a>Configurar o Microsoft defender ATP

![Processo de implantação do Microsoft defender ATP](../media/solutions-architecture-center/deploy-mdatp-steps.png) 

1. [Prepare sua implantação do Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases).
2. [Configurar sua implantação do Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/micros.oft-defender-atp/production-deployment)
3. [Integrado ao serviço Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboarding).
4. [Conclua suas principais tarefas administrativas de segurança](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation).

### <a name="more-information-about-microsoft-defender-atp"></a>Mais informações sobre o Microsoft defender ATP

- [Saiba mais sobre o Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection).
- [Experimente o laboratório de avaliação do Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluation-lab).

## <a name="step-6-configure-microsoft-cloud-app-security"></a>Etapa 6: configurar o Microsoft Cloud app Security

[O Microsoft Cloud app Security](https://docs.microsoft.com/cloud-app-security) é um agente de segurança de acesso à nuvem que oferece suporte a coleta de logs, conectores de API e proxy reverso. O Microsoft Cloud app Security oferece visibilidade avançada, controle sobre a viagem de dados e análises sofisticadas para identificar e combater o ciberataques em todos os seus serviços de nuvem. Com o Microsoft Cloud app Security, suas operações de segurança podem proteger as informações confidenciais da sua organização, proteger contra ciberataques e anomalias, descobrir e monitorar aplicativos que acessam os dados da sua organização e ajudar a garantir que os aplicativos de nuvem da sua organização atendam aos requisitos de conformidade.

### <a name="set-up-microsoft-cloud-app-security"></a>Configurar o Microsoft Cloud app Security

![Processo de implantação do Microsoft Cloud app Security](../media/solutions-architecture-center/deploy-mcas-steps.png) 

1. [Configurar o portal e outros requisitos básicos](https://docs.microsoft.com/cloud-app-security/general-setup).
2. [Configurar a descoberta de nuvem](https://docs.microsoft.com/cloud-app-security/set-up-cloud-discovery) e [conectar aplicativos](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).
3. [Implante o controle de aplicativo de acesso condicional para aplicativos em destaque](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad).
4. [Use as ferramentas e os painéis de investigação](https://docs.microsoft.com/cloud-app-security/investigate).

### <a name="more-information-about-microsoft-cloud-app-security"></a>Mais informações sobre o Microsoft Cloud App Security

- [Analise os novos recursos e funcionalidades](https://docs.microsoft.com/cloud-app-security/release-notes).
- [Saiba mais sobre o Microsoft Cloud app Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).

## <a name="step-7-monitor-status-and-take-actions"></a>Etapa 7: monitorar o status e realizar ações

Após configurar e implantar seus serviços e recursos de proteção contra ameaças, a próxima etapa é monitorar as detecções de ameaças e tomar as medidas apropriadas. O melhor ponto de partida é o centro de segurança do Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ), onde você pode monitorar e gerenciar a segurança em suas identidades, dados, dispositivos, aplicativos e infraestrutura da Microsoft. 

![Centro de segurança do Microsoft 365](../media/solutions-architecture-center/m365-security-center.png)

A central de segurança do Microsoft 365 destina-se especificamente às equipes de administradores de segurança e operações de segurança. No centro de segurança do Microsoft 365, você pode:
- Veja a integridade geral da segurança da sua organização com [Pontuação segura](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).
- [Monitore e exiba relatórios](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting) sobre o status de suas identidades, dados, dispositivos, aplicativos e infraestrutura.
- Conecte os pontos em alertas por meio de [incidentes](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue).
- Use a [investigação e a correção automatizadas](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir) para lidar com ameaças.
- Procurar [ameaças de forma proativa](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview), como tentativas de invasão ou atividade de violação que afetem seus emails, dados, dispositivos e identidades.
- [Entenda as campanhas e as técnicas de ataque mais recentes com a análise de](https://docs.microsoft.com/microsoft-365/security/mtp/latest-attack-campaigns) ameaças.
- ... e muito mais!

### <a name="more-information-about-the-microsoft-365-security-center"></a>Mais informações sobre o centro de segurança do Microsoft 365

- [Introdução à central de segurança do Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center).
- [Monitorar e exibir relatórios](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting).
- [Consulte os portais de segurança no Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/portals).

## <a name="step-8-train-users"></a>Etapa 8: treinar os usuários

O treinamento de usuários pode economizar seus usuários e a equipe de operações de segurança muito tempo e frustração. Os usuários experientes têm menos probabilidade de abrir anexos ou clicar em links em mensagens de email questionáveis, e eles provavelmente evitarão sites suspeitos. 

O [manual de campanha](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) da Harvard Kennedy School cybersecurity fornece orientações excelentes sobre o estabelecimento de uma grande cultura de reconhecimento de segurança em sua organização, incluindo o treinamento de usuários para identificar ataques de phishing. 

A Microsoft 365 fornece os seguintes recursos para ajudar a informar os usuários em sua organização:

|Conceito  |Recursos  |
|---------|---------|
|Microsoft 365     |[Caminhos de aprendizado personalizáveis](https://docs.microsoft.com/office365/customlearning/) <p>Esses recursos podem ajudá-lo a reunir o treinamento para os usuários finais em sua organização        |
|Segurança do Microsoft 365 |[Módulo de aprendizado: proteger sua organização com segurança integrada e interna da Microsoft 365](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>Este módulo permite descrever como os recursos de segurança da Microsoft 365 trabalham juntos e articulam os benefícios desses recursos de segurança. |
|Autenticação multifator     | [Verificação em duas etapas: o que é a página de verificação adicional?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Este artigo ajuda os usuários finais a entender o que é a autenticação multifator e por que ela está sendo usada na sua organização.    |

Além desta orientação, a Microsoft recomenda que os usuários executem as ações descritas neste artigo: [proteja sua conta e seus dispositivos contra hackers e malware](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx). Essas ações incluem:
- Usando senhas fortes
- Protegendo dispositivos 
- Habilitar recursos de segurança nos PCs com Windows 10 e Mac (para dispositivos não gerenciados)
    
A Microsoft também recomenda que os usuários protejam suas contas de email pessoais executando as ações recomendadas nos seguintes artigos:
- [Ajudar a proteger sua conta de email do Outlook.com](https://support.microsoft.com/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [Proteger sua conta do Gmail com a verificação em duas etapas](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
