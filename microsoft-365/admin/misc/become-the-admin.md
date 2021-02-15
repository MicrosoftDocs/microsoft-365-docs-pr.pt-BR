---
title: Executar uma administração interna
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
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
description: Saiba como verificar a propriedade do seu email e domínio para assumir um locatário nãomanagedo no Microsoft 365
ms.openlocfilehash: 28359908576260218459d13b8c1c1b662b9a2c8f
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658058"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="6a7ae-103">Executar uma administração interna</span><span class="sxs-lookup"><span data-stu-id="6a7ae-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="6a7ae-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="6a7ae-105">Se você for um administrador e quiser assumir um locatário não gerenciada criado por uma assinatura de usuário de autoatendida, você pode fazer isso com uma administração interna.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="6a7ae-106">Uma assinatura de autoatendado para qualquer serviço de nuvem que use o Azure AD adicionará o usuário a um diretório do Azure AD não-manado ou "sombra" e criará um locatário não-manado.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="6a7ae-107">Um locatário não-administrador é um diretório sem um administrador global.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="6a7ae-108">Para determinar se um locatário é gerenciado ou não gerenciado, consulte [Determinando o tipo de locatário.](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)</span><span class="sxs-lookup"><span data-stu-id="6a7ae-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="6a7ae-109">Etapa 1: verificar seu endereço de email</span><span class="sxs-lookup"><span data-stu-id="6a7ae-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="6a7ae-110">Se o autoatendado estiver habilitado em seu locatário, os usuários poderão se inscrever para serviços gratuitos, como o Power BI, por conta própria.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="6a7ae-111">Estas etapas presumem que uma assinatura de usuário de autoatendado tenha criado o locatário não gerenciada que você deseja assumir como administrador. Na primeira etapa, você cria um contexto de usuário no locatário não gerenciada, usando o Power BI para ilustrar o caminho de administração do administrador.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="6a7ae-112">Para se inscrever no Power BI, vá para o site do [Power BI](https://powerbi.com) e selecione Iniciar avaliação gratuita de Início Gratuito (na caixa Compartilhar com o Power  >   BI Pro).</span><span class="sxs-lookup"><span data-stu-id="6a7ae-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="6a7ae-113">Inscreva-se com uma conta de usuário que use o nome de domínio da sua organização (como `powerbiadmin@contoso.com` ).</span><span class="sxs-lookup"><span data-stu-id="6a7ae-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="6a7ae-114">Se sua conta já estiver em uso, entre usando sua senha atual.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="6a7ae-115">Verifique seu email em busca do **código de verificação** e digite o código para validar seu endereço de email.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="6a7ae-116">Etapa 2: Criar uma nova conta</span><span class="sxs-lookup"><span data-stu-id="6a7ae-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="6a7ae-117">Ao inserir o código de verificação, você será levado a uma página onde poderá criar uma nova conta.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="6a7ae-118">Preencha os campos nome de usuário e senha com a conta que você deseja usar e selecione **Iniciar.**</span><span class="sxs-lookup"><span data-stu-id="6a7ae-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="6a7ae-119">Etapa 3: Verificar a propriedade do domínio e tornar-se o administrador</span><span class="sxs-lookup"><span data-stu-id="6a7ae-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="6a7ae-120">O **assistente Tornar-se** o administrador será aberto.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="6a7ae-121">Se o assistente não iniciar, procure o **painel** Administrador e selecione-o.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="6a7ae-122">Selecione **Sim, quero ser o administrador.**</span><span class="sxs-lookup"><span data-stu-id="6a7ae-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="6a7ae-123">Verifique se você é o próprio domínio que deseja assumir adicionando um registro TXT ao seu registrador de domínios.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="6a7ae-124">O assistente fornecerá o registro TXT a ser acrescentado, além de fornecer um link para o site do registrador e um link para instruções passo a passo.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="6a7ae-125">Depois de adicionar o registro TXT ao seu site de registrador, retorne ao assistente e selecione **Ok, adicionei o registro.**</span><span class="sxs-lookup"><span data-stu-id="6a7ae-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6a7ae-126">Assumir o locatário de sombra não afetará qualquer informação ou serviço existente.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="6a7ae-127">No entanto, se algum usuário no domínio se inscreveu em serviços que exigem uma licença, você será solicitado a comprar licenças para eles como parte de assumir a função de administrador.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="6a7ae-128">Você pode comprar ou remover licenças depois que o processo de instalação do administrador for concluído.</span><span class="sxs-lookup"><span data-stu-id="6a7ae-128">You can buy or remove licenses once the admin setup process is finished.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="6a7ae-129">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="6a7ae-129">Related articles</span></span>

<span data-ttu-id="6a7ae-130">YouTube: 3 etapas para fazer uma Tomada de Controle de Administração de TI [para o Power BI e o Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span><span class="sxs-lookup"><span data-stu-id="6a7ae-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span></span>

[<span data-ttu-id="6a7ae-131">Administração no Azure AD</span><span class="sxs-lookup"><span data-stu-id="6a7ae-131">Admin takeover in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[<span data-ttu-id="6a7ae-132">Usando o autoatendimento inscreva-se na sua instituição</span><span class="sxs-lookup"><span data-stu-id="6a7ae-132">Using self-service sign up in your organization</span></span>](self-service-sign-up.md)
  
[<span data-ttu-id="6a7ae-133">Noções básicas sobre a função de administrador de serviços do Power BI</span><span class="sxs-lookup"><span data-stu-id="6a7ae-133">Understanding the Power BI service administrator role</span></span>](https://docs.microsoft.com/power-bi/service-admin-role)

