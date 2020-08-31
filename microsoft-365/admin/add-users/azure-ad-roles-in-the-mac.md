---
title: Funções do Azure Active Directory no Centro de administração do Microsoft 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
description: Gerencie essas funções de administrador do Azure no Centro de administração do Microsoft 365.
ms.openlocfilehash: 2295a003fa73cb1805fad3231ff62b37930d0306
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289088"
---
# <a name="azure-active-directory-roles-in-the-microsoft-365-admin-center"></a>Funções do Azure Active Directory no Centro de administração do Microsoft 365

O centro de administração do Microsoft 365 permite gerenciar mais de 30 funções do Azure AD. No entanto, essas funções são um subconjunto das funções disponíveis no portal do Azure. Se você tiver uma empresa de grande porte, pode haver funções no portal do Azure que atendem às suas necessidades organizacionais. Procurando as descrições de função detalhadas do Azure AD? Confira [Permissões da função de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

Um usuário que recebe uma função de administrador terá as mesmas permissões em todos os serviços na nuvem para os quais a sua organização se inscreveu, independentemente de você atribuir a função no centro de administração do Office 365 ou no portal clássico do Azure ou usando o módulo do Azure AD para Windows PowerShell.

::: moniker range="o365-worldwide"

No Centro de administração do Microsoft 365, você pode acessar **Funções** e, em seguida, selecionar qualquer função para abrir seu painel de detalhes. Selecione a guia **Permissões** para exibir a lista detalhada do que os administradores com aquela função têm permissão para fazer. Marque a guia **Atribuir** ou **Administradores atribuídos** para adicionar usuários a funções. Para obter mais informações sobre como atribuir funções no Centro de administração do Microsoft 365, confira [Atribuir funções de administrador](assign-admin-roles.md).

::: moniker-end

## <a name="all-azure-ad-roles"></a>Todas as funções do Azure AD

Esta é uma lista de todas as funções disponíveis no centro de administração do Microsoft 365. Procurando as descrições detalhadas das funções de administrador do Microsoft 365? Veja [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).

|Função do administrador     |Descrição  |
|---------|---------|
|Administrador de aplicativos     |    Acesso total aos aplicativos corporativos, registros de aplicativos e configurações de proxy do aplicativo.     |
|Desenvolvedor de aplicativo     |    Cria registros de aplicativo e consentimento para o acesso do aplicativo em seu próprio nome.     |
|Administrador de autenticação     |    Pode exigir que os usuários registrem novamente a autenticação de credenciais de não senha, como a MFA.     |
|Administrador de Proteção de Informações do Azure     |   Gerencia rótulos para a política de Proteção de Informações do Azure, gerencia modelos de proteção e ativa a proteção.       |
|Administrador de faturamento     |    Faz compras, gerencia assinaturas, gerencia solicitações de serviço e monitora a integridade do serviço.     |
|Administrador de aplicativo na nuvem     | Acesso total aos aplicativos corporativos e registros de aplicativos. Nenhum proxy de aplicativo.     |
|Administrador de dispositivos na nuvem     |    Habilita, desabilita e exclui dispositivos e pode ler as chaves do BitLocker no Windows 10.     |
|Administrador de conformidade     |    Gerencia os requisitos normativos e os casos de descoberta eletrônica e mantém a governança dos dados por locais, identidades e aplicativos.     |
|Administrador de dados de conformidade     |    Monitora os dados, garante que estejam protegidos, obtém informações sobre problemas e ajuda a reduzir riscos.     |
|Administrador de acesso condicional     |   Gerencia as configurações de acesso condicional do Azure Active Directory, mas não a política de acesso condicional do Exchange ActiveSync.      |
|Aprovador de acesso do cliente ao Sistema de Proteção de Dados do Cliente     |      Gerencia solicitações de acesso ao Sistema de Proteção de Dados do Cliente e pode ativar ou desativar o Sistema de Proteção de Dados do cliente.   |
|Administrador de análise da área de trabalho     |   Pode acessar e gerenciar as ferramentas e os serviços de gerenciamento da área de trabalho.      |
|Administrador do Dynamics 365     |  Acesso total ao Microsoft Dynamics 365 Online, gerencia solicitações de serviço e monitora a integridade do serviço.       |
|Administrador do Exchange     |  Acesso total ao Exchange Online, cria e gerencia grupos, gerencia solicitações de serviço e monitora a integridade do serviço.    |
|Administrador de provedor de identidade externa    |     Configure provedores de identidade para usar na federação direta.    |
|Administrador global     |    Tem acesso ilimitado a todos os recursos de gerenciamento e à maioria dos dados em todos os centros de administração.     |
|Leitor global     |    Tem acesso somente leitura a todos os recursos de gerenciamento e à maioria dos dados em centros de administração. Para obter uma descrição detalhada dos direitos e limitações de acesso dessa função, confira [Permissões da função de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader).    |
|Administrador de grupos   |Cria grupos e gerencia todas as configurações de grupos em todos os centros de administração.|
|Emissor de convite     |    Gerencia os convites de usuário do Microsoft Azure Active Directory B2B.     |
|Administrador de help desk     | Redefine senhas e autentica novamente para todas as funções de não administradores e algumas funções de administrador, gerencia solicitações de serviço e monitora a integridade do serviço.      |
|Administrador do Insights     | Gerencia todos os aspectos do aplicativo Microsoft 365 Insights, lê as informações do Azure Active Directory, monitora a integridade do serviço e cria e gerencia solicitações de serviço.      |
|Administrador empresarial do Insights     | Lê relatórios e informações no aplicativo Microsoft 365 Insights.      |
|Administrador do Intune     | Acesso total ao Intune, gerencia usuários e dispositivos para associar políticas e cria e gerencia grupos.      |
|Administrador do Kaizala     |    Acesso total a todos os recursos e dados de gerenciamento do Kaizala e gerencia solicitações de serviço.     |
|Administrador de licença     |     Atribui e remove licenças de usuários e edita seu local de uso.    |
|Leitor de privacidade do centro de mensagens     |    Acesso às mensagens de privacidade de dados no centro de mensagens e recepção de notificações por e-mail.     |
|Leitor de centro de mensagens     | Lê e compartilha mensagens regulares no centro de mensagens, obtém resumos semanais de e-mails, tem acesso somente leitura a usuários, grupos, domínios e assinaturas.     |
|Administrador de aplicativos do Office    |   Gerencia políticas baseadas em nuvem para o Office e o conteúdo de Novidades que os usuários veem em seus aplicativos do Office.   |
|Administrador de senha    |   Redefina as senhas dos usuários que não são administradores ou membros das funções a seguir: leitores de diretório, emissor de convite, administrador de senha. Esta função não pode conceder a capacidade de gerenciar solicitações de serviço ou de monitorar a integridade do serviço.   |
|Administrador do Power BI    |   Acesso completo às tarefas de gerenciamento do Power BI, gerencia solicitações de serviço e monitora a integridade do serviço.   |
|Administrador da plataforma de alimentação     |    Acesso total ao Microsoft Dynamics 365, ao PowerApps, às políticas de prevenção contra perda de dados e ao Microsoft Flow.     |
|Administrador de função com privilégios     |    Gerencia atribuições de funções e todos os recursos de controle de acesso do Gerenciamento de identidades com privilégios.     |
|Administrador de autenticação privilegiada     |    Redefine senhas, atualiza as credenciais sem senha, força o usuário a sair, monitora a integridade do serviço e gerencia as solicitações de serviço.     |
|Leitor de relatórios     |   Lê os dados de relatórios de uso do painel de relatórios, do pacote de conteúdo de adoção do PowerBI, os relatórios de entrada e a API de relatórios do Microsoft Graph.      |
|Administrador de pesquisa     |    Acesso total à Microsoft Search, atribui as funções de administrador de pesquisa e editor de pesquisa, gerencia conteúdo editorial, monitora a integridade do serviço e cria solicitações de serviço.     |
|Editor de pesquisa     |    Só pode criar, editar e excluir o conteúdo da pesquisa da Microsoft, como indicadores, Q&A e locais.     |
|Administrador de segurança     |    Controla a segurança da organização, gerencia políticas de segurança, revisa análise e relatórios de segurança e monitora o panorama de ameaças.     |
|Operador de segurança     |    Investiga e responde a alertas de segurança, gerencia recursos no centro de proteção de identidade e monitora a integridade do serviço.     |
|Leitor de segurança     |    Acesso somente leitura para recursos de segurança, relatórios de entrada e logs de auditoria.     |
|Administrador de suporte do serviço     |    Cria solicitações de serviço para o Azure, o Microsoft 365 e os serviços do Office 365, e monitora a integridade do serviço.     |
|Administrador do SharePoint     |    Acesso total ao SharePoint Online, gerencia grupos do Microsoft 365, gerencia solicitações de serviço e monitora a integridade do serviço.     |
|Administrador do Skype for Business     | Acesso total a todas as equipes e recursos do Skype, aos atributos de usuário do Skype, gerencia solicitações de serviço e monitora a integridade do serviço.      |
|Administrador de equipes     |    Acesso total ao centro de administração do Teams e do Skype, gerencia grupos e solicitações de serviço do Microsoft 365 e monitora a integridade do serviço.     |
|Gerenciador de comunicações de equipes     |    Atribui números de telefone, cria e gerencia políticas de voz e reuniões e lê as estatísticas de chamadas.     |
|Engenheiro de suporte de comunicações de equipes     |    Lê detalhes do registro de chamadas para todos os participantes da chamada para solucionar problemas de comunicação.     |
|Especialista em suporte à comunicação de equipes     |    Lê os detalhes da chamada de usuário apenas para um usuário específico para solucionar problemas de comunicação.|
|Administrador de usuários     |   Redefine senhas, cria e gerencia usuários e grupos, incluindo filtros, gerencia solicitações de serviço e monitora a integridade do serviço.|

## <a name="delegated-administration-for-microsoft-partners"></a>Administração delegada para parceiros da Microsoft

Se você está trabalhando com um parceiro da Microsoft, pode atribua funções administrativas a ele. Ele, por sua vez, pode atribuir funções administrativas a usuários em sua empresa (ou nas empresas deles). Isso pode ser conveniente, por exemplo, se ele estiver configurando e gerenciando a sua organização online para você.
  
Um parceiro pode atribuir estas funções: 

- Administração total, que tem privilégios equivalentes a um administrador global, com exceção de gerenciamento da autenticação multifatorial pelo Partner Center.

- Administração limitada, que tem privilégios equivalentes à administração de help desk.

Antes que o parceiro possa atribuir funções aos usuários, é preciso adicioná-lo como administrador delegado à sua conta. Esse processo é iniciado por um parceiro autorizado.O parceiro envia um email perguntando se você deseja conceder permissão a ele para atuar como administrador delegado. Para obter instruções, confira [Autorizar ou remover relações de parceiro](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).
  
## <a name="related-articles"></a>Artigos relacionados

[Sobre as funções de administrador do Microsoft 365 ](about-admin-roles.md)

[Atribuir funções de administrador](assign-admin-roles.md)
  
[Relatórios de atividades no centro de administração do Microsoft 365](../activity-reports/activity-reports.md)