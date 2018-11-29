---
title: Acesso a recursos de um dispositivo associado ao AD Azure no Microsoft 365 Business local
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Saiba como obter acesso a recursos locais, como aplicativos de linha de negócios, compartilhamentos de arquivos e impressoras a partir de um Windows Azure Active Directory ingressou dispositivo Windows 10.
ms.openlocfilehash: 0a5d4b0828888fcb99676223000c446479f84ddc
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864706"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>Acesso a recursos de um dispositivo associado ao AD Azure no Microsoft 365 Business local

Qualquer dispositivo de 10 do Windows Azure Active Directory ingressou terão acesso a todos os recursos baseados em nuvem, como seus aplicativos do Office 365 e pode ser protegido pela Microsoft 365 Business. Para permitir o acesso aos recursos locais como aplicativos de linha de negócios (LOB), compartilhamentos de arquivos e impressoras também, você deve sincronizar seu Active Directory no local com o Windows Azure Active Directory usando [Conectar do Azure AD](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect). Consulte a [Introdução ao gerenciamento de dispositivo no Windows Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) para saber mais. 
  
## <a name="run-azure-ad-connect"></a>Conecte-se de executar o Azure AD.

Conclua as seguintes etapas para permitir que os dispositivos da sua organização Azure AD ingressado acessar recursos locais.
  
1. Para sincronizar seus usuários, grupos e contatos do Active Directory local para o Windows Azure Active Directory, execute o Assistente de sincronização de diretório e o Azure AD conectar-se como descrito em [Configurar a sincronização de diretório para o Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
2. Depois que a sincronização de diretório estiver concluída, verifique se Windows 10 dispositivos de sua organização são Azure AD ingressado. Esta etapa é realizada individualmente em cada dispositivo Windows 10. Para obter detalhes, consulte [Configurar os dispositivos do Windows para usuários do Microsoft 365 Business](set-up-windows-devices.md) . 
    
3. Depois que os dispositivos Windows 10 estiverem Azure AD ingressado, cada usuário deve reinicializar seus dispositivos e o logon com suas credenciais do Microsoft 365 Business. Todos os dispositivos terão acesso aos recursos de local também.
    
Não há etapas adicionais são necessárias para obter acesso a recursos do Windows Azure AD ingressou dispositivos no local. Isso é interna funcionalidade disponível no Windows 10. 
  
Se sua organização não estiver pronta para implantar o Windows Azure AD ingressou dispositivo configuração descrita acima, considere a configuração de [configuração de dispositivo ingressado for híbrida Azure AD](manage-windows-devices.md).
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a>Considerações ao ingressar seus dispositivos do Windows Azure AD.

Se você estiver Azure AD ingressar em um dispositivo do Windows que tenha sido previamente associados a um domínio ou em um grupo de trabalho, você precisa considerar as seguintes limitações:
  
- Quando um dispositivo Azure AD ingressa, ele cria um novo usuário sem fazer referência a um perfil existente. Para corrigir esse problema, perfis precisam ser migrados manualmente. Um perfil de usuário contém informações sobre como Favoritos, arquivos locais, as configurações do navegador, configurações do menu Iniciar, etc. Uma abordagem recomendada é encontrar uma ferramenta de terceiros para mapear os arquivos existentes e configurações para o novo perfil
    
- Se o dispositivo está usando objetos de diretiva de grupo (GPO), alguns GPOs podem não ter um comparável [Provedor de serviço de configuração](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) no Intune. Execute a [ferramenta MMAT](https://www.microsoft.com/download/details.aspx?id=45520) para encontrar provedores comparáveis para os GPOs existentes. 
    
- Os usuários não poderão autenticar aos aplicativos que dependem de autenticação do Active Directory. Para lidar com isso avaliar usando um aplicativo de legado e considerar a atualização para um aplicativo que usa autenticação moderna se possível.
    
- Descoberta de impressora do Active Directory não funcionará. Para corrigir esse problema, forneça caminhos de impressora direto para todos os usuários ou aproveitar a [Impressão de nuvem híbrida](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).
    

