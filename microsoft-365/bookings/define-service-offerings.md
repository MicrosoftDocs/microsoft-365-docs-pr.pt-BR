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
description: Instruções para inserir informações de ofertas de serviço, incluindo nome do serviço, descrição, local, duração e preços. Você também pode marcar os funcionários qualificados para fornecer o serviço.
ms.openlocfilehash: 095188546c01149a793a478a3cbd5ac9fbeb5524
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962532"
---
# <a name="define-your-service-offerings-in-bookings"></a>Definir suas ofertas de serviço no Bookings

Ao definir suas ofertas de serviço no Microsoft Bookings, você define um nome de serviço, descrição, local (escolha se deseja se reunir pessoalmente ou ter uma reunião online), duração, lembretes padrão para clientes e funcionários, anotações internas sobre o serviço e preços. Você também pode marcar os funcionários qualificados para fornecer o serviço. Em seguida, quando os clientes chegam ao site da sua empresa para agendar um compromisso, eles podem ver exatamente quais tipos de compromissos estão disponíveis, escolher a pessoa que deseja fornecer o serviço e quanto o serviço vai custar.

Você também pode adicionar informações personalizadas e URLs à confirmação de email e lembretes que você envia quando alguém agenda um serviço por meio de sua página de reserva.

## <a name="create-the-service-details"></a>Criar os detalhes do serviço

1. Vá para a [página Gerenciar serviços e](https://outlook.office.com/bookings/services) selecione Adicionar um **serviço**.

2. **Nome do** serviço : insira o nome do seu serviço. Esse é o nome que aparecerá no menu suspenso na página Calendário. Esse nome também aparecerá quando qualquer pessoa adiciona manualmente um compromisso na página Calendário e ele aparecerá como um azulejo na página Autoatendir.

3. **Descrição**: a descrição que você inserir é o que aparecerá quando um usuário clicar no ícone de informações na página Autoatendados.

4. **Local padrão**: esse local é o que será exibido nos emails de confirmação e lembrete para funcionários e clientes, e ele será exibido no evento de calendário criado para a reserva.

5. **Adicionar reunião online**: essa configuração habilita ou desabilita reuniões online para cada compromisso, por meio de Teams ou Skype, dependendo de qual você configurar como o cliente padrão para o membro da equipe.

    - Habilitado:

        - Um link para uma reunião de Teams ou Skype, exclusivo da reserva, será adicionado ao evento de calendário nos calendários da equipe e dos clientes, juntamente com informações de discagem.
        - O link para ingressar na reunião será adicionado a todos os emails de confirmação e lembrete, conforme mostrado no exemplo a seguir:

        :::image type="content" source="media/bookings-teams-meeting-link.jpg" alt-text="Exemplo de link para ingressar Teams reunião no Bookings":::

        > [!NOTE]
        > Teams reuniões podem ser ingressado por meio do aplicativo móvel Teams, o aplicativo de área de trabalho Teams, em um navegador da Web ou por meio do discagem telefônica. É recomendável habiligá-Teams como o serviço de reunião online padrão para seu locatário, para a melhor experiência de reserva de compromissos virtuais.

    - Desabilitado:
        - Os compromissos não conterão uma opção de reunião, e todos os campos relacionados à reunião que aparecem quando **Add online meeting** está habilitado não serão mostrados.

6. **Duração padrão**: é por quanto tempo todas as reuniões serão reservadas. A hora é bloqueada a partir da hora de início, que é selecionada durante a reserva. O horário completo do compromisso será bloqueado nos calendários da equipe.

7. **Tempo de buffer que o** cliente não pode reservar : Habilbilizar essa configuração permite a adição de tempo extra ao calendário da equipe sempre que um compromisso é reservado.

    O tempo será bloqueado no calendário da equipe e afetará as informações de livre/ocupado. Isso significa que, se um compromisso terminar às 15:00 e 10 minutos de tempo de buffer tiver sido adicionado ao final da reunião, o calendário da equipe mostrará como ocupado e não reservado até 15:10. Isso pode ser útil se sua equipe precisar de tempo antes de uma reunião para se preparar, como um médico que revisa o gráfico de um paciente ou um consultor financeiro preparando informações relevantes da conta. Também pode ser útil após uma reunião, como quando alguém precisa de tempo para viajar para outro local.

8. **Permitir que o** cliente gerencie sua reserva : Essa configuração determina se o cliente pode ou não modificar ou cancelar sua reserva, desde que ele foi reservado por meio da guia Calendário no aplicativo Web do Bookings.

    - Habilitado:

        O **botão Gerenciar Reserva** aparece no email de confirmação do cliente. Quando esse botão é selecionado pelo cliente, aparecem três opções:
        - **Reagendar** Selecionar essa opção leva o usuário a uma página de Self-Service específica do serviço, onde ele pode selecionar uma nova hora e/ou data para o mesmo serviço e o mesmo membro da equipe na reserva original. Observe que, mesmo que o membro da equipe original seja anexado à reserva reagendada por padrão, o usuário também tem a opção de alterar o membro da equipe.
        - **Cancelar reserva** Isso cancela a reserva e remove-a do calendário da equipe.
        - **Novo booking** Essa opção leva o usuário à página Self-Service com todos os serviços e funcionários listados, para agendar uma nova reserva.

        :::image type="content" source="media/bookings-manage-booking-button.jpg" alt-text="O botão Gerenciar Reservas no Bookings":::

        Só recomendamos deixar essa configuração habilitada se você estiver confortável com os clientes acessando a Self-Service página.

    - Desabilitado:

        O usuário não terá a capacidade de reagendar ou cancelar sua reserva ao reservar por meio da guia Calendário no aplicativo Web do Bookings. No entanto, ao fazer reserva na página Self-Service, os clientes ainda terão o botão **Gerenciar** Reserva e todas as opções, mesmo quando essa configuração estiver desabilitada.

        Recomendamos desabilitar essa configuração se você quiser limitar o acesso à Self-Service página. Além disso, sugerimos adicionar texto aos emails de confirmação e lembrete que informam aos clientes como fazer alterações na reserva por outros meios, como chamar o escritório ou enviar emails para o help desk.

9. **Máximo de participantes por evento** Essa configuração permite que você crie serviços que exigem a capacidade de várias pessoas agendar o mesmo horário de compromisso e a mesma equipe (como uma aula de fitness). O intervalo de tempo de compromisso para o serviço, equipe e hora selecionados estará disponível para reservar até que o número máximo de participantes, especificado por você, seja atingido. A capacidade atual de compromisso e os participantes podem ser exibidos na guia Calendário no aplicativo Web do Bookings.

    :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="Exemplo de configuração de participantes máximos no Bookings":::

10. **Preço padrão**  Esse é o preço que será exibido na página Self-Service. Se **Preço não definido** estiver selecionado, nenhum preço ou referência ao custo ou preço aparecerá.

11. **Observações** Esse campo aparece no evento de reserva para funcionários reservados, bem como no evento que aparece na guia Calendário no aplicativo Web do Bookings.

12. **Campos personalizados** Esta seção permite que as perguntas sejam adicionadas ou removidas se o cliente precisar responder a qualquer uma para reservar com êxito.

    - Email do cliente, número de telefone, endereço e anotações são campos não removíveis, mas você pode torná-los opcionais desmarcando **Obrigatório ao** lado de cada campo.

    - Você pode adicionar uma pergunta de múltipla escolha ou resposta de texto **selecionando Adicionar uma pergunta**.

        Campos personalizados podem ser úteis ao coletar informações necessárias sempre que o compromisso específico for reservado. Exemplos incluem provedor de seguros antes de uma visita de clínica, tipo de empréstimo para consultas de empréstimo, estudo principal para consultoria acadêmica ou ID de candidato para entrevistas de candidato.

13. **Lembretes e Confirmações** Ambos os tipos de emails são enviados para clientes, membros da equipe ou ambos, em um período de tempo especificado antes do compromisso. Várias mensagens podem ser criadas para cada compromisso, de acordo com sua preferência.

    - Os emails de confirmação e lembrete padrão incluem informações básicas sobre o compromisso, como o nome do cliente/cliente, o nome do membro da equipe, o serviço ou o compromisso reservado e a hora do compromisso. Para reuniões online, um link para ingressar também será incluído. A capacidade de gerenciar a reserva também pode ser incluída, se essa configuração estiver habilitada (conforme descrito acima na etapa 8).

        :::image type="content" source="media/bookings-remind-confirm.jpg" alt-text="Um email de confirmação do Bookings":::

    - Opcionalmente, você pode incluir qualquer texto adicional que você gostaria aqui, como informações sobre remarcação ou o que os clientes devem trazer para o compromisso. Veja a seguir um exemplo de texto personalizado adicionado ao email de confirmação original, visto no campo **Informações adicionais para** Confirmação de Email:

        :::image type="content" source="media/bookings-additional-info.jpg" alt-text="Informações adicionais em um email do Bookings":::

14. **Habilitar notificações de mensagem de texto para seu cliente** Se selecionado, SMS mensagens serão enviadas para o cliente, mas somente se eles optarem.

    - Caixa de aceitação na página de reserva e Self-Service manual:

        :::image type="content" source="media/bookings-opt-In-boc.jpg" alt-text="A caixa de aceitação no Bookings":::

    - As notificações de mensagem de texto terão a seguinte aparência (observe que as notificações SMS estão disponíveis atualmente apenas na América do Norte):

        :::image type="content" source="media/bookings-text-notifications.jpg" alt-text="Uma notificação de texto do Bookings":::

15. **Opções de publicação** Escolha se esse serviço deve ser exibido como reservado na página Self-Service ou para tornar o serviço reservado somente na guia Calendário no aplicativo Web do Bookings.

16. **Política de Agendamento** Essa configuração determina como os horários de compromisso são exibidos e o período em que as reservas podem ser feitas ou canceladas.

17. **Notificações por email** Define quando os emails são enviados para a equipe da organização e para clientes ou clientes.

18. **Equipe** Selecionar essa caixa de seleção permite que clientes ou clientes escolham um membro da equipe específico para seu compromisso.

    - Habilitado:

        Os clientes podem escolher entre todas as equipes atribuídas ao compromisso ao reservar na Self-Service página. Selecionar a opção de **Qualquer Pessoa** fará com que o Bookings escolha um membro da equipe disponível aleatoriamente para atribuir ao compromisso.

    - Desabilitado:

        Os clientes que reservam por meio Self-Service página podem selecionar um serviço e uma hora e uma data. A equipe disponível será reservada aleatoriamente. Observe que funcionários específicos ainda podem ser selecionados quando reservados por meio da guia Calendário no aplicativo Web do Bookings.

19. **Disponibilidade** As opções a seguir determinam quando o serviço pode ser reservado:

    - **Bookable when staff are free** O serviço mantém a disponibilidade com base em quando a equipe está livre no horário comercial, sem restrições de tempo extra.

    - **Horários personalizados (semanal recorrente)** O serviço tem uma camada adicional de disponibilidade que pode ser ainda mais restrita (além de restringir por horário comercial ou com horário de equipe). Use essa opção quando seu serviço só puder ser fornecido ou executado em um momento específico.

    - **Definir disponibilidade diferente para um intervalo de datas** Essa configuração afeta a disponibilidade em um ponto específico no tempo, em vez de uma base recorrente. Por exemplo, isso pode ser usado quando um computador necessário para o serviço está temporariamente sendo atendido e indisponível ou quando uma organização é fechada para um feriado.

20. **Atribuir Equipe** Selecione a equipe (desde que você tenha adicionado membros da equipe à guia Funcionários) que será reservada para esse serviço específico. Selecionar nenhuma equipe individual fará com que toda a equipe seja atribuída ao serviço.