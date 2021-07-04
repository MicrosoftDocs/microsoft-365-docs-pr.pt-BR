---
title: Adicionar um domínio a uma Windows PowerShell cliente para parceiros DAP
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: f49b4d24-9aa0-48a6-95dd-6bae9cf53d2c
description: 'Resumo: use o PowerShell para Microsoft 365 adicionar um nome de domínio alternativo a um locatário de cliente existente.'
ms.openlocfilehash: 5ebbe11da9a93669945e7e3b096ce7afa18b5d3a
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288426"
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a><span data-ttu-id="2581e-103">Adicionar um domínio a uma locação do cliente com o Windows PowerShell para parceiros com permissão de acesso delegado (DAP)</span><span class="sxs-lookup"><span data-stu-id="2581e-103">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>

<span data-ttu-id="2581e-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="2581e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="2581e-105">Você pode criar e associar novos domínios ao seu cliente com o PowerShell para Microsoft 365 mais rápido do que usar o Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2581e-105">You can create and associate new domains with your customer's tenancy with PowerShell for Microsoft 365 faster than using the Microsoft 365 admin center.</span></span>

<span data-ttu-id="2581e-106">Os Parceiros com Permissão de Acesso Delegada (DAP) são parceiros da Agregação e dos Provedores de Soluções em Nuvem (CSP).</span><span class="sxs-lookup"><span data-stu-id="2581e-106">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="2581e-107">Muitas vezes, eles são provedores de rede ou de telecomunicações para outras empresas.</span><span class="sxs-lookup"><span data-stu-id="2581e-107">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="2581e-108">Eles agrupam Microsoft 365 assinaturas em suas ofertas de serviço para seus clientes.</span><span class="sxs-lookup"><span data-stu-id="2581e-108">They bundle Microsoft 365 subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="2581e-109">Quando eles vendem uma assinatura de Microsoft 365, eles são automaticamente concedidos permissões Administer On Behalf Of (AOBO) para as empresas de cliente, para que possam administrar e relatar as permissões do cliente.</span><span class="sxs-lookup"><span data-stu-id="2581e-109">When they sell a Microsoft 365 subscription, they are automatically granted Administer On Behalf Of (AOBO) permissions to the customer tenancies so they can administer and report on the customer tenancies.</span></span>
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2581e-110">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="2581e-110">What do you need to know before you begin?</span></span>

<span data-ttu-id="2581e-111">Os procedimentos neste tópico exigem que você se conecte ao Conexão [para Microsoft 365 com o PowerShell](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="2581e-111">The procedures in this topic require you to connect to [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="2581e-112">Você também precisa ter as credenciais de administrador de locatários do parceiro.</span><span class="sxs-lookup"><span data-stu-id="2581e-112">You also need your partner tenant administrator credentials.</span></span>

<span data-ttu-id="2581e-113">Você também precisará das seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="2581e-113">You also need the following information:</span></span>

- <span data-ttu-id="2581e-114">É necessário o nome de domínio totalmente qualificado (FQDN) escolhido pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="2581e-114">You need the fully qualified domain name (FQDN) that your customer wants.</span></span>

- <span data-ttu-id="2581e-115">É necessária a **TenantId** do cliente.</span><span class="sxs-lookup"><span data-stu-id="2581e-115">You need the customer's **TenantId**.</span></span>

- <span data-ttu-id="2581e-p102">O FQDN deve ser registrado com um registrador de Serviço de Nomes de Domínio da Internet (DNS), como o GoDaddy. Para saber mais sobre como registrar publicamente um nome de domínio, confira [Como comprar um nome de domínio](../admin/get-help-with-domains/buy-a-domain-name.md).</span><span class="sxs-lookup"><span data-stu-id="2581e-p102">The FQDN must be registered with an Internet domain name service (DNS) registrar, such as GoDaddy. For more information on how to publically register a domain name, see [How to buy a domain name](../admin/get-help-with-domains/buy-a-domain-name.md).</span></span>

- <span data-ttu-id="2581e-118">Você precisa saber como adicionar um registro TXT à zona DNS registrada do seu registrador de DNS.</span><span class="sxs-lookup"><span data-stu-id="2581e-118">You need to know how to add a TXT record to the registered DNS zone for your DNS registrar.</span></span> <span data-ttu-id="2581e-119">Para obter mais informações sobre como adicionar um registro TXT, consulte [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="2581e-119">For more information on how to add a TXT record, see [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> <span data-ttu-id="2581e-120">Se esses procedimentos não funcionarem, localize os procedimentos do seu registrador de DNS.</span><span class="sxs-lookup"><span data-stu-id="2581e-120">If those procedures don't work for you, you will need to find the procedures for your DNS registrar.</span></span>

## <a name="create-domains"></a><span data-ttu-id="2581e-121">Criar domínios</span><span class="sxs-lookup"><span data-stu-id="2581e-121">Create domains</span></span>

 <span data-ttu-id="2581e-p104">Os clientes provavelmente vão solicitar a criação de domínios adicionais para associar às suas locações, uma vez que não pretendem ter o<domínio>.onmicrosoft.compadrão como o domínio principal que representa sua identidade corporativa mundialmente. Este procedimento lhe orienta na criação de um novo domínio associado à locação do cliente.</span><span class="sxs-lookup"><span data-stu-id="2581e-p104">Your customers will likely ask you to create additional domains to associate with their tenancy because they don't want the default <domain>.onmicrosoft.com domain to be the primary one that represents their corporate identities to the world. This procedure walks you through creating a new domain associated with your customer's tenancy.</span></span>

> [!NOTE]
> <span data-ttu-id="2581e-124">Para executar algumas dessas operações, a conta de administrador  de parceiro  com a sua assinatura deve ser definida como Administração completa para a configuração Atribuir acesso administrativo às empresas com suporte encontrada nos detalhes da conta de administrador no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2581e-124">To perform some of these operations, the partner administrator account you sign in with must be set to **Full administration** for the **Assign administrative access to companies you support** setting found in the details of the admin account in the Microsoft 365 admin center.</span></span> <span data-ttu-id="2581e-125">Para obter mais informações sobre como gerenciar funções de administrador de parceiros, consulte [Partners: Offer delegated administration](https://go.microsoft.com/fwlink/p/?LinkId=532435).</span><span class="sxs-lookup"><span data-stu-id="2581e-125">For more information on managing partner administrator roles, see [Partners: Offer delegated administration](https://go.microsoft.com/fwlink/p/?LinkId=532435).</span></span>

### <a name="create-the-domain-in-azure-active-directory"></a><span data-ttu-id="2581e-126">Criar o domínio no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2581e-126">Create the domain in Azure Active Directory</span></span>

<span data-ttu-id="2581e-127">Esse comando cria o domínio no Azure Active Directory, mas não o associa ao domínio registrado publicamente.</span><span class="sxs-lookup"><span data-stu-id="2581e-127">This command creates the domain in Azure Active Directory but does not associate it with the publicly registered domain.</span></span> <span data-ttu-id="2581e-128">Isso acontece quando você prova que possui o domínio registrado publicamente para a Microsoft Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="2581e-128">That comes when you prove that you own the publicly registered domain to Microsoft Microsoft 365 for enterprises.</span></span>

```powershell
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

> [!NOTE]
> <span data-ttu-id="2581e-129">O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome.</span><span class="sxs-lookup"><span data-stu-id="2581e-129">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="2581e-130">Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2581e-130">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>

### <a name="get-the-data-for-the-dns-txt-verification-record"></a><span data-ttu-id="2581e-131">Obter os dados do registro de verificação TXT de DNS</span><span class="sxs-lookup"><span data-stu-id="2581e-131">Get the data for the DNS TXT verification record</span></span>

 <span data-ttu-id="2581e-132">Microsoft 365 gerará os dados específicos que você precisa colocar no registro de verificação TXT DNS.</span><span class="sxs-lookup"><span data-stu-id="2581e-132">Microsoft 365 will generate the specific data that you need to place into the DNS TXT verification record.</span></span> <span data-ttu-id="2581e-133">Para obter os dados, execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="2581e-133">To get the data, run this command.</span></span>

```powershell
Get-MsolDomainVerificationDNS -TenantId <customer TenantId> -DomainName <FQDN of new domain> -Mode DnsTxtRecord
```

<span data-ttu-id="2581e-134">Isso lhe dará saída como:</span><span class="sxs-lookup"><span data-stu-id="2581e-134">This will give you output like:</span></span>

 `Label: domainname.com`

 `Text: MS=ms########`

 `Ttl: 3600`

> [!NOTE]
> <span data-ttu-id="2581e-135">Você vai precisar desse texto para criar o registro TXT na zona DNS registrada publicamente.</span><span class="sxs-lookup"><span data-stu-id="2581e-135">You will need this text to create the TXT record in the publicly registered DNS zone.</span></span> <span data-ttu-id="2581e-136">Não deixe de copiá-lo e salvá-lo.</span><span class="sxs-lookup"><span data-stu-id="2581e-136">Be sure to copy and save it.</span></span>

### <a name="add-a-txt-record-to-the-publically-registered-dns-zone"></a><span data-ttu-id="2581e-137">Adicionar um registro TXT à zona DNS registrada publicamente</span><span class="sxs-lookup"><span data-stu-id="2581e-137">Add a TXT record to the publically registered DNS zone</span></span>

<span data-ttu-id="2581e-138">Antes Microsoft 365 começar a aceitar tráfego direcionado para o nome de domínio registrado publicamente, você deve provar que é o seu próprio e ter permissões de administrador para o domínio.</span><span class="sxs-lookup"><span data-stu-id="2581e-138">Before Microsoft 365 will start accepting traffic that is directed to the publicly registered domain name, you must prove that you own and have administrator permissions to the domain.</span></span> <span data-ttu-id="2581e-139">Para provar que você é o proprietário do domínio, crie um registro TXT nele.</span><span class="sxs-lookup"><span data-stu-id="2581e-139">You prove you own the domain by creating a TXT record in the domain.</span></span> <span data-ttu-id="2581e-140">Um registro TXT não altera nada em seu domínio e pode ser excluído depois que for provado que você possui o domínio.</span><span class="sxs-lookup"><span data-stu-id="2581e-140">A TXT record doesn't do anything in your domain, and it can be deleted after your ownership of the domain is established.</span></span> <span data-ttu-id="2581e-141">Para criar os registros TXT, siga os procedimentos em [Adicionar registros DNS para conectar seu domínio](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="2581e-141">To create the TXT records, follow the procedures at [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> <span data-ttu-id="2581e-142">Caso esses procedimentos não funcionem, localize os procedimentos do seu registrador de DNS.</span><span class="sxs-lookup"><span data-stu-id="2581e-142">If those procedures don't work for you , you need to find the procedures for your DNS registrar.</span></span>

<span data-ttu-id="2581e-p111">Confirme a criação bem-sucedida do registro TXT por meio do nslookup. Execute a seguinte sintaxe.</span><span class="sxs-lookup"><span data-stu-id="2581e-p111">Confirm the successful creation of the TXT record via nslookup. Follow this syntax.</span></span>

```console
nslookup -type=TXT <FQDN of registered domain>
```

<span data-ttu-id="2581e-145">Isso lhe dará saída como:</span><span class="sxs-lookup"><span data-stu-id="2581e-145">This will give you output like:</span></span>

 `Non-authoritative answer:`

 `FQDN of the registered domain`

 `text=MS=ms########`

### <a name="validate-domain-ownership-in-microsoft-365"></a><span data-ttu-id="2581e-146">Validar a propriedade de domínio em Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2581e-146">Validate domain ownership in Microsoft 365</span></span>

<span data-ttu-id="2581e-147">Nesta última etapa, você valida para Microsoft 365 que você possui o domínio registrado publicamente.</span><span class="sxs-lookup"><span data-stu-id="2581e-147">In this last step, you validate to Microsoft 365 that you own the publically registered domain.</span></span> <span data-ttu-id="2581e-148">Após esta etapa, Microsoft 365 começará a aceitar o tráfego roteado para o novo nome de domínio.</span><span class="sxs-lookup"><span data-stu-id="2581e-148">After this step, Microsoft 365 will begin accepting traffic routed to the new domain name.</span></span> <span data-ttu-id="2581e-149">Para concluir a criação do domínio e o processo de registro, execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="2581e-149">To complete the domain creation and registration process, run this command.</span></span>

```powershell
Confirm-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

<span data-ttu-id="2581e-150">Este comando não retornará nenhuma saída; portanto, para confirmar se ele funcionou, execute-o.</span><span class="sxs-lookup"><span data-stu-id="2581e-150">This command won't return any output, so to confirm that this worked, run this command.</span></span>

```powershell
Get-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

<span data-ttu-id="2581e-151">Isso retornará algo parecido com o seguinte</span><span class="sxs-lookup"><span data-stu-id="2581e-151">This will return something like this</span></span>

```console
Name                   Status      Authentication
--------------------   ---------   --------------
FQDN of new domain     Verified    Managed
```

## <a name="see-also"></a><span data-ttu-id="2581e-152">Confira também</span><span class="sxs-lookup"><span data-stu-id="2581e-152">See also</span></span>

[<span data-ttu-id="2581e-153">Ajuda para parceiros</span><span class="sxs-lookup"><span data-stu-id="2581e-153">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=533477)
