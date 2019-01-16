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
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Saiba como criar uma política de gerenciamento de aplicativo e proteger os arquivos de trabalho em dispositivos Windows 10.
ms.openlocfilehash: acf19a72d994185a35b2e425f8334a73a121ee10
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26864881"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="59ec6-103">Definir configurações de proteção de aplicativo para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="59ec6-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="59ec6-104">Criar uma política de gerenciamento de aplicativos para Windows 10</span><span class="sxs-lookup"><span data-stu-id="59ec6-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="59ec6-105">Se seus usuários possuírem dispositivos pessoais do Windows 10 nos quais executam tarefas de trabalho, você também pode proteger seus dados nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="59ec6-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="59ec6-p101">Acesse o [Microsoft 365 Business](https://portal.office.com) com credenciais de administrador global. Escolha o bloco **Administrador** para ir para o centro de administração.</span><span class="sxs-lookup"><span data-stu-id="59ec6-p101">Sign in to [Microsoft 365 Business](https://portal.office.com) with global admin credentials. Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="59ec6-108">No cartão **Políticas de dispositivos** do portal de administração, escolha **Adicionar política**.</span><span class="sxs-lookup"><span data-stu-id="59ec6-108">On the **Device policies** card of the admin portal, choose **Add policy**.</span></span>
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. <span data-ttu-id="59ec6-110">No painel **Adicionar política**, insira um nome exclusivo para essa política.</span><span class="sxs-lookup"><span data-stu-id="59ec6-110">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="59ec6-111">Em **Tipo de política**, escolha **Gerenciamento de Aplicativos para Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="59ec6-111">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="59ec6-112">Sob \* \* o tipo de dispositivo \* \*, escolha **pessoal** ou **Empresa proprietária**.</span><span class="sxs-lookup"><span data-stu-id="59ec6-112">Under \*\* Device type \*\*, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="59ec6-113">A opção **Criptografar arquivos de trabalho** é ativada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="59ec6-113">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="59ec6-114">Defina **Impedir que os usuários copiem os dados da empresa para arquivos pessoais e forçar que eles salvem arquivos de trabalho no OneDrive for Business** para **Ativado** se não quiser que os usuários salvem arquivos de trabalho em seus computadores.</span><span class="sxs-lookup"><span data-stu-id="59ec6-114">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
8. <span data-ttu-id="59ec6-p102">Expanda **Gerenciar como os usuários acessam arquivos do Office em dispositivos** \> defina as configurações como desejar. A opção **Gerenciar como os usuários acessam dispositivos do Office em dispositivos móveis** é **Desativada** por padrão, mas recomenda-se que ela seja **Ativada** e que os valores padrão sejam aceitos. Confira [Configurações disponíveis](protection-settings-for-windows-10-devices.md#bkmk_settings) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="59ec6-p102">Expand **Manage how users access Office files on devices** \> configure the settings how you would like. The **Manage how users access Office devices on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values. See [Available settings](protection-settings-for-windows-10-devices.md#bkmk_settings) for more information.</span></span> 
    
    <span data-ttu-id="59ec6-118">Você sempre poderá usar o link **Redefinir as configurações padrão** para voltar para a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="59ec6-118">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
9. <span data-ttu-id="59ec6-119">Expanda **Recupera dados em dispositivos Windows** e é recomendável que essa opção seja **Ativada**.</span><span class="sxs-lookup"><span data-stu-id="59ec6-119">Expand **Recover data on Windows devices** and it is recommended that you turn it **On**.</span></span>
    
    <span data-ttu-id="59ec6-p103">Antes de poder navegar para o local do certificado do Agente de Recuperação de Dados, você precisa primeiro criar um. Para obter instruções, veja [Criar e verificar se um certificado de Agente de Recuperação de Dados (DRA) para o Encrypting File System (EFS)](https://go.microsoft.com/fwlink/p/?linkid=853700).</span><span class="sxs-lookup"><span data-stu-id="59ec6-p103">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one. For instructions see, [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="59ec6-p104">Por padrão, os arquivos de trabalho são criptografados usando uma chave secreta que é armazenada no dispositivo e associada ao perfil do usuário. Somente o usuário pode abrir e descriptografar o arquivo. No entanto, se um dispositivo for perdido ou um usuário for removido, um arquivo pode ficar preso em um estado criptografado. O certificado do Agente de Recuperação de Dados (DRA) pode ser usado por um administrador para descriptografar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="59ec6-p104">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile. Only the user can open and decrypt the file. However, if a device is lost or a user is removed, a file can be stuck in an encrypted state. The Data Recovery Agent (DRA) certificate can be used by an admin to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="59ec6-p105">Expanda **Proteger locais de rede e nuvem adicionais** se quiser adicionar mais domínios ou locais do SharePoint Online para garantir que os arquivos em todos os aplicativos listados sejam protegidos. Se desejar inserir mais de um item em um campo, use um ponto e vírgula (;) entre os itens.</span><span class="sxs-lookup"><span data-stu-id="59ec6-p105">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps will be protected. If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span> 
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="59ec6-p106">Em seguida, decida **Quem receberá estas configurações?** Se não quiser usar o grupo de segurança padrão **Todos os Usuários**, escolha **Alterar**, escolha o grupo de segurança que deverá receber essas configurações \> **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="59ec6-p106">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="59ec6-132">Por fim, escolha **Adicionar** para salvar a política e atribui-la a dispositivos.</span><span class="sxs-lookup"><span data-stu-id="59ec6-132">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="59ec6-133">Configurações disponíveis</span><span class="sxs-lookup"><span data-stu-id="59ec6-133">Available settings</span></span>

<span data-ttu-id="59ec6-134">As configurações a seguir estão disponíveis para gerenciar a forma como os usuários acessam arquivos de trabalho do Office.</span><span class="sxs-lookup"><span data-stu-id="59ec6-134">The following settings are available to manage how users access Office work files.</span></span>
  
<span data-ttu-id="59ec6-135">Para saber mais, confira [Como os recursos de proteção no Microsoft 365 Business são mapeados para as configurações do Intune](map-protection-features-to-intune-settings.md).</span><span class="sxs-lookup"><span data-stu-id="59ec6-135">For more information, see [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md).</span></span>
  
|<span data-ttu-id="59ec6-136">**Configuração**</span><span class="sxs-lookup"><span data-stu-id="59ec6-136">**Setting**</span></span>|<span data-ttu-id="59ec6-137">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="59ec6-137">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="59ec6-138">Exigir um PIN ou uma impressão digital para acessar aplicativos do Office</span><span class="sxs-lookup"><span data-stu-id="59ec6-138">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="59ec6-139">Se essa configuração estiver **Ativada**, os usuários precisarão fornecer outra forma de autenticação, além de seu nome de usuário e senha, para poderem usar os aplicativos do Office em seus dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="59ec6-139">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="59ec6-140">Redefinir o PIN quando houver muitas falhas de logon</span><span class="sxs-lookup"><span data-stu-id="59ec6-140">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="59ec6-141">Para impedir que um usuário não autorizado adivinhe um PIN, o PIN será redefinido após determinado número de tentativas incorretas.</span><span class="sxs-lookup"><span data-stu-id="59ec6-141">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="59ec6-142">Exigir que os usuários entrem novamente depois que os aplicativos do Office ficarem ociosos</span><span class="sxs-lookup"><span data-stu-id="59ec6-142">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="59ec6-143">Esta configuração determina quanto tempo o usuário pode ficar ocioso antes de ser solicitado a entrar novamente.</span><span class="sxs-lookup"><span data-stu-id="59ec6-143">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
   

