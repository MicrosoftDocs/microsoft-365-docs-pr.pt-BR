---
title: Ativar a Proteção contra Ameaças da Microsoft no centro de segurança do Microsoft 365
description: Saiba como habilitar a Proteção contra Ameaças da Microsoft e iniciar a integração do seu incidente de segurança e resposta.
keywords: introdução, habilitar MTP, proteção contra ameaças da Microsoft, M365, segurança, local dos dados, permissões necessárias, qualificação para licença, página Configurações
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b6ac30f7e32bbec80952ad4f2104032886b11503
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016338"
---
# <a name="turn-on-microsoft-threat-protection"></a>Habilitar a Proteção contra Ameaças da Microsoft

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

A [proteção contra ameaças da Microsoft](microsoft-threat-protection.md) unifica seu processo de resposta a incidentes por meio da integração de recursos principais à proteção avançada contra ameaças do Microsoft defender (ATP), Office 365 ATP, Microsoft Cloud app Security e Azure ATP. Essa experiência unificada adiciona recursos avançados que podem acessados no centro de segurança do Microsoft 365.

A proteção contra ameaças da Microsoft automaticamente é ativada quando os clientes qualificados com as permissões necessárias visitam a central de segurança do Microsoft 365. Leia este artigo para entender vários pré-requisitos e como a proteção contra ameaças da Microsoft é provisionada.

## <a name="check-license-eligibility-and-required-permissions"></a>Verificar a qualificação de licenças e as permissões necessárias
Uma licença para um produto de segurança do Microsoft 365 geralmente concede a você o uso da proteção contra ameaças da Microsoft no Microsoft 365, sem custo adicional de licenciamento. Recomendamos obter uma licença de segurança do Microsoft 365 e5, E5 Security, a5 ou a5 ou uma combinação válida de licenças que forneçam acesso a todos os serviços com suporte.

Para obter informações detalhadas sobre licenciamento, [Leia os requisitos de licenciamento](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>Verificar sua função
Você deve ser um **administrador global** ou um **administrador de segurança** no Azure Active Directory para ativar a proteção contra ameaças da Microsoft. [Exibir suas funções no Azure AD](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Serviços com suporte
A proteção contra ameaças da Microsoft agrega dados dos vários serviços com suporte que você já tenha implantado. Ele processará e armazenará dados centralmente para identificar novas insights e tornar os fluxos de trabalho de resposta centralizados possíveis. Ele faz isso sem afetar as implantações, as configurações ou os dados existentes associados aos serviços integrados.

Para obter a melhor proteção e otimizar a proteção contra ameaças da Microsoft, recomendamos implantar todos os serviços compatíveis em sua rede. Para obter mais informações, [Leia sobre a implantação de serviços com suporte](deploy-supported-services.md).

## <a name="before-starting-the-service"></a>Antes de iniciar o serviço
Antes de ativar o serviço, o centro de segurança do Microsoft 365 ([Security.Microsoft.com](https://security.microsoft.com)) mostra a página Configurações de proteção contra ameaças da Microsoft quando você seleciona **incidentes**, **central de ações**ou **busca** no painel de navegação. Esses itens de navegação não são mostrados se você não estiver qualificado para usar a proteção contra ameaças da Microsoft.

![Imagem da página de configurações de proteção contra ameaças da Microsoft mostra se a proteção contra ameaças da Microsoft não foi ativada nas ](../../media/mtp-enable/mtp-settings.png)
 *configurações de proteção contra ameaças da Microsoft no centro de segurança do Microsoft 365*

## <a name="starting-the-service"></a>Iniciar o serviço
Para ativar a proteção contra ameaças da Microsoft, basta selecionar **ativar a proteção contra ameaças da Microsoft** e aplicar a alteração. Você também pode acessar essa opção selecionando **configurações** ([Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) no painel de navegação e, em seguida, selecionando **proteção contra ameaças da Microsoft**.

>[!NOTE]
>Se você não vir **as configurações** no painel de navegação ou não conseguir acessar a página, verifique suas permissões e licenças.

### <a name="data-center-location"></a>Local do Data Center
A proteção contra ameaças da Microsoft armazenará e processará dados no [mesmo local usado pelo Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy). Se você não tiver o Microsoft defender ATP, um novo local de Data Center será selecionado automaticamente com base no local dos serviços de segurança do Microsoft 365 ativos. O local do Data Center selecionado é mostrado na tela. 

Selecione **precisa de ajuda?** no centro de segurança do Microsoft 365 para entrar em contato com o suporte da Microsoft sobre o provisionamento de proteção contra ameaças da Microsoft em um local diferente de data center. 

>[!NOTE]
>O Microsoft defender ATP provisiona automaticamente nos data centers da União Européia (UE) quando ativado pela central de segurança do Azure. A proteção contra ameaças da Microsoft será provisionada automaticamente no mesmo Data Center da UE para clientes que tenham provisionado o Microsoft defender ATP dessa maneira. 

### <a name="confirm-that-the-service-is-on"></a>Confirmar se o serviço está ativado
Depois que o serviço é provisionado, ele adiciona:

- [Gerenciamento de incidentes](incidents-overview.md)
- Uma central de ações para gerenciar [investigações e respostas automatizadas](mtp-autoir.md)
- Recursos [avançados de busca](advanced-hunting-overview.md)

![Imagem do painel de navegação do centro de segurança do Microsoft 365 com o Microsoft Threat Protection apresenta a ](../../media/mtp-enable/mtp-on.png)
 *central de segurança da Microsoft 365 com gerenciamento de incidentes e outros recursos de proteção contra ameaças da Microsoft*

### <a name="getting-azure-atp-data"></a>Obter dados da ATP do Azure
Para compartilhar dados da ATP do Azure com a Proteção contra Ameaças da Microsoft, verifique se a integração do Microsoft Cloud App Security e da ATP do Azure está ativada. [Saiba mais sobre esta integração](https://docs.microsoft.com/cloud-app-security/aatp-integration) 


## <a name="turn-off-microsoft-threat-protection"></a>Desabilitar a Proteção contra Ameaças da Microsoft
Para parar de usar o serviço de Proteção contra Ameaças da Microsoft, vá para **Configurações** > ** Proteção contra Ameaças da Microsoft** > **Aceitar/Recusar** no centro de segurança do Microsoft 365. Desmarque **ativar a proteção contra ameaças da Microsoft** e aplicar as alterações.

Os recursos correspondentes serão removidos da central de segurança do Microsoft 365.

## <a name="get-assistance"></a>Obter assistência

Para obter respostas para as perguntas mais frequentes sobre como ativar a proteção contra ameaças [da Microsoft, leia as perguntas frequentes](mtp-enable-faq.md).

A equipe de suporte da Microsoft pode ajudar a provisionar ou desprovisionar o serviço e os recursos relacionados em seu locatário. Para obter ajuda, selecione **precisa de ajuda?** no centro de segurança do Microsoft 365. Ao entrar em contato com o suporte, mencione a proteção contra ameaças da Microsoft.

## <a name="related-topics"></a>Tópicos relacionados

- [Perguntas frequentes](mtp-enable-faq.md)
- [Requisitos de licenciamento e outros pré-requisitos](prerequisites.md)
- [Implantar serviços com suporte](deploy-supported-services.md)
- [Visão geral da Proteção contra Ameaças da Microsoft](microsoft-threat-protection.md)
- [Visão geral do Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Visão geral da ATP do Office 365](../office-365-security/office-365-atp.md)
- [Visão geral do Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Visão geral da ATP do Azure](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Armazenamento de dados da ATP do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)