---
title: Sincronizar certificados de usuário com o Office 365 para S/MIME
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
ms.custom:
- seo-marvel-apr2020
description: Neste artigo, você aprenderá a publicar certificados apropriados para o Office 365 antes de enviar mensagens protegidas por S/MIME no Exchange Online.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 387f9f405afd45254c6568aa92334a7ee5b4171f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053120"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="b0930-103">Sincronizar certificados de usuário com o Office 365 para S/MIME</span><span class="sxs-lookup"><span data-stu-id="b0930-103">Sync user certificates to Office 365 for S/MIME</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b0930-104">Antes que qualquer pessoa possa enviar mensagens protegidas por S/MIME no Exchange Online, os certificados apropriados devem ser definidos.</span><span class="sxs-lookup"><span data-stu-id="b0930-104">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="b0930-105">Para enviar mensagens criptografadas por meio do Exchange Online, o aplicativo de email do remetente usa o certificado público do destinatário para criptografar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="b0930-105">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="b0930-106">Este certificado X.509 público deve ser publicado no Office 365.</span><span class="sxs-lookup"><span data-stu-id="b0930-106">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="b0930-107">Para sincronizar certificados que dão suporte a S/MIME</span><span class="sxs-lookup"><span data-stu-id="b0930-107">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="b0930-108">Comece a configurar o S/MIME emitindo certificados e publicando-os em seu Serviço de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b0930-108">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="b0930-109">Para obter mais informações, confira [Visão geral de Serviços de Certificados do Active Directory](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="b0930-109">For more information, see [Active Directory Certificate Services Overview](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span></span>

<span data-ttu-id="b0930-110">Depois que seus certificados são publicados, use a ferramenta do Azure AD Connect para sincronizar os dados do usuário do seu ambiente local do Exchange com o Office 365.</span><span class="sxs-lookup"><span data-stu-id="b0930-110">After your certificates are published, use the Azure AD Connect tool to synchronize user data from your on-premises Exchange environment to Office 365.</span></span> <span data-ttu-id="b0930-111">Para obter mais informações sobre esse processo, consulte [Sincronização do Azure AD Connect: Compreender e personalizar a sincronização](/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span><span class="sxs-lookup"><span data-stu-id="b0930-111">For more information on this process, see [Azure AD Connect sync: Understand and customize synchronization](/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

<span data-ttu-id="b0930-112">Juntamente com a sincronização de outros dados de diretório, para fins S/MIME, a ferramenta sincronizará os atributos  **userCertificate** e **userSMIMECertificate** para cada objeto de usuário para que os dados possam ser usados para assinar e criptografar mensagens.</span><span class="sxs-lookup"><span data-stu-id="b0930-112">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="b0930-113">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="b0930-113">More Information</span></span>

[<span data-ttu-id="b0930-114">S/MIME para assinatura e criptografia de mensagens</span><span class="sxs-lookup"><span data-stu-id="b0930-114">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="b0930-115">O que é o Azure AD Connect?</span><span class="sxs-lookup"><span data-stu-id="b0930-115">What is Azure AD Connect?</span></span>](/azure/active-directory/hybrid/whatis-azure-ad-connect)