---
title: Obter notificações de incidentes no Microsoft 365 Defender
description: Saiba como criar regras para receber notificações por email para incidentes no Microsoft 365 Defender
keywords: incidente, email, notficações de email, configurar, usuários, caixa de correio, email, incidentes
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fec2263599f3ed727d3d9d70023927084eb1c094
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501068"
---
# <a name="get-incident-notifications-by-email"></a>Obter notificações de incidentes por email

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Você pode configurar o Microsoft 365 Defender para notificá-lo por email sempre que houver novos incidentes ou novas atualizações para incidentes existentes. 

Você pode optar por receber notificações com base na gravidade do incidente ou no grupo de dispositivos. Você também pode optar por receber uma notificação somente na primeira atualização por incidente.

Você pode adicionar ou remover destinatários nas notificações de email. Os destinatários recém-adicionados são notificados sobre incidentes depois que são adicionados. 

A notificação de email contém detalhes importantes sobre o incidente, como o nome do incidente, gravidade e categorias, entre outros. Você também pode ir diretamente a incidentes para que possa iniciar sua investigação imediatamente. Para obter mais informações sobre a investigação de incidentes, consulte [Investigar incidentes no Microsoft 365 Defender](./investigate-incidents.md).

>[!NOTE]
>Você precisa de permissões "Gerenciar configurações de segurança" para configurar as configurações de notificação de email. Se você optou por usar o gerenciamento de permissões básicas, os usuários com funções de Administrador de Segurança ou Administrador Global podem configurar notificações de email para você. <br> <br>
Da mesma forma, se sua organização estiver usando o controle de acesso baseado em função (RBAC), você só poderá criar, editar, excluir e receber notificações com base nos grupos de dispositivos que você tem permissão para gerenciar.

## <a name="create-rules-for-incident-notifications"></a>Criar regras para notificações de incidentes

Para configurar sua primeira notificação de email para incidentes, crie uma nova regra e personalize as configurações de notificação de email.

1. No painel de navegação, selecione **Configurações**  >  **Notificações de email de incidentes.**
2. Selecione **Adicionar item**.
3. Dê à regra um nome em **Name e** fornece uma **Descrição**.

    ![Criar janela de regra para notificações de email de incidentes](../../media/incidentemailnotif1.png) 
4. Selecione **Próximo** para ir para **Configurações de notificação**. Aqui você pode especificar:
    - **Gravidade do alerta** - Escolha a gravidade do alerta que disparará uma notificação de incidente. Por exemplo, se você quiser apenas ser informado sobre incidentes de alta gravidade, selecione Alta.
    - **Escopo do grupo de** dispositivos - Essa lista lista exibe todos os grupos de dispositivos que o usuário pode acessar. Selecione para quais grupos de dispositivos você está criando as regras de notificação de incidentes.
    - **Notificar somente a primeira ocorrência por incidente** - Selecionar essa opção enviará uma notificação de email somente no primeiro alerta que corresponde às outras seleções. Atualizações posteriores ou alertas relacionados ao incidente não dispararão uma notificação.
    - **Incluir nome da** organização - Indica se o nome do cliente aparece na notificação de email ou não.
    - **Incluir link de portal específico do locatário** - Adiciona um link com a ID do locatário para permitir o acesso a um locatário específico.
    
    ![Notif settings window for incident email notifs](../../media/incidentemailnotif2.png)
5. Selecione **Próximo** para ir na **seção Destinatários.** Aqui você pode especificar endereços de email que receberão as notificações de email de incidente. Selecione **Adicionar um destinatário após** digitar cada endereço de email.

    ![Adicionar janela de destinatários para notificações de email de incidentes](../../media/incidentemailnotif3.png) 

6. Por fim, **selecione Próximo** a ir para **Revisar regra** para que você possa ver todas as configurações associadas à nova regra. Os destinatários começarão a receber notificações de incidentes por email com base nas configurações.

## <a name="see-also"></a>Confira também
- [Visão geral de incidentes no Microsoft 365 Defender](./incidents-overview.md)
- [Priorizar incidentes no Microsoft 365 Defender](./incident-queue.md)
- [Investigar incidentes no Microsoft 365 Defender](./investigate-incidents.md)
