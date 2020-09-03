---
title: Criar um certificado APNs para dispositivos iOS
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Gerenciar dispositivos iOS em mobilidade básica e segurança.
ms.openlocfilehash: 8b41c1c6c891a5d6cb98a6a381c65aa0310a1761
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336719"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="057d1-103">Criar um certificado APNs para dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="057d1-103">Create an APNs certificate for iOS devices</span></span>

<span data-ttu-id="057d1-104">Para gerenciar dispositivos iOS, como iPads e iPhones, em mobilidade básica e segurança, crie um certificado APNs.</span><span class="sxs-lookup"><span data-stu-id="057d1-104">To manage iOS devices such as iPads and iPhones in Basic Mobility and Security, create an APNs certificate.</span></span>

1. <span data-ttu-id="057d1-105">Entre no Microsoft 365 com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="057d1-105">Sign in to Microsoft 365 with your global admin account.</span></span>
    
2. <span data-ttu-id="057d1-106">Em seu navegador, digite  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="057d1-106">In your browser, type [https://protection.office.com](https://protection.office.com/).</span></span>
    
3. <span data-ttu-id="057d1-107">Selecione gerenciamento de dispositivo de  **prevenção contra perda de dados**   >  **Device management**e escolha **certificado APNs para dispositivos IOS**.</span><span class="sxs-lookup"><span data-stu-id="057d1-107">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>    

4. <span data-ttu-id="057d1-108">Na página Configurações de certificado de notificação por push da Apple, escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="057d1-108">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>
    
5. <span data-ttu-id="057d1-109">Selecione baixar seu arquivo CSR e salvar a solicitação de assinatura de certificado em algum lugar no seu computador que você se lembrará.</span><span class="sxs-lookup"><span data-stu-id="057d1-109">Select Download your CSR file and save the certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="057d1-110">Selecione  **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="057d1-110">Select  **Next**.</span></span>
    
6. <span data-ttu-id="057d1-111">Na página criar um certificado APNs:</span><span class="sxs-lookup"><span data-stu-id="057d1-111">On the Create an APNs certificate page:</span></span>  

    1. <span data-ttu-id="057d1-112">Selecione portal Apple APNS para abrir o portal Apple Push Certificates.</span><span class="sxs-lookup"><span data-stu-id="057d1-112">Select  Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>
    
    2. <span data-ttu-id="057d1-113">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="057d1-113">Sign in with an Apple ID.</span></span>   

    >[!IMPORTANT]
    ><span data-ttu-id="057d1-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="057d1-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

    3. <span data-ttu-id="057d1-116">Selecione  **criar um certificado**   e aceitar os termos de uso.</span><span class="sxs-lookup"><span data-stu-id="057d1-116">Select  **Create a Certificate**  and accept the Terms of Use.</span></span>
    
    4. <span data-ttu-id="057d1-117">Navegue até a solicitação de assinatura de certificado que você baixou para seu computador da Microsoft 365 e selecione **carregar**.</span><span class="sxs-lookup"><span data-stu-id="057d1-117">Browse to the certificate signing request you downloaded to your computer from Microsoft 365, and select **Upload**.</span></span>
    
        <span data-ttu-id="057d1-118">Baixe o certificado APNs criado pelo portal de certificado por push da Apple para seu computador.</span><span class="sxs-lookup"><span data-stu-id="057d1-118">Download the APNs certificate created by the Apple Push Certificate Portal to your computer.</span></span>
    
       >[!TIP]
       ><span data-ttu-id="057d1-119">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="057d1-119">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="057d1-120">Volte para o Microsoft 365 e selecione **Avançar**   para acessar a página  **carregar certificado APNS**   .</span><span class="sxs-lookup"><span data-stu-id="057d1-120">Go back to Microsoft 365, and select **Next**  to get to the  **Upload APNS certificate** page.</span></span>
    
8. <span data-ttu-id="057d1-121"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="057d1-121">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>
    
9. <span data-ttu-id="057d1-122">Selecione  **concluir**.</span><span class="sxs-lookup"><span data-stu-id="057d1-122">Select  **Finish**.</span></span>
    
<span data-ttu-id="057d1-123">Para concluir a instalação, volte à segurança & centro de conformidade >gerenciamento de dispositivo de  **políticas de segurança**   >  **Device management**   >  **Gerenciar definições**.</span><span class="sxs-lookup"><span data-stu-id="057d1-123">To complete setup, go back to the Security & Compliance Center > **Security policies** > **Device management** > **Manage settings**.</span></span>
