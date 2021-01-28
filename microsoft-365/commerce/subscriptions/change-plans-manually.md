---
title: Alterar os planos do Microsoft 365 para empresas manualmente
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
description: Altere as assinaturas manualmente comprando uma nova assinatura e garantindo que ambas as assinaturas sejam listadas e ativas.
ms.openlocfilehash: 1127a48ff23c528e3218bae4ccfd063df5e3c26d
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029381"
---
# <a name="change-plans-manually"></a>Alterar planos manualmente

## <a name="step-1-decide-how-to-change-plans"></a>Etapa 1: Decidir como alterar os planos

A melhor maneira de alterar todos os usuários de um plano para outro é [usar a guia Atualização.](upgrade-to-different-plan.md) Às vezes, isso não é possível. Altere os planos manualmente em vez disso:

- Se a **guia** Atualização indicar que você não pode atualizar o plano atual.

- Se, ao selecionar a **guia Atualizar,** o plano que você deseja não estiver listado.

- Se você não quiser atualizar todos os usuários da mesma maneira. Algumas empresas precisam de diferentes usuários inscritos em planos diferentes. Use uma alteração manual para isso.

Para continuar com uma alteração manual, leia [a Etapa 2: Comprar uma nova assinatura](#step-2-buy-a-new-subscription) neste tópico.

> [!IMPORTANT]
> Se estiver mudando para um plano com menos serviços relacionados a dados do que o plano atual (downgrade), você precisará fazer o back up manualmente dos dados que deseja manter. Para obter mais informações, consulte [Fazer o back up de dados antes de alterar os planos.](back-up-data-before-switching-plans.md)

## <a name="step-2-buy-a-new-subscription"></a>Etapa 2: comprar uma nova assinatura

**Já comprou?** Se você já tiver uma assinatura para a quais deseja mover os usuários, pule esta etapa e vá para a Etapa [3:](#step-3-check-your-new-subscription-and-licenses) verificar sua nova assinatura e licenças neste tópico.

OU

**Compre uma nova assinatura e licenças:** Siga as etapas em [Comprar outra assinatura do Microsoft 365 para empresas](../buy-another-subscription.md) para comprar uma nova assinatura.

Certifique-se de comprar uma assinatura para a mesma organização em que os usuários estão agora. Por exemplo, verifique os endereços de email dos usuários que você deseja mover. Se os endereços de email \@ contoso.com, você deve comprar uma nova assinatura para contoso.com.
Inclua uma licença para cada usuário que você deseja mover.

## <a name="step-3-check-your-new-subscription-and-licenses"></a>Etapa 3: Verificar sua nova assinatura e licenças

1. No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.

2. **Verifique se ambas as assinaturas estão listadas e ativas** A assinatura de onde você está movendo os usuários e a assinatura para a que você está movendo os usuários devem estar listadas juntas. Se a nova assinatura não estiver lá quando você verificar pela primeira vez, tente novamente mais tarde. Verifique se ambas as assinaturas estão ativas. [A nova assinatura não está listada ou não está ativa.](#the-new-subscription-isnt-listed-or-isnt-active)

3. **Verifique se você tem licenças suficientes para cada usuário** Cada usuário precisa de uma licença que corresponde à sua assinatura. Portanto, se você quiser mover dez usuários para o Microsoft 365 Business Premium, precisará garantir que dez licenças estão disponíveis.

4. **Precisa de mais licenças para a nova assinatura?**
   Vá para a **página Seus produtos** e compre mais [licenças.](../licenses/buy-licenses.md)

> [E as licenças antigas?](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a>A nova assinatura não está listada ou não está ativa

- **Se você comprou duas assinaturas e elas** não estão listadas aqui, elas podem ter sido adquiridas para organizações diferentes (para domínios diferentes). As assinaturas não podem cruzar os limites da organização.

- **Se você sabe que tem uma assinatura** adicional e não está listada aqui ou não está ativa, ligue para o suporte da [Microsoft.](../../admin/contact-support-for-business-products.md)

### <a name="what-about-the-old-licenses"></a>E as licenças antigas?

As licenças da assinatura atual serão removidas posteriormente; você só pagará pelas novas licenças de usuário a partir de então.

## <a name="step-4-reassign-licenses"></a>Etapa 4: Reatribuir licenças

### <a name="reassign-a-license-for-one-user"></a>Reatribuir uma licença para um usuário

1. No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

2. Na página **Usuários ativos,** selecione o usuário a quem você deseja atribuir uma licença.

3. Na guia **Licenças e** **Aplicativos,** expanda Licenças, marque as caixas das licenças que você deseja atribuir e selecione **Salvar alterações.**

### <a name="reassign-licenses-for-multiple-users-at-once"></a>Reatribuir licenças para vários usuários ao mesmo tempo

1. No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

2. Selecione os círculos ao lado dos nomes dos usuários para os quais você deseja substituir as licenças existentes.

3. At the top, select **More options** (**...**), and then choose Manage **product licenses**.

4. Selecione **Substituir atribuições de licença de produto existentes** \> **Avançar**.

5. Alterne o botão para **a posição** Ligar para os produtos que você deseja atribuir a esses usuários.

    > [!TIP]
    > - Para limitar quais serviços estão disponíveis para o usuário,  alterne para a posição Desligado para os serviços que você deseja remover para esse usuário. Por exemplo, se quiser que o usuário tenha acesso a todos os serviços disponíveis, exceto o Skype for Business Online, você pode alternar a alternância do serviço Skype for Business Online para a posição **Desligado.**
    > - Atribuições de licença para os usuários selecionados que tenham sido feitas anteriormente serão removidas.

6. Na parte inferior do painel **Substituir produtos existentes**, selecione **Substituir** \> **Fechar**.

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a>Etapa 5: Cancelar assinaturas ou remover licenças de que você não precisa mais (Opcional)

Se você moveu todos os usuários de uma assinatura para outra e não precisa mais da assinatura original, poderá [cancelar a assinatura.](cancel-your-subscription.md)

Se você moveu apenas alguns usuários para uma assinatura diferente, [remova as licenças](../licenses/remove-licenses-from-subscription.md) de que não precisa mais.

## <a name="call-support-to-help-you-change-plans"></a>Ligue para o suporte para ajudá-lo a mudar de plano
[Ligar para o suporte da Microsoft](../../admin/contact-support-for-business-products.md)
