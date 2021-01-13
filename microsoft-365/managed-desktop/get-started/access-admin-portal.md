---
title: Acesse o portal do Administrador
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
description: Como encontrar e usar o portal de administração, incluindo controlar o acesso a ele.
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 09427d163b8b5e47911b6df26e5acf0fcd1f3524
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841346"
---
# <a name="access-the-admin-portal"></a>Acessar o portal de administração

Seu gateway para o serviço de Área de Trabalho Gerenciada da Microsoft é o portal do Microsoft [Azure.](https://portal.azure.com) Para saber mais sobre como usar e personalizar sua experiência de portal do Azure em geral, consulte a [documentação do portal do Azure.](https://docs.microsoft.com/azure/azure-portal/) Disponível na visualização agora, você também pode encontrar a Área de Trabalho Gerenciada da Microsoft no [Microsoft Endpoint Manager.](https://endpoint.microsoft.com/) Se você não estiver familiarizado com os recursos deste portal para gerenciamento de dispositivos, consulte a documentação [do Microsoft Endpoint Manager.](https://docs.microsoft.com/mem/)

> [!NOTE]
> No entanto, você escolhe acessar a Área de Trabalho Gerenciada da Microsoft, no [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) ou no portal do [Azure,](https://portal.azure.com)os seguintes navegadores são suportados:
> - Microsoft Edge (versão mais recente)
> - Microsoft Internet Explorer 11
> - Safari (versão mais recente, somente Mac)
> - Chrome (versão mais recente)
> - Firefox (versão mais recente)

Sua conta administrativa precisa de permissões específicas para acessar os recursos administrativos da Área de Trabalho Gerenciada da Microsoft no portal do Azure ou no Microsoft Endpoint Manager. Você pode gerenciar o acesso de administrador a esses recursos em sua organização usando o Controle de Acesso Baseado em Função (RBAC). Várias funções de administrador do Azure Active Directory (Azure AD) e funções personalizadas personalizadas estão disponíveis para fornecer controle mais granular a diferentes recursos no portal do Administrador da Área de Trabalho Gerenciada da Microsoft. Para saber mais sobre as funções do Azure Active Directory, confira Permissões de função [de administrador no Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Ao contrário das funções de administrador do Azure AD que se aplicam a vários produtos e serviços da Microsoft, as funções personalizadas são específicas da Área de Trabalho Gerenciada da Microsoft e só garantirão o acesso aos recursos de Administrador para esse serviço. Os administradores podem atribuir funções personalizadas aos usuários individualmente ou em combinação com as funções de administrador do Azure AD para adicionar permissões de Área de Trabalho Gerenciada da Microsoft a contas de administrador existentes.

Cada uma das funções abaixo pode ser atribuída para fornecer níveis diferentes de acesso:

|Função do Azure AD  |Permissões da Área de Trabalho Gerenciada da Microsoft  |
|---------|---------|
|Administrador Global     | Os administradores com essa função terão **permissões de leitura** e gravação para todos os recursos no portal do Administrador da Área de Trabalho Gerenciada da Microsoft.         |
|Leitor global     | Os administradores com essa função terão **permissões somente leitura para todos os recursos** no portal do Administrador da Área de Trabalho Gerenciada da Microsoft.         |
|Administrador de Serviços do Intune     |  Os administradores com essa função terão **permissões de leitura** e gravação para recursos não relacionados à segurança no portal do Administrador da Área de Trabalho Gerenciada da Microsoft.       |
|Administrador de Suporte ao Serviço     | Os administradores com  essa função terão permissões somente leitura  para recursos não relacionados à segurança e permissões de gravação para gerenciar solicitações de suporte no portal do Administrador da Área de Trabalho Gerenciada da Microsoft.         |
|Administrador de Segurança | Os administradores com  essa função terão permissões somente  leitura para todos os recursos e permissões de gravação para recursos relacionados à segurança na Área de Trabalho Gerenciada da Microsoft no portal de administração. |
|Leitor de segurança |Os administradores com essa função terão **permissões somente leitura para todos os recursos** no portal do Administrador da Área de Trabalho Gerenciada da Microsoft.|

> [!IMPORTANT]
> Somente a função Administrador Global tem as permissões necessárias para registrar *sua* organização na Área de Trabalho Gerenciada da Microsoft. Esteja ciente de que as funções do Azure Active Directory darão privilégios a contas de usuário em uma variedade de serviços Microsoft. Depois de concluir o registro na Área de Trabalho  Gerenciada da Microsoft, você deve sempre usar a função com os privilégios mínimos necessários para realizar outras tarefas.

 
|Função personalizada  |Permissões da Área de Trabalho Gerenciada da Microsoft  |
|---------|---------|
|Administrador do Serviço de Área de Trabalho Gerenciada da Microsoft  | Quando atribuída a um usuário, essa  função concede ao administrador permissões de leitura e gravação para recursos não relacionados à segurança no portal do Administrador da Área de Trabalho Gerenciada da Microsoft.  |
|Leitor de Serviços de Área de Trabalho Gerenciada da Microsoft | Quando atribuída a um usuário, essa  função concede ao administrador permissões somente leitura para recursos não relacionados à segurança no portal do Administrador da Área de Trabalho Gerenciada da Microsoft. |
|Microsoft Managed Desktop Security Manager |Quando atribuída a um usuário, essa  função concede ao administrador permissões de leitura e gravação somente para recursos relacionados à segurança no portal do Administrador da Área de Trabalho Gerenciada da Microsoft.   |

> [!NOTE]
> Os recursos de segurança incluem comunicações relacionadas à segurança, gerenciamento de contatos de segurança, gerenciamento de solicitações de suporte relacionadas à segurança e acesso a relatórios relacionados à segurança. 

## <a name="assigning-roles-to-administrators"></a>Atribuindo funções a administradores

Se precisar de ajuda para atribuir funções do Azure Active Directory, confira Permissões de função [de administrador no Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

Para facilitar o gerenciamento de funções internas, há um grupo de segurança para cada função personalizada (por exemplo, "Funções do Local de Trabalho Modernas – Gerenciador de Segurança"). Para atribuir usuários a um dos grupos de segurança, siga estas etapas:
1.  Acesse o portal do Microsoft Endpoint Manager.
2.  Selecione **Grupos** no lado esquerdo.
3.  Pesquise **funções** de local de trabalho modernas e selecione o grupo associado à função que você deseja atribuir. 
4.  Selecione **Membros** no lado esquerdo e, em seguida, **selecione + Adicionar membros** na barra de comandos.
5.  Insira o email da pessoa que está sendo adicionada. Se ele for um convidado, você deve convidá-lo antes de atribuir o grupo.
6.  Selecione **Selecionar** na parte inferior.

> [!NOTE]
> O aninhamento de grupos de segurança para atribuição de função não é suportado no momento. 
