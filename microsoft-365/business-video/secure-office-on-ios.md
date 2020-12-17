---
title: Proteger aplicativos do Office no iOS
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
description: Saiba como proteger os aplicativos do Office no iOS com o Microsoft 365 Business Premium.
ms.openlocfilehash: 1703faa7cd7731f0779bacc3d2fa3ad3e4556910
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701461"
---
# <a name="secure-office-apps-on-ios"></a>Proteger aplicativos do Office no iOS

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

Você pode configurar uma política de acesso de usuário que exija que os usuários móveis insiram um PIN ou impressão digital para entrar e também criptografe arquivos de trabalho armazenados em seus dispositivos.

## <a name="try-it"></a>Experimente!

1. Acesse o centro de administração do Microsoft 365.
1. Em **políticas**, escolha **Adicionar política**.
1. No painel **Adicionar política** , digite um nome em **nome da política** e escolha o tipo de política que você deseja em **tipo de política**.
1. Ative **gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** e, em seguida, certifique-se de que as três configurações a seguir estão ativadas:
    - **Exigir um PIN ou uma impressão digital para acessar aplicativos do Office**
    - **Proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados**
    - **Criptografar arquivos de trabalho**

1. Em **arquivos nesses aplicativos serão protegidos**, selecione os aplicativos do Office que você deseja proteger em dispositivos móveis.
1. Em **quem receberá essas configurações?**, todos os usuários são selecionados por padrão, mas você pode escolher **alterar** para selecionar qualquer grupo de segurança que você tenha criado.
1. Para concluir a criação da política, escolha **Adicionar**.
1. Na página **Adicionar política** , escolha **fechar**.
1. Na home page do centro de administração, confirme se a nova política foi adicionada escolhendo **políticas** e revisando sua política na página **políticas** .