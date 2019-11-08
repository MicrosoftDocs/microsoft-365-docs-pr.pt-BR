---
title: Acessar recursos locais de um dispositivo associado ao Azure AD no Microsoft 365 Business
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
ms.openlocfilehash: 2af5d4b4f84f39f5b157313e5b38ef030da7263d
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38030525"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>Acessar recursos locais de um dispositivo associado ao Azure AD no Microsoft 365 Business

Qualquer dispositivo Windows 10 que seja associado ao Active Directory do Azure terá acesso a todos os recursos baseados na nuvem, como seus aplicativos do Office 365 e pode ser protegido pelo Microsoft 365 Business. Para permitir o acesso a recursos locais, como aplicativos de linha de negócios (LOB), compartilhamentos de arquivos e impressoras, você deve sincronizar o Active Directory local com o Azure Active Directory usando o [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect). 

Confira [introdução ao gerenciamento de dispositivos no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction) para saber mais.
As etapas também são resumidas nas seções a seguir.

## <a name="run-azure-ad-connect"></a>Executar o Azure AD Connect

Conclua as etapas a seguir para habilitar os dispositivos ingressados no Azure AD da sua organização para acessar recursos locais.
  
1. Para sincronizar seus usuários, grupos e contatos do Active Directory local no Azure Active Directory, execute o assistente de sincronização de diretórios e o Azure AD Connect, conforme descrito em [Configurar a sincronização de diretórios para o Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
2. Após a conclusão da sincronização de diretório, verifique se os dispositivos Windows 10 da sua organização estão associados ao Azure AD. Esta etapa é feita individualmente em cada dispositivo Windows 10. Consulte [configurar dispositivos Windows para usuários do Microsoft 365 Business](set-up-windows-devices.md) para obter detalhes. 
    
3. Depois que os dispositivos Windows 10 são associados ao Azure AD, cada usuário deve reinicializar seus dispositivos e fazer logon com suas credenciais de negócios do Microsoft 365. Todos os dispositivos agora também terão acesso aos recursos locais.
    
Nenhuma etapa adicional é necessária para obter acesso a recursos locais para dispositivos ingressados no Azure AD. Essa é uma funcionalidade interna disponível no Windows 10. 
  
Se sua organização não estiver pronta para implantar na configuração de dispositivo associado ao Azure AD, descrita acima, considere configurar a [configuração do dispositivo associado ao Azure ad híbrido](manage-windows-devices.md).
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a>Considerações ao ingressar em seus dispositivos Windows no Azure AD

Se você for o Azure AD ingressando em um dispositivo do Windows que tenha sido ingressado no domínio ou em um grupo de trabalho, você precisará considerar as seguintes limitações:
  
- Quando um dispositivo do Azure AD se une, ele cria um novo usuário sem fazer referência a um perfil existente. Para corrigir isso, os perfis precisam ser migrados manualmente. Um perfil de usuário contém informações como favoritos, arquivos locais, configurações do navegador, configurações do menu Iniciar, etc. Uma melhor abordagem é localizar uma ferramenta de terceiros para mapear arquivos e configurações existentes para o novo perfil

- Se o dispositivo estiver usando objetos de política de grupo (GPO), alguns GPOs podem não ter um [provedor de serviços de configuração](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) comparável (CSP) no Intune. Execute a [ferramenta MMAT](https://www.microsoft.com/download/details.aspx?id=45520) para localizar CSPs comparáveis para GPOs existentes.

- Os usuários não poderão autenticar em aplicativos que dependem da autenticação do Active Directory. Para lidar com essa avaliação usando um aplicativo herdado e considere a atualização para um aplicativo que usa autenticação moderna, se possível.

- A descoberta de impressora do Active Directory não funcionará. Para corrigir isso, forneça caminhos de impressora diretos para todos os usuários ou aproveite a [impressão de nuvem híbrida](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).
