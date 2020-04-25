---
title: Links seguros de ATP para Teams, safelinks, links seguros, bloquear links mal-intencionados, Office 365 ATP, links seguros de equipes, impedir que os usuários cliquem em links defeituosos, links mal-intencionados
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 02/28/2020
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Agora o Microsoft Teams terá acesso a links seguros no momento do clique. Se você estiver usando chats 1-em-1, entre grupos ou em canais e guias, se você tiver uma assinatura do Office 365 ATP, terá a capacidade de habilitar e usar esse recurso de segurança.
ms.openlocfilehash: 07f20f0adf503e4592d2bd3f3bc9857d08a1e433
ms.sourcegitcommit: 481fb95d8b80cf2102a9c73b21e7effa79e594e7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/24/2020
ms.locfileid: "43808997"
---
<!--06/21/2019-->

# <a name="safe-links-in-teams"></a>Links seguros no Teams

> [!IMPORTANT]
> Este recurso está em **Visualização pública** para clientes no programa de adoção de tecnologia do Microsoft Teams (toque) a partir de 28 de fevereiro de 2020. Esta nota será removida do artigo quando links seguros para o Microsoft Teams estiver mais amplamente disponível.

O Microsoft Teams, um aplicativo baseado em nuvem da Microsoft para gerenciar seu trabalho, já usa anexos seguros (para o Office 365), mas agora terá acesso a links seguros no momento do clique. Se você estiver usando chats, bate-papos de grupo, canais ou guias, se você tiver uma assinatura do Office 365 ATP, você terá a capacidade de habilitar e usar essa medida de segurança. Para saber mais sobre os requisitos de licenciamento, confira [Diretrizes do Licenciamento de Serviços no Nível de Locatário do Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).

Veja como funciona: 

1. Quando você iniciar o aplicativo Teams, a Microsoft 365 verificará se o usuário pertence a uma organização que tem o Office 365 ATP e que o usuário faz parte de uma política de links seguros ativa com sua proteção habilitada para o Microsoft Teams.

2. Se os itens acima forem verdadeiros, as URLs serão validadas no momento do clique em chats, chats de grupo, canais e em guias para esse usuário.
 
## <a name="what-will-users-experience"></a>O que os usuários irão experimentar? 

Todos os usuários protegidos terão essa experiência com URLs perigosas: 

- Se o link tiver sido clicado de uma conversa de equipes, de um chat de grupo ou de canais, uma página será renderizada no navegador padrão. Se o link tiver sido clicado em uma guia fixada, a página aparecerá na GUI do Microsoft Teams dentro dessa guia e a opção de abrir no navegador será desabilitada para fins de segurança.

- Este usuário será impedido de prosseguir para o site da URL.

Se o usuário que enviou o link não estiver protegido pelo Office 365 ATP, ele ou ela estará livre para clicar na URL em seu computador e resolver o problema. Isso torna mais importante para os administradores saber quem estão seus usuários protegidos e se devem estar.

![Uma página de links seguros para o Teams relatando um link mal-intencionado e bloqueando o trânsito para a página.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

Clicar no *botão voltar* nesta página no Microsoft Teams irá fechá-lo (ou pode resultar em uma página em branco que os usuários possam fechar). No entanto, clicar no link novamente resultará na reavaliação da reputação do site para que essa página reapareça.

> [!NOTE]
> Alguns administradores do Microsoft 365 habilitarão a mensagem de **continuar assim mesmo** na página de bloqueio. No entanto, se o recurso links seguros medir a reputação de um site e encontrá-lo, nenhum outro clique deve ser realizada. Não é recomendável que os usuários ignorem medidas de segurança. Considere isso em suas considerações antes de habilitar a continuação de qualquer modo. 
