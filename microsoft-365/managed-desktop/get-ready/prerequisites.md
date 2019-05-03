---
title: Pré-requisitos para a área de trabalho gerenciada da Microsoft
description: ''
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 11/1/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 19bd7c553840b0de51f7b26a8f1206a9c5d7b3af
ms.sourcegitcommit: b27650d1388ca136f85fcc662fe3ba069e9ee895
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/02/2019
ms.locfileid: "33560050"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Pré-requisitos para a área de trabalho gerenciada da Microsoft

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

O sucesso com a área de trabalho gerenciada da Microsoft começa com requisitos conhecidos, documentados e acordados para a infraestrutura do cliente. Esta seção descreve os requisitos do infastructure. 

O Microsoft FastTrack está disponível para ajudar os clientes a cumprir esses requisitos e ajudá-lo a se preparar para participar da área de trabalho gerenciada pela Microsoft. Para obter mais informações, consulte [Microsoft FastTrack](https://fasttrack.microsoft.com/about). 

Área | Detalhes do pré-requisito
--- | ---
Licenciamento |A área de trabalho gerenciada da Microsoft requer o seguinte licenciamento da Microsoft 365 (ou as equivalências):<br>-Microsoft 365 e5<br>-Microsoft 365 E3 + Security e5<br><br>Para obter mais informações sobre licenças disponíveis, consulte [Microsoft 365 Licensing](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).
Conectividade |  Todos os dispositivos de área de trabalho gerenciados da Microsoft exigem conectividade com vários pontos de extremidade do serviço Microsoft a partir da rede corporativa.<br><br>Para obter a lista completa de IPs e URLs necessários, confira [configuração de rede](../get-ready/network.md). 
Azure Active Directory |    O Azure Active Directory (Azure AD) deve ser a fonte de autoridade para todas as contas de usuário, ou as contas de usuário devem ser sincronizadas a partir do Active Directory local usando a versão mais recente suportada do Azure AD Connect.<br><br>Para obter mais informações sobre o Azure AD Connect, consulte [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect).<br><br>Para obter mais informações sobre versões compatíveis do Azure AD Connect, consulte [Azure ad Connect: versão do histórico de versões](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history).
Autenticação |    Se o Azure AD não for a fonte de autoridade para contas de usuário, você deverá configurar uma delas no Azure AD Connect:<br>-Sincronização de hash de senha<br>-Autenticação de passagem<br>-Federação com ADFS<br><br>Ao definir as opções de autenticação com o Azure AD Connect, o Write-back de senha também é necessário. Para obter mais informações, consulte [write-back de senha](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). <br><br>Para obter mais informações sobre as opções de autenticação com o Azure AD, confira [Opções de logon do usuário do Azure ad Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin).
Office 365 |    Embora não seja necessário se inscrever na área de trabalho gerenciada da Microsoft, é altamente recomendável que os seguintes serviços sejam migrados para a nuvem:<br>-Email-migrar para caixas de correio baseadas em nuvem, Exchange Online ou ser configurado com o Exchange Online híbrido com o Exchange 2013 ou superior, no local.<br>-Arquivos e pastas – migre para o OneDrive for Business/SharePoint Online.<br>– Ferramentas de colaboração online – migrar para o Microsoft Teams.
Gerenciamento de dispositivo | Os dispositivos de área de trabalho gerenciada da Microsoft exigem gerenciamento usando o Microsoft Intune. O Intune deve ser definido como a autoridade de gerenciamento de dispositivo móvel.<br><br>Para obter mais informações, consulte [o Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Backup e recuperação de dados | O Microsoft Managed desktop exige que os arquivos sejam sincronizados com o OneDrive for Business para proteção. Qualquer arquivo não sincronizado com o OneDrive for Business não é garantido pela área de trabalho gerenciada pela Microsoft e pode ser perdido durante trocas de dispositivos ou chamadas de suporte que exijam uma redefinição de dispositivo.<br><br>Embora não seja obrigatório, a área de trabalho gerenciada da Microsoft recomenda enfaticamente a migração de unidades de rede mapeadas para a solução de nuvem apropriada.  

Quando estiver pronto para começar a usar a área de trabalho gerenciada da Microsoft, entre em contato com o gerente de contas da Microsoft. 
