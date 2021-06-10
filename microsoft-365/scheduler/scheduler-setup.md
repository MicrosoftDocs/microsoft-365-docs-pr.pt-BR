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
ms.openlocfilehash: ba1e178545001473bf73eea3eb02b5ab1c7bf084
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861474"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>Configurando o Agendador para Microsoft 365

Para configurar o Agendador para Microsoft 365, a seguir estão os pré-requisitos:

|**Do que preciso?** |**Descrição** |
|-------------------|-------------|
|Caixa de correio da Cortana |Os administradores de locatários precisarão definir uma caixa de correio para servir como a caixa de correio "Cortana" (ou seja, cortana@yourdomain.com).         |
|Caixa de correio do Exchange Online |Os usuários devem ter um Exchange Online email e calendário         |
|Licença do agendador |Para obter informações sobre licenciamento e preços, consulte [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).        |

## <a name="create-a-mailbox-for-cortana"></a>Criar uma caixa de correio para a Cortana
Uma Exchange caixa de correio em seu locatário age como a caixa de correio da Cortana para seu locatário enviar e receber emails de e para a Cortana. Todos os emails enviados à Cortana são mantidos na caixa de correio da Cortana do locatário com base em sua política de retenção.

- Use o Microsoft 365 de administração para criar uma caixa de correio de usuário. Uma política de retenção de 30 dias é recomendada. 
- Use o nome Cortana no endereço SMTP principal da caixa de correio. Nomes como "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" ou "Cortana.Scheduler@yourdomain.com" são recomendados.

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a>Designar a caixa de correio como Assistente do Agendador

Após a criação de uma caixa de correio exclusiva para o Agendador da Cortana, você deve designar a caixa de correio para Microsoft 365 formalmente. Depois de designar a caixa de correio do Agendador da Cortana, ela estará disponível para agendar reuniões em nome de seus usuários.

Para designar a caixa de correio do Agendador da Cortana, um administrador autorizado deve executar um comando do PowerShell de uma linha. 

1. Conexão para Microsoft 365 espaço de executar o PowerShell remoto para sua organização.
2. Execute o seguinte script do PowerShell para designar a caixa de correio do Agendador:

```powershell

Set-mailbox cortana@contoso.com -SchedulerAssistant:$true

```

Depois de executar esse comando "set" na caixa de correio do Agendador da Cortana, um novo "PersistedCapability" é definido na caixa de correio para observar que essa caixa de correio é o "SchedulerAssistant".

> [!NOTE]
> Siga estas etapas para conectar sua organização ao PowerShell se você não tiver feito isso anteriormente: Conexão para Microsoft 365 [com o PowerShell - Microsoft 365 Enterprise | Microsoft Docs](../enterprise/connect-to-microsoft-365-powershell.md)

Para descobrir qual caixa de correio em sua organização está definida como assistente do Agendador cortana, execute a função get:
 
```powershell

Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}

```

> [!IMPORTANT]
> Pode levar até duas horas para a caixa de correio do Agendador concluir o provisionamento completo para definir o recurso SchedulerAssistant.

## <a name="exchange-online-mailbox"></a>Caixa de correio do Exchange Online
Agendador é um complemento para Microsoft 365. Os organizadores da reunião devem ter uma caixa Exchange Online caixa de correio e calendário para o Agendador funcionar.

## <a name="exchange-requirements"></a>Requisitos do Exchange

Além do Agendador de licenciamento, você deve ter uma das seguintes licenças:

- Microsoft 365 E3, A3, E5, A5
- Business Basic, Business, Business Standard, Business Premium
- Office 365 E1, A1, E3, A3, E5, A5
- Business Essentials, Business Premium
- Exchange Online Plan 1 or Plan 2 license. 

> [!Note]
> **O agendador Microsoft 365** não está disponível para usuários de Office 365 operados pela 21Vianet na China. Ele também não está disponível para usuários de Microsoft 365 com a nuvem alemã que usa o data trustee German Telekom. Ele tem suporte para usuários na Alemanha cujo local de dados não está no datacenter alemão.
>
>Este recurso também não é compatível com usuários da Nuvem Governamental, incluindo GCC, Consumidor, GCC Alto ou DoD.
