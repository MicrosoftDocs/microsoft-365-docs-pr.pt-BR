---
title: Definir a hora do buffer no Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 271f43e4-b8f7-4d63-8059-b5747679bb7e
description: Defina o tempo de buffer antes ou depois de um compromisso no Microsoft Bookings para permitir tempo para limpeza ou redefinição de equipamentos.
ms.openlocfilehash: 882ab0340fe56976429ed8294f2fa386b801941f
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962342"
---
# <a name="set-buffer-time-in-microsoft-bookings"></a>Definir a hora do buffer no Microsoft Bookings

Alguns compromissos podem exigir tempo antes ou depois de se reunir com seu cliente para configurar, limpar ou redefinir sua sala e equipamento. Ou, se você estiver viajando entre compromissos do cliente, talvez precise de tempo para garantir que você e sua equipe possam se deslocar entre compromissos sem fazer com que o cliente aguarde.

Você pode definir o tempo de buffer antes do início dos compromissos, após o término dos compromissos ou ambos para dar à equipe o tempo extra necessário para se preparar para o próximo compromisso.

## <a name="set-buffer-time-defaults"></a>Definir padrões de tempo de buffer

Os padrões de tempo do buffer são definidos na **página Detalhes do** serviço no Bookings. Como todos os padrões de serviço definidos nesta página, esses padrões podem ser editados por você para uma reserva específica para atender às necessidades específicas do cliente.

A configuração de tempo de buffer pode ser encontrada logo abaixo dos **setores** de duração padrão na **página Detalhes do** serviço. Antes que ele possa ser definido para um determinado serviço, você deve habilitar a configuração de tempo do buffer selecionando a alternância de tempo do buffer. Isso faz **com** que os  drop-downs Antes e Depois apareçam, que são usados para escolher o período padrão de espera antes e depois de cada reserva, conforme mostrado aqui:

   ![Imagem do Bookings com tempo de buffer habilitado](../media/bookings-buffertime.png)

## <a name="buffer-time-and-appointment-timing"></a>Tempo do buffer e tempo do compromisso

Para evitar confusão sobre quando os clientes esperam se encontrar com você, o Bookings mostra o tempo do buffer e a hora real do compromisso (a hora em que seus clientes esperam se encontrar com você) em seu calendário e em confirmações e lembretes por email para a equipe relevante. Por exemplo, veja abaixo o que você verá no Bookings para um compromisso com um cliente que inclui 15 minutos de tempo de buffer de pré-compromisso.

Observe que o próprio evento (à esquerda na imagem abaixo) mostra sombreamento mais claro para o tempo do buffer e sombreamento mais escuro para o compromisso real do cliente. O call-out de compromisso (que é aberto quando você seleciona o evento) declara especificamente que o compromisso é das 9:00 às 10:00AM com Katie Jordan e inclui 15 minutos de tempo de buffer antes do compromisso e 0 minutos após o compromisso. As confirmações e lembretes para a equipe referenciam de forma semelhante o buffer específico e a hora do compromisso, enquanto o cliente só recebe confirmações e lembretes que referenciam um horário de 9:00 a 10:00AM.

   ![Imagem de chamada de compromisso do Bookings mostrando tempo de buffer](../media/bookings-buffertime-callout.png)

## <a name="buffer-time-and-availability"></a>Tempo e disponibilidade do buffer

Seus clientes não veem diretamente e não podem alterar os tempos de buffer definidos por você. No entanto, como o tempo de buffer é usado para calcular a duração geral do serviço, os clientes verão você e sua equipe relevante como reservados durante o buffer e os horários regulares do compromisso. Os clientes também verão a disponibilidade para você e sua equipe somente se houver tempo suficiente para o compromisso e seu tempo de buffer.

Por exemplo, um compromisso de uma hora com um tempo de buffer de pré-compromisso de 15 minutos requer um bloco de tempo disponível de pelo menos 1 hora e 15 minutos. Um compromisso para esse serviço, portanto, preencheria um bloco de 75 minutos de tempo em seu calendário e precisa de 75 minutos de disponibilidade para agendar sem conflito.
