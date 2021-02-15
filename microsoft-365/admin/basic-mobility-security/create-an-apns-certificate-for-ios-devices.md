---
title: Criar um certificado de APNs para dispositivos iOS
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
description: Gerencie dispositivos iOS em Mobilidade Básica e Segurança.
ms.openlocfilehash: 85baef2defa79255d560f848e57120353fd4fa2e
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877075"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="a8829-103">Criar um certificado de APNs para dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="a8829-103">Create an APNs certificate for iOS devices</span></span>

<span data-ttu-id="a8829-104">Para gerenciar dispositivos iOS, como iPads e iPhones, no Basic Mobility and Security, crie um certificado APNs.</span><span class="sxs-lookup"><span data-stu-id="a8829-104">To manage iOS devices such as iPads and iPhones in Basic Mobility and Security, create an APNs certificate.</span></span>

1. <span data-ttu-id="a8829-105">Entre no Microsoft 365 com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="a8829-105">Sign in to Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="a8829-106">No navegador, digite  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="a8829-106">In your browser, type [https://protection.office.com](https://protection.office.com/).</span></span>

3. <span data-ttu-id="a8829-107">Selecione  **Prevenção contra perda de** dados Gerenciamento   >  **de** dispositivos e escolha Certificado **APNs para dispositivos iOS.**</span><span class="sxs-lookup"><span data-stu-id="a8829-107">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>

4. <span data-ttu-id="a8829-108">Na página Configurações do Certificado de Notificação por Push da Apple, escolha **Avançar.**</span><span class="sxs-lookup"><span data-stu-id="a8829-108">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>

5. <span data-ttu-id="a8829-109">Selecione Baixar seu arquivo CSR e salve a solicitação de assinatura de certificado em algum lugar do computador que você lembrará.</span><span class="sxs-lookup"><span data-stu-id="a8829-109">Select Download your CSR file and save the certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="a8829-110">Selecione  **Next**.</span><span class="sxs-lookup"><span data-stu-id="a8829-110">Select  **Next**.</span></span>

6. <span data-ttu-id="a8829-111">Na página Criar um certificado APNs:</span><span class="sxs-lookup"><span data-stu-id="a8829-111">On the Create an APNs certificate page:</span></span>  

    1. <span data-ttu-id="a8829-112">Selecione o Apple APNS Portal para abrir o Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="a8829-112">Select  Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>

    2. <span data-ttu-id="a8829-113">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="a8829-113">Sign in with an Apple ID.</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="a8829-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="a8829-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

    3. <span data-ttu-id="a8829-116">Selecione  **Criar um Certificado** e aceite os Termos de   Uso.</span><span class="sxs-lookup"><span data-stu-id="a8829-116">Select  **Create a Certificate**  and accept the Terms of Use.</span></span>

    4. <span data-ttu-id="a8829-117">Navegue até a solicitação de assinatura de certificado que você baixou para seu computador no Microsoft 365 e selecione **Carregar.**</span><span class="sxs-lookup"><span data-stu-id="a8829-117">Browse to the certificate signing request you downloaded to your computer from Microsoft 365, and select **Upload**.</span></span>

        <span data-ttu-id="a8829-118">Baixe o certificado APNs criado pelo Apple Push Certificate Portal para seu computador.</span><span class="sxs-lookup"><span data-stu-id="a8829-118">Download the APNs certificate created by the Apple Push Certificate Portal to your computer.</span></span>

       >[!TIP]
       ><span data-ttu-id="a8829-119">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="a8829-119">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="a8829-120">Volte para o Microsoft 365 e selecione **Próximo** para chegar à página Carregar   certificado   **APNS.**  </span><span class="sxs-lookup"><span data-stu-id="a8829-120">Go back to Microsoft 365, and select **Next**  to get to the  **Upload APNS certificate** page.</span></span>

8. <span data-ttu-id="a8829-121"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="a8829-121">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>

9. <span data-ttu-id="a8829-122">Selecione  **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="a8829-122">Select  **Finish**.</span></span>

<span data-ttu-id="a8829-123">Para concluir a configuração, volte para o Centro de  \*\*\*\* Conformidade & segurança >políticas de segurança gerenciamento de   >  \*\*\*\*   >  **dispositivos Gerenciar configurações.**</span><span class="sxs-lookup"><span data-stu-id="a8829-123">To complete setup, go back to the Security & Compliance Center > **Security policies** > **Device management** > **Manage settings**.</span></span>
