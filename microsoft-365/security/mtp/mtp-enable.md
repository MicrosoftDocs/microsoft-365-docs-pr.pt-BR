---
title: Ativar o Microsoft 365 Defender na central de segurança do Microsoft 365
description: Saiba como habilitar o Microsoft 365 Defender e começar a integrar seu incidente de segurança e resposta.
keywords: get started, enable MTP, Microsoft Threat Protection, M365, security, data location, required permissions, license eligibility, settings page
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 19f035a271626077911b05082a4aba6d67355cdb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930217"
---
# <a name="turn-on-microsoft-365-defender"></a>Ativar o Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

[O Microsoft 365 Defender](microsoft-threat-protection.md) unifica o processo de resposta a incidentes integrando os principais recursos do Microsoft Defender para Ponto de Extremidade, do Microsoft Defender para Office 365, do Microsoft Cloud App Security e do Microsoft Defender para Identidade. Essa experiência unificada adiciona recursos avançados que podem acessados no centro de segurança do Microsoft 365.

O Microsoft 365 Defender é ativado automaticamente quando clientes qualificados com as permissões necessárias visitam a central de segurança do Microsoft 365. Leia este artigo para entender vários pré-requisitos e como o Microsoft 365 Defender é provisionado.

## <a name="check-license-eligibility-and-required-permissions"></a>Verificar a qualificação de licença e as permissões necessárias

Uma licença para um produto de segurança do Microsoft 365 geralmente dá o direito de usar o Microsoft 365 Defender na central de segurança do Microsoft 365 sem custo adicional de licenciamento. Recomendamos obter uma licença do Microsoft 365 E5, E5 Security, A5 ou A5 Security ou uma combinação válida de licenças que fornece acesso a todos os serviços com suporte.

Para obter informações detalhadas de licenciamento, [leia os requisitos de licenciamento.](prerequisites.md#licensing-requirements)

### <a name="check-your-role"></a>Verificar sua função

Você deve ser um **administrador global ou** um administrador **de** segurança no Azure Active Directory para ativar o Microsoft 365 Defender. [Exibir suas funções no Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Serviços com suporte

O Microsoft 365 Defender agrega dados dos vários serviços com suporte que você já implantou. Ele processará e armazenará dados centralmente para identificar novas ideias e possibilitar fluxos de trabalho de resposta centralizados. Ele faz isso sem afetar implantações, configurações ou dados existentes associados aos serviços integrados.

Para obter a melhor proteção e otimizar o Microsoft 365 Defender, recomendamos implantar todos os serviços com suporte aplicáveis em sua rede. Para obter mais informações, [leia sobre a implantação de serviços com suporte.](deploy-supported-services.md)

## <a name="before-starting-the-service"></a>Antes de iniciar o serviço

Antes de ativar o serviço, a central de segurança do Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)) mostra a página de  configurações do Microsoft 365 Defender quando você seleciona **Incidentes** **,** Central de Ações ou Busca no painel de navegação. Esses itens de navegação não serão mostrados se você não estiver qualificado para usar o Microsoft 365 Defender.

![Imagem da página de configurações do Microsoft 365 Defender mostrada se o Microsoft 365 Defender não tiver sido ligado às configurações do Microsoft 365 Defender na central de segurança do ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft 365*

## <a name="starting-the-service"></a>Iniciando o serviço

Para ativar o Microsoft 365 Defender, basta selecionar **Ativar o Microsoft 365 Defender** e aplicar a alteração. Você também pode acessar  essa opção selecionando Configurações [(security.microsoft.com/settings)](https://security.microsoft.com/settings)no painel de navegação e selecionando **o Microsoft 365 Defender.**

> [!NOTE]
> Se você não vir **Configurações** no painel de navegação ou não conseguiu acessar a página, verifique suas permissões e licenças.

### <a name="data-center-location"></a>Local do data center

O Microsoft 365 Defender armazenará e processará dados no [mesmo local usado pelo Microsoft Defender para o ponto de extremidade.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) Se você não tiver o Microsoft Defender para o Ponto de Extremidade, um novo local do data center será selecionado automaticamente com base no local dos serviços de segurança ativos do Microsoft 365. O local selecionado do data center é mostrado na tela.

Selecione **Precisa de ajuda?** No centro de segurança do Microsoft 365 para entrar em contato com o suporte da Microsoft sobre o provisionamento do Microsoft 365 Defender em um local diferente do data center.

> [!NOTE]
> O Microsoft Defender para Ponto de Extremidade provisiona automaticamente em data centers da União Europeia (UE) quando ativado por meio do Azure Defender. O Microsoft 365 Defender provisiona automaticamente no mesmo data center da UE para clientes que provisionam o Defender para o Ponto de Extremidade dessa maneira.

### <a name="confirm-that-the-service-is-on"></a>Confirmar se o serviço está ativado

Depois que o serviço é provisionado, ele adiciona:

- [Gerenciamento de incidentes](incidents-overview.md)
- Uma central de ações para gerenciar [investigações e respostas automatizadas](mtp-autoir.md)
- [Recursos avançados de busca](advanced-hunting-overview.md)

![Imagem do painel de navegação da central de segurança do Microsoft 365 com o Microsoft 365 Defender recursos da central de segurança do Microsoft 365 com gerenciamento de incidentes e outros ](../../media/mtp-enable/mtp-on.png)
 *recursos do Microsoft 365 Defender*

### <a name="getting-microsoft-defender-for-identity-data"></a>Obter dados do Microsoft Defender para Identidade

Para compartilhar dados do Microsoft Defender for Identity com o Microsoft 365 Defender, certifique-se de que a integração do Microsoft Cloud App Security e do Microsoft Defender for Identity está 1. [Saiba mais sobre essa integração.](https://docs.microsoft.com/cloud-app-security/mdi-integration)

## <a name="get-assistance"></a>Obter assistência

Para obter respostas para as perguntas mais frequentes sobre como ligar o Microsoft 365 Defender, [leia as perguntas frequentes.](mtp-enable-faq.md)

A equipe de suporte da Microsoft pode ajudar a provisionamento ou desprovisionamento do serviço e dos recursos relacionados em seu locatário. Para assistência, selecione **Precisa de ajuda?** no centro de segurança do Microsoft 365. Ao entrar em contato com o suporte, mencione o Microsoft 365 Defender.

## <a name="related-topics"></a>Tópicos relacionados

- [Perguntas frequentes](mtp-enable-faq.md)
- [Requisitos de licenciamento e outros pré-requisitos](prerequisites.md)
- [Implantar serviços com suporte](deploy-supported-services.md)
- [Visão geral do Microsoft 365 Defender](microsoft-threat-protection.md)
- [Visão geral do Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Visão geral do Defender para Office 365](../office-365-security/office-365-atp.md)
- [Visão geral do Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Visão geral do Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Armazenamento de dados do Microsoft Defender para Pontos de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
