---
title: Pré-requisitos da Área de trabalho gerenciada da Microsoft
description: Licenças, contas do Azure, configurações de autenticação e configurações do Microsoft 365 para configurar antes de se inscrever na Área de Trabalho Gerenciada da Microsoft
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

Este tópico descreve os requisitos de infraestrutura que você deve atender para garantir o sucesso com a Área de Trabalho Gerenciada da Microsoft. 


Área | Detalhes dos pré-requisitos
--- | ---
Licenciamento |A Área de Trabalho Gerenciada da Microsoft requer a licença do Microsoft 365 E3 com o Microsoft Defender para o Ponto de Extremidade e o Azure Active Directory Premium 2 (ou equivalentes).<br>Para obter detalhes sobre os planos de serviço específicos, [consulte Mais sobre licenças](#more-about-licenses) neste tópico.<br>Para saber mais sobre as licenças disponíveis, confira [o licenciamento do Microsoft 365.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)
Conectividade |  Todos os dispositivos da Área de Trabalho Gerenciada da Microsoft exigem conectividade com vários pontos de extremidade de serviço da Microsoft da rede corporativa.<br><br>Para ver a lista completa de IPs e URLs necessários, consulte [Configuração de rede.](../get-ready/network.md) 
Azure Active Directory |    O Azure Active Directory (Azure AD) deve ser a fonte de autoridade para todas as contas de usuário ou as contas de usuário devem ser sincronizadas do Active Directory local usando a versão mais recente com suporte do Azure AD Connect.<br><br>[O Enterprise State Roaming](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) deve estar habilitado para usuários da Área de Trabalho Gerenciada da Microsoft.<br><br>Para saber mais, confira [Azure AD Connect.](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)<br><br>Para obter mais informações sobre as versões do Azure AD Connect com suporte, consulte O histórico de versões do [Azure AD Connect:Version.](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history)
Autenticação |    Se o Azure AD não for a origem da autenticação principal para contas de usuário, você deverá configurar uma delas no Azure AD Connect:<br>- Sincronização de hash de senha<br>- Autenticação de passagem<br>- Um provedor de identidade externo (incluindo Windows Server ADFS e IDPs não Microsoft) configurado para atender aos requisitos de integração do Azure AD. Consulte as [diretrizes](https://www.microsoft.com/download/details.aspx?id=56843) para obter mais informações. <br><br>Ao definir opções de autenticação com o Azure AD Connect, o write-back de senha também é recomendado. Para obter mais informações, consulte [Write-back de senha.](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback) <br><br>Se um provedor de identidade externo for implementado, você deverá validar a solução:<br>– Atende aos requisitos de integração do Azure AD<br>– Dá suporte ao Acesso Condicional do Azure AD, que permite que a política de conformidade do dispositivo da Área de Trabalho Gerenciada da Microsoft seja configurada<br>– Permite o registro de dispositivos e o uso de serviços ou recursos do Microsoft 365 necessários como parte da Área de Trabalho Gerenciada da Microsoft <br><br>Para obter mais informações sobre opções de autenticação com o Azure AD, consulte as opções de login do usuário do [Azure AD Connect.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)
Microsoft 365 | O OneDrive for Business deve estar habilitado para usuários da Área de Trabalho Gerenciada da Microsoft.<br><br>Embora não seja necessário se inscrever na Área de Trabalho Gerenciada da Microsoft, é altamente recomendável que os seguintes serviços sejam migrados para a nuvem:<br>- Email: Migrar para caixas de correio baseadas em nuvem, Exchange Online ou configurar com o Exchange Online Híbrido com o Exchange 2013 ou superior, localmente.<br>- Arquivos e pastas: Migrar para o OneDrive for Business ou SharePoint Online.<br>- Ferramentas de colaboração online: Migrar para o Teams.
Gerenciamento de dispositivo | Os dispositivos da Área de Trabalho Gerenciada da Microsoft exigem gerenciamento usando o Microsoft Intune. O Intune deve ser definido como a autoridade de gerenciamento de dispositivo móvel.<br><br>Para obter mais informações, consulte [o Microsoft Intune.](https://www.microsoft.com/cloud-platform/microsoft-intune) 
Backup e recuperação de dados |  A Área de Trabalho Gerenciada da Microsoft exige que os arquivos sejam sincronizados com o OneDrive for Business para proteção. Os arquivos não sincronizados com o OneDrive for Business não são garantidos pela Área de Trabalho Gerenciada da Microsoft e podem ser perdidos durante trocas de dispositivos ou chamadas de suporte que exigem uma redefinição de dispositivo.<br><br>Embora não seja necessário, a Área de Trabalho Gerenciada da Microsoft recomenda a migração de unidades de rede mapeadas para a solução de nuvem apropriada. Para obter mais informações, consulte [Preparar unidades mapeadas para a Área de Trabalho Gerenciada da Microsoft](mapped-drives.md)

Quando você estiver pronto para começar a trabalhar com a Área de Trabalho Gerenciada da Microsoft, entre em contato com o Gerente de Contas da Microsoft. 

## <a name="more-about-licenses"></a>Mais informações sobre licenças

A Área de Trabalho Gerenciada da Microsoft requer determinadas opções de licença para funcionar. Confira [as tecnologias da Área de](../intro/technologies.md) Trabalho Gerenciada da Microsoft para obter informações sobre como essas licenças são usadas.

> [!TIP]
> Para atribuir essas opções de licença a usuários específicos, recomendamos que você aproveite o recurso de licenciamento baseado em grupo [do](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) Azure Active Directory.

- Azure Active Directory Premium P2
- Microsoft Intune 
- Windows 10 Enterprise  
- Microsoft Defender para Ponto de Extremidade
- Microsoft 365 Apps para empresas
- Microsoft Teams
- [SharePoint Online (Plano 2)](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online (Plano 2)](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans) 


> [!TIP]
> Seu Microsoft Account Manager ajudará você a revisar suas licenças e planos de serviço atuais e a encontrar o caminho mais eficiente para obter quaisquer licenças adicionais ou planos de serviço que você possa precisar, evitando a duplicação.
