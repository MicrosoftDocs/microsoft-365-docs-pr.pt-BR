---
title: Gerenciar Links Seguros
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como gerenciar links seguros para proteger sua empresa contra sites mal-intencionados.
ms.openlocfilehash: 1f5b3f61871e8d231029156631031dbb0ef4f2f5
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928013"
---
# <a name="manage-safe-links"></a>Gerenciar Links Seguros

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

O Microsoft Defender para Office 365 , anteriormente chamado de Microsoft 365 ATP ou Proteção Avançada contra Ameaças, ajuda a proteger seus negócios contra sites mal-intencionados quando as pessoas clicam em links em aplicativos do Office.

## <a name="try-it"></a>Experimente!

1. Vá para o [centro de administração](https://admin.microsoft.com)e selecione **Configuração.**
1. Role para baixo **até aumentar a proteção contra ameaças avançadas.** Selecione **Exibir,** **Gerenciar** e Links **Seguros da ATP.**
1. Em **Políticas que se aplicam a toda a organização,** escolha a **política** Padrão e selecione o **ícone Editar.**
1. Insira uma URL que você deseja bloquear.
1. Selecione **Usar links seguros em aplicativos do Office, Office para iOS e Android;** selecione **Não rastrear quando os usuários clicam em links seguros;** e selecione **Não permitir que os usuários cliquem em links seguros para a URL original.** Eles já podem estar selecionados se você configurar a política padrão. Selecione **Salvar**.
1. Em **Políticas que se aplicam a destinatários específicos,** escolha Regra de **links** seguros recomendada e selecione o **ícone Editar.**
1. Selecione **configurações,** role para baixo, insira a URL que você não deseja verificar e selecione o **ícone** Adicionar.
1. Selecione **aplicado e, em** seguida, selecione seu nome de domínio. Selecione os domínios adicionais aos que você deseja que a regra seja aplicada. Selecione **adicionar**, **OK** e, em **seguida, Salvar**.

Os Links Seguros da ATP agora estão configurados. Permita até 30 minutos para que suas alterações entre em vigor.

Quando um usuário receber um email com links, os links serão verificados. Se os links são considerados seguros, eles serão clicáveis. No entanto, se o link estiver na lista de bloqueios, os usuários verão uma mensagem de que ele foi bloqueado.