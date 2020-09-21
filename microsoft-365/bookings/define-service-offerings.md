---
title: Definir suas ofertas de serviço em reservas
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 4a1c391e-524f-48e0-bef8-185df3a9634b
description: Instruções para inserir informações de ofertas de serviço, incluindo nome do serviço, descrição, local, duração e preços. Você também pode marcar os funcionários que estão qualificados para fornecer o serviço.
ms.openlocfilehash: 095188546c01149a793a478a3cbd5ac9fbeb5524
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962532"
---
# <a name="define-your-service-offerings-in-bookings"></a>Definir suas ofertas de serviço em reservas

Ao definir suas ofertas de serviço em Microsoft bookings, você define um nome de serviço, uma descrição, um local (escolha se você deseja se reunir em pessoa ou em uma reunião online), duração, lembretes padrão para clientes e funcionários, anotações internas sobre o serviço e preços. Você também pode marcar os funcionários que estão qualificados para fornecer o serviço. Em seguida, quando os clientes chegam ao seu site comercial para agendar um compromisso, eles podem ver exatamente quais tipos de compromissos estão disponíveis, escolher a pessoa que eles desejam fornecer o serviço e quanto seu serviço custará.

Você também pode adicionar informações personalizadas e URLs às confirmação de email e lembretes que você envia quando alguém manuais de um serviço por meio da página de reserva.

## <a name="create-the-service-details"></a>Criar os detalhes do serviço

1. Vá para a [página Gerenciar Serviços](https://outlook.office.com/bookings/services) e selecione **Adicionar um serviço**.

2. **Nome do serviço**: Insira o nome do serviço. Este é o nome que aparecerá no menu suspenso na página calendário. Esse nome também aparecerá quando alguém adicionar manualmente um compromisso na página calendário e será exibido como um bloco na página de autoatendimento.

3. **Descrição**: a descrição inserida é o que será exibido quando um usuário clicar no ícone de informações na página de autoatendimento.

4. **Local padrão**: esse local é o que será exibido nos emails de confirmação e de lembrete para a equipe e para os clientes, e ele será exibido no evento de calendário criado para a reserva.

5. **Adicionar reunião online**: essa configuração habilita ou desabilita reuniões online para cada compromisso, seja via Teams ou Skype, dependendo de qual deles você configura como o cliente padrão para o membro da equipe.

    - Permiti

        - Um link para uma reunião do Microsoft Teams ou do Skype, exclusivo da reserva, será adicionado ao evento de calendário nos calendários da equipe e dos clientes, juntamente com as informações de discagem.
        - O link para ingressar na reunião será adicionado a todos os emails de confirmação e de lembrete, conforme mostrado no exemplo a seguir:

        :::image type="content" source="media/bookings-teams-meeting-link.jpg" alt-text="Exemplo de link para ingressar na reunião do teams em reservas":::

        > [!NOTE]
        > As reuniões do teams podem ser unidas por meio do aplicativo móvel do Teams, do aplicativo da área de trabalho do Microsoft Teams, em um navegador da Web ou através da discagem telefônica. É altamente recomendável habilitar o Microsoft Teams como o serviço de reunião online padrão para o seu locatário, para a melhor experiência de reserva virtual de compromissos.

    - Deficiência
        - Os compromissos não conterá uma opção de reunião e todos os campos relacionados à reunião que aparecerem quando **Adicionar reunião online** não serão exibidos.

6. **Duração padrão**: por quanto tempo todas as reuniões serão agendadas. O horário é bloqueado a partir da hora de início, que é selecionada durante a reserva. O horário completo do compromisso será bloqueado nos calendários da equipe.

7. **Tempo do buffer que seu cliente não pode agendar**: habilitar essa configuração permite a adição de tempo adicional ao calendário da equipe sempre que um compromisso é registrado.

    O horário será bloqueado no calendário da equipe e afetará as informações de disponibilidade. Isso significa que, se um compromisso terminar às 3:00 p.m. e 10 minutos de tempo do buffer tiver sido adicionado ao final da reunião, o calendário da equipe aparecerá como ocupado e não poderá ser agendado até 3:10pm. Isso pode ser útil se sua equipe precisa de tempo antes de uma reunião ser preparada, como um médico examinando o gráfico de um paciente ou um conselheiro financeiro preparando informações de conta relevantes. Também pode ser útil após uma reunião, como quando alguém precisa de tempo para viajar para outro local.

8. **Permitir que o cliente Gerencie sua reserva**: esta configuração determina se o cliente pode ou não modificar ou cancelar sua reserva, desde que ele tenha sido registrado por meio da guia calendário no aplicativo Web de reservas.

    - Permiti

        O botão **gerenciar reserva** aparece no email de confirmação do cliente. Quando esse botão é selecionado pelo cliente, três opções são exibidas:
        - **Reagendar** Selecionar essa opção traz o usuário para uma página de autoatendimento específica de serviço, onde pode selecionar um novo horário e/ou data para o mesmo serviço e o mesmo membro da equipe da reserva original. Observe que, embora o membro da equipe original esteja anexado à reserva reagendada por padrão, o usuário também tem a opção de alterar o membro da equipe.
        - **Cancelar reserva** Isso cancela a reserva e o Remove do calendário da equipe.
        - **Nova reserva** Essa opção traz o usuário para a página de autoatendimento com todos os serviços e funcionários listados, para agendar uma nova reserva.

        :::image type="content" source="media/bookings-manage-booking-button.jpg" alt-text="O botão gerenciar reservas em reservas":::

        Só recomendamos que você deixe essa configuração habilitada se estiver familiarizado com clientes que acessam a página de autoatendimento.

    - Deficiência

        O usuário não terá capacidade de reagendar ou cancelar sua reserva quando fizer a trificação na guia Calendário do aplicativo Web de livros. Ao fazer o reservas através da página de autoatendimento, no entanto, os clientes ainda terão o botão **gerenciar reserva** e todas as suas opções, mesmo quando essa configuração estiver desabilitada.

        Recomendamos desabilitar essa configuração se quiser limitar o acesso à página de autoatendimento. Além disso, sugerimos adicionar texto a seus emails de confirmação e de lembrete que dizem aos seus clientes como fazer alterações em seus reservas por outros meios, como chamar o Office ou enviar o email para o help desk.

9. **Máximo de participantes por evento** Essa configuração permite que você crie serviços que exijam a capacidade de várias pessoas agendarem o mesmo horário de compromisso e a mesma equipe (como uma classe de aptidão). O intervalo de tempo do compromisso para o serviço, equipe e tempo selecionados estará disponível para o livro até que o número máximo de participantes, especificado por você, tenha sido alcançado. A capacidade e os participantes atuais do compromisso podem ser exibidos na guia Calendário do aplicativo Web de reservas.

    :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="Exemplo de configuração de máximo de participantes em reservas":::

10. **Preço padrão**  Este é o preço que será exibido na página de autoatendimento. Se o **preço não definido** for selecionado, nenhum preço ou referência ao custo ou ao preço será exibido.

11. **Anotações** Este campo é exibido no evento de reserva para a equipe registrada, bem como no evento que aparece na guia Calendário do aplicativo Web de reservas.

12. **Campos personalizados** Esta seção permite que as perguntas sejam adicionadas ou removidas, se o cliente precisa responder a qualquer um para o livro bem-sucedido.

    - O email do cliente, o número de telefone, o endereço e as anotações são campos não removíveis, mas você pode torná-los opcionais ao desmarcar **obrigatório** ao lado de cada campo.

    - Você pode adicionar uma pergunta de múltipla escolha ou resposta de texto selecionando **Adicionar uma pergunta**.

        Os campos personalizados podem ser úteis ao coletar informações necessárias sempre que o compromisso específico é registrado. Os exemplos incluem o provedor de seguros antes da visita de uma clínica, tipo de empréstimo para consultas de empréstimos, principal estudo para o Conselho acadêmico ou ID de candidato para entrevistas candidatas.

13. **Lembretes e confirmações** Os dois tipos de email são enviados para os clientes, membros da equipe ou ambos, em um período de tempo especificado antes do compromisso. Várias mensagens podem ser criadas para cada compromisso, de acordo com sua preferência.

    - Os emails de confirmação e de lembrete padrão incluem informações básicas sobre o compromisso, como o nome do cliente/cliente, o nome do membro da equipe, o serviço ou compromisso registrado e a hora do compromisso. Para reuniões online, um link para ingressar também será incluído. A capacidade de gerenciar a reserva também pode ser incluída, se essa configuração estiver habilitada (conforme descrito acima na etapa 8).

        :::image type="content" source="media/bookings-remind-confirm.jpg" alt-text="Um email de confirmação de reservas":::

    - Opcionalmente, você pode incluir qualquer texto adicional que desejar aqui, como informações sobre o reagendamento ou o que os clientes devem trazer para o compromisso. Veja a seguir um exemplo de texto personalizado adicionado ao email de confirmação original, visto nas **informações adicionais para o campo de confirmação de email** :

        :::image type="content" source="media/bookings-additional-info.jpg" alt-text="Informações adicionais em um email de reservas":::

14. **Habilitar notificações de mensagem de texto para o cliente** Se selecionado, as mensagens SMS serão enviadas para o cliente, mas apenas se optarem por eles.

    - Caixa de consentimento na página de reserva e autoatendimento manual:

        :::image type="content" source="media/bookings-opt-In-boc.jpg" alt-text="A caixa de adesão em reservas":::

    - As notificações de mensagem de texto terão a seguinte aparência (Observe que as notificações do SMS estão disponíveis atualmente apenas na América do Norte):

        :::image type="content" source="media/bookings-text-notifications.jpg" alt-text="Uma notificação de texto de reservas":::

15. **Opções de publicação** Escolha se deseja que esse serviço seja exibido como um registro em uma página de autoatendimento ou para tornar o serviço somente registro na guia Calendário do aplicativo Web de reservas.

16. **Política de agendamento** Essa configuração determina como os horários dos compromissos são exibidos e o período de tempo no qual as reservas podem ser feitas ou canceladas.

17. **Notificações por email** Define quando os emails são enviados para a equipe da organização e para clientes ou clientes.

18. **Equipe** Marcar essa caixa de seleção permite que clientes ou clientes escolham um membro da equipe específico para o compromisso.

    - Permiti

        Os clientes podem escolher entre todos os funcionários atribuídos ao compromisso ao fazer o reservas na página de autoatendimento. Selecionar a opção de **qualquer pessoa** fará com que os reservas escolham um membro da equipe disponível aleatoriamente para atribuir ao compromisso.

    - Deficiência

        Os clientes que estão reservando por meio da página de autoatendimento podem selecionar um serviço e uma data e hora. A equipe disponível será reservada aleatoriamente. Observe que a equipe específica ainda pode ser selecionada quando marcada por meio da guia calendário no aplicativo Web de reservas.

19. **Disponibilidade** As opções a seguir determinam quando o serviço pode ser reservado:

    - **Podem ser acessados quando a equipe estiver livre** O serviço mantém a disponibilidade com base em quando a equipe está livre no horário comercial, sem restrições de tempo extra.

    - **Horas personalizadas (recorrente semanal)** O serviço tem uma camada adicional de disponibilidade que pode ser mais restrita (além de restringir por horário comercial ou com horas da equipe). Use essa opção quando o serviço só puder ser fornecido ou executado em um momento específico.

    - **Definir disponibilidade diferente para um intervalo de datas** Essa configuração impacta a disponibilidade em um ponto específico no tempo, em vez de uma base recorrente. Por exemplo, isso pode ser usado quando uma máquina necessária para o serviço está temporariamente sendo atendida e indisponível, ou quando uma organização é fechada para um feriado.

20. **Atribuir equipe** Selecione a equipe (desde que você tenha adicionado membros da equipe à guia equipe) que poderão ser agendados para esse serviço específico. Selecionar nenhuma equipe individual fará com que todas as pessoas sejam atribuídas ao serviço.