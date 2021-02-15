---
title: Perguntas frequentes ao ligar o Microsoft 365 Defender
description: Obter respostas para as perguntas mais frequentes sobre licenciamento, permissões, configurações iniciais e outros produtos e serviços relacionados à habilitação do Microsoft 365 Defender
keywords: perguntas frequentes, perguntas frequentes, GCC, começar, habilitar MTP, Proteção contra Ameaças da Microsoft, M365, segurança, local dos dados, permissões necessárias, qualificação de licença, página de configurações
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
ms.openlocfilehash: 2cb9aed070959644e3660188835386118d5f4d9b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930181"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Perguntas frequentes ao ligar o Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Leia as respostas às perguntas mais frequentes sobre como ligar o [Microsoft 365 Defender,](microsoft-threat-protection.md)incluindo licenças e permissões necessárias, implantação de serviços de suporte e configurações iniciais.

Para obter instruções sobre como ativar o serviço, [leia Ativar o Microsoft 365 Defender.](mtp-enable.md)

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Não tenho uma licença do Microsoft 365 E5. Ainda posso usar o Microsoft 365 Defender?

Os clientes com as seguintes licenças que não são E5 podem usar o Microsoft 365 Defender:

- Microsoft Defender para Ponto de Extremidade
- O que é o Microsoft Defender para Identidade?
- Microsoft Cloud App Security
- Defender para Office 365 (Plano 2)
 
Para uma lista completa de licenças com suporte, [leia os requisitos de licenciamento.](prerequisites.md#licensing-requirements)

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Preciso instalar ou implantar algo para começar a usar o Microsoft 365 Defender?

Não, o Microsoft 365 Defender consolida os dados dos serviços de segurança do Microsoft 365 que você já implantou. Depois que você a ativar, as experiências de incidente, automação e busca começarão a funcionar dentro do escopo dos produtos implantados. Se nenhum desses produtos for implantado corretamente, o Microsoft 365 Defender não exibirá nenhum dado e não poderá tomar nenhuma ação.

Para otimizar suas experiências do Microsoft 365 Defender, recomendamos implantar todos os produtos e serviços de segurança do [Microsoft 365](deploy-supported-services.md)com suporte. 

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Onde o Microsoft 365 Defender processa e armazena meus dados?
O Microsoft 365 Defender seleciona automaticamente um local ideal para o data center onde os dados consolidados são processados e armazenados. Se você tiver o Microsoft Defender para Ponto de Extremidade, ele selecionará o mesmo local usado pelo Defender para o Ponto de Extremidade.

>[!NOTE]
>O Microsoft Defender para Ponto de Extremidade provisiona automaticamente em data centers da União Europeia (UE) quando ativado por meio do Azure Defender. O Microsoft 365 Defender provisiona automaticamente no mesmo data center da UE para clientes que provisionam o Microsoft Defender para o Ponto de Extremidade dessa maneira. 

O local do data center é mostrado antes e depois que o serviço é provisionado na página de configurações do Microsoft 365 Defender ( Configurações >**Microsoft 365 Defender).** Se você preferir usar outro local de data center, selecione Precisa de **ajuda?** No centro de segurança do Microsoft 365 para entrar em contato com o suporte da Microsoft.

## <a name="where-can-i-access-microsoft-365-defender"></a>Onde posso acessar o Microsoft 365 Defender?

O Microsoft 365 Defender está disponível na central de segurança do Microsoft 365. Para ir para o centro de segurança, navegue até a [https://security.microsoft.com](https://security.microsoft.com) URL.

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Quais permissões preciso para acessar o Microsoft 365 Defender na central de segurança do Microsoft 365?

As contas atribuídas às seguintes funções do Azure Active Directory (AD) podem acessar a funcionalidade e os dados do Microsoft 365 Defender:

- Administrador global
- Administrador de segurança
- Operador de segurança
- Leitor global
- Leitor de segurança

>[!NOTE]
>As configurações de controle de acesso baseado em função no Microsoft Defender para Ponto de Extremidade influenciam o acesso aos dados. Para obter mais informações, leia sobre [como gerenciar o acesso ao Microsoft 365 Defender.](mtp-permissions.md)

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>Para qual fuso horário o Microsoft 365 Defender é padrão?
Por padrão, o Microsoft 365 Defender exibe informações de hora no fuso horário UTC. Você pode alterar essa configuração para usar seu fuso horário local. [Saiba mais sobre como definir o fuso horário](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Como posso saber mais sobre as novas atualizações de interface do usuário e recursos do Microsoft 365 Defender?

A Microsoft fornece informações regularmente por meio de vários canais, incluindo:

- O [centro de mensagens](../../admin/manage/message-center.md) no Centro de administração do Microsoft 365
- Postagens de blog na comunidade técnica de conformidade e segurança & Microsoft [365](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Obter as experiências publicamente mais recentes disponíveis ao ligar os recursos [de visualização.](preview.md)

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>O Microsoft 365 Defender está disponível para o US Government Community Cloud (GCC) ou GCC High?
No momento, ela não está disponível.

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral do Microsoft 365 Defender](microsoft-threat-protection.md)
- [Ativar o Microsoft 365 Defender.](mtp-enable.md)
- [Requisitos de licenciamento e outros pré-requisitos](prerequisites.md)
- [Implantar serviços com suporte](deploy-supported-services.md)
- [Habilitar recursos de prévia](preview.md)
