---
title: Roteiro de segurança do Microsoft 365 - Principais prioridades
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
audience: Admin
ms.topic: conceptual
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: Principais recomendações da equipe de segurança cibernética da Microsoft para implementar recursos de segurança para proteger seu ambiente do Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bd86262cd36d9482cd9a54e7fd7c336a6f0700dd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054229"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Roteiro de segurança - Principais prioridades para os primeiros 30 dias, 90 dias e além

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Este artigo inclui as principais recomendações da equipe de segurança cibernética da Microsoft para implementar recursos de segurança para proteger seu ambiente do Microsoft 365. Este artigo é adaptado de uma sessão do Microsoft Ignite — Proteja o Microsoft 365 como um profissional de segurança cibernética: principais prioridades para os primeiros [30 dias, 90](https://www.youtube.com/watch?v=luignzNyR-o)dias e além . Esta sessão foi desenvolvida e apresentada por Mark Simos e Matt Kemelhar, Arquitetos de Segurança Cibernética empresarial.

Neste artigo:

- [Resultados do roteiro](security-roadmap.md#Roadmap)
- [30 dias — vitórias rápidas poderosas](security-roadmap.md#Thirdaydays)
- [90 dias — proteções aprimoradas](security-roadmap.md#Ninetydays)
- [Além](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Resultados do roteiro
<a name="Roadmap"> </a>

Essas recomendações de roteiro são em estágios em três fases em uma ordem lógica com as seguintes metas.

****

|Quadro de tempo|Resultados|
|---|---|
|30 dias|Configuração rápida: <ul><li>Proteções básicas do administrador.</li><li>Log e análise.</li><li>Proteções básicas de identidade.</li></ul> <p> Configuração do locatário. <p> Preparar participantes.|
|90 dias|Proteções avançadas: <ul><li>Contas de administrador.</li><li>Dados e contas de usuário.</li></ul> <p> Visibilidade das necessidades de conformidade, ameaça e usuário. <p> Adapte e implemente políticas e proteções padrão.|
|Além|Ajustar e refinar políticas e controles de chave. <p> Estender proteções a dependências locais. <p> Integrar-se aos processos de negócios e segurança (ameaça legal, insider etc.).|
|

## <a name="30-days--powerful-quick-wins"></a>30 dias — vitórias rápidas poderosas
<a name="Thirdaydays"> </a>

Essas tarefas podem ser realizadas rapidamente e tem baixo impacto para os usuários.

****

|Área|Tarefas|
|---|---|
|Gerenciamento de segurança|<ul><li>Verifique a Pontuação Segura e anote sua pontuação atual ( <https://securescore.office.com> ).</li><li>Ativar o log de auditoria para o Office 365. Consulte [Pesquisar o log de auditoria](../../compliance/search-the-audit-log-in-security-and-compliance.md).</li><li>[Configure o Microsoft 365 para aumentar a segurança.](tenant-wide-setup-for-increased-security.md)</li><li>Revise regularmente painéis e relatórios no Centro de segurança do Microsoft 365 e no Cloud App Security.</li></ul>|
|Proteção contra ameaças|[Conecte o Microsoft 365](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) ao Microsoft Cloud App Security para iniciar o monitoramento usando as políticas padrão de detecção de ameaças para comportamentos anômalos. Leva sete dias para criar uma linha de base para detecção de anomalias. <p>  Implementar proteção para contas de administrador:<ul><li>Use contas de administrador dedicadas para atividades de administrador.</li><li>Impor a autenticação multifa factor (MFA) para contas de administrador.</li><li>Use um [dispositivo Windows 10 altamente seguro para](/windows-hardware/design/device-experiences/oem-highly-secure) atividades de administrador.</li></ul>|
|Gerenciamento de identidades e acesso|<ul><li>[Habilitar a Proteção de Identidade do Azure Active Directory](/azure/active-directory/active-directory-identityprotection-enable).</li><li>Para ambientes de identidade federados, impor a segurança da conta (comprimento da senha, idade, complexidade etc.).</li></ul>|
|Proteção de informações|Revise as recomendações de proteção de informações de exemplo. A proteção de informações requer coordenação em toda a sua organização. Comece a trabalhar com estes recursos:<ul><li>[Proteção de Informações do Office 365 para o RGPD](/compliance/regulatory/gdpr)</li><li>[Configurar o Teams com três camadas de proteção](../../solutions/configure-teams-three-tiers-protection.md) (inclui compartilhamento, classificação, prevenção contra perda de dados e Proteção de Informações do Azure)</li></ul>|
|

## <a name="90-days--enhanced-protections"></a>90 dias — proteções aprimoradas
<a name="Ninetydays"> </a>

Essas tarefas demoram um pouco mais para planejar e implementar, mas aumentam significativamente as condições de segurança.

****

|Área|Tarefa|
|---|---|
|Gerenciamento de segurança|<ul><li>Verifique a Pontuação Segura de ações recomendadas para seu ambiente ( <https://securescore.office.com> ).</li><li>Continue a revisar regularmente painéis e relatórios no centro de segurança do Microsoft 365, na Segurança do Aplicativo na Nuvem e nas ferramentas SIEM.</li><li>Procure e implemente atualizações de software.</li><li>Conduza simulações de ataque para ataques de phishing, pulverização de senha e força bruta usando o [Simulador](attack-simulator.md) de Ataques (incluído no [Office 365 Threat Intelligence](office-365-ti.md)).</li><li>Procure o risco de compartilhamento revisando os relatórios integrados no Cloud App Security (na guia Investigar).</li><li>Verifique [o Gerenciador de](../../compliance/compliance-manager.md) Conformidade para revisar o status dos regulamentos que se aplicam à sua organização (como o RGPD, NIST 800-171).</li></ul>|
|Proteção contra ameaças|Implementar proteções aprimoradas para contas de administrador: <ul><li>Configure [As Estações de Trabalho de](/security/compass/privileged-access-devices) Acesso Privilegiado (PAWs) para atividade de administrador.</li><li>Configurar [o Azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure).</li><li>Configure uma ferramenta de gerenciamento de eventos e informações de segurança (SIEM) para coletar dados de registro em log do Office 365, Segurança do Aplicativo na Nuvem e outros serviços, incluindo o AD FS. O log de auditoria armazena dados por apenas 90 dias. Capturar esses dados na ferramenta SIEM permite armazenar dados por um período mais longo.</li></ul>|
|Gerenciamento de identidades e acesso|<ul><li>Habilitar e impor o MFA para todos os usuários.</li><li>Implemente um conjunto [de acesso condicional e políticas relacionadas.](microsoft-365-policies-configurations.md)</li></ul>|
|Proteção de informações| Adapte e implemente políticas de proteção de informações. Esses recursos incluem exemplos: <ul><li>[Proteção de Informações do Office 365 para o RGPD](/compliance/regulatory/gdpr)</li><li>[Configure equipes com três níveis de proteção](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> Use políticas de prevenção contra perda de dados e ferramentas de monitoramento no Microsoft 365 para dados armazenados no Microsoft 365 (em vez de Segurança do Aplicativo na Nuvem). <p> Use o Cloud App Security com o Microsoft 365 para recursos avançados de alerta (diferente da prevenção contra perda de dados).|
|

## <a name="beyond"></a>Além
<a name="Beyond"> </a>

Estas são medidas de segurança importantes que se baseam no trabalho anterior.

****

|Área|Tarefa|
|---|---|
|Gerenciamento de segurança|<ul><li>Continue planejando as próximas ações usando a Pontuação Segura ( <https://securescore.office.com> ).</li><li>Continue a revisar regularmente painéis e relatórios no centro de segurança do Microsoft 365, na Segurança do Aplicativo na Nuvem e nas ferramentas SIEM.</li><li>Continue procurando e implementando atualizações de software.</li><li>Integre a Descoberta E Aos seus processos legais e de resposta a ameaças.</li></ul>|
|Proteção contra ameaças|<ul><li>Implemente [o Acesso Privilegiado Seguro](/windows-server/identity/securing-privileged-access/securing-privileged-access) (SPA) para componentes de identidade no local (AD, AD FS).</li><li>Use o Cloud App Security para monitorar ameaças internas.</li><li>Descubra o uso do SaaS de IT de sombra usando o Cloud App Security.</li></ul>|
|Gerenciamento de identidades e acesso|<ul><li>Refine políticas e processos operacionais.</li><li>Use a Proteção de Identidade do Azure AD para identificar ameaças internas.</li></ul>|
|Proteção de informações|Refine as políticas de proteção de informações: <ul><li>Rótulos de sensibilidade do Microsoft 365 e Office 365 e prevenção contra perda de dados (DLP) ou Proteção de Informações do Azure.</li><li>Políticas e alertas de Segurança de Aplicativos na Nuvem.</li></ul>|
|

Consulte também: [Como reduzir ataques cibernéticos rápidos, como Petya e WannaCrypt.](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)