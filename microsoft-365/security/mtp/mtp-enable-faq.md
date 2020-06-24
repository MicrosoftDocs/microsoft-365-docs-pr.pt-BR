---
title: Perguntas frequentes ao ativar a proteção contra ameaças da Microsoft
description: Obtenha respostas para as perguntas mais frequentes sobre licenciamento, permissões, configurações iniciais e outros produtos e serviços relacionados à habilitação da proteção contra ameaças da Microsoft
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
ms.openlocfilehash: 9dcfeb5616afc8953e862d6d1a542d694582b157
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2020
ms.locfileid: "44845055"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-threat-protection"></a>Perguntas frequentes ao ativar a proteção contra ameaças da Microsoft

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

Leia as respostas para as perguntas mais frequentes sobre como ativar a [proteção contra ameaças da Microsoft](microsoft-threat-protection.md), incluindo licenças e permissões necessárias, implantação de serviços de suporte e configurações iniciais.

Para obter instruções sobre como ativar o serviço, [Leia ativar a proteção contra ameaças da Microsoft](mtp-enable.md).

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-threat-protection"></a>Não tenho uma licença do Microsoft 365 e5. Ainda posso usar a proteção contra ameaças da Microsoft?

Os clientes com as seguintes licenças não E5 podem usar a proteção contra ameaças da Microsoft:

- Proteção avançada contra ameaças do Microsoft Defender
- Proteção Avançada contra Ameaças do Azure
- Segurança no aplicativo na nuvem da Microsoft
- Proteção contra Ameaças do Office 365 Advanced (Plano 2)
 
Para obter uma lista completa de licenças compatíveis, [Leia os requisitos de licenciamento](prerequisites.md#licensing-requirements).

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-threat-protection"></a>Preciso instalar ou implantar nada para começar a usar a proteção contra ameaças da Microsoft?

Não, a proteção contra ameaças da Microsoft consolida os dados dos serviços de segurança da Microsoft 365 que você já implantou. Depois que você ativá-la, as experiências de incidentes, de automação e de caça começarão a funcionar dentro do escopo dos produtos implantados. Se nenhum desses produtos estiver implantado corretamente, a proteção contra ameaças da Microsoft não exibirá nenhum dado e não poderá realizar qualquer ação.

Para otimizar suas experiências de proteção contra ameaças da Microsoft, recomendamos implantar *todos os* [produtos e serviços de segurança compatíveis com o Microsoft 365](deploy-supported-services.md).

## <a name="where-does-microsoft-threat-protection-process-and-store-my-data"></a>Onde funciona o processo de proteção contra ameaças da Microsoft e armazenar meus dados?
A proteção contra ameaças da Microsoft seleciona automaticamente um local ideal para o Data Center em que os dados consolidados são processados e armazenados. Se você tiver o Microsoft defender ATP, ele selecionará o mesmo local usado pelo Microsoft defender ATP.

>[!NOTE]
>O Microsoft defender ATP provisiona automaticamente nos data centers da União Européia (UE) quando ativado pela central de segurança do Azure. A proteção contra ameaças da Microsoft será provisionada automaticamente no mesmo Data Center da UE para clientes que tenham provisionado o Microsoft defender ATP dessa maneira. 

O local do Data Center é mostrado antes e depois que o serviço é provisionado na página de configurações para proteção contra ameaças da Microsoft (**configurações > proteção contra ameaças da Microsoft**). Se você preferir usar outro local de data center, selecione **precisa de ajuda?** no centro de segurança do Microsoft 365 para entrar em contato com o suporte da Microsoft.

## <a name="where-can-i-access-microsoft-threat-protection"></a>Onde posso acessar a proteção contra ameaças da Microsoft?

A proteção contra ameaças da Microsoft está disponível no centro de segurança do Microsoft 365. Para ir para a central de segurança, navegue até a URL [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-threat-protection-in-microsoft-365-security-center"></a>Que permissões preciso para acessar a proteção contra ameaças da Microsoft no centro de segurança do Microsoft 365?

Contas atribuídas às seguintes funções do Azure Active Directory (AD) podem acessar a funcionalidade e os dados da Proteção contra Ameaças da Microsoft:

- Administrador global
- Administrador de segurança
- Operador de segurança
- Leitor global
- Leitor de segurança

>[!NOTE]
>As configurações de controle de acesso baseado em função no Microsoft defender ATP influenciam o acesso aos dados. Para obter mais informações, leia sobre [o gerenciamento de acesso à proteção contra ameaças da Microsoft](mtp-permissions.md).

## <a name="what-time-zone-does-microsoft-threat-protection-default-to"></a>A que fuso horário a proteção de ameaças da Microsoft é padrão?
Por padrão, a proteção contra ameaças da Microsoft exibe informações de hora no fuso horário UTC. Você pode alterar essa configuração para usar seu fuso horário local. [Saiba como configurar o fuso horário](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-threat-protection-feature-and-ui-updates"></a>Como posso saber mais sobre o novo recurso de proteção contra ameaças da Microsoft e as atualizações da interface do usuário?

A Microsoft regularmente fornece informações através de vários canais, incluindo:

- O [centro de mensagens](../../admin/manage/message-center.md) no centro de administração do Microsoft 365
- Blogposts na [comunidade técnica de conformidade do Microsoft 365 security &](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Obtenha as experiências disponíveis publicamente mais recentes, ativando os [recursos de visualização](preview.md).

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>A Proteção contra Ameaças da Microsoft está disponível para a nuvem governamental de comunidade dos EUA (GCC) ou para a GCC High (de alta confidencialidade)?
No momento, ela não está disponível.

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral da Proteção contra Ameaças da Microsoft](microsoft-threat-protection.md)
- [Ative a proteção contra ameaças da Microsoft](mtp-enable.md).
- [Requisitos de licenciamento e outros pré-requisitos](prerequisites.md)
- [Implantar serviços com suporte](deploy-supported-services.md)
- [Ativar recursos de visualização](preview.md)