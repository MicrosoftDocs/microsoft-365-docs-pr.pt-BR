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
# <a name="create-an-apns-certificate-for-ios-devices"></a>Criar um certificado APNs para dispositivos iOS

Para gerenciar dispositivos iOS, como iPads e iPhones, em mobilidade básica e segurança, crie um certificado APNs.

1. Entre no Microsoft 365 com sua conta de administrador global.
    
2. Em seu navegador, digite  [https://protection.office.com](https://protection.office.com/) .
    
3. Selecione gerenciamento de dispositivo de  **prevenção contra perda de dados**   >  **Device management**e escolha **certificado APNs para dispositivos IOS**.    

4. Na página Configurações de certificado de notificação por push da Apple, escolha **Avançar**.
    
5. Selecione baixar seu arquivo CSR e salvar a solicitação de assinatura de certificado em algum lugar no seu computador que você se lembrará. Selecione  **Avançar**.
    
6. Na página criar um certificado APNs:  

    1. Selecione portal Apple APNS para abrir o portal Apple Push Certificates.
    
    2. Sign in with an Apple ID.   

    >[!IMPORTANT]
    >Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    3. Selecione  **criar um certificado**   e aceitar os termos de uso.
    
    4. Navegue até a solicitação de assinatura de certificado que você baixou para seu computador da Microsoft 365 e selecione **carregar**.
    
        Baixe o certificado APNs criado pelo portal de certificado por push da Apple para seu computador.
    
       >[!TIP]
       >If you're having trouble downloading the certificate, refresh your browser.

7. Volte para o Microsoft 365 e selecione **Avançar**   para acessar a página  **carregar certificado APNS**   .
    
8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.
    
9. Selecione  **concluir**.
    
Para concluir a instalação, volte à segurança & centro de conformidade >gerenciamento de dispositivo de  **políticas de segurança**   >  **Device management**   >  **Gerenciar definições**.
