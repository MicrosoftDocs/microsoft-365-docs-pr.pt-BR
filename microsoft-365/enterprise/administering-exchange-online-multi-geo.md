---
title: Administrar caixas de correio do Exchange Online em um ambiente multigeográfico
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
localization_priority: normal
description: Saiba como administrar as configurações multigeográficas do Exchange Online no seu ambiente do Microsoft 365 com o PowerShell.
ms.openlocfilehash: 996566d67aa8ba7ebca1406cd5d6265458637fee
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546241"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a><span data-ttu-id="cf669-103">Administrar caixas de correio do Exchange Online em um ambiente multigeográfico</span><span class="sxs-lookup"><span data-stu-id="cf669-103">Administering Exchange Online mailboxes in a multi-geo environment</span></span>

<span data-ttu-id="cf669-104">O PowerShell do Exchange Online é necessário para exibir e configurar várias propriedades geográficas no seu ambiente do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cf669-104">Exchange Online PowerShell is required to view and configure multi geo properties in your Microsoft 365 environment.</span></span> <span data-ttu-id="cf669-105">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="cf669-105">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="cf669-106">É necessário o [Módulo Microsoft Azure Active Directory PowerShell](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 ou superior em v1. x para ver a propriedade **PreferredDataLocation** nos objetos do usuário.</span><span class="sxs-lookup"><span data-stu-id="cf669-106">You need the [Microsoft Azure Active Directory PowerShell Module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 or later in v1.x to see the **PreferredDataLocation** property on user objects.</span></span> <span data-ttu-id="cf669-107">Objetos do usuário sincronizados por meio do AAD Connect no AAD não podem ter seu valore **PreferredDataLocation** modificado diretamente por meio do AAD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf669-107">User objects synchronized via AAD Connect into AAD cannot have their **PreferredDataLocation** value directly modified via AAD PowerShell.</span></span> <span data-ttu-id="cf669-108">Objetos Apenas Nuvem de usuário podem ser modificados pelo AAD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf669-108">Cloud-only user objects can be modified via AAD PowerShell.</span></span> <span data-ttu-id="cf669-109">Para se conectar ao PowerShell do Azure AD, consulte [Conectar-se ao PowerShell](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="cf669-109">To connect to Azure AD PowerShell, see [Connect to PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a><span data-ttu-id="cf669-110">Conecte-se diretamente em uma localização geográfica usando o Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf669-110">Connect directly to a geo location using Exchange Online PowerShell</span></span>

<span data-ttu-id="cf669-111">Normalmente, o PowerShell do Exchange Online se conectará à localização geográfica central.</span><span class="sxs-lookup"><span data-stu-id="cf669-111">Typically, Exchange Online PowerShell will connect to the central geo location.</span></span> <span data-ttu-id="cf669-112">Mas você também pode se conectar diretamente a localizações geográficas por satélite.</span><span class="sxs-lookup"><span data-stu-id="cf669-112">But, you can also connect directly to satellite geo locations.</span></span> <span data-ttu-id="cf669-113">Devido a melhorias no desempenho, recomendamos que você se conecte diretamente à localização geográfica por satélite quando você gerenciar apenas usuários nessa localização.</span><span class="sxs-lookup"><span data-stu-id="cf669-113">Because of performance improvements, we recommend connecting directly to the satellite geo location when you only manage users in that location.</span></span>

<span data-ttu-id="cf669-114">Os requisitos para instalar e usar o módulo EXO V2 são descritos em [Instalar e manter o módulo EXO V2](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span><span class="sxs-lookup"><span data-stu-id="cf669-114">The requirements for installing and using the EXO V2 module are described in [Install and maintain the EXO V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

<span data-ttu-id="cf669-115">Para conectar o PowerShell do Exchange Online a uma localização geográfica específica, o parâmetro *ConnectionURI* é diferente das instruções de conexão normais.</span><span class="sxs-lookup"><span data-stu-id="cf669-115">To connect Exchange Online PowerShell to a specific geo location, the *ConnectionUri* parameter is different than the regular connection instructions.</span></span> <span data-ttu-id="cf669-116">O restante dos comandos e valores são iguais.</span><span class="sxs-lookup"><span data-stu-id="cf669-116">The rest of the commands and values are the same.</span></span>

<span data-ttu-id="cf669-117">Especificamente, você precisa adicionar o `?email=<emailaddress>` valor para o final do valor _ConnectionURI_ .</span><span class="sxs-lookup"><span data-stu-id="cf669-117">Specifically, you need to add the `?email=<emailaddress>` value to end of the _ConnectionUri_ value.</span></span> <span data-ttu-id="cf669-118">`<emailaddress>` é o endereço de email de **qualquer** caixa de correio na localização geográfica de destino.</span><span class="sxs-lookup"><span data-stu-id="cf669-118">`<emailaddress>` is the email address of **any** mailbox in the target geo location.</span></span> <span data-ttu-id="cf669-119">Suas permissões para essa caixa de correio ou a relação com suas credenciais não são um fator; o endereço de email simplesmente diz ao Exchange Online PowerShell onde se conectar.</span><span class="sxs-lookup"><span data-stu-id="cf669-119">Your permissions to that mailbox or the relationship to your credentials are not a factor; the email address simply tells Exchange Online PowerShell where to connect.</span></span>

<span data-ttu-id="cf669-120">Os clientes Microsoft 365 ou Microsoft 365 GCC normalmente não precisam usar o parâmetro _ConnectionURI_ para se conectar ao PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cf669-120">Microsoft 365 or Microsoft 365 GCC customers typically don't need to use the _ConnectionUri_ parameter to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="cf669-121">Mas, para se conectar a um local geográfico específico, você precisa usar o parâmetro _ConnectionURI_ para que possa usar `?email=<emailaddress>` o valor.</span><span class="sxs-lookup"><span data-stu-id="cf669-121">But, to connect to a specific geo location, you do need to use _ConnectionUri_ parameter so you can use `?email=<emailaddress>` in the value.</span></span>

### <a name="connect-to-a-geo-location-in-exchange-online-powershell-using-multi-factor-authentication-mfa"></a><span data-ttu-id="cf669-122">Conectar-se a um local geográfico no PowerShell do Exchange Online usando a protocolo de autenticação multifator (MFA)</span><span class="sxs-lookup"><span data-stu-id="cf669-122">Connect to a geo location in Exchange Online PowerShell using multi-factor authentication (MFA)</span></span>

1. <span data-ttu-id="cf669-123">Em uma janela do Windows PowerShell, carregue o módulo EXO V2 executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="cf669-123">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="cf669-124">No exemplo a seguir, admin@contoso.onmicrosoft.com é a conta de administrador e a localização geográfica de destino é onde o olga@contoso.onmicrosoft.com de caixa de correio reside.</span><span class="sxs-lookup"><span data-stu-id="cf669-124">In the following example, admin@contoso.onmicrosoft.com is the admin account, and the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

  ```powershell
  Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ShowProgress $true -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
  ```

### <a name="connect-to-a-geo-location-in-exchange-online-powershell-without-using-mfa"></a><span data-ttu-id="cf669-125">Conectar-se a um local geográfico no PowerShell do Exchange Online sem usar a MFA</span><span class="sxs-lookup"><span data-stu-id="cf669-125">Connect to a geo location in Exchange Online PowerShell without using MFA</span></span>

1. <span data-ttu-id="cf669-126">Em uma janela do Windows PowerShell, carregue o módulo EXO V2 executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="cf669-126">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="cf669-127">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="cf669-127">Run the following command:</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

   <span data-ttu-id="cf669-128">Na caixa de diálogo **Solicitação de Credencial do Windows PowerShell** que aparece, digite sua conta corporativa ou de estudante e a senha, e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="cf669-128">In the **Windows PowerShell Credential Request** dialog box that appears, type your work or school account and password, and then click **OK**.</span></span>

3. <span data-ttu-id="cf669-129">No exemplo a seguir, a localização geográfica de destino é onde reside a caixa de correio olga@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="cf669-129">In the following example, the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

   ```powershell
   Connect-ExchangeOnline -Credential $UserCredential -ShowProgress $true -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a><span data-ttu-id="cf669-130">Exibir as localizações geográficas disponíveis que estão configurados em sua organização do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cf669-130">View the available geo locations that are configured in your Exchange Online organization</span></span>

<span data-ttu-id="cf669-131">Para visualizar a lista dos locais geográficos configurados no Microsoft 365 Multi-Geo, execute o seguinte comando no Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cf669-131">To see the list of configured geo locations in Microsoft 365 Multi-Geo, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a><span data-ttu-id="cf669-132">Ver a localização geográfica central da sua organização do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cf669-132">View the central geo location for your Exchange Online organization</span></span>

<span data-ttu-id="cf669-133">Para exibir a localização geográfica central do seu locatário, execute o seguinte comando no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="cf669-133">To view your tenant's central geo location, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a><span data-ttu-id="cf669-134">Descobrir a localização geográfica de uma caixa de correio</span><span class="sxs-lookup"><span data-stu-id="cf669-134">Find the geo location of a mailbox</span></span>

<span data-ttu-id="cf669-135">O cmdlet **Get-Mailbox** no Exchange Online PowerShell exibe as seguintes propriedades relacionadas às áreas multigeográficas nas caixas de correio:</span><span class="sxs-lookup"><span data-stu-id="cf669-135">The **Get-Mailbox** cmdlet in Exchange Online PowerShell displays the following multi-geo related properties on mailboxes:</span></span>

- <span data-ttu-id="cf669-136">**Banco de dados**: As 3 primeiras letras do nome do banco de dados correspondem ao código geográfico, o que determina onde a caixa de correio está localizada no momento.</span><span class="sxs-lookup"><span data-stu-id="cf669-136">**Database**: The first 3 letters of the database name correspond to the geo code, which tells you where the mailbox is currently located.</span></span> <span data-ttu-id="cf669-137">Para Caixas de Correio com Arquivo Online a propriedade **ArchiveDatabase** deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="cf669-137">For Online Archive Mailboxes the **ArchiveDatabase** property should be used.</span></span>

- <span data-ttu-id="cf669-138">**MailboxRegion**: Especifica o código da localização geográfica que foi definida pelo administrador (sincronizado do **PreferredDataLocation** no Azure AD).</span><span class="sxs-lookup"><span data-stu-id="cf669-138">**MailboxRegion**: Specifies the geo location code that was set by the admin (synchronized from **PreferredDataLocation** in Azure AD).</span></span>

- <span data-ttu-id="cf669-139">**MailboxRegionLastUpdateTime**: Indica quando o MailboxRegion foi atualizado (automaticamente ou manualmente).</span><span class="sxs-lookup"><span data-stu-id="cf669-139">**MailboxRegionLastUpdateTime**: Indicates when MailboxRegion was last updated (either automatically or manually).</span></span>

<span data-ttu-id="cf669-140">Para ver as propriedades de uma caixa de correio, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="cf669-140">To see these properties for a mailbox, use the following syntax:</span></span>

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

<span data-ttu-id="cf669-141">Por exemplo, para ver as informações da localização geográfica da caixa de correio de chris@contoso.onmicrosoft.com, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="cf669-141">For example, to see the geo location information for the mailbox chris@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

<span data-ttu-id="cf669-142">A saída do comando será parecida com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cf669-142">The output of the command looks like this:</span></span>

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> <span data-ttu-id="cf669-143">Se o código de localização geográfica no nome do banco de dados não corresponder ao valor de **MailboxRegion** , a caixa de correio será automaticamente colocada em uma fila de realocação e movida para o local geográfico especificado pelo valor **MailboxRegion** (o Exchange Online procura por uma incompatibilidade entre esses valores de propriedade).</span><span class="sxs-lookup"><span data-stu-id="cf669-143">If the geo location code in the database name doesn't match **MailboxRegion** value, the mailbox will be automatically be put into a relocation queue and moved to the geo location specified by the **MailboxRegion** value (Exchange Online looks for a mismatch between these property values).</span></span>

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a><span data-ttu-id="cf669-144">Mover uma caixa de correio apenas nuvem existente para uma localização geográfica específica</span><span class="sxs-lookup"><span data-stu-id="cf669-144">Move an existing cloud-only mailbox to a specific geo location</span></span>

<span data-ttu-id="cf669-145">Um usuário somente na nuvem é um usuário não sincronizado com o locatário por meio do AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="cf669-145">A cloud-only user is a user not synchronized to the tenant via AAD Connect.</span></span> <span data-ttu-id="cf669-146">Esse usuário foi criado diretamente no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="cf669-146">This user was created directly in Azure AD.</span></span> <span data-ttu-id="cf669-147">Use os cmdlets **Get-MsolUser** e **Set-MsolUser** no Módulo Azure AD para Windows PowerShell para exibir ou especificar a localização geográfica onde a caixa de correio de um usuário somente na nuvem será armazenada.</span><span class="sxs-lookup"><span data-stu-id="cf669-147">Use the **Get-MsolUser** and **Set-MsolUser** cmdlets in the Azure AD Module for Windows PowerShell to view or specify the geo location where a cloud-only user's mailbox will be stored.</span></span>

<span data-ttu-id="cf669-148">Para exibir o valor **PreferredDataLocation** para um usuário, use esta sintaxe no Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cf669-148">To view the **PreferredDataLocation** value for a user, use this syntax in Azure AD PowerShell:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

<span data-ttu-id="cf669-149">Por exemplo, para ver o valor **PreferredDataLocation** para o usuário michelle@contoso.onmicrosoft.com, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="cf669-149">For example, to see the **PreferredDataLocation** value for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

<span data-ttu-id="cf669-150">Para modificar o valor **PreferredDataLocation** para um objeto de usuário apenas nuvem, use a seguinte sintaxe no Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cf669-150">To modify the **PreferredDataLocation** value for a cloud-only user object, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="cf669-151">Por exemplo, para configurar o valor **PreferredDataLocation** para a área geográfica União Europeia (UE) para o usuário michelle@contoso.onmicrosoft.com, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="cf669-151">For example, to set the **PreferredDataLocation** value to the European Union (EUR) geo for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - <span data-ttu-id="cf669-152">Como mencionado anteriormente, você não pode usar este procedimento para objetos de usuário sincronizados do Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="cf669-152">As mentioned previously, you cannot use this procedure for synchronized user objects from on-premises Active Directory.</span></span> <span data-ttu-id="cf669-153">Você precisa alterar o valor **PreferredDataLocation** no Active Directory e sincronizá-lo usando o AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="cf669-153">You need to change the **PreferredDataLocation** value in Active Directory and synchronize it using AAD Connect.</span></span> <span data-ttu-id="cf669-154">Para obter mais informações, consulte [Sincronização do Azure Active Directory Connect: Configurar o local preferencial dos dados dos recursos do Microsoft 365](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span><span class="sxs-lookup"><span data-stu-id="cf669-154">For more information, see [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span></span>
>
> - <span data-ttu-id="cf669-155">O tempo que leva para relocar uma caixa de correio para uma nova localização geográfica depende de vários fatores:</span><span class="sxs-lookup"><span data-stu-id="cf669-155">How long it takes to relocate a mailbox to a new geo location depends on several factors:</span></span>
>
>   - <span data-ttu-id="cf669-156">O tamanho e tipo de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="cf669-156">The size and type of mailbox.</span></span>
>   - <span data-ttu-id="cf669-157">O número de caixas de correio sendo movidas.</span><span class="sxs-lookup"><span data-stu-id="cf669-157">The number of mailboxes being moved.</span></span>
>   - <span data-ttu-id="cf669-158">Disponibilidade de recursos de movimentação.</span><span class="sxs-lookup"><span data-stu-id="cf669-158">The availability of move resources.</span></span>

### <a name="move-disabled-mailboxes-that-are-on-litigation-hold"></a><span data-ttu-id="cf669-159">Mover caixas de correio desabilitadas que estão em Retenção de Litígio</span><span class="sxs-lookup"><span data-stu-id="cf669-159">Move disabled mailboxes that are on Litigation Hold</span></span>

<span data-ttu-id="cf669-160">Caixas de correio desabilitadas em Retenção de Litígio são preservadas para fins de descoberta eletrônica não podem ser movidas alterando seu valor **PreferredDataLocation** no estado desabilitado.</span><span class="sxs-lookup"><span data-stu-id="cf669-160">Disabled mailboxes on Litigation Hold that are preserved for eDiscovery purposes cannot be moved by changing their **PreferredDataLocation** value in their disabled state.</span></span> <span data-ttu-id="cf669-161">Para mover uma caixa de correio desabilitada em retenção de litígio:</span><span class="sxs-lookup"><span data-stu-id="cf669-161">To move a disabled mailbox on litigation hold:</span></span>

1. <span data-ttu-id="cf669-162">Atribua temporariamente uma licença à caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="cf669-162">Temporarily assign a license to the mailbox.</span></span>

2. <span data-ttu-id="cf669-163">Altere o **PreferredDataLocation**.</span><span class="sxs-lookup"><span data-stu-id="cf669-163">Change the **PreferredDataLocation**.</span></span>

3. <span data-ttu-id="cf669-164">Remova a licença da caixa de correio depois de ser movida para a localização geográfica selecionada para colocá-la novamente no estado desabilitado.</span><span class="sxs-lookup"><span data-stu-id="cf669-164">Remove the license from the mailbox after it has been moved to the selected geo location to put it back into the disabled state.</span></span>

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="cf669-165">Criar novas caixas de correio em nuvem em uma localização geográfica específica</span><span class="sxs-lookup"><span data-stu-id="cf669-165">Create new cloud mailboxes in a specific geo location</span></span>

<span data-ttu-id="cf669-166">Para criar uma nova caixa de correio em uma localização geográfica específica, é preciso seguir uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="cf669-166">To create a new mailbox in a specific geo location, you need to do either of these steps:</span></span>

- <span data-ttu-id="cf669-167">Configurar o valor **PreferredDataLocation** conforme descrito na seção anterior *antes* da caixa de correio ser criada no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cf669-167">Configure the **PreferredDataLocation** value as described in the previous section *before* the mailbox is created in Exchange Online.</span></span> <span data-ttu-id="cf669-168">Por exemplo, configure valor **PreferredDataLocation** em um usuário antes de atribuir uma licença.</span><span class="sxs-lookup"><span data-stu-id="cf669-168">For example, configure the **PreferredDataLocation** value on a user before assigning a license.</span></span>

- <span data-ttu-id="cf669-169">Atribuir uma licença e definir o valor **PreferredDataLocation** ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="cf669-169">Assign a license at the same time you set the **PreferredDataLocation** value.</span></span>

<span data-ttu-id="cf669-170">Para criar um novo usuário licenciado somente na nuvem (não sincronizado pelo AAD Connect) em uma localização geográfica específica, use a seguinte sintaxe no PowerShell do Azure AD:</span><span class="sxs-lookup"><span data-stu-id="cf669-170">To create a new cloud-only licensed user (not AAD Connect synchronized) in a specific geo location, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="cf669-171">Este exemplo cria uma nova conta de usuário para Elizabeth Brunner com os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="cf669-171">This example create a new user account for Elizabeth Brunner with the following values:</span></span>

- <span data-ttu-id="cf669-172">Nome de usuário principal: ebrunner@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="cf669-172">User principal name: ebrunner@contoso.onmicrosoft.com</span></span>
- <span data-ttu-id="cf669-173">Nome: Elizabeth</span><span class="sxs-lookup"><span data-stu-id="cf669-173">First name: Elizabeth</span></span>
- <span data-ttu-id="cf669-174">Sobrenome: Brunner</span><span class="sxs-lookup"><span data-stu-id="cf669-174">Last name: Brunner</span></span>
- <span data-ttu-id="cf669-175">Nome para exibição: Elizabeth Brunner</span><span class="sxs-lookup"><span data-stu-id="cf669-175">Display name: Elizabeth Brunner</span></span>
- <span data-ttu-id="cf669-176">Senha: gerada aleatoriamente e mostrada nos resultados do comando (porque não estamos usando o parâmetro *Senha*)</span><span class="sxs-lookup"><span data-stu-id="cf669-176">Password: randomly-generated and shown in the results of the command (because we're not using the *Password* parameter)</span></span>
- <span data-ttu-id="cf669-177">Licença: `contoso:ENTERPRISEPREMIUM` (E5)</span><span class="sxs-lookup"><span data-stu-id="cf669-177">License: `contoso:ENTERPRISEPREMIUM` (E5)</span></span>
- <span data-ttu-id="cf669-178">Local: Austrália (AUS)</span><span class="sxs-lookup"><span data-stu-id="cf669-178">Location: Australia (AUS)</span></span>

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

<span data-ttu-id="cf669-179">Para obter mais informações de como criar novas contas de usuário e encontrar os valores LicenseAssignment no Azure AD PowerShell, consulte [Criar contas de usuário com o PowerShell](create-user-accounts-with-microsoft-365-powershell.md) e [Exibir licenças e serviços com o PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="cf669-179">For more information about creating new user accounts and finding LicenseAssignment values in Azure AD PowerShell, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md) and [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

> [!NOTE]
> <span data-ttu-id="cf669-180">Se você estiver usando o PowerShell do Exchange Online para habilitar uma caixa de correio e precisar que a caixa de correio seja criada diretamente na localização geográfica especificada em **PreferredDataLocation**, será necessário usar um cmdlet do Exchange Online como **Enable-Mailbox** ou **New-Mailbox** diretamente no serviço de nuvem.</span><span class="sxs-lookup"><span data-stu-id="cf669-180">If you are using Exchange Online PowerShell to enable a mailbox and need the mailbox to be created directly in the geo location that's specified in **PreferredDataLocation**, you need to use an Exchange Online cmdlet such as **Enable-Mailbox** or **New-Mailbox** directly against the cloud service.</span></span> <span data-ttu-id="cf669-181">Se você usar o cmdlet **Enable-RemoteMailbox** no Exchange PowerShell local, a caixa de correio será criada na localização geográfica central.</span><span class="sxs-lookup"><span data-stu-id="cf669-181">If you use the **Enable-RemoteMailbox** cmdlet in on-premises Exchange PowerShell, the mailbox will be created in the central geo location.</span></span>

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="cf669-182">Integração de caixas de correio locais existentes em uma localização geográfica específica</span><span class="sxs-lookup"><span data-stu-id="cf669-182">Onboard existing on-premises mailboxes in a specific geo location</span></span>

<span data-ttu-id="cf669-183">Você pode usar as ferramentas de integração padrão e os processos para migrar uma caixa de correio de uma organização do Exchange local para o Exchange Online, incluindo o [Painel de migração no EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)e o cmdlet [New-MigrationBatch ](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) no Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf669-183">You can use the standard onboarding tools and processes to migrate a mailbox from an on-premises Exchange organization to Exchange Online, including the [Migration dashboard in the EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), and the [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) cmdlet in Exchange Online PowerShell.</span></span>

<span data-ttu-id="cf669-184">A primeira etapa consiste em verificar um objeto de usuário existente para cada caixa de correio a ser integrada e verificar se o valor **PreferredDataLocation** correto está configurado no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="cf669-184">The first step is to verify a user object exists for each mailbox to be onboarded, and verify the correct **PreferredDataLocation** value is configured in Azure AD.</span></span> <span data-ttu-id="cf669-185">As ferramentas de integração respeitarão o valor **PreferredDataLocation** e migrarão as caixas de correio diretamente para a localização geográfica especificada.</span><span class="sxs-lookup"><span data-stu-id="cf669-185">The onboarding tools will respect the **PreferredDataLocation** value and will migrate the mailboxes directly to the specified geo location.</span></span>

<span data-ttu-id="cf669-186">Ou você pode usar as etapas a seguir para integrar as caixas de correio diretamente em uma localização geográfica específica usando o cmdlet [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet no Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf669-186">Or, you can use the following steps to onboard mailboxes directly in a specific geo location using the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet in Exchange Online PowerShell.</span></span>

1. <span data-ttu-id="cf669-187">Verifique se o objeto do usuário existe para cada caixa de correio integrada e se o **PreferredDataLocation** está definido com o valor desejado no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="cf669-187">Verify the user object exists for each mailbox to be onboarded and that **PreferredDataLocation** is set to the desired value in Azure AD.</span></span> <span data-ttu-id="cf669-188">O valor do **PreferredDataLocation** será sincronizado com o atributo **MailboxRegion** do objeto do usuário de email correspondentes no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cf669-188">The value of **PreferredDataLocation** will be synchronized to the **MailboxRegion** attribute of the corresponding mail user object in Exchange Online.</span></span>

2. <span data-ttu-id="cf669-189">Conecte-se diretamente à localização geográfica por satélite específica usando as instruções de conexão descritas anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="cf669-189">Connect directly to the specific satellite geo location using the connection instructions from earlier in this topic.</span></span>

3. <span data-ttu-id="cf669-190">No Exchange Online PowerShell armazene as credenciais de administrador local usadas para realizar a migração da caixa de correio em uma variável ao executar o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="cf669-190">In Exchange Online PowerShell, store the on-premises administrator credentials that's used to perform a mailbox migration in a variable by running the following command:</span></span>

   ```powershell
   $RC = Get-Credential
   ```

4. <span data-ttu-id="cf669-191">No Exchange Online PowerShell, crie um novo **New-MoveRequest** semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="cf669-191">In Exchange Online PowerShell, create a new **New-MoveRequest** similar to the following example:</span></span>

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. <span data-ttu-id="cf669-192">Repita a etapa 4 para cada caixa de correio que você precisa migrar do Exchange local para a localização geográfica por satélite à qual você está conectado no momento.</span><span class="sxs-lookup"><span data-stu-id="cf669-192">Repeat step #4 for every mailbox you need to migrate from on-premises Exchange to the satellite geo location you are currently connected to.</span></span>

6. <span data-ttu-id="cf669-193">Se você precisar migrar caixas de correio adicionais para diferentes localizações geográficas por satélite, repita as etapas de 2 a 4 para cada localização específica.</span><span class="sxs-lookup"><span data-stu-id="cf669-193">If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.</span></span>

## <a name="multi-geo-reporting"></a><span data-ttu-id="cf669-194">Relatórios multigeográficos</span><span class="sxs-lookup"><span data-stu-id="cf669-194">Multi-geo reporting</span></span>

<span data-ttu-id="cf669-195">**Relatórios de uso multigeográfico** no centro de administração do Microsoft 365 centro exiba a contagem de usuários por localização geográfica.</span><span class="sxs-lookup"><span data-stu-id="cf669-195">**Multi-Geo Usage Reports** in the Microsoft 365 admin center displays the user count by geo location.</span></span> <span data-ttu-id="cf669-196">O relatório exibe a distribuição do usuário no mês atual e fornece dados históricos para os últimos seis meses.</span><span class="sxs-lookup"><span data-stu-id="cf669-196">The report displays user distribution for the current month and provides historical data for the past 6 months.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf669-197">Confira também</span><span class="sxs-lookup"><span data-stu-id="cf669-197">See also</span></span>

[<span data-ttu-id="cf669-198">Gerenciar o Microsoft 365 e o Exchange Online com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf669-198">Managing Microsoft 365 and Exchange Online with Windows PowerShell</span></span>](https://support.office.com//article/06a743bb-ceb6-49a9-a61d-db4ffdf54fa6)
