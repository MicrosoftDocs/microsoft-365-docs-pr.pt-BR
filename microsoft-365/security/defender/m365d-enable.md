---
title: Ativar o Microsoft 365 Defender no centro de Microsoft 365 segurança
description: Saiba como habilitar o Microsoft 365 Defender e começar a integrar seu incidente e resposta de segurança.
keywords: get started, enable Microsoft 365 Defender, Microsoft 365 Defender, M365, security, data location, required permissions, license eligibility, settings page
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 3d7564b5d509190c8c8e799c541bb0ca583097f1
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636225"
---
# <a name="turn-on-microsoft-365-defender"></a>Ativar o Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-365-defender.md) unifica seu processo de resposta a incidentes integrando os principais recursos do Microsoft Defender para Ponto de Extremidade, Microsoft Defender para Office 365, Microsoft Cloud App Security e Microsoft Defender para Identidade. Essa experiência unificada adiciona recursos avançados que podem acessados no centro de segurança do Microsoft 365.

Microsoft 365 O Defender é ativado automaticamente quando clientes qualificados com as permissões necessárias visitam Microsoft 365 central de segurança. Leia este artigo para entender vários pré-requisitos e como Microsoft 365 Defender é provisionado.

## <a name="check-license-eligibility-and-required-permissions"></a>Verificar a qualificação da licença e as permissões necessárias

Uma licença para um Microsoft 365 de segurança geralmente lhe dá o direito de usar Microsoft 365 Defender no centro de segurança Microsoft 365 sem custo adicional de licenciamento. Recomendamos obter uma licença de segurança Microsoft 365 E5, segurança do E5, A5 ou A5 ou uma combinação válida de licenças que fornece acesso a todos os serviços com suporte.

Para obter informações detalhadas sobre licenciamento, [leia os requisitos de licenciamento.](prerequisites.md#licensing-requirements)

### <a name="check-your-role"></a>Verificar sua função

Você deve ser um **administrador global ou** um administrador **de** segurança Azure Active Directory ativar o Microsoft 365 Defender. [Exibir suas funções no Azure AD](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Serviços com suporte

Microsoft 365 O Defender agrega dados dos vários serviços com suporte que você já implantou. Ele processará e armazenará dados centralmente para identificar novas percepções e tornar os fluxos de trabalho de resposta centralizados possíveis. Ele faz isso sem afetar implantações, configurações ou dados existentes associados aos serviços integrados.

Para obter a melhor proteção e otimizar Microsoft 365 Defender, recomendamos a implantação de todos os serviços com suporte aplicáveis em sua rede. Para obter mais informações, [leia sobre a implantação de serviços com suporte.](deploy-supported-services.md)

## <a name="onboard-to-the-service"></a>Integração ao serviço
A integração ao Microsoft 365 Defender é simples. No menu de navegação, selecione Microsoft 365 itens do Defender, como Incidentes, Busca, Centro de Ações ou Análise de Ameaças para iniciar o processo de integração. 

### <a name="data-center-location"></a>Local do data center

Microsoft 365 O Defender armazenará e processará dados no [mesmo local usado pelo Microsoft Defender para Ponto de Extremidade.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) Se você não tiver o Microsoft Defender para Ponto de Extremidade, um novo local do data center será selecionado automaticamente com base no local dos serviços Microsoft 365 de segurança ativos. O local do data center selecionado é mostrado na tela.

Selecione **Precisa de ajuda?** no centro de segurança Microsoft 365 para entrar em contato com o suporte da Microsoft sobre o provisionamento Microsoft 365 Defender em um local diferente do data center.

> [!NOTE]
> O Microsoft Defender para Ponto de Extremidade provisiona automaticamente em data centers da União Europeia (UE) quando ativado por meio do Azure Defender. Microsoft 365 O Defender provisiona automaticamente no mesmo data center da UE para clientes que provisionam o Defender para o Ponto de Extremidade dessa maneira.

### <a name="confirm-that-the-service-is-on"></a>Confirmar se o serviço está ativado

Depois que o serviço é provisionado, ele adiciona:

- [Gerenciamento de incidentes](incidents-overview.md)
- [Fila de alertas](investigate-alerts.md)
- Uma central de ações para gerenciar [investigações e respostas automatizadas](m365d-autoir.md)
- [Recursos avançados de busca](advanced-hunting-overview.md)
- Análise de ameaças

![Imagem do painel Microsoft 365 de navegação do centro de segurança com recursos do Microsoft 365 Defender Microsoft 365 central de segurança com gerenciamento de incidentes e outros ](../../media/overview-incident.png)
 *recursos do Microsoft 365 Defender*

### <a name="getting-microsoft-defender-for-identity-data"></a>Obter dados do Microsoft Defender para Identidade 
Para habilitar a integração com Microsoft Cloud App Security, você precisará fazer logon no Microsoft Cloud App Security pelo menos uma vez.

## <a name="get-assistance"></a>Obter assistência

Para obter respostas para as perguntas mais frequentes sobre como a Microsoft 365 Defender, [leia as perguntas frequentes](m365d-enable-faq.md).

A equipe de suporte da Microsoft pode ajudar a provisionamento ou desprovisionamento do serviço e recursos relacionados em seu locatário. Para assistência, selecione **Precisa de ajuda?** no centro Microsoft 365 segurança. Ao entrar em contato com o suporte, Microsoft 365 Defender.

## <a name="related-topics"></a>Tópicos relacionados

- [Perguntas frequentes](m365d-enable-faq.md)
- [Requisitos de licenciamento e outros pré-requisitos](prerequisites.md)
- [Implantar serviços com suporte](deploy-supported-services.md)
- [Microsoft 365 Visão geral do Defender](microsoft-365-defender.md)
- [Visão geral do Microsoft Defender para Ponto de Extremidade](../defender-endpoint/microsoft-defender-endpoint.md)
- [Visão geral do Defender Office 365 visão geral](../office-365-security/defender-for-office-365.md)
- [Visão geral do Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)
- [Visão geral do Microsoft Defender para Identidade](/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender para armazenamento de dados do Ponto de Extremidade](../defender-endpoint/data-storage-privacy.md)
