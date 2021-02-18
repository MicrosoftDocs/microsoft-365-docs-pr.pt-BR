---
title: S/MIME para criptografia no Exchange Online - Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: Os administradores podem aprender a usar S/MIME (Secure/Multipurpose Internet Mail Extensions) no Exchange Online para criptografar emails e assiná-los digitalmente.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 35266b4ceefe161b907ddbc955fd234b716792a6
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288568"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>S/MIME para assinatura e criptografia de mensagens no Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


S/MIME (Secure/Multipurpose Internet Mail Extensions) é um método amplamente aceito (ou, mais precisamente, um protocolo) para enviar mensagens assinadas digitalmente e criptografadas. S/MIME permite que você criptografe email e os assine digitalmente. Quando você usa S/MIME com uma mensagem de email, isso ajuda as pessoas que recebem essa mensagem a ter certeza de que o que veem em suas caixas de entrada é a mensagem exata que partiu do remetente. Isso também ajudará as pessoas que receberem mensagens a terem certeza de que a mensagem veio do remetente específico e não de alguém fingindo ser o remetente. Para fazer isso, S/MIME presta serviços de segurança criptográfica como autenticação, integridade da mensagem e não recusa da origem (usando assinaturas digitais). Isso também ajuda a melhorar a privacidade e a segurança dos dados (usando criptografia) para mensagens eletrônicas. Para obter informações mais completas sobre o histórico e a arquitetura de S/MIME no contexto de email, consulte [Compreendendo S/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65)).

Como administrador do Exchange Online, você pode habilitar a segurança baseada em S/MIME para as caixas de correio em sua organização. Use as diretrizes nos tópicos vinculados aqui junto com o PowerShell do Exchange Online para configurar S/MIME. Para usar S/MIME em clientes de email com suporte, os usuários em sua organização devem ter certificados emitidos para fins de assinatura e criptografia e dados publicados em seu Active Directory Domain Service (AD DS) local. Seu AD DS deve estar localizado em computadores em um local físico que você controla e não em uma instalação remota ou serviço baseado em nuvem em algum lugar na internet. Para obter mais informações sobre o AD DS, consulte a Visão geral dos [Serviços de Domínio Active Directory.](https://docs.microsoft.com/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview)

## <a name="supported-scenarios-and-technical-considerations"></a>Cenários suportados e considerações técnicas

Você pode configurar s/MIME para trabalhar com qualquer um dos seguintes pontos de extremidade:

- Outlook 2010 ou posterior
- Outlook na Web (anteriormente conhecido como Outlook Web App)
- Exchange ActiveSync (EAS)

As etapas que você seguir para configurar S/MIME com cada um desses pontos de extremidade são ligeiramente diferentes. Geralmente, você precisará fazer as seguintes etapas:

1. Instalar uma Autoridade de Certificação (CA) baseada no Windows e configurar uma infraestrutura de chave pública para emitir certificados S/MIME. Também há suporte para certificados emitidos por provedores de certificados de terceiros. Para obter detalhes, consulte [Visão Geral dos Serviços de Certificados do Active Directory](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11)).

   **Observações**:

   - Os certificados emitidos por uma CA de terceiros têm a vantagem de serem automaticamente confiáveis por todos os clientes e dispositivos. Certificados emitidos por uma CA interna privada não são confiáveis automaticamente por clientes e dispositivos, e nem todos os dispositivos (por exemplo, telefones) podem ser configurados para confiar em certificados privados.

   - Considere usar um certificado intermediário em vez do certificado raiz para emitir certificados aos usuários. Dessa forma, se você precisar revogar e reemitar certificados, o certificado raiz ainda está intacto.

2. Publique o certificado de usuário em uma conta do AD DS local nos atributos **UserSMIMECertificate** e/ou **UserCertificate.**

3. Para organizações do Exchange Online, sincronizou os certificados de usuário do AD DS com o Azure Active Directory usando uma versão apropriada do Azure AD Connect. Em seguida, esses certificados serão sincronizados do Active Directory do Azure para o diretório do Exchange Online e serão usados ao criptografar uma mensagem para um destinatário.

4. Configurar uma coletânea de certificados virtuais para validar S/MIME. Essas informações são usadas pelo Outlook na Web ao validar a assinatura de um email e garantir que ele foi assinado por um certificado confiável.

5. Configurar o ponto final do Outlook ou EAS para usar S/MIME.

> [!NOTE]
> Você não pode instalar o controle S/MIME no Outlook na Web no Mac, iOS, Android ou outros dispositivos que não são do Windows. Para obter mais informações, [consulte Criptografar mensagens usando S/MIME no Outlook na Web.](https://support.microsoft.com/office/878c79fc-7088-4b39-966f-14512658f480)

## <a name="set-up-smime-with-outlook-on-the-web"></a>Configurar S/MIME com o Outlook na Web

A configuração de S/MIME para o Exchange Online com o Outlook na Web envolve as seguintes etapas principais:

1. [Definir as configurações de S/MIME para o Outlook Web](configure-s-mime-settings-for-outlook-web-app.md)
2. [Configurar coleção de certificados virtuais para validar S/MIME](set-up-virtual-certificate-collection-to-validate-s-mime.md)
3. [Sincronizar certificados de usuário com o Office 365 para S/MIME](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>Tecnologias de criptografia de mensagem relacionadas

À medida que a segurança das mensagens se torna mais importante, os administradores precisam entender os princípios e conceitos de mensagens seguras. Essa compreensão é especialmente importante devido à crescente variedade de tecnologias relacionadas à proteção (incluindo S/MIME) disponíveis. Para compreender mais sobre S/MIME e como ele funciona no contexto de email, consulte [Compreendendo S/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65)). Várias tecnologias de criptografia trabalham em conjunto para oferecer proteção para mensagens em repouso ou em trânsito. O S/MIME pode trabalhar simultaneamente com as seguintes tecnologias, mas não depende delas:

- O **Transport Layer Security (TLS)** criptografa o túnel ou a rota entre servidores de email para ajudar a impedir a interceptação e a escuta não autorizada.

- **SSL (Secure Sockets Layer)** criptografa a conexão entre clientes de email e servidores do Microsoft 365.

- O **BitLocker** criptografa os dados em um disco rígido de um datacenter, de forma que se alguém obtiver acesso não autorizado, não poderá lê-lo.

### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME em comparação com o Office 365 Message Encryption

S/MIME requer uma infraestrutura de certificado e publicação que é geralmente usada em situações entre empresas e entre empresas e consumidores. O usuário controla as chaves criptográficas no S/MIME e pode escolher se as usará para cada mensagem que enviar. Programas de email como o Outlook procuram um local de autoridade de certificado raiz confiável para realizar a assinatura digital e a verificação da assinatura. O Office 365 Message Encryption é um serviço de criptografia baseado em políticas que pode ser configurado por um administrador, e não um usuário individual, para criptografar email enviado a qualquer pessoa dentro ou fora da organização. É um serviço online que é desenvolvido no Azure Rights Management (RMS) e não conta com uma infraestrutura de chave pública. O Office 365 Message Encryption também oferece recursos adicionais, como o recurso para personalizar o email com a marca da organização. Para saber mais sobre a Criptografia de Mensagens do Office 365, confira [Criptografia no Office 365.](../../compliance/encryption.md)

## <a name="more-information"></a>Mais informações

[Outlook na Web](https://docs.microsoft.com/exchange/exchange-admin-center)

[Email Seguro (2000)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))
