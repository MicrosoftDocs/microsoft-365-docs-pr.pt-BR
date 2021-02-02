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
ms.openlocfilehash: 5b7ba0db52f06f7b3f6fce596015b56c8e46c6c2
ms.sourcegitcommit: 2c4c7ebe9bea52765ece0ed27d3ea77313711b10
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2021
ms.locfileid: "50068948"
---
# <a name="access-the-admin-portal"></a>Acessar o portal de administração

Seu gateway para o serviço de Área de Trabalho Gerenciada da Microsoft é [o Microsoft Endpoint Manager.](https://endpoint.microsoft.com/) Se você não estiver familiarizado com os recursos deste portal para gerenciamento de dispositivos, consulte a documentação [do Microsoft Endpoint Manager.](https://docs.microsoft.com/mem/)

> [!NOTE]
> No [Microsoft Endpoint Manager,](https://endpoint.microsoft.com/) os seguintes navegadores são suportados:
> - Microsoft Edge (versão mais recente)
> - Microsoft Internet Explorer 11
> - Safari (versão mais recente, somente Mac)
> - Chrome (versão mais recente)
> - Firefox (versão mais recente)

Sua conta administrativa precisará de permissões específicas para acessar os recursos administrativos da Área de Trabalho Gerenciada da Microsoft no Microsoft Endpoint Manager. Você pode gerenciar o acesso de administrador a esses recursos em sua organização usando o controle de acesso baseado em função. Várias funções de administrador do Azure Active Directory (Azure AD) e funções de Área de Trabalho Gerenciada da Microsoft estão disponíveis para fornecer controle mais granular a diferentes recursos no portal do Administrador da Área de Trabalho Gerenciada da Microsoft. Para saber mais sobre as funções do Azure Active Directory, confira Permissões de função [de administrador no Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Ao contrário das funções de administrador do Azure AD que se aplicam a vários produtos e serviços da Microsoft, as funções integrados são específicas da Área de Trabalho Gerenciada da Microsoft e só garantirão o acesso aos recursos de Administrador para esse serviço. Os administradores podem atribuir funções internas aos usuários individualmente ou em combinação com as funções de administrador do Azure AD para adicionar permissões de Área de Trabalho Gerenciada da Microsoft a contas de administrador existentes.

## <a name="azure-active-directory-roles-with-microsoft-managed-desktop-access"></a>Funções do Azure Active Directory com acesso à Área de Trabalho Gerenciada da Microsoft

|Função do Azure AD  |Permissões da Área de Trabalho Gerenciada da Microsoft  |
|---------|---------|
|Administrador Global     | Os administradores com essa função terão permissões de leitura e **gravação para todos os recursos** no portal do Administrador da Área de Trabalho Gerenciada da Microsoft.         |
|Leitor global     | Os administradores com essa função terão **permissões somente leitura para todos os recursos** no portal do Administrador da Área de Trabalho Gerenciada da Microsoft.         |
|Administrador de Serviços do Intune     |  Os administradores com essa função terão permissões de **leitura** e gravação para recursos não relacionados à segurança no portal do Administrador da Área de Trabalho Gerenciada da Microsoft.       |
|Administrador de Suporte ao Serviço     | Os administradores com  essa função terão permissões somente leitura  para recursos não relacionados à segurança e permissões de gravação para gerenciar solicitações de suporte no portal do Administrador da Área de Trabalho Gerenciada da Microsoft.         |
|Administrador de Segurança | Os administradores com  essa função terão permissões somente  leitura para todos os recursos e permissões de gravação para recursos relacionados à segurança na Área de Trabalho Gerenciada da Microsoft no portal de administração. |
|Leitor de segurança |Os administradores com essa função terão **permissões somente leitura para todos os recursos** no portal do Administrador da Área de Trabalho Gerenciada da Microsoft.|

Se precisar de ajuda para atribuir funções do Azure Active Directory, confira Permissões de função [de administrador no Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

> [!IMPORTANT]
> Somente a função Administrador Global tem as permissões necessárias para registrar *sua* organização na Área de Trabalho Gerenciada da Microsoft. Esteja ciente de que as funções do Azure Active Directory darão privilégios a contas de usuário em uma variedade de serviços Microsoft. Depois de concluir o registro na Área de Trabalho  Gerenciada da Microsoft, você deve sempre usar a função com os privilégios mínimos necessários para realizar outras tarefas.

## <a name="built-in-roles-provided-by-microsoft-managed-desktop"></a>Funções integrados fornecidas pela Área de Trabalho Gerenciada da Microsoft


|Função integrado  |Permissões da Área de Trabalho Gerenciada da Microsoft  |
|---------|---------|
|Administrador do Serviço de Área de Trabalho Gerenciada da Microsoft  | Quando atribuída a um usuário, essa  função concede ao administrador permissões de leitura e gravação para recursos não relacionados à segurança no portal do Administrador da Área de Trabalho Gerenciada da Microsoft.  |
|Leitor de Serviços de Área de Trabalho Gerenciada da Microsoft | Quando atribuída a um usuário, essa  função concede ao administrador permissões somente leitura para recursos não relacionados à segurança no portal do Administrador da Área de Trabalho Gerenciada da Microsoft. |
|Microsoft Managed Desktop Security Manager |Quando atribuída a um usuário, essa  função concede ao administrador permissões de leitura e gravação somente para recursos relacionados à segurança no portal do Administrador da Área de Trabalho Gerenciada da Microsoft.   |

> [!NOTE]
> Os recursos de segurança incluem comunicações relacionadas à segurança, gerenciamento de contatos de segurança, gerenciamento de solicitações de suporte relacionadas à segurança e acesso a relatórios relacionados à segurança. 

### <a name="assigning-built-in-roles-to-administrators"></a>Atribuindo funções integrados a administradores

Para gerenciar funções internas, há um grupo de segurança para cada função personalizada com o nome "Modern Workplace Roles - _Role Name_"(for example, "Modern Workplace Roles – Security Manager"). Para atribuir usuários a um desses grupos de segurança, siga estas etapas:
1.  Acesse o portal do Microsoft Endpoint Manager.
2.  Selecione **Grupos** no lado esquerdo.
3.  Pesquise **funções** de local de trabalho modernas e selecione o grupo associado à função que você deseja atribuir. 
4.  Selecione **Membros** no lado esquerdo e selecione **+ Adicionar membros** na barra de comandos.
5.  Insira o email da pessoa que está sendo adicionada. Se ele for um convidado, você deve convidá-lo antes de atribuir o grupo.
6.  Selecione **Selecionar** na parte inferior.

> [!NOTE]
> O aninhamento de grupos de segurança para atribuição de função não é suportado no momento. 
