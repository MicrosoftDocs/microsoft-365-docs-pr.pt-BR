---
title: Obter notificações de incidentes no Microsoft 365 Defender
description: Saiba como criar regras para receber notificações por email sobre incidentes no Microsoft 365 Defender
keywords: incidente, email, notações de email, configurar, usuários, caixa de correio, email, incidentes
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f25be4de3f25db869957474c3cb32b20e9f7aa53
ms.sourcegitcommit: 88d358d778804b26d5e41c53b4f725d01a78112b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49848886"
---
# <a name="get-incident-notifications-by-email"></a>Obter notificações de incidentes por email

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Você pode configurar o Microsoft 365 Defender para notificá-lo por email sempre que houver novos incidentes ou novas atualizações para incidentes existentes. 

Você pode optar por receber notificações com base na gravidade do incidente ou por grupo de dispositivos. Você também pode optar por receber uma notificação somente na primeira atualização por incidente.

Você pode adicionar ou remover destinatários nas notificações por email. Os destinatários recém-adicionados são notificados sobre incidentes depois que são adicionados. 

A notificação por email contém detalhes importantes sobre o incidente, como o nome do incidente, a gravidade e as categorias, entre outros. Você também pode ir diretamente a incidentes para iniciar a investigação imediatamente. Para obter mais informações sobre como investigar incidentes, consulte [Investigar incidentes no Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

>[!NOTE]
>Você precisa de permissões de "Gerenciar configurações de segurança" para definir as configurações de notificação de email. Se você optou por usar o gerenciamento de permissões básicas, os usuários com funções de Administrador de Segurança ou Administrador Global podem configurar notificações por email para você. <br> <br>
Da mesma forma, se sua organização estiver usando o controle de acesso baseado em função (RBAC), você só poderá criar, editar, excluir e receber notificações com base nos grupos de dispositivos que você tem permissão para gerenciar.

## <a name="create-rules-for-incident-notifications"></a>Criar regras para notificações de incidentes

Para configurar sua primeira notificação por email para incidentes, crie uma nova regra e personalize as configurações de notificação de email.

1. No painel de navegação, selecione **Notificações por**  >  **email do Incidente de Configurações.**
2. Selecione **Adicionar item**.
3. Dê um nome à regra em **Nome e** fornecer uma **Descrição.**

    ![Criar janela de regra para notifica o email de incidente](../../media/incidentemailnotif1.png) 
4. Selecione **Próximo** para ir para **configurações de Notificação.** Aqui você pode especificar:
    - **Gravidade do alerta** - Escolha a gravidade do alerta que disparará uma notificação de incidente. Por exemplo, se você quiser apenas ser informado sobre incidentes de alta gravidade, selecione Alta.
    - **Escopo do grupo de** dispositivos - Essa lista suspenso exibe todos os grupos de dispositivos que o usuário pode acessar. Selecione para quais grupos de dispositivos você está criando as regras de notificação de incidentes.
    - **Notificar somente na primeira ocorrência por incidente-** Selecionar essa opção enviará uma notificação por email somente no primeiro alerta que corresponde às outras seleções. Atualizações ou alertas posteriores relacionados ao incidente não dispararão uma notificação.
    - **Incluir nome da** organização - Indica se o nome do cliente aparece na notificação por email ou não.
    - **Inclua um link de portal específico do locatário:** adiciona um link com a ID de locatário para permitir o acesso a um locatário específico.
    
    ![Notif settings window for incident email notifs](../../media/incidentemailnotif2.png)
5. Selecione **Próximo** para ir na **seção Destinatários.** Aqui você pode especificar endereços de email que receberão as notificações por email de incidente. Selecione **Adicionar um destinatário depois** de digitar cada endereço de email.

    ![Janela Adicionar destinatários para notifica o email de incidente](../../media/incidentemailnotif3.png) 

6. Por fim, **selecione Próximo** para ir **para a** regra revisão para que você possa ver todas as configurações associadas à sua nova regra. Os destinatários começarão a receber notificações de incidentes por email com base nas configurações.

## <a name="see-also"></a>Confira também
- [Visão geral de incidentes no Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [Priorizar incidentes no Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [Investigar incidentes no Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

