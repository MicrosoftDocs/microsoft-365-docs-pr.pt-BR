---
title: Mapa de segurança da Microsoft 365-principais prioridades
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: 'Principais recomendações da equipe do cybersecurity da Microsoft para a implementação de recursos de segurança para proteger seu ambiente do Microsoft 365. '
ms.openlocfilehash: d62db9206a98078ae5adaad220a7c9b53ff116cd
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561688"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Mapa de segurança-principais prioridades para os primeiros 30 dias, 90 dias e depois

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Este artigo inclui as principais recomendações da equipe do cybersecurity da Microsoft para a implementação de recursos de segurança para proteger seu ambiente do Microsoft 365. Este artigo é adaptado de uma sessão do Microsoft Ignite — [Secure microsoft 365 like a cybersecurity pro: Top prioridades para os primeiros 30 dias, 90 dias e além](https://www.youtube.com/watch?v=luignzNyR-o). Esta sessão foi desenvolvida e apresentada por Mark Simos e Matt Kemelhar, Enterprise cybersecurity Architects.

Nesse artigo:

- [Resultados do roteiro](security-roadmap.md#Roadmap)
- [30 dias — rápido WINS avançado](security-roadmap.md#Thirdaydays)
- [90 dias — proteções aprimoradas](security-roadmap.md#Ninetydays)
- [Deles](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Resultados do roteiro
<a name="Roadmap"> </a>

Essas recomendações de roteiro são testadas em três fases em uma ordem lógica com os seguintes objetivos.

****

|Intervalo de tempo|Resultados|
|---|---|
|30 dias|Configuração rápida: <ul><li>Proteção básica de administradores.</li><li>Registro em log e análise.</li><li>Proteções de identidade básica.</li></ul> <p> Configuração do locatário. <p> Preparar participantes.|
|90 dias|Proteções avançadas: <ul><li>Contas de administrador.</li><li>Dados e contas de usuário.</li></ul> <p> Visibilidade das necessidades de conformidade, ameaça e usuário. <p> Adaptar e implementar políticas e proteções padrão.|
|Deles|Ajustar e refinar políticas e controles de chave. <p> Estenda as proteções para dependências locais. <p> Integre com processos de segurança e de negócios (jurídico, ameaça de insider, etc.).|
|

## <a name="30-days--powerful-quick-wins"></a>30 dias — rápido WINS avançado
<a name="Thirdaydays"> </a>

Essas tarefas podem ser realizadas rapidamente e tem baixo impacto para os usuários.

****

|Área|Tarefas|
|---|---|
|Gerenciamento de segurança|<ul><li>Verifique a pontuação segura e anote sua pontuação atual ( <https://securescore.office.com> ).</li><li>Ative o log de auditoria do Office 365. Confira [Pesquisar o log de auditoria](../../compliance/search-the-audit-log-in-security-and-compliance.md).</li><li>[Configure o Microsoft 365 para maior segurança](tenant-wide-setup-for-increased-security.md).</li><li>Revise regularmente painéis e relatórios no centro de segurança do Microsoft 365 e no Cloud app Security.</li></ul>|
|Proteção contra Ameaças|[Conecte o microsoft 365 ao Microsoft Cloud app Security](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) para iniciar o monitoramento usando as políticas de detecção de ameaças padrão para comportamentos anormais. Leva sete dias para criar uma linha de base para detecção de anomalias. <p>  Implementar proteção para contas de administrador:<ul><li>Use contas de administrador dedicadas para atividades de administração.</li><li>Aplicar a MFA (autenticação multifator) para contas de administrador.</li><li>Use um [dispositivo Windows 10 altamente seguro](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) para a atividade de administração.</li></ul>|
|Gerenciamento de identidades e acesso|<ul><li>[Habilitar a proteção de identidade do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</li><li>Para ambientes de identidade federada, impor segurança de conta (comprimento da senha, idade, complexidade, etc.).</li></ul>|
|Proteção de informações|Revisar exemplos de recomendações de proteção de informações. A proteção de informações exige coordenação em toda a organização. Comece a trabalhar com estes recursos:<ul><li>[Proteção de Informações do Office 365 para o RGPD](https://aka.ms/o365gdpr)</li><li>[Configurar o Microsoft Teams com três camadas de proteção](../../solutions/configure-teams-three-tiers-protection.md) (inclui compartilhamento, classificação, prevenção de perda de dados e proteção de informações do Azure)</li></ul>|
|

## <a name="90-days--enhanced-protections"></a>90 dias — proteções aprimoradas
<a name="Ninetydays"> </a>

Essas tarefas demoram um pouco mais para planejar e implementar, mas aumentam significativamente as condições de segurança.

****

|Área|Tarefas|
|---|---|
|Gerenciamento de segurança|<ul><li>Verifique a pontuação segura para as ações recomendadas para seu ambiente ( [https://securescore.office.com](https://securescore.office.com) ).</li><li>Continue a examinar regularmente painéis e relatórios no centro de segurança do Microsoft 365, no Cloud app Security e nas ferramentas SIEM.</li><li>Procure e implemente as atualizações de software.</li><li>Conduzir simulações de ataque para os ataques de senhas de spear-phishing, de irrigação de senha e de força bruta usando o [Attack Simulator](attack-simulator.md) (incluído no [Office 365 Threat Intelligence](office-365-ti.md)).</li><li>Procure por compartilhar riscos examinando os relatórios internos no Cloud app Security (na guia investigar).</li><li>Verifique o [Gerenciador de conformidade](https://docs.microsoft.com/microsoft-365/compliance/compliance-manager) para analisar o status das regulamentações que se aplicam à sua organização (como RGPD, NIST 800-171).</li></ul>|
|Proteção contra Ameaças|Implementar proteções aprimoradas para contas de administrador: <ul><li>Configure o PAWs ( [estações de trabalho privilegiadas](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) ) para atividades de administração.</li><li>Configure o [Azure ad Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</li><li>Configure a ferramenta de gerenciamento de eventos e informações de segurança (SIEM) para coletar dados de log do Office 365, do Cloud app Security e de outros serviços, incluindo o AD FS. O log de auditoria armazena dados por apenas 90 dias. A captura desses dados na ferramenta SIEM permite que você armazene dados por um período mais longo.</li></ul>|
|Gerenciamento de identidades e acesso|<ul><li>Habilitar e impor a MFA para todos os usuários.</li><li>Implementar um conjunto de [acesso condicional e políticas relacionadas](microsoft-365-policies-configurations.md).</li></ul>|
|Proteção de informações| Adaptar e implementar políticas de proteção de informações. Esses recursos incluem exemplos: <ul><li>[Proteção de Informações do Office 365 para o RGPD](https://aka.ms/o365gdpr)</li><li>[Configurar equipes com três camadas de proteção](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> Use políticas de prevenção de perda de dados e ferramentas de monitoramento no Microsoft 365 para dados armazenados no Microsoft 365 (em vez de segurança do Cloud app). <p> Use o Cloud app Security com o Microsoft 365 para recursos avançados de alerta (diferentes de prevenção de perda de dados).|
|

## <a name="beyond"></a>Deles
<a name="Beyond"> </a>

Essas são medidas de segurança importantes que são criadas no trabalho anterior.

****

|Área|Tarefas|
|---|---|
|Gerenciamento de segurança|<ul><li>Continue planejando as próximas ações usando a pontuação segura ( <https://securescore.office.com> ).</li><li>Continue a examinar regularmente painéis e relatórios no centro de segurança do Microsoft 365, no Cloud app Security e nas ferramentas SIEM.</li><li>Continue a procurar e implementar atualizações de software.</li><li>Integre a descoberta eletrônica em seus processos de resposta legal e de ameaça.</li></ul>|
|Proteção contra Ameaças|<ul><li>Implementar o [acesso privilegiado seguro](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (Spa) para componentes de identidade no local (AD, AD FS).</li><li>Use o Cloud app Security para monitorar ameaças Insider.</li><li>Descobrir o uso do SaaS de ti de sombra usando o Cloud app Security.</li></ul>|
|Gerenciamento de identidades e acesso|<ul><li>Refine políticas e processos operacionais.</li><li>Use o Azure AD Identity Protection para identificar as ameaças Insider.</li></ul>|
|Proteção de informações|Refinar políticas de proteção de informações: <ul><li>Microsoft 365 e Office 365 rótulos de sensibilidade e prevenção de perda de dados (DLP) ou proteção de informações do Azure.</li><li>Políticas e alertas do Cloud app Security.</li></ul>|
|

Consulte também: [como mitigar cyberattacks rápidos, como Petya e WannaCrypt](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/).
