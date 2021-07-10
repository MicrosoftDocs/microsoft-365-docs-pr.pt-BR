---
title: Configurando o Agendador para Microsoft 365.
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Configurando o Agendador para Microsoft 365.
ms.openlocfilehash: 924b25e3d921f402c97632f7475ed5beea98d5c7
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362541"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>Configurando o Agendador para o Microsoft 365


Para configurar o Agendador para Microsoft 365, a seguir estão os pré-requisitos:

| Do que preciso? | Descrição |
|-------------------|-------------|
|Cortana caixa de correio |Os administradores de locatários precisarão definir uma caixa de correio para servir como a caixa de correio "Cortana" (ou seja, cortana@yourdomain.com).         |
|Caixa de correio do Exchange Online |Os usuários devem ter um Exchange Online email e calendário         |
|Licença do agendador |Para obter informações sobre licenciamento e preços, consulte [Scheduler for Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing).        |

## <a name="create-a-mailbox-for-cortana"></a>Criar uma caixa de correio para Cortana

Uma Exchange de correio em seu locatário age como a caixa de correio Cortana seu locatário para enviar e receber emails de e para Cortana. Todos os emails enviados Cortana são mantidos na caixa de correio de Cortana de seu locatário com base em sua política de retenção.

- Use o Centro de administração do Microsoft 365 para criar uma caixa de correio de usuário. Uma política de retenção de 30 dias é recomendada. 
- Use o nome Cortana no endereço SMTP principal da caixa de correio. Nomes como "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" ou "Cortana. Scheduler@yourdomain.com' são recomendados.

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a>Designar a caixa de correio como Assistente do Agendador

Depois que uma caixa de correio exclusiva para Cortana Agendador tiver sido criada, você deve designar a caixa de correio para Microsoft 365 formalmente. Depois de designar Cortana caixa de correio do Agendador, ela estará disponível para agendar reuniões em nome de seus usuários.

Para designar Cortana caixa de correio do Agendador, um administrador autorizado deve executar um comando do PowerShell de uma linha. 

1. Conexão para Microsoft 365 espaço de executar o PowerShell remoto para sua organização.

2. Execute o seguinte script do PowerShell para designar a caixa de correio do Agendador:

    ```powershell
    Set-mailbox cortana@contoso.com -SchedulerAssistant:$true
    ```
    
    Depois de executar esse comando "set" na caixa de correio Cortana Agendador, um novo "PersistedCapability" é definido na caixa de correio para observar que essa caixa de correio é o "SchedulerAssistant".

> [!NOTE]
> Siga estas etapas para conectar sua organização ao PowerShell se você não tiver feito isso anteriormente: Conexão para Microsoft 365 [com o PowerShell](../enterprise/connect-to-microsoft-365-powershell.md).

Para descobrir qual caixa de correio na sua organização está definida como assistente Cortana agendador, execute a função get:

```powershell
Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}
```

> [!IMPORTANT]
> Pode levar até duas horas para a caixa de correio do Agendador concluir o provisionamento completo para definir o recurso SchedulerAssistant.

## <a name="exchange-online-mailbox"></a>Caixa de correio do Exchange Online
Uma licença do Agendador é um complemento para Microsoft 365, que permite ao organizador da reunião delegar suas tarefas de agendamento de reunião ao assistente do Agendador. Para que o Agendador funcione, normalmente por meio Microsoft 365 licença, os organizadores da reunião exigem os seguintes componentes:

- Uma caixa de correio designada como caixa de correio de assistente de agendamento
- Licença do agendador
- Exchange Online caixa de correio e calendário

Os participantes da reunião não exigem agendador ou Microsoft 365 licença.

## <a name="scheduler-end-user-license-requirements"></a>Requisitos de licença do usuário final do agendador

Uma licença do Agendador requer uma das seguintes licenças:

- Microsoft 365 E3, A3, E5, A5
- Business Basic, Business, Business Standard, Business Premium
- Office 365 E1, A1, E3, A3, E5, A5
- Business Essentials, Business Premium
- Exchange Online Plan 1 or Plan 2 license. 

> [!Note]

> O agendador para Microsoft 365 está disponível em ambientes multi-locatários em todo o mundo somente em inglês. **O agendador Microsoft 365** não está disponível para os usuários de:

- Microsoft 365 operado pela 21Vianet na China
- Microsoft 365 com a nuvem alemã que usa o telekom alemão do destinatário de dados
- Nuvem governamental incluindo GCC, Consumidor, GCC Alta ou DoD

O agendador dá suporte a usuários na Alemanha cuja localização de dados não está no datacenter alemão.
