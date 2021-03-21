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
description: Descreve como se preparar para provisionar usuários para o Microsoft 365 usando a sincronização de diretórios e os benefícios a longo prazo do uso desse método.
ms.openlocfilehash: 1fe99247a5c50c7bb8fc7eb1347ce6a4cd6aad94
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927319"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a><span data-ttu-id="94daf-103">Preparar-se para a sincronização de diretórios com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="94daf-103">Prepare for directory synchronization to Microsoft 365</span></span>

<span data-ttu-id="94daf-104">*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="94daf-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="94daf-105">Os benefícios para a sincronização de identidade híbrida e diretórios da sua organização incluem:</span><span class="sxs-lookup"><span data-stu-id="94daf-105">The benefits to hybrid identity and directory synchronization your organization include:</span></span>

- <span data-ttu-id="94daf-106">Reduzindo os programas administrativos em sua organização</span><span class="sxs-lookup"><span data-stu-id="94daf-106">Reducing the administrative programs in your organization</span></span>
- <span data-ttu-id="94daf-107">Opcionalmente, habilitando cenário de login único</span><span class="sxs-lookup"><span data-stu-id="94daf-107">Optionally enabling single sign-on scenario</span></span>
- <span data-ttu-id="94daf-108">Automatizar alterações de conta no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="94daf-108">Automating account changes in Microsoft 365</span></span>

<span data-ttu-id="94daf-109">Para obter mais informações sobre as vantagens de usar a sincronização de diretórios, consulte [hybrid identity with Azure Active Directory (Azure AD)](/azure/active-directory/hybrid/whatis-hybrid-identity) and [hybrid identity for Microsoft 365](plan-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="94daf-109">For more information about the advantages of using directory synchronization, see [hybrid identity with Azure Active Directory (Azure AD)](/azure/active-directory/hybrid/whatis-hybrid-identity) and [hybrid identity for Microsoft 365](plan-for-directory-synchronization.md).</span></span>

<span data-ttu-id="94daf-110">No entanto, a sincronização de diretório requer planejamento e preparação para garantir que seus Serviços de Domínio do Active Directory (AD DS) se sincronizam com o locatário do Azure AD da sua assinatura do Microsoft 365 com um mínimo de erros.</span><span class="sxs-lookup"><span data-stu-id="94daf-110">However, directory synchronization requires planning and preparation to ensure that your Active Directory Domain Services (AD DS) synchronizes to the Azure AD tenant of your Microsoft 365 subscription with a minimum of errors.</span></span>

<span data-ttu-id="94daf-111">Siga estas etapas para obter os melhores resultados.</span><span class="sxs-lookup"><span data-stu-id="94daf-111">Follow these steps in order for the best results.</span></span>

## <a name="1-directory-cleanup-tasks"></a><span data-ttu-id="94daf-112">1. Tarefas de limpeza de diretório</span><span class="sxs-lookup"><span data-stu-id="94daf-112">1. Directory cleanup tasks</span></span>

<span data-ttu-id="94daf-113">Antes de sincronizar o AD DS com seu locatário do Azure AD, você precisa limpar o AD DS.</span><span class="sxs-lookup"><span data-stu-id="94daf-113">Before you synchronize your AD DS to your Azure AD tenant, you need to clean up your AD DS.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="94daf-114">Se você não executar a limpeza do AD DS antes de sincronizar, isso pode levar a um impacto negativo significativo no processo de implantação.</span><span class="sxs-lookup"><span data-stu-id="94daf-114">If you don't perform AD DS cleanup before you synchronize, it can lead to a significant negative impact on the deployment process.</span></span> <span data-ttu-id="94daf-115">Pode levar dias ou até semanas para passar pelo ciclo de sincronização de diretórios, identificando erros e ressincronização.</span><span class="sxs-lookup"><span data-stu-id="94daf-115">It might take days, or even weeks, to go through the cycle of directory synchronization, identifying errors, and re-synchronization.</span></span>

<span data-ttu-id="94daf-116">No AD DS, conclua as seguintes tarefas de limpeza para cada conta de usuário que receberá uma licença do Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="94daf-116">In your AD DS, complete the following clean-up tasks for each user account that will be assigned a Microsoft 365 license:</span></span>

1. <span data-ttu-id="94daf-117">Certifique-se de um endereço de email válido e exclusivo no **atributo proxyAddresses.**</span><span class="sxs-lookup"><span data-stu-id="94daf-117">Ensure a valid and unique email address in the **proxyAddresses** attribute.</span></span>

2. <span data-ttu-id="94daf-118">Remova quaisquer valores duplicados no **atributo proxyAddresses.**</span><span class="sxs-lookup"><span data-stu-id="94daf-118">Remove any duplicate values in the **proxyAddresses** attribute.</span></span>

3. <span data-ttu-id="94daf-119">Se possível, certifique-se de um valor válido e exclusivo para o **atributo userPrincipalName** no objeto de **usuário do** usuário.</span><span class="sxs-lookup"><span data-stu-id="94daf-119">If possible, ensure a valid and unique value for the **userPrincipalName** attribute in the user's **user** object.</span></span> <span data-ttu-id="94daf-120">Para a melhor experiência de sincronização, verifique se o UPN do AD DS corresponde ao UPN do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="94daf-120">For the best synchronization experience, ensure that the AD DS UPN matches the Azure AD UPN.</span></span> <span data-ttu-id="94daf-121">Se um usuário não tiver um valor para o atributo  **userPrincipalName,** o objeto do usuário deverá conter um valor válido e exclusivo para o atributo **sAMAccountName.**</span><span class="sxs-lookup"><span data-stu-id="94daf-121">If a user does not have a value for the **userPrincipalName** attribute, then the **user** object must contain a valid and unique value for the **sAMAccountName** attribute.</span></span> <span data-ttu-id="94daf-122">Remova quaisquer valores duplicados no **atributo userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="94daf-122">Remove any duplicate values in the **userPrincipalName** attribute.</span></span>

4. <span data-ttu-id="94daf-123">Para uso ideal da GAL (lista de endereços global), verifique se as informações nos seguintes atributos da conta de usuário do AD DS estão corretas:</span><span class="sxs-lookup"><span data-stu-id="94daf-123">For optimal use of the global address list (GAL), ensure the information in the following attributes of the AD DS user account is correct:</span></span>

   - <span data-ttu-id="94daf-124">givenName</span><span class="sxs-lookup"><span data-stu-id="94daf-124">givenName</span></span>
   - <span data-ttu-id="94daf-125">surname</span><span class="sxs-lookup"><span data-stu-id="94daf-125">surname</span></span>
   - <span data-ttu-id="94daf-126">displayName</span><span class="sxs-lookup"><span data-stu-id="94daf-126">displayName</span></span>
   - <span data-ttu-id="94daf-127">Cargo</span><span class="sxs-lookup"><span data-stu-id="94daf-127">Job Title</span></span>
   - <span data-ttu-id="94daf-128">Departamento</span><span class="sxs-lookup"><span data-stu-id="94daf-128">Department</span></span>
   - <span data-ttu-id="94daf-129">Escritório</span><span class="sxs-lookup"><span data-stu-id="94daf-129">Office</span></span>
   - <span data-ttu-id="94daf-130">Telefone comercial</span><span class="sxs-lookup"><span data-stu-id="94daf-130">Office Phone</span></span>
   - <span data-ttu-id="94daf-131">Telefone celular</span><span class="sxs-lookup"><span data-stu-id="94daf-131">Mobile Phone</span></span>
   - <span data-ttu-id="94daf-132">Número do fax</span><span class="sxs-lookup"><span data-stu-id="94daf-132">Fax Number</span></span>
   - <span data-ttu-id="94daf-133">Endereço</span><span class="sxs-lookup"><span data-stu-id="94daf-133">Street Address</span></span>
   - <span data-ttu-id="94daf-134">Cidade</span><span class="sxs-lookup"><span data-stu-id="94daf-134">City</span></span>
   - <span data-ttu-id="94daf-135">Estado</span><span class="sxs-lookup"><span data-stu-id="94daf-135">State or Province</span></span>
   - <span data-ttu-id="94daf-136">CEP</span><span class="sxs-lookup"><span data-stu-id="94daf-136">Zip or Postal Code</span></span>
   - <span data-ttu-id="94daf-137">País</span><span class="sxs-lookup"><span data-stu-id="94daf-137">Country or Region</span></span>

## <a name="2-directory-object-and-attribute-preparation"></a><span data-ttu-id="94daf-138">2. Preparação de objeto e atributo de diretório</span><span class="sxs-lookup"><span data-stu-id="94daf-138">2. Directory object and attribute preparation</span></span>

<span data-ttu-id="94daf-139">A sincronização de diretórios bem-sucedida entre o AD DS e o Microsoft 365 exige que seus atributos do AD DS estejam preparados corretamente.</span><span class="sxs-lookup"><span data-stu-id="94daf-139">Successful directory synchronization between your AD DS and Microsoft 365 requires that your AD DS attributes are properly prepared.</span></span> <span data-ttu-id="94daf-140">Por exemplo, você precisa garantir que caracteres específicos não sejam usados em determinados atributos sincronizados com o ambiente do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="94daf-140">For example, you need to ensure that specific characters aren't used in certain attributes that are synchronized with the Microsoft 365 environment.</span></span> <span data-ttu-id="94daf-141">Caracteres inesperados não causam falha na sincronização de diretórios, mas podem retornar um aviso.</span><span class="sxs-lookup"><span data-stu-id="94daf-141">Unexpected characters do not cause directory synchronization to fail but might return a warning.</span></span> <span data-ttu-id="94daf-142">Caracteres inválidos causarão falha na sincronização de diretórios.</span><span class="sxs-lookup"><span data-stu-id="94daf-142">Invalid characters will cause directory synchronization to fail.</span></span>

<span data-ttu-id="94daf-143">A sincronização de diretórios também falhará se alguns dos usuários do AD DS têm um ou mais atributos duplicados.</span><span class="sxs-lookup"><span data-stu-id="94daf-143">Directory synchronization will also fail if some of your AD DS users have one or more duplicate attributes.</span></span> <span data-ttu-id="94daf-144">Cada usuário deve ter atributos exclusivos.</span><span class="sxs-lookup"><span data-stu-id="94daf-144">Each user must have unique attributes.</span></span>

<span data-ttu-id="94daf-145">Os atributos que você precisa preparar estão listados aqui:</span><span class="sxs-lookup"><span data-stu-id="94daf-145">The attributes that you need to prepare are listed here:</span></span>

- <span data-ttu-id="94daf-146">**displayName**</span><span class="sxs-lookup"><span data-stu-id="94daf-146">**displayName**</span></span>

  - <span data-ttu-id="94daf-147">Se o atributo existir no objeto user, ele será sincronizado com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="94daf-147">If the attribute exists in the user object, it will be synchronized with Microsoft 365.</span></span>
  - <span data-ttu-id="94daf-148">Se esse atributo existir no objeto do usuário, deve haver um valor para ele.</span><span class="sxs-lookup"><span data-stu-id="94daf-148">If this attribute exists in the user object, there must be a value for it.</span></span> <span data-ttu-id="94daf-149">Ou seja, o atributo não deve estar em branco.</span><span class="sxs-lookup"><span data-stu-id="94daf-149">That is, the attribute must not be blank.</span></span>
  - <span data-ttu-id="94daf-150">Número máximo de caracteres: 256</span><span class="sxs-lookup"><span data-stu-id="94daf-150">Maximum number of characters: 256</span></span>

- <span data-ttu-id="94daf-151">**givenName**</span><span class="sxs-lookup"><span data-stu-id="94daf-151">**givenName**</span></span>

  - <span data-ttu-id="94daf-152">Se o atributo existir no objeto user, ele será sincronizado com o Microsoft 365, mas o Microsoft 365 não exige ou o usa.</span><span class="sxs-lookup"><span data-stu-id="94daf-152">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>
  - <span data-ttu-id="94daf-153">Número máximo de caracteres: 64</span><span class="sxs-lookup"><span data-stu-id="94daf-153">Maximum number of characters: 64</span></span>

- <span data-ttu-id="94daf-154">**mail**</span><span class="sxs-lookup"><span data-stu-id="94daf-154">**mail**</span></span>

  - <span data-ttu-id="94daf-155">O valor do atributo deve ser exclusivo no diretório.</span><span class="sxs-lookup"><span data-stu-id="94daf-155">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="94daf-156">Se houver valores duplicados, o primeiro usuário com o valor será sincronizado.</span><span class="sxs-lookup"><span data-stu-id="94daf-156">If there are duplicate values, the first user with the value is synchronized.</span></span> <span data-ttu-id="94daf-157">Os usuários subsequentes não aparecerão no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="94daf-157">Subsequent users will not appear in Microsoft 365.</span></span> <span data-ttu-id="94daf-158">Você deve modificar o valor no Microsoft 365 ou modificar ambos os valores no AD DS para que ambos os usuários apareçam no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="94daf-158">You must modify either the value in Microsoft 365 or modify both of the values in AD DS in order for both users to appear in Microsoft 365.</span></span>

- <span data-ttu-id="94daf-159">**mailNickname** (alias do Exchange)</span><span class="sxs-lookup"><span data-stu-id="94daf-159">**mailNickname** (Exchange alias)</span></span>

  - <span data-ttu-id="94daf-160">O valor do atributo não pode começar com um ponto (.).</span><span class="sxs-lookup"><span data-stu-id="94daf-160">The attribute value cannot begin with a period (.).</span></span>
  - <span data-ttu-id="94daf-161">O valor do atributo deve ser exclusivo no diretório.</span><span class="sxs-lookup"><span data-stu-id="94daf-161">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="94daf-162">Sublinha ("_") no nome sincronizado indica que o valor original deste atributo contém caracteres inválidos.</span><span class="sxs-lookup"><span data-stu-id="94daf-162">Underscores ("_") in the synchronized name indicates that the original value of this attribute contains invalid characters.</span></span> <span data-ttu-id="94daf-163">Para obter mais informações sobre esse atributo, consulte [atributo alias do Exchange](/powershell/module/exchange/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="94daf-163">For more information on this attribute, see [Exchange alias attribute](/powershell/module/exchange/set-mailbox).</span></span>
    >

- <span data-ttu-id="94daf-164">**proxyAddresses**</span><span class="sxs-lookup"><span data-stu-id="94daf-164">**proxyAddresses**</span></span>

  - <span data-ttu-id="94daf-165">Atributo de vários valores</span><span class="sxs-lookup"><span data-stu-id="94daf-165">Multiple-value attribute</span></span>
  - <span data-ttu-id="94daf-166">Número máximo de caracteres por valor: 256</span><span class="sxs-lookup"><span data-stu-id="94daf-166">Maximum number of characters per value: 256</span></span>
  - <span data-ttu-id="94daf-167">O valor do atributo não deve conter um espaço.</span><span class="sxs-lookup"><span data-stu-id="94daf-167">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="94daf-168">O valor do atributo deve ser exclusivo no diretório.</span><span class="sxs-lookup"><span data-stu-id="94daf-168">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="94daf-169">Caracteres inválidos: \< \> ( ) ; , [ ] " '</span><span class="sxs-lookup"><span data-stu-id="94daf-169">Invalid characters: \< \> ( ) ; , [ ] " '</span></span>

    <span data-ttu-id="94daf-170">Observe que os caracteres inválidos se aplicam aos caracteres após o delimiter de tipo e ":", de SMTP:User@contso.com é permitido, mas SMTP:user:M@contoso.com não é.</span><span class="sxs-lookup"><span data-stu-id="94daf-170">Note that the invalid characters apply to the characters following the type delimiter and ":", such that SMTP:User@contso.com is allowed, but SMTP:user:M@contoso.com is not.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="94daf-171">Todos os endereços SMTP (Simple Mail Transport Protocol) devem estar em conformidade com os padrões de mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="94daf-171">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span> <span data-ttu-id="94daf-172">Remova endereços duplicados ou indesejados se eles existirem.</span><span class="sxs-lookup"><span data-stu-id="94daf-172">Remove duplicate or unwanted addresses if they exist.</span></span>

- <span data-ttu-id="94daf-173">**sAMAccountName**</span><span class="sxs-lookup"><span data-stu-id="94daf-173">**sAMAccountName**</span></span>

  - <span data-ttu-id="94daf-174">Número máximo de caracteres: 20</span><span class="sxs-lookup"><span data-stu-id="94daf-174">Maximum number of characters: 20</span></span>
  - <span data-ttu-id="94daf-175">O valor do atributo deve ser exclusivo no diretório.</span><span class="sxs-lookup"><span data-stu-id="94daf-175">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="94daf-176">Caracteres inválidos: [ \ " | , / : \< \> + = ; ?</span><span class="sxs-lookup"><span data-stu-id="94daf-176">Invalid characters: [ \ " | , / : \< \> + = ; ?</span></span> <span data-ttu-id="94daf-177">\* ']</span><span class="sxs-lookup"><span data-stu-id="94daf-177">\* ']</span></span>
  - <span data-ttu-id="94daf-178">Se um usuário tiver um atributo **sAMAccountName** inválido, mas tiver um atributo **userPrincipalName** válido, a conta de usuário será criada no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="94daf-178">If a user has an invalid **sAMAccountName** attribute but has a valid **userPrincipalName** attribute, the user account is created in Microsoft 365.</span></span>
  - <span data-ttu-id="94daf-179">Se **sAMAccountName** e **userPrincipalName** são inválidos, o atributo AD DS **userPrincipalName** deve ser atualizado.</span><span class="sxs-lookup"><span data-stu-id="94daf-179">If both **sAMAccountName** and **userPrincipalName** are invalid, the AD DS **userPrincipalName** attribute must be updated.</span></span>

- <span data-ttu-id="94daf-180">**sn** (sobrenome)</span><span class="sxs-lookup"><span data-stu-id="94daf-180">**sn** (surname)</span></span>

  - <span data-ttu-id="94daf-181">Se o atributo existir no objeto user, ele será sincronizado com o Microsoft 365, mas o Microsoft 365 não exige ou o usa.</span><span class="sxs-lookup"><span data-stu-id="94daf-181">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>

- <span data-ttu-id="94daf-182">**targetAddress**</span><span class="sxs-lookup"><span data-stu-id="94daf-182">**targetAddress**</span></span>

    <span data-ttu-id="94daf-183">É necessário que o atributo **targetAddress** (por exemplo, SMTP:tom@contoso.com) preenchido para o usuário apareça na GAL do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="94daf-183">It's required that the **targetAddress** attribute (for example, SMTP:tom@contoso.com) that's populated for the user must appear in the Microsoft 365 GAL.</span></span> <span data-ttu-id="94daf-184">Em cenários de migração de mensagens de terceiros, isso exigiria a extensão de esquema do Microsoft 365 para o AD DS.</span><span class="sxs-lookup"><span data-stu-id="94daf-184">In third-party messaging migration scenarios, this would require the Microsoft 365 schema extension for the AD DS.</span></span> <span data-ttu-id="94daf-185">A extensão de esquema do Microsoft 365 também adicionaria outros atributos úteis para gerenciar objetos do Microsoft 365 preenchidos usando uma ferramenta de sincronização de diretórios do AD DS.</span><span class="sxs-lookup"><span data-stu-id="94daf-185">The Microsoft 365 schema extension would also add other useful attributes to manage Microsoft 365 objects that are populated by using a directory synchronization tool from AD DS.</span></span> <span data-ttu-id="94daf-186">Por exemplo, o **atributo msExchHideFromAddressLists** para gerenciar caixas de correio ocultas ou grupos de distribuição seria adicionado.</span><span class="sxs-lookup"><span data-stu-id="94daf-186">For example, the **msExchHideFromAddressLists** attribute to manage hidden mailboxes or distribution groups would be added.</span></span>

  - <span data-ttu-id="94daf-187">Número máximo de caracteres: 256</span><span class="sxs-lookup"><span data-stu-id="94daf-187">Maximum number of characters: 256</span></span>
  - <span data-ttu-id="94daf-188">O valor do atributo não deve conter um espaço.</span><span class="sxs-lookup"><span data-stu-id="94daf-188">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="94daf-189">O valor do atributo deve ser exclusivo no diretório.</span><span class="sxs-lookup"><span data-stu-id="94daf-189">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="94daf-190">Caracteres inválidos: \ \< \> ( ) ; , [ ] "</span><span class="sxs-lookup"><span data-stu-id="94daf-190">Invalid characters: \ \< \> ( ) ; , [ ] "</span></span>
  - <span data-ttu-id="94daf-191">Todos os endereços SMTP (Simple Mail Transport Protocol) devem estar em conformidade com os padrões de mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="94daf-191">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>

- <span data-ttu-id="94daf-192">**userPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="94daf-192">**userPrincipalName**</span></span>

  - <span data-ttu-id="94daf-193">O **atributo userPrincipalName** deve estar no formato de logon no estilo Internet, onde o nome do usuário é seguido pelo sinal de at (@) e um nome de domínio: por exemplo, user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="94daf-193">The **userPrincipalName** attribute must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name: for example, user@contoso.com.</span></span> <span data-ttu-id="94daf-194">Todos os endereços SMTP (Simple Mail Transport Protocol) devem estar em conformidade com os padrões de mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="94daf-194">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>
  - <span data-ttu-id="94daf-195">O número máximo de caracteres para o **atributo userPrincipalName** é 113.</span><span class="sxs-lookup"><span data-stu-id="94daf-195">The maximum number of characters for the **userPrincipalName** attribute is 113.</span></span> <span data-ttu-id="94daf-196">Um número específico de caracteres é permitido antes e depois do sinal de at (@), da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="94daf-196">A specific number of characters are permitted before and after the at sign (@), as follows:</span></span>
  - <span data-ttu-id="94daf-197">Número máximo de caracteres para o nome de usuário que está na frente do sinal de at (@): 64</span><span class="sxs-lookup"><span data-stu-id="94daf-197">Maximum number of characters for the username that is in front of the at sign (@): 64</span></span>
  - <span data-ttu-id="94daf-198">Número máximo de caracteres para o nome de domínio após o sinal de at (@): 48</span><span class="sxs-lookup"><span data-stu-id="94daf-198">Maximum number of characters for the domain name following the at sign (@): 48</span></span>
  - <span data-ttu-id="94daf-199">Caracteres inválidos: \ % &amp; \* + / = ?</span><span class="sxs-lookup"><span data-stu-id="94daf-199">Invalid characters: \ % &amp; \* + / = ?</span></span> <span data-ttu-id="94daf-200">{ } | \< \> ( ) ; : , [ ] "</span><span class="sxs-lookup"><span data-stu-id="94daf-200">{ } | \< \> ( ) ; : , [ ] "</span></span>
  - <span data-ttu-id="94daf-201">Caracteres permitidos: A – Z, a - z, 0 – 9, ' .</span><span class="sxs-lookup"><span data-stu-id="94daf-201">Characters allowed: A – Z, a - z, 0 – 9, ' .</span></span> <span data-ttu-id="94daf-202">- _ !</span><span class="sxs-lookup"><span data-stu-id="94daf-202">- _ !</span></span> <span data-ttu-id="94daf-203"># ^ ~</span><span class="sxs-lookup"><span data-stu-id="94daf-203"># ^ ~</span></span>
  - <span data-ttu-id="94daf-204">Letras com marcas diacríticas, como umlauts, ênfases e blocos, são caracteres inválidos.</span><span class="sxs-lookup"><span data-stu-id="94daf-204">Letters with diacritical marks, such as umlauts, accents, and tildes, are invalid characters.</span></span>
  - <span data-ttu-id="94daf-205">O caractere @ é necessário em cada **valor userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="94daf-205">The @ character is required in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="94daf-206">O caractere @ não pode ser o primeiro caractere em **cada valor userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="94daf-206">The @ character cannot be the first character in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="94daf-207">O nome de usuário não pode terminar com um ponto (.), uma ampersand ( &amp; ), um espaço ou um sinal de at (@).</span><span class="sxs-lookup"><span data-stu-id="94daf-207">The username cannot end with a period (.), an ampersand (&amp;), a space, or an at sign (@).</span></span>
  - <span data-ttu-id="94daf-208">O nome de usuário não pode conter espaços.</span><span class="sxs-lookup"><span data-stu-id="94daf-208">The username cannot contain any spaces.</span></span>
  - <span data-ttu-id="94daf-209">Domínios de tabela devem ser usados; por exemplo, domínios locais ou internos não podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="94daf-209">Routable domains must be used; for example, local or internal domains cannot be used.</span></span>
  - <span data-ttu-id="94daf-210">Unicode é convertido em caracteres de sublinhado.</span><span class="sxs-lookup"><span data-stu-id="94daf-210">Unicode is converted to underscore characters.</span></span>
  - <span data-ttu-id="94daf-211">**userPrincipalName** não pode conter valores duplicados no diretório.</span><span class="sxs-lookup"><span data-stu-id="94daf-211">**userPrincipalName** cannot contain any duplicate values in the directory.</span></span>

## <a name="3-prepare-the-userprincipalname-attribute"></a><span data-ttu-id="94daf-212">3. Preparar o atributo userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="94daf-212">3. Prepare the userPrincipalName attribute</span></span>

<span data-ttu-id="94daf-213">O Active Directory foi projetado para permitir que os usuários finais da sua organização entre no diretório usando **sAMAccountName** ou **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="94daf-213">Active Directory is designed to allow the end users in your organization to sign in to your directory by using either **sAMAccountName** or **userPrincipalName**.</span></span> <span data-ttu-id="94daf-214">Da mesma forma, os usuários finais podem entrar no Microsoft 365 usando o nome principal do usuário (UPN) de sua conta de trabalho ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="94daf-214">Similarly, end users can sign in to Microsoft 365 by using the user principal name (UPN) of their work or school account.</span></span> <span data-ttu-id="94daf-215">A sincronização de diretório tenta criar novos usuários no Azure Active Directory usando o mesmo UPN que está no AD DS.</span><span class="sxs-lookup"><span data-stu-id="94daf-215">Directory synchronization attempts to create new users in Azure Active Directory by using the same UPN that's in your AD DS.</span></span> <span data-ttu-id="94daf-216">O UPN é formatado como um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="94daf-216">The UPN is formatted like an email address.</span></span>

<span data-ttu-id="94daf-217">No Microsoft 365, o UPN é o atributo padrão usado para gerar o endereço de email.</span><span class="sxs-lookup"><span data-stu-id="94daf-217">In Microsoft 365, the UPN is the default attribute that's used to generate the email address.</span></span> <span data-ttu-id="94daf-218">É fácil obter **userPrincipalName** (no AD DS e no Azure AD) e o endereço de email principal em **proxyAddresses** definido como valores diferentes.</span><span class="sxs-lookup"><span data-stu-id="94daf-218">It's easy to get **userPrincipalName** (in AD DS and in Azure AD) and the primary email address in **proxyAddresses** set to different values.</span></span> <span data-ttu-id="94daf-219">Quando eles são definidos como valores diferentes, pode haver confusão para administradores e usuários finais.</span><span class="sxs-lookup"><span data-stu-id="94daf-219">When they are set to different values, there can be confusion for administrators and end users.</span></span>

<span data-ttu-id="94daf-220">É melhor alinhar esses atributos para reduzir a confusão.</span><span class="sxs-lookup"><span data-stu-id="94daf-220">It's best to align these attributes to reduce confusion.</span></span> <span data-ttu-id="94daf-221">Para atender aos requisitos de um único login com o AD FS (Serviços de Federação do Active Directory) 2.0, você precisa garantir que os UPNs no Azure Active Directory e seu AD DS corresponderão e usem um namespace de domínio válido.</span><span class="sxs-lookup"><span data-stu-id="94daf-221">To meet the requirements of single sign-on with Active Directory Federation Services (AD FS) 2.0, you need to ensure that the UPNs in Azure Active Directory and your AD DS match and are using a valid domain namespace.</span></span>

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a><span data-ttu-id="94daf-222">4. Adicione um sufixo UPN alternativo ao AD DS</span><span class="sxs-lookup"><span data-stu-id="94daf-222">4. Add an alternative UPN suffix to AD DS</span></span>

<span data-ttu-id="94daf-223">Talvez seja necessário adicionar um sufixo UPN alternativo para associar as credenciais corporativas do usuário ao ambiente do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="94daf-223">You may need to add an alternative UPN suffix to associate the user's corporate credentials with the Microsoft 365 environment.</span></span> <span data-ttu-id="94daf-224">Um sufixo UPN é a parte do UPN à direita do caractere @.</span><span class="sxs-lookup"><span data-stu-id="94daf-224">A UPN suffix is the part of a UPN to the right of the @ character.</span></span> <span data-ttu-id="94daf-225">UPNs usados para logon único podem conter letras, números, pontos, traços e sublinhados, mas nenhum outro tipo de caracteres.</span><span class="sxs-lookup"><span data-stu-id="94daf-225">UPNs that are used for single sign-on can contain letters, numbers, periods, dashes, and underscores, but no other types of characters.</span></span>

<span data-ttu-id="94daf-226">Para obter mais informações sobre como adicionar um sufixo UPN alternativo ao Active Directory, consulte [Prepare for directory synchronization]( https://go.microsoft.com/fwlink/p/?LinkId=525430).</span><span class="sxs-lookup"><span data-stu-id="94daf-226">For more information on how to add an alternative UPN suffix to Active Directory, see [Prepare for directory synchronization]( https://go.microsoft.com/fwlink/p/?LinkId=525430).</span></span>

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a><span data-ttu-id="94daf-227">5. Corresponder o UPN do AD DS com o UPN do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="94daf-227">5. Match the AD DS UPN with the Microsoft 365 UPN</span></span>

<span data-ttu-id="94daf-228">Se você já tiver definido a sincronização de diretórios, o UPN do usuário para o Microsoft 365 pode não corresponder ao UPN do AD DS do usuário definido no AD DS.</span><span class="sxs-lookup"><span data-stu-id="94daf-228">If you've already set up directory synchronization, the user's UPN for Microsoft 365 may not match the user's AD DS UPN that's defined in your AD DS.</span></span> <span data-ttu-id="94daf-229">Isso pode ocorrer quando uma licença foi atribuída ao usuário antes da verificação do domínio.</span><span class="sxs-lookup"><span data-stu-id="94daf-229">This can occur when a user was assigned a license before the domain was verified.</span></span> <span data-ttu-id="94daf-230">Para corrigir isso, use [o PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396730) para corrigir UPN duplicado para atualizar o UPN do usuário para garantir que o UPN do Microsoft 365 corresponde ao nome de usuário corporativo e ao domínio.</span><span class="sxs-lookup"><span data-stu-id="94daf-230">To fix this, use [PowerShell to fix duplicate UPN](https://go.microsoft.com/fwlink/p/?LinkId=396730) to update the user's UPN to ensure that the Microsoft 365 UPN matches the corporate user name and domain.</span></span> <span data-ttu-id="94daf-231">Se você estiver atualizando o UPN no AD DS e quiser que ele seja sincronizado com a identidade do Azure Active Directory, você precisará remover a licença do usuário no Microsoft 365 antes de fazer as alterações no AD DS.</span><span class="sxs-lookup"><span data-stu-id="94daf-231">If you are updating the UPN in the AD DS and would like it to synchronize with the Azure Active Directory identity, you need to remove the user's license in Microsoft 365 prior to making the changes in AD DS.</span></span>

<span data-ttu-id="94daf-232">Consulte [Também Como preparar um domínio não stável (como domínio .local) para sincronização de diretórios.](prepare-a-non-routable-domain-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="94daf-232">Also see [How to prepare a non-routable domain (such as .local domain) for directory synchronization](prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="94daf-233">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="94daf-233">Next steps</span></span>

<span data-ttu-id="94daf-234">Se você tiver feito as etapas 1 a 5 acima, consulte [Configurar a sincronização de diretórios](set-up-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="94daf-234">If you have done steps 1 through 5 above, see [Set up directory synchronization](set-up-directory-synchronization.md).</span></span>