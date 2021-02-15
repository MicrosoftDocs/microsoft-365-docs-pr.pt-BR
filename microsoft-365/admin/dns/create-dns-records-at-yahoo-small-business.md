---
title: Criar registros DNS no Yahoo! Small Business para Microsoft
f1.keywords:
- NOCSH
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
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 034bd7bc-b098-4c4d-8a93-4d74ff24532a
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços no Yahoo! Small Business para Microsoft.
ms.openlocfilehash: 47b3b1f3a6e889d067d0166f872725aa3812a7b4
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656898"
---
# <a name="create-dns-records-at-yahoo-small-business-for-microsoft"></a><span data-ttu-id="9257a-105">Criar registros DNS no Yahoo!</span><span class="sxs-lookup"><span data-stu-id="9257a-105">Create DNS records at Yahoo!</span></span> <span data-ttu-id="9257a-106">Small Business para Microsoft</span><span class="sxs-lookup"><span data-stu-id="9257a-106">Small Business for Microsoft</span></span>

 <span data-ttu-id="9257a-107">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="9257a-107">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9257a-p104">Se o Yahoo! Small Business tiver sido seu provedor de hospedagem DNS, você deve estar ciente de que seu provedor agora é a Aabaco Small Business.</span><span class="sxs-lookup"><span data-stu-id="9257a-p104">If Yahoo! Small Business has been your DNS hosting provider, you should be aware that your provider is now Aabaco Small Business.</span></span>
  
<span data-ttu-id="9257a-110">Siga as etapas neste artigo para criar uma conta na Aabaco, onde você pode fazer alterações de DNS e renovar seus domínios.</span><span class="sxs-lookup"><span data-stu-id="9257a-110">Follow the steps in this article to create an account at Aabaco, where you can make DNS changes and renew your domain or domains.</span></span>
  
<span data-ttu-id="9257a-111">Você deve criar sua conta da Aabaco antes de criar [registros DNS.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="9257a-111">You must create your Aabaco account before you can [create DNS records](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

  
## <a name="create-an-aabaco-small-business-account"></a><span data-ttu-id="9257a-112">Criar uma conta na Aabaco Small Business</span><span class="sxs-lookup"><span data-stu-id="9257a-112">Create an Aabaco Small Business account</span></span>

1. <span data-ttu-id="9257a-113">To get started, go to your domains page at Aabaco by using [this link](https://www.luminate.com/services/), and select Setup **your Aabaco Small Business account**.</span><span class="sxs-lookup"><span data-stu-id="9257a-113">To get started, go to your domains page at Aabaco by using [this link](https://www.luminate.com/services/), and select **Setup your Aabaco Small Business account**.</span></span>
    
    ![Selecione Configurar sua conta da Aabaco Small Business](../../media/d708f272-d42f-40a1-9aaf-d05d8cfd55cf.png)
  
2. <span data-ttu-id="9257a-115">Forneça o Email/ID do Yahoo do Yahoo!</span><span class="sxs-lookup"><span data-stu-id="9257a-115">Provide your Yahoo!</span></span> <span data-ttu-id="9257a-116">Small Business **Email/Yahoo ID** e, em seguida, selecione **I'm not a robot**.</span><span class="sxs-lookup"><span data-stu-id="9257a-116">Small Business **Email/Yahoo ID**, and then select **I'm not a robot**.</span></span>
    
    ![Select I am not a robot](../../media/ded4b5dd-4e04-4baa-ae31-8426b5799151.png)
  
3. <span data-ttu-id="9257a-118">Selecione **Iniciar.**</span><span class="sxs-lookup"><span data-stu-id="9257a-118">Select **Get started**.</span></span>
    
    ![Select Get started](../../media/6674707d-c222-4f0d-bec4-229d39ab2499.png)
  
4. <span data-ttu-id="9257a-p106">Entre na sua conta de email do Yahoo! Small Business e abra o novo email da Aabaco Small Business.</span><span class="sxs-lookup"><span data-stu-id="9257a-p106">Sign in to your Yahoo! Small Business email account and open the new email from Aabaco Small Business.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9257a-122">Reenvie a mensagem, se necessário, escolhendo a opção **Reenviar o link de email** na página **Você tem email**.</span><span class="sxs-lookup"><span data-stu-id="9257a-122">Resend the message, if necessary, by choosing the **resend the email link** on the **You've got mail** page.</span></span> 
  
    ![The You've got mail page](../../media/2e02fc30-6cca-40d6-bb64-131a41b4a369.png)
  
5. <span data-ttu-id="9257a-124">Na Aabaco **Confirme seu endereço de email para continuar a configurar** a mensagem de email, selecione Confirmar **email.**</span><span class="sxs-lookup"><span data-stu-id="9257a-124">In the Aabaco **Confirm your email address to continue setup** email message, select **Confirm email**.</span></span>
    
    ![Selecionar Confirmar email](../../media/eb5f5526-6f90-4a10-83a7-5249a1ebd562.png)
  
6. <span data-ttu-id="9257a-126">Na página **Escolha sua senha**, digite ou copie e cole a senha que você deseja usar para sua conta da Aabaco.</span><span class="sxs-lookup"><span data-stu-id="9257a-126">On the **Choose your password** page, type or copy and paste the password that you want to use for your Aabaco account.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="9257a-p107">Você pode usar a mesma senha usada na conta do Yahoo! Small Business.</span><span class="sxs-lookup"><span data-stu-id="9257a-p107">You can use the same password that you used with your Yahoo! Small Business account.</span></span> 
  
    ![The Choose your password page](../../media/cc592345-72d1-4a41-9410-a1f3345cfd1d.png)
  
7. <span data-ttu-id="9257a-130">Selecione **I agree to the terms and conditions**, and then select Create **password**.</span><span class="sxs-lookup"><span data-stu-id="9257a-130">Select **I agree to the terms and conditions**, and then select **Create password**.</span></span>
    
    ![Selecione Criar senha](../../media/434aa6a3-076e-4abf-a9cf-31145786e819.png)
  
8. <span data-ttu-id="9257a-p108">Entre na sua conta de email do Yahoo! Small Business e, em seguida, abra o novo email da Aabaco Small Business.</span><span class="sxs-lookup"><span data-stu-id="9257a-p108">Sign in to your Yahoo! Small Business email account, and then open the new email from Aabaco Small Business.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9257a-p109">Reenvie a mensagem, se necessário, escolhendo a opção **Reenviar o link de email** na página **Está quase acabando!**.</span><span class="sxs-lookup"><span data-stu-id="9257a-p109">Resend the message, if necessary, by choosing the **resend the email link** on the **You're almost done!** page.</span></span> 
  
    ![The You're almost done page](../../media/1a4142a3-e140-48a8-9c80-aa126ff08179.png)
  
9. <span data-ttu-id="9257a-137">In the Aabaco **You're almost there** email message, select **Activate my account**.</span><span class="sxs-lookup"><span data-stu-id="9257a-137">In the Aabaco **You're almost there** email message, select **Activate my account**.</span></span>
    
    ![Selecionar Ativar minha conta](../../media/e76d5edc-d8ba-4d8d-872d-d916716c3618.png)
  
10. <span data-ttu-id="9257a-139">Entre na conta da Aabaco Small Business.</span><span class="sxs-lookup"><span data-stu-id="9257a-139">Sign in to your Aabaco Small Business account.</span></span>
    
    ![The sign-in page for Aabaco Small Business](../../media/4ef3cfc3-26da-4e03-932b-9346ef217848.png)
  
<span data-ttu-id="9257a-141">Agora que você criou sua conta da Aabaco, pode criar registros DNS na [Aabaco Small Business para a Microsoft.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="9257a-141">Now that you have created your Aabaco account, you can [Create DNS records at Aabaco Small Business for Microsoft](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>
  
