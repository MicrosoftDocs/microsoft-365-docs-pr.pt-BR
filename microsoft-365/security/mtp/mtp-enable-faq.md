---
title: Perguntas frequentes ao ativar o Microsoft 365 defender
description: Obtenha respostas para as perguntas mais frequentes sobre licenciamento, permissões, configurações iniciais e outros produtos e serviços relacionados à habilitação do Microsoft 365 defender
keywords: perguntas frequentes, perguntas frequentes, GCC, introdução, habilitar MTP, proteção contra ameaças da Microsoft, M365, segurança, local dos dados, permissões necessárias, qualificação para licenças, página Configurações
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
ms.openlocfilehash: bfb58cb043f2bc641245814c41e389ddcdbfdefa
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842411"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Perguntas frequentes ao ativar o Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 defender

Leia as respostas para as perguntas mais frequentes sobre a ativação do [Microsoft 365 defender](microsoft-threat-protection.md), incluindo as licenças e permissões necessárias, a implantação de serviços de suporte e as configurações iniciais.

Para obter instruções sobre como ativar o serviço, [Leia ativar o Microsoft 365 defender](mtp-enable.md).

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Não tenho uma licença do Microsoft 365 e5. Ainda posso usar o Microsoft 365 defender?

Os clientes com as seguintes licenças não E5 podem usar o Microsoft 365 defender:

- Microsoft Defender para Ponto de Extremidade
- Microsoft Defender para Identidade
- Segurança no aplicativo na nuvem da Microsoft
- Defender para Office 365 (plano 2)
 
Para obter uma lista completa de licenças compatíveis, [Leia os requisitos de licenciamento](prerequisites.md#licensing-requirements).

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Preciso instalar ou implantar nada para começar a usar o Microsoft 365 defender?

Não, o Microsoft 365 defender consolida dados dos serviços de segurança da Microsoft 365 que você já implantou. Depois que você ativá-la, as experiências de incidentes, de automação e de caça começarão a funcionar dentro do escopo dos produtos implantados. Se nenhum desses produtos estiver implantado corretamente, o Microsoft 365 defender não exibirá nenhum dado e não poderá realizar qualquer ação.

Para otimizar as experiências do Microsoft 365 defender, recomendamos implantar *todos os* [produtos e serviços de segurança da Microsoft 365](deploy-supported-services.md)suportados.

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Onde o Microsoft 365 defender processa e armazena meus dados?
O Microsoft 365 defender seleciona automaticamente um local ideal para o Data Center em que os dados consolidados são processados e armazenados. Se você tiver o Microsoft defender para ponto de extremidade, ele selecionará o mesmo local usado pelo defender para Endpoint.

>[!NOTE]
>O Microsoft defender for Endpoint provisiona automaticamente nos data centers da União Europeia (UE) quando ativado pelo Azure defender *. O Microsoft 365 defender será automaticamente provisionado no mesmo Data Center da UE para clientes que tenham provisionado o Microsoft defender para ponto de extremidade dessa maneira. 

O local do Data Center é mostrado antes e depois que o serviço é provisionado na página de configurações do Microsoft 365 defender ( **configurações > Microsoft 365 defender** ). Se você preferir usar outro local de data center, selecione **precisa de ajuda?** no centro de segurança do Microsoft 365 para entrar em contato com o suporte da Microsoft.

## <a name="where-can-i-access-microsoft-365-defender"></a>Onde posso acessar o Microsoft 365 defender?

O Microsoft 365 defender está disponível na central de segurança do Microsoft 365. Para ir para a central de segurança, navegue até a URL [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Quais permissões são necessárias para acessar o Microsoft 365 defender na central de segurança da Microsoft 365?

As contas atribuídas às seguintes funções do Azure Active Directory (AD) podem acessar a funcionalidade e os dados do Microsoft 365 defender:

- Administrador global
- Administrador de segurança
- Operador de segurança
- Leitor global
- Leitor de segurança

>[!NOTE]
>As configurações de controle de acesso baseado em função no Microsoft defender para ponto de extremidade influenciam o acesso aos dados. Para obter mais informações, leia sobre como [gerenciar o acesso ao Microsoft 365 defender](mtp-permissions.md).

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>A que fuso horário o Microsoft 365 defender tem como padrão?
Por padrão, o Microsoft 365 defender exibe informações de hora no fuso horário UTC. Você pode alterar essa configuração para usar seu fuso horário local. [Saiba como configurar o fuso horário](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Como posso saber mais sobre as novas atualizações do recurso Microsoft 365 defender e da interface do usuário?

A Microsoft regularmente fornece informações através de vários canais, incluindo:

- O [centro de mensagens](../../admin/manage/message-center.md) no centro de administração do Microsoft 365
- Blogposts na [comunidade técnica de conformidade do Microsoft 365 security &](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Obtenha as experiências disponíveis publicamente mais recentes, ativando os [recursos de visualização](preview.md).

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>O Microsoft 365 defender está disponível para a nuvem da Comunidade dos EUA (GCC) ou GCC High?
No momento, ela não está disponível.

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral do Microsoft 365 defender](microsoft-threat-protection.md)
- [Ative o Microsoft 365 defender](mtp-enable.md).
- [Requisitos de licenciamento e outros pré-requisitos](prerequisites.md)
- [Implantar serviços com suporte](deploy-supported-services.md)
- [Habilitar recursos de prévia](preview.md)
