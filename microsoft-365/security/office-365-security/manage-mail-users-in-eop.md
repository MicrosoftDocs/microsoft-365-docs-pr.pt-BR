---
title: Gerenciar usuários de e-mail no EOP autônomo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Saiba mais sobre como gerenciar usuários de email na proteção do Exchange Online (EOP), incluindo o uso da sincronização de diretórios, da Eat e do PowerShell para gerenciar usuários.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d82170499bcfa6465164ca2644eea43c2558ad18
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616829"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="37481-103">Gerenciar usuários de e-mail no EOP autônomo</span><span class="sxs-lookup"><span data-stu-id="37481-103">Manage mail users in standalone EOP</span></span>

<span data-ttu-id="37481-104">Em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, os usuários de email são o tipo fundamental de conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="37481-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="37481-105">Um usuário de email tem credenciais de conta em sua organização autônoma do EOP e pode acessar recursos (permissões atribuídas).</span><span class="sxs-lookup"><span data-stu-id="37481-105">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="37481-106">O endereço de email de um usuário de email é externo (por exemplo, em seu ambiente de email local).</span><span class="sxs-lookup"><span data-stu-id="37481-106">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="37481-107">Quando você cria um usuário de email, a conta de usuário correspondente está disponível no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="37481-107">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="37481-108">Ao criar uma conta de usuário no centro de administração do Microsoft 365, você não pode usar essa conta para criar um usuário de email.</span><span class="sxs-lookup"><span data-stu-id="37481-108">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="37481-109">O método recomendado para criar e gerenciar usuários de email no EOP autônomo é usar a sincronização de diretórios, conforme descrito na seção [usar a sincronização de diretórios para gerenciar usuários de email](#use-directory-synchronization-to-manage-mail-users) mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="37481-109">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this topic.</span></span>

<span data-ttu-id="37481-110">Para organizações EOP autônomas com um pequeno número de usuários, você pode adicionar e gerenciar usuários de email no centro de administração do Exchange (Eat) ou no EOP PowerShell autônomo, conforme descrito neste tópico.</span><span class="sxs-lookup"><span data-stu-id="37481-110">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this topic.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="37481-111">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="37481-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="37481-112">Para abrir o centro de administração do Exchange (Eat), confira [centro de administração do Exchange em EOP autônomo](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="37481-112">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="37481-113">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="37481-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="37481-114">Ao criar usuários de email no EOP PowerShell, você pode encontrar limitação.</span><span class="sxs-lookup"><span data-stu-id="37481-114">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="37481-115">Além disso, os cmdlets do EOP PowerShell usam um método de processamento em lotes que resulta em um atraso de propagação de alguns minutos antes que os resultados dos comandos fiquem visíveis.</span><span class="sxs-lookup"><span data-stu-id="37481-115">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="37481-116">Você precisa receber permissões para executar esses procedimentos.</span><span class="sxs-lookup"><span data-stu-id="37481-116">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="37481-117">Especificamente, você precisa das funções de criação de destinatário de email (criar) e de destinatários de email (modificar), que são atribuídas aos grupos de função gerenciamento (administradores globais) e RecipientManagement por padrão.</span><span class="sxs-lookup"><span data-stu-id="37481-117">Specifically, you need the Mail Recipient Creation (create) and Mail Recipients (modify) roles, which are assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="37481-118">Para obter mais informações, consulte [permissões em EOP autônomos](feature-permissions-in-eop.md) e [use o Eat modificar a lista de membros nos grupos de função](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="37481-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="37481-119">Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="37481-119">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="37481-120">Está com problemas?</span><span class="sxs-lookup"><span data-stu-id="37481-120">Having problems?</span></span> <span data-ttu-id="37481-121">Peça ajuda nos fóruns do Exchange.</span><span class="sxs-lookup"><span data-stu-id="37481-121">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="37481-122">Visite o fórum do [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="37481-122">Visit the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="37481-123">Usar o centro de administração do Exchange para gerenciar usuários de email</span><span class="sxs-lookup"><span data-stu-id="37481-123">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="37481-124">Usar o Eat para criar usuários de email</span><span class="sxs-lookup"><span data-stu-id="37481-124">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="37481-125">No Eat, vá para **Recipients** \> **contatos** de destinatários</span><span class="sxs-lookup"><span data-stu-id="37481-125">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="37481-126">Clique em **novo** ![ ícone novo ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="37481-126">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="37481-127">Na página **novo usuário de email** que é aberta, defina as seguintes configurações.</span><span class="sxs-lookup"><span data-stu-id="37481-127">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="37481-128">As configurações marcadas com um <sup>\*</sup> são obrigatórias.</span><span class="sxs-lookup"><span data-stu-id="37481-128">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="37481-129">**Nome**</span><span class="sxs-lookup"><span data-stu-id="37481-129">**First name**</span></span>

   - <span data-ttu-id="37481-130">**Iniciais**: a inicial do segundo nome da pessoa.</span><span class="sxs-lookup"><span data-stu-id="37481-130">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="37481-131">**Sobrenome**</span><span class="sxs-lookup"><span data-stu-id="37481-131">**Last name**</span></span>

   - <span data-ttu-id="37481-132"><sup>\*</sup>**Nome para exibição**: por padrão, essa caixa mostra os valores das **caixas nome**, **iniciais**e **sobrenome** .</span><span class="sxs-lookup"><span data-stu-id="37481-132"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="37481-133">Você pode aceitar esse valor ou alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="37481-133">You can accept this value or change it.</span></span> <span data-ttu-id="37481-134">O valor deve ser exclusivo e ter um comprimento máximo de 64 caracteres.</span><span class="sxs-lookup"><span data-stu-id="37481-134">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="37481-135"><sup>\*</sup>**Alias**: Insira um alias exclusivo, usando até 64 caracteres, para o usuário</span><span class="sxs-lookup"><span data-stu-id="37481-135"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="37481-136">**Endereço de email externo**: Insira o endereço de email do usuário.</span><span class="sxs-lookup"><span data-stu-id="37481-136">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="37481-137">O domínio deve ser externo à sua organização baseada na nuvem.</span><span class="sxs-lookup"><span data-stu-id="37481-137">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="37481-138"><sup>\*</sup>**ID de usuário**: Insira a conta que a pessoa usará para entrar no serviço.</span><span class="sxs-lookup"><span data-stu-id="37481-138"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="37481-139">A ID do usuário consiste em um nome de usuário no lado esquerdo do símbolo de arroba (@) e um domínio no lado direito.</span><span class="sxs-lookup"><span data-stu-id="37481-139">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="37481-140"><sup>\*</sup>**Nova senha** e <sup>\*</sup> **Confirmar senha**: Insira e digite novamente a senha da conta.</span><span class="sxs-lookup"><span data-stu-id="37481-140"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="37481-141">Verifique se a senha está em conformidade com os requisitos de tamanho, complexidade e histórico de senha da sua organização.</span><span class="sxs-lookup"><span data-stu-id="37481-141">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="37481-142">Quando tiver terminado, clique em **Salvar** para criar o usuário de email.</span><span class="sxs-lookup"><span data-stu-id="37481-142">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="37481-143">Usar o Eat para modificar usuários de email</span><span class="sxs-lookup"><span data-stu-id="37481-143">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="37481-144">No EAC, acesse **Destinatários** \> **Contatos**.</span><span class="sxs-lookup"><span data-stu-id="37481-144">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="37481-145">Selecione o usuário de email que você deseja modificar e clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="37481-145">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="37481-146">Na página de propriedades do usuário de email que é aberta, clique em uma das guias a seguir para exibir ou alterar propriedades.</span><span class="sxs-lookup"><span data-stu-id="37481-146">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="37481-147">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="37481-147">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="37481-148">Geral</span><span class="sxs-lookup"><span data-stu-id="37481-148">General</span></span>

<span data-ttu-id="37481-149">Use a guia **geral** para exibir ou alterar as informações básicas sobre o usuário de email.</span><span class="sxs-lookup"><span data-stu-id="37481-149">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="37481-150">**Nome**</span><span class="sxs-lookup"><span data-stu-id="37481-150">**First name**</span></span>

- <span data-ttu-id="37481-151">**Iniciais**</span><span class="sxs-lookup"><span data-stu-id="37481-151">**Initials**</span></span>

- <span data-ttu-id="37481-152">**Sobrenome**</span><span class="sxs-lookup"><span data-stu-id="37481-152">**Last name**</span></span>

- <span data-ttu-id="37481-153">**Nome para exibição**: esse nome é exibido no catálogo de endereços da sua organização, nas linhas para: e de: no email e na lista de contatos no Eat.</span><span class="sxs-lookup"><span data-stu-id="37481-153">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="37481-154">Esse nome não pode conter espaços vazios antes ou depois do nome para exibição.</span><span class="sxs-lookup"><span data-stu-id="37481-154">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="37481-155">**ID do usuário**: esta é a conta do usuário no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="37481-155">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="37481-156">Você não pode modificar este valor aqui.</span><span class="sxs-lookup"><span data-stu-id="37481-156">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="37481-157">Informações de contato</span><span class="sxs-lookup"><span data-stu-id="37481-157">Contact information</span></span>

<span data-ttu-id="37481-158">Use a guia **informações de contato** para exibir ou alterar as informações de contato do usuário.</span><span class="sxs-lookup"><span data-stu-id="37481-158">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="37481-159">As informações nesta página são exibidas no catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="37481-159">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="37481-160">**Street**</span><span class="sxs-lookup"><span data-stu-id="37481-160">**Street**</span></span>
- <span data-ttu-id="37481-161">**Cidade**</span><span class="sxs-lookup"><span data-stu-id="37481-161">**City**</span></span>
- <span data-ttu-id="37481-162">**Estado/Província**</span><span class="sxs-lookup"><span data-stu-id="37481-162">**State/Province**</span></span>
- <span data-ttu-id="37481-163">**CEP/código postal**</span><span class="sxs-lookup"><span data-stu-id="37481-163">**ZIP/Postal code**</span></span>
- <span data-ttu-id="37481-164">**País/região**</span><span class="sxs-lookup"><span data-stu-id="37481-164">**Country/Region**</span></span>
- <span data-ttu-id="37481-165">**Telefone comercial**</span><span class="sxs-lookup"><span data-stu-id="37481-165">**Work phone**</span></span>
- <span data-ttu-id="37481-166">**Telefone celular**</span><span class="sxs-lookup"><span data-stu-id="37481-166">**Mobile phone**</span></span>
- <span data-ttu-id="37481-167">**Fax**</span><span class="sxs-lookup"><span data-stu-id="37481-167">**Fax**</span></span>
- <span data-ttu-id="37481-168">**Mais opções**</span><span class="sxs-lookup"><span data-stu-id="37481-168">**More options**</span></span>

  - <span data-ttu-id="37481-169">**Office**</span><span class="sxs-lookup"><span data-stu-id="37481-169">**Office**</span></span>
  - <span data-ttu-id="37481-170">**Telefone residencial**</span><span class="sxs-lookup"><span data-stu-id="37481-170">**Home phone**</span></span>
  - <span data-ttu-id="37481-171">**Página da Web**</span><span class="sxs-lookup"><span data-stu-id="37481-171">**Web page**</span></span>
  - <span data-ttu-id="37481-172">**Anotações**</span><span class="sxs-lookup"><span data-stu-id="37481-172">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="37481-173">Organização</span><span class="sxs-lookup"><span data-stu-id="37481-173">Organization</span></span>

<span data-ttu-id="37481-174">Use a guia **organização** para registrar informações detalhadas sobre a função do usuário na organização.</span><span class="sxs-lookup"><span data-stu-id="37481-174">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="37481-175">**Title**</span><span class="sxs-lookup"><span data-stu-id="37481-175">**Title**</span></span>
- <span data-ttu-id="37481-176">**Departamento**</span><span class="sxs-lookup"><span data-stu-id="37481-176">**Department**</span></span>
- <span data-ttu-id="37481-177">**Company**</span><span class="sxs-lookup"><span data-stu-id="37481-177">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="37481-178">Usar o Eat para remover usuários de email</span><span class="sxs-lookup"><span data-stu-id="37481-178">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="37481-179">No EAC, acesse **Destinatários** \> **Contatos**.</span><span class="sxs-lookup"><span data-stu-id="37481-179">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="37481-180">Selecione o usuário de email que você deseja remover e clique em **remover** ![ ícone Remover ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="37481-180">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="37481-181">Usar o PowerShell para gerenciar usuários de email</span><span class="sxs-lookup"><span data-stu-id="37481-181">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="37481-182">Usar o EOP PowerShell autônomo para exibir usuários de email</span><span class="sxs-lookup"><span data-stu-id="37481-182">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="37481-183">Para retornar uma lista resumida de todos os usuários de email do EOP PowerShell autônomo, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="37481-183">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="37481-184">Para exibir informações detalhadas sobre um usuário de email específico, substitua \<MailUserIdentity\> o nome, o alias ou o nome da conta do usuário de email e execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="37481-184">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="37481-185">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) e [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).</span><span class="sxs-lookup"><span data-stu-id="37481-185">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="37481-186">Usar o EOP autônomo do PowerShell para criar usuários de email</span><span class="sxs-lookup"><span data-stu-id="37481-186">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="37481-187">Para criar usuários de email no EOP PowerShell autônomo, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="37481-187">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="37481-188">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="37481-188">**Notes**:</span></span>

- <span data-ttu-id="37481-189">O parâmetro _Name_ é obrigatório, tem um comprimento máximo de 64 caracteres e deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="37481-189">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="37481-190">Se você não usa o parâmetro _DisplayName_, o valor do parâmetro _Name_ é usado para o nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="37481-190">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="37481-191">Se você não usar o parâmetro _alias_ , o lado esquerdo do parâmetro _MicrosoftOnlneServicesID_ será usado para o alias.</span><span class="sxs-lookup"><span data-stu-id="37481-191">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlneServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="37481-192">Se você não usar o parâmetro _ExternalEmailAddress_ , o valor _MicrosoftOnlineServicesID_ será usado para o endereço de email externo.</span><span class="sxs-lookup"><span data-stu-id="37481-192">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="37481-193">Este exemplo cria um usuário de email com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="37481-193">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="37481-194">O nome é JeffreyZeng e o nome de exibição é Jeffrey Martins.</span><span class="sxs-lookup"><span data-stu-id="37481-194">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="37481-195">O primeiro nome é Diogo e o sobrenome é Martins.</span><span class="sxs-lookup"><span data-stu-id="37481-195">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="37481-196">O alias é diogom.</span><span class="sxs-lookup"><span data-stu-id="37481-196">The alias is jeffreyz.</span></span>
- <span data-ttu-id="37481-197">O endereço de email externo é diogom@tailspintoys.com.</span><span class="sxs-lookup"><span data-stu-id="37481-197">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="37481-198">O nome da conta é jeffreyz@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="37481-198">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="37481-199">A senha é Pa$$word1.</span><span class="sxs-lookup"><span data-stu-id="37481-199">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="37481-200">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="37481-200">For detailed syntax and parameter information, see [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="37481-201">Usar EOP PowerShell autônomo para modificar usuários de email</span><span class="sxs-lookup"><span data-stu-id="37481-201">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="37481-202">Para modificar usuários de email existentes no PowerShell autônomo do EOP, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="37481-202">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Textg>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="37481-203">Este exemplo define o endereço de email externo de Brenda Fernandes.</span><span class="sxs-lookup"><span data-stu-id="37481-203">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="37481-204">Este exemplo define a propriedade Company de todos os usuários de email como Contoso.</span><span class="sxs-lookup"><span data-stu-id="37481-204">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="37481-205">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="37481-205">For detailed syntax and parameter information, see [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="37481-206">Usar o EOP PowerShell autônomo para remover usuários de email</span><span class="sxs-lookup"><span data-stu-id="37481-206">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="37481-207">Para remover usuários de email do EOP PowerShell autônomo, substitua \<MailUserIdentity\> o nome, o alias ou o nome da conta do usuário de email e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="37481-207">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="37481-208">Este exemplo remove o usuário de email de Jeffrey Martins.</span><span class="sxs-lookup"><span data-stu-id="37481-208">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="37481-209">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="37481-209">For detailed syntax and parameter information, see [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="37481-210">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="37481-210">How do you know these procedures worked?</span></span>

<span data-ttu-id="37481-211">Para verificar se você criou, modificou ou removeu com êxito os usuários de email no EOP autônomo, use qualquer um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="37481-211">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="37481-212">No EAC, acesse **Destinatários** \> **Contatos**.</span><span class="sxs-lookup"><span data-stu-id="37481-212">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="37481-213">Verifique se o usuário de email está listado (ou não está listado).</span><span class="sxs-lookup"><span data-stu-id="37481-213">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="37481-214">Selecione o usuário de email e visualize as informações no painel de detalhes ou clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-AddIcon.png) para exibir as configurações.</span><span class="sxs-lookup"><span data-stu-id="37481-214">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="37481-215">Em EOP autônomo do PowerShell, execute o seguinte comando para verificar se o usuário de email está listado (ou não está listado):</span><span class="sxs-lookup"><span data-stu-id="37481-215">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="37481-216">Substitua \<MailUserIdentity\> pelo nome, alias ou nome da conta do usuário de email e execute os seguintes comandos para verificar as configurações:</span><span class="sxs-lookup"><span data-stu-id="37481-216">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="37481-217">Utilizar a sincronização de diretórios para gerenciar usuários de email</span><span class="sxs-lookup"><span data-stu-id="37481-217">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="37481-218">No EOP autônomo, a sincronização de diretórios está disponível para clientes com o Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="37481-218">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="37481-219">Você pode sincronizar essas contas no Azure Active Directory (Azure AD), onde as cópias das contas são armazenadas na nuvem.</span><span class="sxs-lookup"><span data-stu-id="37481-219">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="37481-220">Ao sincronizar suas contas de usuário existentes com o Azure Active Directory, você pode exibir esses usuários no painel **destinatários** do centro de administração do Exchange (Eat) ou no PowerShell do EOP autônomo.</span><span class="sxs-lookup"><span data-stu-id="37481-220">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="37481-221">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="37481-221">**Notes**:</span></span>

- <span data-ttu-id="37481-222">Se você usar a sincronização de diretório para gerenciar seus destinatários, ainda poderá adicionar e gerenciar usuários no centro de administração do Microsoft 365, mas eles não serão sincronizados com o Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="37481-222">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="37481-223">Isso porque a sincronização de diretórios sincroniza apenas destinatários de seu Active Directory local com a nuvem.</span><span class="sxs-lookup"><span data-stu-id="37481-223">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="37481-224">A sincronização de diretório é recomendada para uso com os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="37481-224">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="37481-225">Listas **de remetentes seguros do Outlook e listas de remetentes bloqueados**: quando sincronizado com o serviço, essas listas terão precedência sobre a filtragem de spam no serviço.</span><span class="sxs-lookup"><span data-stu-id="37481-225">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="37481-226">Isso permite que os usuários gerenciem sua própria lista de remetentes confiáveis e a lista de remetentes bloqueados com entradas de domínio e remetentes individuais.</span><span class="sxs-lookup"><span data-stu-id="37481-226">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="37481-227">Para obter mais informações, confira [Definir as configurações de lixo eletrônico nas caixas de correio do Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="37481-227">For more information, see [Configure junk email settings on Exchange Online mailboxes](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes).</span></span>

  - <span data-ttu-id="37481-228">**Bloqueio de borda baseado em diretório (DBEB)**: para obter mais informações sobre o DBEB, confira [usar o bloqueio de borda baseado em diretório para rejeitar mensagens enviadas a destinatários inválidos](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span><span class="sxs-lookup"><span data-stu-id="37481-228">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="37481-229">**Acesso de usuário final à quarentena**: para acessar suas mensagens em quarentena, os destinatários devem ter uma ID de usuário e senha válidas no serviço.</span><span class="sxs-lookup"><span data-stu-id="37481-229">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="37481-230">Para obter mais informações sobre quarentena, consulte [Localizar e liberar mensagens em quarentena como um usuário](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user).</span><span class="sxs-lookup"><span data-stu-id="37481-230">For more information about quarantine, see [Find and release quarantined messages as a user](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user).</span></span>

  - <span data-ttu-id="37481-231">**Regras de fluxo de emails (também conhecidas como regras de transporte)**: quando você usa a sincronização de diretório, os usuários e grupos existentes do Active Directory são carregados automaticamente para a nuvem e você pode criar regras de fluxo de email que se destinam a usuários e/ou grupos específicos sem precisar adicioná-los manualmente no serviço.</span><span class="sxs-lookup"><span data-stu-id="37481-231">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="37481-232">Observe que os [grupos dinâmicos de distribuição](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) não podem ser sincronizados através da sincronização de diretório.</span><span class="sxs-lookup"><span data-stu-id="37481-232">Note that [dynamic distribution groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="37481-233">Obtenha as permissões necessárias e prepare-se para a sincronização de diretório, conforme descrito em [o que é a identidade híbrida com o Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span><span class="sxs-lookup"><span data-stu-id="37481-233">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="37481-234">Sincronizar diretórios com o Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="37481-234">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="37481-235">Ative a sincronização de diretórios, conforme descrito na [sincronização do Azure ad Connect: compreender e personalizar a sincronização](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span><span class="sxs-lookup"><span data-stu-id="37481-235">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="37481-236">Instale e configure um computador local para executar o AAD Connect conforme descrito em [pré-requisitos para o Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span><span class="sxs-lookup"><span data-stu-id="37481-236">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="37481-237">[Selecione o tipo de instalação a ser usado para o Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span><span class="sxs-lookup"><span data-stu-id="37481-237">[Select which installation type to use for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="37481-238">Express</span><span class="sxs-lookup"><span data-stu-id="37481-238">Express</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="37481-239">Personalizados</span><span class="sxs-lookup"><span data-stu-id="37481-239">Custom</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="37481-240">Autenticação de passagem</span><span class="sxs-lookup"><span data-stu-id="37481-240">Pass-through authentication</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="37481-p121">Após a conclusão do Assistente de Configuração da Ferramenta de Sincronização do Microsoft Azure Active Directory, a conta **MSOL_AD_SYNC** será criada em sua floresta do Active Directory. Esta conta é usada para ler e sincronizar suas informações do Active Directory local. Para que a sincronização de diretórios funcione corretamente, verifique se a porta TCP 443 em seu servidor de sincronização de diretórios local está aberta.</span><span class="sxs-lookup"><span data-stu-id="37481-p121">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="37481-244">Depois de configurar a sincronização, verifique se a conexão do AAD está sincronizando corretamente.</span><span class="sxs-lookup"><span data-stu-id="37481-244">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="37481-245">No EAC, vá para **Destinatários** \> **Contatos** e veja se a lista de usuários foi corretamente sincronizada com seu ambiente local.</span><span class="sxs-lookup"><span data-stu-id="37481-245">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>
