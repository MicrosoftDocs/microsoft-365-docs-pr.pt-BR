---
title: Preparar o acesso a recursos locais para a área de trabalho gerenciada da Microsoft
description: Etapas importantes para garantir que um Azure AD possa se comunicar com o AD local para fornecer autenticação
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: c4ebe0c7ad3d1e197cf90cc975366df61d3b0cb5
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276912"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Preparar o acesso a recursos locais para a área de trabalho gerenciada da Microsoft

Na área de trabalho gerenciada da Microsoft, os dispositivos são adicionados automaticamente ao Azure Active Directory (Azure AD). Isso significa que, se você estiver usando um Active Directory local, será necessário verificar algumas coisas para garantir que os dispositivos que ingressaram no Azure AD possam se comunicar com seu Active Directory local. 

> [!NOTE]  
> *Híbrido* O Azure AD Join não é suportado pela área de trabalho gerenciada da Microsoft.

O Azure Active Directory permite que os usuários aproveitem o SSO (logon único), o que significa que eles normalmente não precisam fornecer credenciais sempre que usam recursos.

Para obter informações sobre como ingressar no Active Directory do Azure, consulte [como: planejar sua implementação de ingresso no Azure ad](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan). Para obter informações detalhadas sobre logon único (SSO) em dispositivos que ingressaram no Azure AD, confira [como o SSO para recursos locais funciona em dispositivos ingressados no Azure ad](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works).


Este tópico explica o que você precisa verificar para garantir que os aplicativos e outros recursos que dependem da conectividade do Active Directory local funcionem sem problemas com a área de trabalho gerenciada da Microsoft.


## <a name="single-sign-on-for-on-premises-resources"></a>Logon único para recursos locais

O logon único (SSO) usando o UPN e a senha são habilitados por padrão em dispositivos de área de trabalho gerenciada da Microsoft. Mas os usuários também podem usar o Windows Hello para empresas, que requer algumas etapas de configuração adicionais. 

### <a name="single-sign-on-by-using-upn-and-password"></a>Logon único usando o UPN e a senha

Na maioria das organizações, seus usuários poderão usar o SSO para autenticar por UPN e senha em dispositivos de área de trabalho gerenciada da Microsoft. No enTanto, para garantir que isso funcione, você deve verificar novamente o seguinte:

- Confirme se o Azure AD Connect está configurado e usa um servidor do Active Directory local executando o Windows Server 2008 R2 ou posterior.
- Confirme se o Azure AD Connect está executando uma versão com suporte e se está definido para sincronizar esses três atributos com o Azure AD: 
    - Nome de domínio DNS do Active Directory local (onde os usuários finais estão localizados)
    - NetBIOS de seu Active Directory local (onde os usuários finais estão localizados)
    - Nome da conta SAM do usuário


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>Logon único usando o Windows Hello para empresas

Os dispositivos de área de trabalho gerenciada da Microsoft também oferecem aos seus usuários uma experiência rápida e com senha, empregando o Windows Hello para empresas. Para garantir que o Windows Hello para empresas funcione sem que seus usuários tenham que fornecer seus próprios UPN e senha, visite [configurar os dispositivos ingressaDos no Azure ad para o logon único local usando o Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) para verificar os requisitos e, em seguida, Siga as etapas fornecidas lá.


## <a name="apps-and-resources-that-use-authentication"></a>Aplicativos e recursos que usam autenticação

Consulte [entender as considerações de aplicativos e recursos](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) no conjunto de conteúdo do Azure para obter orientação completa sobre como configurar aplicativos para trabalhar com o Azure Active Directory. Em Resumo:


- Se você usar **aplicativos baseados em nuvem**, como os adicionados à galeria de aplicativos do Azure AD, a maioria não precisará de mais preparação para trabalhar com a área de trabalho gerenciada da Microsoft. No enTanto, os aplicativos Win32 que não usam o Gerenciador de contas da Web (WAM) ainda podem solicitar a autenticação dos usuários.

- Para aplicativos hospedados **no local**, certifique-se de adicionar esses aplicativos à lista de sites confiáveis em seus navegadores. Isso permitirá que a autenticação do Windows funcione perfeitamente, sem que os usuários sejam solicitados a fornecer credenciais. Para fazer isso, consulte [sites confiáveis](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites) na referência de [configurações configuráveis](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref).

- Se você estiver usando os serviços federados do Active Directory, verifique se o SSO está habilitado usando as etapas em [verificar e gerenciar o logon único com o AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100)). 

- Para aplicativos **locais e usar protocolos mais antigos**, nenhuma configuração adicional é necessária, desde que os dispositivos tenham acesso a um controlador de domínio local para autenticar. Para fornecer acesso seguro a esses aplicativos, no entanto, você deve implantar o proxy de aplicativo do Azure AD. Para obter mais informações, consulte [acesso remoto para aplicativos locais por meio do proxy de aplicativo do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).

- Os aplicativos que são executados **no local e dependem da autenticação de máquina** não são suportados, portanto, você deve considerar substituí-los por versões mais recentes.

### <a name="network-shares-that-use-authentication"></a>Compartilhamentos de rede que usam autenticação

Nenhuma configuração adicional é necessária para que os usuários acessem os compartilhamentos de rede, contanto que os dispositivos tenham acesso a um controlador de domínio local usando um caminho UNC.

### <a name="printers"></a>Impressoras

Os dispositivos de área de trabalho gerenciada da Microsoft não podem se conectar a impressoras publicadas no seu Active Directory local, a menos que você tenha configurado a [impressão de nuvem híbrida](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).

Embora as impressoras não possam ser descobertas automaticamente em um ambiente somente na nuvem, os usuários podem usar impressoras locais usando o caminho da impressora ou o caminho da fila da impressora, contanto que os dispositivos tenham acesso a um controlador de domínio local.

<!--add fuller material on printers when available-->
