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
audience: Admin
ms.openlocfilehash: 6df23e0d7e3ea0ecd7ebacd96f00cb47b9e0aa84
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574590"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Prepare o acesso aos recursos locais da Área de trabalho gerenciada da Microsoft

Na Área de Trabalho Gerenciada da Microsoft, os dispositivos são automaticamente ingressados no Azure Active Directory (Azure AD). Por esse motivo, se você estiver usando um Active Directory local, você terá que verificar algumas coisas para garantir que os dispositivos ingressados no Azure AD possam se comunicar com o Active Directory local. 

> [!NOTE]  
> *Híbrido* A junção ao Azure AD não é suportada pela Área de Trabalho Gerenciada da Microsoft.

O Azure Active Directory permite que os usuários aproveitem o SSO (Single Sign-On), o que significa que eles normalmente não terão que fornecer credenciais sempre que usarem recursos.

Para obter informações sobre como ingressar no Azure Active Directory, consulte [How to: Plan your Azure AD join implementation](/azure/active-directory/devices/azureadjoin-plan). Para obter informações em segundo plano sobre o SSO (single Sign-On) em dispositivos ingressados no Azure AD, consulte Como o SSO para recursos locais funciona em [dispositivos ingressados no Azure AD.](/azure/active-directory/devices/azuread-join-sso#how-it-works)


Este artigo explica as coisas que você precisa verificar para garantir que os aplicativos e outros recursos que dependem da conectividade local do Active Directory funcionem suavemente com a Área de Trabalho Gerenciada da Microsoft.


## <a name="single-sign-on-for-on-premises-resources"></a>Single Sign-On para recursos locais

O Sign-On único (SSO) usando UPN e senha é habilitado por padrão em Dispositivos de Área de Trabalho Gerenciados da Microsoft. Mas os usuários também podem usar o Windows Hello para Empresas, o que requer algumas etapas de configuração extras. 

### <a name="single-sign-on-by-using-upn-and-password"></a>Single Sign-On usando UPN e senha

Na maioria das organizações, os usuários poderão usar o SSO para autenticação por UPN e senha em Dispositivos de Área de Trabalho Gerenciados da Microsoft. No entanto, para garantir que essa função funcione, verifique duas vezes as seguintes coisas:

- Confirme se o Azure AD Connect está definido e usa um servidor do Active Directory local executando o Windows Server 2008 R2 ou posterior.
- Confirme se o Azure AD Connect está executando uma versão com suporte e está definido para sincronizar esses três atributos com o Azure AD: 
    - Nome de domínio DNS do Active Directory local (onde os usuários estão localizados)
    - NetBIOS do Active Directory local (onde os usuários estão localizados)
    - Nome da conta SAM do usuário


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>Single Sign-On usando o Windows Hello para Empresas

Os dispositivos da Área de Trabalho Gerenciada da Microsoft também oferecem aos seus usuários uma experiência rápida e sem senha empregando o Windows Hello para Empresas. Para garantir que o Windows Hello para Empresas funcione sem que seus usuários tenha que fornecer o UPN e a senha respectivos, visite [Configurar dispositivos ingressados no Azure AD](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) para o Single-Sign local ao usar o Windows Hello para Empresas para verificar os requisitos e, em seguida, seguir as etapas fornecidas lá.


## <a name="apps-and-resources-that-use-authentication"></a>Aplicativos e recursos que usam autenticação

Consulte [Understand considerations for applications and resources](/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) in the Azure content set for full guidance on setting up apps to work with Azure Active Directory. Em resumo:


- Se você usar **aplicativos** baseados em nuvem , como os adicionados à galeria de aplicativos do Azure AD, a maioria não exige mais preparação para trabalhar com a Área de Trabalho Gerenciada da Microsoft. No entanto, quaisquer aplicativos Win32 que não usam o WAM (Web Account Manager) ainda podem solicitar autenticação aos usuários.

- Para aplicativos hospedados no local, **certifique-se** de adicionar esses aplicativos à lista de sites confiáveis em seus navegadores. Esta etapa permitirá que a autenticação do Windows funcione perfeitamente, sem que os usuários seja solicitado a solicitar credenciais. Para adicionar aplicativos, consulte [Sites confiáveis](../working-with-managed-desktop/config-setting-ref.md#trusted-sites) na [referência configurações configuráveis](../working-with-managed-desktop/config-setting-ref.md).

- Se você estiver usando Serviços Federados do Active Directory, verifique se o SSO está habilitado usando as etapas em Verificar e gerenciar o login único com [o AD FS](/previous-versions/azure/azure-services/jj151809(v=azure.100)). 

- Para aplicativos que estão no local e usam **protocolos** mais antigos, nenhuma configuração extra é necessária, desde que os dispositivos tenham acesso a um controlador de domínio local para autenticação. No entanto, para fornecer acesso seguro a esses aplicativos, você deve implantar o Proxy de Aplicativo do Azure AD. Para obter mais informações, consulte Acesso remoto a aplicativos locais por meio do Proxy de Aplicativo do [Azure Active Directory.](/azure/active-directory/manage-apps/application-proxy)

- Os aplicativos **que são executados no local** e dependem da autenticação do computador não são suportados, portanto, você deve considerar substituí-los por versões mais recentes.

### <a name="network-shares-that-use-authentication"></a>Compartilhamentos de rede que usam autenticação

Nenhuma configuração adicional é necessária para que os usuários acessem compartilhamentos de rede, desde que os dispositivos tenham acesso a um controlador de domínio local usando um caminho UNC.

### <a name="printers"></a>Impressoras

Os dispositivos da Área de Trabalho Gerenciada da Microsoft não podem se conectar a impressoras publicadas no Active Directory local, a menos que você tenha configurado [o Hybrid Cloud Print](/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).

Embora as impressoras não possam ser descobertas automaticamente em um ambiente somente na nuvem, os usuários podem usar impressoras locais usando o caminho da impressora ou o caminho da fila da impressora, desde que os dispositivos tenham acesso a um controlador de domínio local.

<!--add fuller material on printers when available-->
## <a name="steps-to-get-ready"></a>Etapas para se preparar

1. Revise [os pré-requisitos da Área de Trabalho Gerenciada da Microsoft.](prerequisites.md)
2. Use [ferramentas de avaliação de preparação.](readiness-assessment-tool.md)
3. [Pré-requisitos para contas de convidados](guest-accounts.md)
4. [Configuração de rede na Área de Trabalho Gerenciada da Microsoft](network.md)
5. [Preparar certificados e perfis de rede da Área de Trabalho Gerenciada da Microsoft](certs-wifi-lan.md)
6. [Preparar o acesso de recursos locais para a Área de Trabalho Gerenciada](authentication.md) da Microsoft (Este artigo)
7. [Aplicativos na Área de Trabalho Gerenciada da Microsoft](apps.md)
8. [Preparar unidades mapeadas da Área de Trabalho Gerenciada da Microsoft](mapped-drives.md)
9. [Preparar recursos de impressão da Área de Trabalho Gerenciada da Microsoft](printing.md)
