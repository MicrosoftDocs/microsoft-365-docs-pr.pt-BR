---
title: Restringir o acesso a tópicos nos tópicos do Microsoft Viva
description: Como excluir tópicos para impedir que eles são descobertos.
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
- m365initiative-topics
localization_priority: None
ms.openlocfilehash: 6b3d2a4b6cbfc67623cea58b73681b7af7cc4889
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107153"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a>Restringir o acesso a tópicos nos tópicos do Microsoft Viva

No Microsoft Viva, os participantes em sua organização podem querer garantir que tópicos específicos não sejam descobertos e expostos aos usuários licenciados. Por exemplo, você pode estar trabalhando em um projeto sobre o que ainda não deseja expor. Embora as permissões do Office 365 em sites, arquivos e outros recursos impeçam que os usuários de Experiências de Tópicos vejam informações confidenciais em tópicos, há proteções adicionais para impedir que tópicos específicos sejam descobertos.

Embora os administradores de conhecimento controlem as configurações da rede de conhecimento para impedir que os tópicos são descobertos, os gerentes de conhecimento e outros participantes precisam saber como isso é feito para que possam trabalhar de forma colaborativa.

> [!Important] 
> Este artigo descreve maneiras de impedir que os tópicos sejam identificados por meio de IA ou exibidos em seu ambiente como uma proteção de segurança adicional. É importante observar que, nos Tópicos do Viva, os usuários não têm permissão para exibir nada em um tópico que eles não têm permissão para acessar por meio das permissões do Office 365. Mesmo que um usuário possa exibir um tópico, seus arquivos, sites e páginas que não têm permissões do Office 365 para exibir não estarão visíveis para eles. Garantir que as permissões para arquivos confidenciais sejam definidas corretamente deve ser sua proteção de segurança principal.

## <a name="prevent-topics-from-being-identified"></a>Impedir que tópicos sejam identificados

O administrador de conhecimento pode restringir o acesso a tópicos específicos, impedindo-os de serem encontrados na indexação inicial. Há duas maneiras de fazer essa tarefa nas configurações de administrador da Rede de Conhecimento no Centro de administração do Microsoft 365.
 
- [Selecione sites do SharePoint a serem excluídos da](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)descoberta de tópicos: você pode usar essa configuração para impedir que sites específicos do SharePoint seja rastreados para tópicos.
- [Excluir tópicos por nome:](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name)os administradores podem usar essa configuração para impedir que tópicos específicos sejam descobertos por nome. Nas configurações de administração da Rede de Conhecimento, um administrador pode carregar uma lista de tópicos a serem excluídos em um arquivo CSV. Você pode excluir tópicos que tenham uma combinação exata ou parcial de um nome de tópico.

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>Impedir que tópicos são exibidos por usuários específicos

Os administradores de conhecimento [também podem selecionar quem pode exibir tópicos em sua organização.](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules) Essa configuração permite selecionar quais usuários licenciados podem exibir todos os tópicos. Por exemplo, em um ambiente piloto, talvez você queira permitir que apenas um pequeno grupo de usuários seja capaz de exibir tópicos.

## <a name="remove-topics-from-being-viewed"></a>Remover tópicos da exibição

Os gerentes de conhecimento [podem optar por remover tópicos](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) para que os usuários não possam mais vê-los. Na página Gerenciar tópicos no Centro de **Tópicos,** os gerentes de conhecimento podem optar por rejeitar tópicos específicos para impedir que eles são exibidos. Os tópicos podem ser removidos independentemente de eles estar em um estado sugerido ou confirmado.

Os tópicos removidos podem ser adicionados posteriormente como tópicos que podem ser visualizados, se necessário. 


## <a name="see-also"></a>Confira também



  






