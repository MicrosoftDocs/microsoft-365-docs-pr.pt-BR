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
ms.openlocfilehash: 17696b18b4109b568bb1d616813ba40e2a9dccdc
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430466"
---
# <a name="access-the-admin-portal"></a>Acessar o portal de administração

Seu gateway para o serviço de área de trabalho gerenciada da Microsoft é o portal do Microsoft [Azure](https://portal.azure.com). Para saber mais sobre como usar e personalizar sua experiência do portal do Azure geralmente, consulte a [documentação do portal do Azure](https://docs.microsoft.com/azure/azure-portal/). Disponível em versão prévia agora, você também pode encontrar a área de trabalho gerenciada da Microsoft no [Microsoft Endpoint Manager](https://endpoint.microsoft.com/). Se você não estiver familiarizado com os recursos deste portal para gerenciamento de dispositivos, consulte a [documentação do Microsoft Endpoint Manager](https://docs.microsoft.com/mem/).

Sua conta administrativa precisa de permissões específicas para acessar o portal de administração de área de trabalho gerenciada da Microsoft. Você pode gerenciar o acesso de administrador a esses recursos dentro da sua organização usando o controle de acesso baseado em função (RBAC). Para obter mais informações sobre as funções do Azure Active Directory, consulte [permissões de função de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

Atribua suas contas de usuário de administrador a qualquer uma das seguintes funções para garantir o acesso:

|Função do Azure AD  |Permissões de área de trabalho gerenciada da Microsoft  |
|---------|---------|
|Administrador Global     | Os administradores com essa função terão **permissões de leitura e gravação** para todos os recursos no portal de administração de área de trabalho gerenciada da Microsoft.         |
|Leitor global     | Os administradores com essa função terão **permissões somente leitura** para todos os recursos no portal de administração de área de trabalho gerenciada da Microsoft.         |
|Administrador de serviço do Intune     |  Os administradores com essa função terão **permissões de leitura e gravação** para todos os recursos no portal de administração de área de trabalho gerenciada da Microsoft.       |
|Administrador de suporte de serviço     | Os administradores com essa função terão **permissões de leitura e gravação** para todos os recursos no portal de administração de área de trabalho gerenciada da Microsoft.         |

> [!IMPORTANT]
> Somente a função de administrador global tem as permissões necessárias para *registrar* sua organização na área de trabalho gerenciada da Microsoft. Lembre-se de que as funções do Azure Active Directory fornecerão privilégios de contas de usuário em vários serviços da Microsoft. Após concluir o registro com a área de trabalho gerenciada da Microsoft, você sempre deve usar a função com os privilégios *mínimos* necessários para realizar suas outras tarefas.

## <a name="assigning-roles-to-administrators"></a>Atribuindo funções a administradores

Se você precisar de ajuda para atribuir funções do Azure Active Directory, consulte [permissões de função de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).
