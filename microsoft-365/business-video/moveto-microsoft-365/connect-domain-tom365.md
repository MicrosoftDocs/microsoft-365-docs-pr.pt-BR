---
title: Conectar seu domínio ao Microsoft 365
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
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
description: Saiba como conectar seu domínio ao Microsoft 365.
ms.openlocfilehash: c7827b93b56560579b31bd2abb5a852467565103
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794567"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>Conectar seu domínio ao Microsoft 365 para empresas

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

Depois de configurar o Microsoft 365 e mudar seus dados de email do Google Workspace, você poderá conectar seu domínio ao Microsoft 365. 

Primeiro, você precisará excluir registros DNS existentes do Google e, em seguida, podemos adicionar novos registros DNS do Microsoft 365.

## <a name="try-it"></a>Experimente!

1. Entre no console de administração do Espaço de Trabalho do Google [admin.google.com.](https://admin.google.com)
1. Select **Domains**, **Manage domains**, **View details**, Manage **domain**, then **DNS** in the left nav.
1. Role para baixo **até registros sintéticos,** abra **Google Workspace**, selecione **Excluir** e **Excluir** novamente.
1. Role para baixo **até registros** de recursos personalizados e exclua quaisquer registros DNS existentes que apareçam, incluindo qualquer um que você possa ter criado anteriormente para o Microsoft 365.
1. Vá para o [Centro de administração do Microsoft 365.](https://admin.microsoft.com)
1. In the left nav, choose, **Show all**, **Settings**, **Domains**.
1. Em seguida, escolha seu domínio padrão.
1. Selecione **Continuar configuração,** em seguida, para conectar seu domínio, escolha  **Continuar**.
1. Role para baixo para exibir os registros DNS que precisam ser copiados para o Google.
1. Abra **registros MX** e, em **Pontos de endereço ou valor,** copie o registro.
1. Retorne ao Google e, na seção **Registros** de recursos personalizados, abra o menu suspenso de tipo de registro e selecione **MX**.
1. No campo **Dados,** copie o registro copiado.
1. Em seguida, selecione **OK**.
1. Repita o processo para registros CNAME e TXT e adicione os valores na página de gerenciamento dns do Google.
1. Retorne ao Centro de administração do Microsoft 365 e selecione **Continuar.**

    Sua configuração de domínio foi concluída.