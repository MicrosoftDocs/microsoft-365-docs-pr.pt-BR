---
title: Gerenciar Chave do Cliente
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
description: Depois de configurar a Chave do Cliente, saiba como gerenciá-la restaurando chaves AKV e gerenciando permissões e políticas de criptografia de dados.
ms.openlocfilehash: de85edd5c53fc2b76be4361575e1a85655c0f297
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547081"
---
# <a name="manage-customer-key"></a><span data-ttu-id="7d17f-103">Gerenciar Chave do Cliente</span><span class="sxs-lookup"><span data-stu-id="7d17f-103">Manage Customer Key</span></span>

<span data-ttu-id="7d17f-104">Depois de configurar a Chave do Cliente para o Office 365, você poderá gerenciar suas chaves conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="7d17f-104">After you've set up Customer Key for Office 365, you can manage your keys as described in this article.</span></span> <span data-ttu-id="7d17f-105">Saiba mais sobre a Chave do Cliente nos tópicos relacionados.</span><span class="sxs-lookup"><span data-stu-id="7d17f-105">Learn more about Customer Key in the related topics.</span></span>

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="7d17f-106">Restaurar chaves do Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="7d17f-106">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="7d17f-107">Antes de executar uma restauração, use os recursos de recuperação fornecidos pela exclusão suave.</span><span class="sxs-lookup"><span data-stu-id="7d17f-107">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="7d17f-108">Todas as chaves usadas com a Chave do Cliente devem ter a exclusão suave habilitada.</span><span class="sxs-lookup"><span data-stu-id="7d17f-108">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="7d17f-109">A exclusão suave age como uma lixeira e permite a recuperação por até 90 dias sem a necessidade de restauração.</span><span class="sxs-lookup"><span data-stu-id="7d17f-109">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="7d17f-110">A restauração só deve ser necessária em circunstâncias extremas ou incomuns, por exemplo, se a chave ou o cofre de chaves for perdido.</span><span class="sxs-lookup"><span data-stu-id="7d17f-110">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="7d17f-111">Se você tiver que restaurar uma chave para uso com a Chave do Cliente, no Azure PowerShell, execute o cmdlet Restore-AzureKeyVaultKey seguinte:</span><span class="sxs-lookup"><span data-stu-id="7d17f-111">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="7d17f-112">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7d17f-112">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="7d17f-113">Se o cofre de chaves já contiver uma chave com o mesmo nome, a operação de restauração falhará.</span><span class="sxs-lookup"><span data-stu-id="7d17f-113">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="7d17f-114">Restore-AzKeyVaultKey restaura todas as versões principais e todos os metadados da chave, incluindo o nome da chave.</span><span class="sxs-lookup"><span data-stu-id="7d17f-114">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="7d17f-115">Gerenciar permissões de cofre de chaves</span><span class="sxs-lookup"><span data-stu-id="7d17f-115">Manage key vault permissions</span></span>

<span data-ttu-id="7d17f-116">Vários cmdlets estão disponíveis que permitem exibir e, se necessário, remover permissões de cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="7d17f-116">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="7d17f-117">Talvez seja necessário remover permissões, por exemplo, quando um funcionário deixa a equipe.</span><span class="sxs-lookup"><span data-stu-id="7d17f-117">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="7d17f-118">Para cada uma dessas tarefas, você usará o Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d17f-118">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="7d17f-119">Para saber mais sobre o Azure PowerShell, confira [Visão geral do Azure PowerShell.](https://docs.microsoft.com/powershell/azure/)</span><span class="sxs-lookup"><span data-stu-id="7d17f-119">For information about Azure Powershell, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/).</span></span>

<span data-ttu-id="7d17f-120">Para exibir as permissões do cofre de chaves, execute o Get-AzKeyVault cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7d17f-120">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="7d17f-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7d17f-121">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="7d17f-122">Para remover as permissões de um administrador, execute o Remove-AzKeyVaultAccessPolicy cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7d17f-122">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="7d17f-123">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7d17f-123">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a><span data-ttu-id="7d17f-124">Gerenciar políticas de criptografia de dados (DEPs) com a Chave do Cliente</span><span class="sxs-lookup"><span data-stu-id="7d17f-124">Manage data encryption policies (DEPs) with Customer Key</span></span>

<span data-ttu-id="7d17f-125">A Chave do Cliente lida com DEPs de maneira diferente entre os diferentes serviços.</span><span class="sxs-lookup"><span data-stu-id="7d17f-125">Customer Key handles DEPs differently between the different services.</span></span> <span data-ttu-id="7d17f-126">Por exemplo, você pode criar um número diferente de DEPs para os diferentes serviços.</span><span class="sxs-lookup"><span data-stu-id="7d17f-126">For example, you can create a different number of DEPs for the different services.</span></span>

<span data-ttu-id="7d17f-127">**Exchange Online e Skype for Business:** Você pode criar até 50 DEPs.</span><span class="sxs-lookup"><span data-stu-id="7d17f-127">**Exchange Online and Skype for Business:** You can create up to 50 DEPs.</span></span> <span data-ttu-id="7d17f-128">Para obter instruções, [consulte Criar uma política de criptografia de dados (DEP) para uso com o Exchange Online e o Skype for Business.](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)</span><span class="sxs-lookup"><span data-stu-id="7d17f-128">For instructions, see [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span></span>

<span data-ttu-id="7d17f-129">**SharePoint Online, OneDrive for Business e arquivos do Teams:** Uma DEP se aplica a dados em uma localização geográfica, também chamada de _localização geográfica._</span><span class="sxs-lookup"><span data-stu-id="7d17f-129">**SharePoint Online, OneDrive for Business, and Teams files:** A DEP applies to data in one geographic location, also called a _geo_.</span></span> <span data-ttu-id="7d17f-130">Se você usar o recurso multi-geo do Office 365, poderá criar uma DEP por geo.</span><span class="sxs-lookup"><span data-stu-id="7d17f-130">If you use the multi-geo feature of Office 365, you can create one DEP per geo.</span></span> <span data-ttu-id="7d17f-131">Se você não estiver usando multi-geo, poderá criar uma DEP.</span><span class="sxs-lookup"><span data-stu-id="7d17f-131">If you are not using multi-geo, you can create one DEP.</span></span> <span data-ttu-id="7d17f-132">Normalmente, você cria a DEP quando configura a Chave do Cliente.</span><span class="sxs-lookup"><span data-stu-id="7d17f-132">Normally, you create the DEP when you set up Customer Key.</span></span> <span data-ttu-id="7d17f-133">Para obter instruções, confira Criar uma política de criptografia de dados [(DEP) para cada área](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)geográfica do SharePoint Online e do OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="7d17f-133">For instructions, see [Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="7d17f-134">Exibir os DEPs que você criou para o Exchange Online e o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7d17f-134">View the DEPs you've created for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="7d17f-135">Para exibir uma lista de todos os DEPs criados para o Exchange Online e o Skype for Business usando o cmdlet Get-DataEncryptionPolicy PowerShell, conclua estas etapas.</span><span class="sxs-lookup"><span data-stu-id="7d17f-135">To view a list of all the DEPs you've created for Exchange Online and Skype for Business using the Get-DataEncryptionPolicy PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="7d17f-136">Usando uma conta de trabalho ou de estudante que tenha permissões de administrador global em sua organização, [conecte-se ao PowerShell do Exchange Online.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="7d17f-136">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="7d17f-137">Para retornar todos os DEPs em sua organização, execute o cmdlet Get-DataEncryptionPolicy sem parâmetros.</span><span class="sxs-lookup"><span data-stu-id="7d17f-137">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

   ```powershell
   Get-DataEncryptionPolicy
   ```

   <span data-ttu-id="7d17f-138">Para obter mais informações sobre Get-DataEncryptionPolicy cmdlet, consulte [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy).</span><span class="sxs-lookup"><span data-stu-id="7d17f-138">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="7d17f-139">Atribuir uma DEP antes de migrar uma caixa de correio para a nuvem</span><span class="sxs-lookup"><span data-stu-id="7d17f-139">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="7d17f-140">Quando você atribui a DEP, o Microsoft 365 criptografa o conteúdo da caixa de correio usando a DEP atribuída durante a migração.</span><span class="sxs-lookup"><span data-stu-id="7d17f-140">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="7d17f-141">Esse processo é mais eficiente do que migrar a caixa de correio, atribuir a DEP e aguardar a criptografia ocorrer, o que pode levar horas ou possivelmente dias.</span><span class="sxs-lookup"><span data-stu-id="7d17f-141">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="7d17f-142">Para atribuir um DEP a uma caixa de correio antes de migrá-la para o Office 365, execute o cmdlet Set-MailUser no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="7d17f-142">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="7d17f-143">Usando uma conta de trabalho ou de estudante que tenha permissões de administrador global em sua organização, [conecte-se ao PowerShell do Exchange Online.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="7d17f-143">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="7d17f-144">Execute o Set-MailUser cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7d17f-144">Run the Set-MailUser cmdlet.</span></span>

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   <span data-ttu-id="7d17f-145">Onde *GeneralMailboxOrMailUserIdParameter* especifica uma caixa de correio e *DataEncryptionPolicyIdParameter* é a ID da DEP.</span><span class="sxs-lookup"><span data-stu-id="7d17f-145">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="7d17f-146">Para obter mais informações sobre Set-MailUser cmdlet, consulte [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser).</span><span class="sxs-lookup"><span data-stu-id="7d17f-146">For more information about the Set-MailUser cmdlet, see [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="7d17f-147">Determinar a DEP atribuída a uma caixa de correio</span><span class="sxs-lookup"><span data-stu-id="7d17f-147">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="7d17f-148">Para determinar a DEP atribuída a uma caixa de correio, use o Get-MailboxStatistics cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7d17f-148">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="7d17f-149">O cmdlet retorna um identificador exclusivo (GUID).</span><span class="sxs-lookup"><span data-stu-id="7d17f-149">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="7d17f-150">Usando uma conta de trabalho ou de estudante que tenha permissões de administrador global em sua organização, [conecte-se ao PowerShell do Exchange Online.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="7d17f-150">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="7d17f-151">Onde *GeneralMailboxOrMailUserIdParameter especifica* uma caixa de correio e DataEncryptionPolicyID retorna o GUID da DEP.</span><span class="sxs-lookup"><span data-stu-id="7d17f-151">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="7d17f-152">Para obter mais informações sobre o Get-MailboxStatistics cmdlet, consulte [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics).</span><span class="sxs-lookup"><span data-stu-id="7d17f-152">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics).</span></span>
  
2. <span data-ttu-id="7d17f-153">Execute o Get-DataEncryptionPolicy cmdlet para descobrir o nome amigável da DEP à qual a caixa de correio está atribuída.</span><span class="sxs-lookup"><span data-stu-id="7d17f-153">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="7d17f-154">Onde *GUID* é o GUID retornado pelo Get-MailboxStatistics cmdlet na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="7d17f-154">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="7d17f-155">Verificar se a chave do cliente concluiu a criptografia</span><span class="sxs-lookup"><span data-stu-id="7d17f-155">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="7d17f-156">Se você acabou de rolar uma Chave do Cliente, se atribuiu uma nova DEP ou migrou uma caixa de correio, use as etapas nesta seção para garantir que a criptografia seja concluída.</span><span class="sxs-lookup"><span data-stu-id="7d17f-156">Whether you've just rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="7d17f-157">Verificar a criptografia concluída para o Exchange Online e o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7d17f-157">Verify encryption completes for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="7d17f-158">Criptografar uma caixa de correio pode levar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="7d17f-158">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="7d17f-159">Recomendamos que você aguarde 72 horas antes de tentar validar a criptografia depois de alterar uma DEP ou da primeira vez que atribuir um DEP a uma caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="7d17f-159">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="7d17f-160">Use o Get-MailboxStatistics cmdlet para determinar se uma caixa de correio está criptografada.</span><span class="sxs-lookup"><span data-stu-id="7d17f-160">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="7d17f-161">A propriedade IsEncrypted retornará um valor verdadeiro se a  caixa de correio estiver criptografada e um valor falso se a caixa de correio não estiver criptografada. </span><span class="sxs-lookup"><span data-stu-id="7d17f-161">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="7d17f-162">O tempo para concluir as movimentações de caixa de correio depende do tamanho da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="7d17f-162">The time to complete mailbox moves depends on the size of the mailbox.</span></span> <span data-ttu-id="7d17f-163">Se a Chave do Cliente não tiver criptografado completamente a caixa de correio após 72 horas a partir do momento em que você atribuir uma nova DEP, entre em contato com o suporte da Microsoft para ajudar.</span><span class="sxs-lookup"><span data-stu-id="7d17f-163">If Customer Key hasn't completely encrypted the mailbox after 72 hours from the time you assign a new DEP, contact Microsoft support for help.</span></span> <span data-ttu-id="7d17f-164">O New-MoveRequest cmdlet não está mais disponível para movimentações de caixa de correio local.</span><span class="sxs-lookup"><span data-stu-id="7d17f-164">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="7d17f-165">Consulte este [comunicado para](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) obter informações adicionais.</span><span class="sxs-lookup"><span data-stu-id="7d17f-165">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="7d17f-166">Verificar a criptografia concluída para arquivos do SharePoint Online, OneDrive for Business e Teams</span><span class="sxs-lookup"><span data-stu-id="7d17f-166">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="7d17f-167">Verifique o status da criptografia executando o cmdlet Get-SPODataEncryptionPolicy a seguir:</span><span class="sxs-lookup"><span data-stu-id="7d17f-167">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="7d17f-168">A saída desse cmdlet inclui:</span><span class="sxs-lookup"><span data-stu-id="7d17f-168">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="7d17f-169">O URI da chave primária.</span><span class="sxs-lookup"><span data-stu-id="7d17f-169">The URI of the primary key.</span></span>

- <span data-ttu-id="7d17f-170">O URI da chave secundária.</span><span class="sxs-lookup"><span data-stu-id="7d17f-170">The URI of the secondary key.</span></span>

- <span data-ttu-id="7d17f-171">O status de criptografia da área geográfica.</span><span class="sxs-lookup"><span data-stu-id="7d17f-171">The encryption status for the geo.</span></span> <span data-ttu-id="7d17f-172">Os estados possíveis incluem:</span><span class="sxs-lookup"><span data-stu-id="7d17f-172">Possible states include:</span></span>

  - <span data-ttu-id="7d17f-173">**Não registro:** A criptografia da Chave do Cliente ainda não foi aplicada.</span><span class="sxs-lookup"><span data-stu-id="7d17f-173">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="7d17f-174">**Registro:** A criptografia de Chave de Cliente foi aplicada e seus arquivos estão em processo de criptografia.</span><span class="sxs-lookup"><span data-stu-id="7d17f-174">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="7d17f-175">Se a chave da área geográfica estiver se registrando, você também verá informações sobre qual porcentagem de sites na área geográfica está concluída para que você possa monitorar o progresso da criptografia.</span><span class="sxs-lookup"><span data-stu-id="7d17f-175">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="7d17f-176">**Registrado:** A criptografia da Chave do Cliente foi aplicada e todos os arquivos em todos os sites foram criptografados.</span><span class="sxs-lookup"><span data-stu-id="7d17f-176">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="7d17f-177">**Rolagem:** Uma rolagem de teclas está em andamento.</span><span class="sxs-lookup"><span data-stu-id="7d17f-177">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="7d17f-178">Se a chave da área geográfica estiver sendo rolada, você também verá informações sobre qual porcentagem de sites concluiu a operação de rolagem de chaves para que você possa monitorar o progresso.</span><span class="sxs-lookup"><span data-stu-id="7d17f-178">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="unassign-a-dep-from-a-mailbox"></a><span data-ttu-id="7d17f-179">Desa designe uma DEP de uma caixa de correio</span><span class="sxs-lookup"><span data-stu-id="7d17f-179">Unassign a DEP from a mailbox</span></span>

<span data-ttu-id="7d17f-180">Você desa designa uma DEP de uma caixa de correio usando o cmdlet Set-mailbox PowerShell e configurando `DataEncryptionPolicy` o para `$NULL` .</span><span class="sxs-lookup"><span data-stu-id="7d17f-180">You unassign a DEP from a mailbox using the Set-mailbox PowerShell cmdlet and setting the `DataEncryptionPolicy` to `$NULL`.</span></span> <span data-ttu-id="7d17f-181">A execução desse cmdlet desassocia a DEP atribuída no momento e criptografa a caixa de correio usando a DEP associada às chaves gerenciadas padrão da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7d17f-181">Running this cmdlet unassigns the currently assigned DEP and reencrypts the mailbox using the DEP associated with default Microsoft managed keys.</span></span> <span data-ttu-id="7d17f-182">Você não pode desa designá-la usada pelas chaves gerenciadas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7d17f-182">You can't unassign the DEP used by Microsoft managed keys.</span></span> <span data-ttu-id="7d17f-183">Se você não quiser usar chaves gerenciadas da Microsoft, poderá atribuir outra DEP à caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="7d17f-183">If you don't want to use Microsoft managed keys, you can assign another DEP to the mailbox.</span></span>

<span data-ttu-id="7d17f-184">Para desa designar a DEP de uma caixa de correio usando o cmdlet Set-Mailbox PowerShell, conclua estas etapas.</span><span class="sxs-lookup"><span data-stu-id="7d17f-184">To unassign the DEP from a mailbox using the Set-Mailbox PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="7d17f-185">Usando uma conta de trabalho ou de estudante que tenha permissões de administrador global em sua organização, [conecte-se ao PowerShell do Exchange Online.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="7d17f-185">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="7d17f-186">Execute o Set-Mailbox cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7d17f-186">Run the Set-Mailbox cmdlet.</span></span>

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="7d17f-187">Revogar suas chaves e iniciar o processo de limpeza de dados</span><span class="sxs-lookup"><span data-stu-id="7d17f-187">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="7d17f-188">Você controla a revogação de todas as chaves raiz, incluindo a chave de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="7d17f-188">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="7d17f-189">A Chave do Cliente fornece controle do aspecto de planejamento de saída dos requisitos regulatórios para você.</span><span class="sxs-lookup"><span data-stu-id="7d17f-189">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="7d17f-190">Se você decidir revogar suas chaves para limpar seus dados e sair do serviço, o serviço excluirá a chave de disponibilidade depois que o processo de limpeza de dados for concluído.</span><span class="sxs-lookup"><span data-stu-id="7d17f-190">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span>

<span data-ttu-id="7d17f-191">O Microsoft 365 audita e valida o caminho de limpeza de dados.</span><span class="sxs-lookup"><span data-stu-id="7d17f-191">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="7d17f-192">Para obter mais informações, consulte o Relatório do SOC 2 do SSAE 18 disponível no [Portal de Confiança do Serviço.](https://servicetrust.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="7d17f-192">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="7d17f-193">Além disso, a Microsoft recomenda os seguintes documentos:</span><span class="sxs-lookup"><span data-stu-id="7d17f-193">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="7d17f-194">Guia de Avaliação de Risco e Conformidade para Instituições Financeiras no Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="7d17f-194">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="7d17f-195">Considerações sobre o planejamento de saída do O365</span><span class="sxs-lookup"><span data-stu-id="7d17f-195">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="7d17f-196">O caminho de limpeza de dados difere ligeiramente entre os diferentes serviços.</span><span class="sxs-lookup"><span data-stu-id="7d17f-196">The data purge path differs slightly between the different services.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="7d17f-197">Revogar suas Chaves do Cliente e a chave de disponibilidade do Exchange Online e do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7d17f-197">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="7d17f-198">Ao iniciar o caminho de limpeza de dados para o Exchange Online e o Skype for Business, você configura uma solicitação de limpeza de dados permanente em uma DEP.</span><span class="sxs-lookup"><span data-stu-id="7d17f-198">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="7d17f-199">Isso exclui permanentemente os dados criptografados nas caixas de correio às quais essa DEP está atribuída.</span><span class="sxs-lookup"><span data-stu-id="7d17f-199">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="7d17f-200">Como você só pode executar o cmdlet do PowerShell em um DEP por vez, considere reatribuir uma única DEP a todas as suas caixas de correio antes de iniciar o caminho de limpeza de dados.</span><span class="sxs-lookup"><span data-stu-id="7d17f-200">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="7d17f-201">Não use o caminho de limpeza de dados para excluir um subconjunto de suas caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="7d17f-201">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="7d17f-202">Esse processo destina-se apenas aos clientes que estão saindo do serviço.</span><span class="sxs-lookup"><span data-stu-id="7d17f-202">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="7d17f-203">Para iniciar o caminho de limpeza de dados, conclua estas etapas:</span><span class="sxs-lookup"><span data-stu-id="7d17f-203">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="7d17f-204">Remova as permissões wrap e unwrap do "Exchange Online do O365" do Azure Key Vaults.</span><span class="sxs-lookup"><span data-stu-id="7d17f-204">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="7d17f-205">Usando uma conta de trabalho ou de estudante que tenha privilégios de administrador global em sua organização, [conecte-se ao PowerShell do Exchange Online.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="7d17f-205">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

3. <span data-ttu-id="7d17f-206">Para cada DEP que contém caixas de correio que você deseja excluir, execute o cmdlet [Set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="7d17f-206">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="7d17f-207">Se o comando falhar, verifique se você removeu as permissões do Exchange Online das duas chaves no Azure Key Vault conforme especificado anteriormente nesta tarefa.</span><span class="sxs-lookup"><span data-stu-id="7d17f-207">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="7d17f-208">Depois de definir a opção PermanentDataPurgeRequested usando o cmdlet Set-DataEncryptionPolicy, você não poderá mais atribuir essa DEP às caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="7d17f-208"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="7d17f-209">Entre em contato com o suporte da Microsoft e solicite o eDocument de Limpeza de Dados.</span><span class="sxs-lookup"><span data-stu-id="7d17f-209">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="7d17f-210">A sua solicitação, a Microsoft envia um documento legal para confirmar e autorizar a exclusão de dados.</span><span class="sxs-lookup"><span data-stu-id="7d17f-210">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="7d17f-211">A pessoa em sua organização que se inscreveu como aprovador na oferta do FastTrack durante a integração precisa assinar este documento.</span><span class="sxs-lookup"><span data-stu-id="7d17f-211">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="7d17f-212">Normalmente, é um executivo ou outra pessoa designada em sua empresa que está legalmente autorizado a assinar a documentação em nome da sua organização.</span><span class="sxs-lookup"><span data-stu-id="7d17f-212">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="7d17f-213">Depois que seu representante assinar o documento legal, retorne-o à Microsoft (geralmente por meio de uma assinatura do eDoc).</span><span class="sxs-lookup"><span data-stu-id="7d17f-213">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="7d17f-214">Depois que a Microsoft recebe o documento legal, a Microsoft executa cmdlets para disparar a limpeza de dados que primeiro exclui a política, marca as caixas de correio para exclusão permanente e, em seguida, exclui a chave de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="7d17f-214">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="7d17f-215">Depois que o processo de limpeza de dados for concluído, os dados serão limpos, estarão inacessíveis para o Exchange Online e não serão recuperáveis.</span><span class="sxs-lookup"><span data-stu-id="7d17f-215">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="7d17f-216">Revogar suas Chaves do Cliente e a chave de disponibilidade para arquivos do SharePoint Online, OneDrive for Business e Teams</span><span class="sxs-lookup"><span data-stu-id="7d17f-216">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="7d17f-217">Para iniciar o caminho de limpeza de dados para arquivos do SharePoint Online, OneDrive for Business e Teams, conclua estas etapas:</span><span class="sxs-lookup"><span data-stu-id="7d17f-217">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="7d17f-218">Revogar o acesso ao Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="7d17f-218">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="7d17f-219">Todos os administradores do cofre de chaves devem concordar em revogar o acesso.</span><span class="sxs-lookup"><span data-stu-id="7d17f-219">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="7d17f-220">Você não exclui o Azure Key Vault para SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7d17f-220">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="7d17f-221">Os cofres de chaves podem ser compartilhados entre vários locatários e DEPs do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7d17f-221">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="7d17f-222">Contate a Microsoft para excluir a chave de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="7d17f-222">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="7d17f-223">Quando você contatar a Microsoft para excluir a chave de disponibilidade, enviaremos um documento legal.</span><span class="sxs-lookup"><span data-stu-id="7d17f-223">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="7d17f-224">A pessoa em sua organização que se inscreveu como aprovador na oferta do FastTrack durante a integração precisa assinar este documento.</span><span class="sxs-lookup"><span data-stu-id="7d17f-224">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="7d17f-225">Normalmente, é um executivo ou outra pessoa designada em sua empresa que está legalmente autorizado a assinar a documentação em nome da sua organização.</span><span class="sxs-lookup"><span data-stu-id="7d17f-225">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="7d17f-226">Depois que seu representante assinar o documento legal, retorne-o à Microsoft (geralmente por meio de uma assinatura do eDoc).</span><span class="sxs-lookup"><span data-stu-id="7d17f-226">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="7d17f-227">Depois que a Microsoft recebe o documento legal, executamos cmdlets para disparar a limpeza de dados que executa a exclusão criptografada da chave de locatário, da chave do site e de todas as chaves individuais por documento, quebrando irrevogavelmente a hierarquia de chaves.</span><span class="sxs-lookup"><span data-stu-id="7d17f-227">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="7d17f-228">Depois que os cmdlets de limpeza de dados são concluídos, seus dados são limpos.</span><span class="sxs-lookup"><span data-stu-id="7d17f-228">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="7d17f-229">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="7d17f-229">Related articles</span></span>

- [<span data-ttu-id="7d17f-230">Criptografia do serviço com a Chave de Cliente</span><span class="sxs-lookup"><span data-stu-id="7d17f-230">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="7d17f-231">Saiba mais sobre a chave de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="7d17f-231">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="7d17f-232">Configurar a Chave do Cliente</span><span class="sxs-lookup"><span data-stu-id="7d17f-232">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="7d17f-233">Rolar ou girar uma Chave de Cliente ou uma chave de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="7d17f-233">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="7d17f-234">Sistema de Proteção de Dados do Cliente</span><span class="sxs-lookup"><span data-stu-id="7d17f-234">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="7d17f-235">Criptografia de Serviço</span><span class="sxs-lookup"><span data-stu-id="7d17f-235">Service Encryption</span></span>](office-365-service-encryption.md)
