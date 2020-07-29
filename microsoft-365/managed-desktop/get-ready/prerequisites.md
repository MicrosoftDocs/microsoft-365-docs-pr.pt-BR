---
title: Pré-requisitos da Área de trabalho gerenciada da Microsoft
description: ''
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 4751a5a38229039ae325c0efc9353d4582243349
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430478"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Pré-requisitos da Área de trabalho gerenciada da Microsoft

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

Este tópico descreve os requisitos de infraestrutura que você deve atender para garantir o sucesso com a área de trabalho gerenciada da Microsoft. 

O Microsoft FastTrack está disponível para ajudá-lo a atender a esses requisitos e ajudá-lo a se preparar para participar da área de trabalho gerenciada pela Microsoft. Para obter mais informações, consulte [Microsoft FastTrack](https://fasttrack.microsoft.com/about). 

Área | Detalhes do pré-requisito
--- | ---
Licenças |O Microsoft Managed desktop requer uma das seguintes licenças do Microsoft 365 (ou equivalentes):<br>-Microsoft 365 e5<br>-Microsoft 365 E3 com o complemento de segurança do Microsoft 365 e5<br><br>Para obter detalhes sobre os planos de serviço específicos e sua função na área de trabalho gerenciada da Microsoft, consulte [mais sobre licenças](#more-about-licenses) neste tópico.<br>Para obter mais informações sobre licenças disponíveis, consulte [Microsoft 365 Licensing](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).
Conectividade |  Todos os dispositivos de área de trabalho gerenciados da Microsoft exigem conectividade com vários pontos de extremidade do serviço Microsoft a partir da rede corporativa.<br><br>Para obter a lista completa de IPs e URLs necessários, confira [configuração de rede](../get-ready/network.md). 
Azure Active Directory |    O Azure Active Directory (Azure AD) deve ser a fonte de autoridade para todas as contas de usuário, ou as contas de usuário devem ser sincronizadas a partir do Active Directory local usando a versão mais recente suportada do Azure AD Connect.<br><br>O [roaming de estado corporativo](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) deve ser habilitado para usuários da área de trabalho gerenciada da Microsoft.<br><br>Para obter mais informações, consulte [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect).<br><br>Para obter mais informações sobre versões compatíveis do Azure AD Connect, consulte [Azure ad Connect: versão do histórico de versões](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history).
Autenticação |    Se o Azure AD não for a fonte de autenticação principal para contas de usuário, você deverá configurar uma delas no Azure AD Connect:<br>-Sincronização de hash de senha<br>-Autenticação de passagem<br>– Um provedor de identidade externa (incluindo o Windows Server ADFS e não-Microsoft IDPs) configurado para atender aos requisitos de integração do Azure AD. Consulte as [diretrizes](https://www.microsoft.com/en-us/download/details.aspx?id=56843) para obter mais informações. <br><br>Ao definir as opções de autenticação com o Azure AD Connect, o Write-back de senha também é recomendado. Para obter mais informações, consulte [write-back de senha](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). <br><br>Se um provedor de identidade externo for implementado, você deverá validar a solução:<br>– Atende aos requisitos de integração do Azure AD<br>– Oferece suporte ao acesso condicional do Azure AD, para habilitar a configuração da política de conformidade do dispositivo MMD<br>– Habilita o registro de dispositivos e o uso de serviços ou recursos do Microsoft 365 necessários como parte da área de trabalho gerenciada da Microsoft <br><br>Para obter mais informações sobre as opções de autenticação com o Azure AD, confira [Opções de logon do usuário do Azure ad Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin).
Microsoft 365 | O OneDrive for Business deve estar habilitado para usuários da área de trabalho gerenciada da Microsoft.<br><br>Embora não seja necessário inscrever-se com a área de trabalho gerenciada da Microsoft, é altamente recomendável que os seguintes serviços sejam migrados para a nuvem:<br>– Email: migrar para caixas de correio baseadas em nuvem, Exchange Online ou configurar com o Exchange Online híbrido com o Exchange 2013 ou superior, no local.<br>-Arquivos e pastas: migrar para o OneDrive for Business ou o SharePoint Online.<br>– Ferramentas de colaboração online: migrar para o Microsoft Teams.
Gerenciamento de dispositivo | Os dispositivos de área de trabalho gerenciada da Microsoft exigem gerenciamento usando o Microsoft Intune. O Intune deve ser definido como a autoridade de gerenciamento de dispositivo móvel.<br><br>Para obter mais informações, consulte [o Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Backup e recuperação de dados | O Microsoft Managed desktop exige que os arquivos sejam sincronizados com o OneDrive for Business para proteção. Qualquer arquivo não sincronizado com o OneDrive for Business não é garantido pela área de trabalho gerenciada pela Microsoft e pode ser perdido durante trocas de dispositivos ou chamadas de suporte que exijam uma redefinição de dispositivo.<br><br>Embora não seja obrigatório, a área de trabalho gerenciada da Microsoft recomenda enfaticamente a migração de unidades de rede mapeadas para a solução de nuvem apropriada. Para obter mais informações, consulte [preparar unidades mapeadas para a área de trabalho gerenciada da Microsoft](mapped-drives.md)

Quando estiver pronto para começar a usar a área de trabalho gerenciada da Microsoft, entre em contato com o gerente de contas da Microsoft. 

## <a name="more-about-licenses"></a>Mais sobre licenças

O Microsoft Managed desktop requer determinadas opções de licença para funcionar. Essas opções estão disponíveis em vários pacotes de licença, alguns dos quais você já pode ter. Esta tabela mostra quais opções necessárias estão disponíveis em quais licenças e resume sua função na área de trabalho gerenciada da Microsoft.

> [!TIP]
> Para atribuir essas opções de licença a usuários específicos, recomendamos que você aproveite o [recurso de licenciamento baseado em grupo](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) do Azure Active Directory.



|Opção de licença |Disponível em *qualquer* um desses produtos de licença |Como a área de trabalho gerenciada da Microsoft o usa|
|-------------|-------------|-------------|
|Azure Active Directory Premium P1     |-Microsoft 365 e5<br>-Microsoft 365 E3 + Microsoft 365 *E5* Security Add-on<br>– Enterprise Mobility + Security e5<br>– Enterprise Mobility + Security E3<br>-Azure Active Directory Premium P1|  Fornece acesso aos serviços do Microsoft Cloud; permite que o AutoPilot Registre dispositivos      |
|Microsoft Intune | -Microsoft 365 e5<br>-Microsoft 365 E3 + Microsoft 365 *E5* Security Add-on<br>– Enterprise Mobility + Security e5<br>– Enterprise Mobility + Security E3<br>– Microsoft Intune  |  Necessário para registrar dispositivos, implantar atualizações e gerenciar dispositivos       |
|Windows 10 Enterprise  |-Microsoft 365 e5<br>-Microsoft 365 E3 + Microsoft 365 *E5* Security Add-on<br>– Windows 10 Enterprise E3<br>– Windows 10 Enterprise e5 | Oferece recursos da empresa do Windows 10       |
|Proteção avançada contra ameaças do Microsoft Defender | -Microsoft 365 e5<br>-Microsoft 365 E3 + Microsoft 365 *E5* Security Add-on<br>– Windows 10 Enterprise e5<br>– Proteção avançada contra ameaças do Microsoft defender   |  Oferece detecção, monitoramento, alerta e resposta a ameaças  |
|Microsoft 365 Apps para empresas  |-Microsoft 365 e5<br>-Microsoft 365 E3<br>-Office 365 e5<br>-Office 365 E3| Ativa ferramentas de colaboração e de produtividade do Office    |

> [!TIP]
> O gerente de contas da Microsoft ajudará você a revisar suas licenças atuais e seus planos de serviço e encontrará o caminho mais eficiente para obter qualquer licença ou plano de serviço adicional que você possa precisar, enquanto evita a duplicação.
