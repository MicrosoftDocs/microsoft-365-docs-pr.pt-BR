---
title: Definir o tempo do buffer em Microsoft bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 271f43e4-b8f7-4d63-8059-b5747679bb7e
description: Defina o tempo do buffer antes ou depois de um compromisso em Microsoft bookings para permitir o tempo de limpeza ou redefinição de equipamento.
ms.openlocfilehash: 882ab0340fe56976429ed8294f2fa386b801941f
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962342"
---
# <a name="set-buffer-time-in-microsoft-bookings"></a>Definir o tempo do buffer em Microsoft bookings

Alguns dos seus compromissos podem exigir tempo antes ou após a reunião com o cliente para configurar, limpar ou redefinir a sala e o equipamento. Ou se você estiver viajando entre compromissos de clientes, talvez precise de tempo para garantir que você e sua equipe possam viajar entre compromissos sem fazer o cliente aguardar.

Você pode definir o tempo do buffer antes do início dos compromissos, após o fim dos compromissos ou ambos para dar à equipe o tempo adicional necessário para se preparar para o próximo compromisso.

## <a name="set-buffer-time-defaults"></a>Definir padrões de tempo do buffer

Os padrões de tempo do buffer são definidos na página **detalhes do serviço** em reservas. Como todos os padrões de serviço definidos nessa página, esses padrões podem ser editados por você para uma reserva específica para atender às necessidades específicas do cliente.

A configuração de tempo do buffer pode ser encontrada logo abaixo dos seletores de **duração padrão** na página **detalhes do serviço** . Antes de poder definir um determinado serviço, você deve habilitar a configuração de tempo do buffer selecionando a opção de tempo de buffer toggle. Isso faz com que as listas suspensas **antes** e **depois** apareçam, que são usadas para escolher a quantidade de tempo padrão a ser mantida antes e depois de cada reserva, conforme mostrado aqui:

   ![Imagem de reservas com tempo de buffer habilitado](../media/bookings-buffertime.png)

## <a name="buffer-time-and-appointment-timing"></a>Intervalo de tempo e compromisso do buffer

Para evitar confusão sobre quando os clientes esperam se reunir com você, as reservas mostram o tempo do buffer e o tempo real do compromisso (o tempo que seus clientes esperam cumprir com você) em seu calendário e em confirmações e lembretes de email para a equipe relevante. Por exemplo, veja a seguir o que você veria em reservas de um compromisso com um cliente que inclui 15 minutos de tempo de buffer antes do compromisso.

Observe que o evento em si (à esquerda na imagem abaixo) mostra um sombreamento mais claro para o tempo do buffer e sombreamento mais escuro para o compromisso do cliente real. O check-out do compromisso (que é aberto quando você seleciona o evento) declara especificamente que o compromisso é de 9:00AM a 10:00AM com o Katie Jordânia e inclui 15 minutos de tempo de buffer antes do compromisso e 0 minutos após o compromisso. Confirmações e lembretes para a equipe referenciar o buffer específico e o tempo do compromisso, enquanto o cliente só obteria confirmações e lembretes que fazem referência a um horário de compromisso 9:00AM a 10:00AM.

   ![Imagem de reservas de compromisso com o tempo de buffer mostrando](../media/bookings-buffertime-callout.png)

## <a name="buffer-time-and-availability"></a>Tempo e disponibilidade do buffer

Os clientes não vêem diretamente nem podem alterar os tempos de buffer que você definiu. No entanto, como o tempo de buffer é usado para calcular a duração geral do serviço, os clientes verão você e sua equipe relevante como reservados durante o buffer e os horários de compromissos regulares. Os clientes também veem a disponibilidade para você e sua equipe se houver tempo suficiente para o compromisso e o tempo do buffer.

Por exemplo, um compromisso de uma hora com um tempo de buffer de pré compromisso de 15 minutos requer um bloco de tempo disponível de pelo menos 1 hora e 15 minutos. Portanto, um compromisso para esse serviço preencherá um bloco de tempo de 75 minutos no seu calendário e precisará de 75 minutos de disponibilidade para o livro sem conflito.
