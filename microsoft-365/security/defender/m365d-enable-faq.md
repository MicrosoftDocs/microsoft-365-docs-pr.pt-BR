---
title: Perguntas frequentes ao ligar o Microsoft 365 Defender
description: Obter respostas para as perguntas mais frequentes sobre licenciamento, permissões, configurações iniciais e outros produtos e serviços relacionados à habilitação do Microsoft 365 Defender
keywords: perguntas frequentes, perguntas frequentes, GCC, começar, habilitar o Microsoft 365 Defender, o Microsoft 365 Defender, o M365, a segurança, o local dos dados, as permissões necessárias, a qualificação da licença, a página de configurações
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
ms.openlocfilehash: 55c1a3807fe8e28ca12f4f638c1ab2ca717523ed
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933428"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Perguntas frequentes ao ligar o Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Leia respostas às perguntas mais frequentes sobre como acionar o [Microsoft 365 Defender](microsoft-365-defender.md), incluindo licenças e permissões necessárias, implantação de serviços de suporte e configurações iniciais.

Para obter instruções sobre como ativar o serviço, [leia Ativar o Microsoft 365 Defender](m365d-enable.md).

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Não tenho uma licença do Microsoft 365 E5. Ainda posso usar o Microsoft 365 Defender?

Os clientes com as seguintes licenças que não são do E5 podem usar o Microsoft 365 Defender:

- Microsoft Defender para Ponto de Extremidade
- Microsoft Defender para Identidade?
- Microsoft Cloud App Security
- Defender para Office 365 (Plano 2)
 
Para uma lista completa de licenças com suporte, [leia os requisitos de licenciamento.](prerequisites.md#licensing-requirements)

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Preciso instalar ou implantar algo para começar a usar o Microsoft 365 Defender?

Não, o Microsoft 365 Defender consolida dados dos serviços de segurança do Microsoft 365 que você já implantou. Depois que você a ativar, as experiências de incidente, automação e busca começarão a funcionar no escopo dos produtos implantados. Se nenhum desses produtos for implantado corretamente, o Microsoft 365 Defender não exibirá dados e não poderá tomar nenhuma ação.

Para otimizar suas experiências do Microsoft 365 Defender, recomendamos implantar todos os produtos e serviços de segurança do [Microsoft 365](deploy-supported-services.md)com suporte. 

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Onde o Microsoft 365 Defender processa e armazena meus dados?
O Microsoft 365 Defender seleciona automaticamente um local ideal para o data center onde os dados consolidados são processados e armazenados. Se você tiver o Microsoft Defender para Ponto de Extremidade, ele selecionará o mesmo local usado pelo Defender para Ponto de Extremidade.

>[!NOTE]
>O Microsoft Defender para Ponto de Extremidade provisiona automaticamente em data centers da União Europeia (UE) quando ativado por meio do Azure Defender. O Microsoft 365 Defender provisiona automaticamente no mesmo data center da UE para clientes que provisionam o Microsoft Defender para o Ponto de Extremidade dessa maneira. 

O local do data center é mostrado antes e depois que o serviço é provisionado na página de configurações do Microsoft 365 Defender (**Configurações > Microsoft 365 Defender**). Se você preferir usar outro local do data center, selecione Precisa **de ajuda?** no Centro de segurança do Microsoft 365 para entrar em contato com o suporte da Microsoft.

## <a name="where-can-i-access-microsoft-365-defender"></a>Onde posso acessar o Microsoft 365 Defender?

O Microsoft 365 Defender está disponível no Centro de segurança do Microsoft 365. Para ir para o centro de segurança, navegue até a URL [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Quais permissões preciso para acessar o Microsoft 365 Defender no Centro de segurança do Microsoft 365?

As contas atribuídas às seguintes funções do Azure Active Directory (AD) podem acessar a funcionalidade e os dados do Microsoft 365 Defender:

- Administrador global
- Administrador de segurança
- Operador de segurança
- Leitor global
- Leitor de segurança

>[!NOTE]
>As configurações de controle de acesso baseado em função no Microsoft Defender para Ponto de Extremidade influenciam o acesso aos dados. Para obter mais informações, leia sobre como [gerenciar o acesso ao Microsoft 365 Defender](m365d-permissions.md).

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>Para qual fuso horário o Microsoft 365 Defender é padrão?
Por padrão, o Microsoft 365 Defender exibe informações de hora no fuso horário UTC. Você pode alterar essa configuração para usar o fuso horário local. [Saiba mais sobre como definir o fuso horário](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Como saber mais sobre os novos recursos do Microsoft 365 Defender e as atualizações da interface do usuário?

A Microsoft fornece regularmente informações por meio dos vários canais, incluindo:

- O [centro de mensagens](../../admin/manage/message-center.md) no Centro de administração do Microsoft 365
- Blogposts na comunidade técnica de segurança [do Microsoft 365 & conformidade](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Obter as experiências mais recentes disponíveis publicamente, a partir de recursos [de visualização.](preview.md)

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>O Microsoft 365 Defender está disponível para a GCC (Nuvem da Comunidade Governamental) dos EUA ou GCC High?
No momento, ela não está disponível.

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral do Microsoft 365 Defender](microsoft-365-defender.md)
- [A turn on Microsoft 365 Defender](m365d-enable.md).
- [Requisitos de licenciamento e outros pré-requisitos](prerequisites.md)
- [Implantar serviços com suporte](deploy-supported-services.md)
- [Habilitar recursos de prévia](preview.md)
