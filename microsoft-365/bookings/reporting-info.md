---
title: Informações de relatório do Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 03a9acc9-f29c-456b-9fb2-0f49474b2708
description: Saiba como você pode ver uma exibição de 4 meses de sua atividade do Bookings
ms.openlocfilehash: ad0a21454cfe28cec521e545e587105e8f8a7454
ms.sourcegitcommit: 76f3c75413cc960289489d0ca29efadb8a9a5b31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "51887216"
---
# <a name="reporting-info-for-bookings"></a>Informações de relatórios para o Bookings

Agora você pode ver uma exibição de quatro meses do calendário do Bookings em um arquivo TSV. O arquivo TSV mostrará quatro meses de dados, mas você pode selecionar diferentes períodos de quatro meses ao longo de um ano.

Essas informações de nível de compromisso podem ser usadas para visualizar a atividade do cliente em torno do calendário do Bookings. Os arquivos TSV são arquivos de valores separados por tabulação. Você pode exibir ou editar um arquivo como este com qualquer editor de texto ou programa de planilha, como Excel.

## <a name="see-four-months-of-booking-activity"></a>Consulte quatro meses de atividade do Booking

1. No painel de calendário do Bookings, selecione **Exportar mais dados como TSV**.

:::image type="content" source="../media/bookings-activities.png" alt-text="Captura de tela: 4 meses de atividade do Bookings":::

1. Salve o arquivo com um novo nome e especifique .xls ou formato xlsx.

1. Abra o arquivo para ver a exibição de quatro meses do calendário do Bookings.

1. Escolha a data do relatório e selecione **Exportar**.

:::image type="content" source="../media/bookings-reporting-dates.png" alt-text="Captura de tela: escolha um intervalo de tempo e exporte dados para o arquivo TSV.":::

1. O relatório baixado contém um novo conjunto de campos além dos campos existentes.

O relatório inclui os campos a seguir.

 - **Data & Hora**
- **Nome do cliente**
- **Email do Cliente**
- **Cliente Telefone**
- **Endereço do cliente**
- **Bastão**
- **Serviço**
- **Location**
- **Duração (minutos)**
- **Tipo de Evento**

O relatório aprimorado agora contém os campos a seguir.

- **Tipo de preço**   Tipo de preço padrão definido para um serviço ao criar o serviço.
- **Preço**   Preço correspondente ao tipo de preço escolhido.
- **Conversor de Moedas** Conversor de Moedas tipo definido para uma empresa.   
- **Participantes cc**   Os destinatários que receberão as notificações de email para uma reserva. Isso pode ser especificado no aplicativo Teams ao criar uma reserva.
- **Contagem de participantes inscretos**   Quantos clientes reservaram um serviço de reserva de grupo.
- **Notificações de texto habilitadas**   Se os clientes podem receber SMS notificações relacionadas a texto.
- **Campos personalizados**   Todas as perguntas e respostas relacionadas a uma única reserva são combinadas neste campo.
- **ID do Booking**   Isso é útil para identificar as mesmas reservas de um serviço de grupo.
