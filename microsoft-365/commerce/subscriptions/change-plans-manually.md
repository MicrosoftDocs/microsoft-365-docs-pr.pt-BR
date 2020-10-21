---
title: Alterar manualmente os planos do Microsoft 365 for Business
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ROBOTS: NOINDEX
description: Altere as assinaturas manualmente, comprando uma nova assinatura e garantindo que ambas as assinaturas estejam listadas e ativas.
ms.openlocfilehash: 09557b3556db1e6f17d7a4cd54a88ba34d0f0bd7
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48647814"
---
# <a name="change-plans-manually"></a>Alterar planos manualmente

## <a name="step-1-decide-how-to-change-plans"></a>Etapa 1: decidir como alterar planos

A melhor maneira de alterar todos os usuários de um plano para outro é [usar a guia atualização](upgrade-to-different-plan.md). Às vezes, isso não é possível. Altere os planos manualmente em vez disso:

- Se a guia **atualização** indicar que você não pode atualizar o plano atual.

- Se, ao selecionar a guia **atualização** , o plano que você deseja não estiver listado.

- Se você não quiser atualizar todos os seus usuários da mesma maneira. Algumas empresas precisam de diferentes usuários inscritos em diferentes planos. Use uma alteração manual para isso.

Para continuar com uma alteração manual, leia [a etapa 2: comprar uma nova assinatura](#step-2-buy-a-new-subscription) neste tópico.

> [!IMPORTANT]
> Se você estiver mudando para um plano com menos serviços relacionados a dados do que o plano atual (downgrade), será necessário fazer backup manual de todos os dados que você deseja manter. Para obter mais informações, consulte [backup de dados antes de mudar de planos](back-up-data-before-switching-plans.md).

## <a name="step-2-buy-a-new-subscription"></a>Etapa 2: comprar uma nova assinatura

**Já comprou?** Se você já tem uma assinatura para a qual deseja mover os usuários, pule esta etapa e vá para a [etapa 3: Verifique sua nova assinatura e licenças](#step-3-check-your-new-subscription-and-licenses) neste tópico.

OU

**Adquira uma nova assinatura e licenças:** Siga as etapas em [comprar outra assinatura do Microsoft 365 for Business](../buy-another-subscription.md) para comprar uma nova assinatura.

Certifique-se de comprar uma assinatura para a mesma organização em que os usuários estão agora. Por exemplo, verifique os endereços de email dos usuários que você deseja mover. Se seus endereços de email incluírem \@ contoso.com, você deverá adquirir uma nova assinatura para o contoso.com.
Inclua uma licença para cada usuário que você deseja mover.

## <a name="step-3-check-your-new-subscription-and-licenses"></a>Etapa 3: verificar sua nova assinatura e licenças

1. No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.

2. **Verificar se as duas assinaturas estão listadas e ativas** A assinatura da qual você está migrando usuários e a assinatura à qual você está movendo usuários devem estar listadas em conjunto. Se a nova assinatura não estiver quando você verificar pela primeira vez, tente novamente mais tarde. Verifique se ambas as assinaturas estão ativas. [A nova assinatura não está listada ou não está ativa](#the-new-subscription-isnt-listed-or-isnt-active).

3. **Verifique se você tem licenças suficientes para cada usuário** Cada usuário precisa de uma licença que corresponda à sua assinatura. Portanto, se você quiser mover dez usuários para o Microsoft 365 Business Premium, será necessário garantir que dez licenças estejam disponíveis.

4. **Precisa de mais licenças para a nova assinatura?**
   Vá para a página **produtos** e [compre mais licenças](../licenses/buy-licenses.md).

> [E as licenças antigas?](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a>A nova assinatura não está listada ou não está ativa

- **Se você comprou duas assinaturas e elas não estão listadas aqui**, elas podem ter sido adquiridas para diferentes organizações (para diferentes domínios). As assinaturas não podem atravessar os limites da organização.

- **Se você souber que tem uma assinatura adicional**e ela não estiver listada aqui ou não estiver ativa, [ligue para o suporte da Microsoft](../../admin/contact-support-for-business-products.md).

### <a name="what-about-the-old-licenses"></a>E as licenças antigas?

As licenças para a assinatura atual serão removidas mais tarde; Você só pagará pelas novas licenças de usuário de então em diante.

## <a name="step-4-reassign-licenses"></a>Etapa 4: Reatribuir licenças

### <a name="reassign-a-license-for-one-user"></a>Reatribuir uma licença para um usuário

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

2. Na página **usuários ativos** , selecione o usuário ao qual você deseja atribuir uma licença.

3. Na guia de **licenças e aplicativos** , expanda **licenças**, selecione as caixas para as licenças que você deseja atribuir e, em seguida, selecione **salvar alterações**.

### <a name="reassign-licenses-for-multiple-users-at-once"></a>Reatribuir licenças para vários usuários de uma só vez

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

2. Selecione os círculos ao lado dos nomes dos usuários para os quais você deseja substituir as licenças existentes.

3. Na parte superior, selecione **mais opções** (**...**) e, em seguida, escolha **gerenciar licenças de produto**.

4. Selecione **Substituir atribuições de licença de produto existentes** \> **Avançar**.

5. Alterne o botão de alternância para a posição **ativado** dos produtos que você deseja atribuir a esses usuários.

    > [!TIP]
    > - Para limitar quais serviços estão disponíveis para o usuário, mude para alternar para a posição **desativado** dos serviços que você deseja remover para esse usuário. Por exemplo, se você deseja que o usuário tenha acesso a todos os serviços disponíveis, exceto o Skype for Business Online, você pode alterar o recurso de alternância para o serviço Skype for Business online para a posição **desativado** .
    > - Atribuições de licença para os usuários selecionados que tenham sido feitas anteriormente serão removidas.

6. Na parte inferior do painel **Substituir produtos existentes**, selecione **Substituir** \> **Fechar**.

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a>Etapa 5: cancelar assinaturas ou remover licenças que não são mais necessárias (opcional)

Se você moveu todos os usuários de uma assinatura para outra e não precisa mais da assinatura original, você pode [cancelar a assinatura](cancel-your-subscription.md).

Se você moveu apenas alguns usuários para uma assinatura diferente, [remova as licenças](../licenses/remove-licenses-from-subscription.md) que não são mais necessárias.

## <a name="call-support-to-help-you-change-plans"></a>Ligar para o suporte para ajudá-lo a alterar planos
[Chamar o suporte da Microsoft](../../admin/contact-support-for-business-products.md)