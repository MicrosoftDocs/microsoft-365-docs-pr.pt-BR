---
title: Definir configurações de proteção de aplicativo para dispositivos Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Saiba como criar uma política de gerenciamento de aplicativos e proteger arquivos de trabalho em dispositivos Windows 10.
ms.openlocfilehash: 289c6a74f6ccb53f6a833612a7b4a5bcddd3ea56
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278149"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="c801d-103">Definir configurações de proteção de aplicativo para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="c801d-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="c801d-104">Criar uma política de gerenciamento de aplicativos para Windows 10</span><span class="sxs-lookup"><span data-stu-id="c801d-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="c801d-105">Se seus usuários possuírem dispositivos pessoais do Windows 10 nos quais executam tarefas de trabalho, você também pode proteger seus dados nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c801d-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="c801d-106">Entre no [centro de administração](https://go.microsoft.com/fwlink/p/?linkid=837890) com credenciais de administrador global.</span><span class="sxs-lookup"><span data-stu-id="c801d-106">Sign in to [admin center](https://go.microsoft.com/fwlink/p/?linkid=837890) with global admin credentials.</span></span> <span data-ttu-id="c801d-107">Escolha o bloco **Administrador** para ir para o centro de administração.</span><span class="sxs-lookup"><span data-stu-id="c801d-107">Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="c801d-108">No painel de navegação esquerdo, escolha **Adicionar** **políticas** \> de **dispositivos** \> .</span><span class="sxs-lookup"><span data-stu-id="c801d-108">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>

3. <span data-ttu-id="c801d-109">No painel **Adicionar política**, insira um nome exclusivo para essa política.</span><span class="sxs-lookup"><span data-stu-id="c801d-109">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="c801d-110">Em **Tipo de política**, escolha **Gerenciamento de Aplicativos para Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="c801d-110">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="c801d-111">Under \*\* Device type \*\*, choose either **Personal** or **Company Owned**.</span><span class="sxs-lookup"><span data-stu-id="c801d-111">Under \*\* Device type \*\*, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="c801d-112">A opção **Criptografar arquivos de trabalho** é ativada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c801d-112">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="c801d-113">Defina **Impedir que os usuários copiem os dados da empresa para arquivos pessoais e forçar que eles salvem arquivos de trabalho no OneDrive for Business** para **Ativado** se não quiser que os usuários salvem arquivos de trabalho em seus computadores.</span><span class="sxs-lookup"><span data-stu-id="c801d-113">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
8. <span data-ttu-id="c801d-114">Expanda **Gerenciar como os usuários acessam arquivos do Office em dispositivos** \> defina as configurações como desejar.</span><span class="sxs-lookup"><span data-stu-id="c801d-114">Expand **Manage how users access Office files on devices** \> configure the settings how you would like.</span></span> <span data-ttu-id="c801d-115">A opção **Gerenciar como os usuários acessam dispositivos do Office em dispositivos móveis** é **Desativada** por padrão, mas recomenda-se que ela seja **Ativada** e que os valores padrão sejam aceitos.</span><span class="sxs-lookup"><span data-stu-id="c801d-115">The **Manage how users access Office devices on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="c801d-116">ConFira [configurações disponíveis](#available-settings)para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c801d-116">See [Available settings](#available-settings)for more information.</span></span> 
    
    <span data-ttu-id="c801d-117">Você sempre poderá usar o link **Redefinir as configurações padrão** para voltar para a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="c801d-117">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
9. <span data-ttu-id="c801d-118">Expanda **Recupera dados em dispositivos Windows** e é recomendável que essa opção seja **Ativada**.</span><span class="sxs-lookup"><span data-stu-id="c801d-118">Expand **Recover data on Windows devices** and it is recommended that you turn it **On**.</span></span>
    
    <span data-ttu-id="c801d-p103">Antes de poder navegar para o local do certificado do Agente de Recuperação de Dados, você precisa primeiro criar um. Para obter instruções, veja [Criar e verificar se um certificado de Agente de Recuperação de Dados (DRA) para o Encrypting File System (EFS)](https://go.microsoft.com/fwlink/p/?linkid=853700).</span><span class="sxs-lookup"><span data-stu-id="c801d-p103">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one. For instructions see, [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="c801d-p104">Por padrão, os arquivos de trabalho são criptografados usando uma chave secreta que é armazenada no dispositivo e associada ao perfil do usuário. Somente o usuário pode abrir e descriptografar o arquivo. No entanto, se um dispositivo for perdido ou um usuário for removido, um arquivo pode ficar preso em um estado criptografado. O certificado do Agente de Recuperação de Dados (DRA) pode ser usado por um administrador para descriptografar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="c801d-p104">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile. Only the user can open and decrypt the file. However, if a device is lost or a user is removed, a file can be stuck in an encrypted state. The Data Recovery Agent (DRA) certificate can be used by an admin to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="c801d-p105">Expanda **Proteger locais de rede e nuvem adicionais** se quiser adicionar mais domínios ou locais do SharePoint Online para garantir que os arquivos em todos os aplicativos listados sejam protegidos. Se desejar inserir mais de um item em um campo, use um ponto e vírgula (;) entre os itens.</span><span class="sxs-lookup"><span data-stu-id="c801d-p105">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps will be protected. If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span> 
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="c801d-p106">Em seguida, decida **Quem receberá estas configurações?** Se não quiser usar o grupo de segurança padrão **Todos os Usuários**, escolha **Alterar**, escolha o grupo de segurança que deverá receber essas configurações \> **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="c801d-p106">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="c801d-131">Por fim, escolha **Adicionar** para salvar a política e atribui-la a dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c801d-131">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="c801d-132">Configurações disponíveis</span><span class="sxs-lookup"><span data-stu-id="c801d-132">Available settings</span></span>

<span data-ttu-id="c801d-133">As configurações a seguir estão disponíveis para gerenciar a forma como os usuários acessam arquivos de trabalho do Office.</span><span class="sxs-lookup"><span data-stu-id="c801d-133">The following settings are available to manage how users access Office work files.</span></span>
  
<span data-ttu-id="c801d-134">Para saber mais, confira [Como os recursos de proteção no Microsoft 365 Business são mapeados para as configurações do Intune](map-protection-features-to-intune-settings.md).</span><span class="sxs-lookup"><span data-stu-id="c801d-134">For more information, see [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md).</span></span>
  
|<span data-ttu-id="c801d-135">**Configuração**</span><span class="sxs-lookup"><span data-stu-id="c801d-135">**Setting**</span></span>|<span data-ttu-id="c801d-136">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c801d-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c801d-137">Exigir um PIN ou uma impressão digital para acessar aplicativos do Office</span><span class="sxs-lookup"><span data-stu-id="c801d-137">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="c801d-138">Se essa configuração estiver **Ativada**, os usuários precisarão fornecer outra forma de autenticação, além de seu nome de usuário e senha, para poderem usar os aplicativos do Office em seus dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="c801d-138">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="c801d-139">Redefinir o PIN quando houver muitas falhas de logon</span><span class="sxs-lookup"><span data-stu-id="c801d-139">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="c801d-140">Para impedir que um usuário não autorizado adivinhe um PIN, o PIN será redefinido após determinado número de tentativas incorretas.</span><span class="sxs-lookup"><span data-stu-id="c801d-140">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="c801d-141">Exigir que os usuários entrem novamente depois que os aplicativos do Office ficarem ociosos</span><span class="sxs-lookup"><span data-stu-id="c801d-141">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="c801d-142">Esta configuração determina quanto tempo o usuário pode ficar ocioso antes de ser solicitado a entrar novamente.</span><span class="sxs-lookup"><span data-stu-id="c801d-142">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
   

