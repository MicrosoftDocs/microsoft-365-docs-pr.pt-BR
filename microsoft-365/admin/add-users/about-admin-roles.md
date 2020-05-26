---
title: Sobre as funções de administrador no centro de administração do Microsoft 365
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: da585eea-f576-4f55-a1e0-87090b6aaa9d
description: As funções de administrador são mapeadas para as funções de negócios e oferecem permissões para realizar tarefas específicas no centro de administração. Por exemplo, o administrador do serviço abre tíquetes de suporte da Microsoft.
ms.custom: okr_smb
ms.openlocfilehash: 2f3b5fedf77c2f763f60c097b25101255d55ecaf
ms.sourcegitcommit: 4ce28ad4d17d336106c1720d65349f19f9e90e04
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44294201"
---
# <a name="about-admin-roles"></a>Sobre funções de administrador

Sua assinatura do Microsoft 365 ou do Office 365 acompanha um conjunto de funções de administrador que você pode atribuir aos usuários em sua organização usando o Centro de administração do Microsoft 365. Cada função de administrador é mapeada para uma função de negócios comum da empresa e concede permissões para a realização de tarefas específicas nos centros de administração.

O Centro de administração do Microsoft 365 permite gerenciar as funções do Azure AD e do Microsoft Intune. No entanto, essas funções são um subconjunto das funções disponíveis no portal do Azure AD e no centro de administração do Intune.

Procurando as descrições de função detalhadas do Azure AD? Confira [Permissões da função de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

Procurando as descrições de função detalhadas do Microsoft Intune? Confira [Controle de acesso baseado em função (RBAC) com o Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).

Para obter mais informações sobre como atribuir funções no Centro de administração do Microsoft 365, confira [Atribuir funções de administrador](assign-admin-roles.md).

## <a name="things-to-consider"></a>Coisas a considerar...

Como os administradores têm acesso a dados e arquivos confidenciais, recomendamos que você siga estas diretrizes para manter a segurança dos dados da sua organização.

| Recomendação                  | Por que isso é importante?                 |
| :------------------- | :------------------- |
| Ter de 2 a 4 administradores globais  | Como somente outro administrador global pode redefinir a senha de um administrador global, recomendamos que você tenha pelo menos dois administradores globais em sua organização no caso de bloqueio de conta. No entanto, o administrador global tem acesso quase ilimitado às configurações da sua organização e à maior parte dos dados, portanto, também recomendamos que você não tenha mais de quatro administradores globais porque essa é uma ameaça de segurança. |
| Atribuir a função *menos permissiva*    | Atribuir a função *menos permissiva* significa conceder aos administradores somente o acesso de que precisam para realizar o trabalho. Por exemplo, se você deseja que alguém redefina senhas de funcionários, não deve atribuir a função de administrador global ilimitado. Deve atribuir uma função de administrador limitada, como administrador de senha ou administrador de assistência técnica. Isso ajudará a manter seus dados seguros.                 |
| Exija autenticação multifatorial para administradores                  |    Na verdade, é uma boa ideia solicitar a MFA de todos os seus usuários, mas os administradores certamente devem usar a MFA para entrar. A MFA permite que os usuários insiram um segundo método de identificação para verificar se eles são quem dizem que são. Os administradores podem ter acesso a vários dados de clientes e funcionários e, caso exija a MFA, mesmo que a senha do administrador tenha sido comprometida, a senha é inútil sem a segunda forma de identificação.  <br><br>Quando você ativa a MFA, da próxima vez que o usuário entrar, será necessário fornecer um endereço de e-mail alternativo e um número de telefone para a recuperação de conta.  <br> [Configurar autenticação multifatorial](../security-and-compliance/set-up-multi-factor-authentication.md)          |

Se você receber uma mensagem no centro de administração informando que você não tem permissões para editar uma configuração ou página, é porque você recebeu uma função que não tem essa permissão.

## <a name="azure-ad-roles-available-in-the-microsoft-365-admin-center"></a>Funções do Azure AD disponíveis no Centro de administração do Microsoft 365

O centro de administração do Microsoft 365 permite gerenciar mais de 30 funções do Azure AD. No entanto, essas funções são um subconjunto das funções disponíveis no portal do Azure. Se você tiver uma empresa de grande porte, pode haver funções no portal do Azure que atendem às suas necessidades organizacionais.

Um usuário que recebe uma função de administrador terá as mesmas permissões em todos os serviços na nuvem para os quais a sua organização se inscreveu, independentemente de você atribuir a função no centro de administração do Office 365 ou no portal clássico do Azure ou usando o módulo do Azure AD para Windows PowerShell.

::: moniker range="o365-worldwide"

No Centro de administração do Microsoft 365, você pode acessar **Funções** e, em seguida, selecionar qualquer função para abrir seu painel de detalhes. Selecione a guia **Permissões** para exibir a lista detalhada do que os administradores com aquela função têm permissão para fazer. Marque a guia **Atribuir** ou **Administradores atribuídos** para adicionar usuários a funções.

::: moniker-end

Provavelmente, você só precisará atribuir as funções a seguir em sua organização. Por padrão, vamos primeiro mostrar as funções que a maioria das organizações usa. Se você não conseguir encontrar uma função, vá para a parte inferior da lista e selecione **Ver mais funções**. "(Para obter informações detalhadas, incluindo os cmdlets associados a uma função, confira [Permissões de função de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).)

|Função do administrador     |Quem deve ser atribuído com esta função?  |
|---------|---------|
|Administrador do Exchange     |   Atribua a função de administrador do Exchange a usuários que precisam exibir e gerenciar as caixas de correio de e-mail do usuário, grupos do Microsoft 365 e Exchange Online. <br><br> Os administradores do Exchange também podem:<br> - Recuperar itens excluídos na caixa de correio de um usuário <br> - Configurar delegados "Enviar como" e "Enviar em nome" <br>  |
|Administrador global     |   Atribua a função de administrador global aos usuários que precisam de acesso global à maioria dos recursos e dados de gerenciamento nos serviços online da Microsoft. <br><br> Conceder a muitos usuários o acesso global é um risco à segurança e é recomendável que você tenha entre dois e quatro administradores globais. <br><br> Somente os administradores globais podem:<br> - Redefinir senhas para todos os usuários <br> - Adicionar e gerenciar domínios <br> <br> **Observação:** a pessoa que se inscreveu no Microsoft Online Services automaticamente se torna um administrador global. |
|Leitor global    |   Atribua a função leitor global aos usuários que precisam exibir os recursos e as configurações do administrador no centro de administração que o administrador global pode exibir. O administrador leitor global não pode editar as configurações.   |
|Administrador de grupos     |   Atribua a função de administrador grupos aos usuários que precisam gerenciar todas as configurações de grupos em todos os centros de administração, incluindo o centro de administração do Microsoft 365 e o portal do Azure Active Directory. <br><br> Os administradores de grupos podem:<br> - Criar, editar, excluir e restaurar grupos do Microsoft 365 <br> - Criar e atualizar políticas de criação, expiração e nomeação de grupos <br> - Criar, editar, excluir e restaurar grupos de segurança do Azure Active Directory| 
|Administrador de help desk     |   Atribua a função de administrador de help desk aos usuários que precisam fazer o seguinte:<br> - Redefinir senhas <br> - Forçar os usuários a sair <br> - Gerenciar solicitações de serviço <br> - Monitorar a integridade do serviço <br> <br> **Observação**: o administrador de help desk só pode ajudar usuários não administradores e usuários atribuídos a essas funções: leitor de diretório, emissor de convite, administrador de help desk, leitor de centro de mensagens e leitor de relatórios.      |
|Administrador de aplicativos do Office    |   Atribua a função de administrador de aplicativos do Office aos usuários que precisam fazer o seguinte: <br> - Use o serviço de política de nuvem do Office para criar e gerenciar políticas baseadas em nuvem para o Office <br> - Criar e gerenciar solicitações de serviço <br> – Gerenciar o conteúdo Novidades que os usuários veem em seus aplicativos do Office   <br> - Monitorar a integridade do serviço  |
|Administrador de serviço    |   Atribua a função de administrador de serviço como uma função adicional aos administradores ou usuários cuja função não incluem as tarefas abaixo, mas ainda precisam fazer o seguinte: <br> - Abrir e gerenciar solicitações de serviço <br> - Exibir e compartilhar postagens do centro de mensagens   |
|Administrador do SharePoint    |   Atribua a função de administrador do SharePoint aos usuários que precisam acessar e gerenciar o centro de administração do SharePoint Online. <br><br>Os administradores do SharePoint também podem: <br> - Criar e excluir sites <br> - Gerenciar conjuntos de sites e configurações globais do SharePoint   |
|Administrador do serviço do Teams    |   Atribua a função de administrador do serviço do Teams aos usuários que precisam acessar e gerenciar o centro de administração do Teams. <br><br>Os administradores do serviço do Teams também podem: <br> - Gerenciar reuniões <br> - Gerenciar pontes de conferência <br> - Gerenciar todas as configurações de toda a organização, inclusive federação, atualizar equipes e configurações de cliente de equipes   |
|Administrador de usuários     |    Atribua a função de administrador de usuários aos usuários que precisam fazer o seguinte para todos os usuários: <br> - Adicionar usuários ou grupos <br> - Atribuir licenças <br> - Gerenciar a maioria das propriedades dos usuários <br> - Criar e gerenciar exibições de usuário <br> - Atualizar políticas de expiração de senha <br> - Gerenciar solicitações de serviço <br> - Monitorar a integridade do serviço <br><br>  O administrador do usuário também pode realizar as seguintes ações para os usuários que não são administradores e para os usuários com as seguintes funções: leitor de diretório, emissor de convite, administrador de help desk, leitor de centro de mensagens, leitor de relatórios: <br> - Gerenciar nomes de usuários<br> - Excluir e restaurar usuários<br> - Redefinir senhas <br> - Forçar os usuários a sair <br> - Atualizar teclas de dispositivo (FIDO)   |

### <a name="all-azure-ad-roles"></a>Todas as funções do Azure AD

 Esta é uma lista de todas as funções disponíveis no centro de administração do Microsoft 365.

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
|Administrador do Intune     | Acesso total ao Intune, gerencia usuários e dispositivos para associar políticas e cria e gerencia grupos.      |
|Administrador do Kaizala     |    Acesso total a todos os recursos e dados de gerenciamento do Kaizala e gerencia solicitações de serviço.     |
|Administrador de licença     |     Atribui e remove licenças de usuários e edita seu local de uso.    |
|Leitor de privacidade do centro de mensagens     |    Acesso às mensagens de privacidade de dados no centro de mensagens e recepção de notificações por e-mail.     |
|Leitor de centro de mensagens     | Lê e compartilha mensagens regulares no centro de mensagens, obtém resumos semanais de e-mails, tem acesso somente leitura a usuários, grupos, domínios e assinaturas.     |
|Administrador de aplicativos do Office    |   Gerencia políticas baseadas em nuvem para o Office e o conteúdo de Novidades que os usuários veem em seus aplicativos do Office.   |
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

## <a name="microsoft-intune-roles-available-in-the-microsoft-365-admin-center"></a>Funções do Microsoft Intune disponíveis no Centro de administração do Microsoft 365

|Função do administrador     |Quem deve ser atribuído com esta função?  |
|---------|---------|
|Gerente de aplicativos     |   Atribuir a função Gerente de aplicativos a usuários que gerenciam o ciclo de vida do aplicativo para aplicativos móveis, configuram aplicativos gerenciados por política e exibem informações sobre os dispositivos e perfis de configuração.  |
|Operador de suporte técnico     |   Atribua a função de operador de suporte técnico a usuários que atribuem aplicativos e políticas a usuários e dispositivos. |
|Administrador de função Intune    |   Atribua o administrador de função do Intune a usuários que podem atribuir permissões do Intune a outros administradores e podem gerenciar funções personalizadas e internas do Intune.   |
|Gerente de Política e Perfil     |   Atribua a função Gerente de Política e Perfil aos usuários para gerenciar políticas de conformidade, perfis de configuração e registro da Apple.   |
|Operador Somente Leitura     |   Atribua a função operador somente leitura para os usuários que só podem visualizar usuários, dispositivos, detalhes de registro e configurações.   |
|Administrador escolar     |   Atribua a função de administrador escolar aos usuários para obter acesso total para gerenciar dispositivos Windows 10 e iOS, aplicativos e configurações no Intune for Education.   |

## <a name="delegated-administration-for-microsoft-partners"></a>Administração delegada para parceiros da Microsoft

Se você está trabalhando com um parceiro da Microsoft, pode atribua funções administrativas a ele. Ele, por sua vez, pode atribuir funções administrativas a usuários em sua empresa (ou nas empresas deles). Isso pode ser conveniente, por exemplo, se ele estiver configurando e gerenciando a sua organização online para você.
  
Um parceiro pode atribuir estas funções: 
  
- Administração total, que tem privilégios equivalentes a um administrador global, com exceção de gerenciamento da autenticação multifatorial pelo Partner Center.
    
- Administração limitada, que tem privilégios equivalentes à administração de help desk.

Antes que o parceiro possa atribuir funções aos usuários, é preciso adicioná-lo como administrador delegado à sua conta. Esse processo é iniciado por um parceiro autorizado.O parceiro envia um email perguntando se você deseja conceder permissão a ele para atuar como administrador delegado. Para obter instruções, confira [Autorizar ou remover relações de parceiro](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).
  
## <a name="related-articles"></a>Artigos relacionados

[Atribuir funções de administrador](assign-admin-roles.md)
  
[Relatórios de atividades no centro de administração do Microsoft 365](../activity-reports/activity-reports.md)
