---
title: Acesse o portal do Administrador
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 8a5de1673a7b67481c368c5c76444e817f237fe7
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315772"
---
# <a name="access-the-admin-portal"></a>Acessar o portal de administração

Seu gateway para o serviço de área de trabalho gerenciada da Microsoft é o portal do Microsoft [Azure](https://portal.azure.com). Para saber mais sobre como usar e personalizar sua experiência do portal do Azure geralmente, consulte a [documentação do portal do Azure](https://docs.microsoft.com/azure/azure-portal/). Disponível em versão prévia agora, você também pode encontrar a área de trabalho gerenciada da Microsoft no [Microsoft Endpoint Manager](https://endpoint.microsoft.com/). Se você não estiver familiarizado com os recursos deste portal para gerenciamento de dispositivos, consulte a [documentação do Microsoft Endpoint Manager](https://docs.microsoft.com/mem/).

Sua conta administrativa precisa de permissões específicas para acessar os recursos administrativos da área de trabalho gerenciada da Microsoft no portal do Azure ou no Microsoft Endpoint Manager. Você pode gerenciar o acesso de administrador a esses recursos dentro da sua organização usando o controle de acesso baseado em função (RBAC). Várias funções de administrador do Azure AD e funções personalizadas internas estão disponíveis para fornecer controle mais granular a diferentes recursos no portal de administração de área de trabalho gerenciada da Microsoft. Para obter mais informações sobre as funções do Azure Active Directory, consulte [permissões de função de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Diferentemente das funções de administrador do AAD que se aplicam a uma variedade de produtos e serviços da Microsoft, as funções personalizadas são específicas para a área de trabalho gerenciada da Microsoft e só garantem o acesso aos recursos de administração desse serviço. Os administradores podem atribuir funções personalizadas a usuários individualmente ou em combinação com funções de administrador do AAD para adicionar permissões de área de trabalho gerenciada da Microsoft às contas de administração existentes.

Cada uma das funções abaixo pode ser atribuída para fornecer diferentes níveis de acesso:

|Função do Azure AD  |Permissões de área de trabalho gerenciada da Microsoft  |
|---------|---------|
|Administrador Global     | Os administradores com essa função terão **permissões de leitura e gravação** para todos os recursos no portal de administração de área de trabalho gerenciada da Microsoft.         |
|Leitor global     | Os administradores com essa função terão **permissões somente leitura** para todos os recursos no portal de administração de área de trabalho gerenciada da Microsoft.         |
|Administrador de serviço do Intune     |  Os administradores com essa função terão **permissões de leitura e gravação** para todos os recursos no portal de administração de área de trabalho gerenciada da Microsoft. **Alteração:** A inicialização de todos os administradores de setembro de 2020 com essa função não terá acesso aos recursos de segurança do Microsoft Managed desktop.       |
|Administrador de suporte de serviço     | Os administradores com essa função terão **permissões de leitura e gravação** para todos os recursos no portal de administração de área de trabalho gerenciada da Microsoft. **Alteração:** A inicialização de todos os administradores de setembro de 2020 com essa função não terá acesso aos recursos de segurança do Microsoft Managed desktop.         |
|Administrador de segurança | **(Na visualização de setembro de 2020)** Os administradores com essa função terão permissões somente leitura para todos os recursos e permissões de gravação para recursos relacionados à segurança no Microsoft Managed desktop no portal de administração. |
|Leitor de segurança | **(Na visualização de setembro de 2020)**  Os administradores com essa função terão permissões somente leitura para todos os recursos no portal de administração de área de trabalho gerenciada da Microsoft.|

> [!IMPORTANT]
> Somente a função de administrador global tem as permissões necessárias para *registrar* sua organização na área de trabalho gerenciada da Microsoft. Lembre-se de que as funções do Azure Active Directory fornecerão privilégios de contas de usuário em vários serviços da Microsoft. Após concluir o registro com a área de trabalho gerenciada da Microsoft, você sempre deve usar a função com os privilégios *mínimos* necessários para realizar suas outras tarefas.

 
|Função personalizada  |Permissões de área de trabalho gerenciada da Microsoft  |
|---------|---------|
|Administrador do serviço de área de trabalho gerenciada da Microsoft  | **(Na visualização de setembro de 2020)** Quando atribuída a um usuário, essa função concede permissões de **leitura & gravação de administrador para recursos não relacionados à segurança** no portal de administração de área de trabalho gerenciada da Microsoft.  |
|Leitor de serviço de área de trabalho gerenciada da Microsoft | **(Na visualização de setembro de 2020)** Quando atribuída a um usuário, essa função fornece as **permissões somente leitura do administrador a recursos não relacionados à segurança** no portal de administração de área de trabalho gerenciada da Microsoft. |
|Gerenciador de segurança do Microsoft Managed desktop | **(Na visualização de setembro de 2020)** Quando atribuída a um usuário, essa função concede permissões de **leitura & gravação somente para recursos relacionados à segurança** no portal de administração de área de trabalho gerenciada da Microsoft.   |

> [!NOTE]
> Os recursos de segurança incluem comunicações relacionadas à segurança, gerenciamento de contatos de segurança, gerenciamento de solicitações de suporte relacionadas à segurança e acesso a relatórios relacionados à segurança. 

## <a name="assigning-roles-to-administrators"></a>Atribuindo funções a administradores

Se você precisar de ajuda para atribuir funções do Azure Active Directory, consulte [permissões de função de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

Para facilitar o gerenciamento das funções internas, um grupo de segurança foi criado para cada função personalizada (por exemplo, "funções de área de trabalho moderna – gerente de segurança"). Para atribuir usuários a um dos grupos de segurança, siga estas etapas:
1.  Vá para o portal do Azure e navegue até a folha do Azure Active Directory.
2.  Selecione grupos no lado esquerdo.
3.  Procure funções de local de trabalho moderno e selecione o grupo associado à função que você deseja atribuir. 
4.  Selecione Membros no lado esquerdo e, em seguida, selecione + Adicionar Membros na barra de comandos.
5.  Insira o email da pessoa que está sendo adicionada. Se for um usuário externo, você terá que convidá-los antes de poder atribuir o grupo.
6.  Selecione Selecionar na parte inferior.

> [!NOTE]
> No momento, não há suporte para aninhamento de grupos de segurança para atribuição de função. 
