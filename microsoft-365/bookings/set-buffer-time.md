---
title: Definir tempo de buffer no Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 271f43e4-b8f7-4d63-8059-b5747679bb7e
description: Defina o tempo de buffer antes ou depois de um compromisso no Microsoft Bookings para permitir tempo para limpar ou redefinir o equipamento.
ms.openlocfilehash: 882ab0340fe56976429ed8294f2fa386b801941f
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962342"
---
# <a name="set-buffer-time-in-microsoft-bookings"></a>Definir tempo de buffer no Microsoft Bookings

Alguns dos seus compromissos podem exigir tempo antes ou depois de se reunir com seu cliente para configurar, limpar ou redefinir sua sala e equipamento. Ou se você estiver no caminho entre os compromissos do cliente, talvez precise de tempo para garantir que você e sua equipe possam viajar entre compromissos sem fazer com que o cliente aguarde.

Você pode definir o tempo de buffer antes do início dos compromissos, após o término dos compromissos ou ambos para dar aos funcionários o tempo extra necessário para se prepararem para o próximo compromisso.

## <a name="set-buffer-time-defaults"></a>Definir padrões de tempo de buffer

Os padrões de tempo de buffer são definidos na página **Detalhes do** serviço no Bookings. Como todos os padrões de serviço definidos nesta página, esses padrões podem ser editados por você para uma reserva específica para atender às necessidades específicas do cliente.

A configuração de tempo de buffer pode ser encontrada logo abaixo dos **seladores** de duração padrão na **página Detalhes do** serviço. Antes que ele possa ser definido para um determinado serviço, você deve habilitar a configuração de tempo de buffer selecionando a alternância de tempo do buffer. Isso faz com  que os drop-downs **Antes** e Depois apareçam, que são usados para escolher o período de tempo padrão a ser reservado antes e depois de cada reserva, conforme mostrado aqui:

   ![Imagem do Bookings com tempo de buffer habilitado](../media/bookings-buffertime.png)

## <a name="buffer-time-and-appointment-timing"></a>Tempo de buffer e hora do compromisso

Para evitar confusão sobre quando os clientes esperam se reunir com você, o Bookings mostra a hora do buffer e a hora real do compromisso (o tempo que seus clientes esperam reunir com você) em seu calendário e em confirmações de email e lembretes para funcionários relevantes. Por exemplo, abaixo está o que você verá no Bookings para um compromisso com um cliente que inclui 15 minutos de tempo de buffer de pré-compromisso.

Observe que o evento em si (à esquerda na imagem abaixo) mostra sombreamento mais claro para o tempo de buffer e sombreamento mais escuro para o compromisso real do cliente. O chamado de compromisso (que é aberto quando você seleciona o evento) afirma especificamente que o compromisso é das 9:00 às 10:00 da manhã com Katie Jordan e inclui 15 minutos de tempo de buffer antes do compromisso e 0 minutos após o compromisso. Confirmações e lembretes para a equipe referenciam o buffer específico e o horário do compromisso, enquanto o cliente só recebe confirmações e lembretes que referenciam um horário de 9:00 a 10:00AM.

   ![Imagem de chamada de compromisso do Bookings com tempo de buffer sendo exibido](../media/bookings-buffertime-callout.png)

## <a name="buffer-time-and-availability"></a>Tempo de buffer e disponibilidade

Seus clientes não veem diretamente e não podem alterar os tempos de buffer definidos. No entanto, como o tempo de buffer é usado para calcular a duração geral do serviço, os clientes verão você e sua equipe relevantes como reservados durante o buffer e os horários de compromisso regulares. Os clientes também só verão disponibilidade para você e sua equipe se houver tempo suficiente para o compromisso e seu tempo de buffer.

Por exemplo, um compromisso de uma hora com um tempo de buffer de pré-compromisso de 15 minutos requer um bloco de tempo disponível de pelo menos 1 hora e 15 minutos. Portanto, um compromisso para esse serviço preencheria um bloco de 75 minutos de tempo em seu calendário e precisa de 75 minutos de disponibilidade para reservar sem conflitos.
