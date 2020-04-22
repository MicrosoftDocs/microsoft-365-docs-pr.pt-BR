---
title: Gerenciar chave do cliente
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Depois de configurar a chave do cliente, saiba como gerenciá-la restaurando as chaves do AKV e gerenciando as permissões e as políticas de criptografia de dados.
ms.openlocfilehash: 4796fcef69e052725b635acb4170d73bb36de787
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635597"
---
# <a name="manage-customer-key"></a><span data-ttu-id="2df93-103">Gerenciar chave do cliente</span><span class="sxs-lookup"><span data-stu-id="2df93-103">Manage Customer Key</span></span>

<span data-ttu-id="2df93-104">Depois de configurar a chave do cliente para o Office 365, você pode gerenciar suas chaves, conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="2df93-104">After you've set up Customer Key for Office 365, you can manage your keys as described in this article.</span></span> <span data-ttu-id="2df93-105">Saiba mais sobre a chave do cliente nos tópicos relacionados.</span><span class="sxs-lookup"><span data-stu-id="2df93-105">Learn more about Customer Key in the related topics.</span></span>

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="2df93-106">Restaurar chaves do Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="2df93-106">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="2df93-107">Antes de executar uma restauração, use os recursos de recuperação fornecidos pela exclusão reversível.</span><span class="sxs-lookup"><span data-stu-id="2df93-107">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="2df93-108">Todas as chaves usadas com a chave do cliente são necessárias para que a exclusão reversível seja habilitada.</span><span class="sxs-lookup"><span data-stu-id="2df93-108">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="2df93-109">A exclusão reversível funciona como uma lixeira e permite a recuperação de até 90 dias sem a necessidade de restauração.</span><span class="sxs-lookup"><span data-stu-id="2df93-109">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="2df93-110">A restauração deve ser necessária somente em circunstâncias extremas ou incomuns, por exemplo, se a chave ou o cofre de chaves for perdido.</span><span class="sxs-lookup"><span data-stu-id="2df93-110">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="2df93-111">Se for necessário restaurar uma chave para uso com a chave do cliente, no PowerShell do Azure, execute o cmdlet Restore-AzureKeyVaultKey da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="2df93-111">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="2df93-112">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2df93-112">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="2df93-113">Se o cofre de chaves já contiver uma chave com o mesmo nome, a operação de restauração falhará.</span><span class="sxs-lookup"><span data-stu-id="2df93-113">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="2df93-114">Restore-AzKeyVaultKey restaura todas as versões de chave e todos os metadados da chave, incluindo o nome da chave.</span><span class="sxs-lookup"><span data-stu-id="2df93-114">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="2df93-115">Gerenciar permissões do Key Vault</span><span class="sxs-lookup"><span data-stu-id="2df93-115">Manage key vault permissions</span></span>

<span data-ttu-id="2df93-116">Há vários cmdlets disponíveis que permitem que você visualize e, se necessário, remova as permissões do Key Vault.</span><span class="sxs-lookup"><span data-stu-id="2df93-116">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="2df93-117">Talvez seja necessário remover permissões, por exemplo, quando um funcionário sair da equipe.</span><span class="sxs-lookup"><span data-stu-id="2df93-117">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="2df93-118">Para cada uma dessas tarefas, você usará o Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2df93-118">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="2df93-119">Para obter informações sobre o Azure PowerShell, consulte [visão geral do Azure PowerShell](https://docs.microsoft.com/powershell/azure/).</span><span class="sxs-lookup"><span data-stu-id="2df93-119">For information about Azure Powershell, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/).</span></span>

<span data-ttu-id="2df93-120">Para exibir as permissões do compartimento de chaves, execute o cmdlet Get-AzKeyVault.</span><span class="sxs-lookup"><span data-stu-id="2df93-120">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="2df93-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2df93-121">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="2df93-122">Para remover as permissões de um administrador, execute o cmdlet Remove-AzKeyVaultAccessPolicy:</span><span class="sxs-lookup"><span data-stu-id="2df93-122">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="2df93-123">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2df93-123">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a><span data-ttu-id="2df93-124">Gerenciar políticas de criptografia de dados (DEPs) com a chave do cliente</span><span class="sxs-lookup"><span data-stu-id="2df93-124">Manage data encryption policies (DEPs) with Customer Key</span></span>

<span data-ttu-id="2df93-125">As alças de chave do cliente DEPs de forma diferente entre os diferentes serviços.</span><span class="sxs-lookup"><span data-stu-id="2df93-125">Customer Key handles DEPs differently between the different services.</span></span> <span data-ttu-id="2df93-126">Por exemplo, você pode criar um número diferente de DEPs para os diferentes serviços.</span><span class="sxs-lookup"><span data-stu-id="2df93-126">For example, you can create a different number of DEPs for the different services.</span></span>

<span data-ttu-id="2df93-127">**Exchange Online e Skype for Business:** Você pode criar até 50 DEPs.</span><span class="sxs-lookup"><span data-stu-id="2df93-127">**Exchange Online and Skype for Business:** You can create up to 50 DEPs.</span></span> <span data-ttu-id="2df93-128">Para obter instruções, consulte [criar uma política de criptografia de dados (DEP) para uso com o Exchange Online e o Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span><span class="sxs-lookup"><span data-stu-id="2df93-128">For instructions, see [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span></span>

<span data-ttu-id="2df93-129">**SharePoint Online, onedrive for Business e arquivos do teams:** Uma DEP aplica-se aos dados em um local geográfico, também chamado de uma _geografia_.</span><span class="sxs-lookup"><span data-stu-id="2df93-129">**SharePoint Online, OneDrive for Business, and Teams files:** A DEP applies to data in one geographic location, also called a _geo_.</span></span> <span data-ttu-id="2df93-130">Se você usar o recurso multigeográfico do Office 365, poderá criar uma DEP por Geo.</span><span class="sxs-lookup"><span data-stu-id="2df93-130">If you use the multi-geo feature of Office 365, you can create one DEP per geo.</span></span> <span data-ttu-id="2df93-131">Se você não estiver usando o multigeográfico, você pode criar um DEP.</span><span class="sxs-lookup"><span data-stu-id="2df93-131">If you are not using multi-geo, you can create one DEP.</span></span> <span data-ttu-id="2df93-132">Normalmente, você cria a DEP ao configurar a chave do cliente.</span><span class="sxs-lookup"><span data-stu-id="2df93-132">Normally, you create the DEP when you set up Customer Key.</span></span> <span data-ttu-id="2df93-133">Para obter instruções, consulte [criar uma DEP (política de criptografia de dados) para cada Geografia do SharePoint Online e do onedrive for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span><span class="sxs-lookup"><span data-stu-id="2df93-133">For instructions, see [Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="2df93-134">Exibir o DEPs que você criou para o Exchange Online e o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2df93-134">View the DEPs you've created for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="2df93-135">Para exibir uma lista de todos os DEPs que você criou para o Exchange Online e o Skype for Business usando o cmdlet Get-DataEncryptionPolicy do PowerShell, conclua estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2df93-135">To view a list of all the DEPs you've created for Exchange Online and Skype for Business using the Get-DataEncryptionPolicy PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="2df93-136">Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização, [Conecte-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="2df93-136">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="2df93-137">Para retornar todos os DEPs em sua organização, execute o cmdlet Get-DataEncryptionPolicy sem nenhum parâmetro.</span><span class="sxs-lookup"><span data-stu-id="2df93-137">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

  ```powershell
  Get-DataEncryptionPolicy
  ```

  <span data-ttu-id="2df93-138">Para obter mais informações sobre o cmdlet Get-DataEncryptionPolicy, consulte [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-dataencryptionpolicy?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="2df93-138">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-dataencryptionpolicy?view=exchange-ps).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="2df93-139">Atribuir uma DEP antes de migrar uma caixa de correio para a nuvem</span><span class="sxs-lookup"><span data-stu-id="2df93-139">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="2df93-140">Quando você atribui a DEP, a Microsoft 365 criptografa o conteúdo da caixa de correio usando a DEP atribuída durante a migração.</span><span class="sxs-lookup"><span data-stu-id="2df93-140">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="2df93-141">Esse processo é mais eficiente do que migrar a caixa de correio, atribuindo a DEP e, em seguida, aguardando a criptografia ocorrer, o que pode levar horas ou possivelmente dias.</span><span class="sxs-lookup"><span data-stu-id="2df93-141">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="2df93-142">Para atribuir uma DEP a uma caixa de correio antes de migrá-la para o Office 365, execute o cmdlet Set-MailUser no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="2df93-142">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="2df93-143">Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização, [Conecte-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="2df93-143">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="2df93-144">Execute o cmdlet Set-MailUser.</span><span class="sxs-lookup"><span data-stu-id="2df93-144">Run the Set-MailUser cmdlet.</span></span>

  ```powershell
  Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
  ```

  <span data-ttu-id="2df93-145">Onde *GeneralMailboxOrMailUserIdParameter* especifica uma caixa de correio e *DATAENCRYPTIONPOLICYIDPARAMETER* é a ID da DEP.</span><span class="sxs-lookup"><span data-stu-id="2df93-145">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="2df93-146">Para obter mais informações sobre o cmdlet Set-MailUser, consulte [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-mailuser?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="2df93-146">For more information about the Set-MailUser cmdlet, see [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-mailuser?view=exchange-ps).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="2df93-147">Determinar a DEP atribuída a uma caixa de correio</span><span class="sxs-lookup"><span data-stu-id="2df93-147">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="2df93-148">Para determinar a DEP atribuída a uma caixa de correio, use o cmdlet Get-MailboxStatistics.</span><span class="sxs-lookup"><span data-stu-id="2df93-148">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="2df93-149">O cmdlet retorna um identificador exclusivo (GUID).</span><span class="sxs-lookup"><span data-stu-id="2df93-149">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="2df93-150">Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização, [Conecte-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="2df93-150">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="2df93-151">Onde *GeneralMailboxOrMailUserIdParameter* especifica uma caixa de correio e DataEncryptionPolicyID retorna o GUID da DEP.</span><span class="sxs-lookup"><span data-stu-id="2df93-151">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="2df93-152">Para obter mais informações sobre o cmdlet Get-MailboxStatistics, consulte [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/get-mailboxstatistics?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="2df93-152">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/get-mailboxstatistics?view=exchange-ps).</span></span>
  
2. <span data-ttu-id="2df93-153">Execute o cmdlet Get-DataEncryptionPolicy para descobrir o nome amigável da DEP à qual a caixa de correio é atribuída.</span><span class="sxs-lookup"><span data-stu-id="2df93-153">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="2df93-154">Onde *GUID* é o GUID retornado pelo cmdlet Get-MailboxStatistics na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="2df93-154">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="2df93-155">Verificar se a chave do cliente terminou a criptografia</span><span class="sxs-lookup"><span data-stu-id="2df93-155">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="2df93-156">Se você acabou de reverter uma chave de cliente, atribuiu uma nova DEP ou migrou uma caixa de correio, use as etapas desta seção para garantir que a criptografia seja concluída.</span><span class="sxs-lookup"><span data-stu-id="2df93-156">Whether you've just rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="2df93-157">Verificar se a criptografia é concluída para o Exchange Online e o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2df93-157">Verify encryption completes for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="2df93-158">Criptografar uma caixa de correio pode levar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="2df93-158">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="2df93-159">Recomendamos que você aguarde 72 horas antes de tentar validar a criptografia após alterar uma DEP ou a primeira vez em que você atribui uma DEP a uma caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="2df93-159">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="2df93-160">Use o cmdlet Get-MailboxStatistics para determinar se uma caixa de correio está criptografada.</span><span class="sxs-lookup"><span data-stu-id="2df93-160">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="2df93-161">A Propriedade IsEncrypted retornará um valor **true** se a caixa de correio for criptografada e um valor **false** se a caixa de correio não estiver criptografada.</span><span class="sxs-lookup"><span data-stu-id="2df93-161">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="2df93-162">O tempo para concluir movimentações de caixa de correio depende do tamanho da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="2df93-162">The time to complete mailbox moves depends on the size of the mailbox.</span></span> <span data-ttu-id="2df93-163">Se a chave do cliente não tiver criptografado completamente a caixa de correio após 72 horas a partir do momento em que você atribuir uma nova DEP, inicie uma movimentação de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="2df93-163">If Customer Key hasn't completely encrypted the mailbox after 72 hours from the time you assign a new DEP, initiate a mailbox move.</span></span> <span data-ttu-id="2df93-164">Para fazer isso, use o cmdlet New-MoveRequest e forneça o alias da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="2df93-164">To do this, use the New-MoveRequest cmdlet and provide the alias of the mailbox.</span></span> <span data-ttu-id="2df93-165">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2df93-165">For example:</span></span>
  
```powershell
New-MoveRequest <alias>
```

<span data-ttu-id="2df93-166">Para obter mais informações sobre esse cmdlet, consulte [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="2df93-166">For more information about this cmdlet, see [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps).</span></span>

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="2df93-167">Verificar se a criptografia é concluída para os arquivos do SharePoint Online, do OneDrive for Business e do teams</span><span class="sxs-lookup"><span data-stu-id="2df93-167">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="2df93-168">Verifique o status da criptografia executando o cmdlet Get-SPODataEncryptionPolicy da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="2df93-168">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="2df93-169">A saída deste cmdlet inclui:</span><span class="sxs-lookup"><span data-stu-id="2df93-169">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="2df93-170">O URI da chave primária.</span><span class="sxs-lookup"><span data-stu-id="2df93-170">The URI of the primary key.</span></span>

- <span data-ttu-id="2df93-171">O URI da chave secundária.</span><span class="sxs-lookup"><span data-stu-id="2df93-171">The URI of the secondary key.</span></span>

- <span data-ttu-id="2df93-172">O status de criptografia para a geografia.</span><span class="sxs-lookup"><span data-stu-id="2df93-172">The encryption status for the geo.</span></span> <span data-ttu-id="2df93-173">Os Estados possíveis incluem:</span><span class="sxs-lookup"><span data-stu-id="2df93-173">Possible states include:</span></span>

  - <span data-ttu-id="2df93-174">Não **registrado:** A criptografia de chave do cliente ainda não foi aplicada.</span><span class="sxs-lookup"><span data-stu-id="2df93-174">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="2df93-175">**Registro:** A criptografia da chave do cliente foi aplicada e seus arquivos estão em processo de criptografia.</span><span class="sxs-lookup"><span data-stu-id="2df93-175">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="2df93-176">Se a chave da geografia estiver se registrando, você também verá informações sobre qual porcentagem de sites na geografia estão concluídas para que você possa monitorar o andamento da criptografia.</span><span class="sxs-lookup"><span data-stu-id="2df93-176">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="2df93-177">**Registrado:** A criptografia da chave do cliente foi aplicada e todos os arquivos em todos os sites foram criptografados.</span><span class="sxs-lookup"><span data-stu-id="2df93-177">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="2df93-178">**Sem interrupção:** Um rolo de chave está em andamento.</span><span class="sxs-lookup"><span data-stu-id="2df93-178">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="2df93-179">Se a chave da geografia estiver sem interrupção, você também verá informações sobre a porcentagem de sites que concluiram a operação do registro principal para que você possa monitorar o progresso.</span><span class="sxs-lookup"><span data-stu-id="2df93-179">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="2df93-180">Revogar suas chaves e iniciar o processo de caminho de limpeza de dados</span><span class="sxs-lookup"><span data-stu-id="2df93-180">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="2df93-181">Você controla a revogação de todas as chaves raiz, incluindo a chave de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="2df93-181">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="2df93-182">A chave do cliente oferece controle do aspecto de planejamento de saída dos requisitos normativos para você.</span><span class="sxs-lookup"><span data-stu-id="2df93-182">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="2df93-183">Se você decidir revogar suas chaves para limpar seus dados e sair do serviço, o serviço excluirá a chave de disponibilidade após a conclusão do processo de limpeza de dados.</span><span class="sxs-lookup"><span data-stu-id="2df93-183">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span>

<span data-ttu-id="2df93-184">O Microsoft 365 audita e valida o caminho de limpeza dos dados.</span><span class="sxs-lookup"><span data-stu-id="2df93-184">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="2df93-185">Para obter mais informações, consulte o SSAE 18 SOC 2 Report disponível no [portal de confiança do serviço](https://servicetrust.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="2df93-185">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="2df93-186">Além disso, a Microsoft recomenda os seguintes documentos:</span><span class="sxs-lookup"><span data-stu-id="2df93-186">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="2df93-187">Guia de conformidade e avaliação de riscos para instituições financeiras na nuvem da Microsoft</span><span class="sxs-lookup"><span data-stu-id="2df93-187">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="2df93-188">Considerações de planejamento de saída do O365</span><span class="sxs-lookup"><span data-stu-id="2df93-188">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="2df93-189">O caminho de limpeza de dados difere ligeiramente entre os diferentes serviços.</span><span class="sxs-lookup"><span data-stu-id="2df93-189">The data purge path differs slightly between the different services.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="2df93-190">Revogar as chaves do cliente e a chave de disponibilidade para o Exchange Online e o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2df93-190">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="2df93-191">Ao iniciar o caminho de limpeza de dados do Exchange Online e do Skype for Business, você define uma solicitação de limpeza de dados permanente em uma DEP.</span><span class="sxs-lookup"><span data-stu-id="2df93-191">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="2df93-192">Isso exclui permanentemente os dados criptografados nas caixas de correio às quais a DEP é atribuída.</span><span class="sxs-lookup"><span data-stu-id="2df93-192">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="2df93-193">Como você só pode executar o cmdlet do PowerShell em uma DEP por vez, considere reatribuir uma única DEP a todas as suas caixas de correio antes de iniciar o caminho de limpeza dos dados.</span><span class="sxs-lookup"><span data-stu-id="2df93-193">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="2df93-194">Não use o caminho de limpeza de dados para excluir um subconjunto de suas caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="2df93-194">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="2df93-195">Este processo destina-se apenas aos clientes que estão saindo do serviço.</span><span class="sxs-lookup"><span data-stu-id="2df93-195">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="2df93-196">Para iniciar o caminho de limpeza de dados, conclua estas etapas:</span><span class="sxs-lookup"><span data-stu-id="2df93-196">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="2df93-197">Remova as permissões de quebra e descodificação de "O365 Exchange Online" dos compartimentos de chave do Azure.</span><span class="sxs-lookup"><span data-stu-id="2df93-197">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="2df93-198">Usando uma conta corporativa ou de estudante que tenha privilégios de administrador global em sua organização, [Conecte-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="2df93-198">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

3. <span data-ttu-id="2df93-199">Para cada DEP que contenha caixas de correio que você deseja excluir, execute o cmdlet [set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-dataencryptionpolicy) da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="2df93-199">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="2df93-200">Se o comando falhar, verifique se você removeu as permissões do Exchange Online das chaves do Azure Key Vault, conforme especificado anteriormente nesta tarefa.</span><span class="sxs-lookup"><span data-stu-id="2df93-200">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="2df93-201">Depois de definir a opção PermanentDataPurgeRequested usando o cmdlet Set-DataEncryptionPolicy, você não poderá mais atribuir essa DEP às caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="2df93-201"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="2df93-202">Entre em contato com o suporte da Microsoft e solicite a limpeza de dados eDocument.</span><span class="sxs-lookup"><span data-stu-id="2df93-202">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="2df93-203">Na sua solicitação, a Microsoft envia a você um documento legal para confirmar e autorizar a exclusão de dados.</span><span class="sxs-lookup"><span data-stu-id="2df93-203">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="2df93-204">A pessoa em sua organização que se inscreveu como Aprovador na oferta do FastTrack durante a integração precisa assinar este documento.</span><span class="sxs-lookup"><span data-stu-id="2df93-204">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="2df93-205">Normalmente, esse é um executivo ou outra pessoa designada em sua empresa legalmente autorizada a assinar a papelada em nome da sua organização.</span><span class="sxs-lookup"><span data-stu-id="2df93-205">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="2df93-206">Depois que seu representante assinou o documento legal, devolva-o à Microsoft (geralmente por meio de uma assinatura eDoc).</span><span class="sxs-lookup"><span data-stu-id="2df93-206">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="2df93-207">Depois que a Microsoft recebe o documento legal, a Microsoft executa cmdlets para acionar a limpeza de dados que primeiro exclui a política, marca as caixas de correio para exclusão permanente e, em seguida, exclui a chave de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="2df93-207">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="2df93-208">Após a conclusão do processo de limpeza de dados, os dados são removidos, não podem ser acessados pelo Exchange Online e não são recuperáveis.</span><span class="sxs-lookup"><span data-stu-id="2df93-208">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="2df93-209">Revogar as chaves do cliente e a chave de disponibilidade para os arquivos do SharePoint Online, do OneDrive for Business e do teams</span><span class="sxs-lookup"><span data-stu-id="2df93-209">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="2df93-210">Para iniciar o caminho de limpeza de dados para os arquivos do SharePoint Online, do OneDrive for Business e do Teams, conclua estas etapas:</span><span class="sxs-lookup"><span data-stu-id="2df93-210">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="2df93-211">Revoga o acesso do Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="2df93-211">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="2df93-212">Todos os administradores de cofre de chaves devem concordar em revogar o acesso.</span><span class="sxs-lookup"><span data-stu-id="2df93-212">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="2df93-213">Você não exclui o Azure Key Vault para o SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="2df93-213">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="2df93-214">Os principais cofres podem ser compartilhados entre vários locatários e DEPs do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="2df93-214">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="2df93-215">Contate a Microsoft para excluir a chave de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="2df93-215">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="2df93-216">Ao entrar em contato com a Microsoft para excluir a chave de disponibilidade, enviaremos um documento legal.</span><span class="sxs-lookup"><span data-stu-id="2df93-216">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="2df93-217">A pessoa em sua organização que se inscreveu como Aprovador na oferta do FastTrack durante a integração precisa assinar este documento.</span><span class="sxs-lookup"><span data-stu-id="2df93-217">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="2df93-218">Normalmente, este é um executivo ou outra pessoa designada na sua empresa legalmente autorizada a assinar a papelada em nome da sua organização.</span><span class="sxs-lookup"><span data-stu-id="2df93-218">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="2df93-219">Depois que o representante assinar o documento legal, devolva-o à Microsoft (geralmente por meio de uma assinatura eDoc).</span><span class="sxs-lookup"><span data-stu-id="2df93-219">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="2df93-220">Depois que a Microsoft recebe o documento legal, executamos cmdlets para acionar a limpeza de dados que realiza a exclusão de criptografia da chave do locatário, da chave do site e de todas as chaves individuais por documento, irrevogável a hierarquia de chaves.</span><span class="sxs-lookup"><span data-stu-id="2df93-220">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="2df93-221">Depois que os cmdlets de limpeza de dados forem concluídos, seus dados foram removidos.</span><span class="sxs-lookup"><span data-stu-id="2df93-221">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="2df93-222">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="2df93-222">Related articles</span></span>

- [<span data-ttu-id="2df93-223">Criptografia de serviço com a chave do cliente</span><span class="sxs-lookup"><span data-stu-id="2df93-223">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="2df93-224">Saiba mais sobre a chave de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="2df93-224">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="2df93-225">Configurar a chave do cliente</span><span class="sxs-lookup"><span data-stu-id="2df93-225">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="2df93-226">Rolar ou girar uma Chave de Cliente ou uma chave de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="2df93-226">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="2df93-227">Sistema de Proteção de Dados do Cliente</span><span class="sxs-lookup"><span data-stu-id="2df93-227">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="2df93-228">Criptografia de serviço</span><span class="sxs-lookup"><span data-stu-id="2df93-228">Service Encryption</span></span>](office-365-service-encryption.md)
