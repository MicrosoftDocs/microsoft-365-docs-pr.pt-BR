---
title: Restringir o acesso aos tópicos
description: Como excluir tópicos para impedir que eles sejam descobertos.
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: b23d01585d9282132d9e55c74bb22bcdc6ca314a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698784"
---
# <a name="restrict-access-to-topics-in-topic-experiences"></a>Restringir o acesso a tópicos em experiências de tópico

No tópico experiências, os participantes da sua organização podem querer garantir que tópicos específicos não sejam descobertos e expostos aos seus usuários licenciados. Por exemplo, você pode estar trabalhando em um projeto que não deseja expor nenhuma informação sobre o. Embora as permissões do Office 365 em sites, os arquivos e outros recursos impeçam que o tópico que os usuários exibam informações confidenciais nos tópicos, há garantias adicionais que impedem que tópicos específicos sejam descobertos.

Embora os administradores de conhecimento controlem as configurações de rede de conhecimento para evitar que os tópicos sejam descobertos, os gerentes de conhecimento e outros participantes precisam saber como isso é feito para que eles possam trabalhar de forma colaborativa.

> [!Important] 
> Este artigo descreve maneiras de impedir que os tópicos sejam identificados por meio do AI ou exibidos no seu ambiente como uma maior proteção de segurança. É importante observar que, em experiências de tópico, os usuários não têm permissão para exibir nada em um tópico que eles não têm permissão para acessar através de permissões do Office 365. Mesmo que um usuário possa exibir um tópico, seus arquivos, sites e páginas que não têm as permissões do Office 365 para exibir não serão visíveis para eles. Certificar-se de que as permissões para arquivos confidenciais estão definidas corretamente deve ser a proteção de segurança principal.

## <a name="prevent-topics-from-being-identified"></a>Impedir a identificação de tópicos

O administrador de conhecimento pode restringir o acesso a tópicos específicos, impedindo que eles sejam encontrados na indexação inicial. Há duas maneiras de fazer isso nas configurações de administração de rede de conhecimento no centro de administração do Microsoft 365.
 
- [Selecione sites do SharePoint a serem excluídos da descoberta de tópicos](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources): você pode usar essa configuração para impedir que sites específicos do SharePoint sejam rastreados para tópicos.
- [Excluir tópicos por nome](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): os administradores podem usar essa configuração para impedir que tópicos específicos sejam descobertos pelo nome. Nas configurações de administração da rede de conhecimento, um administrador pode carregar uma lista de tópicos a serem excluídos em um arquivo CSV. Você pode excluir os tópicos que têm correspondências exatas ou parciais de um nome de tópico.

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>Impedir que os tópicos sejam exibidos por usuários específicos

Os administradores de conhecimento também podem [selecionar quem pode exibir tópicos em sua organização](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules). Essa configuração permite que você Selecione quais usuários licenciados podem exibir todos os tópicos. Por exemplo, em um ambiente piloto, talvez você queira permitir que apenas um pequeno grupo de usuários possa exibir tópicos.

## <a name="remove-topics-from-being-viewed"></a>Remover tópicos da exibição

Os gerentes de conhecimento podem optar por [Remover tópicos](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) para que os usuários não possam mais vê-los. Na página **gerenciar tópicos** no **Centro** de tópicos, os gerentes de conhecimento podem optar por rejeitar tópicos específicos para impedir que eles sejam exibidos. Os tópicos podem ser removidos independentemente de estarem em um estado sugerido ou confirmado.

Os tópicos removidos posteriormente podem ser adicionados novamente como tópicos exibíveis, se necessário. 


## <a name="see-also"></a>Confira também



  






