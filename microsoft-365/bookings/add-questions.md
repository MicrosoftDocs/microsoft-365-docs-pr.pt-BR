---
title: Adicionar perguntas personalizadas e necessárias à página de reserva
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: fd6b7587-5055-4bcd-83a4-13bd4929bfff
description: Se você precisar fazer perguntas aos clientes ao agendar um compromisso online, você pode adicionar perguntas personalizadas e perguntas necessárias à página de reserva.
ms.openlocfilehash: ebbb07857fd8bb196f769dfb7e71ad25a85dfd54
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419249"
---
# <a name="add-custom-and-required-questions-to-the-booking-page"></a>Adicionar perguntas personalizadas e necessárias à página de reserva

As reservas permitem que você crie perguntas para perguntar aos clientes quando eles estão reservando compromissos. Também permite que você escolha quais perguntas são necessárias.

Você associa as perguntas a um serviço, portanto, cada serviço pode ter um conjunto diferente de perguntas. Por exemplo, uma stylist de cabelo pode perguntar aos clientes que estão reservando um compromisso de cores de cabelo caso tenham qualquer allergies conhecida para bleaches ou matizes. Isso permite que você e seus clientes Economizem tempo quando eles chegarem ao compromisso.

Os clientes verão as perguntas personalizadas quando criarem seus compromissos na página de reserva. A equipe verá as perguntas personalizadas quando criar uma nova reserva do calendário de reservas ou ao exibir um compromisso existente. As reservas salvam todas as suas perguntas em uma lista mestra para que você não precise recriar as mesmas perguntas para todos os serviços. Você também pode escolher se as perguntas são obrigatórias ou opcionais.

> [!NOTE]
> As respostas do cliente às perguntas podem ser vistas quando você olhar para o compromisso no calendário de reserva.

Para obter mais informações sobre como personalizar e personalizar sua página de reservas, consulte [personalizar sua página de reservas](customize-booking-page.md).

## <a name="add-custom-questions-to-your-services"></a>Adicionar perguntas personalizadas aos seus serviços

1. Entre no Microsoft 365 e vá para **reservas**.

1. Vá até **Serviços** e edite um serviço existente ou **adicione um serviço**.

1. Role para baixo até a seção **campos personalizados** e, em seguida, selecione **Modificar**.

   Já adicionamos algumas perguntas básicas sobre informações do cliente: email do cliente, número de telefone, endereço do cliente e notas do cliente. Na primeira vez que você fizer isso, as perguntas de informações sobre o cliente serão realçadas em cinza. Isso significa que o usuário verá essa pergunta. Se você selecionar a pergunta, a caixa de realce em torno dela desaparecerá e seu cliente não será solicitado a confirmar essa pergunta.

   Neste exemplo, o número de telefone e as anotações do cliente foram desativados e criamos duas novas perguntas personalizadas a serem feitas.

   ![Imagem da tela de perguntas personalizadas](../media/bookings-questions-custom-fields.png)

1. Para fazer a pergunta obrigatória, marque a caixa de seleção **necessário** . Seu cliente não poderá concluir a reserva até que ele tenha respondido às perguntas necessárias.

1. Para criar uma pergunta personalizada, selecione **Adicionar uma pergunta** na parte superior do painel. Escreva a sua pergunta e, em seguida, selecione **salvar**.

1. Clique na pergunta para habilitá-la. Uma caixa realçada é exibida ao redor e a pergunta está habilitada.

1. Clique em **OK** na parte superior da página e, em seguida, **salve o serviço**.

Os agendamentos salvarão todas as suas perguntas personalizadas em uma lista mestra para que você possa facilmente adicionar perguntas a cada serviço sem precisar digitar repetidamente as mesmas perguntas. Por exemplo, se você abrir um serviço diferente, a pergunta que você criou para o primeiro serviço será mostrada na seção campos personalizados, mas ela wil ser desabilitada. Clique na pergunta para que um retângulo realçado seja exibido e a pergunta esteja habilitada.

Neste exemplo, você pode ver que as perguntas adicionadas para o primeiro serviço estão disponíveis para este serviço. Qualquer pergunta que você criar para esse serviço estará disponível para todos os serviços.

   ![Imagem das perguntas que aparecem para vários serviços](../media/bookings-questions-services.png)

Se sua página de reserva já estiver publicada, você não precisará fazer mais nada. Os clientes verão as perguntas na próxima vez que fizerem o seu livro. Se sua página de reserva ainda não estiver publicada, vá para a **página de reserva** do Outlook na Web e selecione **salvar e publicar**.

> [!WARNING]
> Você também pode excluir perguntas da lista mestra. No entanto, se você excluir uma pergunta, ela será excluída de todos os serviços. Recomendamos que você desabilite a pergunta selecionando-a para garantir que não afete nenhum outro serviço. Você pode ver que uma pergunta está desabilitada se não estiver entre um retângulo realçado.

## <a name="customer-experience"></a>Experiência do cliente

Quando o seu cliente agendar um compromisso com você, as perguntas básicas sobre as informações do cliente serão exibidas na seção **adicionar seus detalhes** . Qualquer pergunta personalizada que você adicionar estará na seção **fornecer informações adicionais** .

![Imagem do que os clientes veem quando as perguntas estão habilitadas](../media/bookings-questions-customer.png)

## <a name="staff-experience"></a>Experiência da equipe

Quando seus clientes agendarem um compromisso com você, sua equipe verá as perguntas e as respostas do cliente no calendário de reservas. Para vê-lo, acesse calendário de **reservas** \> **Calendar** e abra um compromisso.

![Imagem da equipe que vê quando as perguntas estão habilitadas](../media/bookings-questions-staff.png)
