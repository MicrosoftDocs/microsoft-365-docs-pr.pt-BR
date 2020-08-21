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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
ms.custom:
- seo-marvel-apr2020
description: Neste artigo, você aprenderá como publicar certificados apropriados no Office 365 antes de enviar mensagens protegidas por S/MIME no Exchange Online.
ms.openlocfilehash: 634b65e45b01186a27f9ae61c91d4b27f1a11635
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826476"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>Sincronizar certificados de usuário com o Office 365 para S/MIME

Antes que qualquer pessoa possa enviar mensagens S/MIME protegidas no Exchange Online, os certificados apropriados devem ser configurados. Para enviar mensagens criptografadas por meio do Exchange Online, o aplicativo de email do remetente usa o certificado público do destinatário para criptografar a mensagem. Este certificado X.509 público deve ser publicado no Office 365.

## <a name="to-sync-certificates-that-support-smime"></a>Para sincronizar certificados que dão suporte a S/MIME

Comece a configurar o S/MIME emitindo certificados e publicando-os em seu Serviço de domínio do Active Directory. Para obter mais informações, confira [Visão geral de Serviços de Certificados do Active Directory](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).

Depois que os certificados forem publicados, use a ferramenta Azure AD Connect para sincronizar os dados do usuário do seu ambiente local do Exchange para o Office 365. Para obter mais informações sobre esse processo, confira [sincronização do Azure ad Connect: entender e personalizar a sincronização](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).

Juntamente com a sincronização de outros dados de diretório, para fins S/MIME, a ferramenta sincronizará os atributos  **userCertificate** e **userSMIMECertificate** para cada objeto user, de forma que os dados possam ser usados para assinar e criptografar mensagens.

## <a name="more-information"></a>Informações adicionais

[S/MIME para assinatura e criptografia de mensagens](s-mime-for-message-signing-and-encryption.md)

[O que é o Azure AD Connect?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
