---
title: Resumo do Microsoft 365 for Enterprise Security para a Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Como a contoso usa os recursos de segurança do Microsoft 365 para empresas.
ms.openlocfilehash: 8d62dba96ecf19f0dc31af2cf5a2d85257ca19d5
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847101"
---
# <a name="summary-of-microsoft-365-for-enterprise-security-for-the-contoso-corporation"></a>Resumo do Microsoft 365 for Enterprise Security para a Contoso Corporation

Para obter aprovação para implantar o Microsoft 365 for Enterprise, o departamento de segurança de ti da Contoso realizou uma revisão de segurança completa. Eles identificaram os seguintes requisitos de segurança para a nuvem:

- Use os métodos mais fortes de autenticação para o acesso do funcionário aos recursos da nuvem.
- Certifique-se de que PCs e dispositivos móveis conectam e acessam aplicativos de maneiras seguras.
- Proteger PCs e emails de malware.
- Permissões em ativos digitais baseados em nuvem definem quem pode acessar o que e o que eles podem fazer, e foram projetados para acesso de privilégios mínimos
- Ativos digitais confidenciais e altamente regulamentados são rotulados, criptografados e armazenados em locais seguros.
- Ativos digitais altamente regulamentados são protegidos com criptografia e permissões adicionais.
- A equipe de segurança de ti pode monitorar a postura de segurança atual de painéis centrais e receber notificações de eventos de segurança para resposta e atenuação rápidas.

## <a name="the-contoso-path-to-microsoft-365-security-readiness"></a>O caminho da Contoso para a preparação de segurança da Microsoft 365

A contoso seguiu estas etapas para preparar a segurança para a implantação do Microsoft 365 for Enterprise:

1. Limitar contas de administrador para a nuvem

   A contoso realizou uma análise abrangente de suas contas de administrador existentes do AD DS (serviços de domínio Active Directory) e configurou a série de contas e grupos de administradores de nuvem dedicados.

2. Classificar dados em três níveis de segurança

   A contoso realizou uma análise cuidadosa e determinou os três níveis, que foram usados para identificar os recursos do Microsoft 365 for Enterprise para proteger os dados mais valiosos.

3. Determinar políticas de acesso, retenção e proteção de informações para níveis de dados

   Com base nos níveis de dados, a contoso determinou os requisitos detalhados para qualificar as cargas de trabalho de ti futuras que são movidas para a nuvem.

Para seguir as práticas recomendadas de segurança e a Microsoft 365 para requisitos de implantação corporativa, os administradores de segurança da Contoso e seu departamento de ti implantaram muitos recursos e recursos de segurança, conforme descrito nas seções a seguir.

## <a name="identity-and-access-management"></a>Gerenciamento de identidades e acesso 

- Contas de administrador global dedicadas com MFA e PIM

  Em vez de atribuir a função de administrador global às contas de usuário diárias, a contoso criou três contas de administrador global dedicadas com senhas fortes. As contas são protegidas pela MFA (autenticação multifator) do Azure e pelo Azure Active Directory (gerenciamento de identidades do Azure AD). *O PIM está disponível apenas com o Microsoft 365 E5.*

  Entrar com uma conta de administrador global só é feita para tarefas administrativas específicas. As senhas são conhecidas apenas por equipes designadas e só podem ser usadas em um período de tempo configurado no PIM do Azure AD.

  Os administradores de segurança da Contoso atribuíram menos funções de administrador a contas apropriadas para a função de trabalho do profissional de ti.

  Para obter mais informações, consulte [Sobre as funções de administrador do Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).

- Autenticação Multifator para todas as contas de usuário

  A MFA adiciona uma camada adicional de proteção ao processo de entrada. Ele exige que os usuários reconheçam uma chamada telefônica, uma mensagem de texto ou uma notificação de aplicativo em seu telefone inteligente após inserir corretamente a senha. Com a MFA, as contas de usuário do Azure AD são protegidas contra o logon não autorizado, mesmo que uma senha de conta seja comprometida.

   - Para se proteger contra o comprometimento da assinatura do Microsoft 365, a contoso requer MFA em todas as contas de administrador global.
   - Para se proteger contra ataques de phishing, no qual um invasor compromete as credenciais de uma pessoa confiável na organização e envia emails mal-intencionados, a Contoso habilitou a MFA em todas as contas de usuário, incluindo diretoria e gerência.

- Acesso mais seguro a dispositivos e aplicativos com Políticas de Acesso Condicional

  A Contoso está usando [Políticas de Acesso Condicional](../security/office-365-security/microsoft-365-policies-configurations.md) para identidade, dispositivos, Exchange Online e SharePoint Online. As políticas de acesso condicional à identidade incluem exigir alterações de senha dos usuários de alto risco e impedir que os clientes usem aplicativos que não suportam autenticação moderna. As políticas de dispositivos incluem a definição de aplicativos aprovados e a exigência de computadores e dispositivos móveis compatíveis. As políticas de Acesso Condicional do Exchange Online incluem impedir clientes do ActiveSync e configurar a criptografia de mensagem do Office 365. As políticas de Acesso Condicional do SharePoint Online incluem proteção adicional para sites confidenciais e altamente controlados.

- Windows Hello para Empresas

  A contoso implantou o [Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) para, eventualmente, eliminar a necessidade de senhas por meio de uma autenticação de dois fatores fortes em computadores e dispositivos móveis que executam o Windows 10 Enterprise.

- Windows Defender Credential Guard

  Para bloquear ataques de destino e malware em execução no sistema operacional com privilégios administrativos, a contoso habilitou o [Windows Defender Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) através da política de grupo do AD DS.

## <a name="threat-protection"></a>Proteção contra Ameaças

- Proteção contra malware com o Windows Defender Antivírus

  A Contoso está usando o [Windows Defender Antivírus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) para proteção contra malware e gerenciamento antimalware para PCs e dispositivos com o Windows 10 Enterprise.

- Fluxo de email seguro e log de auditoria de caixa de correio com o Microsoft defender para Office 365 

  A Contoso está usando o Exchange Online Protection e o [defender para Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) para proteger contra malware, vírus e URLs mal-intencionadas desconhecidos transmitidos por emails.

  A contoso também habilitou o log de auditoria de caixa de correio para identificar quem efetua login nas caixas de correio do usuário, envia mensagens e outras atividades realizadas pelo proprietário da caixa de correio, por um usuário delegado ou por um administrador.

- Monitoramento e prevenção contra ataques com investigação e resposta a ameaças do Office 365

  A contoso usa a [investigação e a resposta contra ameaças do Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-ti) para proteger os usuários, facilitando a identificação e o atendimento de ataques e para evitar ataques futuros.

- Proteção contra ataques sofisticados com Advanced Threat Analytics

  A Contoso usa [Advanced Threat Analytics (ATA)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata) para se proteger contra ataques direcionados avançados.  A ATA analisa, aprende e identifica automaticamente comportamento normal e anormal de entidades (usuário, dispositivos e recursos).

## <a name="information-protection"></a>Proteção de informações

- Proteja ativos digitais sensíveis e altamente regulamentados com rótulos de Proteção de Informações do Azure

  A Contoso determinou três níveis de proteção de dados e implantou [Rótulos de confidencialidade do Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) que os usuários aplicam a ativos digitais. Para seus segredos comerciais e outras propriedades intelectuais, a contoso usa subrótulos de sensibilidade para dados altamente regulamentados. Esse processo criptografa o conteúdo e restringe o acesso a grupos e contas de usuários específicos.

- Evite vazamentos de dados na intranet com a Prevenção contra perda de dados

  A contoso configurou as políticas de [prevenção contra perda de dados](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) para o Exchange Online, o SharePoint e o onedrive for Business para impedir que os usuários compartilhem acidentalmente ou intencionalmente dados confidenciais.

- Impedir o vazamento de dados do dispositivo com a Proteção de Informações do Windows

  A Contoso está usando a [proteção de informações do Windows (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) para proteger contra vazamento de dados através de aplicativos e serviços da empresa e de aplicativos e dados corporativos em dispositivos de propriedade corporativa e dispositivos pessoais que os funcionários trazem para trabalhar.

- Monitoramento de nuvem com o Microsoft Cloud App Security

  A Contoso está usando o [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) para mapear o ambiente de nuvem, monitorar o uso e detectar ocorrências e eventos de segurança. *O Microsoft Cloud App Security só está disponível no Microsoft 365 E5.*

- Gerenciamento de dispositivos com o Microsoft Intune

  A Contoso usa o [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) para se inscrever, gerenciar e configurar o acesso a dispositivos móveis e os aplicativos que são executados neles. As políticas de Acesso Condicional com Base no Dispositivo também exigem aplicativos aprovados, dispositivos móveis e computadores compatíveis.

## <a name="security-management"></a>Gerenciamento de segurança

- Painel central de segurança para ti com o Azure defender *

  A contoso usa o [Azure defender *](https://azure.microsoft.com/services/security-center/) para apresentar uma visão unificada da proteção contra ameaças e segurança, gerenciar políticas de segurança em suas cargas de trabalho e responder a cyberattacks.

- Painel central de segurança para os usuários com a Central de Segurança do Windows Defender

  A contoso implantou o [aplicativo de segurança do Windows](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) em seus PCs e dispositivos que executam o Windows 10 Enterprise para que os usuários possam ver a postura de segurança rapidamente e agir.
