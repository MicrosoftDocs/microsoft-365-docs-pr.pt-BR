---
title: Microsoft 365 suporte a aplicativos de cliente e serviços
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
description: Neste artigo, encontre detalhes sobre o Microsoft 365 de aplicativos de cliente e serviços.
ms.openlocfilehash: e380efffc1bf29cbd4d3a77d32e4d1f8b2994da3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905003"
---
# <a name="microsoft-365-client-and-services-app-support"></a>Microsoft 365 suporte a aplicativos de cliente e serviços

A Microsoft oferece suporte a uma ampla variedade de recursos de segurança, autenticação e conformidade para manter os dados do cliente seguros e permite que os administradores de IT personalizem políticas no centro de administração Microsoft 365 para seus usuários. Os recursos a seguir são apenas um subconjunto dos muitos recursos corporativos que você pode configurar dependendo da sua assinatura Microsoft 365.

## <a name="client-and-service-support"></a>Suporte a cliente e serviço

### <a name="continuous-access-evaluation-preview"></a>Avaliação de acesso contínuo (visualização)

A avaliação de acesso contínuo é implementada habilitando serviços, como Exchange Online, SharePoint Online e Teams, para assinar eventos críticos no Azure Active Directory para que esses eventos possam ser avaliados e imposto quase em tempo real. A avaliação de eventos críticos não depende das políticas de Acesso Condicional, portanto, está disponível em qualquer locatário.

No momento, os seguintes eventos são avaliados:

- Uma conta de usuário é excluída ou desabilitada
- A senha de um usuário é alterada ou redefinida
- A autenticação multifabilitar está habilitada para o usuário
- O administrador revoga explicitamente todos os tokens de atualização para um usuário
- Risco de usuário elevado detectado pela Proteção de Identidade do Azure AD

Para obter mais informações sobre a avaliação de acesso contínuo para suporte a aplicativos de cliente e serviços, consulte [Continuous access evaluation (preview)](/azure/active-directory/conditional-access/concept-continuous-access-evaluation).

## <a name="client-support"></a>Suporte ao cliente

### <a name="certificate-based-authentication"></a>Autenticação baseada em certificados

A autenticação baseada em certificado (CBA) é o uso de um certificado digital para identificar um usuário, máquina ou dispositivo antes de conceder acesso a um recurso, rede, aplicativo ou serviço. Na autenticação do usuário, ela geralmente é implantada em coordenação com métodos tradicionais, como nomes de usuário e senhas.

Algumas soluções tradicionais só funcionam para usuários, como biometria e senhas únicas (OTP). Com a autenticação baseada em certificado, a mesma solução pode ser usada para todos os pontos de extremidade; usuários, dispositivos e a Internet das Coisas (IoT) crescente.

Para obter mais informações sobre autenticação baseada em certificado para suporte a aplicativos de cliente e serviços, consulte Microsoft 365 Suporte a aplicativos [cliente: Autenticação baseada em certificado.](microsoft-365-client-support-certificate-based-authentication.md)

### <a name="conditional-access"></a>Acesso Condicional

O Acesso Condicional é a ferramenta usada pela Azure Active Directory para reunir sinais, tomar decisões e impor políticas de acesso organizacional. O Acesso Condicional está no centro do novo modelo de controle controlado por identidade.

As políticas de Acesso Condicional são instruções if-then para conceder acesso aos recursos. Se um usuário quiser acessar um recurso, o usuário deverá concluir uma ação. Os sinais comuns que o Acesso Condicional pode usar ao tomar uma decisão de acesso à política incluem:

- Associação de usuário ou grupo
- Informações sobre o local IP
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

- [Microsoft 365 Suporte ao aplicativo cliente: Acesso Condicional baseado em dispositivo](microsoft-365-client-support-conditional-access.md)

### <a name="mobile-application-management"></a>Gerenciamento de aplicativos móveis

Os usuários geralmente acessam documentos, emails e dados pessoais da organização e pessoais do mesmo dispositivo móvel. Esses dispositivos geralmente são de propriedade pessoal e devem ser configurados para proteger os dados da organização e a privacidade pessoal do usuário.

Quando um usuário acessa dados da organização, a organização deve estar confiante de que as políticas da organização, como políticas de configuração e políticas de proteção, são aplicadas para ajudar a proteger os dados da organização no dispositivo. Além disso, o conteúdo pessoal do usuário no dispositivo deve permanecer fora do controle da organização.

Para conteúdo gerenciado pela organização, você pode aplicar políticas de gerenciamento de aplicativos para controlar como os dados são acessados, compartilhados e usados usando Microsoft Intune. Por exemplo, há suporte para as seguintes ações:

- Apagar remotamente o conteúdo da organização gerenciada (também chamado de dados da organização)
- Impedir o colar conteúdo da organização em locais que não são da organização
- Exigir um PIN para acessar o conteúdo da organização
- Impedir que aplicativos gerenciados seja executado em dispositivos com cadeia ou raiz
- Impedir que o conteúdo da organização seja salvo em provedores de armazenamento em nuvem não aprovados
- Impedir que o conteúdo não aprovado seja transferido para aplicativos gerenciados
- Permitir acesso ao conteúdo da organização somente depois que as políticas foram aplicadas
- Fornecer configuração de aplicativo para gerenciar o comportamento e as configurações do aplicativo
- Restringir o aplicativo gerenciado a uma identidade definida desabilitando recursos de várias identidades ou uso pessoal

Para obter mais informações sobre o gerenciamento de aplicativos móveis com Microsoft Intune, consulte O que é [Microsoft Intune de aplicativos?](/mem/intune/apps/app-management)

### <a name="multi-factor-authentication"></a>Autenticação multifator

[A autenticação multifator (MFA) é um método de controle de acesso ao computador no qual um usuário só tem acesso depois de apresentar várias evidências separadas com êxito para um mecanismo de autenticação. Esse método normalmente usa pelo menos duas das seguintes categorias:

- Conhecimento (algo que eles sabem)
- Possessão (algo que eles têm)
- Inerência (algo que são)

Para obter mais informações sobre a autenticação multifa factor para suporte a aplicativos de cliente e serviços, consulte Microsoft 365 Suporte a aplicativos [cliente: autenticação multifa factor](microsoft-365-client-support-multi-factor-authentication.md).

### <a name="single-sign-on"></a>Logon único

O SSO (sign-on único) adiciona segurança e conveniência quando os usuários se inssoam em aplicativos Azure Active Directory. Com o logont único, os usuários se ingressam uma vez com uma conta para acessar dispositivos ingressados no domínio do AD DS (Serviços de Domínio do Active Directory) locais, aplicativos saaS (serviço como serviço) e aplicativos Web em sua organização.

Para obter mais informações sobre o login único para suporte a aplicativos de cliente e serviços, consulte Microsoft 365 Suporte ao aplicativo [cliente: Entrada única](microsoft-365-client-support-single-sign-on.md).

## <a name="services-support"></a>Suporte a serviços

### <a name="modern-authentication"></a>Autenticação moderna

A autenticação moderna permite que novos cenários para os clientes se autenticam no Office 365 e para os administradores de locatários imporem requisitos específicos de autenticação no Office 365 locatário, como:

- Suporte à autenticação multifaionária para interação administrativa com a interatividade e serviços e interação do usuário final com aplicativos e seus dados
- Acesso condicional
- Entrar no provedor de identidade de terceiros baseado em SAML
- Log de cartão inteligente em computadores pessoais
- Autenticação baseada em certificado em dispositivos móveis
- Não é mais necessário a transmissão de credenciais por meio da autenticação básica.

Para obter mais informações sobre o suporte a serviços de autenticação modernos, consulte [Authentication vs. authorization](/azure/active-directory/develop/authentication-vs-authorization).

### <a name="azure-active-directory-conditional-access"></a>Acesso condicional ao Microsoft Azure Active Directory

Azure Active Directory regras de Acesso Condicional (Azure AD) permitem que os clientes controlem o acesso a serviços online, com base em atributos como conformidade de dispositivo ou local de rede. As seguintes soluções podem ser usadas:

- Acesso Condicional baseado em autenticação multifacional do Azure AD
- Acesso Condicional baseado em local do Azure AD
- Acesso Condicional baseado em dispositivo do Azure AD

As regras de acesso condicional do Azure AD são aplicadas por aplicativo e estão disponíveis para os clientes controlarem o acesso com base em diferentes condições. Usando o Gerenciamento de Dispositivo Móvel [(MDM)](/mem/intune/fundamentals/what-is-device-management)ou o Intune, os clientes devem ser capazes de restringir o acesso ao Microsoft 365 somente aos usuários que estão usando um dispositivo da organização ou que registraram seu dispositivo pessoal para gerenciamento. Por exemplo, os clientes podem configurar regras de Acesso Condicional para impor controles como:

- Permitir somente o acesso de dispositivos que são compatíveis com domínio ou ingressados no domínio
- Impor a autenticação multifa factor para todo o acesso aos serviços Exchange Online serviços

Para obter mais informações sobre Azure Active Directory Acesso Condicional, consulte [O que é o Acesso Condicional?](/azure/active-directory/conditional-access/overview)

### <a name="tls-12-support"></a>Suporte ao TLS 1.2

Para fornecer a melhor criptografia em classe para nossos clientes, a Microsoft planeja descontinuar o suporte para as versões 1.0 e 1.1 da Transport Layer Security (TLS) em Office 365 e Office 365 GCC.

Entendemos que a segurança dos seus dados é importante, e estamos comprometidos com a transparência sobre as alterações que podem afetar o uso do serviço TLS. Recomendamos que todas as combinações cliente-servidor e navegador-servidor usem o TLS 1.2 (ou uma versão posterior) para manter a conexão com os serviços Office 365. Você poderá ter que atualizar certas combinações de cliente-servidor e navegador-servidor.

Para obter mais informações sobre suporte e serviços do TLS 1.2, consulte [Preparing for TLS 1.2 in Office 365 and Office 365 GCC](../compliance/prepare-tls-1.2-in-office-365.md).