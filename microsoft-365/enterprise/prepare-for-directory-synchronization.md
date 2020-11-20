---
title: Preparar-se para a sincronização de diretórios com o Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Descreve como se preparar para provisionar usuários para a Microsoft 365 usando a sincronização de diretórios e os benefícios de longo prazo de usar esse método.
ms.openlocfilehash: e49cc4472b47320650d8a0ca90395b69ae5b6df7
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371619"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a><span data-ttu-id="9bfbf-103">Preparar-se para a sincronização de diretórios com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9bfbf-103">Prepare for directory synchronization to Microsoft 365</span></span>

<span data-ttu-id="9bfbf-104">*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="9bfbf-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9bfbf-105">Os benefícios para a identidade híbrida e a sincronização de diretórios que a organização incluem:</span><span class="sxs-lookup"><span data-stu-id="9bfbf-105">The benefits to hybrid identity and directory synchronization your organization include:</span></span>

- <span data-ttu-id="9bfbf-106">Reduzindo os programas administrativos em sua organização</span><span class="sxs-lookup"><span data-stu-id="9bfbf-106">Reducing the administrative programs in your organization</span></span>
- <span data-ttu-id="9bfbf-107">Opcionalmente, habilitando o cenário de logon único</span><span class="sxs-lookup"><span data-stu-id="9bfbf-107">Optionally enabling single sign-on scenario</span></span>
- <span data-ttu-id="9bfbf-108">Automatizar alterações de conta no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9bfbf-108">Automating account changes in Microsoft 365</span></span>

<span data-ttu-id="9bfbf-109">Para obter mais informações sobre as vantagens de usar a sincronização de diretório, consulte [identidade híbrida com Azure Active Directory (Azure AD)](https://go.microsoft.com/fwlink/p/?LinkId=525398) e [identidade híbrida do Microsoft 365](plan-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="9bfbf-109">For more information about the advantages of using directory synchronization, see [hybrid identity with Azure Active Directory (Azure AD)](https://go.microsoft.com/fwlink/p/?LinkId=525398) and [hybrid identity for Microsoft 365](plan-for-directory-synchronization.md).</span></span>

<span data-ttu-id="9bfbf-110">No entanto, a sincronização de diretórios requer planejamento e preparação para garantir que os serviços de domínio do Active Directory (AD DS) sincronizem o locatário do Azure AD da sua assinatura do Microsoft 365 com um mínimo de erros.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-110">However, directory synchronization requires planning and preparation to ensure that your Active Directory Domain Services (AD DS) synchronizes to the Azure AD tenant of your Microsoft 365 subscription with a minimum of errors.</span></span>

<span data-ttu-id="9bfbf-111">Siga estas etapas para obter os melhores resultados.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-111">Follow these steps in order for the best results.</span></span>

## <a name="1-directory-cleanup-tasks"></a><span data-ttu-id="9bfbf-112">1. tarefas de limpeza de diretório</span><span class="sxs-lookup"><span data-stu-id="9bfbf-112">1. Directory cleanup tasks</span></span>

<span data-ttu-id="9bfbf-113">Antes de sincronizar o AD DS com seu locatário do Azure AD, você precisa limpar o AD DS.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-113">Before you synchronize your AD DS to your Azure AD tenant, you need to clean up your AD DS.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9bfbf-114">Se você não executar a limpeza do AD DS antes de sincronizar, ela pode levar a um impacto negativo significativo no processo de implantação.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-114">If you don't perform AD DS cleanup before you synchronize, it can lead to a significant negative impact on the deployment process.</span></span> <span data-ttu-id="9bfbf-115">Pode levar dias ou até mesmo semanas para passar pelo ciclo de sincronização de diretórios, identificar erros e ressincronizar.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-115">It might take days, or even weeks, to go through the cycle of directory synchronization, identifying errors, and re-synchronization.</span></span>

<span data-ttu-id="9bfbf-116">No AD DS, conclua as seguintes tarefas de limpeza para cada conta de usuário à qual será atribuída uma licença da Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="9bfbf-116">In your AD DS, complete the following clean-up tasks for each user account that will be assigned a Microsoft 365 license:</span></span>

1. <span data-ttu-id="9bfbf-117">Verifique se um endereço de email válido e exclusivo no atributo **proxyAddresses** .</span><span class="sxs-lookup"><span data-stu-id="9bfbf-117">Ensure a valid and unique email address in the **proxyAddresses** attribute.</span></span>

2. <span data-ttu-id="9bfbf-118">Remova os valores duplicados no atributo **proxyAddresses** .</span><span class="sxs-lookup"><span data-stu-id="9bfbf-118">Remove any duplicate values in the **proxyAddresses** attribute.</span></span>

3. <span data-ttu-id="9bfbf-119">Se possível, assegure um valor válido e exclusivo para o atributo **userPrincipalName** no objeto **User** do usuário.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-119">If possible, ensure a valid and unique value for the **userPrincipalName** attribute in the user's **user** object.</span></span> <span data-ttu-id="9bfbf-120">Para obter a melhor experiência de sincronização, verifique se o UPN do AD DS corresponde ao UPN do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-120">For the best synchronization experience, ensure that the AD DS UPN matches the Azure AD UPN.</span></span> <span data-ttu-id="9bfbf-121">Se um usuário não tiver um valor para o atributo **userPrincipalName** , o objeto de **usuário** deverá conter um valor válido e exclusivo para o atributo **sAMAccountName** .</span><span class="sxs-lookup"><span data-stu-id="9bfbf-121">If a user does not have a value for the **userPrincipalName** attribute, then the **user** object must contain a valid and unique value for the **sAMAccountName** attribute.</span></span> <span data-ttu-id="9bfbf-122">Remova os valores duplicados no atributo **userPrincipalName** .</span><span class="sxs-lookup"><span data-stu-id="9bfbf-122">Remove any duplicate values in the **userPrincipalName** attribute.</span></span>

4. <span data-ttu-id="9bfbf-123">Para o uso ideal da GAL (lista de endereços global), verifique se as informações nos seguintes atributos da conta de usuário do AD DS estão corretas:</span><span class="sxs-lookup"><span data-stu-id="9bfbf-123">For optimal use of the global address list (GAL), ensure the information in the following attributes of the AD DS user account is correct:</span></span>

   - <span data-ttu-id="9bfbf-124">givenName</span><span class="sxs-lookup"><span data-stu-id="9bfbf-124">givenName</span></span>
   - <span data-ttu-id="9bfbf-125">surname</span><span class="sxs-lookup"><span data-stu-id="9bfbf-125">surname</span></span>
   - <span data-ttu-id="9bfbf-126">displayName</span><span class="sxs-lookup"><span data-stu-id="9bfbf-126">displayName</span></span>
   - <span data-ttu-id="9bfbf-127">Cargo</span><span class="sxs-lookup"><span data-stu-id="9bfbf-127">Job Title</span></span>
   - <span data-ttu-id="9bfbf-128">Departamento</span><span class="sxs-lookup"><span data-stu-id="9bfbf-128">Department</span></span>
   - <span data-ttu-id="9bfbf-129">Escritório</span><span class="sxs-lookup"><span data-stu-id="9bfbf-129">Office</span></span>
   - <span data-ttu-id="9bfbf-130">Telefone comercial</span><span class="sxs-lookup"><span data-stu-id="9bfbf-130">Office Phone</span></span>
   - <span data-ttu-id="9bfbf-131">Telefone celular</span><span class="sxs-lookup"><span data-stu-id="9bfbf-131">Mobile Phone</span></span>
   - <span data-ttu-id="9bfbf-132">Número do fax</span><span class="sxs-lookup"><span data-stu-id="9bfbf-132">Fax Number</span></span>
   - <span data-ttu-id="9bfbf-133">Endereço</span><span class="sxs-lookup"><span data-stu-id="9bfbf-133">Street Address</span></span>
   - <span data-ttu-id="9bfbf-134">Cidade</span><span class="sxs-lookup"><span data-stu-id="9bfbf-134">City</span></span>
   - <span data-ttu-id="9bfbf-135">Estado</span><span class="sxs-lookup"><span data-stu-id="9bfbf-135">State or Province</span></span>
   - <span data-ttu-id="9bfbf-136">CEP</span><span class="sxs-lookup"><span data-stu-id="9bfbf-136">Zip or Postal Code</span></span>
   - <span data-ttu-id="9bfbf-137">País</span><span class="sxs-lookup"><span data-stu-id="9bfbf-137">Country or Region</span></span>

## <a name="2-directory-object-and-attribute-preparation"></a><span data-ttu-id="9bfbf-138">2. preparação de objeto e atributo de diretório</span><span class="sxs-lookup"><span data-stu-id="9bfbf-138">2. Directory object and attribute preparation</span></span>

<span data-ttu-id="9bfbf-139">A sincronização de diretório com êxito entre seu AD DS e o Microsoft 365 requer que seus atributos do AD DS sejam preparados adequadamente.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-139">Successful directory synchronization between your AD DS and Microsoft 365 requires that your AD DS attributes are properly prepared.</span></span> <span data-ttu-id="9bfbf-140">Por exemplo, você precisa garantir que caracteres específicos não sejam usados em determinados atributos que são sincronizados com o ambiente do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-140">For example, you need to ensure that specific characters aren't used in certain attributes that are synchronized with the Microsoft 365 environment.</span></span> <span data-ttu-id="9bfbf-141">Caracteres inesperados não causam a sincronização de diretório, mas podem retornar um aviso.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-141">Unexpected characters do not cause directory synchronization to fail but might return a warning.</span></span> <span data-ttu-id="9bfbf-142">Caracteres inválidos causarão falha na sincronização do diretório.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-142">Invalid characters will cause directory synchronization to fail.</span></span>

<span data-ttu-id="9bfbf-143">A sincronização de diretórios também falhará se alguns dos seus usuários do AD DS tiverem um ou mais atributos duplicados.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-143">Directory synchronization will also fail if some of your AD DS users have one or more duplicate attributes.</span></span> <span data-ttu-id="9bfbf-144">Cada usuário deve ter atributos exclusivos.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-144">Each user must have unique attributes.</span></span>

<span data-ttu-id="9bfbf-145">Os atributos que você precisa preparar estão listados aqui:</span><span class="sxs-lookup"><span data-stu-id="9bfbf-145">The attributes that you need to prepare are listed here:</span></span>

- <span data-ttu-id="9bfbf-146">**displayName**</span><span class="sxs-lookup"><span data-stu-id="9bfbf-146">**displayName**</span></span>

  - <span data-ttu-id="9bfbf-147">Se o atributo existir no objeto do usuário, ele será sincronizado com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-147">If the attribute exists in the user object, it will be synchronized with Microsoft 365.</span></span>
  - <span data-ttu-id="9bfbf-148">Se esse atributo existir no objeto user, deverá haver um valor para ele.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-148">If this attribute exists in the user object, there must be a value for it.</span></span> <span data-ttu-id="9bfbf-149">Ou seja, o atributo não deve estar em branco.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-149">That is, the attribute must not be blank.</span></span>
  - <span data-ttu-id="9bfbf-150">Número máximo de caracteres: 256</span><span class="sxs-lookup"><span data-stu-id="9bfbf-150">Maximum number of characters: 256</span></span>

- <span data-ttu-id="9bfbf-151">**givenName**</span><span class="sxs-lookup"><span data-stu-id="9bfbf-151">**givenName**</span></span>

  - <span data-ttu-id="9bfbf-152">Se o atributo existir no objeto do usuário, ele será sincronizado com o Microsoft 365, mas a Microsoft 365 não o exigirá ou o usará.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-152">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>
  - <span data-ttu-id="9bfbf-153">Número máximo de caracteres: 64</span><span class="sxs-lookup"><span data-stu-id="9bfbf-153">Maximum number of characters: 64</span></span>

- <span data-ttu-id="9bfbf-154">**mala**</span><span class="sxs-lookup"><span data-stu-id="9bfbf-154">**mail**</span></span>

  - <span data-ttu-id="9bfbf-155">O valor do atributo deve ser exclusivo no diretório.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-155">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9bfbf-156">Se houver valores duplicados, o primeiro usuário com o valor será sincronizado.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-156">If there are duplicate values, the first user with the value is synchronized.</span></span> <span data-ttu-id="9bfbf-157">Os usuários subsequentes não aparecerão no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-157">Subsequent users will not appear in Microsoft 365.</span></span> <span data-ttu-id="9bfbf-158">Você deve modificar o valor no Microsoft 365 ou modificar os dois valores no AD DS para que ambos os usuários sejam exibidos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-158">You must modify either the value in Microsoft 365 or modify both of the values in AD DS in order for both users to appear in Microsoft 365.</span></span>

- <span data-ttu-id="9bfbf-159">**mailNickname** (alias do Exchange)</span><span class="sxs-lookup"><span data-stu-id="9bfbf-159">**mailNickname** (Exchange alias)</span></span>

  - <span data-ttu-id="9bfbf-160">O valor do atributo não pode começar com um ponto (.).</span><span class="sxs-lookup"><span data-stu-id="9bfbf-160">The attribute value cannot begin with a period (.).</span></span>
  - <span data-ttu-id="9bfbf-161">O valor do atributo deve ser exclusivo no diretório.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-161">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9bfbf-162">Sublinhados ("_") no nome sincronizado indica que o valor original desse atributo contém caracteres inválidos.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-162">Underscores ("_") in the synchronized name indicates that the original value of this attribute contains invalid characters.</span></span> <span data-ttu-id="9bfbf-163">Para obter mais informações sobre este atributo, consulte [atributo de alias do Exchange](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="9bfbf-163">For more information on this attribute, see [Exchange alias attribute](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).</span></span>
    >

- <span data-ttu-id="9bfbf-164">**proxyAddresses**</span><span class="sxs-lookup"><span data-stu-id="9bfbf-164">**proxyAddresses**</span></span>

  - <span data-ttu-id="9bfbf-165">Atributo de vários valores</span><span class="sxs-lookup"><span data-stu-id="9bfbf-165">Multiple-value attribute</span></span>
  - <span data-ttu-id="9bfbf-166">Número máximo de caracteres por valor: 256</span><span class="sxs-lookup"><span data-stu-id="9bfbf-166">Maximum number of characters per value: 256</span></span>
  - <span data-ttu-id="9bfbf-167">O valor do atributo não deve conter um espaço.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-167">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="9bfbf-168">O valor do atributo deve ser exclusivo no diretório.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-168">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="9bfbf-169">Caracteres inválidos: \< \> ();, [] "'</span><span class="sxs-lookup"><span data-stu-id="9bfbf-169">Invalid characters: \< \> ( ) ; , [ ] " '</span></span>

    <span data-ttu-id="9bfbf-170">Observe que os caracteres inválidos se aplicam aos caracteres após o delimitador de tipo e ":", de modo que SMTP:User@contso.com seja permitido, mas SMTP:user:M@contoso.com não.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-170">Note that the invalid characters apply to the characters following the type delimiter and ":", such that SMTP:User@contso.com is allowed, but SMTP:user:M@contoso.com is not.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9bfbf-171">Todos os endereços SMTP (Simple Mail Transport Protocol) devem estar em conformidade com os padrões de mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-171">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span> <span data-ttu-id="9bfbf-172">Remova endereços duplicados ou indesejados se existirem.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-172">Remove duplicate or unwanted addresses if they exist.</span></span>

- <span data-ttu-id="9bfbf-173">**sAMAccountName**</span><span class="sxs-lookup"><span data-stu-id="9bfbf-173">**sAMAccountName**</span></span>

  - <span data-ttu-id="9bfbf-174">Número máximo de caracteres: 20</span><span class="sxs-lookup"><span data-stu-id="9bfbf-174">Maximum number of characters: 20</span></span>
  - <span data-ttu-id="9bfbf-175">O valor do atributo deve ser exclusivo no diretório.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-175">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="9bfbf-176">Caracteres inválidos: [\ "|,/: \< \> + =;?</span><span class="sxs-lookup"><span data-stu-id="9bfbf-176">Invalid characters: [ \ " | , / : \< \> + = ; ?</span></span> <span data-ttu-id="9bfbf-177">\* ']</span><span class="sxs-lookup"><span data-stu-id="9bfbf-177">\* ']</span></span>
  - <span data-ttu-id="9bfbf-178">Se um usuário tiver um atributo **sAMAccountName** inválido, mas tiver um atributo **userPrincipalName** válido, a conta do usuário será criada no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-178">If a user has an invalid **sAMAccountName** attribute but has a valid **userPrincipalName** attribute, the user account is created in Microsoft 365.</span></span>
  - <span data-ttu-id="9bfbf-179">Se **sAMAccountName** e **userPrincipalName** forem inválidos, o atributo **userPrincipalName** do AD DS deverá ser atualizado.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-179">If both **sAMAccountName** and **userPrincipalName** are invalid, the AD DS **userPrincipalName** attribute must be updated.</span></span>

- <span data-ttu-id="9bfbf-180">**SN** (sobrenome)</span><span class="sxs-lookup"><span data-stu-id="9bfbf-180">**sn** (surname)</span></span>

  - <span data-ttu-id="9bfbf-181">Se o atributo existir no objeto do usuário, ele será sincronizado com o Microsoft 365, mas a Microsoft 365 não o exigirá ou o usará.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-181">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>

- <span data-ttu-id="9bfbf-182">**targetAddress**</span><span class="sxs-lookup"><span data-stu-id="9bfbf-182">**targetAddress**</span></span>

    <span data-ttu-id="9bfbf-183">É necessário que o atributo **targetAddress** (por exemplo, SMTP:Tom@contoso.com) preenchido para o usuário seja exibido na GAL 365 da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-183">It's required that the **targetAddress** attribute (for example, SMTP:tom@contoso.com) that's populated for the user must appear in the Microsoft 365 GAL.</span></span> <span data-ttu-id="9bfbf-184">Em cenários de migração de mensagens de terceiros, isso exigiria a extensão de esquema do Microsoft 365 para o AD DS.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-184">In third-party messaging migration scenarios, this would require the Microsoft 365 schema extension for the AD DS.</span></span> <span data-ttu-id="9bfbf-185">A extensão de esquema do Microsoft 365 também adiciona outros atributos úteis para gerenciar os objetos do Microsoft 365 que são preenchidos usando uma ferramenta de sincronização de diretório do AD DS.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-185">The Microsoft 365 schema extension would also add other useful attributes to manage Microsoft 365 objects that are populated by using a directory synchronization tool from AD DS.</span></span> <span data-ttu-id="9bfbf-186">Por exemplo, o atributo **msExchHideFromAddressLists** para gerenciar caixas de correio ou grupos de distribuição ocultos seria adicionado.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-186">For example, the **msExchHideFromAddressLists** attribute to manage hidden mailboxes or distribution groups would be added.</span></span>

  - <span data-ttu-id="9bfbf-187">Número máximo de caracteres: 256</span><span class="sxs-lookup"><span data-stu-id="9bfbf-187">Maximum number of characters: 256</span></span>
  - <span data-ttu-id="9bfbf-188">O valor do atributo não deve conter um espaço.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-188">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="9bfbf-189">O valor do atributo deve ser exclusivo no diretório.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-189">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="9bfbf-190">Caracteres inválidos: \ \< \> ();, [] "</span><span class="sxs-lookup"><span data-stu-id="9bfbf-190">Invalid characters: \ \< \> ( ) ; , [ ] "</span></span>
  - <span data-ttu-id="9bfbf-191">Todos os endereços SMTP (Simple Mail Transport Protocol) devem estar em conformidade com os padrões de mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-191">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>

- <span data-ttu-id="9bfbf-192">**userPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="9bfbf-192">**userPrincipalName**</span></span>

  - <span data-ttu-id="9bfbf-193">O atributo **userPrincipalName** deve estar no formato de entrada no estilo da Internet, onde o nome do usuário é seguido pelo sinal de arroba (@) e um nome de domínio: por exemplo, User@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-193">The **userPrincipalName** attribute must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name: for example, user@contoso.com.</span></span> <span data-ttu-id="9bfbf-194">Todos os endereços SMTP (Simple Mail Transport Protocol) devem estar em conformidade com os padrões de mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-194">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>
  - <span data-ttu-id="9bfbf-195">O número máximo de caracteres para o atributo **userPrincipalName** é 113.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-195">The maximum number of characters for the **userPrincipalName** attribute is 113.</span></span> <span data-ttu-id="9bfbf-196">Um número específico de caracteres é permitido antes e depois do sinal de arroba (@), da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="9bfbf-196">A specific number of characters are permitted before and after the at sign (@), as follows:</span></span>
  - <span data-ttu-id="9bfbf-197">Número máximo de caracteres para o nome de usuário que está na frente do sinal de arroba (@): 64</span><span class="sxs-lookup"><span data-stu-id="9bfbf-197">Maximum number of characters for the username that is in front of the at sign (@): 64</span></span>
  - <span data-ttu-id="9bfbf-198">Número máximo de caracteres para o nome de domínio após o sinal de arroba (@): 48</span><span class="sxs-lookup"><span data-stu-id="9bfbf-198">Maximum number of characters for the domain name following the at sign (@): 48</span></span>
  - <span data-ttu-id="9bfbf-199">Caracteres inválidos: \% &amp; \* +/=?</span><span class="sxs-lookup"><span data-stu-id="9bfbf-199">Invalid characters: \ % &amp; \* + / = ?</span></span> <span data-ttu-id="9bfbf-200">{ } | \< \> ( ) ; : , [ ] "</span><span class="sxs-lookup"><span data-stu-id="9bfbf-200">{ } | \< \> ( ) ; : , [ ] "</span></span>
  - <span data-ttu-id="9bfbf-201">Caracteres permitidos: A – Z, a-z, 0 – 9, ".</span><span class="sxs-lookup"><span data-stu-id="9bfbf-201">Characters allowed: A – Z, a - z, 0 – 9, ' .</span></span> <span data-ttu-id="9bfbf-202">- _ !</span><span class="sxs-lookup"><span data-stu-id="9bfbf-202">- _ !</span></span> <span data-ttu-id="9bfbf-203"># ^ ~</span><span class="sxs-lookup"><span data-stu-id="9bfbf-203"># ^ ~</span></span>
  - <span data-ttu-id="9bfbf-204">Letras com sinais diacríticos, como tremas, acentos e tils, são caracteres inválidos.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-204">Letters with diacritical marks, such as umlauts, accents, and tildes, are invalid characters.</span></span>
  - <span data-ttu-id="9bfbf-205">O caractere @ é necessário em cada valor **userPrincipalName** .</span><span class="sxs-lookup"><span data-stu-id="9bfbf-205">The @ character is required in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="9bfbf-206">O caractere @ não pode ser o primeiro caractere em cada valor **userPrincipalName** .</span><span class="sxs-lookup"><span data-stu-id="9bfbf-206">The @ character cannot be the first character in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="9bfbf-207">O nome de usuário não pode terminar com um ponto (.), um e comercial ( &amp; ), um espaço ou um sinal de arroba (@).</span><span class="sxs-lookup"><span data-stu-id="9bfbf-207">The username cannot end with a period (.), an ampersand (&amp;), a space, or an at sign (@).</span></span>
  - <span data-ttu-id="9bfbf-208">O nome de usuário não pode conter espaços.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-208">The username cannot contain any spaces.</span></span>
  - <span data-ttu-id="9bfbf-209">Domínios roteáveis devem ser usados; por exemplo, domínios locais ou internos não podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-209">Routable domains must be used; for example, local or internal domains cannot be used.</span></span>
  - <span data-ttu-id="9bfbf-210">Unicode é convertido em caracteres de sublinhado.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-210">Unicode is converted to underscore characters.</span></span>
  - <span data-ttu-id="9bfbf-211">**userPrincipalName** não pode conter valores duplicados no diretório.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-211">**userPrincipalName** cannot contain any duplicate values in the directory.</span></span>

## <a name="3-prepare-the-userprincipalname-attribute"></a><span data-ttu-id="9bfbf-212">3. Prepare o atributo userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="9bfbf-212">3. Prepare the userPrincipalName attribute</span></span>

<span data-ttu-id="9bfbf-213">O Active Directory é projetado para permitir que os usuários finais em sua organização entrem em seu diretório usando **sAMAccountName** ou **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-213">Active Directory is designed to allow the end users in your organization to sign in to your directory by using either **sAMAccountName** or **userPrincipalName**.</span></span> <span data-ttu-id="9bfbf-214">Da mesma forma, os usuários finais podem entrar no Microsoft 365 usando o nome principal do usuário (UPN) de sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-214">Similarly, end users can sign in to Microsoft 365 by using the user principal name (UPN) of their work or school account.</span></span> <span data-ttu-id="9bfbf-215">A sincronização de diretório tenta criar novos usuários no Azure Active Directory usando o mesmo UPN que está no AD DS.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-215">Directory synchronization attempts to create new users in Azure Active Directory by using the same UPN that's in your AD DS.</span></span> <span data-ttu-id="9bfbf-216">O UPN é formatado como um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-216">The UPN is formatted like an email address.</span></span>

<span data-ttu-id="9bfbf-217">No Microsoft 365, o UPN é o atributo padrão usado para gerar o endereço de email.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-217">In Microsoft 365, the UPN is the default attribute that's used to generate the email address.</span></span> <span data-ttu-id="9bfbf-218">É fácil obter **userPrincipalName** (no AD DS e no Azure AD) e o endereço de email principal no **proxyAddresses** definido como valores diferentes.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-218">It's easy to get **userPrincipalName** (in AD DS and in Azure AD) and the primary email address in **proxyAddresses** set to different values.</span></span> <span data-ttu-id="9bfbf-219">Quando estão definidas como valores diferentes, pode haver confusão para administradores e usuários finais.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-219">When they are set to different values, there can be confusion for administrators and end users.</span></span>

<span data-ttu-id="9bfbf-220">É melhor alinhar esses atributos para reduzir a confusão.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-220">It's best to align these attributes to reduce confusion.</span></span> <span data-ttu-id="9bfbf-221">Para atender aos requisitos de logon único com os serviços de Federação do Active Directory (AD FS) 2,0, você precisa garantir que os UPNs no Active Directory do Azure e o AD DS coincidam e estejam usando um namespace de domínio válido.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-221">To meet the requirements of single sign-on with Active Directory Federation Services (AD FS) 2.0, you need to ensure that the UPNs in Azure Active Directory and your AD DS match and are using a valid domain namespace.</span></span>

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a><span data-ttu-id="9bfbf-222">4. adicionar um sufixo UPN alternativo ao AD DS</span><span class="sxs-lookup"><span data-stu-id="9bfbf-222">4. Add an alternative UPN suffix to AD DS</span></span>

<span data-ttu-id="9bfbf-223">Talvez seja necessário adicionar um sufixo UPN alternativo para associar as credenciais corporativas do usuário ao ambiente do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-223">You may need to add an alternative UPN suffix to associate the user's corporate credentials with the Microsoft 365 environment.</span></span> <span data-ttu-id="9bfbf-224">Um sufixo UPN é a parte do UPN à direita do caractere @.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-224">A UPN suffix is the part of a UPN to the right of the @ character.</span></span> <span data-ttu-id="9bfbf-225">UPNs usados para logon único podem conter letras, números, pontos, traços e sublinhados, mas nenhum outro tipo de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-225">UPNs that are used for single sign-on can contain letters, numbers, periods, dashes, and underscores, but no other types of characters.</span></span>

<span data-ttu-id="9bfbf-226">Para obter mais informações sobre como adicionar um sufixo UPN alternativo ao Active Directory, consulte [preparar para a sincronização de diretórios]( https://go.microsoft.com/fwlink/p/?LinkId=525430).</span><span class="sxs-lookup"><span data-stu-id="9bfbf-226">For more information on how to add an alternative UPN suffix to Active Directory, see [Prepare for directory synchronization]( https://go.microsoft.com/fwlink/p/?LinkId=525430).</span></span>

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a><span data-ttu-id="9bfbf-227">5. corresponda ao UPN do AD DS com o Microsoft 365 UPN</span><span class="sxs-lookup"><span data-stu-id="9bfbf-227">5. Match the AD DS UPN with the Microsoft 365 UPN</span></span>

<span data-ttu-id="9bfbf-228">Se você já configurou a sincronização de diretórios, o UPN do usuário para o Microsoft 365 pode não corresponder ao UPN do AD DS do usuário definido no AD DS.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-228">If you've already set up directory synchronization, the user's UPN for Microsoft 365 may not match the user's AD DS UPN that's defined in your AD DS.</span></span> <span data-ttu-id="9bfbf-229">Isso pode ocorrer quando uma licença foi atribuída ao usuário antes da verificação do domínio.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-229">This can occur when a user was assigned a license before the domain was verified.</span></span> <span data-ttu-id="9bfbf-230">Para corrigir isso, use o [PowerShell para corrigir o UPN duplicado](https://go.microsoft.com/fwlink/p/?LinkId=396730) para atualizar o UPN do usuário para garantir que o Microsoft 365 UPN corresponda ao nome de usuário e domínio corporativos.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-230">To fix this, use [PowerShell to fix duplicate UPN](https://go.microsoft.com/fwlink/p/?LinkId=396730) to update the user's UPN to ensure that the Microsoft 365 UPN matches the corporate user name and domain.</span></span> <span data-ttu-id="9bfbf-231">Se você estiver atualizando o UPN no AD DS e quiser que ele seja sincronizado com a identidade do Azure Active Directory, será necessário remover a licença do usuário no Microsoft 365 antes de realizar as alterações no AD DS.</span><span class="sxs-lookup"><span data-stu-id="9bfbf-231">If you are updating the UPN in the AD DS and would like it to synchronize with the Azure Active Directory identity, you need to remove the user's license in Microsoft 365 prior to making the changes in AD DS.</span></span>

<span data-ttu-id="9bfbf-232">Consulte também [como preparar um domínio não roteável (como o domínio. local) para a sincronização de diretórios](prepare-a-non-routable-domain-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="9bfbf-232">Also see [How to prepare a non-routable domain (such as .local domain) for directory synchronization](prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9bfbf-233">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="9bfbf-233">Next steps</span></span>

<span data-ttu-id="9bfbf-234">Se você tiver concluído as etapas de 1 a 5 acima, consulte [set up Directory Synchronization](set-up-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="9bfbf-234">If you have done steps 1 through 5 above, see [Set up directory synchronization](set-up-directory-synchronization.md).</span></span>
