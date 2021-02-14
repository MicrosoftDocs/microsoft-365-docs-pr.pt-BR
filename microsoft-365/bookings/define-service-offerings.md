---
title: Definir suas ofertas de serviço no Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 4a1c391e-524f-48e0-bef8-185df3a9634b
description: Instruções para inserir informações de ofertas de serviço, incluindo nome do serviço, descrição, local, duração e preço. Você também pode marcar os funcionários qualificados para fornecer o serviço.
ms.openlocfilehash: 095188546c01149a793a478a3cbd5ac9fbeb5524
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962532"
---
# <a name="define-your-service-offerings-in-bookings"></a>Definir suas ofertas de serviço no Bookings

Ao definir suas ofertas de serviço no Microsoft Bookings, você define, um nome de serviço, uma descrição, um local (escolha se deseja se reunir pessoalmente ou se tem uma reunião online), duração, lembretes padrão para clientes e funcionários, anotações internas sobre o serviço e preços. Você também pode marcar os funcionários qualificados para fornecer o serviço. Em seguida, quando os clientes vêm ao seu site de negócios para agendar um compromisso, eles podem ver exatamente quais tipos de compromissos estão disponíveis, escolher a pessoa que eles querem fornecer o serviço e quanto o serviço vai custar.

Você também pode adicionar informações personalizadas e URLs à confirmação de email e lembretes que você envia quando alguém reserva um serviço por meio de sua página de reserva.

## <a name="create-the-service-details"></a>Criar os detalhes do serviço

1. Vá para a [página Gerenciar serviços e](https://outlook.office.com/bookings/services) selecione Adicionar um **serviço.**

2. **Nome do** serviço: insira o nome do seu serviço. Esse é o nome que aparecerá no menu suspenso na página Calendário. Esse nome também aparecerá quando qualquer pessoa adiciona manualmente um compromisso na página Calendário, e ele aparecerá como um tile na página Autoatendir.

3. **Descrição:** a descrição que você inserir será exibida quando um usuário clicar no ícone de informação na página Autoatendir.

4. **Local padrão:** esse local é o que será exibido nos emails de confirmação e lembrete para funcionários e clientes, e ele será exibido no evento de calendário criado para a reserva.

5. **Adicionar reunião online:** essa configuração habilita ou desabilita reuniões online para cada compromisso, seja por meio do Teams ou do Skype, dependendo de qual você configurar como o cliente padrão para o membro da equipe.

    - Habilitado:

        - Um link para uma reunião do Teams ou do Skype, exclusivo da reserva, será adicionado ao evento do calendário nos calendários da equipe e dos clientes, juntamente com as informações de discagem.
        - O link para ingressar na reunião será adicionado a todos os emails de confirmação e lembrete, conforme mostrado no exemplo a seguir:

        :::image type="content" source="media/bookings-teams-meeting-link.jpg" alt-text="Exemplo de link para ingressar em uma reunião do Teams no Bookings":::

        > [!NOTE]
        > As reuniões do Teams podem ser ingressáveis por meio do aplicativo móvel do Teams, do aplicativo da área de trabalho do Teams, em um navegador da Web ou por meio da discagem por telefone. É fortemente recomendável ativar o Teams como o serviço de reunião online padrão para seu locatário, para a melhor experiência de reserva de compromissos virtuais.

    - Desabilitado:
        - Os compromissos não conterão uma opção de reunião, e todos os campos relacionados à reunião que aparecem quando Adicionar reunião **online** está habilitada não serão mostrados.

6. **Duração** padrão: é por quanto tempo todas as reuniões serão reservadas. A hora é bloqueada a partir da hora de início, que é selecionada durante a reserva. O horário completo do compromisso será bloqueado nos calendários da equipe.

7. **Tempo de buffer que seu** cliente não pode reservar: habilizar essa configuração permite a adição de tempo extra ao calendário da equipe sempre que um compromisso é reservado.

    O tempo será bloqueado no calendário da equipe e afetará as informações de livre/ocupado. Isso significa que se um compromisso terminar às 15:00 e 10 minutos de tempo de buffer tiver sido adicionado ao final da reunião, o calendário da equipe será mostrar como ocupado e não reservado até 15:10. Isso pode ser útil se sua equipe precisar de tempo antes de uma reunião para se preparar, como um reviso no gráfico de um paciente ou um consultor financeiro preparando informações relevantes da conta. Também pode ser útil após uma reunião, como quando alguém precisa de tempo para se deslocar para outro local.

8. **Permitir que** o cliente gerencie sua reserva: essa configuração determina se o cliente pode ou não modificar ou cancelar sua reserva, desde que ele foi reservado por meio da guia Calendário no aplicativo Web do Bookings.

    - Habilitado:

        O **botão Gerenciar Reserva** aparece no email de confirmação do cliente. Quando esse botão é selecionado pelo cliente, três opções são exibidas:
        - **Reagendar** Selecionar essa opção leva o usuário a uma página de Self-Service específica do serviço, onde ele pode selecionar uma nova hora e/ou data para o mesmo serviço e o mesmo membro da equipe na reserva original. Observe que, embora o membro da equipe original seja anexado à reserva reagendada por padrão, o usuário também tem a opção de alterar o membro da equipe.
        - **Cancelar reserva** Isso cancela a reserva e a remove do calendário da equipe.
        - **Nova reserva** Essa opção leva o usuário para a página de Self-Service com todos os serviços e funcionários listados, para agendar uma nova reserva.

        :::image type="content" source="media/bookings-manage-booking-button.jpg" alt-text="O botão Gerenciar Reservas no Bookings":::

        Só recomendamos deixar essa configuração habilitada se você estiver confortável com os clientes acessando a Self-Service página.

    - Desabilitado:

        O usuário não poderá reagendar ou cancelar sua reserva ao agendar por meio da guia Calendário no aplicativo Web do Bookings. Ao fazer reservas por meio da Self-Service, no  entanto, os clientes ainda terão o botão Gerenciar Reserva e todas as suas opções, mesmo quando essa configuração estiver desabilitada.

        Recomendamos desabilitar essa configuração se você quiser limitar o acesso à Self-Service página. Além disso, sugerimos adicionar texto aos seus emails de confirmação e lembrete que informam aos clientes como fazer alterações na reserva por outros meios, como ligar para o escritório ou enviar um email para o help desk.

9. **Máximo de participantes por evento** Essa configuração permite que você crie serviços que exigem a capacidade de várias pessoas agendar o mesmo horário de compromisso e a mesma equipe (como uma aula de fitness). O intervalo de tempo do compromisso para o serviço, a equipe e a hora selecionados estarão disponíveis para reserva até que o número máximo de participantes, especificado por você, seja atingido. A capacidade atual do compromisso e os participantes podem ser exibidos na guia Calendário no aplicativo Web do Bookings.

    :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="Exemplo de configuração do máximo de participantes no Bookings":::

10. **Preço padrão**  Esse é o preço que será exibido na Self-Service página. Se **Preço não definido** estiver selecionado, nenhum preço ou referência para custo ou preço será exibido.

11. **Observações** Esse campo aparece no evento de reserva da equipe reservada, bem como no evento que aparece na guia Calendário no aplicativo Web do Bookings.

12. **Campos personalizados** Esta seção permite que perguntas sejam adicionadas ou removidas se o cliente precisar responder a qualquer uma para agendar com êxito.

    - Email do cliente, número de telefone, endereço e anotações são campos não removíveis, mas você pode torná-los opcionais desmarcando Obrigatório **ao** lado de cada campo.

    - Você pode adicionar uma pergunta de múltipla escolha ou resposta de texto **selecionando Adicionar uma pergunta.**

        Os campos personalizados podem ser úteis ao coletar informações necessárias sempre que o compromisso específico é reservado. Os exemplos incluem o provedor de seguros antes de uma visita a um candidato, o tipo de empréstimo para consultas de empréstimo, o principal estudo de consultoria acadêmica ou ID de candidato para entrevistas de candidatos.

13. **Lembretes e confirmações** Ambos os tipos de emails são enviados para clientes, membros da equipe ou ambos, em um período de tempo especificado antes do compromisso. Várias mensagens podem ser criadas para cada compromisso, de acordo com sua preferência.

    - Os emails de confirmação e lembrete padrão incluem informações básicas sobre o compromisso, como o nome do cliente/cliente, o nome do membro da equipe, o serviço ou compromisso agendado e a hora do compromisso. Para reuniões online, um link para ingressar também será incluído. A capacidade de gerenciar a reserva também pode ser incluída, se essa configuração estiver habilitada (conforme descrito acima na etapa 8).

        :::image type="content" source="media/bookings-remind-confirm.jpg" alt-text="Um email de confirmação do Bookings":::

    - Opcionalmente, você pode incluir qualquer texto adicional que quiser aqui, como informações sobre o reagendamento ou o que os clientes devem trazer para o compromisso. Veja a seguir um exemplo de texto personalizado adicionado ao email de confirmação original, visto nas informações adicionais do **campo Confirmação de Email:**

        :::image type="content" source="media/bookings-additional-info.jpg" alt-text="Informações adicionais em um email do Bookings":::

14. **Habilitar notificações de mensagem de texto para seu cliente** Se selecionada, as mensagens SMS serão enviadas para o cliente, mas somente se eles optarem por isso.

    - Caixa de aceitação na página de reserva e Self-Service manual:

        :::image type="content" source="media/bookings-opt-In-boc.jpg" alt-text="A caixa de aceitação no Bookings":::

    - As notificações de mensagem de texto terão a seguinte aparência (observe que as notificações de SMS estão atualmente disponíveis apenas na América do Norte):

        :::image type="content" source="media/bookings-text-notifications.jpg" alt-text="Uma notificação de texto do Bookings":::

15. **Opções de publicação** Escolha se esse serviço deve ser exibido como bookable na página Self-Service ou para torná-lo a ser reservado somente na guia Calendário no aplicativo Web do Bookings.

16. **Política de Agendamento** Esta configuração determina como os horários dos compromissos são exibidos e o período no qual as reservas podem ser feitas ou canceladas.

17. **Notificações por email** Define quando os emails são enviados para a equipe da organização e para clientes ou clientes.

18. **Equipe** Marcar essa caixa de seleção permite que clientes ou clientes escolham um determinado membro da equipe para seu compromisso.

    - Habilitado:

        Os clientes podem escolher entre todas as equipes atribuídas ao compromisso ao agendar na Self-Service página. Selecionar a opção Qualquer **Pessoa** fará com que o Bookings escolha um membro da equipe disponível aleatoriamente para atribuir ao compromisso.

    - Desabilitado:

        Os clientes reservando por meio Self-Service página podem selecionar um serviço e uma hora e data. A equipe disponível será reservada aleatoriamente. Observe que funcionários específicos ainda podem ser selecionados quando reservados por meio da guia Calendário no aplicativo Web do Bookings.

19. **Disponibilidade** As opções a seguir determinam quando o serviço pode ser reservado:

    - **Bookable when staff are free** O serviço mantém a disponibilidade com base em quando os funcionários estão livres no horário comercial, sem restrições de tempo extra.

    - **Horas personalizadas (recorrente semanalmente)** O serviço tem uma camada adicional de disponibilidade que pode ser ainda mais restrita (além de restringir por horário comercial ou com horário de equipe). Use essa opção quando seu serviço só puder ser fornecido ou executado em um horário específico.

    - **Definir disponibilidade diferente para um intervalo de datas** Essa configuração afeta a disponibilidade em um momento específico, em vez de uma base recorrente. Por exemplo, isso pode ser usado quando um computador necessário para o serviço está temporariamente sendo atendido e indisponível, ou quando uma organização está fechada para um feriado.

20. **Atribuir Equipe** Selecione a equipe (desde que você tenha adicionado membros da equipe à guia Funcionários) que será reservado para esse serviço específico. Selecionar nenhuma equipe individual fará com que toda a equipe seja atribuída ao serviço.