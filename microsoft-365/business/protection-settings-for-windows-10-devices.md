---
title: Definir configurações de proteção de aplicativo para dispositivos Windows 10
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Saiba como criar uma política de gerenciamento de aplicativos e proteger arquivos de trabalho em dispositivos Windows 10.
ms.openlocfilehash: ca6d789e0242975a0395e6cf5653d3f43f819801
ms.sourcegitcommit: 5d11f516e78ea4a74145e19ba2300f0792c8bac1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2019
ms.locfileid: "38715243"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="9a8fa-103">Definir configurações de proteção de aplicativo para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="9a8fa-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="9a8fa-104">Criar uma política de gerenciamento de aplicativos para Windows 10</span><span class="sxs-lookup"><span data-stu-id="9a8fa-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="9a8fa-105">Se seus usuários possuírem dispositivos pessoais do Windows 10 nos quais executam tarefas de trabalho, você também pode proteger seus dados nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9a8fa-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="9a8fa-106">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="9a8fa-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="9a8fa-107">No painel de navegação esquerdo, escolha **Adicionar** **políticas** \> de **dispositivos** \> .</span><span class="sxs-lookup"><span data-stu-id="9a8fa-107">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>

3. <span data-ttu-id="9a8fa-108">No painel **Adicionar política**, insira um nome exclusivo para essa política.</span><span class="sxs-lookup"><span data-stu-id="9a8fa-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="9a8fa-109">Em **Tipo de política**, escolha **Gerenciamento de Aplicativos para Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="9a8fa-109">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="9a8fa-110">Em **tipo de dispositivo**, escolha **pessoal** ou **empresa de propriedade**.</span><span class="sxs-lookup"><span data-stu-id="9a8fa-110">Under **Device type**, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="9a8fa-111">A opção **Criptografar arquivos de trabalho** é ativada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9a8fa-111">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="9a8fa-112">Defina **Impedir que os usuários copiem os dados da empresa para arquivos pessoais e forçar que eles salvem arquivos de trabalho no OneDrive for Business** para **Ativado** se não quiser que os usuários salvem arquivos de trabalho em seus computadores.</span><span class="sxs-lookup"><span data-stu-id="9a8fa-112">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
9. <span data-ttu-id="9a8fa-113">Expanda **recuperar dados em dispositivos Windows**.</span><span class="sxs-lookup"><span data-stu-id="9a8fa-113">Expand **Recover data on Windows devices**.</span></span> <span data-ttu-id="9a8fa-114">Recomendamos **ativá-la**.</span><span class="sxs-lookup"><span data-stu-id="9a8fa-114">We recommend that you turn it **On**.</span></span>
    
    <span data-ttu-id="9a8fa-115">Antes de poder navegar para o local do certificado do Agente de Recuperação de Dados, você precisa primeiro criar um.</span><span class="sxs-lookup"><span data-stu-id="9a8fa-115">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one.</span></span> <span data-ttu-id="9a8fa-116">Para obter instruções, consulte [criar e verificar um certificado de agente de recuperação de dados (EFS) do sistema de arquivos com criptografia (EFS](https://go.microsoft.com/fwlink/p/?linkid=853700)).</span><span class="sxs-lookup"><span data-stu-id="9a8fa-116">For instructions, see [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="9a8fa-117">Por padrão, os arquivos de trabalho são criptografados usando uma chave secreta que é armazenada no dispositivo e associada ao perfil do usuário.</span><span class="sxs-lookup"><span data-stu-id="9a8fa-117">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile.</span></span> <span data-ttu-id="9a8fa-118">Somente o usuário pode abrir e descriptografar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="9a8fa-118">Only the user can open and decrypt the file.</span></span> <span data-ttu-id="9a8fa-119">No entanto, se um dispositivo for perdido ou um usuário for removido, um arquivo pode ficar preso em um estado criptografado.</span><span class="sxs-lookup"><span data-stu-id="9a8fa-119">However, if a device is lost or a user is removed, a file can be stuck in an encrypted state.</span></span> <span data-ttu-id="9a8fa-120">Um administrador pode usar o certificado de agente de recuperação de dados (DRA) para descriptografar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="9a8fa-120">An admin can use the Data Recovery Agent (DRA) certificate to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="9a8fa-122">Expanda **proteção adicional de rede e locais de nuvem** se você quiser adicionar domínios adicionais ou locais do SharePoint Online para garantir que os arquivos em todos os aplicativos listados estejam protegidos.</span><span class="sxs-lookup"><span data-stu-id="9a8fa-122">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps are protected.</span></span> <span data-ttu-id="9a8fa-123">Se desejar inserir mais de um item em um campo, use um ponto e vírgula (;) entre os itens.</span><span class="sxs-lookup"><span data-stu-id="9a8fa-123">If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span>
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="9a8fa-p105">Em seguida, decida **Quem receberá estas configurações?** Se não quiser usar o grupo de segurança padrão **Todos os Usuários**, escolha **Alterar**, escolha o grupo de segurança que deverá receber essas configurações \> **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="9a8fa-p105">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="9a8fa-127">Por fim, escolha **Adicionar** para salvar a política e atribui-la a dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9a8fa-127">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 