---
title: Atribuir permissões para investigações de dados (versão prévia)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Este artigo descreve como configurar as permissões necessárias para usar a ferramenta de investigações de dados no Microsoft 365.
ms.openlocfilehash: 85a800c3e21c270f46de78bdef77d7b7a98e0eca
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285437"
---
# <a name="assign-permissions-for-data-investigations-preview"></a><span data-ttu-id="5e55a-103">Atribuir permissões para investigações de dados (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="5e55a-103">Assign permissions for Data Investigations (preview)</span></span>

<span data-ttu-id="5e55a-104">Para acessar uma investigação de dados no centro de conformidade do Office 365 ou do Microsoft 365, você precisa ser membro do grupo de função do investigador de dados.</span><span class="sxs-lookup"><span data-stu-id="5e55a-104">To access a data investigation in the Office 365 or Microsoft 365 compliance center, you need be a member of the Data Investigator role group.</span></span> <span data-ttu-id="5e55a-105">Para adicionar membros a um grupo de funções, você deve ser membro do grupo de função gerenciamento da organização ou atribuir a função de gerenciamento de função no centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="5e55a-105">To add members to a role group, you must be a member of the Organization Management role group or assigned the Role Management role in the Security & Compliance Center.</span></span> <span data-ttu-id="5e55a-106">Depois que um usuário se torna membro do grupo de função do investigador de dados, eles podem criar, acessar e conduzir investigações nas investigações de dados das quais você é membro.</span><span class="sxs-lookup"><span data-stu-id="5e55a-106">After a user becomes a member of the Data Investigator role group, they can create, access, and conduct investigations in the data investigations that you are a member of.</span></span>

<span data-ttu-id="5e55a-107">Para atribuir permissões de investigações de dados:</span><span class="sxs-lookup"><span data-stu-id="5e55a-107">To assign data investigations permissions:</span></span>

1. <span data-ttu-id="5e55a-108">Acesse [https://protection.office.com](https://protection.office.com) e entre usando as credenciais de uma conta de administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="5e55a-108">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="5e55a-109">No centro de conformidade & segurança, clique em **permissões**.</span><span class="sxs-lookup"><span data-stu-id="5e55a-109">In the Security & Compliance Center, click **Permissions**.</span></span>

3. <span data-ttu-id="5e55a-110">Clique no grupo de função **Data Investigator** e, em seguida, ao lado de **Membros** na página do submenu, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5e55a-110">Click the **Data Investigator** role group, and then next to **Members** on the flyout page, click **Edit**.</span></span>

4. <span data-ttu-id="5e55a-111">Clique em **escolher Membros** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="5e55a-111">Click **Choose members** and then click **Add**.</span></span> <span data-ttu-id="5e55a-112">Selecione os usuários que você deseja adicionar como investigadores de dados e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="5e55a-112">Select the users that you want to add as data investigators, and then click **Add**.</span></span>

5. <span data-ttu-id="5e55a-113">Depois de adicionar todos os usuários, clique em **concluído** e, em seguida, clique em **salvar** para salvar as alterações no grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="5e55a-113">After you've added all the users, click **Done** and then click **Save** to save the changes to the role group.</span></span>

> [!NOTE]
> <span data-ttu-id="5e55a-114">A função de gerenciamento de investigação de dados que é atribuída ao grupo de função do investigador de dados fornece as permissões necessárias para acessar a ferramenta de investigações de dados no centro de conformidade do Office 365 ou Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5e55a-114">The Data Investigation Management role that is assigned to the Data Investigator role group provides the necessary permissions to access the Data Investigations tool in the Office 365 or Microsoft 365 compliance center.</span></span> <span data-ttu-id="5e55a-115">Por padrão, essa função não é atribuída ao grupo de função gerenciamento da organização, o que significa que os administradores globais em sua organização podem não conseguir acessar a ferramenta de investigações de dados por padrão.</span><span class="sxs-lookup"><span data-stu-id="5e55a-115">By default, this role is not assigned to the Organization Management role group, which means that global admins in your organization may not be able to access the Data Investigations tool by default.</span></span> <span data-ttu-id="5e55a-116">Para corrigir isso, você pode adicionar administradores globais ao grupo de função data Investigator ou adicionar a função de gerenciamento de investigação de dados ao grupo de funções Gerenciamento da organização.</span><span class="sxs-lookup"><span data-stu-id="5e55a-116">To fix this, you can add global admins to the Data Investigator role group or add the Data Investigation Management role to the Organization Management role group.</span></span> <span data-ttu-id="5e55a-117">Uma terceira opção seria criar um grupo de função personalizado e atribuir a função de gerenciamento de investigação de dados (e outras funções) e adicionar membros apropriados.</span><span class="sxs-lookup"><span data-stu-id="5e55a-117">A third option would be to create a custom role group and assign the Data Investigation Management role (and other roles) and then add appropriate members.</span></span> <span data-ttu-id="5e55a-118">Para obter mais informações sobre grupos de funções e funções, consulte [permissões no centro de conformidade de & de segurança](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="5e55a-118">For more information about role groups and roles, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>
