---
title: Gerenciar usuários de email no EOP autônomo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Saiba mais sobre como gerenciar usuários de email no Exchange Online Protection (EOP), incluindo o uso de sincronização de diretórios, EAC e PowerShell para gerenciar usuários.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 863bde5ef860ee980f768ddc085379180e6a71aa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910613"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="3c6f7-103">Gerenciar usuários de email no EOP autônomo</span><span class="sxs-lookup"><span data-stu-id="3c6f7-103">Manage mail users in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3c6f7-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="3c6f7-104">**Applies to**</span></span>
-  [<span data-ttu-id="3c6f7-105">Proteção autônoma do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3c6f7-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="3c6f7-106">Em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, os usuários de email são o tipo fundamental de conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="3c6f7-107">Um usuário de email tem credenciais de conta em sua organização EOP autônoma e pode acessar recursos (tem permissões atribuídas).</span><span class="sxs-lookup"><span data-stu-id="3c6f7-107">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="3c6f7-108">O endereço de email de um usuário de email é externo (por exemplo, em seu ambiente de email local).</span><span class="sxs-lookup"><span data-stu-id="3c6f7-108">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="3c6f7-109">Quando você cria um usuário de email, a conta de usuário correspondente está disponível no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-109">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="3c6f7-110">Ao criar uma conta de usuário no Centro de administração do Microsoft 365, não é possível usar essa conta para criar um usuário de email.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-110">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="3c6f7-111">O método recomendado para criar e gerenciar usuários de email no EOP [](#use-directory-synchronization-to-manage-mail-users) autônomo é usar a sincronização de diretório conforme descrito na seção Usar sincronização de diretórios para gerenciar usuários de email posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-111">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this article.</span></span>

<span data-ttu-id="3c6f7-112">Para organizações EOP autônomas com um pequeno número de usuários, você pode adicionar e gerenciar usuários de email no Centro de administração do Exchange (EAC) ou no EOP PowerShell autônomo, conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-112">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3c6f7-113">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="3c6f7-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3c6f7-114">Para abrir o Centro de administração do Exchange (EAC), consulte Centro de administração [do Exchange no EOP](exchange-admin-center-in-exchange-online-protection-eop.md)autônomo .</span><span class="sxs-lookup"><span data-stu-id="3c6f7-114">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="3c6f7-115">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="3c6f7-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="3c6f7-116">Ao criar usuários de email no EOP PowerShell, você pode encontrar a throttling.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-116">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="3c6f7-117">Além disso, os cmdlets do EOP PowerShell usam um método de processamento em lote que resulta em um atraso de propagação de alguns minutos antes que os resultados dos comandos sejam visíveis.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-117">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="3c6f7-118">Você precisa ter permissões atribuídas no Exchange Online Protection antes de poder fazer os procedimentos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-118">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="3c6f7-119">Especificamente, você precisa das funções **Criação** de Destinatários de Email (criar) e Destinatários de Email  (modificar), que são **atribuídas** aos grupos de função Gerenciamento da Organização **(administradores** globais) e Gerenciamento de Destinatários por padrão.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-119">Specifically, you need the **Mail Recipient Creation** (create) and **Mail Recipients** (modify) roles, which are assigned to the **Organization Management** (global admins) and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="3c6f7-120">Para obter mais informações, consulte [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="3c6f7-120">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="3c6f7-121">Para obter informações sobre atalhos de teclado que podem se aplicar aos procedimentos neste artigo, consulte [Atalhos](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)de teclado para o centro de administração do Exchange no Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="3c6f7-121">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="3c6f7-122">Está com problemas?</span><span class="sxs-lookup"><span data-stu-id="3c6f7-122">Having problems?</span></span> <span data-ttu-id="3c6f7-123">Peça ajuda nos fóruns do Exchange.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-123">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="3c6f7-124">Visite o [fórum de Proteção do Exchange Online.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)</span><span class="sxs-lookup"><span data-stu-id="3c6f7-124">Visit the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="3c6f7-125">Usar o Centro de administração do Exchange para gerenciar usuários de email</span><span class="sxs-lookup"><span data-stu-id="3c6f7-125">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="3c6f7-126">Usar o EAC para criar usuários de email</span><span class="sxs-lookup"><span data-stu-id="3c6f7-126">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="3c6f7-127">No EAC, vá  para \> **Destinatários Contatos**</span><span class="sxs-lookup"><span data-stu-id="3c6f7-127">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="3c6f7-128">Clique **em Novo** Ícone ![ ](../../media/ITPro-EAC-AddIcon.png) novo.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-128">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="3c6f7-129">Na página **Novo usuário de email** que é aberta, configure as configurações a seguir.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-129">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="3c6f7-130">As configurações marcadas com <sup>\*</sup> um são necessárias.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-130">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="3c6f7-131">**Nome**</span><span class="sxs-lookup"><span data-stu-id="3c6f7-131">**First name**</span></span>

   - <span data-ttu-id="3c6f7-132">**Iniciais**: a inicial do meio da pessoa.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-132">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="3c6f7-133">**Sobrenome**</span><span class="sxs-lookup"><span data-stu-id="3c6f7-133">**Last name**</span></span>

   - <span data-ttu-id="3c6f7-134"><sup>\*</sup>**Nome para** exibição : Por padrão, esta caixa mostra os valores das caixas **Nome,** **Iniciais** e **Sobrenome.**</span><span class="sxs-lookup"><span data-stu-id="3c6f7-134"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="3c6f7-135">Você pode aceitar esse valor ou alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-135">You can accept this value or change it.</span></span> <span data-ttu-id="3c6f7-136">O valor deve ser exclusivo e tem um comprimento máximo de 64 caracteres.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-136">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="3c6f7-137"><sup>\*</sup>**Alias**: insira um alias exclusivo, usando até 64 caracteres, para o usuário</span><span class="sxs-lookup"><span data-stu-id="3c6f7-137"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="3c6f7-138">**Endereço de email externo**: Insira o endereço de email do usuário.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-138">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="3c6f7-139">O domínio deve ser externo à sua organização baseada em nuvem.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-139">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="3c6f7-140"><sup>\*</sup>**ID do** usuário : Insira a conta que a pessoa usará para entrar no serviço.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-140"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="3c6f7-141">A ID do usuário consiste em um nome de usuário no lado esquerdo do símbolo at (@) e um domínio no lado direito.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-141">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="3c6f7-142"><sup>\*</sup>**Nova senha e** <sup>\*</sup> **Confirmar senha**: Insira e insira novamente a senha da conta.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-142"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="3c6f7-143">Verifique se a senha está em conformidade com os requisitos de comprimento, complexidade e histórico de senha da sua organização.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-143">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="3c6f7-144">Quando tiver terminado, clique em **Salvar** para criar o usuário de email.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-144">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="3c6f7-145">Usar o EAC para modificar usuários de email</span><span class="sxs-lookup"><span data-stu-id="3c6f7-145">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="3c6f7-146">No EAC, acesse **Destinatários** \> **Contatos**.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-146">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="3c6f7-147">Selecione o usuário de email que você deseja modificar e clique em **Editar** ![ ícone ](../../media/ITPro-EAC-AddIcon.png) editar.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-147">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="3c6f7-148">Na página propriedades do usuário de email que é aberta, clique em uma das seguintes guias para exibir ou alterar propriedades.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-148">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="3c6f7-149">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-149">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="3c6f7-150">Geral</span><span class="sxs-lookup"><span data-stu-id="3c6f7-150">General</span></span>

<span data-ttu-id="3c6f7-151">Use a **guia Geral** para exibir ou alterar informações básicas sobre o usuário de email.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-151">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="3c6f7-152">**Nome**</span><span class="sxs-lookup"><span data-stu-id="3c6f7-152">**First name**</span></span>

- <span data-ttu-id="3c6f7-153">**Iniciais**</span><span class="sxs-lookup"><span data-stu-id="3c6f7-153">**Initials**</span></span>

- <span data-ttu-id="3c6f7-154">**Sobrenome**</span><span class="sxs-lookup"><span data-stu-id="3c6f7-154">**Last name**</span></span>

- <span data-ttu-id="3c6f7-155">**Nome para** exibição : esse nome aparece no livro de endereços da sua organização, nas linhas Para: e De: no email e na lista de contatos no EAC.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-155">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="3c6f7-156">Esse nome não pode conter espaços vazios antes ou depois do nome para exibição.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-156">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="3c6f7-157">**ID do** usuário: essa é a conta do usuário no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-157">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="3c6f7-158">Você não pode modificar esse valor aqui.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-158">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="3c6f7-159">Informações de contato</span><span class="sxs-lookup"><span data-stu-id="3c6f7-159">Contact information</span></span>

<span data-ttu-id="3c6f7-160">Use a **guia Informações de** contato para exibir ou alterar as informações de contato do usuário.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-160">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="3c6f7-161">As informações nesta página são exibidas no catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-161">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="3c6f7-162">**Street**</span><span class="sxs-lookup"><span data-stu-id="3c6f7-162">**Street**</span></span>
- <span data-ttu-id="3c6f7-163">**Cidade**</span><span class="sxs-lookup"><span data-stu-id="3c6f7-163">**City**</span></span>
- <span data-ttu-id="3c6f7-164">**Estado/Província**</span><span class="sxs-lookup"><span data-stu-id="3c6f7-164">**State/Province**</span></span>
- <span data-ttu-id="3c6f7-165">**CEP/Código postal**</span><span class="sxs-lookup"><span data-stu-id="3c6f7-165">**ZIP/Postal code**</span></span>
- <span data-ttu-id="3c6f7-166">**País/região**</span><span class="sxs-lookup"><span data-stu-id="3c6f7-166">**Country/Region**</span></span>
- <span data-ttu-id="3c6f7-167">**Telefone de trabalho**</span><span class="sxs-lookup"><span data-stu-id="3c6f7-167">**Work phone**</span></span>
- <span data-ttu-id="3c6f7-168">**Telefone celular**</span><span class="sxs-lookup"><span data-stu-id="3c6f7-168">**Mobile phone**</span></span>
- <span data-ttu-id="3c6f7-169">**Fax**</span><span class="sxs-lookup"><span data-stu-id="3c6f7-169">**Fax**</span></span>
- <span data-ttu-id="3c6f7-170">**Mais opções**</span><span class="sxs-lookup"><span data-stu-id="3c6f7-170">**More options**</span></span>

  - <span data-ttu-id="3c6f7-171">**Office**</span><span class="sxs-lookup"><span data-stu-id="3c6f7-171">**Office**</span></span>
  - <span data-ttu-id="3c6f7-172">**Telefone 1**</span><span class="sxs-lookup"><span data-stu-id="3c6f7-172">**Home phone**</span></span>
  - <span data-ttu-id="3c6f7-173">**Página da Web**</span><span class="sxs-lookup"><span data-stu-id="3c6f7-173">**Web page**</span></span>
  - <span data-ttu-id="3c6f7-174">**Anotações**</span><span class="sxs-lookup"><span data-stu-id="3c6f7-174">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="3c6f7-175">Organização</span><span class="sxs-lookup"><span data-stu-id="3c6f7-175">Organization</span></span>

<span data-ttu-id="3c6f7-176">Use a **guia Organização** para registrar informações detalhadas sobre a função do usuário na organização.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-176">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="3c6f7-177">**Título**</span><span class="sxs-lookup"><span data-stu-id="3c6f7-177">**Title**</span></span>
- <span data-ttu-id="3c6f7-178">**Departamento**</span><span class="sxs-lookup"><span data-stu-id="3c6f7-178">**Department**</span></span>
- <span data-ttu-id="3c6f7-179">**Company**</span><span class="sxs-lookup"><span data-stu-id="3c6f7-179">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="3c6f7-180">Usar o EAC para remover usuários de email</span><span class="sxs-lookup"><span data-stu-id="3c6f7-180">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="3c6f7-181">No EAC, acesse **Destinatários** \> **Contatos**.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-181">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="3c6f7-182">Selecione o usuário de email que você deseja remover e clique em **Remover** ![ ícone ](../../media/ITPro-EAC-RemoveIcon.gif) Remover.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-182">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="3c6f7-183">Usar o PowerShell para gerenciar usuários de email</span><span class="sxs-lookup"><span data-stu-id="3c6f7-183">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="3c6f7-184">Usar o EOP PowerShell autônomo para exibir usuários de email</span><span class="sxs-lookup"><span data-stu-id="3c6f7-184">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="3c6f7-185">Para retornar uma lista resumida de todos os usuários de email no EOP PowerShell autônomo, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3c6f7-185">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="3c6f7-186">Para exibir informações detalhadas sobre um usuário de email específico, substitua pelo nome, alias ou nome da conta do usuário de email e execute \<MailUserIdentity\> os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="3c6f7-186">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="3c6f7-187">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-Recipient](/powershell/module/exchange/get-recipient) e [Get-User](/powershell/module/exchange/get-user).</span><span class="sxs-lookup"><span data-stu-id="3c6f7-187">For detailed syntax and parameter information, see [Get-Recipient](/powershell/module/exchange/get-recipient) and [Get-User](/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="3c6f7-188">Usar o EOP PowerShell autônomo para criar usuários de email</span><span class="sxs-lookup"><span data-stu-id="3c6f7-188">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="3c6f7-189">Para criar usuários de email no EOP PowerShell autônomo, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="3c6f7-189">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="3c6f7-190">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="3c6f7-190">**Notes**:</span></span>

- <span data-ttu-id="3c6f7-191">O _parâmetro Name_ é necessário, tem um comprimento máximo de 64 caracteres e deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-191">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="3c6f7-192">Se você não usa o parâmetro _DisplayName_, o valor do parâmetro _Name_ é usado para o nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-192">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="3c6f7-193">Se você não usar o parâmetro _Alias,_ o lado esquerdo do _parâmetro MicrosoftOnlineServicesID_ será usado para o alias.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-193">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlineServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="3c6f7-194">Se você não usar o parâmetro _ExternalEmailAddress,_ o _valor MicrosoftOnlineServicesID_ será usado para o endereço de email externo.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-194">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="3c6f7-195">Este exemplo cria um usuário de email com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="3c6f7-195">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="3c6f7-196">O nome é JeffreyZeng e o nome de exibição é Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-196">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="3c6f7-197">O primeiro nome é Diogo e o sobrenome é Martins.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-197">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="3c6f7-198">O alias é diogom.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-198">The alias is jeffreyz.</span></span>
- <span data-ttu-id="3c6f7-199">O endereço de email externo é diogom@tailspintoys.com.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-199">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="3c6f7-200">O nome da conta é jeffreyz@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-200">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="3c6f7-201">A senha é Pa$$word1.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-201">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="3c6f7-202">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-EOPMailUser](/powershell/module/exchange/new-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="3c6f7-202">For detailed syntax and parameter information, see [New-EOPMailUser](/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="3c6f7-203">Usar o EOP PowerShell autônomo para modificar usuários de email</span><span class="sxs-lookup"><span data-stu-id="3c6f7-203">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="3c6f7-204">Para modificar os usuários de email existentes no EOP PowerShell autônomo, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="3c6f7-204">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="3c6f7-205">Este exemplo define o endereço de email externo de Brenda Fernandes.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-205">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="3c6f7-206">Este exemplo define a propriedade Company de todos os usuários de email como Contoso.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-206">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="3c6f7-207">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-EOPMailUser](/powershell/module/exchange/set-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="3c6f7-207">For detailed syntax and parameter information, see [Set-EOPMailUser](/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="3c6f7-208">Usar o EOP PowerShell autônomo para remover usuários de email</span><span class="sxs-lookup"><span data-stu-id="3c6f7-208">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="3c6f7-209">Para remover usuários de email no EOP PowerShell autônomo, substitua pelo nome, alias ou nome da conta do usuário de email e execute \<MailUserIdentity\> o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3c6f7-209">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="3c6f7-210">Este exemplo remove o usuário de email de Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-210">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="3c6f7-211">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-EOPMailUser](/powershell/module/exchange/remove-eopmailuser).</span><span class="sxs-lookup"><span data-stu-id="3c6f7-211">For detailed syntax and parameter information, see [Remove-EOPMailUser](/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="3c6f7-212">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="3c6f7-212">How do you know these procedures worked?</span></span>

<span data-ttu-id="3c6f7-213">Para verificar se você criou, modificou ou removeu usuários de email com êxito no EOP autônomo, use qualquer um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="3c6f7-213">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="3c6f7-214">No EAC, acesse **Destinatários** \> **Contatos**.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-214">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="3c6f7-215">Verifique se o usuário de email está listado (ou não está listado).</span><span class="sxs-lookup"><span data-stu-id="3c6f7-215">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="3c6f7-216">Selecione o usuário de email e exibir as informações no painel Detalhes ou clique em **Editar** ![ ícone editar para exibir as ](../../media/ITPro-EAC-AddIcon.png) configurações.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-216">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="3c6f7-217">No EOP PowerShell autônomo, execute o seguinte comando para verificar se o usuário de email está listado (ou não está listado):</span><span class="sxs-lookup"><span data-stu-id="3c6f7-217">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="3c6f7-218">Substitua pelo nome, alias ou nome da conta do usuário de email e execute os seguintes comandos \<MailUserIdentity\> para verificar as configurações:</span><span class="sxs-lookup"><span data-stu-id="3c6f7-218">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="3c6f7-219">Utilizar a sincronização de diretórios para gerenciar usuários de email</span><span class="sxs-lookup"><span data-stu-id="3c6f7-219">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="3c6f7-220">No EOP autônomo, a sincronização de diretórios está disponível para clientes com o Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-220">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="3c6f7-221">Você pode sincronizar essas contas com o Azure Active Directory (Azure AD), onde cópias das contas são armazenadas na nuvem.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-221">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="3c6f7-222">Ao sincronizar suas contas de usuário existentes com o Azure Active Directory, você pode exibir esses usuários no painel **Destinatários** do Centro de administração do Exchange (EAC) ou no EOP PowerShell autônomo.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-222">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="3c6f7-223">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="3c6f7-223">**Notes**:</span></span>

- <span data-ttu-id="3c6f7-224">Se você usar a sincronização de diretórios para gerenciar seus destinatários, ainda poderá adicionar e gerenciar usuários no Centro de administração do Microsoft 365, mas eles não serão sincronizados com o Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-224">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="3c6f7-225">Isso porque a sincronização de diretórios sincroniza apenas destinatários de seu Active Directory local com a nuvem.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-225">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="3c6f7-226">A sincronização de diretório é recomendada para uso com os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="3c6f7-226">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="3c6f7-227">**Listas de remetentes** seguros do Outlook e listas de Remetentes Bloqueados : Quando sincronizadas com o serviço, essas listas terão precedência sobre a filtragem de spam no serviço.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-227">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="3c6f7-228">Isso permite que os usuários gerenciem sua própria lista de Remetentes Seguros e Lista de Remetentes Bloqueados com entradas individuais de remetente e domínio.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-228">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="3c6f7-229">Para obter mais informações, confira [Definir as configurações de lixo eletrônico nas caixas de correio do Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="3c6f7-229">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="3c6f7-230">Bloqueio de Borda Com Base em Diretório **(DBEB)**: Para obter mais informações sobre DBEB, consulte Use Directory Based Edge Blocking to reject messages sent [to invalid recipients](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span><span class="sxs-lookup"><span data-stu-id="3c6f7-230">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="3c6f7-231">**Acesso do usuário final à quarentena**: Para acessar suas mensagens em quarentena, os destinatários devem ter uma ID de usuário e uma senha válidas no serviço.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-231">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="3c6f7-232">Para obter mais informações sobre a quarentena, [consulte Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="3c6f7-232">For more information about quarantine, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  - <span data-ttu-id="3c6f7-233">Regras de fluxo de emails (também conhecidas como regras de **transporte)**: quando você usa a sincronização de diretórios, os usuários e grupos existentes do Active Directory são carregados automaticamente na nuvem e você pode criar regras de fluxo de emails que direcionam usuários específicos e/ou grupos sem precisar adicioná-los manualmente no serviço.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-233">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="3c6f7-234">Observe que os [grupos dinâmicos de distribuição](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) não podem ser sincronizados através da sincronização de diretório.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-234">Note that [dynamic distribution groups](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="3c6f7-235">Obter as permissões necessárias e preparar-se para a sincronização de diretórios, conforme descrito em O que é a identidade híbrida com o [Azure Active Directory?](/azure/active-directory/hybrid/whatis-hybrid-identity).</span><span class="sxs-lookup"><span data-stu-id="3c6f7-235">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="3c6f7-236">Sincronizar diretórios com o Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="3c6f7-236">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="3c6f7-237">Ativar a sincronização de diretório conforme descrito na sincronização [do Azure AD Connect: Compreender e personalizar a sincronização](/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span><span class="sxs-lookup"><span data-stu-id="3c6f7-237">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="3c6f7-238">Instalar e configurar um computador local para executar o AAD Connect conforme descrito em [Pré-requisitos para o Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span><span class="sxs-lookup"><span data-stu-id="3c6f7-238">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="3c6f7-239">[Selecione o tipo de instalação a ser usado para o Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span><span class="sxs-lookup"><span data-stu-id="3c6f7-239">[Select which installation type to use for Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="3c6f7-240">Express</span><span class="sxs-lookup"><span data-stu-id="3c6f7-240">Express</span></span>](/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="3c6f7-241">Personalizados</span><span class="sxs-lookup"><span data-stu-id="3c6f7-241">Custom</span></span>](/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="3c6f7-242">Autenticação de passagem</span><span class="sxs-lookup"><span data-stu-id="3c6f7-242">Pass-through authentication</span></span>](/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="3c6f7-p121">Após a conclusão do Assistente de Configuração da Ferramenta de Sincronização do Microsoft Azure Active Directory, a conta **MSOL_AD_SYNC** será criada em sua floresta do Active Directory. Esta conta é usada para ler e sincronizar suas informações do Active Directory local. Para que a sincronização de diretórios funcione corretamente, verifique se a porta TCP 443 em seu servidor de sincronização de diretórios local está aberta.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-p121">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="3c6f7-246">Depois de configurar sua sincronização, verifique se o AAD Connect está sincronizando corretamente.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-246">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="3c6f7-247">No EAC, vá para **Destinatários** \> **Contatos** e veja se a lista de usuários foi corretamente sincronizada com seu ambiente local.</span><span class="sxs-lookup"><span data-stu-id="3c6f7-247">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>