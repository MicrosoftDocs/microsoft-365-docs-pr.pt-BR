---
title: Frequentemente faz perguntas ao ligar Microsoft 365 Defender
description: Obtenha respostas para as perguntas mais comumente feitas sobre licenciamento, permissões, configurações iniciais e outros produtos e serviços relacionados à habilitação de Microsoft 365 Defender
keywords: perguntas frequentes, perguntas faq, GCC, começar, habilitar Microsoft 365 Defender, Microsoft 365 Defender, M365, segurança, localização de dados, permissões necessárias, elegibilidade da licença, página de configurações
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
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Frequentemente faz perguntas ao ligar Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Leia respostas às perguntas mais comumente feitas sobre ligar [Microsoft 365 Defender](microsoft-365-defender.md), incluindo licenças e permissões necessárias, implantação de serviços de suporte e configurações iniciais.

Para obter instruções sobre como ativar o serviço, [leia Ativar Microsoft 365 Defender](m365d-enable.md).

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Não tenho licença Microsoft 365 E5. Ainda posso usar Microsoft 365 Defender?

Os clientes com as seguintes licenças não-E5 podem usar Microsoft 365 Defender:

- Microsoft Defender para Ponto de Extremidade
- Microsoft Defender para Identidade?
- Microsoft Cloud App Security
- Microsoft Defender para Office 365 (Plano 2)
 
Para obter uma lista completa de licenças suportadas, [leia os requisitos de licenciamento.](prerequisites.md#licensing-requirements)

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Preciso instalar ou implantar alguma coisa para começar a usar Microsoft 365 Defender?

Não, Microsoft 365 Defender consolida dados de Microsoft 365 serviços de segurança que você já implantou. Uma vez que você ligá-lo, experiências de incidente, automação e caça começarão a trabalhar dentro do escopo dos produtos implantados. Se nenhum desses produtos for devidamente implantado, Microsoft 365 Defender não exibirá nenhum dado e não poderá tomar nenhuma ação.

Para otimizar suas experiências Microsoft 365 Defender, recomendamos a implantação de *todos os* produtos e serviços de segurança [Microsoft 365 suportados.](deploy-supported-services.md)

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Onde Microsoft 365 o processo do Defender e armazena meus dados?
Microsoft 365 O Defender seleciona automaticamente um local ideal para o data center onde os dados consolidados são processados e armazenados. Se você tiver o Microsoft Defender para endpoint, ele selecionará o mesmo local usado pelo Defender para Endpoint.

>[!NOTE]
>O Microsoft Defender for Endpoint fornece automaticamente nos data centers da União Europeia (UE) quando ligado através do Azure Defender. Microsoft 365 O Defender será automaticamente provisionado no mesmo data center da UE para clientes que provisionaram o Microsoft Defender para endpoint desta maneira. 

O local do data center é mostrado antes e depois do serviço ser provisionado na página de configurações do Microsoft 365 Defender (**Configurações > Microsoft 365 Defender).** Se você preferir usar outro local de data center, selecione **Precisar de ajuda?** no Microsoft 365 centro de segurança para entrar em contato com o suporte da Microsoft.

## <a name="where-can-i-access-microsoft-365-defender"></a>Onde posso acessar Microsoft 365 Defender?

Microsoft 365 O Defender está disponível no centro de segurança Microsoft 365. Para ir ao centro de segurança, navegue até a URL [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Que permissões preciso para acessar Microsoft 365 Defender no centro de segurança Microsoft 365?

As contas atribuídas às seguintes funções de Azure Active Directory (Azure AD) podem acessar Microsoft 365 funcionalidade e dados do Defender:

- Administrador global
- Administrador de segurança
- Operador de segurança
- Leitor global
- Leitor de segurança

>[!NOTE]
>As configurações de controle de acesso baseadas em função no Microsoft Defender for Endpoint influenciam o acesso aos dados. Para mais informações, leia sobre [como gerenciar o acesso ao Microsoft 365 Defender](m365d-permissions.md).

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>Para que fuso horário Microsoft 365 o Defender é padrão?
Por padrão, Microsoft 365 Defender exibe informações de tempo no fuso horário UTC. Você pode alterar esta configuração para usar o fuso horário local. [Saiba como definir o fuso horário](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Como posso aprender sobre o novo recurso Microsoft 365 Defender e atualizações de interface do usuário?

A Microsoft fornece regularmente informações através dos vários canais, incluindo:

- O [centro de mensagens](../../admin/manage/message-center.md) em Microsoft 365 centro administrativo
- Blogs na [comunidade de tecnologia de segurança Microsoft 365 & conformidade](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Obtenha as últimas experiências disponíveis ao público, ligando [os recursos de pré-visualização](preview.md).

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>O Microsoft 365 Defender está disponível para Nuvem da Comunidade Governamental dos EUA (GCC) ou GCC High?
No momento, ela não está disponível.

## <a name="related-topics"></a>Tópicos relacionados

- [Microsoft 365 Visão geral do defensor](microsoft-365-defender.md)
- [Ligue Microsoft 365 Defender](m365d-enable.md).
- [Requisitos de licenciamento e outros pré-requisitos](prerequisites.md)
- [Implantar serviços com suporte](deploy-supported-services.md)
- [Habilitar recursos de prévia](preview.md)
