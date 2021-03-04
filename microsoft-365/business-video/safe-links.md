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
description: Saiba como gerenciar Links Seguros para proteger sua empresa contra sites mal-intencionados.
ms.openlocfilehash: 0f0cc6845f699ba5b05c30e21f876f4b4d47b6a6
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422238"
---
# <a name="manage-safe-links"></a>Gerenciar links seguros

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

O Microsoft Defender para Office 365 , anteriormente chamado de Microsoft 365 ATP ou Proteção Avançada contra Ameaças, ajuda a proteger sua empresa contra sites mal-intencionados quando as pessoas clicam em links em aplicativos do Office.

## <a name="try-it"></a>Experimente!

1. Vá para o [centro de administração](https://admin.microsoft.com)e selecione **Configurar**.
1. Role para baixo **até Aumentar a proteção contra ameaças avançadas**. Selecione **Exibir,** **Gerenciar** e, em seguida, **ATP Links Seguros.**
1. Em **Políticas que se aplicam a toda a organização,** escolha a política **Padrão** e selecione o **ícone** Editar.
1. Insira uma URL que você deseja bloquear.
1. Selecione **Usar links seguros em aplicativos do Office, Office para iOS e Android;** selecione **Não rastrear quando os usuários clicarem em links seguros;** e selecione **Não permitir que os usuários cliquem em links seguros para a URL original.** Eles podem já estar selecionados se você configurar a política padrão. Selecione **Salvar**.
1. Em **Políticas que se aplicam a destinatários específicos,** escolha Regra de **links** seguros recomendados e selecione o **ícone** Editar.
1. Selecione **configurações,** role para baixo, insira a URL que você não deseja verificar e selecione o **ícone Adicionar.**
1. Selecione **aplicado a** e, em seguida, selecione seu nome de domínio. Selecione quaisquer domínios adicionais aos que você deseja que a regra seja aplicada. Selecione **adicionar**, **OK** e, em **seguida, Salvar**.

Os Links Seguros atp agora estão configurados. Permita até 30 minutos para que suas alterações entre em vigor.

Quando um usuário recebe um email com links, os links serão verificados. Se os links são considerados seguros, eles serão clicáveis. No entanto, se o link estiver na lista bloqueada, os usuários verão uma mensagem de que ele foi bloqueado.