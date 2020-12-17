---
title: Adicionar um domínio
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
description: Saiba como adicionar outro domínio à sua assinatura.
ms.openlocfilehash: 16f6c4e416ede560d69014e320eb32c4453fd3f5
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701488"
---
# <a name="add-another-domain"></a>Adicionar outro domínio

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

Sua empresa pode precisar de vários nomes de domínio para fins diferentes. Por exemplo, você pode querer adicionar uma ortografia diferente ao nome da sua empresa porque os clientes já o estão usando e as comunicações não conseguiram contatá-lo.

## <a name="try-it"></a>Experimente!

1. No centro de administração do Microsoft 365, escolha **Configurar**.
1. Em **obter o domínio personalizado configurado**, selecione **Exibir**.
1. Escolha **gerenciar** e **Adicionar domínio**.
1. Insira o novo nome de domínio que você deseja adicionar e, em seguida, selecione **Avançar**.
1. Entre no seu registrador de domínio, neste caso, GoDaddy e selecione **Avançar**.
1. Se solicitado, entre em seu registrador e, em seguida, escolha **autorizar**.
1. Escolha **adicionar os registros DNS para mim** e, em seguida, selecione **Avançar**.
1. Escolha os serviços para o novo domínio e desmarque as caixas de seleção de todos os serviços que serão manipulados por um domínio diferente. Por exemplo, se você só quiser usar o novo domínio para email, escolha **Exchange** e desmarque as caixas de seleção para o **Skype for Business** e o **Gerenciamento de dispositivo móvel do Office 365**.
1. Selecione **Avançar**, **autorizar**, **Avançar** e **concluir**. Seu novo domínio foi adicionado.

Para receber emails em seu novo domínio, você precisará adicionar um novo alias de email para cada usuário:

1. Selecione **usuários**, **usuários ativos** e, em seguida, selecione o usuário ao qual o novo alias será atribuído.
1. Escolha **gerenciar aliases de email** e, em seguida, **adicione um alias**.
1. Insira o nome de usuário e, em seguida, escolha o novo domínio na lista suspensa.
1. Selecione **salvar alterações** e feche a janela.
1. Repita essas etapas para cada usuário que deve receber emails no novo domínio.