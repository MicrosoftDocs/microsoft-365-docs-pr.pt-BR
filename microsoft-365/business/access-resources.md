---
title: Acessar recursos locais de um dispositivo ingressado no Azure AD no Microsoft 365 Business
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Saiba como obter acesso a recursos locais, como aplicativos de linha de negócios, compartilhamentos de arquivos e impressoras de um dispositivo do Azure Active Directory ingressado no Windows 10.
ms.openlocfilehash: 27549d6c3b03413f2f05c69845caad155333ca97
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580305"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>Acessar recursos locais de um dispositivo ingressado no Azure AD no Microsoft 365 Business Premium

Este artigo se aplica ao Microsoft 365 Business Premium.

Qualquer dispositivo Windows 10 ingressado no Azure Active Directory tem acesso a todos os recursos baseados em nuvem, como seus aplicativos do Microsoft 365, e pode ser protegido pelo Microsoft 365 Business Premium. Você também pode permitir o acesso a recursos locais, como aplicativos de linha de negócios (LOB), compartilhamentos de arquivos e impressoras. Para permitir o acesso, use [o Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect) para sincronizar seu Active Directory local com o Azure Active Directory. 

Para saber mais, confira [Introdução ao gerenciamento de dispositivos no Azure Active Directory](/azure/active-directory/device-management-introduction).
As etapas também são resumidas nas seções a seguir.
 
## <a name="run-azure-ad-connect"></a>Executar o Azure AD Connect

Conclua as etapas a seguir para habilitar os dispositivos ingressados no Azure AD da sua organização para acessar recursos locais.
  
1. Para sincronizar seus usuários, grupos e contatos do Active Directory local no Azure Active Directory, execute o assistente de sincronização de diretórios e o Azure AD Connect, conforme descrito em Configurar a sincronização de diretórios para [o Office 365](../enterprise/set-up-directory-synchronization.md).
    
2. Depois que a sincronização de diretórios for concluída, certifique-se de que os dispositivos Windows 10 da sua organização estejam ingressados no Azure AD. Esta etapa é feita individualmente em cada dispositivo Windows 10. Consulte [Configurar dispositivos Windows para usuários do Microsoft 365 Business Premium](set-up-windows-devices.md) para obter detalhes. 
    
3. Depois que os dispositivos Windows 10 ingressarem no Azure AD, cada usuário deverá reiniciar seus dispositivos e entrar com suas credenciais do Microsoft 365 Business Premium. Todos os dispositivos agora têm acesso a recursos locais também.
    
Nenhuma etapa adicional é necessária para obter acesso a recursos locais para dispositivos ingressados no Azure AD. Essa funcionalidade é criada no Windows 10. 

Se você tiver planos de fazer logon no dispositivo AADJ que não seja o método de senha Como PIN/Biométrica por meio do logon de credencial WHFB e, em seguida, acessar recursos locais (compartilhamentos,impressoras.. etc), siga https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
Se sua organização não estiver pronta para implantar na configuração de dispositivo ingressada no Azure AD descrita acima, considere configurar a configuração de dispositivo ingressada no [Azure AD híbrido.](manage-windows-devices.md)
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Considerações ao ingressar dispositivos Windows no Azure AD

Se o dispositivo Windows que você ingressou no Azure-AD foi ingressado anteriormente no domínio ou em um grupo de trabalho, considere as seguintes limitações:
  
- Quando um dispositivo do Azure AD entra, ele cria um novo usuário sem fazer referência a um perfil existente. Os perfis devem ser migrados manualmente. Um perfil de usuário contém informações como favoritos, arquivos locais, configurações do navegador e configurações de menu Iniciar. Uma melhor abordagem é encontrar uma ferramenta de terceiros para mapear arquivos e configurações existentes para o novo perfil.

- Se o dispositivo estiver usando Objetos de Política de Grupo (GPO), alguns GPOs podem não ter um CSP [(Provedor](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) de Serviços de Configuração) comparável no Intune. Execute a [ferramenta MMAT](https://www.microsoft.com/download/details.aspx?id=45520) para encontrar CSPs comparáveis para GPOs existentes.

- Os usuários podem não ser capazes de se autenticar em aplicativos que dependem da autenticação do Active Directory. Avalie o aplicativo herdado e considere atualizar para um aplicativo que usa a Auth moderna, se possível.

- A descoberta da impressora do Active Directory não funcionará. Você pode fornecer caminhos de impressora diretos para todos os usuários ou usar [Impressão Universal](/universal-print/).

### <a name="related-articles"></a>Artigos relacionados

[Pré-requisitos para o Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)
