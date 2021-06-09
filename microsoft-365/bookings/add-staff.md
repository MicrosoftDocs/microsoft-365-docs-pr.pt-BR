---
title: Adicionar funcionários ao Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
description: Use esta página para criar sua lista de funcionários e gerenciar detalhes do membro da equipe, como nome, número de telefone e endereço de email.
ms.openlocfilehash: 23757c492986936125eff1203e6a99231164da22
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768940"
---
# <a name="add-staff-to-bookings"></a>Adicionar funcionários ao Microsoft Bookings

A página Equipe no Bookings é onde você cria sua lista de funcionários e gerencia os detalhes do membro da equipe, como nome, número de telefone e endereço de email. Você também pode definir horários de trabalho para cada membro da equipe a partir daqui.

## <a name="before-you-begin"></a>Antes de começar

Embora o Bookings seja um recurso Microsoft 365, nem todos os membros da sua equipe precisam ter uma conta Microsoft 365. Todos os membros da equipe devem ter um endereço de email válido para que possam receber reservas e agendar alterações.

## <a name="watch-add-your-staff-to-bookings"></a>Assista: Adicione sua equipe ao Bookings

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWuVka]

## <a name="steps"></a>Etapas

1. Vá para a [página Gerenciar equipe e](https://outlook.office.com/bookings/staff) selecione Adicionar **equipe**

2. Selecione o **botão Adicionar Equipe.**

3. Ao adicionar funcionários de dentro da sua organização, digite seu nome no campo **Adicionar** pessoas e selecione-as quando elas aparecerem no menu suspenso. Os outros campos serão preenchidos automaticamente.

    Depois que um membro da equipe é adicionado, você pode editar o nome que aparece em todas as comunicações do Bookings selecionando **o x** ao lado de seu nome e editando o campo **Adicionar pessoas.** Isso pode ser útil se você quiser que os membros da equipe tenham um título ou nome específico exibido para clientes, como listar Adele Vance como "Dr. Vance, MD".

4. Para adicionar funcionários de fora da sua organização, preencha manualmente seus emails e outras informações.

    > [!NOTE]
    > A equipe de fora do seu locatário não poderá compartilhar informações de livre/ocupado com o Bookings.

5. Para cada membro da equipe, selecione uma função: Administrador, Visualizador ou Convidado.
    - **Os administradores** podem editar todas as configurações, adicionar e remover funcionários e criar, editar ou excluir reservas.
    - **Os** visualizadores podem ver todas as reservas no calendário, mas não podem modificá-las ou excluí-las. Eles têm acesso somente leitura às configurações.
    - **Os** convidados podem ser atribuídos a reservas, mas não podem abrir a caixa de correio de reserva.

6. Selecione **Notificar toda a equipe por email quando uma reserva** atribuída a eles for criada ou alterada para habilitar emails da equipe. Veja a seguir um exemplo de email:

    :::image type="content" source="media/bookings-notify-all-email.jpg" alt-text="Um email de notificação do Bookings":::

7. Selecione **Eventos no Office 365 calendário** afetarão a disponibilidade se você quiser que as informações de disponibilidade dos calendários dos membros da equipe afetem a disponibilidade dos serviços de reserva por meio do Bookings.

    Por exemplo, se um membro da equipe tiver uma reunião de equipe ou um compromisso pessoal agendado para 15h de uma quarta-feira, o Bookings mostrará que o membro da equipe não está disponível para ser reservado nesse intervalo de tempo. Esse tempo aparecerá como ocupado ou provisório na exibição de calendário do Bookings, conforme mostrado no exemplo a seguir.

    :::image type="content" source="media/bookings-busy-tentative-view.jpg" alt-text="Uma exibição de um calendário do Bookings":::

> [!IMPORTANT]
> É altamente recomendável deixar essa configuração em (ela está 100% ativas por padrão) para evitar reservas duplas e otimizar a disponibilidade de seus membros da equipe.

8. Selecione **Usar o horário comercial** para definir todos os horários reservados para que seus membros da equipe sejam apenas dentro do horário comercial definido na seção **Horário** Comercial na página Informações Comerciais.

    Ao desmarcar essa caixa, a equipe pode receber horários personalizados que limitam ainda mais quando podem ser reservados. Isso é útil para cenários em que um membro da equipe pode estar apenas nas terças e quartas-feiras do site, ou dedica suas manhãs para um tipo de compromissos e suas tardes para outros tipos.

    > [!NOTE]
    > Somente os primeiros 31 membros da equipe que você adicionar à sua página de equipe serão exibidos quando você atribuir membros da equipe a um serviço.

## <a name="make-a-bookings-user-a-super-user-without-adding-them-as-staff-in-bookings"></a>Tornar um usuário do Bookings um super usuário sem adiá-los como Funcionários no Bookings

Talvez você queira adicionar uma pessoa à sua lista de funcionários no Bookings sem disponibilizar para clientes ou clientes. Depois de torná-los um super usuário, eles se tornarão administradores da caixa de correio de reserva. Ser um administrador de uma caixa de correio de reserva é definido como tendo acesso total e permissões de envio à caixa de correio de reserva.

> [!NOTE]
> Essas etapas só funcionam se o usuário que está sendo adicionado ainda não tiver atribuído **uma** função de visualizador no Bookings.

1. [Conexão para Microsoft 365 com o PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

2. Usando o PowerShell, atribua acesso total aos seguintes comandos:

    ```powershell
    Add-MailboxPermission -Identity <bookingmailbox@emailaddress> -User <adminusers@emailaddress> -AccessRights FullAccess -Deny:$false
    ```

3. Em seguida, execute este comando para atribuir permissões de envio como.

    ```powershell
    Add-RecipientPermission -Identity <bookingmailbox@emailaddress> -Trustee <adminusers@emailaddress> -AccessRights SendAs -Confirm:$false
    ```

Veja um exemplo de comando do PowerShell para adicionar Allie Bellew à caixa de correio de reserva de daycare da Contoso.

1. Primeiro execute este comando:

    ```powershell
    Add-MailboxPermission -Identity "daycare@contoso.com" -User "Allie Bellew" -AccessRights FullAccess -InheritanceType All
    ```

2. Em seguida, execute este comando:

    ```powershell
    Add-RecipientPermission -Identity <bookingmailbox@emailaddress> -Trustee <adminusers@emailaddress> -AccessRights SendAs -Confirm:$false
    ```

**Allie Bellew** agora tem acesso ao administrador, mas não aparece como funcionário reservado no Bookings.
