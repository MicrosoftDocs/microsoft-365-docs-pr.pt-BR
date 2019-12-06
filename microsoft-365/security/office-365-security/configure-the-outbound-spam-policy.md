---
title: Configurar a política de spam de saída
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: A filtragem de spam de saída está sempre habilitada se você utilizar o serviço de envio de email de saída, protegendo assim as organizações que utilizam o serviço e seus destinatários desejados.
ms.openlocfilehash: baf6999923a4c4cf346915800b8f97a0d0378f58
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871907"
---
# <a name="configure-the-outbound-spam-policy"></a>Configurar a política de spam de saída

A filtragem de spam de saída está sempre habilitada se você utilizar o serviço de envio de email de saída, protegendo assim as organizações que utilizam o serviço e seus destinatários desejados. Semelhante à filtragem de entrada, a filtragem de spam de saída é composta por filtragem de conexão e filtragem de conteúdo e permite que alguns controles específicos manipulem mensagens de saída. Tipos de configurações de política de filtro de spam de saída:

- Padrão: a política de filtro de spam de saída padrão é usada para definir configurações de filtro de spam de saída para toda a empresa. Essa política não pode ser renomeada e está sempre ativa.

- Personalizado: as políticas de filtro de spam de saída personalizadas podem ser detalhadas e aplicadas a usuários, grupos ou domínios específicos em sua organização. As políticas personalizadas sempre têm precedência sobre a política padrão. Você pode alterar a ordem na qual suas políticas personalizadas são executadas, alterando a prioridade de cada política personalizada; no entanto, somente a política de maior prioridade (ou seja, número mais próximo a 0) será aplicada se o usuário corresponder a várias políticas.

> [!NOTE]
> Para obter mais informações sobre os [controles de spam de saída no Office 365](https://docs.microsoft.com/office365/securitycompliance/outbound-spam-controls). <br><br> As atualizações da política de spam de saída estão sendo distribuídas atualmente, com a atualização esperada concluída no final de outubro de 2019. Durante esse tempo, algumas opções podem não estar disponíveis.  Para obter mais informações, consulte [Office 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?featureid=54125) 

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?
<a name="sectionSection0"> </a>

Tempo estimado para conclusão: 5 minutos

Para executar este procedimento ou estes procedimentos, você precisa receber permissões. Para ver quais são as permissões necessárias, confira a Entrada antispam, no tópico [Permissões de recursos no Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions).

O procedimento a seguir também pode ser realizado pelo PowerShell remoto. Use o cmdlet [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy) para analisar suas configurações e o cmdlet [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy) para editar as configurações de política de spam de saída. Para saber como usar o Windows PowerShell para se conectar à Proteção do Exchange Online, confira [Conectar-se ao PowerShell do Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkid=627290). Para saber como usar o Windows PowerShell para se conectar ao Exchange Online, confira o artigo [Conectar-se ao Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

## <a name="use-the-security-and-compliance-center-scc-to-edit-the-default-outbound-spam-policy"></a>Usar o centro de conformidade e segurança (SCC) para editar a política de spam de saída padrão

Utilize o procedimento a seguir para editar a política de spam de saída padrão.

### <a name="to-configure-the-default-outbound-spam-policy"></a>Para configurar a política de spam de saída padrão.

1. No SCC, navegue até **anti-spam** da **política** \> de **Gerenciamento** \> de ameaças

2. Expanda a seção **política de filtro de spam de saída (AlwaysOn)** e clique em **Editar política**.

3. Expanda a seção **notificações** e marque as seguintes caixas de seleção referentes a mensagens de saída e, em seguida, selecione **adicionar pessoas** para adicionar um endereço de email ou endereços associados na caixa de diálogo que o acompanha. (elas podem ser listas de distribuição se resolverem como destinos SMTP válidos):

   - **Envie uma cópia de todas as mensagens de email de saída suspeitas para o endereço ou endereços de email a seguir**: são mensagens marcadas como spam pelo filtro (independentemente da classificação de SCL). Eles não são rejeitados pelo filtro, mas são roteados através do pool de entrega de risco mais alto. Separe com ponto e vírgula os diversos endereços. Observe que os destinatários especificados receberão as mensagens como um Endereço CCO (com cópia oculta) (os campos de e para são o remetente e o destinatário originais).

   - **Envie uma notificação para o seguinte endereço de email quando um remetente estiver bloqueado enviando spam de saída**: Separe vários endereços com ponto e vírgula.

   Quando uma quantidade significativa de spam ou outras anomalias de envio são detectadas de um usuário específico, o usuário está restrito a enviar mensagens de email e uma notificação é enviada para os endereços de email especificados.

   O administrador para o domínio, especificado usando esta configuração, será informado de que as mensagens de saída estão bloqueadas para este usuário.  Para ver a aparência dessa notificação, confira [exemplo de notificação quando um remetente estiver bloqueado enviando spam de saída](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md).

   [Observação!] Um alerta do sistema também é gerado, indicando que o usuário foi restringido.  Para saber mais sobre o alerta e como recuperar o usuário, confira [remover um usuário do portal de usuários restritos depois de enviar email de spam](removing-user-from-restricted-users-portal-after-spam.md).

4. Expanda a seção **limites de destinatário** para especificar o número máximo de destinatários que um usuário pode enviar, por hora, para destinatários internos e externos junto com o número máximo por dia.

    [Observação!] O número máximo de qualquer entrada é 10.000.  Para obter mais informações [, consulte recebendo e enviando limites no Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)

7. Especifique a **ação** a ser tomada quando um usuário exceder os limites especificados.  As ações possíveis são as seguintes:
    * **Impedir que o usuário envie email até o dia seguinte**.  Após o limite de envio ter sido excedido (interno, externo ou diário) um alerta será gerado para o administrador e o usuário não poderá enviar mais emails até o dia seguinte, com base na hora UTC. Não há como o administrador substituir esse bloco.

    * **Impedir que o usuário envie emails**.  Após o limite de envio ter sido excedido (interno, externo ou diário) um alerta será gerado para o administrador e o usuário não poderá enviar mais emails até que o administrador remova a restrição.  Nesses casos, o usuário será listado na [página usuários restritos](removing-user-from-restricted-users-portal-after-spam.md).  Após a remoção da lista, o usuário não será restringido novamente nesse dia.

    * **Sem ação/alerta apenas**. Após o limite de envio ter sido excedido (interno, externo ou diário) um alerta será gerado para o administrador, mas nenhuma ação será tomada para restringir o usuário.

6. Expanda a seção **aplica-se a** e crie uma regra baseada em condição para especificar os usuários, grupos e domínios aos quais aplicar essa política. É possível criar várias condições, se elas forem únicas.  Observação: os usuários devem atender a todas as condições quando várias condições forem especificadas.  

      * Para selecionar usuários, selecione **o remetente é**. Na caixa de diálogo subsequente, selecione um ou mais remetentes da sua empresa na lista de seletor de usuários e então clique em adicionar. Para adicionar remetentes que não estão na lista, digite os seus endereços de email e então clique em Verificar nomes. Ao finalizar suas seleções, clique em ok para retornar a tela principal.

      * Para selecionar grupos, selecione **o remetente é um membro**. Em seguida, na caixa de diálogo posterior, selecione ou especifique os grupos. Clique em ok para retornar à tela principal.

      * Para selecionar domínios, selecione **o domínio do remetente**. Em seguida, na caixa de diálogo posterior, adicione os domínios. Clique em ok para retornar à tela principal.

        Você pode criar exceções dentro da regra. Por exemplo, você pode filtrar mensagens de todos os domínios, exceto para um determinado domínio. Clique em Adicionar exceção e, em seguida, crie suas condições de exceção da mesma forma que criou as demais condições.

        A aplicação de uma política de spam de saída a um grupo só é suportada para grupos de segurança habilitados para email.

7. Clique em **salvar**.

## <a name="to-create-a-custom-policy-for-a-specific-set-of-users"></a>Para criar uma política personalizada para um conjunto específico de usuários
1. No SCC, navegue até **anti-spam** da **política** \> de **Gerenciamento** \> de ameaças

2. Clique no botão **criar uma política de saída** .

3. Expanda a seção **notificações** e marque as seguintes caixas de seleção referentes a mensagens de saída e, em seguida, selecione **adicionar pessoas** para adicionar um endereço de email ou endereços associados na caixa de diálogo que o acompanha.

4. Expanda a seção **limites do destinatário** para especificar o número máximo de destinatários que um usuário pode enviar, por hora, para destinatários internos e externos e o número máximo por dia.

7. Especifique a **ação** a ser tomada quando um usuário exceder os limites especificados.

6. Expanda a seção **aplica-se a** e crie uma regra baseada em condição para especificar os usuários, grupos e domínios aos quais aplicar essa política. É possível criar várias condições, se elas forem únicas.  

8. Clique em **salvar**

## <a name="for-more-information"></a>Para saber mais

[Remoção de um usuário do portal de Usuários Restritos após o envio de email de spam](https://docs.microsoft.com/office365/SecurityCompliance/removing-user-from-restricted-users-portal-after-spam)

[Pool de entrega de alto risco para mensagens de saída](high-risk-delivery-pool-for-outbound-messages.md)

[Perguntas frequentes sobre a proteção antispam](anti-spam-protection-faq.md)
