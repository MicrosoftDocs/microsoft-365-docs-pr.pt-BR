---
title: Executar um administrador interno tomada
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Saiba como verificar sua propriedade de email e domínio para assumir o controle de um locatário não gerenciado no Microsoft 365
ms.openlocfilehash: 1eb54a6c34c9700bda09a660c71d2b1222fcdb8c
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45022152"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="996ca-103">Executar um administrador interno tomada</span><span class="sxs-lookup"><span data-stu-id="996ca-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="996ca-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="996ca-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="996ca-105">Se você é um administrador e deseja assumir o controle de um locatário não gerenciado criado por uma inscrição de usuário de autoatendimento, é possível fazer isso com um administrador de tomada interno.</span><span class="sxs-lookup"><span data-stu-id="996ca-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="996ca-106">Uma inscrição autoatendimento para qualquer serviço de nuvem que usa o Azure AD adicionará o usuário a um diretório do Azure AD não gerenciado ou "sombra" e criará um locatário não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="996ca-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="996ca-107">Um locatário não gerenciado é um diretório sem um administrador global.</span><span class="sxs-lookup"><span data-stu-id="996ca-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="996ca-108">Para determinar se um locatário é gerenciado ou não gerenciado, confira [determinando o tipo de locatário](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span><span class="sxs-lookup"><span data-stu-id="996ca-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="996ca-109">Etapa 1: verificar seu endereço de email</span><span class="sxs-lookup"><span data-stu-id="996ca-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="996ca-110">Se o autoatendimento estiver habilitado em seu locatário, os usuários poderão assinar serviços gratuitos, como o Power BI, por conta própria.</span><span class="sxs-lookup"><span data-stu-id="996ca-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="996ca-111">Essas etapas pressupõem que uma assinatura de usuário de autoatendimento tenha criado o locatário não gerenciado que você deseja assumir como administrador. Na primeira etapa, você cria um contexto de usuário no locatário não gerenciado, usando o Power BI para ilustrar o caminho do tomada de administração.</span><span class="sxs-lookup"><span data-stu-id="996ca-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="996ca-112">Para se inscrever no Power bi, vá para o [site do Power bi](https://powerbi.com) e selecione **iniciar liberação**gratuita  >  de**inicialização** (na caixa compartilhar com o Power bi pro).</span><span class="sxs-lookup"><span data-stu-id="996ca-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="996ca-113">Inscreva-se em uma conta de usuário que usa o nome de domínio da sua organização (como `powerbiadmin@contoso.com` ).</span><span class="sxs-lookup"><span data-stu-id="996ca-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="996ca-114">Se sua conta já estiver em uso, entre usando sua senha atual.</span><span class="sxs-lookup"><span data-stu-id="996ca-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="996ca-115">Verifique seu email para o **código de verificação** e insira o código para validar seu endereço de email.</span><span class="sxs-lookup"><span data-stu-id="996ca-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="996ca-116">Etapa 2: criar uma nova conta</span><span class="sxs-lookup"><span data-stu-id="996ca-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="996ca-117">Ao inserir o código de verificação, você será levado a uma página onde você pode criar uma nova conta.</span><span class="sxs-lookup"><span data-stu-id="996ca-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="996ca-118">Preencha os campos nome de usuário e senha com a conta que você deseja usar e, em seguida, selecione **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="996ca-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="996ca-119">Etapa 3: verificar a propriedade do domínio e tornar-se o administrador</span><span class="sxs-lookup"><span data-stu-id="996ca-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="996ca-120">O assistente **de administração** será aberto.</span><span class="sxs-lookup"><span data-stu-id="996ca-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="996ca-121">Se o assistente não for iniciado, procure o bloco **administrador** e selecione-o.</span><span class="sxs-lookup"><span data-stu-id="996ca-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="996ca-122">Selecione **Sim, quero ser o administrador**.</span><span class="sxs-lookup"><span data-stu-id="996ca-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="996ca-123">Verifique se você é o proprietário do domínio que deseja assumir adicionando um registro TXT ao registrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="996ca-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="996ca-124">O assistente fornecerá o registro TXT a ser adicionado, além de fornecer um link para o site do registrador e um link para as instruções passo a passo.</span><span class="sxs-lookup"><span data-stu-id="996ca-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="996ca-125">Após adicionar o registro TXT ao seu site de registrador, retorne ao assistente e selecione **OK, adicionei o registro**.</span><span class="sxs-lookup"><span data-stu-id="996ca-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="996ca-126">A realização do locatário de sombra não afetará nenhuma informação ou serviço existente.</span><span class="sxs-lookup"><span data-stu-id="996ca-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="996ca-127">No entanto, se qualquer usuário no domínio se inscrever em serviços que exijam uma licença, você será solicitado a comprar licenças para eles como parte da função de administrador.</span><span class="sxs-lookup"><span data-stu-id="996ca-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="996ca-128">Você pode comprar ou remover licenças quando o processo de instalação administrativa estiver concluído.</span><span class="sxs-lookup"><span data-stu-id="996ca-128">You can buy or remove licenses once the admin setup process is finished.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="996ca-129">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="996ca-129">Related articles</span></span>

<span data-ttu-id="996ca-130">YouTube: [3 etapas para fazer um tomada de administração de ti para o Power bi e o Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span><span class="sxs-lookup"><span data-stu-id="996ca-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span></span>

[<span data-ttu-id="996ca-131">Tomada de administração no Azure AD</span><span class="sxs-lookup"><span data-stu-id="996ca-131">Admin takeover in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[<span data-ttu-id="996ca-132">Obter ajuda com domínios</span><span class="sxs-lookup"><span data-stu-id="996ca-132">Get help with domains</span></span>](../get-help-with-domains/get-help-with-domains.md)

[<span data-ttu-id="996ca-133">Usando a inscrição de autoatendimento em sua organização</span><span class="sxs-lookup"><span data-stu-id="996ca-133">Using self-service sign up in your organization</span></span>](self-service-sign-up.md)
  
[<span data-ttu-id="996ca-134">Noções básicas sobre a função de administrador do serviço do Power BI</span><span class="sxs-lookup"><span data-stu-id="996ca-134">Understanding the Power BI service administrator role</span></span>](https://docs.microsoft.com/power-bi/service-admin-role)

