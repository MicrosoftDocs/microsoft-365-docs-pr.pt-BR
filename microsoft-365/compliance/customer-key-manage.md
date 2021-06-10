---
title: Gerenciar Chave do Cliente
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Depois de configurar a Chave do Cliente, saiba como gerenciá-la restaurando chaves AKV e gerenciando permissões e criando e atribuindo políticas de criptografia de dados.
ms.openlocfilehash: da806ec9dcf1327ec5fdd6b0a0c9e7f22c89584e
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345053"
---
# <a name="manage-customer-key"></a><span data-ttu-id="c9f34-103">Gerenciar Chave do Cliente</span><span class="sxs-lookup"><span data-stu-id="c9f34-103">Manage Customer Key</span></span>

<span data-ttu-id="c9f34-104">Depois de configurar a Chave do Cliente para Office 365, você precisará criar e atribuir uma ou mais políticas de criptografia de dados (DEP).</span><span class="sxs-lookup"><span data-stu-id="c9f34-104">After you've set up Customer Key for Office 365, you'll need to create and assign one or more data encryption policies (DEP).</span></span> <span data-ttu-id="c9f34-105">Depois de ter atribuído seus DEPs, você pode gerenciar suas chaves conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="c9f34-105">Once you've assigned your DEPs, you can manage your keys as described in this article.</span></span> <span data-ttu-id="c9f34-106">Saiba mais sobre a Chave do Cliente nos tópicos relacionados.</span><span class="sxs-lookup"><span data-stu-id="c9f34-106">Learn more about Customer Key in the related topics.</span></span>

## <a name="create-a-dep-for-use-with-multiple-workloads-for-all-tenant-users"></a><span data-ttu-id="c9f34-107">Criar um DEP para uso com várias cargas de trabalho para todos os usuários de locatários</span><span class="sxs-lookup"><span data-stu-id="c9f34-107">Create a DEP for use with multiple workloads for all tenant users</span></span>

<span data-ttu-id="c9f34-108">Antes de começar, verifique se você concluiu as tarefas necessárias para configurar o Cliente.</span><span class="sxs-lookup"><span data-stu-id="c9f34-108">Before you begin, ensure that you've completed the tasks required to set up Customer.</span></span> <span data-ttu-id="c9f34-109">Para obter informações, [consulte Set up Customer Key](customer-key-set-up.md).</span><span class="sxs-lookup"><span data-stu-id="c9f34-109">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span> <span data-ttu-id="c9f34-110">Para criar o DEP, você precisa das URIs do Cofre de Chaves obtidas durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="c9f34-110">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="c9f34-111">Para obter informações, [consulte Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span><span class="sxs-lookup"><span data-stu-id="c9f34-111">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>

<span data-ttu-id="c9f34-112">Para criar uma DEP de várias cargas de trabalho, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c9f34-112">To create a multi-workload DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="c9f34-113">Em seu computador local, usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador ou administrador de conformidade em sua organização, conecte-se ao [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) em uma janela Windows PowerShell de conformidade.</span><span class="sxs-lookup"><span data-stu-id="c9f34-113">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="c9f34-114">Para criar um DEP, use o New-M365DataAtRestEncryptionPolicy cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c9f34-114">To create a DEP, use the New-M365DataAtRestEncryptionPolicy cmdlet.</span></span>

   ```powershell
   New-M365DataAtRestEncryptionPolicy -Name <PolicyName> -AzureKeyIDs <KeyVaultURI1, KeyVaultURI2> [-Description <String>]
   ```

   <span data-ttu-id="c9f34-115">Onde:</span><span class="sxs-lookup"><span data-stu-id="c9f34-115">Where:</span></span>

   - <span data-ttu-id="c9f34-116">*PolicyName* é o nome que você deseja usar para a política.</span><span class="sxs-lookup"><span data-stu-id="c9f34-116">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="c9f34-117">Os nomes não podem conter espaços.</span><span class="sxs-lookup"><span data-stu-id="c9f34-117">Names can't contain spaces.</span></span> <span data-ttu-id="c9f34-118">Por exemplo, Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="c9f34-118">For example, Contoso_Global.</span></span>

   - <span data-ttu-id="c9f34-119">*KeyVaultURI1* é o URI da primeira chave da política.</span><span class="sxs-lookup"><span data-stu-id="c9f34-119">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="c9f34-120">Por exemplo, <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.</span><span class="sxs-lookup"><span data-stu-id="c9f34-120">For example, <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.</span></span>

   - <span data-ttu-id="c9f34-121">*KeyVaultURI2* é o URI da segunda chave da política.</span><span class="sxs-lookup"><span data-stu-id="c9f34-121">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="c9f34-122">Por exemplo, <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>.</span><span class="sxs-lookup"><span data-stu-id="c9f34-122">For example, <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>.</span></span> <span data-ttu-id="c9f34-123">Separe as duas URIs por uma vírgula e um espaço.</span><span class="sxs-lookup"><span data-stu-id="c9f34-123">Separate the two URIs by a comma and a space.</span></span>

   - <span data-ttu-id="c9f34-124">*Descrição da* política é uma descrição amigável da política que ajudará você a lembrar para que a política é.</span><span class="sxs-lookup"><span data-stu-id="c9f34-124">*Policy Description* is a user-friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="c9f34-125">Você pode incluir espaços na descrição.</span><span class="sxs-lookup"><span data-stu-id="c9f34-125">You can include spaces in the description.</span></span> <span data-ttu-id="c9f34-126">Por exemplo, "Política raiz para várias cargas de trabalho para todos os usuários no locatário.".</span><span class="sxs-lookup"><span data-stu-id="c9f34-126">For example, "Root policy for multiple workloads for all users in the tenant.".</span></span>

<span data-ttu-id="c9f34-127">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="c9f34-127">Example:</span></span>

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Contoso_Global" -AzureKeyIDs "https://contosoWestUSvault1.vault.azure.net/keys/Key_01","https://contosoCentralUSvault1.vault.azure.net/keys/Key_02" -Description "Policy for multiple workloads for all users in the tenant."
```

### <a name="assign-multi-workload-policy"></a><span data-ttu-id="c9f34-128">Atribuir política de várias cargas de trabalho</span><span class="sxs-lookup"><span data-stu-id="c9f34-128">Assign multi-workload policy</span></span>

<span data-ttu-id="c9f34-129">Atribua o DEP usando o Set-M365DataAtRestEncryptionPolicyAssignment cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c9f34-129">Assign the DEP by using the Set-M365DataAtRestEncryptionPolicyAssignment cmdlet.</span></span> <span data-ttu-id="c9f34-130">Depois de atribuir a política, Microsoft 365 criptografa os dados com a chave identificada no DEP.</span><span class="sxs-lookup"><span data-stu-id="c9f34-130">Once you assign the policy, Microsoft 365 encrypts the data with the key identified in the DEP.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy <PolicyName or ID>
```

 <span data-ttu-id="c9f34-131">Onde *PolicyName* é o nome da política.</span><span class="sxs-lookup"><span data-stu-id="c9f34-131">Where *PolicyName* is the name of the policy.</span></span> <span data-ttu-id="c9f34-132">Por exemplo, Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="c9f34-132">For example, Contoso_Global.</span></span>

<span data-ttu-id="c9f34-133">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="c9f34-133">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Contoso_Global"
```

## <a name="create-a-dep-for-use-with-exchange-online-mailboxes"></a><span data-ttu-id="c9f34-134">Criar um DEP para uso com Exchange Online caixas de correio</span><span class="sxs-lookup"><span data-stu-id="c9f34-134">Create a DEP for use with Exchange Online mailboxes</span></span>

<span data-ttu-id="c9f34-135">Antes de começar, verifique se você concluiu as tarefas necessárias para configurar o Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="c9f34-135">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="c9f34-136">Para obter informações, [consulte Set up Customer Key](customer-key-set-up.md).</span><span class="sxs-lookup"><span data-stu-id="c9f34-136">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span> <span data-ttu-id="c9f34-137">Você concluirá essas etapas conectando-se remotamente ao Exchange Online com Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9f34-137">You'll complete these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>

<span data-ttu-id="c9f34-138">Um DEP é associado a um conjunto de chaves armazenadas no Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="c9f34-138">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="c9f34-139">Você atribui um DEP a uma caixa de correio em Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c9f34-139">You assign a DEP to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="c9f34-140">Microsoft 365 usar as chaves identificadas na política para criptografar a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="c9f34-140">Microsoft 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="c9f34-141">Para criar o DEP, você precisa das URIs do Cofre de Chaves obtidas durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="c9f34-141">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="c9f34-142">Para obter informações, [consulte Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span><span class="sxs-lookup"><span data-stu-id="c9f34-142">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>

<span data-ttu-id="c9f34-143">Lembre-se!</span><span class="sxs-lookup"><span data-stu-id="c9f34-143">Remember!</span></span> <span data-ttu-id="c9f34-144">Quando você cria um DEP, especifica duas chaves em dois cofres de chave do Azure diferentes.</span><span class="sxs-lookup"><span data-stu-id="c9f34-144">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="c9f34-145">Crie essas chaves em duas regiões separadas do Azure para garantir a redundância geográfica.</span><span class="sxs-lookup"><span data-stu-id="c9f34-145">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>

<span data-ttu-id="c9f34-146">Para criar um DEP a ser usado com uma caixa de correio, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c9f34-146">To create a DEP to use with a mailbox, follow these steps:</span></span>
  
1. <span data-ttu-id="c9f34-147">No computador local, usando uma conta de estudante ou de trabalho que tenha permissões de administrador global ou Exchange Online de administrador em sua organização, conecte-se ao [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) em uma janela Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9f34-147">On your local computer, using a work or school account that has global administrator or Exchange Online admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="c9f34-148">Para criar um DEP, use o cmdlet New-DataEncryptionPolicy digitando o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="c9f34-148">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="c9f34-149">Onde:</span><span class="sxs-lookup"><span data-stu-id="c9f34-149">Where:</span></span>

   - <span data-ttu-id="c9f34-150">*PolicyName* é o nome que você deseja usar para a política.</span><span class="sxs-lookup"><span data-stu-id="c9f34-150">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="c9f34-151">Os nomes não podem conter espaços.</span><span class="sxs-lookup"><span data-stu-id="c9f34-151">Names can't contain spaces.</span></span> <span data-ttu-id="c9f34-152">Por exemplo, USA_mailboxes.</span><span class="sxs-lookup"><span data-stu-id="c9f34-152">For example, USA_mailboxes.</span></span>

   - <span data-ttu-id="c9f34-153">*Descrição da* política é uma descrição amigável da política que ajudará você a lembrar para que a política é.</span><span class="sxs-lookup"><span data-stu-id="c9f34-153">*Policy Description* is a user-friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="c9f34-154">Você pode incluir espaços na descrição.</span><span class="sxs-lookup"><span data-stu-id="c9f34-154">You can include spaces in the description.</span></span> <span data-ttu-id="c9f34-155">Por exemplo, "Chave raiz para caixas de correio nos EUA e seus territórios".</span><span class="sxs-lookup"><span data-stu-id="c9f34-155">For example, "Root key for mailboxes in USA and its territories".</span></span>

   - <span data-ttu-id="c9f34-156">*KeyVaultURI1* é o URI da primeira chave da política.</span><span class="sxs-lookup"><span data-stu-id="c9f34-156">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="c9f34-157">Por exemplo, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span><span class="sxs-lookup"><span data-stu-id="c9f34-157">For example, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span></span>

   - <span data-ttu-id="c9f34-158">*KeyVaultURI2* é o URI da segunda chave da política.</span><span class="sxs-lookup"><span data-stu-id="c9f34-158">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="c9f34-159">Por exemplo, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span><span class="sxs-lookup"><span data-stu-id="c9f34-159">For example, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span></span> <span data-ttu-id="c9f34-160">Separe as duas URIs por uma vírgula e um espaço.</span><span class="sxs-lookup"><span data-stu-id="c9f34-160">Separate the two URIs by a comma and a space.</span></span>

   <span data-ttu-id="c9f34-161">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="c9f34-161">Example:</span></span>
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault02.vault.azure.net/keys/USA_key_01, https://contoso_CentralUSvault02.vault.azure.net/keys/USA_Key_02
   ```

<span data-ttu-id="c9f34-162">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).</span><span class="sxs-lookup"><span data-stu-id="c9f34-162">For detailed syntax and parameter information, see [New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).</span></span>

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="c9f34-163">Atribuir um DEP a uma caixa de correio</span><span class="sxs-lookup"><span data-stu-id="c9f34-163">Assign a DEP to a mailbox</span></span>

<span data-ttu-id="c9f34-164">Atribua o DEP a uma caixa de correio usando Set-Mailbox cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c9f34-164">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="c9f34-165">Depois de atribuir a política, Microsoft 365 criptografar a caixa de correio com a chave identificada no DEP.</span><span class="sxs-lookup"><span data-stu-id="c9f34-165">Once you assign the policy, Microsoft 365 can encrypt the mailbox with the key identified in the DEP.</span></span>
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="c9f34-166">Onde *MailboxIdParameter* especifica uma caixa de correio de usuário.</span><span class="sxs-lookup"><span data-stu-id="c9f34-166">Where *MailboxIdParameter* specifies a user mailbox.</span></span> <span data-ttu-id="c9f34-167">Para obter mais informações sobre o Set-Mailbox cmdlet, consulte [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="c9f34-167">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span></span>

<span data-ttu-id="c9f34-168">Em ambientes híbridos, você pode atribuir um DEP aos dados de caixa de correio locais que são sincronizados no seu locatário Exchange Online local.</span><span class="sxs-lookup"><span data-stu-id="c9f34-168">In hybrid environments, you can assign a DEP to the on-premises mailbox data that is synchronized into your Exchange Online tenant.</span></span> <span data-ttu-id="c9f34-169">Para atribuir um DEP a esses dados de caixa de correio sincronizados, você usará o cmdlet Set-MailUser usuário.</span><span class="sxs-lookup"><span data-stu-id="c9f34-169">To assign a DEP to this synchronized mailbox data, you'll use the Set-MailUser cmdlet.</span></span> <span data-ttu-id="c9f34-170">Para obter mais informações sobre dados de caixa de correio no ambiente híbrido, consulte caixas de correio locais usando Outlook para iOS e Android com [autenticação moderna híbrida.](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)</span><span class="sxs-lookup"><span data-stu-id="c9f34-170">For more information about mailbox data in the hybrid environment, see [on-premises mailboxes using Outlook for iOS and Android with hybrid Modern Authentication](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth).</span></span>

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="c9f34-171">Onde *MailUserIdParameter* especifica um usuário de email (também conhecido como um usuário habilitado para email).</span><span class="sxs-lookup"><span data-stu-id="c9f34-171">Where *MailUserIdParameter* specifies a mail user (also known as a mail-enabled user).</span></span> <span data-ttu-id="c9f34-172">Para obter mais informações sobre o Set-MailUser cmdlet, consulte [Set-MailUser](/powershell/module/exchange/set-mailuser).</span><span class="sxs-lookup"><span data-stu-id="c9f34-172">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

## <a name="create-a-dep-for-use-with-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="c9f34-173">Criar um DEP para uso com SharePoint online, OneDrive for Business e Teams arquivos</span><span class="sxs-lookup"><span data-stu-id="c9f34-173">Create a DEP for use with SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="c9f34-174">Antes de começar, verifique se você concluiu as tarefas necessárias para configurar o Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="c9f34-174">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="c9f34-175">Para obter informações, [consulte Set up Customer Key](customer-key-set-up.md).</span><span class="sxs-lookup"><span data-stu-id="c9f34-175">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span>
  
<span data-ttu-id="c9f34-176">Para configurar a Chave do Cliente para arquivos SharePoint Online, OneDrive for Business e Teams você conclui essas etapas conectando-se remotamente ao SharePoint Online com Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9f34-176">To set up Customer Key for SharePoint Online, OneDrive for Business, and Teams files you complete these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
<span data-ttu-id="c9f34-177">Você associa um DEP a um conjunto de chaves armazenadas no Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="c9f34-177">You associate a DEP with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="c9f34-178">Você aplica uma DEP a todos os seus dados em uma localização geográfica, também chamada de geo.</span><span class="sxs-lookup"><span data-stu-id="c9f34-178">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="c9f34-179">Se você usar o recurso multi-geo da Office 365, poderá criar um DEP por geo com a capacidade de usar chaves diferentes por geo.</span><span class="sxs-lookup"><span data-stu-id="c9f34-179">If you use the multi-geo feature of Office 365, you can create one DEP per geo with the capability to use different keys per geo.</span></span> <span data-ttu-id="c9f34-180">Se você não estiver usando multi-geo, poderá criar um DEP em sua organização para uso com arquivos SharePoint Online, OneDrive for Business e Teams.</span><span class="sxs-lookup"><span data-stu-id="c9f34-180">If you aren't using multi-geo, you can create one DEP in your organization for use with SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="c9f34-181">Microsoft 365 usa as chaves identificadas no DEP para criptografar seus dados nesse geo.</span><span class="sxs-lookup"><span data-stu-id="c9f34-181">Microsoft 365 uses the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="c9f34-182">Para criar o DEP, você precisa das URIs do Cofre de Chaves obtidas durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="c9f34-182">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="c9f34-183">Para obter informações, [consulte Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span><span class="sxs-lookup"><span data-stu-id="c9f34-183">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>
  
<span data-ttu-id="c9f34-184">Lembre-se!</span><span class="sxs-lookup"><span data-stu-id="c9f34-184">Remember!</span></span> <span data-ttu-id="c9f34-185">Quando você cria um DEP, especifica duas chaves em dois cofres de chave do Azure diferentes.</span><span class="sxs-lookup"><span data-stu-id="c9f34-185">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="c9f34-186">Crie essas chaves em duas regiões separadas do Azure para garantir a redundância geográfica.</span><span class="sxs-lookup"><span data-stu-id="c9f34-186">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="c9f34-187">Para criar uma DEP, você precisa se conectar remotamente ao SharePoint Online usando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9f34-187">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="c9f34-188">No computador local, usando uma conta de trabalho ou de estudante que tenha permissões globais de administrador em sua organização, Conexão [para SharePoint PowerShell Online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="c9f34-188">On your local computer, using a work or school account that has global administrator permissions in your organization, [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps).</span></span>

2. <span data-ttu-id="c9f34-189">No Shell Microsoft Office SharePoint Online Gerenciamento, execute o cmdlet Register-SPODataEncryptionPolicy da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="c9f34-189">In the Microsoft SharePoint Online Management Shell, run the Register-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="c9f34-190">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="c9f34-190">Example:</span></span>
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   <span data-ttu-id="c9f34-191">Quando você registra o DEP, a criptografia começa nos dados no geo.</span><span class="sxs-lookup"><span data-stu-id="c9f34-191">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="c9f34-192">A criptografia pode levar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="c9f34-192">Encryption can take some time.</span></span> <span data-ttu-id="c9f34-193">Para obter mais informações sobre como usar esse parâmetro, consulte [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="c9f34-193">For more information on using this parameter, see [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-mailboxes"></a><span data-ttu-id="c9f34-194">Exibir os DEPs que você criou para Exchange Online caixas de correio</span><span class="sxs-lookup"><span data-stu-id="c9f34-194">View the DEPs you've created for Exchange Online mailboxes</span></span>

<span data-ttu-id="c9f34-195">Para exibir uma lista de todos os DEPs que você criou para caixas de correio, use o cmdlet Get-DataEncryptionPolicy PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9f34-195">To view a list of all the DEPs you've created for mailboxes, use the Get-DataEncryptionPolicy PowerShell cmdlet.</span></span>

1. <span data-ttu-id="c9f34-196">Usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização, [conecte-se Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c9f34-196">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="c9f34-197">Para retornar todos os DEPs da sua organização, execute o cmdlet Get-DataEncryptionPolicy sem parâmetros.</span><span class="sxs-lookup"><span data-stu-id="c9f34-197">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

   ```powershell
   Get-DataEncryptionPolicy
   ```

   <span data-ttu-id="c9f34-198">Para obter mais informações sobre o Get-DataEncryptionPolicy cmdlet, consulte [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).</span><span class="sxs-lookup"><span data-stu-id="c9f34-198">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="c9f34-199">Atribuir um DEP antes de migrar uma caixa de correio para a nuvem</span><span class="sxs-lookup"><span data-stu-id="c9f34-199">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="c9f34-200">Quando você atribui o DEP, Microsoft 365 criptografa o conteúdo da caixa de correio usando o DEP atribuído durante a migração.</span><span class="sxs-lookup"><span data-stu-id="c9f34-200">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="c9f34-201">Esse processo é mais eficiente do que migrar a caixa de correio, atribuir o DEP e esperar que a criptografia seja realizada, o que pode levar horas ou possivelmente dias.</span><span class="sxs-lookup"><span data-stu-id="c9f34-201">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="c9f34-202">Para atribuir um DEP a uma caixa de correio antes de migrar para Office 365, execute o cmdlet Set-MailUser no Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c9f34-202">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="c9f34-203">Usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização, [conecte-se Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c9f34-203">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="c9f34-204">Execute o cmdlet Set-MailUser.</span><span class="sxs-lookup"><span data-stu-id="c9f34-204">Run the Set-MailUser cmdlet.</span></span>

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   <span data-ttu-id="c9f34-205">Onde *GeneralMailboxOrMailUserIdParameter* especifica uma caixa de correio, e *DataEncryptionPolicyIdParameter* é a ID do DEP.</span><span class="sxs-lookup"><span data-stu-id="c9f34-205">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="c9f34-206">Para obter mais informações sobre o Set-MailUser cmdlet, consulte [Set-MailUser](/powershell/module/exchange/set-mailuser).</span><span class="sxs-lookup"><span data-stu-id="c9f34-206">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="c9f34-207">Determinar o DEP atribuído a uma caixa de correio</span><span class="sxs-lookup"><span data-stu-id="c9f34-207">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="c9f34-208">Para determinar o DEP atribuído a uma caixa de correio, use Get-MailboxStatistics cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c9f34-208">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="c9f34-209">O cmdlet retorna um identificador exclusivo (GUID).</span><span class="sxs-lookup"><span data-stu-id="c9f34-209">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="c9f34-210">Usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização, [conecte-se Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c9f34-210">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="c9f34-211">Onde *GeneralMailboxOrMailUserIdParameter* especifica uma caixa de correio e DataEncryptionPolicyID retorna o GUID do DEP.</span><span class="sxs-lookup"><span data-stu-id="c9f34-211">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="c9f34-212">Para obter mais informações sobre o Get-MailboxStatistics cmdlet, consulte [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).</span><span class="sxs-lookup"><span data-stu-id="c9f34-212">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).</span></span>
  
2. <span data-ttu-id="c9f34-213">Execute o Get-DataEncryptionPolicy cmdlet para descobrir o nome amigável do DEP ao qual a caixa de correio é atribuída.</span><span class="sxs-lookup"><span data-stu-id="c9f34-213">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="c9f34-214">Onde *GUID* é o GUID retornado pelo cmdlet Get-MailboxStatistics na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="c9f34-214">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="c9f34-215">Verificar se a Chave do Cliente terminou a criptografia</span><span class="sxs-lookup"><span data-stu-id="c9f34-215">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="c9f34-216">Se você tenha rolado uma Chave do Cliente, atribuído um novo DEP ou migrado uma caixa de correio, use as etapas nesta seção para garantir que a criptografia seja concluída.</span><span class="sxs-lookup"><span data-stu-id="c9f34-216">Whether you've rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-mailboxes"></a><span data-ttu-id="c9f34-217">Verificar se a criptografia é concluída para Exchange Online caixas de correio</span><span class="sxs-lookup"><span data-stu-id="c9f34-217">Verify encryption completes for Exchange Online mailboxes</span></span>

<span data-ttu-id="c9f34-218">Criptografar uma caixa de correio pode levar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="c9f34-218">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="c9f34-219">Pela primeira vez, a caixa de correio também deve mudar completamente de um banco de dados para outro para que o serviço possa criptografar a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="c9f34-219">For first time encryption, the mailbox must also completely move from one database to another before the service can encrypt the mailbox.</span></span>
  
<span data-ttu-id="c9f34-220">Use o cmdlet Get-MailboxStatistics para determinar se uma caixa de correio está criptografada.</span><span class="sxs-lookup"><span data-stu-id="c9f34-220">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="c9f34-221">A propriedade IsEncrypted retorna  um valor true se a caixa de correio for criptografada e um valor de **false** se a caixa de correio não estiver criptografada.</span><span class="sxs-lookup"><span data-stu-id="c9f34-221">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox isn't encrypted.</span></span> <span data-ttu-id="c9f34-222">O tempo para concluir as movimentações de caixa de correio depende do número de caixas de correio às quais você atribui um DEP pela primeira vez e do tamanho das caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="c9f34-222">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, and the size of the mailboxes.</span></span> <span data-ttu-id="c9f34-223">Se as caixas de correio não foram criptografadas após uma semana a partir do momento em que você atribuiu o DEP, contate a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9f34-223">If the mailboxes haven't been encrypted after a week from the time you assigned the DEP, contact Microsoft.</span></span>

<span data-ttu-id="c9f34-224">O New-MoveRequest cmdlet não está mais disponível para movimentações de caixa de correio local.</span><span class="sxs-lookup"><span data-stu-id="c9f34-224">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="c9f34-225">Consulte este [comunicado para](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) obter informações adicionais.</span><span class="sxs-lookup"><span data-stu-id="c9f34-225">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="c9f34-226">Verificar se a criptografia é concluída SharePoint arquivos online, OneDrive for Business e Teams online</span><span class="sxs-lookup"><span data-stu-id="c9f34-226">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="c9f34-227">Verifique o status da criptografia executando o cmdlet Get-SPODataEncryptionPolicy da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="c9f34-227">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```PowerShell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="c9f34-228">A saída deste cmdlet inclui:</span><span class="sxs-lookup"><span data-stu-id="c9f34-228">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="c9f34-229">O URI da chave primária.</span><span class="sxs-lookup"><span data-stu-id="c9f34-229">The URI of the primary key.</span></span>

- <span data-ttu-id="c9f34-230">O URI da chave secundária.</span><span class="sxs-lookup"><span data-stu-id="c9f34-230">The URI of the secondary key.</span></span>

- <span data-ttu-id="c9f34-231">O status de criptografia do geo.</span><span class="sxs-lookup"><span data-stu-id="c9f34-231">The encryption status for the geo.</span></span> <span data-ttu-id="c9f34-232">Os estados possíveis incluem:</span><span class="sxs-lookup"><span data-stu-id="c9f34-232">Possible states include:</span></span>

  - <span data-ttu-id="c9f34-233">**Não-registro:** A criptografia chave do cliente ainda não foi aplicada.</span><span class="sxs-lookup"><span data-stu-id="c9f34-233">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="c9f34-234">**Registrando:** A criptografia chave do cliente foi aplicada e seus arquivos estão sendo criptografados.</span><span class="sxs-lookup"><span data-stu-id="c9f34-234">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="c9f34-235">Se a chave do geo estiver registrando, você também será mostrado informações sobre qual porcentagem de sites no geo está concluída para que você possa monitorar o progresso da criptografia.</span><span class="sxs-lookup"><span data-stu-id="c9f34-235">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="c9f34-236">**Registrado:** A criptografia chave do cliente foi aplicada e todos os arquivos em todos os sites foram criptografados.</span><span class="sxs-lookup"><span data-stu-id="c9f34-236">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="c9f34-237">**Rolling:** Um rol de teclas está em andamento.</span><span class="sxs-lookup"><span data-stu-id="c9f34-237">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="c9f34-238">Se a chave do geo estiver rolando, você também será mostrado informações sobre qual porcentagem de sites concluiu a operação de rolagem de chaves para que você possa monitorar o progresso.</span><span class="sxs-lookup"><span data-stu-id="c9f34-238">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="get-details-about-deps-you-use-with-multiple-workloads"></a><span data-ttu-id="c9f34-239">Obter detalhes sobre DEPs que você usa com várias cargas de trabalho</span><span class="sxs-lookup"><span data-stu-id="c9f34-239">Get details about DEPs you use with multiple workloads</span></span>

<span data-ttu-id="c9f34-240">Para obter detalhes sobre todos os DEPs que você criou para usar com várias cargas de trabalho, conclua estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c9f34-240">To get details about all of the DEPs you've created to use with multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="c9f34-241">Em seu computador local, usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador ou administrador de conformidade em sua organização, conecte-se ao [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) em uma janela Windows PowerShell de conformidade.</span><span class="sxs-lookup"><span data-stu-id="c9f34-241">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

   - <span data-ttu-id="c9f34-242">Para retornar a lista de todos os DEPs de várias cargas de trabalho na organização, execute este comando.</span><span class="sxs-lookup"><span data-stu-id="c9f34-242">To return the list of all multi-workload DEPs in the organization, run this command.</span></span>

     ```powershell
        Get-M365DataAtRestEncryptionPolicy
     ```

   - <span data-ttu-id="c9f34-243">Para retornar detalhes sobre um DEP específico, execute este comando.</span><span class="sxs-lookup"><span data-stu-id="c9f34-243">To return details about a specific DEP, run this command.</span></span> <span data-ttu-id="c9f34-244">Este exemplo retorna informações detalhadas para a DEP chamada "Contoso_Global".</span><span class="sxs-lookup"><span data-stu-id="c9f34-244">This example returns detailed information for the DEP named "Contoso_Global".</span></span>

     ```powershell
        Get-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global"
     ```

## <a name="get-multi-workload-dep-assignment-information"></a><span data-ttu-id="c9f34-245">Obter informações de atribuição de DEP de várias cargas de trabalho</span><span class="sxs-lookup"><span data-stu-id="c9f34-245">Get multi-workload DEP assignment information</span></span>

<span data-ttu-id="c9f34-246">Para descobrir qual DEP está atualmente atribuído ao seu locatário, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c9f34-246">To find out which DEP is currently assigned to your tenant, follow these steps.</span></span> 

1. <span data-ttu-id="c9f34-247">Em seu computador local, usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador ou administrador de conformidade em sua organização, conecte-se ao [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) em uma janela Windows PowerShell de conformidade.</span><span class="sxs-lookup"><span data-stu-id="c9f34-247">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="c9f34-248">Digite este comando.</span><span class="sxs-lookup"><span data-stu-id="c9f34-248">Type this command.</span></span>

   ```powershell
      Get-M365DataAtRestEncryptionPolicyAssignment
   ```

## <a name="disable-a-multi-workload-dep"></a><span data-ttu-id="c9f34-249">Desabilitar uma DEP de várias cargas de trabalho</span><span class="sxs-lookup"><span data-stu-id="c9f34-249">Disable a multi-workload DEP</span></span>

<span data-ttu-id="c9f34-250">Antes de desabilitar uma DEP de várias cargas de trabalho, desaprompa o DEP de cargas de trabalho em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="c9f34-250">Before you disable a multi-workload DEP, unassign the DEP from workloads in your tenant.</span></span> <span data-ttu-id="c9f34-251">Para desabilitar um DEP usado com várias cargas de trabalho, conclua estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c9f34-251">To disable a DEP used with multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="c9f34-252">Em seu computador local, usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador ou administrador de conformidade em sua organização, conecte-se ao [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) em uma janela Windows PowerShell de conformidade.</span><span class="sxs-lookup"><span data-stu-id="c9f34-252">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="c9f34-253">Execute o cmdlet Set-M365DataAtRestEncryptionPolicy.</span><span class="sxs-lookup"><span data-stu-id="c9f34-253">Run the Set-M365DataAtRestEncryptionPolicy cmdlet.</span></span>
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Enabled $false
   ```

<span data-ttu-id="c9f34-254">Onde *PolicyName* é o nome ou ID exclusiva da política.</span><span class="sxs-lookup"><span data-stu-id="c9f34-254">Where *PolicyName* is the name or unique ID of the policy.</span></span> <span data-ttu-id="c9f34-255">Por exemplo, Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="c9f34-255">For example, Contoso_Global.</span></span>

<span data-ttu-id="c9f34-256">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="c9f34-256">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Enabled $false
```

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="c9f34-257">Restaurar chaves do Cofre de Chaves do Azure</span><span class="sxs-lookup"><span data-stu-id="c9f34-257">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="c9f34-258">Antes de executar uma restauração, use os recursos de recuperação fornecidos pela exclusão suave.</span><span class="sxs-lookup"><span data-stu-id="c9f34-258">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="c9f34-259">Todas as chaves usadas com a Chave do Cliente são necessárias para habilitar a exclusão suave.</span><span class="sxs-lookup"><span data-stu-id="c9f34-259">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="c9f34-260">A exclusão suave age como uma lixeira e permite a recuperação por até 90 dias sem a necessidade de restauração.</span><span class="sxs-lookup"><span data-stu-id="c9f34-260">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="c9f34-261">A restauração só deve ser necessária em circunstâncias extremas ou incomuns, por exemplo, se a chave ou o cofre de chaves for perdido.</span><span class="sxs-lookup"><span data-stu-id="c9f34-261">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="c9f34-262">Se você deve restaurar uma chave para uso com a Chave do Cliente, em Azure PowerShell, execute o cmdlet Restore-AzureKeyVaultKey da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="c9f34-262">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="c9f34-263">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c9f34-263">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="c9f34-264">Se o cofre de chaves já contiver uma chave com o mesmo nome, a operação de restauração falhará.</span><span class="sxs-lookup"><span data-stu-id="c9f34-264">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="c9f34-265">Restore-AzKeyVaultKey restaura todas as versões principais e todos os metadados da chave, incluindo o nome da chave.</span><span class="sxs-lookup"><span data-stu-id="c9f34-265">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="c9f34-266">Gerenciar permissões de cofre de chaves</span><span class="sxs-lookup"><span data-stu-id="c9f34-266">Manage key vault permissions</span></span>

<span data-ttu-id="c9f34-267">Vários cmdlets estão disponíveis que permitem que você veja e, se necessário, remova as permissões do cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="c9f34-267">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="c9f34-268">Talvez seja necessário remover permissões, por exemplo, quando um funcionário sair da equipe.</span><span class="sxs-lookup"><span data-stu-id="c9f34-268">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="c9f34-269">Para cada uma dessas tarefas, você usará Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9f34-269">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="c9f34-270">Para obter informações sobre Azure PowerShell, consulte [Overview of Azure PowerShell](/powershell/azure/).</span><span class="sxs-lookup"><span data-stu-id="c9f34-270">For information about Azure PowerShell, see [Overview of Azure PowerShell](/powershell/azure/).</span></span>

<span data-ttu-id="c9f34-271">Para exibir permissões de cofre de chaves, execute o cmdlet Get-AzKeyVault chave.</span><span class="sxs-lookup"><span data-stu-id="c9f34-271">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="c9f34-272">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c9f34-272">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="c9f34-273">Para remover as permissões de um administrador, execute o cmdlet Remove-AzKeyVaultAccessPolicy:</span><span class="sxs-lookup"><span data-stu-id="c9f34-273">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="c9f34-274">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c9f34-274">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a><span data-ttu-id="c9f34-275">Reverter da Chave do Cliente para chaves gerenciadas da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c9f34-275">Roll back from Customer Key to Microsoft managed Keys</span></span>

<span data-ttu-id="c9f34-276">Se precisar reverter para chaves gerenciadas pela Microsoft, você pode.</span><span class="sxs-lookup"><span data-stu-id="c9f34-276">If you need to revert to Microsoft-managed keys, you can.</span></span> <span data-ttu-id="c9f34-277">Quando você sai do barco, seus dados são recriptados usando a criptografia padrão suportada por cada carga de trabalho individual.</span><span class="sxs-lookup"><span data-stu-id="c9f34-277">When you offboard, your data is re-encrypted using default encryption supported by each individual workload.</span></span> <span data-ttu-id="c9f34-278">Por exemplo, Exchange Online dá suporte à criptografia padrão usando chaves gerenciadas pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9f34-278">For example, Exchange Online supports default encryption using Microsoft-managed keys.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9f34-279">O offboard não é o mesmo que uma limpeza de dados.</span><span class="sxs-lookup"><span data-stu-id="c9f34-279">Offboarding is not the same as a data purge.</span></span> <span data-ttu-id="c9f34-280">Uma limpeza de dados exclui permanentemente os dados da sua organização Microsoft 365, o offboard não.</span><span class="sxs-lookup"><span data-stu-id="c9f34-280">A data purge permanently crypto-deletes your organization's data from Microsoft 365, offboarding does not.</span></span> <span data-ttu-id="c9f34-281">Você não pode executar uma limpeza de dados para uma política de carga de trabalho múltipla.</span><span class="sxs-lookup"><span data-stu-id="c9f34-281">You can't perform a data purge for a multiple workload policy.</span></span>

<span data-ttu-id="c9f34-282">Se você decidir não usar Mais a Chave do Cliente para atribuir DEPs de várias cargas de trabalho, você precisará falar com o suporte da Microsoft com uma solicitação para "offboard" da Chave do Cliente.</span><span class="sxs-lookup"><span data-stu-id="c9f34-282">If you decide not to use Customer Key for assigning multi-workload DEPs anymore then you'll need to reach out to Microsoft support with a request to “offboard” from Customer Key.</span></span> <span data-ttu-id="c9f34-283">Peça à equipe de suporte para arquivar uma solicitação de serviço Microsoft 365 equipe de Chave do Cliente.</span><span class="sxs-lookup"><span data-stu-id="c9f34-283">Ask the support team to file a service request against Microsoft 365 Customer Key team.</span></span> <span data-ttu-id="c9f34-284">Entre em contato m365-ck@service.microsoft.com se você tiver alguma dúvida.</span><span class="sxs-lookup"><span data-stu-id="c9f34-284">Reach out to m365-ck@service.microsoft.com if you have any questions.</span></span>

<span data-ttu-id="c9f34-285">Se você não quiser mais criptografar caixas de correio individuais usando DEPs de nível de caixa de correio, poderá desasinhar DEPs de nível de caixa de correio de todas as suas caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="c9f34-285">If you do not want to encrypt individual mailboxes using mailbox level DEPs anymore, then you can unassign mailbox level DEPs from all your mailboxes.</span></span>

<span data-ttu-id="c9f34-286">Para desausinar DEPs de caixa de correio, use o cmdlet Set-Mailbox PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9f34-286">To unassign mailbox DEPs, use the Set-Mailbox PowerShell cmdlet.</span></span>

1. <span data-ttu-id="c9f34-287">Usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização, [conecte-se Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c9f34-287">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="c9f34-288">Execute o cmdlet Set-Mailbox.</span><span class="sxs-lookup"><span data-stu-id="c9f34-288">Run the Set-Mailbox cmdlet.</span></span>

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

<span data-ttu-id="c9f34-289">Executar este cmdlet desassocia o DEP atribuído no momento e reenscriptografa a caixa de correio usando o DEP associado às chaves gerenciadas pela Microsoft padrão.</span><span class="sxs-lookup"><span data-stu-id="c9f34-289">Running this cmdlet unassigns the currently assigned DEP and reencrypts the mailbox using the DEP associated with default Microsoft-managed keys.</span></span> <span data-ttu-id="c9f34-290">Não é possível desa desasinalhar o DEP usado pelas chaves gerenciadas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9f34-290">You can't unassign the DEP used by Microsoft managed keys.</span></span> <span data-ttu-id="c9f34-291">Se você não quiser usar chaves gerenciadas pela Microsoft, poderá atribuir outro DEP de Chave de Cliente à caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="c9f34-291">If you don't want to use Microsoft-managed keys, you can assign another Customer Key DEP to the mailbox.</span></span>

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="c9f34-292">Revogar suas chaves e iniciar o processo de caminho de limpeza de dados</span><span class="sxs-lookup"><span data-stu-id="c9f34-292">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="c9f34-293">Você controla a revogação de todas as chaves raiz, incluindo a chave de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="c9f34-293">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="c9f34-294">A Chave do Cliente fornece controle do aspecto de planejamento de saída dos requisitos regulatórios para você.</span><span class="sxs-lookup"><span data-stu-id="c9f34-294">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="c9f34-295">Se você decidir revogar suas chaves para limpar seus dados e sair do serviço, o serviço excluirá a chave de disponibilidade depois que o processo de limpeza de dados for concluído.</span><span class="sxs-lookup"><span data-stu-id="c9f34-295">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span> <span data-ttu-id="c9f34-296">Isso é suportado para DEPs de Chave de Cliente que são atribuídos a caixas de correio individuais.</span><span class="sxs-lookup"><span data-stu-id="c9f34-296">This is supported for Customer Key DEPs that are assigned to individual mailboxes.</span></span>

<span data-ttu-id="c9f34-297">Microsoft 365 audita e valida o caminho de limpeza de dados.</span><span class="sxs-lookup"><span data-stu-id="c9f34-297">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="c9f34-298">Para obter mais informações, consulte o Relatório soc 2 do SSAE 18 disponível no [Portal de Confiança do Serviço.](https://servicetrust.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="c9f34-298">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="c9f34-299">Além disso, a Microsoft recomenda os seguintes documentos:</span><span class="sxs-lookup"><span data-stu-id="c9f34-299">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="c9f34-300">Guia de Avaliação e Conformidade de Riscos para Instituições Financeiras no Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="c9f34-300">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="c9f34-301">Considerações sobre o planejamento de saída do O365</span><span class="sxs-lookup"><span data-stu-id="c9f34-301">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="c9f34-302">Não há suporte para a depuração de DEP de várias cargas de trabalho Microsoft 365 Customer Key.</span><span class="sxs-lookup"><span data-stu-id="c9f34-302">Purging of multi-workload DEP is not supported for Microsoft 365 Customer Key.</span></span> <span data-ttu-id="c9f34-303">A DEP de várias cargas de trabalho é usada para criptografar dados em várias cargas de trabalho em todos os usuários de locatários.</span><span class="sxs-lookup"><span data-stu-id="c9f34-303">The multi-workload DEP is used to encrypt data across multiple workloads across all tenant users.</span></span> <span data-ttu-id="c9f34-304">A purgação desse DEP resultaria em dados de várias cargas de trabalho inacessíveis.</span><span class="sxs-lookup"><span data-stu-id="c9f34-304">Purging such DEP would result into data from across multiple workloads become inaccessible.</span></span> <span data-ttu-id="c9f34-305">Se você decidir sair completamente Microsoft 365 serviços, poderá seguir o caminho da exclusão de locatários por meio do processo documentado.</span><span class="sxs-lookup"><span data-stu-id="c9f34-305">If you decide to exit Microsoft 365 services altogether then you could pursue the path of tenant deletion per the documented process.</span></span> <span data-ttu-id="c9f34-306">Veja [como excluir um locatário no Azure Active Directoy](/azure/active-directory/enterprise-users/directory-delete-howto).</span><span class="sxs-lookup"><span data-stu-id="c9f34-306">See [how to delete a tenant in Azure Active Directoy](/azure/active-directory/enterprise-users/directory-delete-howto).</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="c9f34-307">Revogar suas Chaves de Cliente e a chave de disponibilidade para Exchange Online e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c9f34-307">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="c9f34-308">Ao iniciar o caminho de limpeza de dados para Exchange Online e Skype for Business, você definirá uma solicitação permanente de limpeza de dados em um DEP.</span><span class="sxs-lookup"><span data-stu-id="c9f34-308">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="c9f34-309">Isso exclui permanentemente os dados criptografados nas caixas de correio às quais esse DEP é atribuído.</span><span class="sxs-lookup"><span data-stu-id="c9f34-309">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="c9f34-310">Como você só pode executar o cmdlet do PowerShell em um DEP por vez, considere reatribuir um único DEP para todas as suas caixas de correio antes de iniciar o caminho de limpeza de dados.</span><span class="sxs-lookup"><span data-stu-id="c9f34-310">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="c9f34-311">Não use o caminho de limpeza de dados para excluir um subconjunto de suas caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="c9f34-311">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="c9f34-312">Esse processo destina-se apenas aos clientes que estão saindo do serviço.</span><span class="sxs-lookup"><span data-stu-id="c9f34-312">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="c9f34-313">Para iniciar o caminho de limpeza de dados, conclua estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c9f34-313">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="c9f34-314">Remova permissões de quebra e desembrulhamento para "O365 Exchange Online" dos Cofres de Chaves do Azure.</span><span class="sxs-lookup"><span data-stu-id="c9f34-314">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="c9f34-315">Usando uma conta de estudante ou de trabalho que tenha privilégios globais de administrador em sua organização, [conecte-se ao Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c9f34-315">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

3. <span data-ttu-id="c9f34-316">Para cada DEP que contém caixas de correio que você deseja excluir, execute o cmdlet [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="c9f34-316">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="c9f34-317">Se o comando falhar, verifique se você removeu as permissões Exchange Online de ambas as chaves no Azure Key Vault conforme especificado anteriormente nesta tarefa.</span><span class="sxs-lookup"><span data-stu-id="c9f34-317">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="c9f34-318">Depois de definir a opção PermanentDataPurgeRequested usando o cmdlet Set-DataEncryptionPolicy, você não poderá mais atribuir esse DEP às caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="c9f34-318"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="c9f34-319">Entre em contato com o suporte da Microsoft e solicite o eDocument de Limpeza de Dados.</span><span class="sxs-lookup"><span data-stu-id="c9f34-319">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="c9f34-320">Em sua solicitação, a Microsoft envia um documento legal para confirmar e autorizar a exclusão de dados.</span><span class="sxs-lookup"><span data-stu-id="c9f34-320">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="c9f34-321">A pessoa em sua organização que se inscreveu como aprovador na oferta do FastTrack durante a integração precisa assinar este documento.</span><span class="sxs-lookup"><span data-stu-id="c9f34-321">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="c9f34-322">Normalmente, esse é um executivo ou outra pessoa designada em sua empresa que está legalmente autorizado a assinar a documentação em nome da sua organização.</span><span class="sxs-lookup"><span data-stu-id="c9f34-322">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="c9f34-323">Depois que seu representante tiver assinado o documento legal, retorne-o à Microsoft (geralmente por meio de uma assinatura do eDoc).</span><span class="sxs-lookup"><span data-stu-id="c9f34-323">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="c9f34-324">Depois que a Microsoft recebe o documento legal, a Microsoft executa cmdlets para disparar a limpeza de dados que primeiro exclui a política, marca as caixas de correio para exclusão permanente e exclui a chave de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="c9f34-324">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="c9f34-325">Depois que o processo de limpeza de dados for concluído, os dados serão limpos, estarão inacessíveis Exchange Online e não serão recuperáveis.</span><span class="sxs-lookup"><span data-stu-id="c9f34-325">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="c9f34-326">Revogar suas Chaves de Cliente e a chave de disponibilidade para arquivos SharePoint Online, OneDrive for Business e Teams Online</span><span class="sxs-lookup"><span data-stu-id="c9f34-326">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="c9f34-327">Para iniciar o caminho de limpeza de dados para arquivos SharePoint Online, OneDrive for Business e Teams, conclua estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c9f34-327">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="c9f34-328">Revogar o acesso ao Cofre de Chaves do Azure.</span><span class="sxs-lookup"><span data-stu-id="c9f34-328">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="c9f34-329">Todos os administradores do cofre de chaves devem concordar em revogar o acesso.</span><span class="sxs-lookup"><span data-stu-id="c9f34-329">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="c9f34-330">Você não exclui o Azure Key Vault para SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c9f34-330">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="c9f34-331">Os cofres chave podem ser compartilhados entre vários locatários SharePoint Online e DEPs.</span><span class="sxs-lookup"><span data-stu-id="c9f34-331">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="c9f34-332">Contate a Microsoft para excluir a chave de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="c9f34-332">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="c9f34-333">Quando você entrar em contato com a Microsoft para excluir a chave de disponibilidade, enviaremos um documento legal.</span><span class="sxs-lookup"><span data-stu-id="c9f34-333">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="c9f34-334">A pessoa em sua organização que se inscreveu como aprovador na oferta do FastTrack durante a integração precisa assinar este documento.</span><span class="sxs-lookup"><span data-stu-id="c9f34-334">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="c9f34-335">Normalmente, esse é um executivo ou outra pessoa designada em sua empresa que está legalmente autorizado a assinar a documentação em nome da sua organização.</span><span class="sxs-lookup"><span data-stu-id="c9f34-335">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="c9f34-336">Depois que o representante assinar o documento legal, retorne-o à Microsoft (geralmente por meio de uma assinatura do eDoc).</span><span class="sxs-lookup"><span data-stu-id="c9f34-336">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="c9f34-337">Depois que a Microsoft recebe o documento legal, executamos cmdlets para disparar a limpeza de dados que executa a exclusão criptografada da chave de locatário, da chave do site e de todas as chaves individuais por documento, quebrando irrevogavelmente a hierarquia de chaves.</span><span class="sxs-lookup"><span data-stu-id="c9f34-337">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="c9f34-338">Depois que os cmdlets de limpeza de dados são concluídos, seus dados são limpos.</span><span class="sxs-lookup"><span data-stu-id="c9f34-338">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="c9f34-339">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="c9f34-339">Related articles</span></span>

- [<span data-ttu-id="c9f34-340">Criptografia do serviço com a Chave de Cliente</span><span class="sxs-lookup"><span data-stu-id="c9f34-340">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="c9f34-341">Saiba mais sobre a chave de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="c9f34-341">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="c9f34-342">Configurar a Chave do Cliente</span><span class="sxs-lookup"><span data-stu-id="c9f34-342">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="c9f34-343">Rolar ou girar uma Chave de Cliente ou uma chave de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="c9f34-343">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="c9f34-344">Sistema de Proteção de Dados do Cliente</span><span class="sxs-lookup"><span data-stu-id="c9f34-344">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="c9f34-345">Criptografia de Serviço</span><span class="sxs-lookup"><span data-stu-id="c9f34-345">Service Encryption</span></span>](office-365-service-encryption.md)