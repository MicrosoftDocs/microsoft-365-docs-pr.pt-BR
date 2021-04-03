---
title: Restringir o acesso a tópicos em Tópicos do Microsoft Viva
description: Como excluir tópicos para impedi-los de serem descobertos.
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: d6dfb2f7f432a40c5b6e96a9437f50ba47e23387
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500876"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a>Restringir o acesso a tópicos em Tópicos do Microsoft Viva

No Microsoft Viva, os participantes da sua organização podem querer garantir que tópicos específicos não sejam descobertos e expostos aos usuários licenciados. Por exemplo, você pode estar trabalhando em um projeto que ainda não deseja expor informações. Embora as permissões do Office 365 em sites, arquivos e outros recursos impeçam que os usuários de Experiências de Tópicos visualizam informações confidenciais em tópicos, há proteções adicionais para impedir que tópicos específicos sejam descobertos.

Embora os administradores de conhecimento controlem as configurações para impedir que os tópicos são descobertos, os gerentes de conhecimento e outras partes interessadas precisam saber como isso é feito para que eles possam trabalhar de forma colaborativa.

> [!Important] 
> Este artigo descreve maneiras de impedir que os tópicos sejam identificados por meio da IA ou exibidos em seu ambiente como uma proteção de segurança adicional. É importante observar que, em Tópicos do Viva, os usuários não têm permissão para exibir nada em um tópico que não tenham permissão para acessar por meio de permissões do Office 365. Mesmo que um usuário seja capaz de exibir um tópico, seus arquivos, sites e páginas que eles não têm permissões do Office 365 para exibir não estarão visíveis para eles. Garantir que as permissões para arquivos confidenciais sejam definidas corretamente devem ser sua proteção de segurança principal.

## <a name="prevent-topics-from-being-identified"></a>Impedir que os tópicos sejam identificados

O administrador de conhecimento pode restringir o acesso a tópicos específicos impedindo-os de serem encontrados na indexação inicial. Há duas maneiras de fazer essa tarefa nas configurações de administrador do Viva Topics no centro de administração do Microsoft 365.
 
- [Selecione sites do SharePoint a serem excluídos da](./topic-experiences-discovery.md#select-sharepoint-topic-sources)descoberta de tópicos : você pode usar essa configuração para impedir que sites específicos do SharePoint seja rastreado para tópicos.
- [Excluir tópicos pelo nome:](./topic-experiences-discovery.md#exclude-topics-by-name)os administradores podem usar essa configuração para impedir que tópicos específicos sejam descobertos pelo nome. Nas configurações de administrador do Viva Topics, um administrador pode carregar uma lista de tópicos a serem excluídos em um arquivo CSV. Você pode excluir tópicos que tenham combinações exatas ou parciais de um nome de tópico.

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>Impedir que os tópicos são exibidos por usuários específicos

Os administradores de conhecimento também podem [selecionar quem pode exibir tópicos em sua organização.](./topic-experiences-knowledge-rules.md) Essa configuração permite selecionar quais usuários licenciados podem exibir todos os tópicos. Por exemplo, em um ambiente piloto, talvez você queira permitir que um pequeno grupo de usuários possa exibir tópicos.

## <a name="remove-topics-from-being-viewed"></a>Remover tópicos de serem exibidos

Os gerentes de conhecimento podem [optar por remover tópicos](./manage-topics.md) para que os usuários não possam mais vê-los. Na página **Gerenciar tópicos** na Central de Tópicos, os gerentes de conhecimento podem optar por rejeitar tópicos específicos para impedir que eles são exibidos. Os tópicos podem ser removidos independentemente se eles estão em um estado sugerido ou confirmado.

Os tópicos removidos podem ser adicionados posteriormente como tópicos exibiveis, se necessário. 


## <a name="see-also"></a>Confira também



