---
title: Rolar ou girar uma Chave de Cliente ou uma chave de disponibilidade
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
description: Saiba como rolar as chaves raiz do cliente armazenadas no Azure Key Vault que são usadas com a Chave do Cliente. Os serviços incluem Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business e Teams arquivos.
ms.openlocfilehash: 892d77959bec1fb33b0ea6bcfaa8c530dd9b8911
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345113"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a><span data-ttu-id="c671a-104">Rolar ou girar uma Chave de Cliente ou uma chave de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="c671a-104">Roll or rotate a Customer Key or an availability key</span></span>

> [!CAUTION]
> <span data-ttu-id="c671a-105">Somente role uma chave de criptografia que você usa com a Chave do Cliente quando seus requisitos de segurança ou conformidade determinam que você deve rolar a chave.</span><span class="sxs-lookup"><span data-stu-id="c671a-105">Only roll an encryption key that you use with Customer Key when your security or compliance requirements dictate that you must roll the key.</span></span> <span data-ttu-id="c671a-106">Além disso, não exclua as chaves que estão ou foram associadas às políticas.</span><span class="sxs-lookup"><span data-stu-id="c671a-106">In addition, do not delete any keys that are or were associated with policies.</span></span> <span data-ttu-id="c671a-107">Quando você rolar suas chaves, haverá conteúdo criptografado com as chaves anteriores.</span><span class="sxs-lookup"><span data-stu-id="c671a-107">When you roll your keys, there will be content encrypted with the previous keys.</span></span> <span data-ttu-id="c671a-108">Por exemplo, embora as caixas de correio ativas sejam criptografadas com frequência, as caixas de correio inativas, desconectadas e desabilitadas ainda poderão ser criptografadas com as chaves anteriores.</span><span class="sxs-lookup"><span data-stu-id="c671a-108">For example, while active mailboxes will be re-encrypted frequently, inactive, disconnected, and disabled mailboxes may still be encrypted with the previous keys.</span></span> <span data-ttu-id="c671a-109">SharePoint Online executa backup de conteúdo para fins de restauração e recuperação, portanto, ainda pode haver conteúdo arquivado usando chaves mais antigas.</span><span class="sxs-lookup"><span data-stu-id="c671a-109">SharePoint Online performs backup of content for restore and recovery purposes, so there may still be archived content using older keys.</span></span>

## <a name="about-rolling-the-availability-key"></a><span data-ttu-id="c671a-110">Sobre a rolagem da chave de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="c671a-110">About rolling the availability key</span></span>

<span data-ttu-id="c671a-111">A Microsoft não expõe o controle direto da chave de disponibilidade aos clientes.</span><span class="sxs-lookup"><span data-stu-id="c671a-111">Microsoft does not expose direct control of the availability key to customers.</span></span> <span data-ttu-id="c671a-112">Por exemplo, você só pode rolar (girar) as chaves que possui no Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="c671a-112">For example, you can only roll (rotate) the keys that you own in Azure Key Vault.</span></span> <span data-ttu-id="c671a-113">Microsoft 365 as chaves de disponibilidade em um cronograma definido internamente.</span><span class="sxs-lookup"><span data-stu-id="c671a-113">Microsoft 365 rolls the availability keys on an internally-defined schedule.</span></span> <span data-ttu-id="c671a-114">Não há nenhum contrato de nível de serviço (SLA) voltado para o cliente para esses rolados de chaves.</span><span class="sxs-lookup"><span data-stu-id="c671a-114">There is no customer-facing, service-level agreement (SLA) for these key rolls.</span></span> <span data-ttu-id="c671a-115">Microsoft 365 gira a chave de disponibilidade usando Microsoft 365 código de serviço em um processo automatizado e não manual.</span><span class="sxs-lookup"><span data-stu-id="c671a-115">Microsoft 365 rotates the availability key using Microsoft 365 service code in an automated, non-manual process.</span></span> <span data-ttu-id="c671a-116">Os administradores da Microsoft podem iniciar o processo de rolagem.</span><span class="sxs-lookup"><span data-stu-id="c671a-116">Microsoft administrators may initiate the roll process.</span></span> <span data-ttu-id="c671a-117">A chave é rolada usando mecanismos automatizados sem acesso direto ao armazenamento de chaves.</span><span class="sxs-lookup"><span data-stu-id="c671a-117">The key is rolled using automated mechanisms without direct access to the key store.</span></span> <span data-ttu-id="c671a-118">O acesso ao armazenamento secreto da chave de disponibilidade não é provisionado para administradores da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c671a-118">Access to the availability key secret store is not provisioned to Microsoft administrators.</span></span> <span data-ttu-id="c671a-119">A rolagem da chave de disponibilidade aproveita o mesmo mecanismo usado inicialmente para gerar a chave.</span><span class="sxs-lookup"><span data-stu-id="c671a-119">Availability key rolling leverages the same mechanism used to initially generate the key.</span></span> <span data-ttu-id="c671a-120">Para obter mais informações sobre a chave de disponibilidade, consulte [Understand the availability key](customer-key-availability-key-understand.md).</span><span class="sxs-lookup"><span data-stu-id="c671a-120">For more information about the availability key, see [Understand the availability key](customer-key-availability-key-understand.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c671a-121">Exchange Online e Skype for Business de disponibilidade podem ser efetivamente roladas pelos clientes criando um novo DEP, pois uma chave de disponibilidade exclusiva é gerada para cada DEP que você criar.</span><span class="sxs-lookup"><span data-stu-id="c671a-121">Exchange Online and Skype for Business availability keys can be effectively rolled by customers creating a new DEP, since a unique availability key is generated for each DEP you create.</span></span> <span data-ttu-id="c671a-122">As chaves de disponibilidade para arquivos SharePoint Online, OneDrive for Business e Teams existem no nível da floresta e são compartilhadas entre DEPs e clientes, o que significa que a rolagem só ocorre em um cronograma definido internamente pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c671a-122">Availability keys for SharePoint Online, OneDrive for Business, and Teams files exist at the forest level and are shared across DEPs and customers, which means rolling only occurs at a Microsoft internally defined schedule.</span></span> <span data-ttu-id="c671a-123">Para atenuar o risco de não rolar a chave de disponibilidade sempre que uma nova DEP for criada, SharePoint, OneDrive e Teams rolar a chave intermediária do locatário (TIK), a chave envolvida pelas chaves raiz do cliente e pela chave de disponibilidade, sempre que um novo DEP for criado.</span><span class="sxs-lookup"><span data-stu-id="c671a-123">To mitigate the risk of not rolling the availability key each time a new DEP is created, SharePoint, OneDrive, and Teams roll the tenant intermediate key (TIK), the key wrapped by the customer root keys and availability key, each time a new DEP is created.</span></span>

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a><span data-ttu-id="c671a-124">Solicitar uma nova versão de cada chave raiz existente que você deseja rolar</span><span class="sxs-lookup"><span data-stu-id="c671a-124">Request a new version of each existing root key you want to roll</span></span>

<span data-ttu-id="c671a-125">Quando você rola uma chave, solicita uma nova versão de uma chave existente.</span><span class="sxs-lookup"><span data-stu-id="c671a-125">When you roll a key, you request a new version of an existing key.</span></span> <span data-ttu-id="c671a-126">Para solicitar uma nova versão de uma chave existente, use o mesmo cmdlet, [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey), com a mesma sintaxe usada para criar a chave em primeiro lugar.</span><span class="sxs-lookup"><span data-stu-id="c671a-126">To request a new version of an existing key, you use the same cmdlet, [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey), with the same syntax that you used to create the key in the first place.</span></span> <span data-ttu-id="c671a-127">Depois de terminar de rolar qualquer chave associada a uma POLÍTICA de Criptografia de Dados (DEP), execute outro cmdlet para garantir que a Chave do Cliente comece a usar a nova chave.</span><span class="sxs-lookup"><span data-stu-id="c671a-127">After you've finished rolling any key associated with a Data Encryption Policy (DEP), you run another cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="c671a-128">Faça esta etapa em cada Azure Key Vault (AKV).</span><span class="sxs-lookup"><span data-stu-id="c671a-128">Do this step in each Azure Key Vault (AKV).</span></span>

<span data-ttu-id="c671a-129">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c671a-129">For example:</span></span>

1. <span data-ttu-id="c671a-130">Entre em sua assinatura do Azure com Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c671a-130">Sign in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="c671a-131">Para obter instruções, [consulte Entrar com Azure PowerShell](/powershell/azure/authenticate-azureps).</span><span class="sxs-lookup"><span data-stu-id="c671a-131">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="c671a-132">Execute o Add-AzKeyVaultKey cmdlet como mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="c671a-132">Run the Add-AzKeyVaultKey cmdlet as shown in the following example:</span></span>

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   <span data-ttu-id="c671a-133">Neste exemplo, como uma chave chamada **Contoso-CK-EX-NA-VaultA1-Key001** existe no cofre **Contoso-CK-EX-NA-VaultA1,** o cmdlet cria uma nova versão da chave.</span><span class="sxs-lookup"><span data-stu-id="c671a-133">In this example, since a key named **Contoso-CK-EX-NA-VaultA1-Key001** exists in the **Contoso-CK-EX-NA-VaultA1** vault, the cmdlet creates a new version of the key.</span></span> <span data-ttu-id="c671a-134">Essa operação preserva as versões de chave anteriores no histórico de versão da chave.</span><span class="sxs-lookup"><span data-stu-id="c671a-134">This operation preserves the previous key versions in the version history for the key.</span></span> <span data-ttu-id="c671a-135">Você precisa da versão da chave anterior para descriptografar os dados que eles ainda criptografam.</span><span class="sxs-lookup"><span data-stu-id="c671a-135">You need the previous key version to decrypt the data that it still encrypts.</span></span> <span data-ttu-id="c671a-136">Depois de concluir a rolagem de qualquer chave associada a um DEP, execute um cmdlet extra para garantir que a Chave do Cliente comece a usar a nova chave.</span><span class="sxs-lookup"><span data-stu-id="c671a-136">Once you complete rolling any key associated with a DEP,  run an extra cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="c671a-137">As seções a seguir descrevem os cmdlets com mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="c671a-137">The following sections describe the cmdlets in more detail.</span></span>
  
## <a name="update-the-keys-for-multi-workload-deps"></a><span data-ttu-id="c671a-138">Atualizar as chaves para DEPs de várias cargas de trabalho</span><span class="sxs-lookup"><span data-stu-id="c671a-138">Update the keys for multi-workload DEPs</span></span>

<span data-ttu-id="c671a-139">Quando você rola uma das teclas do Azure Key Vault associadas a um DEP usado com várias cargas de trabalho, você deve atualizar o DEP para apontar para a nova chave.</span><span class="sxs-lookup"><span data-stu-id="c671a-139">When you roll either of the Azure Key Vault keys associated with a DEP used with multiple workloads, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="c671a-140">Esse processo não gira a chave de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="c671a-140">This process does not rotate the availability key.</span></span>

<span data-ttu-id="c671a-141">Para instruir a Chave do Cliente a usar a nova chave para criptografar várias cargas de trabalho, conclua estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c671a-141">To instruct Customer Key to use the new key to encrypt multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="c671a-142">Em seu computador local, usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador ou administrador de conformidade em sua organização, conecte-se ao [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) em uma janela Windows PowerShell de conformidade.</span><span class="sxs-lookup"><span data-stu-id="c671a-142">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="c671a-143">Execute o cmdlet Set-M365DataAtRestEncryptionPolicy.</span><span class="sxs-lookup"><span data-stu-id="c671a-143">Run the Set-M365DataAtRestEncryptionPolicy cmdlet.</span></span>
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Refresh
   ```

<span data-ttu-id="c671a-144">Onde *PolicyName* é o nome ou ID exclusiva da política.</span><span class="sxs-lookup"><span data-stu-id="c671a-144">Where *PolicyName* is the name or unique ID of the policy.</span></span> <span data-ttu-id="c671a-145">Por exemplo, Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="c671a-145">For example, Contoso_Global.</span></span>

<span data-ttu-id="c671a-146">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="c671a-146">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Refresh
```

## <a name="update-the-keys-for-exchange-online-deps"></a><span data-ttu-id="c671a-147">Atualizar as chaves para Exchange Online DEPs</span><span class="sxs-lookup"><span data-stu-id="c671a-147">Update the keys for Exchange Online DEPs</span></span>

<span data-ttu-id="c671a-148">Quando você rola uma das teclas do Azure Key Vault associadas a um DEP usado com Exchange Online e Skype for Business, você deve atualizar o DEP para apontar para a nova chave.</span><span class="sxs-lookup"><span data-stu-id="c671a-148">When you roll either of the Azure Key Vault keys associated with a DEP used with Exchange Online and Skype for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="c671a-149">Isso não gira a chave de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="c671a-149">This does not rotate the availability key.</span></span>

<span data-ttu-id="c671a-150">Para instruir a Chave do Cliente a usar a nova chave para criptografar caixas de correio, execute o cmdlet Set-DataEncryptionPolicy da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="c671a-150">To instruct Customer Key to use the new key to encrypt mailboxes, run the Set-DataEncryptionPolicy cmdlet as follows:</span></span>

1. <span data-ttu-id="c671a-151">Execute o cmdlet Set-DataEncryptionPolicy Azure PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c671a-151">Run the Set-DataEncryptionPolicy cmdlet in Azure PowerShell:</span></span>
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

2. <span data-ttu-id="c671a-152">Para verificar o valor da propriedade DataEncryptionPolicyID para a caixa de correio, use as etapas em [Determine the DEP assigned to a mailbox](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox).</span><span class="sxs-lookup"><span data-stu-id="c671a-152">To check the value for the DataEncryptionPolicyID property for the mailbox, use the steps in [Determine the DEP assigned to a mailbox](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox).</span></span> <span data-ttu-id="c671a-153">O valor dessa propriedade muda quando o serviço aplica a chave atualizada.</span><span class="sxs-lookup"><span data-stu-id="c671a-153">The value for this property changes once the service applies the updated key.</span></span>
  
## <a name="update-the-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="c671a-154">Atualizar as chaves para arquivos SharePoint Online, OneDrive for Business e Teams</span><span class="sxs-lookup"><span data-stu-id="c671a-154">Update the keys for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="c671a-155">SharePoint Online só permite rolar uma chave por vez.</span><span class="sxs-lookup"><span data-stu-id="c671a-155">SharePoint Online only allows you to roll one key at a time.</span></span> <span data-ttu-id="c671a-156">Se você quiser rolar as duas chaves em um cofre de chaves, aguarde a conclusão da primeira operação.</span><span class="sxs-lookup"><span data-stu-id="c671a-156">If you want to roll both keys in a key vault, wait for the first operation to complete.</span></span> <span data-ttu-id="c671a-157">A Microsoft recomenda que você escalone suas operações para evitar esse problema.</span><span class="sxs-lookup"><span data-stu-id="c671a-157">Microsoft recommends that you stagger your operations to avoid this issue.</span></span> <span data-ttu-id="c671a-158">Quando você rola uma das teclas do Azure Key Vault associadas a um DEP usado com o SharePoint Online e o OneDrive for Business, você deve atualizar o DEP para apontar para a nova chave.</span><span class="sxs-lookup"><span data-stu-id="c671a-158">When you roll either of the Azure Key Vault keys associated with a DEP used with SharePoint Online and OneDrive for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="c671a-159">Isso não gira a chave de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="c671a-159">This does not rotate the availability key.</span></span>

1. <span data-ttu-id="c671a-160">Execute o Update-SPODataEncryptionPolicy cmdlet da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="c671a-160">Run the Update-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   <span data-ttu-id="c671a-161">Enquanto esse cmdlet inicia a operação de rolagem de chaves para SharePoint Online e OneDrive for Business, a ação não é concluída imediatamente.</span><span class="sxs-lookup"><span data-stu-id="c671a-161">While this cmdlet starts the key roll operation for SharePoint Online and OneDrive for Business, the action doesn't complete immediately.</span></span>

2. <span data-ttu-id="c671a-162">Para ver o progresso da operação de rolagem de teclas, execute o cmdlet Get-SPODataEncryptionPolicy da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="c671a-162">To see the progress of the key roll operation, run the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a><span data-ttu-id="c671a-163">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="c671a-163">Related articles</span></span>

- [<span data-ttu-id="c671a-164">Criptografia de serviço com Chave de Cliente para Office 365</span><span class="sxs-lookup"><span data-stu-id="c671a-164">Service encryption with Customer Key for Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="c671a-165">Configurar a Chave de Cliente do Office 365</span><span class="sxs-lookup"><span data-stu-id="c671a-165">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="c671a-166">Gerenciar Chave de Cliente do Office 365</span><span class="sxs-lookup"><span data-stu-id="c671a-166">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="c671a-167">Saiba mais sobre a chave de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="c671a-167">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)