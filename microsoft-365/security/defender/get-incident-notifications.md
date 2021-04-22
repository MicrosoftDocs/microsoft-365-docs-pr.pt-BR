---
title: Obter notificações de incidentes por email no Microsoft 365 Defender
description: Saiba como criar regras para receber notificações por email para incidentes no Microsoft 365 Defender
keywords: incident, email, email notfications, configure, users, mailbox, email, incidents, analyze, response
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
ms.openlocfilehash: 7ba21e08f72760654993335764df00e78abc87b2
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939713"
---
# <a name="get-incident-notifications-by-email"></a>Obter notificações de incidentes por email

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Você pode configurar o Microsoft 365 Defender para notificar sua equipe com um email sobre novos incidentes ou atualizações para incidentes existentes. Você pode optar por receber notificações com base em:

- Gravidade do incidente.
- Grupo de dispositivos.
- Somente na primeira atualização por incidente.

A notificação de email contém detalhes importantes sobre o incidente, como o nome do incidente, gravidade e categorias, entre outros. Você também pode ir diretamente para o incidente e iniciar sua análise imediatamente. Para obter mais informações, consulte [Analyze incidents](investigate-incidents.md).

Você pode adicionar ou remover destinatários nas notificações de email. Novos destinatários são notificados sobre incidentes depois que são adicionados. 

>[!NOTE]
>Você precisa da permissão "Gerenciar configurações de segurança" para configurar as configurações de notificação de email. Se você optou por usar o gerenciamento de permissões básicas, os usuários com funções de Administrador de Segurança ou Administrador Global podem configurar notificações de email para você. <br> <br>
Da mesma forma, se sua organização estiver usando o controle de acesso baseado em função (RBAC), você só poderá criar, editar, excluir e receber notificações com base nos grupos de dispositivos que você tem permissão para gerenciar.

## <a name="create-a-rule-for-email-notifications"></a>Criar uma regra para notificações por email

Siga estas etapas para criar uma nova regra e personalizar as configurações de notificação de email.

1. No painel de navegação, selecione **Configurações > do Microsoft 365 Defender > notificações de email de incidentes.**
2. Selecione **Adicionar item**.
3. Na página **Noções Básicas,** digite o nome da regra e uma descrição e selecione **Next**.
4. Na página **Configurações de notificação,** configure:
    - **Gravidade do alerta** - Escolha as gravidades de alerta que dispararão uma notificação de incidente. Por exemplo, se você quiser apenas ser informado sobre incidentes de alta gravidade, selecione **Alta**.
    - **Escopo do grupo de** dispositivos - Você pode especificar todos os grupos de dispositivos ou selecionar na lista de grupos de dispositivos em seu locatário.
    - **Notificar somente a primeira ocorrência por incidente** - Selecione se quiser uma notificação somente no primeiro alerta que corresponde às outras seleções. Atualizações ou alertas posteriores relacionados ao incidente não enviarão notificações adicionais.
    - **Inclua o nome da organização no email** - Selecione se você deseja que o nome da sua organização apareça na notificação de email.
    - **Incluir link de portal** específico do locatário - Selecione se você deseja adicionar um link com a ID do locatário na notificação de email para acesso a um locatário específico do Microsoft 365.

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="Configurações de notificação para notificações de email de incidentes":::

5. Selecione **Avançar**. Na página **Destinatários,** adicione os endereços de email que receberão as notificações de incidentes. Selecione **Adicionar** após digitar cada novo endereço de email. Para testar notificações e garantir que os destinatários as recebam nas caixas de entrada, selecione **Enviar email de teste.** 
6. Selecione **Avançar**. Na página **Revisar regra,** revise as configurações da regra e selecione **Criar regra**. Os destinatários começarão a receber notificações de incidentes por email com base nas configurações.

Para editar uma regra existente, selecione-a na lista de regras. No painel com o nome da regra, selecione **Editar** regra e faça suas alterações nas páginas **Noções Básicas,** Configurações de Notificação e **Destinatários.** 

Para editar uma regra existente, selecione-a na lista de regras. No painel com o nome da regra, selecione **Excluir**.

## <a name="see-also"></a>Confira também
- [Visão geral dos incidentes](incidents-overview.md)
- [Priorizar incidentes](incident-queue.md)
- [Analisar incidentes](investigate-incidents.md)
