---
title: Gerenciar links seguros
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como gerenciar links seguros para proteger sua empresa contra sites mal-intencionados.
ms.openlocfilehash: eabb2c1f71b1183867ffcb005ba4f7e44ed6e4b7
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701463"
---
# <a name="manage-safe-links"></a>Gerenciar links seguros

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

O Microsoft defender para Office 365, anteriormente chamado de Microsoft 365 ATP, ou proteção avançada contra ameaças, ajuda a proteger sua empresa contra sites mal-intencionados quando as pessoas clicam em links nos aplicativos do Office.

## <a name="try-it"></a>Experimente!

1. Vá para o [centro de administração](https://admin.microsoft.com)e selecione **configuração**.
1. Role para baixo para **aumentar a proteção contra ameaças avançadas**. Selecione **Exibir**, **gerenciar** e, em seguida, **links seguros de ATP**.
1. Em **políticas que se aplicam a toda a organização**, escolha a política **padrão** e, em seguida, selecione o ícone **Editar** .
1. Insira uma URL que você deseja bloquear.
1. Selecione **usar links seguros em aplicativos do Office, Office para IOS e Android**; Selecione não **rastrear quando os usuários clicarem em links seguros**; e selecione não **permitir que os usuários cliquem por meio de links seguros para a URL original**. Eles já podem estar selecionados se você configurar a política padrão. Selecione **Salvar**.
1. Em **políticas que se aplicam a destinatários específicos**, escolha **regra de links seguros recomendados** e, em seguida, selecione o ícone **Editar** .
1. Selecione **configurações**, role para baixo, digite a URL que você não deseja verificar e, em seguida, selecione o ícone **Adicionar** .
1. Selecione **aplicado a** e selecione seu nome de domínio. Selecione os domínios adicionais aos quais você deseja aplicar a regra. Selecione **Adicionar**, **OK** e **salvar**.

Os links seguros de ATP agora estão configurados. Aguarde até 30 minutos para que as alterações entrem em vigor.

Quando um usuário recebe um email com links, os links serão examinados. Se os links forem considerados seguros, eles serão clicados. No entanto, se o link estiver na lista de bloqueados, os usuários verão uma mensagem de que ela foi bloqueada.