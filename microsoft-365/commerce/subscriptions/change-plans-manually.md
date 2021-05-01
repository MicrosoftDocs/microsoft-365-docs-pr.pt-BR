---
title: Alterar Microsoft 365 para planos de negócios manualmente
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
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
- PPM_jmueller
ms.reviewer: jkinma
search.appverid:
- MET150
ROBOTS: NOINDEX
description: Altere as assinaturas manualmente comprando uma nova assinatura e garantindo que ambas as assinaturas sejam listadas e ativas.
ms.date: 03/17/2021
ms.openlocfilehash: 1dc7ff8cd6b8a43db7d70ab6c17aec16a020baac
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107675"
---
# <a name="change-plans-manually"></a>Alterar planos manualmente

## <a name="step-1-decide-how-to-change-plans"></a>Etapa 1: Decidir como alterar planos

A melhor maneira de alterar todos os usuários de um plano para outro é [usar a guia Atualização.](upgrade-to-different-plan.md) Às vezes, isso não é possível. Em vez disso, altere os planos manualmente:

- Se a **guia** Atualização indicar que você não pode atualizar o plano atual.

- Se, ao selecionar a guia **Atualização,** o plano que você deseja não estiver listado.

- Se você não quiser atualizar todos os usuários da mesma maneira. Algumas empresas precisam de usuários diferentes inscritos em planos diferentes. Use uma alteração manual para isso.

Para continuar com uma alteração manual, leia [Etapa 2: Comprar](#step-2-buy-a-new-subscription) uma nova assinatura neste tópico.

> [!IMPORTANT]
> Se você estiver mudando para um plano com menos serviços relacionados a dados do que seu plano atual (downgrading), você precisará fazer o back-up manualmente de todos os dados que deseja manter. Para obter mais informações, consulte [Back up data before changing plans](back-up-data-before-switching-plans.md).

## <a name="step-2-buy-a-new-subscription"></a>Etapa 2: Comprar uma nova assinatura

**Já comprou?** Se você já tem uma assinatura para a que deseja mover os usuários, ignore esta etapa e vá para a Etapa [3:](#step-3-check-your-new-subscription-and-licenses) Verifique sua nova assinatura e licenças neste tópico.

OU

**Comprar uma nova assinatura e licenças:** Siga as etapas em [Comprar outra assinatura Microsoft 365 para empresas](../try-or-buy-microsoft-365.md) para comprar uma nova assinatura.

Certifique-se de comprar uma assinatura para a mesma organização em que os usuários estão agora. Por exemplo, verifique os endereços de email dos usuários que você deseja mover. Se os endereços de email contoso.com, você \@ deve comprar uma nova assinatura para contoso.com.
Inclua uma licença para cada usuário que você deseja mover.

## <a name="step-3-check-your-new-subscription-and-licenses"></a>Etapa 3: Verificar sua nova assinatura e licenças

1. No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.

2. **Verifique se ambas as assinaturas estão listadas e ativas** A assinatura de onde você está movendo os usuários e a assinatura para a que você está movendo os usuários devem estar listadas juntas. Se a nova assinatura não estiver lá quando você verificar pela primeira vez, tente novamente mais tarde. Verifique se ambas as assinaturas estão ativas. [A nova assinatura não está listada ou não está ativa](#the-new-subscription-isnt-listed-or-isnt-active).

3. **Verifique se você tem licenças suficientes para cada usuário** Cada usuário precisa de uma licença que corresponde à assinatura. Portanto, se você quiser mover dez usuários para Microsoft 365 Business Premium, você precisará garantir que dez licenças estão disponíveis.

4. **Precisa de mais licenças para a nova assinatura?**
   Vá até a **página Seus produtos** e compre mais [licenças.](../licenses/buy-licenses.md)

> [E as licenças antigas?](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a>A nova assinatura não está listada ou não está ativa

- **Se você comprou duas assinaturas** e elas não estão listadas aqui , elas podem ter sido compradas para organizações diferentes (para domínios diferentes). As assinaturas não podem cruzar os limites da organização.

- **Se você sabe que tem uma assinatura** adicional e ela não está listada aqui ou não está ativa, chame o suporte da [Microsoft.](../../admin/contact-support-for-business-products.md)

### <a name="what-about-the-old-licenses"></a>E as licenças antigas?

As licenças da assinatura atual serão removidas posteriormente; você só pagará pelas novas licenças de usuário a partir daí.

## <a name="step-4-reassign-licenses"></a>Etapa 4: Reatribuir licenças

### <a name="reassign-a-license-for-one-user"></a>Reatribuir uma licença para um usuário

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

2. Na página **Usuários ativos,** selecione o usuário ao qual você deseja atribuir uma licença.

3. Na guia **Licenças e** **Aplicativos,** expanda Licenças, selecione as caixas para as licenças que você deseja atribuir e selecione **Salvar alterações**.

### <a name="reassign-licenses-for-multiple-users-at-once"></a>Reatribuir licenças para vários usuários de uma só vez

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

2. Selecione os círculos ao lado dos nomes dos usuários para os quais você deseja substituir as licenças existentes.

3. Na parte superior, selecione **Mais opções** (**...**) e escolha **Gerenciar licenças de produto**.

4. Selecione **Substituir atribuições de licença de produto existentes** \> **Avançar**.

5. Alterne a alternância **para a posição On** para os produtos que você deseja atribuir a esses usuários.

    > [!TIP]
    > - Para limitar quais serviços estão disponíveis para o usuário,  alterne para alternar para a posição Off para os serviços que você deseja remover para esse usuário. Por exemplo, se você quiser que o usuário tenha acesso a todos os serviços disponíveis, exceto Skype for Business Online, você pode alternar a alternância para o serviço Skype for Business Online para a posição **Off.**
    > - Atribuições de licença para os usuários selecionados que tenham sido feitas anteriormente serão removidas.

6. Na parte inferior do painel **Substituir produtos existentes**, selecione **Substituir** \> **Fechar**.

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a>Etapa 5: Cancelar assinaturas ou remover licenças que você não precisa mais (Opcional)

Se você tiver movido todos os usuários de uma assinatura para outra e não precisar mais da assinatura original, poderá [cancelar a assinatura](cancel-your-subscription.md).

Se você moveu apenas alguns usuários para uma assinatura diferente, [remova as licenças](../licenses/buy-licenses.md) que você não precisa mais.

## <a name="call-support-to-help-you-change-plans"></a>Chamar suporte para ajudá-lo a mudar de planos
[Chamar o suporte da Microsoft](../../admin/contact-support-for-business-products.md)