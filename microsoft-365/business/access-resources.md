---
title: Acessar recursos locais de um dispositivo associado ao Azure AD no Microsoft 365 Business
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Saiba como obter acesso a recursos locais, como aplicativos de linha de negócios, compartilhamento de arquivos e impressoras de um dispositivo Windows 10 associado ao Azure Active Directory.
ms.openlocfilehash: 980efbf09349cc0203ac50ae5e028c008d5694ca
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165892"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>Acessar recursos locais de um dispositivo associado ao Azure AD no Microsoft 365 Business Premium

Qualquer dispositivo Windows 10 que esteja associado ao Azure Active Directory tem acesso a todos os recursos baseados na nuvem, como seus aplicativos do Microsoft 365 e pode ser protegido pelo Microsoft 365 Business Premium. Você também pode permitir o acesso a recursos locais, como aplicativos de linha de negócios (LOB), compartilhamentos de arquivos e impressoras. Para permitir o acesso, use o [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) para sincronizar seu Active Directory local com o Azure Active Directory. 

Para saber mais, confira [Introduction to Device Management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
As etapas também são resumidas nas seções a seguir.

> [!IMPORTANT]
> Este procedimento só é aplicável ao OAuth e ao NTLM. Não há suporte para Kerberos.
 
## <a name="run-azure-ad-connect"></a>Executar o Azure AD Connect

Conclua as etapas a seguir para habilitar os dispositivos ingressados no Azure AD da sua organização para acessar recursos locais.
  
1. Para sincronizar seus usuários, grupos e contatos do Active Directory local no Azure Active Directory, execute o assistente de sincronização de diretórios e o Azure AD Connect, conforme descrito em [Configurar a sincronização de diretórios para o Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).
    
2. Após a conclusão da sincronização de diretório, verifique se os dispositivos Windows 10 da sua organização estão associados ao Azure AD. Esta etapa é feita individualmente em cada dispositivo Windows 10. Consulte [configurar dispositivos Windows para usuários do Microsoft 365 Business Premium](set-up-windows-devices.md) para obter detalhes. 
    
3. Depois que os dispositivos Windows 10 são associados ao Azure AD, cada usuário deve reinicializar seus dispositivos e entrar com suas credenciais do Microsoft 365 Business Premium. Agora, todos os dispositivos também têm acesso a recursos locais.
    
Nenhuma etapa adicional é necessária para obter acesso a recursos locais para dispositivos ingressados no Azure AD. Essa funcionalidade é incorporada no Windows 10. 

Se você planeja fazer logon no dispositivo AADJ que não seja o método de senha, como PIN/bio-Metric via login de credencial do WHFB e, em seguida, acesse recursos locais (compartilhamentos, impressoras. etc.), sigahttps://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
Se sua organização não estiver pronta para implantar na configuração de dispositivo associado ao Azure AD, descrita acima, considere configurar a [configuração do dispositivo associado ao Azure ad híbrido](manage-windows-devices.md).
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Considerações ao ingressar em dispositivos Windows no Azure AD

Se o dispositivo do Windows que você ingressou no Azure no AD tiver ingressado anteriormente no domínio ou em um grupo de trabalho, considere as seguintes limitações:
  
- Quando um dispositivo do Azure AD se une, ele cria um novo usuário sem fazer referência a um perfil existente. Os perfis devem ser migrados manualmente. Um perfil de usuário contém informações como favoritos, arquivos locais, configurações do navegador e configurações do menu iniciar. Uma melhor abordagem é localizar uma ferramenta de terceiros para mapear arquivos e configurações existentes para o novo perfil.

- Se o dispositivo estiver usando objetos de política de grupo (GPO), alguns GPOs podem não ter um [provedor de serviços de configuração](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) comparável (CSP) no Intune. Execute a [ferramenta MMAT](https://www.microsoft.com/download/details.aspx?id=45520) para localizar CSPs comparáveis para GPOs existentes.

- Os usuários não conseguirão se autenticar nos aplicativos que dependem da autenticação do Active Directory. Avalie o aplicativo herdado e considere a atualização para um aplicativo que usa autenticação moderna, se possível.

- A descoberta de impressora do Active Directory não funcionará. Você pode fornecer caminhos de impressora direta para todos os usuários ou usar a [impressão de nuvem híbrida](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).
