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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: da585eea-f576-4f55-a1e0-87090b6aaa9d
description: As funções de administrador como a Administração de serviços fazem mapeamento para as funções de negócios e dão permissões para realizar tarefas específicas no centro de administração.
ms.openlocfilehash: 1fea8720b174846dd95d9dd6aeee91f7ecfbc7fa
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908048"
---
# <a name="about-admin-roles"></a>Sobre funções de administrador

A assinatura do Microsoft 365 ou do Office 365 vem com um conjunto de funções administrativas que você pode atribuir aos usuários em sua organização usando o Centro de administração do Microsoft 365. Cada função administrativa é mapeada para funções de negócios comuns e concede às pessoas em sua organização permissões para realizar tarefas específicas nos centros administrativos.

O Centro de administração do Microsoft 365 permite gerenciar as funções do Azure AD e do Microsoft Intune. No entanto, essas funções são um subconjunto das funções disponíveis no portal do Azure AD e no centro de administração do Intune.

## <a name="before-you-begin"></a>Antes de começar

Procurando a lista completa de descrições detalhadas da função do Azure Active Directory que você pode gerenciar no Centro de administração do Microsoft 365? Confira as permissões da função de administrador no Azure Active Directory. [Permissões da função de administrador no Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

Procurando a lista completa de descrições detalhadas da função do Intune que você pode gerenciar no Centro de administração do Microsoft 365?  Confira [Controle de acesso baseado em função (RBAC) com o Microsoft Intune](/mem/intune/fundamentals/role-based-access-control).

Para obter mais informações sobre como atribuir funções no Centro de administração do Microsoft 365, confira [Atribuir funções de administrador](assign-admin-roles.md).

## <a name="watch-what-is-an-admin"></a>Assista: O que é um administrador?

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1SRc0]

## <a name="security-guidelines-for-assigning-roles"></a>Diretrizes de segurança para atribuir funções

Como os administradores têm acesso a dados e arquivos confidenciais, recomendamos que você siga estas diretrizes para manter a segurança dos dados da sua organização.

| Recomendação                  | Por que isso é importante?                 |
| :------------------- | :------------------- |
| Ter de 2 a 4 administradores globais  | Como somente outro administrador global pode redefinir a senha de um administrador global, recomendamos que você tenha pelo menos dois administradores globais em sua organização no caso de bloqueio de conta. No entanto, o administrador global tem acesso quase ilimitado às configurações da sua organização e à maior parte dos dados, portanto, também recomendamos que você não tenha mais de quatro administradores globais porque essa é uma ameaça de segurança. |
| Atribuir a função *menos permissiva*    | Atribuir a função *menos permissiva* significa conceder aos administradores somente o acesso de que precisam para realizar o trabalho. Por exemplo, se você deseja que alguém redefina senhas de funcionários, não deve atribuir a função de administrador global ilimitado. Deve atribuir uma função de administrador limitada, como administrador de senha ou administrador de assistência técnica. Isso ajudará a manter seus dados seguros.                 |
| Exija autenticação multifatorial para administradores                  |    Na verdade, é uma boa ideia solicitar a MFA de todos os seus usuários, mas os administradores certamente devem usar a MFA para entrar. A MFA permite que os usuários insiram um segundo método de identificação para verificar se eles são quem dizem que são. Os administradores podem ter acesso a vários dados de clientes e funcionários e, caso exija a MFA, mesmo que a senha do administrador tenha sido comprometida, a senha é inútil sem a segunda forma de identificação.  <br><br>Quando você ativa a MFA, da próxima vez que o usuário entrar, será necessário fornecer um endereço de e-mail alternativo e um número de telefone para a recuperação de conta.  <br> [Configurar autenticação multifatorial](../security-and-compliance/set-up-multi-factor-authentication.md)          |

Se você receber uma mensagem no centro de administração informando que você não tem permissões para editar uma configuração ou página, é porque você recebeu uma função que não tem essa permissão.

## <a name="commonly-used-microsoft-365-admin-center-roles"></a>Funções comuns do Centro de administração do Microsoft 365

No Centro de administração do Microsoft 365, você pode acessar **Funções** e, em seguida, selecionar qualquer função para abrir seu painel de detalhes. Selecione a guia **Permissões** para exibir a lista detalhada do que os administradores com aquela função têm permissão para fazer. Marque a guia **Atribuir** ou **Administradores atribuídos** para adicionar usuários a funções.

Provavelmente, você só precisará atribuir as funções a seguir em sua organização. Por padrão, vamos primeiro mostrar as funções que a maioria das organizações usa. Se você não conseguir encontrar uma função, vá para a parte inferior da lista e selecione **Mostrar tudo por categoria**. "(Para obter informações detalhadas, incluindo os cmdlets associados a uma função, confira [Permissões de função de administrador no Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).)

|Função do administrador     |Quem deve ser atribuído com esta função?  |
|---------|---------|
|Administrador de faturamento     |   Atribua a função de administrador de cobrança aos usuários que fazem compras, gerenciam assinaturas e solicitações de serviço, e monitoram a integridade do serviço. <br><br> Os administradores de faturamento também podem:<br> - Gerenciar todos os aspectos da cobrança <br> - Criar e gerenciar tíquetes de suporte no portal do Microsoft Azure <br>  |
|Administrador do Exchange     |   Atribua a função de administrador do Exchange a usuários que precisam exibir e gerenciar as caixas de correio de e-mail do usuário, grupos do Microsoft 365 e Exchange Online. <br><br> Os administradores do Exchange também podem:<br> - Recuperar itens excluídos na caixa de correio de um usuário <br> - Configurar delegados "Enviar como" e "Enviar em nome" <br>  |
|Administrador global     |   Atribua a função de administrador global aos usuários que precisam de acesso global à maioria dos recursos e dados de gerenciamento nos serviços online da Microsoft. <br><br> Conceder a muitos usuários o acesso global é um risco à segurança e é recomendável que você tenha entre dois e quatro administradores globais. <br><br> Somente os administradores globais podem:<br> - Redefinir senhas para todos os usuários <br> - Adicionar e gerenciar domínios <br> <br> **Observação:** a pessoa que se inscreveu no Microsoft Online Services automaticamente se torna um administrador global. |
|Leitor global    |   Atribua a função de leitor global aos usuários que precisam exibir recursos e configurações de administração em centros de administração que o administrador global pode exibir. O administrador de leitor global não pode editar as configurações.   |
|Administrador de grupos     |   Atribua a função de administrador grupos aos usuários que precisam gerenciar todas as configurações de grupos em todos os centros de administração, incluindo o Centro de administração do Microsoft 365 e o portal do Azure Active Directory. <br><br> Os administradores de grupos podem:<br> - Criar, editar, excluir e restaurar grupos do Microsoft 365 <br> - Criar e atualizar políticas de criação, expiração e nomeação de grupos <br> - Criar, editar, excluir e restaurar grupos de segurança do Azure Active Directory| 
|Administrador de help desk     |   Atribua a função de administrador de help desk aos usuários que precisam fazer o seguinte:<br> - Redefinir senhas <br> - Forçar os usuários a sair <br> - Gerenciar solicitações de serviço <br> - Monitorar a integridade do serviço <br> <br> **Observação**: o administrador de help desk só pode ajudar usuários não administradores e usuários atribuídos a essas funções: leitor de diretório, emissor de convite, administrador de help desk, leitor de centro de mensagens e leitor de relatórios.      |
|Administrador de licença    |   Atribua a função Administrador de licença a usuários que precisam atribuir e remover licenças de usuários, e edite o local de uso. <br/><br/> Os administradores de licenças também podem: <br> - Reprocessar as atribuições de licença para licenciamento baseado em grupo <br> - Atribuir licenças de produto a grupos para licenciamento baseado em grupo  |
|Administrador de aplicativos do Office    |   Atribua a função de administrador de aplicativos do Office aos usuários que precisam fazer o seguinte: <br> - Use o serviço de política de nuvem do Office para criar e gerenciar políticas baseadas em nuvem para o Office <br> - Criar e gerenciar solicitações de serviço <br> – Gerenciar o conteúdo Novidades que os usuários veem em seus aplicativos do Office   <br> - Monitorar a integridade do serviço  |
|Administrador de senha  |   Atribua a função de administrador de senha a um usuário que precisa redefinir senhas para não-administradores e administradores de senhas.   |
|Leitor do centro de mensagens |   Atribua a função de Leitor de relatórios aos usuários que precisam fazer o seguinte: <br> - Monitorar as notificações do centro de mensagens <br> - Obter os resumos semanais por email das postagens e atualizações do centro de mensagens <br> - Compartilhar as postagens do centro de mensagens <br> - Ter acesso somente leitura aos serviços do Azure Active Directory, como usuários e grupos|
|Administrador do Power Platform |   Atribua a função de Leitor de relatórios aos usuários que precisam fazer o seguinte: <br> - Gerenciar todos os recursos de administração para PowerApps, Microsoft Flow e prevenção contra perda de dados <br> - Criar e gerenciar as solicitações do serviço <br> - Monitorar a integridade do serviço  |
|Leitor de relatórios |   Atribua a função de Leitor de relatórios aos usuários que precisam fazer o seguinte: <br> - Exibir os dados do uso e os relatórios de atividades no Centro de administração do Microsoft 365 <br> - Obter acesso ao pacote de conteúdo de adoção do Power BI <br> - Obter acesso a relatórios de entrada e atividades no Azure Active Directory <br> - Exibir os dados retornados pela API dos relatórios do Microsoft Graph|
|Administrador do Suporte do Serviço   |   Atribua a função do administrador do Suporte do Serviço como uma função adicional para administradores ou usuários que precisam fazer o seguinte, além de sua função de administrador normal: <br> - Abrir e gerenciar solicitações de serviço <br> - Exibir e compartilhar postagens do centro de mensagens <br> - Monitorar a integridade do serviço   |
|Administrador do SharePoint    |   Atribua a função de administrador do SharePoint aos usuários que precisam acessar e gerenciar o centro de administração do SharePoint Online. <br><br>Os administradores do SharePoint também podem: <br> - Criar e excluir sites <br> - Gerenciar conjuntos de sites e configurações globais do SharePoint   |
|Administrador do serviço do Teams    |   Atribua a função de administrador do serviço do Teams aos usuários que precisam acessar e gerenciar o centro de administração do Teams. <br><br>Os administradores do serviço do Teams também podem: <br> - Gerenciar reuniões <br> - Gerenciar pontes de conferência <br> - Gerenciar todas as configurações de toda a organização, inclusive federação, atualizar equipes e configurações de cliente de equipes   |
|Administrador de usuários     |    Atribua a função de administrador de usuários aos usuários que precisam fazer o seguinte para todos os usuários: <br> - Adicionar usuários ou grupos <br> - Atribuir licenças <br> - Gerenciar a maioria das propriedades dos usuários <br> - Criar e gerenciar exibições de usuário <br> - Atualizar políticas de expiração de senha <br> - Gerenciar solicitações de serviço <br> - Monitorar a integridade do serviço <br><br>  O administrador do usuário também pode realizar as seguintes ações para os usuários que não são administradores e para os usuários com as seguintes funções: leitor de diretório, emissor de convite, administrador de help desk, leitor de centro de mensagens, leitor de relatórios: <br> - Gerenciar nomes de usuários<br> - Excluir e restaurar usuários<br> - Redefinir senhas <br> - Forçar os usuários a sair <br> - Atualizar teclas de dispositivo (FIDO)   |

## <a name="delegated-administration-for-microsoft-partners"></a>Administração delegada para parceiros da Microsoft

Se estiver trabalhando com um parceiro Microsoft, você pode atribuir a ele funções de administrador. Eles, por sua vez, podem atribuir as funções administrativas a usuários em sua empresa ou na empresa. Você pode querer que eles façam isso, por exemplo, se estiverem configurando e gerenciando a sua organização online para você.
  
Um parceiro pode atribuir estas funções: 
  
- Privilégios de **Operador Administrativo** equivalentes a um administrador global, com exceção do gerenciamento de autenticação multifator por meio da Partner Center.

- Privilégios de **Operador de Central de ajuda** equivalentes a um administrador de central de ajuda.

Antes que o parceiro possa atribuir funções aos usuários, é preciso adicioná-lo como administrador delegado à sua conta. Esse processo é iniciado por um parceiro autorizado.O parceiro envia um email perguntando se você deseja conceder permissão a ele para atuar como administrador delegado. Para obter instruções, confira [Autorizar ou remover relações de parceiro](../misc/add-partner.md).
  
## <a name="related-content"></a>Conteúdo relacionado

[Atribuir funções de administrador](assign-admin-roles.md) (artigo)
[Funções de Azure Active Directory no Centro de administração do Microsoft 365](azure-ad-roles-in-the-mac.md) (artigo)\
[Relatórios de atividades no Centro de administração do Microsoft 365](../activity-reports/activity-reports.md) (artigo)\
[Função de administrador do Exchange Online](about-exchange-online-admin-role.md) (artigo)
