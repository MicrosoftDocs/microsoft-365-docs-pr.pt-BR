---
title: Mapa de segurança do Office 365-principais prioridades para os primeiros 30 dias, 90 dias e além de
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
description: 'Principais recomendações da equipe do cybersecurity da Microsoft para a implementação de recursos de segurança para proteger seu ambiente do Office 365. '
ms.openlocfilehash: ab2d780ff947ac829ba2565cf3fd142208fcf8b0
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38627565"
---
# <a name="office-365-security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Mapa de segurança do Office 365-principais prioridades para os primeiros 30 dias, 90 dias e além de

Este artigo inclui as principais recomendações da equipe do cybersecurity da Microsoft para a implementação de recursos de segurança para proteger seu ambiente do Office 365. Este artigo é adaptado de uma sessão do Microsoft Ignite — [Secure Office 365 like a cybersecurity pro: principais prioridades para os primeiros 30 dias, 90 dias e além](https://www.youtube.com/watch?v=luignzNyR-o). Esta sessão foi desenvolvida e apresentada por Mark Simos e Matt Kemelhar, Enterprise cybersecurity Architects.
  
Neste artigo:
  
- [Resultados do roteiro](security-roadmap.md#Roadmap)
    
- [30 dias — rápido WINS avançado](security-roadmap.md#Thirdaydays)
    
- [90 dias — proteções aprimoradas](security-roadmap.md#Ninetydays)
    
- [Deles](security-roadmap.md#Beyond)
    
## <a name="roadmap-outcomes"></a>Resultados do roteiro
<a name="Roadmap"> </a>

Essas recomendações de roteiro são testadas em três fases em uma ordem lógica com os seguintes objetivos.

|||
|:-----|:-----|
| |Resultados
|30 dias|Configuração rápida:  <br/> • Proteções básicas de administração  <br/> • Registro em log e análise  <br/> • Proteções de identidade básica  <br/> Configuração do locatário  <br/>  Preparar participantes  <br/> |
|90 dias|Proteções avançadas:  <br/> • Contas de administrador  <br/>  • Contas &amp; de usuário de dados  <br/>  Visibilidade das necessidades de conformidade, ameaça e usuário  <br/>  Adaptar e implementar políticas e proteções padrão  <br/> |
|Deles|Ajustar e refinar políticas e controles de chave  <br/> Estender as proteções para dependências locais  <br/> Integração com processos de segurança e de negócios (jurídico, ameaça de insider, etc.)  <br/> |
  

   
## <a name="30-days--powerful-quick-wins"></a>30 dias — rápido WINS avançado
<a name="Thirdaydays"> </a>

Essas tarefas podem ser realizadas rapidamente e tem baixo impacto para os usuários.
  
|||
|:-----|:-----|
|Área  <br/> |Tarefas  <br/> |
|Gerenciamento de segurança  <br/> |• Verifique a pontuação segura e anote sua pontuação atual ( [https://securescore.office.com](https://securescore.office.com)).  <br/>  • Ative o log de auditoria do Office 365. Confira [Pesquisar o log de auditoria](../../compliance/search-the-audit-log-in-security-and-compliance.md).  <br/> • [Configure seu locatário do Office 365 para maior segurança](tenant-wide-setup-for-increased-security.md) .  <br/>  • Revise regularmente painéis e relatórios no centro de segurança do Microsoft 365 e no Cloud app Security.  <br/> |
|Proteção contra Ameaças  <br/> |[Conecte o Office 365 ao Microsoft Cloud app Security](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) para iniciar o monitoramento usando as políticas de detecção de ameaças padrão para comportamentos anormais. Leva sete dias para criar uma linha de base para detecção de anomalias.  <br><br/>  Implementar proteção para contas de administrador:  <br/> • Use contas de administrador dedicadas para atividades de administração.  <br/>  • Aplicar a MFA (autenticação multifator) para contas de administrador.  <br/>  • Use um [dispositivo Windows 10 altamente seguro](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) para a atividade de administração.  <br/> |
|Gerenciamento de identidades e acesso  <br/> |• [Habilitar a proteção de identidade do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).  <br/> • Para ambientes de identidade federada, reforçar a segurança da conta (comprimento da senha, idade, complexidade, etc.).  <br/> |
|Proteção de informações  <br/> | Revisar exemplos de recomendações de proteção de informações. A proteção de informações exige coordenação em toda a organização. Comece a trabalhar com estes recursos:  <br/> • [Proteção de informações do Office 365 para rgpd](https://aka.ms/o365gdpr) <br/> • [Proteger sites e arquivos do SharePoint Online](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files) (inclui compartilhamento, classificação, prevenção de perda de dados e proteção de informações do Azure)  <br/> |
   
## <a name="90-days--enhanced-protections"></a>90 dias — proteções aprimoradas
<a name="Ninetydays"> </a>

Essas tarefas demoram um pouco mais para planejar e implementar, mas aumentam significativamente as condições de segurança. 
  
|||
|:-----|:-----|
|Área  <br/> |Tarefa  <br/> |
|Gerenciamento de segurança  <br/> | • Verifique a pontuação segura para as ações recomendadas para [https://securescore.office.com](https://securescore.office.com)seu ambiente ().  <br/>  • Continue a examinar regularmente painéis e relatórios no centro de segurança do Microsoft 365, no Cloud app Security e nas ferramentas SIEM.  <br/>  • Procure e implemente atualizações de software.  <br/>  • Conduzir simulações de ataque para os ataques de senhas de spear-phishing, de irrigação de senha e de força bruta usando o [Attack Simulator](https://support.office.com/article/attack-simulator-office-365-da5845db-c578-4a41-b2cb-5a09689a551b) (incluído no [Office 365 Threat Intelligence](office-365-ti.md)).  <br/>  • Procure por compartilhar riscos examinando os relatórios internos no Cloud app Security (na guia investigar).  <br/>  • Verifique o [Gerenciador de conformidade](../../compliance/meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md) para analisar o status das regulamentações que se aplicam à sua organização (como RGPD, NIST 800-171).  <br/> |
|Proteção contra Ameaças  <br/> | Implementar proteções aprimoradas para contas de administrador:  <br/>  • Configure o PAWs ( [estações de trabalho com privilégios de acesso privilegiados](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) ) para atividades de administrador.  <br/>  • Configure o [Azure ad Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).  <br/>  • Configure uma ferramenta de gerenciamento de eventos e informações de segurança (SIEM) para coletar dados de log do Office 365, do Cloud app Security e de outros serviços, incluindo o AD FS. O log de auditoria do Office 365 armazena dados por apenas 90 dias. A captura desses dados na ferramenta SIEM permite que você armazene dados por um período mais longo.  <br/> |
|Gerenciamento de identidades e acesso  <br/> | • Habilitar e impor a MFA para todos os usuários.  <br/>  • Implemente um conjunto de [acesso condicional e políticas relacionadas](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations). |
|Proteção de informações  <br/> | Adaptar e implementar políticas de proteção de informações. Esses recursos incluem exemplos:  <br/> • [Proteção de informações do Office 365 para rgpd](https://aka.ms/o365gdpr) <br/> • [Proteger sites e arquivos do SharePoint Online](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files) <br/> <br> Use políticas de prevenção de perda de dados e ferramentas de monitoramento no Office 365 para dados armazenados no Office 365 (em vez de segurança do Cloud app). <br><br>Use o Cloud app Security com o Office 365 para recursos avançados de alerta (diferentes de prevenção de perda de dados).  <br/> |
   
## <a name="beyond"></a>Deles
<a name="Beyond"> </a>

Essas são medidas de segurança importantes que são criadas no trabalho anterior. 
  
|||
|:-----|:-----|
|Área  <br/> |Tarefa  <br/> |
|Gerenciamento de segurança  <br/> |• Continue planejando as próximas ações usando a pontuação segura [https://securescore.office.com](https://securescore.office.com)().  <br/>  • Continue a examinar regularmente painéis e relatórios no centro de segurança do Microsoft 365, no Cloud app Security e nas ferramentas SIEM.  <br/>  • Continue a procurar e implementar atualizações de software.  <br/>  • Integre a descoberta eletrônica em seus processos de resposta legal e de ameaça.  <br/> |
|Proteção contra Ameaças  <br/> | • Implemente o [acesso privilegiado seguro](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (Spa) para componentes de identidade no local (AD, AD FS).  <br/>  • Use o Cloud app Security para monitorar ameaças Insider.  <br/>  • Descubra o uso do SaaS de ti de sombra usando o Cloud app Security.  <br/> |
|Gerenciamento de identidades e acesso  <br/> | • Refine políticas e processos operacionais.  <br/>  • Use o Azure AD Identity Protection para identificar ameaças Insider.  |
|Proteção de informações  <br/> | Refinar políticas de proteção de informações:  <br/>  • Microsoft 365 e Office 365 rótulos de sensibilidade e prevenção de perda de dados (DLP) ou proteção de informações do Azure.  <br/>  • Políticas e alertas do Cloud app Security.  <br/> |
   
Consulte também: [como mitigar cyberattacks rápidos, como Petya e WannaCrypt](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/). 
  

