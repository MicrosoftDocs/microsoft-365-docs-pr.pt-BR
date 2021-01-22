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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como adicionar outro domínio à sua assinatura.
ms.openlocfilehash: a5df440f3b7e28c2bdbc69f9383a8399ef193ed0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927605"
---
# <a name="add-another-domain"></a>Adicionar outro domínio

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

Sua empresa pode precisar de vários nomes de domínio para finalidades diferentes. Por exemplo, talvez você queira adicionar uma ortografia diferente do nome da sua empresa, pois os clientes já a estão usando e suas comunicações não alcançaram você.

## <a name="try-it"></a>Experimente!

1. No Centro de administração do Microsoft 365, escolha **Configuração.**
1. Em **Obter sua configuração de domínio personalizado,** selecione **Exibir**.
1. Escolha **Gerenciar** e, em **seguida, Adicionar domínio.**
1. Insira o novo nome de domínio que você deseja adicionar e selecione **Next**.
1. Entre no registrador de domínios, neste caso, GoDaddy e selecione **Próximo.**
1. Se solicitado, entre no registrador e escolha **Autorizar.**
1. Choose **Add the DNS records for me**, and then select **Next**.
1. Escolha os serviços para seu novo domínio e des marque as caixas de seleção de todos os serviços que serão tratados por um domínio diferente. Por exemplo, se você quiser usar apenas o novo domínio para email, escolha **Exchange** e des marque as caixas de seleção do **Skype for Business** e gerenciamento de dispositivos móveis para o Office **365.**
1. Selecione **Next**, **Authorize**, **Next** e, em **seguida, Finish**. Seu novo domínio foi adicionado.

Para receber emails em seu novo domínio, você precisará adicionar um novo alias de email para cada usuário:

1. Selecione **Usuários**, **Usuários ativos** e, em seguida, selecione o usuário que receberá o novo alias.
1. Escolha **Gerenciar aliases de email** e, em **seguida, adicione um alias.**
1. Insira o nome de usuário e escolha o novo domínio na lista drop-down.
1. Selecione **Salvar alterações** e feche a janela.
1. Repita essas etapas para cada usuário que deve receber emails no novo domínio.