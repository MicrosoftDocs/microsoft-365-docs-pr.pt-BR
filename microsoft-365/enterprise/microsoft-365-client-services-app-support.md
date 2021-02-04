---
title: Suporte a aplicativos de cliente e serviços do Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: Neste artigo, encontre detalhes sobre o suporte a aplicativos de cliente e serviços do Microsoft 365.
ms.openlocfilehash: 4e32e39281175ed66970a358ff632c2ddbb3ac1a
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097457"
---
# <a name="microsoft-365-client-and-services-app-support"></a>Suporte a aplicativos de cliente e serviços do Microsoft 365

A Microsoft oferece suporte a uma ampla variedade de recursos de segurança, autenticação e conformidade para manter os dados do cliente seguros e permite que os administradores de IT personalizem políticas no Centro de administração do Microsoft 365 para seus usuários. Os recursos a seguir são apenas um subconjunto dos muitos recursos corporativos que você pode configurar dependendo da sua assinatura do Microsoft 365.

## <a name="client-and-service-support"></a>Suporte a cliente e serviço

### <a name="continuous-access-evaluation-preview"></a>Avaliação de acesso contínuo (visualização)

A avaliação de acesso contínuo é implementada habilitando serviços, como o Exchange Online, o SharePoint Online e o Teams, para assinar eventos críticos no Azure Active Directory para que esses eventos possam ser avaliados e aplicados quase em tempo real. A avaliação de eventos críticos não depende das políticas de Acesso Condicional, portanto, está disponível em qualquer locatário.

Os seguintes eventos são avaliados no momento:

- Uma conta de usuário é excluída ou desabilitada
- A senha de um usuário é alterada ou redefinida
- A autenticação multifa factor está habilitada para o usuário
- O administrador revoga explicitamente todos os tokens de atualização para um usuário
- Risco elevado do usuário detectado pelo Azure AD Identity Protection

Para obter mais informações sobre a avaliação de acesso contínuo para suporte a aplicativos de cliente e serviços, consulte [avaliação de acesso contínuo (visualização).](/azure/active-directory/conditional-access/concept-continuous-access-evaluation)

## <a name="client-support"></a>Suporte ao cliente

### <a name="certificate-based-authentication"></a>Autenticação baseada em certificados

A autenticação baseada em certificado (CBA) é o uso de um certificado digital para identificar um usuário, computador ou dispositivo antes de conceder acesso a um recurso, rede, aplicativo ou serviço. Na autenticação do usuário, ela geralmente é implantada em coordenação com métodos tradicionais, como nomes de usuário e senhas.

Algumas soluções tradicionais só funcionam para usuários, como biometria e senhas únicas (OTP). Com a autenticação baseada em certificado, a mesma solução pode ser usada para todos os pontos de extremidade; usuários, dispositivos e a Crescente Internet das Coisas (IoT).

Para obter mais informações sobre a autenticação baseada em certificado para suporte a aplicativos de cliente e serviços, consulte Suporte ao aplicativo cliente [do Microsoft 365:](microsoft-365-client-support-certificate-based-authentication.md)autenticação baseada em certificado.

### <a name="conditional-access"></a>Acesso Condicional

O Acesso Condicional é a ferramenta usada pelo Azure Active Directory para reunir sinais, tomar decisões e impor políticas de acesso organizacional. O Acesso Condicional está no centro do novo modelo de controle controlado por identidade.

As políticas de Acesso Condicional são instruções if-then para conceder acesso aos recursos. Se um usuário quiser acessar um recurso, ele deverá concluir uma ação. Sinais comuns que o Acesso Condicional pode usar ao tomar uma decisão de acesso à política incluem:

- Associação de usuário ou grupo
- Informações de localização IP
- Informações do dispositivo
- Informações do aplicativo
- Detecção de risco em tempo real e calculada
- MCAS (Microsoft Cloud App Security)

Ao tomar essas decisões de acesso, as políticas podem tomar ações diferentes:

- A política pode bloquear o acesso: essa configuração é a ação mais restritiva e impede que o usuário acesse o recurso.
- A política pode conceder acesso: essa configuração é uma decisão menos restritiva e ainda pode exigir uma ou mais das seguintes opções:

    - Autenticação multifator
    - O dispositivo a ser marcado como compatível
    - O dispositivo é híbrido ingressado no Azure AD
    - Um aplicativo cliente aprovado
    - Política de proteção de aplicativo configurada (visualização)

Para obter mais informações sobre o Acesso Condicional para suporte a aplicativos de cliente e serviços, consulte:

- [Suporte ao aplicativo cliente microsoft 365: acesso condicional baseado em dispositivo](microsoft-365-client-support-conditional-access.md)

### <a name="mobile-application-management"></a>Gerenciamento de aplicativos móveis

Os usuários frequentemente acessam documentos, emails e dados pessoais da organização e pessoais do mesmo dispositivo móvel. Esses dispositivos geralmente são de propriedade pessoal e devem ser configurados para proteger os dados da organização e a privacidade pessoal do usuário.

Quando um usuário acessa os dados da organização, a organização deve ter certeza de que as políticas da organização, como políticas de configuração e políticas de proteção, são aplicadas para ajudar a proteger os dados da organização no dispositivo. Além disso, o conteúdo pessoal do usuário no dispositivo deve permanecer fora do controle da organização.

Para conteúdo gerenciado pela organização, você pode aplicar políticas de gerenciamento de aplicativos para controlar como os dados são acessados, compartilhados e usados usando o Microsoft Intune. Por exemplo, as seguintes ações são suportadas:

- Apagar remotamente o conteúdo da organização gerenciada (também conhecido como dados da organização)
- Impedir a colar o conteúdo da organização em locais que não são da organização
- Exigir um PIN para acessar o conteúdo da organização
- Impedir que aplicativos gerenciados são executados em dispositivos com jailbreque ou com raiz
- Impedir que o conteúdo da organização seja salvo em provedores de armazenamento em nuvem não aprovados
- Impedir que conteúdo não aprovado seja transferido para aplicativos gerenciados
- Permitir acesso ao conteúdo da organização somente depois que as políticas foram aplicadas
- Entregar a configuração do aplicativo para gerenciar o comportamento e as configurações do aplicativo
- Restringir o aplicativo gerenciado a uma identidade definida desabilitando recursos de várias identidades ou uso pessoal

Para obter mais informações sobre o gerenciamento de aplicativos móveis com o Microsoft Intune, consulte O que é o gerenciamento de [aplicativos do Microsoft Intune?](/mem/intune/apps/app-management)

### <a name="multi-factor-authentication"></a>Autenticação multifator

[A autenticação multifator (MFA) é um método de controle de acesso do computador no qual um usuário só tem acesso depois de apresentar várias evidências separadas para um mecanismo de autenticação. Esse método normalmente usa pelo menos duas das seguintes categorias:

- Conhecimento (algo que eles sabem)
- Posse (algo que eles têm)
- Incoerência (algo que são)

Para obter mais informações sobre a autenticação multifa factor para suporte a aplicativos de cliente e serviços, consulte Suporte ao aplicativo cliente [do Microsoft 365: autenticação multifa factor.](microsoft-365-client-support-multi-factor-authentication.md)

### <a name="single-sign-on"></a>Logon único

O SSO (single sign-on) adiciona segurança e conveniência quando os usuários se ins login em aplicativos no Azure Active Directory. Com o logor único, os usuários podem entrar uma vez com uma conta para acessar dispositivos ingressados no domínio dos Serviços de Domínio do Active Directory (AD DS), aplicativos de software como serviço (SaaS) e aplicativos Web em sua organização.

Para obter mais informações sobre o single sign-on para suporte a aplicativos de cliente e serviços, consulte Suporte ao aplicativo cliente [do Microsoft 365: single sign-on](microsoft-365-client-support-single-sign-on.md).

## <a name="services-support"></a>Suporte a serviços

### <a name="modern-authentication"></a>Autenticação moderna

A autenticação moderna permite que novos cenários para que os clientes se autenthem no Office 365 e para os administradores de locatários imporem requisitos de autenticação específicos no locatário do Office 365, como:

- Suporte à autenticação multifaionária para interação administrativa com a aplicação e serviços e interação do usuário final com aplicativos e seus dados
- Acesso condicional
- Entrar no provedor de identidade de terceiros baseado em SAML
- Log do cartão inteligente em computadores pessoais
- Autenticação baseada em certificado em dispositivos móveis
- Não exige mais a transmissão de credenciais pela autenticação básica.

Para obter mais informações sobre o suporte a serviços de autenticação moderna, consulte [Autenticação versus autorização.](/azure/active-directory/develop/authentication-vs-authorization)

### <a name="azure-active-directory-conditional-access"></a>Acesso Condicional do Azure Active Directory

As regras de Acesso Condicional do Azure Active Directory (Azure AD) permitem que os clientes controlem o acesso a serviços online, com base em atributos como a conformidade do dispositivo ou o local da rede. As soluções a seguir podem ser usadas:

- Acesso Condicional baseado em autenticação multifacional do Azure AD
- Acesso Condicional baseado no local do Azure AD
- Acesso Condicional baseado em dispositivo do Azure AD

As regras de acesso condicional do Azure AD são aplicadas por aplicativo e estão disponíveis para que os clientes controlem o acesso com base em diferentes condições. Usando o Gerenciamento de Dispositivo Móvel [(MDM)](/mem/intune/fundamentals/what-is-device-management)ou o Intune, os clientes devem ser capazes de restringir o acesso ao Microsoft 365 apenas aos usuários que estão usando um dispositivo da organização ou que registraram seus dispositivos pessoais para gerenciamento. Por exemplo, os clientes podem configurar regras de Acesso Condicional para impor controles como:

- Permitir somente o acesso de dispositivos que são ingressados no domínio ou são compatíveis com domínio
- Impor a autenticação multifa factor para todo o acesso aos serviços do Exchange Online

Para obter mais informações sobre o Acesso Condicional do Azure Active Directory, consulte [O que é Acesso Condicional?](/azure/active-directory/conditional-access/overview)

### <a name="tls-12-support"></a>Suporte a TLS 1.2

Para fornecer a melhor criptografia para nossos clientes, a Microsoft planeja interromper o suporte para as versões 1.0 e 1.1 do Transport Layer Security (TLS) no Office 365 e no Office 365 GCC.

Entendemos que a segurança dos seus dados é importante, e estamos comprometidos com a transparência sobre as alterações que podem afetar o uso do serviço TLS. Recomendamos que todas as combinações cliente-servidor e navegador-servidor usem o TLS 1.2 (ou uma versão posterior) para manter a conexão com os serviços do Office 365. Você poderá ter que atualizar certas combinações de cliente-servidor e navegador-servidor.

Para obter mais informações sobre suporte e serviços do TLS 1.2, consulte Preparando-se para [o TLS 1.2 no Office 365 e no Office 365 GCC.](/microsoft-365/compliance/prepare-tls-1.2-in-office-365)
