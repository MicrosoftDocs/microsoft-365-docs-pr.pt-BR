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
description: Gerencie dispositivos iOS em Mobilidade Básica e Segurança.
ms.openlocfilehash: 85baef2defa79255d560f848e57120353fd4fa2e
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877075"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>Criar um certificado APNs para dispositivos iOS

Para gerenciar dispositivos iOS, como iPads e iPhones, no Basic Mobility and Security, crie um certificado APNs.

1. Entre no Microsoft 365 com sua conta de administrador global.

2. No navegador, digite  [https://protection.office.com](https://protection.office.com/) .

3. Selecione  **Prevenção contra perda de** dados Gerenciamento   >  **de** dispositivos e escolha Certificado **APNs para dispositivos iOS.**

4. Na página Configurações do Certificado de Notificação por Push da Apple, escolha **Avançar.**

5. Selecione Baixar seu arquivo CSR e salve a solicitação de assinatura de certificado em algum lugar do computador que você lembrará. Selecione  **Next**.

6. Na página Criar um certificado APNs:  

    1. Selecione o Apple APNS Portal para abrir o Apple Push Certificates Portal.

    2. Sign in with an Apple ID.

    >[!IMPORTANT]
    >Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    3. Selecione  **Criar um Certificado** e aceite os Termos de   Uso.

    4. Navegue até a solicitação de assinatura de certificado que você baixou para seu computador no Microsoft 365 e selecione **Carregar.**

        Baixe o certificado APNs criado pelo Apple Push Certificate Portal para seu computador.

       >[!TIP]
       >If you're having trouble downloading the certificate, refresh your browser.

7. Volte para o Microsoft 365 e selecione **Próximo** para chegar à página Carregar   certificado   **APNS.**  

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. Selecione  **Concluir**.

Para concluir a configuração, volte para o Centro de  **** Conformidade & segurança >políticas de segurança gerenciamento de   >  ****   >  **dispositivos Gerenciar configurações.**
