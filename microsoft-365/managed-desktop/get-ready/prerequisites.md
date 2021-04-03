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
audience: Admin
ms.openlocfilehash: fcfddadf13e000156fa5431cc30bc72f4f3537e2
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581041"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Pré-requisitos da Área de trabalho gerenciada da Microsoft

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

Este tópico descreve os requisitos de infraestrutura que você deve atender para garantir o sucesso com a Área de Trabalho Gerenciada da Microsoft. 


Área | Detalhes do pré-requisito
--- | ---
Licenças |A Área de Trabalho Gerenciada da Microsoft requer a licença do Microsoft 365 E3 com o Microsoft Defender para Ponto de Extremidade (ou equivalentes) atribuída aos seus usuários. Duas licenças para o Azure Active Directory Premium 2 devem estar disponíveis no locatário, mas os usuários não precisam dessa licença. <br>Para obter detalhes sobre os planos de serviço específicos, consulte [Mais sobre licenças](#more-about-licenses) neste tópico.<br>Para obter mais informações sobre licenças disponíveis, consulte Licenciamento do [Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).
Conectividade |  Todos os dispositivos da Área de Trabalho Gerenciada da Microsoft exigem conectividade com vários pontos de extremidade de serviço da Microsoft da rede corporativa.<br><br>Para ver a lista completa de IPs e URLs necessárias, consulte [Configuração de rede](../get-ready/network.md). 
Azure Active Directory |    O Azure Active Directory (Azure AD) deve ser a fonte de autoridade para todas as contas de usuário ou as contas de usuário devem ser sincronizadas do Active Directory local usando a versão mais recente com suporte do Azure AD Connect.<br><br>[O Roaming de Estado Corporativo](/azure/active-directory/devices/enterprise-state-roaming-overview) deve estar habilitado para usuários da Área de Trabalho Gerenciada da Microsoft.<br><br>Para obter mais informações, consulte [Azure AD Connect](/azure/active-directory/hybrid/whatis-azure-ad-connect).<br><br>Para obter mais informações sobre versões suportadas do Azure AD Connect, consulte O histórico de versão [do Azure AD Connect:Version.](/azure/active-directory/hybrid/reference-connect-version-history)
Autenticação |    Se o Azure AD não for a fonte de autenticação primária para contas de usuário, você deverá configurar uma delas no Azure AD Connect:<br>- Sincronização de hash de senha<br>- Autenticação de passagem<br>- Um provedor de identidade externo (incluindo o Windows Server ADFS e IDPs não Microsoft) configurado para atender aos requisitos de integração do Azure AD. Confira as [diretrizes](https://www.microsoft.com/download/details.aspx?id=56843) para obter mais informações. <br><br>Ao definir opções de autenticação com o Azure AD Connect, o writeback de senha também é recomendado. Para obter mais informações, consulte [Writeback de senha](/azure/active-directory/authentication/howto-sspr-writeback). <br><br>Se um provedor de identidade externa for implementado, você deverá validar a solução:<br>- Atende aos requisitos de integração do Azure AD<br>- Oferece suporte ao Acesso Condicional do Azure AD, que permite que a política de conformidade de dispositivos da Área de Trabalho Gerenciada da Microsoft seja configurada<br>- Permite o registro de dispositivos e o uso de serviços ou recursos do Microsoft 365 necessários como parte da Área de Trabalho Gerenciada da Microsoft <br><br>Para obter mais informações sobre opções de autenticação com o Azure AD, consulte Opções de login do usuário do [Azure AD Connect.](/azure/active-directory/connect/active-directory-aadconnect-user-signin)
Microsoft 365 | O OneDrive for Business deve estar habilitado para usuários da Área de Trabalho Gerenciada da Microsoft.<br><br>Embora não seja necessário se inscrever na Área de Trabalho Gerenciada da Microsoft, recomendamos que os seguintes serviços sejam migrados para a nuvem:<br>- Email: migrar para caixas de correio baseadas em nuvem, Exchange online ou configurar com o Exchange Online Híbrido com o Exchange 2013 ou superior, local.<br>- Arquivos e pastas: Migrar para OneDrive for Business ou SharePoint Online.<br>- Ferramentas de colaboração online: Migrar para o Teams.
Gerenciamento de dispositivo | Os dispositivos da Área de Trabalho Gerenciada da Microsoft exigem gerenciamento usando o Microsoft Intune. O Intune deve ser definido como a autoridade de Gerenciamento de Dispositivo Móvel.<br><br>Para obter mais informações, consulte [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Backup e recuperação de dados |  A Área de Trabalho Gerenciada da Microsoft exige que os arquivos sejam sincronizados com o OneDrive for Business para proteção. Os arquivos não sincronizados com o OneDrive for Business não são garantidos pela Área de Trabalho Gerenciada da Microsoft e podem ser perdidos durante as trocas de dispositivos ou as chamadas de suporte que exigem uma redefinição de dispositivo.<br><br>Embora não seja necessário, a Área de Trabalho Gerenciada da Microsoft recomenda fortemente a migração de unidades de rede mapeadas para a solução de nuvem apropriada. Para obter mais informações, [consulte Preparar unidades mapeadas para a Área de Trabalho Gerenciada da Microsoft](mapped-drives.md)

Quando estiver pronto para começar a trabalhar com a Área de Trabalho Gerenciada da Microsoft, entre em contato com o Microsoft Account Manager. 

## <a name="more-about-licenses"></a>Mais sobre licenças

A Área de Trabalho Gerenciada da Microsoft requer determinadas opções de licença para funcionar. Consulte [Tecnologias da Área de Trabalho Gerenciada](../intro/technologies.md) da Microsoft para obter informações sobre como essas licenças são usadas.

> [!TIP]
> Para atribuir essas opções de licença a usuários específicos, recomendamos que você aproveite o recurso de licenciamento baseado em grupo [do](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) Azure Active Directory.

- Azure Active Directory Premium P1
- Microsoft Intune 
- Windows 10 Enterprise  
- Microsoft Defender para Ponto de Extremidade
- Microsoft 365 Apps para empresas
- Microsoft Teams
- [SharePoint Online (Plano 2)](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online (Plano 2)](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans) 


> [!TIP]
> O Microsoft Account Manager ajudará você a revisar suas licenças e planos de serviço atuais e a encontrar o caminho mais eficiente para obter quaisquer licenças ou planos de serviço adicionais que você possa precisar, evitando a duplicação.

## <a name="steps-to-get-ready"></a>Etapas para se preparar

1. Revise [os pré-requisitos da Área de Trabalho Gerenciada da Microsoft.](prerequisites.md) (Este artigo)
2. Use [ferramentas de avaliação de preparação.](readiness-assessment-tool.md)
3. [Pré-requisitos para contas de convidados](guest-accounts.md)
4. [Configuração de rede na Área de Trabalho Gerenciada da Microsoft](network.md)
5. [Preparar certificados e perfis de rede da Área de Trabalho Gerenciada da Microsoft](certs-wifi-lan.md)
6. [Preparar o acesso aos recursos locais da Área de Trabalho Gerenciada da Microsoft](authentication.md)
7. [Aplicativos na Área de Trabalho Gerenciada da Microsoft](apps.md)
8. [Preparar unidades mapeadas da Área de Trabalho Gerenciada da Microsoft](mapped-drives.md)
9. [Preparar recursos de impressão da Área de Trabalho Gerenciada da Microsoft](printing.md)
