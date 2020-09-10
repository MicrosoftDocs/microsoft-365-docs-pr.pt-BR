---
title: Adicionar equipe a reservas
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 298c529b-407b-4a2b-b2c5-6e77a9d1f07f
description: Use esta página para criar sua lista de equipes e gerenciar os detalhes do membro da equipe, como nome, número de telefone e endereço de email.
ms.openlocfilehash: cfd42eedb6e0bea08cdee1503fc373167996c75b
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419252"
---
# <a name="add-staff-to-bookings"></a>Adicionar equipe a reservas

A página da equipe em reservas é onde você cria sua lista de equipe e gerencia detalhes do membro da equipe, como nome, número de telefone e endereço de email. Você também pode definir as horas de trabalho para cada membro da equipe daqui.

> [!NOTE]
> As reservas são ativadas por padrão para clientes que têm as assinaturas do Microsoft 365 Business Standard, da Microsoft 365 a3 ou do Microsoft 365 a5. As reservas também estão disponíveis para clientes que têm o Office 365 Enterprise E3 e o Office 365 Enterprise e5, mas estão desativados por padrão. Para começar, confira [obter acesso aos Microsoft bookings](get-access.md). Para ativar ou desativar reservas, consulte [Ativar ou desativar reservas para sua organização](turn-bookings-on-or-off.md).

## <a name="add-staff"></a>Adicionar equipe

Embora as reservas sejam um recurso do Microsoft 365, nem todos os membros da equipe precisam ter uma conta do Microsoft 365. Todos os membros da equipe devem ter um endereço de email válido para que possam receber reservas e agendar alterações.

Assista a este vídeo ou siga as etapas abaixo para adicionar sua equipe.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWuVka]

1. Vá para a [página Gerenciar equipe](https://outlook.office.com/bookings/staff) e selecione **Adicionar equipe**

2. Selecione o botão **Adicionar equipe** .

3. Ao adicionar a equipe de dentro do seu locatário, digite o nome dele no campo **adicionar pessoas** e selecione-os quando eles aparecerem no menu suspenso. Os outros campos serão preenchidos automaticamente.

    Depois que um membro da equipe é adicionado, você pode editar o nome que aparece em todas as comunicações de livros, selecionando o **x** ao lado do nome e editando o campo **adicionar pessoas** . Isso pode ser útil se você quiser que os membros da equipe tenham um título ou nome específico exibido para clientes, como listar Adele Vance como "Dr. Vance, MD".

4. Para adicionar a equipe de fora do seu locatário, preencha manualmente o email e outras informações.

    > [!NOTE]
    > A equipe de fora do seu locatário não poderá compartilhar informações de disponibilidade com reservas.

5. Para cada membro da equipe, selecione uma função: administrador, visualizador ou convidado.
    - **Os administradores** podem editar todas as configurações, adicionar e remover equipe e criar, editar ou excluir reservas.
    - Os **visualizadores** podem ver todos os registros no calendário, mas não podem modificá-los ou excluí-los. Eles têm acesso somente leitura às configurações.
    - **Convidados** podem ser atribuídos a reservas, mas não podem abrir a caixa de correio de reserva.

6. Selecione **notificar todos os funcionários por email quando um reserva atribuído a eles for criado ou alterado** para habilitar emails de equipe. Este é um exemplo de email:

    :::image type="content" source="media/bookings-notify-all-email.jpg" alt-text="Um email de notificação de reservas":::

7. Selecionar **eventos no calendário do Office 365 afeta a disponibilidade** se você quiser que as informações de disponibilidade dos calendários dos membros da equipe afetem a disponibilidade dos serviços de reservas por meio de reservas.

    Por exemplo, se um membro da equipe tiver uma reunião de equipe ou um compromisso pessoal agendado para 3pm em uma quarta-feira, os registros mostrarão esse membro da equipe como indisponível para ser reservado nesse intervalo de tempo. Esse horário será exibido como ocupado ou provisório no modo de exibição calendário de livros, conforme mostrado no exemplo a seguir.

    :::image type="content" source="media/bookings-busy-tentative-view.jpg" alt-text="Um modo de exibição de um calendário de livros":::

> [!IMPORTANT]
> É altamente recomendável que você deixe essa configuração ativada (ela é ativada por padrão) para evitar reservas duplas e para otimizar a disponibilidade de seus membros da equipe.

8. Selecione **usar horário comercial** para definir todos os horários que possam ser agendados para que os membros da equipe estejam apenas dentro do horário comercial definido na seção **horário comercial** da página informações comerciais.

    Ao desmarcar essa caixa, a equipe pode receber horas personalizadas que limitam ainda mais quando podem ser agendadas. Isso é útil em cenários em que um membro da equipe só pode estar no local terças e Wednesdays ou dedicar suas manhãs para um tipo de compromisso e sua tarde para outros tipos.
