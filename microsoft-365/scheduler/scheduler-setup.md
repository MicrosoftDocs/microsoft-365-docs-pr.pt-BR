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
ms.openlocfilehash: 79e1596288836770c720cb312580fc706bb7b95f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286123"
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

- Use o Microsoft 365 de administração para criar uma nova caixa de correio. Uma política de retenção de 30 dias é recomendada. Use o nome Cortana no endereço SMTP principal da caixa de correio. Nomes como "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" ou "Cortana.Scheduler@yourdomain.com" são recomendados.
- Contate a Microsoft (scheduler_m365@microsoft.com) para habilitar sua caixa de correio da Cortana. 

> [!IMPORTANT]
> Entre em contato com a Microsoft para configurar sua caixa de correio da Cortana para usar o serviço Agendador enviando emails scheduler_m365@microsoft.com. A habilitação da caixa de correio da Cortana pode levar até duas semanas.

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
