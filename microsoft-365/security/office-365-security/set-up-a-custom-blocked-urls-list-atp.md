---
title: Configurar uma lista de URLs bloqueadas personalizada usando links seguros de ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Saiba como configurar uma lista de URLs bloqueadas para sua organização usando a proteção avançada contra ameaças do Office 365.
ms.openlocfilehash: 5f863a3ba61278d0bec5304034ed75d343f93c77
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656642"
---
# <a name="set-up-a-custom-blocked-urls-list-using-atp-safe-links"></a><span data-ttu-id="236a5-103">Configurar uma lista de URLs bloqueadas personalizada usando links seguros de ATP</span><span class="sxs-lookup"><span data-stu-id="236a5-103">Set up a custom blocked URLs list using ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="236a5-104">Este artigo destina-se aos clientes corporativos que têm a [Proteção Avançada contra Ameaças do Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="236a5-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="236a5-105">Se você for um usuário doméstico que procura informações sobre links seguros no Outlook, consulte [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="236a5-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="236a5-106">Com a [proteção avançada contra ameaças do Office 365](office-365-atp.md) (ATP), sua organização pode ter uma lista personalizada de endereços de sites (URLs) bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="236a5-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked.</span></span> <span data-ttu-id="236a5-107">Quando uma URL é bloqueada, as pessoas que clicam em links para a URL bloqueada são levadas para uma [página de aviso](atp-safe-links-warning-pages.md) que se assemelha à seguinte imagem:</span><span class="sxs-lookup"><span data-stu-id="236a5-107">When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span>

![Este site é bloqueado](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

<span data-ttu-id="236a5-109">A lista de URLs bloqueadas é definida pela equipe de segurança do Microsoft 365 for Business da sua organização e essa lista se aplica a todos na organização que estão cobertos pelas políticas de links seguros do Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="236a5-109">The blocked URLs list is defined by your organization's Microsoft 365 for business security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span>

<span data-ttu-id="236a5-110">Leia este artigo para saber como configurar a lista de URLs bloqueadas personalizadas da sua organização para [links seguros de ATP no Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="236a5-110">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>

## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="236a5-111">Exibir ou editar uma lista personalizada de URLs bloqueadas</span><span class="sxs-lookup"><span data-stu-id="236a5-111">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="236a5-112">Os [links seguros de ATP no Office 365](atp-safe-links.md) usam várias listas, incluindo a lista de URLs bloqueadas da sua organização.</span><span class="sxs-lookup"><span data-stu-id="236a5-112">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list.</span></span> <span data-ttu-id="236a5-113">Se tiver as permissões necessárias, você poderá configurar a lista personalizada da sua organização.</span><span class="sxs-lookup"><span data-stu-id="236a5-113">If you have the necessary permissions, you can set up your organization's custom list.</span></span> <span data-ttu-id="236a5-114">Para fazer isso, edite a política de links seguros padrão da sua organização.</span><span class="sxs-lookup"><span data-stu-id="236a5-114">You do this by editing your organization's default Safe Links policy.</span></span>

<span data-ttu-id="236a5-115">Para editar (ou definir) políticas ATP, você deve receber uma das funções descritas na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="236a5-115">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span>

****

|<span data-ttu-id="236a5-116">Role</span><span class="sxs-lookup"><span data-stu-id="236a5-116">Role</span></span>|<span data-ttu-id="236a5-117">Onde/como a atribuição</span><span class="sxs-lookup"><span data-stu-id="236a5-117">Where/how assigned</span></span>|
|---|---|
|<span data-ttu-id="236a5-118">administrador global</span><span class="sxs-lookup"><span data-stu-id="236a5-118">global administrator</span></span>|<span data-ttu-id="236a5-119">Por padrão, a pessoa que se inscreve para comprar a Microsoft 365 é um administrador global.</span><span class="sxs-lookup"><span data-stu-id="236a5-119">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="236a5-120">(Consulte [about Microsoft 365 admin Roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) para saber mais.)</span><span class="sxs-lookup"><span data-stu-id="236a5-120">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="236a5-121">Administrador de Segurança</span><span class="sxs-lookup"><span data-stu-id="236a5-121">Security Administrator</span></span>|<span data-ttu-id="236a5-122">Centro de administração do Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )</span><span class="sxs-lookup"><span data-stu-id="236a5-122">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="236a5-123">Gerenciamento de Organização do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="236a5-123">Exchange Online Organization Management</span></span>|<span data-ttu-id="236a5-124">Centro de administração do Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) )</span><span class="sxs-lookup"><span data-stu-id="236a5-124">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="236a5-125">ou</span><span class="sxs-lookup"><span data-stu-id="236a5-125">or</span></span> <br>  <span data-ttu-id="236a5-126">Cmdlets do PowerShell (consulte [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span><span class="sxs-lookup"><span data-stu-id="236a5-126">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span></span>|
|

> [!TIP]
> <span data-ttu-id="236a5-127">Para saber mais sobre funções e permissões, consulte [permissões no centro de conformidade de & de segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="236a5-127">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a><span data-ttu-id="236a5-128">Para exibir ou editar uma lista de URLs bloqueadas personalizada</span><span class="sxs-lookup"><span data-stu-id="236a5-128">To view or edit a custom blocked URLs list</span></span>

1. <span data-ttu-id="236a5-129">Acesse [https://protection.office.com](https://protection.office.com) e entre com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="236a5-129">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="236a5-130">Na navegação à esquerda, em **Gerenciamento de ameaças**, **Policy** escolha \> **links seguros**de política.</span><span class="sxs-lookup"><span data-stu-id="236a5-130">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>

3. <span data-ttu-id="236a5-131">Na seção **políticas que se aplicam a toda a organização** , selecione **padrão**e, em seguida, escolha **Editar** (o botão Editar parece um lápis).</span><span class="sxs-lookup"><span data-stu-id="236a5-131">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="236a5-132">![Clique em Editar para editar a política padrão para proteção de links seguros](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="236a5-132">![Click Edit to edit your default policy for Safe Links protection](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="236a5-133">Isso permite que você exiba a lista de URLs bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="236a5-133">This enables you to view your list of blocked URLs.</span></span> <span data-ttu-id="236a5-134">Em primeiro lugar, talvez você não tenha URLs listadas aqui.</span><span class="sxs-lookup"><span data-stu-id="236a5-134">At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="236a5-135">![Lista de URLs bloqueadas na política de links seguros padrão](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="236a5-135">![Blocked URLs list in the default Safe Links policy](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>

4. <span data-ttu-id="236a5-136">Selecione a caixa **Insira uma URL válida** , digite uma URL e, em seguida, escolha o sinal de mais ( **+** ).</span><span class="sxs-lookup"><span data-stu-id="236a5-136">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span>

5. <span data-ttu-id="236a5-137">Quando terminar de adicionar URLs, no canto inferior direito da tela, escolha **salvar**.</span><span class="sxs-lookup"><span data-stu-id="236a5-137">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>

## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="236a5-138">Há algumas coisas que você deve ter em mente</span><span class="sxs-lookup"><span data-stu-id="236a5-138">A few things to keep in mind</span></span>

<span data-ttu-id="236a5-139">Ao adicionar URLs à sua lista, tenha em mente os seguintes pontos:</span><span class="sxs-lookup"><span data-stu-id="236a5-139">While you add URLs to your list, keep the following points in mind:</span></span>

- <span data-ttu-id="236a5-140">Não inclua uma barra ( **/** ) no final da URL.</span><span class="sxs-lookup"><span data-stu-id="236a5-140">Do not include a forward slash ( **/**) at the end of the URL.</span></span> <span data-ttu-id="236a5-141">Por exemplo, em vez de inserir `https://www.contoso.com/` , insira `https://www.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="236a5-141">For example, instead of entering `https://www.contoso.com/`, enter `https://www.contoso.com`.</span></span>

- <span data-ttu-id="236a5-142">Você pode especificar uma URL somente de domínio (como `contoso.com` ou `tailspintoys.com` ).</span><span class="sxs-lookup"><span data-stu-id="236a5-142">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`).</span></span> <span data-ttu-id="236a5-143">Isso bloqueará cliques em qualquer URL que contenha o domínio.</span><span class="sxs-lookup"><span data-stu-id="236a5-143">This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="236a5-144">Você pode especificar um subdomínio (como `toys.contoso.com*` ) sem bloquear um domínio completo (como `contoso.com` ).</span><span class="sxs-lookup"><span data-stu-id="236a5-144">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`).</span></span> <span data-ttu-id="236a5-145">Isso bloqueará cliques em qualquer URL que contenha o subdomínio, mas não bloqueará cliques para uma URL que contenha o domínio completo.</span><span class="sxs-lookup"><span data-stu-id="236a5-145">This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>

- <span data-ttu-id="236a5-146">Você pode incluir até três asteriscos curinga ( \* ) por URL.</span><span class="sxs-lookup"><span data-stu-id="236a5-146">You can include up to three wildcard asterisks (\*) per URL.</span></span> <span data-ttu-id="236a5-147">A tabela a seguir lista alguns exemplos do que você pode inserir e o efeito que essas entradas têm.</span><span class="sxs-lookup"><span data-stu-id="236a5-147">The following table lists some examples of what you can enter and what effect those entries have.</span></span>

****

|<span data-ttu-id="236a5-148">Entrada de exemplo</span><span class="sxs-lookup"><span data-stu-id="236a5-148">Example Entry</span></span>|<span data-ttu-id="236a5-149">O que ele faz</span><span class="sxs-lookup"><span data-stu-id="236a5-149">What It Does</span></span>|
|---|---|
|<span data-ttu-id="236a5-150">`contoso.com` ou `*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="236a5-150">`contoso.com` or `*contoso.com*`</span></span>|<span data-ttu-id="236a5-151">Bloqueia o domínio, subdomínios e caminhos, como `https://www.contoso.com` , `https://sub.contoso.com` e`https://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="236a5-151">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="236a5-152">Bloqueia um site `https://contoso.com/a` , mas não outros subcaminhos como`https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="236a5-152">Blocks a site `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a*`|<span data-ttu-id="236a5-153">Bloqueia um site `https://contoso.com/a` e subcaminhos adicionais, como`https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="236a5-153">Blocks a site `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`</span></span>|
|`https://toys.contoso.com*`|<span data-ttu-id="236a5-154">Bloqueia um subdomínio ("Toys" nesse caso), mas permite cliques para outras URLs de domínio (como `https://contoso.com` ou `https://home.contoso.com` ).</span><span class="sxs-lookup"><span data-stu-id="236a5-154">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>|
|

> [!NOTE]
> <span data-ttu-id="236a5-155">Por padrão, você só pode adicionar URLs 500 à lista de URLs bloqueadas na política padrão do Office 365 ATP Safe links.</span><span class="sxs-lookup"><span data-stu-id="236a5-155">By default, you can only add 500 URLs to the blocked URL list in the Office 365 ATP Safe Links default policy.</span></span>

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="236a5-156">Como definir exceções para determinados usuários em uma organização</span><span class="sxs-lookup"><span data-stu-id="236a5-156">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="236a5-157">Se quiser que certos grupos possam exibir URLs que podem ser bloqueadas para outras pessoas, você pode especificar uma política de links seguros de ATP que se aplica a destinatários específicos.</span><span class="sxs-lookup"><span data-stu-id="236a5-157">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients.</span></span> <span data-ttu-id="236a5-158">Confira [Configurar uma lista de URLs "não reconfigurar" personalizada usando os links seguros de ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span><span class="sxs-lookup"><span data-stu-id="236a5-158">See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
