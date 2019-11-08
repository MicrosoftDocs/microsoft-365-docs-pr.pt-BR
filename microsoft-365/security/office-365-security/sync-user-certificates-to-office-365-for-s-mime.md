---
title: Sincronizar certificados de usuário com o Office 365 para S/MIME
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
description: Antes que alguém possa enviar mensagens protegidas por S/MIME, os certificados adequados deverão ser configurados. Para enviar mensagens criptografadas por meio do Exchange Online, o programa de email do destinatário usa o certificado público do destinatário para criptografar a mensagem. Este certificado X.509 público deve ser publicado no Office 365.
ms.openlocfilehash: 7b42f757ade54e362afc65f920096252bf69eb31
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38030835"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="1da84-105">Sincronizar certificados de usuário com o Office 365 para S/MIME</span><span class="sxs-lookup"><span data-stu-id="1da84-105">Sync user certificates to Office 365 for S/MIME</span></span>

<span data-ttu-id="1da84-106">Antes que qualquer pessoa possa enviar mensagens S/MIME protegidas no Exchange Online, os certificados apropriados devem ser configurados.</span><span class="sxs-lookup"><span data-stu-id="1da84-106">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="1da84-107">Para enviar mensagens criptografadas por meio do Exchange Online, o aplicativo de email do remetente usa o certificado público do destinatário para criptografar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="1da84-107">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="1da84-108">Este certificado X.509 público deve ser publicado no Office 365.</span><span class="sxs-lookup"><span data-stu-id="1da84-108">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="1da84-109">Para sincronizar certificados que dão suporte a S/MIME</span><span class="sxs-lookup"><span data-stu-id="1da84-109">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="1da84-110">Comece a configurar o S/MIME emitindo certificados e publicando-os em seu Serviço de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1da84-110">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="1da84-111">Para obter mais informações sobre o gerenciamento de certificados no Exchange Server, consulte [certificados digitais e SSL](https://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx).</span><span class="sxs-lookup"><span data-stu-id="1da84-111">For more information about managing certificates in Exchange Server, see [Digital Certificates and SSL](https://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx).</span></span>

<span data-ttu-id="1da84-112">Depois que os certificados forem publicados, use a ferramenta de sincronização do Azure Active Directory para sincronizar os dados do usuário do seu ambiente local do Exchange para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="1da84-112">After your certificates are published, use the Azure Active Directory Sync tool to synchronize user data from your on-premises Exchange environment to Office 365.</span></span> <span data-ttu-id="1da84-113">Para obter mais informações sobre esse processo, consulte [DirSync: versão da ferramenta de sincronização de diretório do histórico de versões](https://go.microsoft.com/fwlink/p/?LinkId=392587).</span><span class="sxs-lookup"><span data-stu-id="1da84-113">For more information on this process, see [DirSync: Directory Sync Tool Version Release History](https://go.microsoft.com/fwlink/p/?LinkId=392587).</span></span>

<span data-ttu-id="1da84-114">Juntamente com a sincronização de outros dados de diretório, para fins S/MIME, a ferramenta sincronizará os atributos **userCertificate** e **userSMIMECertificate** para cada objeto user, de forma que os dados possam ser usados para assinar e criptografar mensagens.</span><span class="sxs-lookup"><span data-stu-id="1da84-114">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="1da84-115">Mais informações</span><span class="sxs-lookup"><span data-stu-id="1da84-115">More Information</span></span>

[<span data-ttu-id="1da84-116">S/MIME para assinatura e criptografia de mensagens</span><span class="sxs-lookup"><span data-stu-id="1da84-116">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="1da84-117">Ferramenta de sincronização do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="1da84-117">Azure Active Directory Sync tool</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=392587)
