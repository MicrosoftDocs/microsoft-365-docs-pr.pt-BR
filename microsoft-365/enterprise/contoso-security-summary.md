---
title: Resumo do Microsoft 365 para segurança corporativa para a Contoso Corporation
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
description: Como a Contoso usa os recursos de segurança do Microsoft 365 para empresas.
ms.openlocfilehash: 31baf61011fb67fbe11394718086d73afa2bc680
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907657"
---
# <a name="summary-of-microsoft-365-for-enterprise-security-for-the-contoso-corporation"></a>Resumo do Microsoft 365 para segurança corporativa para a Contoso Corporation

Para obter aprovação para implantar o Microsoft 365 para empresas, o departamento de segurança de IT da Contoso realizou uma revisão completa de segurança. Eles identificaram os seguintes requisitos de segurança para a nuvem:

- Use os métodos mais fortes de autenticação para acesso de funcionários a recursos de nuvem.
- Certifique-se de que os PCs e dispositivos móveis se conectem e acessem aplicativos de maneiras seguras.
- Proteja PCs e emails contra malware.
- As permissões em ativos digitais baseados em nuvem definem quem pode acessar o que e o que podem fazer e são projetadas para acesso com privilégios mínimos
- Os ativos digitais confidenciais e altamente regulamentados são rotulados, criptografados e armazenados em locais seguros.
- Os ativos digitais altamente regulamentados são protegidos com criptografia e permissões adicionais.
- A equipe de segurança de IT pode monitorar a postura de segurança atual dos painéis centrais e ser notificada sobre eventos de segurança para resposta rápida e mitigação.

## <a name="the-contoso-path-to-microsoft-365-security-readiness"></a>O caminho da Contoso para a preparação de segurança do Microsoft 365

A Contoso seguiu estas etapas para preparar sua segurança para a implantação do Microsoft 365 para empresas:

1. Limitar contas de administrador para a nuvem

   A Contoso fez uma revisão extensiva de suas contas de administrador do Active Directory Domain Services (AD DS) existentes e definiu uma série de contas e grupos de administradores de nuvem dedicados.

2. Classificar dados em três níveis de segurança

   A Contoso fez uma revisão cuidadosa e determinou os três níveis, que foram usados para identificar os recursos do Microsoft 365 para empresas para proteger os dados mais valiosos.

3. Determinar políticas de acesso, retenção e proteção de informações para níveis de dados

   Com base nos níveis de dados, a Contoso determinou requisitos detalhados para qualificar cargas de trabalho futuras de IT movidas para a nuvem.

Para seguir as práticas recomendadas de segurança e o Microsoft 365 para requisitos de implantação empresarial, os administradores de segurança da Contoso e seu departamento de IT implantaram muitos recursos e recursos de segurança, conforme descrito nas seções a seguir.

## <a name="identity-and-access-management"></a>Gerenciamento de identidades e acesso 

- Contas de administrador global dedicadas com MFA e PIM

  Em vez de atribuir a função de administrador global a contas de usuário diárias, a Contoso criou três contas de administrador global dedicadas com senhas fortes. As contas são protegidas pelo Azure AD Multi-Factor Authentication (MFA) e pelo Azure Active Directory (Azure AD) Privileged Identity Management (PIM). *O PIM está disponível apenas com o Microsoft 365 E5.*

  Entrar com uma conta de administrador global só é feito para tarefas administrativas específicas. As senhas só são conhecidas por funcionários designados e só podem ser usadas em um período de tempo configurado no PIM do Azure AD.

  Os administradores de segurança da Contoso atribuiu funções de administrador menores a contas apropriadas à função de trabalho do trabalhador de IT.

  Para obter mais informações, consulte [Sobre as funções de administrador do Microsoft 365](/office365/admin/add-users/about-admin-roles).

- Autenticação Multifator para todas as contas de usuário

  O MFA adiciona uma camada adicional de proteção ao processo de login. Exige que os usuários reconheçam uma chamada telefônica, uma mensagem de texto ou uma notificação de aplicativo em seu smartphone depois de inserir corretamente a senha. Com o MFA, as contas de usuário do Azure AD são protegidas contra a in-loco não autorizada, mesmo que uma senha de conta seja comprometida.

   - Para se proteger contra o comprometimento da assinatura do Microsoft 365, a Contoso requer MFA em todas as contas de administrador global.
   - Para se proteger contra ataques de phishing, no qual um invasor compromete as credenciais de uma pessoa confiável na organização e envia emails mal-intencionados, a Contoso habilitou a MFA em todas as contas de usuário, incluindo diretoria e gerência.

- Acesso mais seguro a dispositivos e aplicativos com Políticas de Acesso Condicional

  A Contoso está usando [Políticas de Acesso Condicional](../security/office-365-security/microsoft-365-policies-configurations.md) para identidade, dispositivos, Exchange Online e SharePoint Online. As políticas de acesso condicional à identidade incluem exigir alterações de senha dos usuários de alto risco e impedir que os clientes usem aplicativos que não suportam autenticação moderna. As políticas de dispositivos incluem a definição de aplicativos aprovados e a exigência de computadores e dispositivos móveis compatíveis. As políticas de Acesso Condicional do Exchange Online incluem impedir clientes do ActiveSync e configurar a criptografia de mensagem do Office 365. As políticas de Acesso Condicional do SharePoint Online incluem proteção adicional para sites confidenciais e altamente controlados.

- Windows Hello para Empresas

  A Contoso implantou o [Windows Hello para Empresas](/windows/security/identity-protection/hello-for-business/hello-identity-verification) para eliminar a necessidade de senhas por meio da autenticação forte de dois fatores em computadores e dispositivos móveis que executam o Windows 10 Enterprise.

- Windows Defender Credential Guard

  Para bloquear ataques direcionados e malware em execução no sistema operacional com privilégios administrativos, a Contoso habilita Windows Defender [Credential Guard](/windows/security/identity-protection/credential-guard/credential-guard) por meio da política de grupo do AD DS.

## <a name="threat-protection"></a>Proteção contra Ameaças

- Proteção contra malware com o Windows Defender Antivírus

  A Contoso está usando o [Windows Defender Antivírus](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) para proteção contra malware e gerenciamento antimalware para PCs e dispositivos com o Windows 10 Enterprise.

- Fluxo de email seguro e log de auditoria de caixa de correio com o Microsoft Defender para Office 365 

  A Contoso está usando a Proteção do Exchange Online e o [Defender para o Office 365](/office365/securitycompliance/office-365-atp) para proteger contra malwares desconhecidos, vírus e URLs mal-intencionadas transmitidas por emails.

  A Contoso também habilita o log de auditoria de caixa de correio para identificar quem faz logor nas caixas de correio do usuário, envia mensagens e faz outras atividades realizadas pelo proprietário da caixa de correio, um usuário delegado ou um administrador.

- Monitoramento e prevenção contra ataques com investigação e resposta a ameaças do Office 365

  A Contoso usa a investigação e a resposta contra ameaças do [Office 365](/office365/securitycompliance/office-365-ti) para proteger os usuários, facilitando a identificação e o endereço de ataques e evitando ataques futuros.

- Proteção contra ataques sofisticados com Advanced Threat Analytics

  A Contoso usa [Advanced Threat Analytics (ATA)](/advanced-threat-analytics/what-is-ata) para se proteger contra ataques direcionados avançados.  A ATA analisa, aprende e identifica automaticamente comportamento normal e anormal de entidades (usuário, dispositivos e recursos).

## <a name="information-protection"></a>Proteção de informações

- Proteja ativos digitais sensíveis e altamente regulamentados com rótulos de Proteção de Informações do Azure

  A Contoso determinou três níveis de proteção de dados e implantou [Rótulos de confidencialidade do Microsoft 365](../compliance/sensitivity-labels.md) que os usuários aplicam a ativos digitais. Para seus segredos comerciais e outras propriedades intelectuais, a Contoso usa sub-rótulos de sensibilidade para dados altamente regulamentados. Esse processo criptografa conteúdo e restringe o acesso a contas de usuário e grupos específicos.

- Evite vazamentos de dados na intranet com a Prevenção contra perda de dados

  A Contoso [configurou](../compliance/data-loss-prevention-policies.md) políticas de Prevenção contra Perda de Dados para Exchange Online, SharePoint e OneDrive for Business para impedir que os usuários compartilhem dados confidenciais acidentalmente ou intencionalmente.

- Impedir o vazamento de dados do dispositivo com a Proteção de Informações do Windows

  A Contoso está usando a Proteção de Informações do [Windows (WIP)](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) para proteger contra vazamento de dados por meio de aplicativos e serviços baseados na Internet e aplicativos corporativos e dados em dispositivos corporativos e dispositivos pessoais que os funcionários trazem para o trabalho.

- Monitoramento de nuvem com o Microsoft Cloud App Security

  A Contoso está usando o [Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security) para mapear o ambiente de nuvem, monitorar o uso e detectar ocorrências e eventos de segurança. *O Microsoft Cloud App Security só está disponível no Microsoft 365 E5.*

- Gerenciamento de dispositivos com o Microsoft Intune

  A Contoso usa o [Microsoft Intune](/intune/introduction-intune) para se inscrever, gerenciar e configurar o acesso a dispositivos móveis e os aplicativos que são executados neles. As políticas de Acesso Condicional com Base no Dispositivo também exigem aplicativos aprovados, dispositivos móveis e computadores compatíveis.

## <a name="security-management"></a>Gerenciamento de segurança

- Painel de segurança central para IT com o Azure Defender

  A Contoso usa o [Azure Defender](https://azure.microsoft.com/services/security-center/) para apresentar uma visão unificada da proteção contra ameaças e segurança, para gerenciar políticas de segurança em suas cargas de trabalho e para responder a ataques cibernéticos.

- Painel central de segurança para os usuários com a Central de Segurança do Windows Defender

  A Contoso implantou o aplicativo de Segurança do [Windows](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) em seus computadores e dispositivos que executam o Windows 10 Enterprise para que os usuários possam ver sua postura de segurança rapidamente e tomar medidas.