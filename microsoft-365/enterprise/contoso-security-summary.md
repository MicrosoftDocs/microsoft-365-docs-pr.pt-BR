---
title: Resumo de segurança do Microsoft 365 Enterprise para a Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Como a Contoso está usando os recursos de segurança no Microsoft 365 Enterprise.
ms.openlocfilehash: fd3f73919a113389e9d423dbed11cf0074fb5833
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802056"
---
# <a name="summary-of-microsoft-365-enterprise-security-for-the-contoso-corporation"></a>Resumo de segurança do Microsoft 365 Enterprise para a Contoso Corporation

Para obter a aprovação da implantação do Microsoft 365 Enterprise pelo departamento de segurança de TI, foi realizada uma revisão completa de segurança. Aqui estão os requisitos de segurança da Contoso para a nuvem:

- Use os métodos mais seguros de autenticação de acesso do funcionário aos recursos da nuvem
- Garanta que computadores e dispositivos móveis se conectem e acessem os aplicativos de forma segura
- Email e PCs são protegidos contra malware
- Permissões em ativos digitais baseados em nuvem definem quem pode acessar o que e o que podem fazer e são projetadas para acesso de menor privilégio
- Ativos digitais confidenciais e altamente regulamentados são rotulados, criptografados e armazenados em locais seguros
- Ativos digitais altamente regulamentados são protegidos com criptografia e permissões adicionais
- A equipe de segurança de TI pode monitorar a postura de segurança atual a partir de painéis centrais e receber notificações de eventos de segurança para conseguir responder rapidamente e mitigar o problema

## <a name="contosos-path-to-microsoft-365-security-readiness"></a>Caminho da Contoso para preparação para segurança do Microsoft 365

A Contoso realizou as etapas a seguir para preparar a segurança para a implantação do Microsoft 365 Enterprise:

1. Contas de administrador limitadas para a nuvem

   A Contoso fez um amplo exame das contas de administrador existentes dos Serviços de Domínio do Active Directory (AD DS) e configurou uma série de grupos e contas de administrador de nuvem.

2. Executou a análise de classificação de dados em três níveis

   A Contoso fez um exame cuidadoso e determinou os três níveis, que foram usados para determinar os recursos do Microsoft 365 Enterprise para proteger os dados mais valiosos da Contoso.

3. Determinou as políticas de acesso, de retenção e de proteção de informações para níveis de dados

   Com base nos níveis de dados, a Contoso determinou requisitos detalhados, que serão usados para qualificar cargas de trabalho de TI futuras que estejam sendo movidas para a nuvem.

De acordo com as práticas recomendadas de segurança e os requisitos de implantação do Microsoft 365 Enterprise, os administradores de segurança da Contoso e o departamento de TI implantaram vários recursos e funcionalidades de segurança, conforme descrito nas seções a seguir.

## <a name="identity--access-management"></a>Gerenciamento de identidades e acesso 

- Contas de administrador global dedicadas com MFA e PIM

  Em vez de atribuir a função de administrador global para contas de usuários comuns, a Contoso criou três contas de administrador global dedicadas com senhas fortes e as protegeu com a Autenticação Multifator (MFA) do Azure e com o Azure Active Directory Privileged Identity Management (PIM). O PIM está disponível apenas com o Microsoft 365 E5.

  A entrada com uma conta de administrador global é realizada apenas para tarefas administrativas específicas, as senhas são conhecidas somente por funcionários designados e só podem ser usadas no horário configurado com o Azure AD PIM. 

  Os administradores de segurança da Contoso atribuíram funções de administrador com menos privilégios para contas que são apropriadas para a função de trabalho e a responsabilidade desse profissional de TI.

  Para saber mais, veja [Sobre as funções de administrador do Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).

- Autenticação multifator para todas as contas de usuário

  A MFA adiciona uma outra camada de proteção ao processo de login exigindo que os usuários confirmem uma chamada, mensagem de texto ou uma notificação de aplicativo no smartphone após inserir a senha corretamente. Com a MFA, as contas de usuário do Azure AD são protegidas contra entrada não autorizada, mesmo que a senha de uma conta esteja comprometida.

   - Para proteger contra o comprometimento da assinatura do Microsoft 365, a Contoso exige MFA em todas as contas de administrador global.
   - Para se proteger contra ataques de phishing, no qual um invasor compromete as credenciais de uma pessoa confiável na organização e envia emails mal-intencionados, a Contoso habilitou a MFA em todas as contas de usuário, incluindo diretoria e gerência. 

- Acesso mais seguro a dispositivos e aplicativos com Políticas de Acesso Condicional

  A Contoso está usando [Políticas de Acesso Condicional](microsoft-365-policies-configurations.md) para identidade, dispositivos, Exchange Online e SharePoint Online. As políticas de Acesso Condicional de Identidade incluem exigir alterações de senha para usuários de alto risco e impedir clientes de usar aplicativos que não são compatíveis com a autenticação moderna. As políticas de dispositivos incluem a definição de aplicativos aprovados e a exigência de computadores e dispositivos móveis compatíveis. As políticas de Acesso Condicional do Exchange Online incluem impedir clientes do ActiveSync e configurar a criptografia de mensagem do Office 365. As políticas de Acesso Condicional do SharePoint Online incluem proteção adicional para sites confidenciais e altamente controlados.

- Windows Hello para Empresas

  A Contoso implantou e exige o [Windows Hello para Empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) para eventualmente eliminar a necessidade de senhas fortes com a autenticação de dois fatores em PCs e dispositivos móveis com o Windows 10 Enterprise.

- Windows Defender Credential Guard

  Para impedir ataques direcionados e malware em execução no sistema operacional com privilégios administrativos, a Contoso habilitou o [Windows Defender Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) por meio da política de grupo do AD DS.

## <a name="threat-protection"></a>Proteção contra Ameaças

- Proteção contra malware com o Windows Defender Antivírus

  A Contoso está usando o [Windows Defender Antivírus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) para proteção contra malware e gerenciamento antimalware para PCs e dispositivos com o Windows 10 Enterprise.

- Garanta a segurança do fluxo de emails e o log de auditoria de caixa de correio com a Proteção Avançada contra Ameaças do Office 365 

  A Contoso está usando a Proteção do Exchange Online e a [Proteção Avançada contra Ameaças do Office 365 (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) para proteger contra malware desconhecido, vírus e URLs mal-intencionadas enviadas por emails. 

  A Contoso também habilitou o log de auditoria de caixa de correio para determinar quem se conectou nas caixas de correio de usuário, enviou mensagens e outras atividades realizadas pelo proprietário da caixa de correio, um usuário delegado ou um administrador.

- Monitoramento e prevenção contra ataques com investigação e resposta a ameaças do Office 365

  A Contoso usa a [investigação e resposta a ameças do Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-ti) para proteger seus usuários do Office 365 facilitando a identificação e a resolução de ataques, e para evitar ataques futuros.

- Proteção contra ataques sofisticados com Advanced Threat Analytics

  A Contoso usa [Advanced Threat Analytics (ATA)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata) para se proteger contra ataques direcionados avançados.  A ATA analisa, aprende e identifica automaticamente comportamento normal e anormal de entidades (usuário, dispositivos e recursos). 

## <a name="information-protection"></a>Proteção de informações

- Proteja ativos digitais sensíveis e altamente regulamentados com rótulos de Proteção de Informações do Azure

  A Contoso determinou três níveis de proteção de dados e implantou [rótulos de confidencialidade do Office 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels), que os usuários aplicam a ativos digitais. Para seus segredos comerciais e outros direitos de propriedade intelectual, a Contoso usa dados altamente regulamentados de sub-rótulos de confidencialidade para que criptografam conteúdos e restringem o acesso a grupos e contas de usuários específicos.

- Evite vazamentos de dados de intranet com a prevenção contra perda de dados do Office 365

  A Contoso configurou políticas de [Prevenção contra Perda de Dados](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) do Exchange Online, do SharePoint Online e do OneDrive for Business para impedir que os usuários compartilhem dados confidenciais de maneira intencional ou acidental.

- Impedir o vazamento de dados do dispositivo com a Proteção de Informações do Windows

  A Contoso está usando a [Proteção de Informações do Windows (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) para proteger contra perda de dados por meio de aplicativos baseados na Internet e serviços e aplicativos empresariais e dados em dispositivos de propriedade da empresa e dispositivos pessoais que os funcionários levam para o trabalho.

- Monitoramento de nuvem com o Microsoft Cloud App Security

  A Contoso está usando o [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) para mapear o ambiente de nuvem, monitorar o uso e detectar ocorrências e eventos de segurança. O Microsoft Cloud App Security só está disponível no Microsoft 365 E5.

- Gerenciamento de dispositivos com o Microsoft Intune

  A Contoso usa o [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) para se inscrever, gerenciar e configurar o acesso a dispositivos móveis e os aplicativos que são executados neles. As políticas de Acesso Condicional com Base no Dispositivo também exigem aplicativos aprovados, dispositivos móveis e computadores compatíveis.

## <a name="security-management"></a>Gerenciamento de segurança

- Painel central de segurança para TI com a Central de Segurança do Azure

  A Contoso usa a [Central de Segurança do Azure](https://azure.microsoft.com/services/security-center/) para uma exibição unificada de segurança e proteção contra ameaças, a fim de gerenciar políticas de segurança em suas cargas de trabalho e responder a ataques cibernéticos.

- Painel central de segurança para os usuários com a Central de Segurança do Windows Defender

  A Contoso implantou o [aplicativo de Segurança do Windows](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) para seus PCs e dispositivos executando o Windows 10 Enterprise, para que os usuários possam ver a postura de segurança rapidamente e tomar medidas.


## <a name="next-step"></a>Próxima etapa

[Saiba](contoso-sharepoint-online-site-for-highly-confidential-assets.md) como a Contoso criou um site do SharePoint com dados altamente regulamentados para facilitar a colaboração entre suas equipes de pesquisa.

