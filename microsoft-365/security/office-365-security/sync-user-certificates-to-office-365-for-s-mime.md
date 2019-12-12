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
ms.openlocfilehash: caf5c3694034f3415b42f3b09302b6605fbf09cb
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970087"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>Sincronizar certificados de usuário com o Office 365 para S/MIME

Antes que qualquer pessoa possa enviar mensagens S/MIME protegidas no Exchange Online, os certificados apropriados devem ser configurados. Para enviar mensagens criptografadas por meio do Exchange Online, o aplicativo de email do remetente usa o certificado público do destinatário para criptografar a mensagem. Este certificado X.509 público deve ser publicado no Office 365.

## <a name="to-sync-certificates-that-support-smime"></a>Para sincronizar certificados que dão suporte a S/MIME

Comece a configurar o S/MIME emitindo certificados e publicando-os em seu Serviço de domínio do Active Directory. Para obter mais informações, confira [Visão geral de Serviços de Certificados do Active Directory](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).

Depois que os certificados forem publicados, use a ferramenta Azure AD Connect para sincronizar os dados do usuário do seu ambiente local do Exchange para o Office 365. Para obter mais informações sobre esse processo, confira [sincronização do Azure ad Connect: entender e personalizar a sincronização](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).

Juntamente com a sincronização de outros dados de diretório, para fins S/MIME, a ferramenta sincronizará os atributos **userCertificate** e **userSMIMECertificate** para cada objeto user, de forma que os dados possam ser usados para assinar e criptografar mensagens.

## <a name="more-information"></a>Mais informações

[S/MIME para assinatura e criptografia de mensagens](s-mime-for-message-signing-and-encryption.md)

[O que é o Azure AD Connect?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
