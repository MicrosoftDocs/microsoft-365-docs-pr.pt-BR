---
title: Prepare o acesso aos recursos locais da Área de trabalho gerenciada da Microsoft
description: Etapas importantes para garantir que um Azure AD possa se comunicar com o AD local para fornecer autenticação
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: c1732dc17188427f9a181d1c47abe71bb8f39584
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841406"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Prepare o acesso aos recursos locais da Área de trabalho gerenciada da Microsoft

Na Área de Trabalho Gerenciada da Microsoft, os dispositivos são automaticamente ingressados no Azure Active Directory (Azure AD). Por esse motivo, se estiver usando um Active Directory local, você terá que verificar algumas coisas para garantir que os dispositivos ingressados no Azure AD possam se comunicar com seu Active Directory local. 

> [!NOTE]  
> *Híbrido* O ingressar no Azure AD não é suportado pela Área de Trabalho Gerenciada da Microsoft.

O Azure Active Directory permite que os usuários aproveitem o SSO (single Sign-On), o que significa que eles geralmente não terão que fornecer credenciais sempre que usarem recursos.

Para obter informações sobre como ingressar no Azure Active Directory, consulte Como: planejar sua implementação de participação [no Azure AD.](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan) Para obter informações básicas sobre o SSO (single Sign-On) em dispositivos ingressados no Azure AD, consulte como o SSO para recursos locais funciona em [dispositivos ingressados no Azure AD.](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works)


Este artigo explica o que você precisa verificar para garantir que os aplicativos e outros recursos que dependem da conectividade local do Active Directory funcionem perfeitamente com a Área de Trabalho Gerenciada da Microsoft.


## <a name="single-sign-on-for-on-premises-resources"></a>Single Sign-On for on-premises resources

O Sign-On único (SSO) usando UPN e senha é habilitado por padrão em Dispositivos de Área de Trabalho Gerenciada da Microsoft. Mas os usuários também podem usar o Windows Hello para Empresas, o que requer algumas etapas adicionais de configuração. 

### <a name="single-sign-on-by-using-upn-and-password"></a>Single Sign-On by using UPN and password

Na maioria das organizações, os usuários poderão usar o SSO para autenticação por UPN e senha em Dispositivos de Área de Trabalho Gerenciada da Microsoft. No entanto, para garantir que essa função funcione, verifique as seguintes coisas:

- Confirme se o Azure AD Connect está definido e usa um servidor do Active Directory local executando o Windows Server 2008 R2 ou posterior.
- Confirme se o Azure AD Connect está executando uma versão com suporte e está definido para sincronizar esses três atributos com o Azure AD: 
    - Nome de domínio DNS do Active Directory local (onde os usuários estão localizados)
    - NetBIOS do Active Directory local (onde os usuários estão localizados)
    - Nome da conta SAM do usuário


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>Single Sign-On by using Windows Hello for Business

Os dispositivos da Área de Trabalho Gerenciada da Microsoft também oferecem aos usuários uma experiência rápida e sem senha empregando o Windows Hello para Empresas. Para garantir que o Windows Hello para Empresas funcione sem que seus usuários tenha que fornecer os respectivos UPN e senha, visite Configurar [dispositivos ingressados no Azure AD](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) para o Single-Sign No local usando o Windows Hello para Empresas para verificar os requisitos e, em seguida, siga as etapas fornecidas lá.


## <a name="apps-and-resources-that-use-authentication"></a>Aplicativos e recursos que usam autenticação

Consulte [Noções detalhadas sobre aplicativos](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) e recursos no conjunto de conteúdo do Azure para obter orientação completa sobre como configurar aplicativos para trabalhar com o Azure Active Directory. Em resumo:


- Se você **usar** aplicativos baseados em nuvem, como aqueles adicionados à galeria de aplicativos do Azure AD, a maioria não exigirá mais preparação para trabalhar com a Área de Trabalho Gerenciada da Microsoft. No entanto, quaisquer aplicativos Win32 que não usam o Gerenciador de Contas da Web (WAM) ainda podem solicitar a autenticação dos usuários.

- Para aplicativos hospedados no local, **certifique-se** de adicionar esses aplicativos à lista de sites confiáveis em seus navegadores. Esta etapa permitirá que a autenticação do Windows funcione perfeitamente, sem que os usuários seja solicitado a solicitar credenciais. Para adicionar aplicativos, consulte [sites confiáveis](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites) na [referência de configurações configuráveis.](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref)

- Se você estiver usando os Serviços Federados do Active Directory, verifique se o SSO está habilitado usando as etapas em Verificar e gerenciar o single [sign-on com o AD FS.](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100)) 

- Para aplicativos locais e usam **protocolos** mais antigos, nenhuma configuração extra é necessária, desde que os dispositivos tenham acesso a um controlador de domínio local para autenticação. Para fornecer acesso seguro para esses aplicativos, no entanto, você deve implantar o Proxy de Aplicativo do Azure AD. Para obter mais informações, consulte Acesso remoto a aplicativos locais por meio do Proxy de Aplicativo [do Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)

- Os aplicativos que são executados no local e dependem da autenticação de máquina não são **suportados,** portanto, você deve considerar substituí-los por versões mais recentes.

### <a name="network-shares-that-use-authentication"></a>Compartilhamentos de rede que usam autenticação

Nenhuma configuração extra é necessária para que os usuários acessem compartilhamentos de rede, desde que os dispositivos tenham acesso a um controlador de domínio local usando um caminho UNC.

### <a name="printers"></a>Impressoras

Os dispositivos da Área de Trabalho Gerenciada da Microsoft não podem se conectar a impressoras publicadas no Active Directory local, a menos que você tenha configurado a Impressão [Híbrida na Nuvem.](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)

Embora as impressoras não possam ser descobertas automaticamente em um ambiente somente na nuvem, os usuários podem usar impressoras locais usando o caminho da impressora ou o caminho da fila da impressora, desde que os dispositivos tenham acesso a um controlador de domínio local.

<!--add fuller material on printers when available-->
