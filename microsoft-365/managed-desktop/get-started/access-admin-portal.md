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
ms.openlocfilehash: 7293c8ced43332f84ced56908ea5203ba867e600
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925899"
---
# <a name="access-the-admin-portal"></a>Acessar o portal de administração

Seu gateway para o serviço de Área de Trabalho Gerenciada da Microsoft é [o Microsoft Endpoint Manager.](https://endpoint.microsoft.com/) Se você não estiver familiarizado com os recursos deste portal para gerenciamento de dispositivos, consulte a documentação do [Microsoft Endpoint Manager](/mem/).

> [!NOTE]
> No [Microsoft Endpoint Manager,](https://endpoint.microsoft.com/) há suporte para os seguintes navegadores:
> - Microsoft Edge (versão mais recente)
> - Microsoft Internet Explorer 11
> - Safari (versão mais recente, somente Mac)
> - Chrome (versão mais recente)
> - Firefox (versão mais recente)

Sua conta administrativa precisará de permissões específicas para acessar os recursos administrativos da Área de Trabalho Gerenciada da Microsoft no Microsoft Endpoint Manager. Você pode gerenciar o acesso de administrador a esses recursos em sua organização usando o controle de acesso baseado em função. Várias funções de administrador do Azure Active Directory (Azure AD) e funções de Área de Trabalho Gerenciada da Microsoft estão disponíveis para fornecer um controle mais granular para diferentes recursos no portal de Administração da Área de Trabalho Gerenciada da Microsoft. Para obter mais informações sobre funções do Azure Active Directory, consulte Permissões de função de administrador [no Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Ao contrário das funções de administrador do Azure AD que se aplicam a vários produtos e serviços da Microsoft, as funções embutidas são específicas da Área de Trabalho Gerenciada da Microsoft e garantirão apenas o acesso aos recursos de Administração para esse serviço. Os administradores podem atribuir funções internas aos usuários individualmente ou em combinação com funções de administrador do Azure AD para adicionar permissões da Área de Trabalho Gerenciada da Microsoft às contas de administração existentes.

## <a name="azure-active-directory-roles-with-microsoft-managed-desktop-access"></a>Funções do Azure Active Directory com acesso à Área de Trabalho Gerenciada da Microsoft

|Função do Azure AD  |Permissões da Área de Trabalho Gerenciada da Microsoft  |
|---------|---------|
|Administrador Global     | Os administradores com essa função terão **permissões de leitura e** gravação para todos os recursos no portal de Administração da Área de Trabalho Gerenciada da Microsoft.         |
|Leitor Global     | Os administradores com essa função terão permissões somente leitura **para todos os recursos** no portal de Administração da Área de Trabalho Gerenciada da Microsoft.         |
|Administrador de Serviço do Intune     |  Os administradores com essa função terão **permissões de** leitura e gravação para recursos não relacionados à segurança no portal de Administração da Área de Trabalho Gerenciada da Microsoft.       |
|Administrador de Suporte ao Serviço     | Os administradores com  essa função terão permissões somente leitura  para recursos não relacionados à segurança e permissões de gravação para gerenciar solicitações de suporte no portal de Administração da Área de Trabalho Gerenciada da Microsoft.         |
|Administrador de Segurança | Os administradores com essa função terão permissões somente  leitura **para** todos os recursos e permissões de gravação para recursos relacionados à segurança na Área de Trabalho Gerenciada da Microsoft no portal de administração. |
|Leitor de segurança |Os administradores com essa função terão permissões somente leitura **para todos os recursos** no portal de Administração da Área de Trabalho Gerenciada da Microsoft.|

Se você precisar de ajuda para atribuir funções do Azure Active Directory, consulte Permissões de função de administrador [no Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

> [!IMPORTANT]
> Somente a função Administrador Global tem as permissões necessárias para *registrar sua* organização na Área de Trabalho Gerenciada da Microsoft. Esteja ciente de que as funções do Azure Active Directory darão privilégios de contas de usuário em uma variedade de serviços da Microsoft. Depois de concluir o registro na Área de Trabalho  Gerenciada da Microsoft, você sempre deve usar a função com os mínimos privilégios necessários para realizar suas outras tarefas.

## <a name="built-in-roles-provided-by-microsoft-managed-desktop"></a>Funções integrados fornecidas pela Área de Trabalho Gerenciada da Microsoft


|Função integrado  |Permissões da Área de Trabalho Gerenciada da Microsoft  |
|---------|---------|
|Administrador do Serviço de Área de Trabalho Gerenciado da Microsoft  | Quando atribuída a um usuário, essa  função concede ao administrador permissões de leitura e gravação para recursos não relacionados à segurança no portal de Administração da Área de Trabalho Gerenciada da Microsoft.  |
|Leitor de Serviço de Área de Trabalho Gerenciado da Microsoft | Quando atribuída a um usuário, essa  função concede ao administrador permissões somente leitura para recursos não relacionados à segurança no portal de Administração da Área de Trabalho Gerenciada da Microsoft. |
|Microsoft Managed Desktop Security Manager |Quando atribuída a um usuário, essa  função concede ao administrador permissões de leitura e gravação apenas para recursos relacionados à segurança no portal de Administração da Área de Trabalho Gerenciada da Microsoft.   |

> [!NOTE]
> Os recursos de segurança incluem comunicações relacionadas à segurança, gerenciamento de contatos de segurança, gerenciamento de solicitações de suporte relacionadas à segurança e acesso a relatórios relacionados à segurança. 

### <a name="assigning-built-in-roles-to-user"></a>Atribuir funções internas ao usuário

Para um gerenciamento fácil de funções internas, há um grupo de segurança para cada função personalizada com o nome "Funções de Trabalho Modernas - _Nome_ da Função "(por exemplo, "Funções de Trabalho Modernas – Gerente de Segurança"). Para atribuir usuários a um desses grupos de segurança, siga estas etapas:
1.  Acesse o portal do Microsoft Endpoint Manager.
2.  Selecione **Grupos** no lado esquerdo.
3.  Pesquise **funções** de local de trabalho modernas e selecione o grupo associado à função que você deseja atribuir. 
4.  Selecione **Membros** no lado esquerdo e selecione **+ Adicionar membros** na barra de comandos.
5.  Insira o email da pessoa que está sendo adicionada. Se eles são convidados, você deve convidá-los antes de poder atribuir o grupo.
6.  Selecione **Selecionar** na parte inferior.

> [!NOTE]
> Não há suporte para aninhar grupos de segurança para atribuição de função. 

### <a name="assigning-built-in-roles-to-groups"></a>Atribuindo funções in-locar a grupos

Se você precisar atribuir uma ou mais funções embutida a um grupo existente, siga estas etapas:
1. Vá para [portal.azure.com](https://portal.azure.com/).
2. Pesquise e abra **aplicativos Enterprise.**
3. Altere **o filtro de tipo de** aplicativo para Microsoft _Applications_ e, em seguida, selecione **Aplicar**.
4. Pesquise e selecione _APIs modernas do cliente do local de trabalho._
5. Selecione **Usuários e grupos** no painel no lado esquerdo e selecione + Adicionar **usuário/grupo**.
6. Pesquise o grupo que você deseja de **Usuários e grupos.**
7. Pesquise a função aplicável em **Selecionar uma função** e selecione-a.
8. Selecione **Atribuir**.
