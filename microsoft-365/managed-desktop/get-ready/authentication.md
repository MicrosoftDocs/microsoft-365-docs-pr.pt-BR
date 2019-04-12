---
title: Preparar o acesso a recursos locais para a área de trabalho gerenciada da Microsoft
description: Etapas importantes para garantir que um Azure AD possa se comunicar com o AD local para fornecer autenticação
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0f9cbe6712b8d16f435cfdf5fd84875656fa9c2e
ms.sourcegitcommit: ef589025820ddf6edb5f454826b1c12c9bcb8e49
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/11/2019
ms.locfileid: "31824461"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Preparar o acesso a recursos locais para a área de trabalho gerenciada da Microsoft

Na área de trabalho gerenciada da Microsoft, os dispositivos são automaticamente Unidos ao Active Directory do Azure. Isso significa que, se você estiver usando um Active Directory local, será necessário verificar algumas coisas para garantir que os dispositivos que ingressaram no Azure AD possam se comunicar com seu Active Directory local. 

> [!NOTE]  
> *Híbrido* O Azure AD Join não é suportado pela área de trabalho gerenciada da Microsoft.

O Azure Active Directory permite que os usuários aproveitem o SSO (logon único), o que significa que eles normalmente não precisam fornecer credenciais sempre que querem fazer algo. Se você for completamente novo no Azure Active Directory, consulte [como: planejar sua implementação de ingresso no Azure ad](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)– no entanto, à medida que você faz referência à documentação do Azure Active Directory, lembre-se de que a junção *híbrida* do Azure ad não é suportada pela Microsoft Área de trabalho gerenciada.


Este tópico explica o que você precisa verificar para garantir que os aplicativos e outros recursos que dependem da conectividade do Active Directory local funcionem sem problemas com a área de trabalho gerenciada da Microsoft.


> [!IMPORTANT]  
> Para que os usuários possam registrar dispositivos no Azure Active Directory e se inscrever no Intune (necessário para a área de trabalho gerenciada da Microsoft), siga as etapas em [Configure your device settings](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) antes de prosseguir com o restante deste tópico.


## <a name="single-sign-on-for-on-premises-resources"></a>Logon único para recursos locais

O logon único (SSO) para seus dispositivos usando UPN ou senhas (o método padrão) já deve funcionar por padrão. Mas você também pode usar o Windows Hello para empresas, que requer algumas etapas de configuração adicionais. Para obter informações detalhadas sobre SSO, confira [como o SSO para recursos locais funciona em dispositivos ingressados no Azure ad](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works).


### <a name="single-sign-on-by-using-upn-and-passwords"></a>Logon único usando UPN e senhas

Nenhuma configuração especial é necessária para que os usuários sejam autenticados por UPN e por senha--você obtém isso por padrão no Azure. No enTanto, para garantir que isso funcione, você deve verificar novamente o seguinte:

- Confirme se a conexão do Azure Active Directory (AAD) está configurada com um servidor do Active Directory local executando o Windows Server 2008 R2 ou posterior.
- O AAD Connect está executando uma versão com suporte e está definido para sincronizar esses três atributos de chave com o Azure AD: 
    - Nome de domínio DNS onde o usuário está presente no seu Active Directory local
    - Nome de domínio NetBIOS onde o usuário está presente no seu Active Directory local
    - Nome da conta SAM do usuário


### <a name="sso-by-using-windows-hello-for-business"></a>SSO usando o Windows Hello para empresas

Como alternativa, você pode oferecer aos seus usuários uma experiência rápida e com senha, empregando o Windows Hello para empresas. Para configurar isso, visite [configurar os dispositivos ingressaDos no Azure ad para o logon único local usando o Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) para verificar os requisitos e siga as etapas fornecidas lá.


## <a name="apps-and-resources-that-use-authentication"></a>Aplicativos e recursos que usam autenticação

Consulte [entender as considerações de aplicativos e recursos](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) no conjunto de conteúdo do Azure para obter orientação completa sobre como configurar aplicativos para trabalhar com o Azure Active Directory. Em Resumo:


- Se você usar **aplicativos baseados em nuvem**, como os adicionados à galeria de aplicativos do Azure AD, a maioria não precisará de mais preparação para trabalhar com a área de trabalho gerenciada da Microsoft. No enTanto, os aplicativos Win32 que não usam o Gerenciador de contas da Web (WAM) {Verify this acrônimo} ainda podem solicitar a autenticação dos usuários.

- Para aplicativos hospedados **no local**, certifique-se de adicionar esses aplicativos à lista de sites confiáveis em seus navegadores. Isso permitirá que a autenticação do Windows funcione perfeitamente, sem que os usuários sejam solicitados a fornecer credenciais.

- Se você estiver usando os serviços federados do Active Directory, siga as etapas em [verificar e gerenciar o logon único com o AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100)). 

- Para aplicativos **locais e usar protocolos mais antigos**, nenhuma configuração adicional é necessária, desde que os dispositivos tenham acesso a um controlador de domínio local. Para fornecer acesso seguro a esses aplicativos, no entanto, você deve implantar o proxy de aplicativo do Azure AD. Para obter mais informações, consulte [acesso remoto para aplicativos locais por meio do proxy de aplicativo do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).

- Os aplicativos que são executados **no local e dependem da autenticação de máquina** não são suportados, portanto, você deve considerar substituí-los por versões mais recentes.

## <a name="network-shares-that-use-authentication"></a>Compartilhamentos de rede que usam autenticação

Nenhuma configuração adicional é necessária para que os usuários acessem os compartilhamentos de rede, contanto que os dispositivos tenham acesso a um controlador de domínio local usando um caminho UNC.

## <a name="printers"></a>Impressoras

Embora as impressoras não possam ser descobertas automaticamente em um ambiente somente na nuvem, os usuários também podem usar o caminho UNC das impressoras para adicioná-las diretamente.

<!--add fuller material on printers when available-->