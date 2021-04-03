---
title: Editar ou definir configurações de proteção de aplicativos para dispositivos Windows 10
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Saiba como criar ou editar políticas de gerenciamento de aplicativos e proteger arquivos de trabalho em dispositivos Windows 10 pessoais de seus usuários.
ms.openlocfilehash: aa270c563e6bdce6fd48f8713d7db3ce23921925
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580005"
---
# <a name="set-or-edit-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="afc82-103">Definir ou editar configurações de proteção de aplicativos para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="afc82-103">Set or edit application protection settings for Windows 10 devices</span></span>

<span data-ttu-id="afc82-104">Este artigo se aplica ao Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="afc82-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="edit-an-app-management-policy-for-windows-10"></a><span data-ttu-id="afc82-105">Editar uma política de gerenciamento de aplicativos para o Windows 10</span><span class="sxs-lookup"><span data-stu-id="afc82-105">Edit an app management policy for Windows 10</span></span>

1. <span data-ttu-id="afc82-106">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="afc82-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>     
2. <span data-ttu-id="afc82-107">À esquerda, escolha **Políticas** de \> **Dispositivos** .</span><span class="sxs-lookup"><span data-stu-id="afc82-107">On the left nav, choose **Devices** \> **Policies** .</span></span>
1. <span data-ttu-id="afc82-108">Escolha uma política de aplicativo do Windows existente e **edite**.</span><span class="sxs-lookup"><span data-stu-id="afc82-108">Choose an existing Windows app policy and then **Edit**.</span></span>
1. <span data-ttu-id="afc82-109">Escolha **Editar** ao lado de uma configuração que você deseja alterar e, em seguida, **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="afc82-109">Choose **Edit** next to a setting you want to change and then **Save**.</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="afc82-110">Criar uma política de gerenciamento de aplicativos para Windows 10</span><span class="sxs-lookup"><span data-stu-id="afc82-110">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="afc82-111">Se seus usuários possuírem dispositivos pessoais do Windows 10 nos quais executam tarefas de trabalho, você também pode proteger seus dados nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="afc82-111">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="afc82-112">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="afc82-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
2. <span data-ttu-id="afc82-113">À esquerda, escolha  Políticas de \>  \> **Dispositivos Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="afc82-113">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
3. <span data-ttu-id="afc82-114">No painel **Adicionar política**, insira um nome exclusivo para essa política.</span><span class="sxs-lookup"><span data-stu-id="afc82-114">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
4. <span data-ttu-id="afc82-115">Em **Tipo de política**, escolha **Gerenciamento de Aplicativos para Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="afc82-115">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
5. <span data-ttu-id="afc82-116">Em **Tipo de dispositivo**, escolha **Personal** ou Company **Owned**.</span><span class="sxs-lookup"><span data-stu-id="afc82-116">Under **Device type**, choose either **Personal** or **Company Owned**.</span></span>
6. <span data-ttu-id="afc82-117">A opção **Criptografar arquivos de trabalho** é ativada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="afc82-117">The **Encrypt work files** is turned on automatically.</span></span> 
7. <span data-ttu-id="afc82-118">Defina **Impedir que os usuários copiem os dados da empresa para arquivos pessoais e forçar que eles salvem arquivos de trabalho no OneDrive for Business** para **Ativado** se não quiser que os usuários salvem arquivos de trabalho em seus computadores.</span><span class="sxs-lookup"><span data-stu-id="afc82-118">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
9. <span data-ttu-id="afc82-119">Expanda **Recuperar dados em dispositivos Windows.**</span><span class="sxs-lookup"><span data-stu-id="afc82-119">Expand **Recover data on Windows devices**.</span></span> <span data-ttu-id="afc82-120">Recomendamos que você a **a ligue.**</span><span class="sxs-lookup"><span data-stu-id="afc82-120">We recommend that you turn it **On**.</span></span>
    <span data-ttu-id="afc82-121">Antes de poder navegar para o local do certificado do Agente de Recuperação de Dados, você precisa primeiro criar um.</span><span class="sxs-lookup"><span data-stu-id="afc82-121">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one.</span></span> <span data-ttu-id="afc82-122">Para obter instruções, [consulte Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA).](/windows/security/information-protection/windows-information-protection/create-and-verify-an-efs-dra-certificate)</span><span class="sxs-lookup"><span data-stu-id="afc82-122">For instructions, see [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](/windows/security/information-protection/windows-information-protection/create-and-verify-an-efs-dra-certificate).</span></span>
    
    <span data-ttu-id="afc82-123">Por padrão, os arquivos de trabalho são criptografados usando uma chave secreta que é armazenada no dispositivo e associada ao perfil do usuário.</span><span class="sxs-lookup"><span data-stu-id="afc82-123">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile.</span></span> <span data-ttu-id="afc82-124">Somente o usuário pode abrir e descriptografar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="afc82-124">Only the user can open and decrypt the file.</span></span> <span data-ttu-id="afc82-125">No entanto, se um dispositivo for perdido ou um usuário for removido, um arquivo pode ficar preso em um estado criptografado.</span><span class="sxs-lookup"><span data-stu-id="afc82-125">However, if a device is lost or a user is removed, a file can be stuck in an encrypted state.</span></span> <span data-ttu-id="afc82-126">Um administrador pode usar o certificado DRA (Agente de Recuperação de Dados) para descriptografar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="afc82-126">An admin can use the Data Recovery Agent (DRA) certificate to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="afc82-128">Expanda **Proteger locais** de rede e nuvem adicionais se você quiser adicionar domínios adicionais ou locais do SharePoint Online para garantir que os arquivos em todos os aplicativos listados sejam protegidos.</span><span class="sxs-lookup"><span data-stu-id="afc82-128">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps are protected.</span></span> <span data-ttu-id="afc82-129">Se desejar inserir mais de um item em um campo, use um ponto e vírgula (;) entre os itens.</span><span class="sxs-lookup"><span data-stu-id="afc82-129">If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span>
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="afc82-p104">Em seguida, decida **Quem receberá estas configurações?** Se não quiser usar o grupo de segurança padrão **Todos os Usuários**, escolha **Alterar**, escolha o grupo de segurança que deverá receber essas configurações \> **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="afc82-p104">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
12. <span data-ttu-id="afc82-133">Por fim, escolha **Adicionar** para salvar a política e atribui-la a dispositivos.</span><span class="sxs-lookup"><span data-stu-id="afc82-133">Finally, choose **Add** to save the policy, and assign it to devices.</span></span>