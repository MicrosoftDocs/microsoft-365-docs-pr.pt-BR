---
title: Ative o Microsoft 365 defender no centro de segurança do Microsoft 365
description: Saiba como habilitar o Microsoft 365 defender e começar a integrar seu incidente de segurança e resposta.
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
ms.openlocfilehash: b052f70c1b618adef12c4f70c2b3fe55741697d5
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760501"
---
# <a name="turn-on-microsoft-365-defender"></a>Ativar o Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

O [Microsoft 365 defender](microsoft-threat-protection.md) unifica seu processo de resposta a incidentes por meio da integração de recursos importantes no Microsoft defender para ponto de extremidade, Microsoft defender para Office 365, Microsoft Cloud app Security e Microsoft defender para identidade. Essa experiência unificada adiciona recursos avançados que podem acessados no centro de segurança do Microsoft 365.

O Microsoft 365 defender automaticamente é ativado quando os clientes qualificados com as permissões necessárias visitam a central de segurança da Microsoft 365. Leia este artigo para entender vários pré-requisitos e como o Microsoft 365 defender é provisionado.

## <a name="check-license-eligibility-and-required-permissions"></a>Verificar a qualificação de licenças e as permissões necessárias

Uma licença para um produto de segurança do Microsoft 365 geralmente concede a você o uso do Microsoft 365 defender no centro de segurança do Microsoft 365 sem custo adicional de licenciamento. Recomendamos obter uma licença de segurança do Microsoft 365 e5, E5 Security, a5 ou a5 ou uma combinação válida de licenças que forneçam acesso a todos os serviços com suporte.

Para obter informações detalhadas sobre licenciamento, [Leia os requisitos de licenciamento](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>Verificar sua função

Você deve ser um **administrador global** ou um **administrador de segurança** no Azure Active Directory para ativar o Microsoft 365 defender. [Exibir suas funções no Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Serviços com suporte

O Microsoft 365 defender agrega dados dos vários serviços com suporte que você já tenha implantado. Ele processará e armazenará dados centralmente para identificar novas insights e tornar os fluxos de trabalho de resposta centralizados possíveis. Ele faz isso sem afetar as implantações, as configurações ou os dados existentes associados aos serviços integrados.

Para obter a melhor proteção e otimizar o Microsoft 365 defender, recomendamos implantar todos os serviços compatíveis em sua rede. Para obter mais informações, [Leia sobre a implantação de serviços com suporte](deploy-supported-services.md).

## <a name="before-starting-the-service"></a>Antes de iniciar o serviço

Antes de ativar o serviço, o centro de segurança do Microsoft 365 ([Security.Microsoft.com](https://security.microsoft.com)) mostra a página de configurações do Microsoft 365 defender quando você seleciona **incidentes**, **central de ações** ou **busca** no painel de navegação. Esses itens de navegação não são mostrados se você não estiver qualificado para usar o Microsoft 365 defender.

![Imagem da página de configurações do Microsoft 365 defender mostra se o Microsoft 365 defender não foi ativado nas ](../../media/mtp-enable/mtp-settings.png)
 *configurações do Microsoft 365 defender no centro de segurança do Microsoft 365*

## <a name="starting-the-service"></a>Iniciar o serviço

Para ativar o Microsoft 365 defender, basta selecionar **ativar o microsoft 365 defender** e aplicar a alteração. Você também pode acessar essa opção selecionando **configurações** ([Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) no painel de navegação e, em seguida, selecionando **o Microsoft 365 defender**.

> [!NOTE]
> Se você não vir **as configurações** no painel de navegação ou não conseguir acessar a página, verifique suas permissões e licenças.

### <a name="data-center-location"></a>Local do Data Center

O Microsoft 365 defender armazenará e processará dados no [mesmo local usado pelo Microsoft defender para ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy). Se você não tiver o Microsoft defender para ponto de extremidade, um novo local de Data Center será selecionado automaticamente com base no local dos serviços de segurança do Microsoft 365 ativos. O local do Data Center selecionado é mostrado na tela.

Selecione **precisa de ajuda?** no centro de segurança do Microsoft 365 para entrar em contato com o suporte da Microsoft sobre o provisionamento do Microsoft 365 defender em um local diferente de data center.

> [!NOTE]
> O Microsoft defender for Endpoint provisiona automaticamente nos data centers da União Europeia (UE) quando ativado pelo Azure defender. O Microsoft 365 defender será automaticamente provisionado no mesmo Data Center da UE para clientes que tenham provisionado o defender para ponto de extremidade dessa maneira.

### <a name="confirm-that-the-service-is-on"></a>Confirmar se o serviço está ativado

Depois que o serviço é provisionado, ele adiciona:

- [Gerenciamento de incidentes](incidents-overview.md)
- Uma central de ações para gerenciar [investigações e respostas automatizadas](mtp-autoir.md)
- Recursos [avançados de busca](advanced-hunting-overview.md)

![Imagem do painel de navegação do centro de segurança do Microsoft 365 com o Microsoft 365 defender apresenta ](../../media/mtp-enable/mtp-on.png)
 *o centro de segurança da Microsoft 365 com gerenciamento de incidentes e outros recursos do Microsoft 365 defender*

### <a name="getting-microsoft-defender-for-identity-data"></a>Obtendo dados do Microsoft defender para identidade

Para compartilhar os dados do Microsoft defender para identidade com o Microsoft 365 defender, certifique-se de que o Microsoft Cloud app Security e o Microsoft defender para integração de identidade estejam ativados. [Saiba mais sobre essa integração](https://docs.microsoft.com/cloud-app-security/mdi-integration).

## <a name="get-assistance"></a>Obter assistência

Para obter respostas para as perguntas mais frequentes sobre como ativar o Microsoft 365 defender, [Leia as perguntas frequentes](mtp-enable-faq.md).

A equipe de suporte da Microsoft pode ajudar a provisionar ou desprovisionar o serviço e os recursos relacionados em seu locatário. Para obter ajuda, selecione **precisa de ajuda?** no centro de segurança do Microsoft 365. Ao entrar em contato com o suporte, mencione o Microsoft 365 defender.

## <a name="related-topics"></a>Tópicos relacionados

- [Perguntas frequentes](mtp-enable-faq.md)
- [Requisitos de licenciamento e outros pré-requisitos](prerequisites.md)
- [Implantar serviços com suporte](deploy-supported-services.md)
- [Visão geral do Microsoft 365 defender](microsoft-threat-protection.md)
- [Visão geral do Microsoft defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Visão geral do defender for Office 365](../office-365-security/office-365-atp.md)
- [Visão geral do Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Visão geral do Microsoft defender para identidade](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Armazenamento de dados do Microsoft defender para ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
