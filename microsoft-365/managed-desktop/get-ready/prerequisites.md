---
title: Pré-requisitos da Área de trabalho gerenciada da Microsoft
description: Licenças, contas do Azure, configurações de autenticação e configurações do Microsoft 365 para configurar antes de registrar na área de trabalho gerenciada da Microsoft
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 79ae949d9624021121492edb811a4ea5bfcc729a
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659135"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Pré-requisitos da Área de trabalho gerenciada da Microsoft

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

Este tópico descreve os requisitos de infraestrutura que você deve atender para garantir o sucesso com a área de trabalho gerenciada da Microsoft. 


Área | Detalhes do pré-requisito
--- | ---
Licenças |A área de trabalho gerenciada da Microsoft requer a licença do Microsoft 365 E3 com o Microsoft defender for Endpoint e o Azure Active Directory Premium 2 (ou equivalentes).<br>Para obter detalhes sobre os planos de serviço específicos, consulte [mais sobre as licenças](#more-about-licenses) neste tópico.<br>Para obter mais informações sobre licenças disponíveis, consulte [Microsoft 365 Licensing](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).
Conectividade |  Todos os dispositivos de área de trabalho gerenciados da Microsoft exigem conectividade com vários pontos de extremidade do serviço Microsoft a partir da rede corporativa.<br><br>Para obter a lista completa de IPs e URLs necessários, confira [configuração de rede](../get-ready/network.md). 
Azure Active Directory |    O Azure Active Directory (Azure AD) deve ser a fonte de autoridade para todas as contas de usuário, ou as contas de usuário devem ser sincronizadas a partir do Active Directory local usando a versão mais recente suportada do Azure AD Connect.<br><br>O [roaming de estado corporativo](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) deve ser habilitado para usuários da área de trabalho gerenciada da Microsoft.<br><br>Para obter mais informações, consulte [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect).<br><br>Para obter mais informações sobre versões compatíveis do Azure AD Connect, consulte [Azure ad Connect: versão do histórico de versões](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history).
Autenticação |    Se o Azure AD não for a fonte de autenticação principal para contas de usuário, você deverá configurar uma delas no Azure AD Connect:<br>-Sincronização de hash de senha<br>-Autenticação de passagem<br>– Um provedor de identidade externa (incluindo o Windows Server ADFS e não-Microsoft IDPs) configurado para atender aos requisitos de integração do Azure AD. Consulte as [diretrizes](https://www.microsoft.com/download/details.aspx?id=56843) para obter mais informações. <br><br>Ao definir as opções de autenticação com o Azure AD Connect, o Write-back de senha também é recomendado. Para obter mais informações, consulte [write-back de senha](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). <br><br>Se um provedor de identidade externo for implementado, você deverá validar a solução:<br>– Atende aos requisitos de integração do Azure AD<br>– Oferece suporte ao acesso condicional do Azure AD, que permite que a política de conformidade do dispositivo de área de trabalho gerenciado da Microsoft seja configurada<br>– Habilita o registro de dispositivos e o uso de serviços ou recursos do Microsoft 365 necessários como parte da área de trabalho gerenciada da Microsoft <br><br>Para obter mais informações sobre as opções de autenticação com o Azure AD, confira [Opções de logon do usuário do Azure ad Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin).
Microsoft 365 | O OneDrive for Business deve estar habilitado para usuários da área de trabalho gerenciada da Microsoft.<br><br>Embora não seja necessário inscrever-se com a área de trabalho gerenciada da Microsoft, é altamente recomendável que os seguintes serviços sejam migrados para a nuvem:<br>– Email: migrar para caixas de correio baseadas em nuvem, Exchange Online ou configurar com o Exchange Online híbrido com o Exchange 2013 ou superior, no local.<br>-Arquivos e pastas: migrar para o OneDrive for Business ou o SharePoint Online.<br>– Ferramentas de colaboração online: migrar para o Microsoft Teams.
Gerenciamento de dispositivo | Os dispositivos de área de trabalho gerenciada da Microsoft exigem gerenciamento usando o Microsoft Intune. O Intune deve ser definido como a autoridade de gerenciamento de dispositivo móvel.<br><br>Para obter mais informações, consulte [o Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Backup e recuperação de dados |  O Microsoft Managed desktop exige que os arquivos sejam sincronizados com o OneDrive for Business para proteção. Qualquer arquivo não sincronizado com o OneDrive for Business não é garantido pela área de trabalho gerenciada pela Microsoft e pode ser perdido durante trocas de dispositivos ou chamadas de suporte que exijam uma redefinição de dispositivo.<br><br>Embora não seja obrigatório, a área de trabalho gerenciada da Microsoft recomenda enfaticamente a migração de unidades de rede mapeadas para a solução de nuvem apropriada. Para obter mais informações, consulte [preparar unidades mapeadas para a área de trabalho gerenciada da Microsoft](mapped-drives.md)

Quando estiver pronto para começar a usar a área de trabalho gerenciada da Microsoft, entre em contato com o gerente de contas da Microsoft. 

## <a name="more-about-licenses"></a>Mais sobre licenças

O Microsoft Managed desktop requer determinadas opções de licença para funcionar. Consulte [Microsoft Managed desktop Technologies](../intro/technologies.md) para obter informações sobre como essas licenças são usadas.

> [!TIP]
> Para atribuir essas opções de licença a usuários específicos, recomendamos que você aproveite o [recurso de licenciamento baseado em grupo](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) do Azure Active Directory.

- Azure Active Directory Premium P2
- Microsoft Intune 
- Windows 10 Enterprise  
- Microsoft Defender para Ponto de Extremidade
- Microsoft 365 Apps para empresas
- Microsoft Teams
- [SharePoint Online (Plano 2)](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online (Plano 2)](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans) 


> [!TIP]
> O gerente de contas da Microsoft ajudará você a revisar suas licenças atuais e seus planos de serviço e encontrará o caminho mais eficiente para obter qualquer licença ou plano de serviço adicional que você possa precisar, enquanto evita a duplicação.
