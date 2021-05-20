---
title: Perguntas frequentes ao Microsoft 365 Defender
description: Obter respostas para as perguntas mais frequentes sobre licenciamento, permissões, configurações iniciais e outros produtos e serviços relacionados à habilitação do Microsoft 365 Defender
keywords: perguntas frequentes, perguntas frequentes, GCC, começar, habilitar Microsoft 365 Defender, Microsoft 365 Defender, M365, segurança, localização de dados, permissões necessárias, qualificação de licença, página de configurações
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
ms.openlocfilehash: 008e3cc6ee65597a032aa932b74a64ac591927f2
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572760"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Perguntas frequentes ao Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Leia respostas às perguntas mais frequentes sobre como acionar o [Microsoft 365 Defender](microsoft-365-defender.md), incluindo licenças e permissões necessárias, implantação de serviços de suporte e configurações iniciais.

Para obter instruções sobre como ativar o serviço, [leia Ativar Microsoft 365 Defender](m365d-enable.md).

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Não tenho uma licença de Microsoft 365 E5. Ainda posso usar o Microsoft 365 Defender?

Os clientes com as seguintes licenças que não são do E5 podem usar Microsoft 365 Defender:

- Microsoft Defender para Ponto de Extremidade
- Microsoft Defender para Identidade?
- Microsoft Cloud App Security
- Microsoft Defender para Office 365 (Plano 2)
 
Para uma lista completa de licenças com suporte, [leia os requisitos de licenciamento.](prerequisites.md#licensing-requirements)

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Preciso instalar ou implantar algo para começar a usar o Microsoft 365 Defender?

Não, Microsoft 365 Defender consolida dados Microsoft 365 serviços de segurança que você já implantou. Depois que você a ativar, as experiências de incidente, automação e busca começarão a funcionar no escopo dos produtos implantados. Se nenhum desses produtos for implantado corretamente, o Microsoft 365 Defender não exibirá dados e não poderá tomar nenhuma ação.

Para otimizar suas experiências do Microsoft 365 Defender, recomendamos a implantação de todos os produtos e serviços Microsoft 365 segurança com [suporte.](deploy-supported-services.md) 

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Onde o Microsoft 365 Defender processa e armazena meus dados?
Microsoft 365 O Defender seleciona automaticamente um local ideal para o data center onde os dados consolidados são processados e armazenados. Se você tiver o Microsoft Defender para Ponto de Extremidade, ele selecionará o mesmo local usado pelo Defender para Ponto de Extremidade.

>[!NOTE]
>O Microsoft Defender para Ponto de Extremidade provisiona automaticamente em data centers da União Europeia (UE) quando ativado por meio do Azure Defender. Microsoft 365 O Defender provisiona automaticamente no mesmo data center da UE para clientes que provisionam o Microsoft Defender para o Ponto de Extremidade dessa maneira. 

O local do data center é mostrado antes e depois que o serviço é provisionado na página de configurações do Microsoft 365 Defender (**Configurações > Microsoft 365 Defender**). Se você preferir usar outro local do data center, selecione Precisa de **ajuda?** no centro de segurança Microsoft 365 para entrar em contato com o suporte da Microsoft.

## <a name="where-can-i-access-microsoft-365-defender"></a>Onde posso acessar o Microsoft 365 Defender?

Microsoft 365 O Defender está disponível Microsoft 365 central de segurança. Para ir para o centro de segurança, navegue até a URL [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Quais permissões preciso para acessar o Microsoft 365 Defender no Microsoft 365 de segurança?

As contas atribuídas às seguintes Azure Active Directory (Azure AD) podem acessar Microsoft 365 funcionalidade e dados do Defender:

- Administrador global
- Administrador de segurança
- Operador de segurança
- Leitor global
- Leitor de segurança

>[!NOTE]
>As configurações de controle de acesso baseado em função no Microsoft Defender para Ponto de Extremidade influenciam o acesso aos dados. Para obter mais informações, leia sobre como [gerenciar o acesso ao Microsoft 365 Defender](m365d-permissions.md).

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>Para qual fuso horário Microsoft 365 Defender padrão?
Por padrão, Microsoft 365 Defender exibe informações de hora no fuso horário UTC. Você pode alterar essa configuração para usar o fuso horário local. [Saiba mais sobre como definir o fuso horário](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Como posso saber mais sobre as novas Microsoft 365 do Defender e atualizações da interface do usuário?

A Microsoft fornece regularmente informações por meio dos vários canais, incluindo:

- O [centro de mensagens](../../admin/manage/message-center.md) no Microsoft 365 de administração
- Blogposts na Microsoft 365 [de segurança & de conformidade](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Obter as experiências mais recentes disponíveis publicamente, a partir de recursos [de visualização.](preview.md)

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>O Microsoft 365 Defender está disponível para usuários Nuvem da Comunidade Governamental (GCC) ou GCC High?
No momento, ela não está disponível.

## <a name="related-topics"></a>Tópicos relacionados

- [Microsoft 365 Visão geral do Defender](microsoft-365-defender.md)
- [A Microsoft 365 Defender](m365d-enable.md).
- [Requisitos de licenciamento e outros pré-requisitos](prerequisites.md)
- [Implantar serviços com suporte](deploy-supported-services.md)
- [Habilitar recursos de prévia](preview.md)
