---
title: Atualizar para um plano de negócios diferente
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- commerce
ms.custom:
- SaRA
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
description: Saiba como atualizar para uma nova assinatura.
ms.openlocfilehash: b0f79233e6a05c2838026093bb0027cd4789b01b
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141061"
---
# <a name="upgrade-to-a-different-plan"></a>Atualizar para um plano diferente

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se sua experiência não corresponder aos detalhes apresentados aqui, consulte [sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Quando sua empresa mudar ou precisar de mais recursos, você poderá atualizar os planos. A maneira mais fácil de fazer isso é usar a guia **atualização** no centro de administração. No entanto, não há suporte para o uso da guia **atualização** em todas as situações. Em alguns casos, talvez seja possível alterar os planos manualmente.

> [!NOTE]
> Este artigo aplica-se ao novo centro de administração. Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page. Para exibir o artigo sobre o centro de administração antigo, consulte [alternar para um plano diferente do Microsoft 365 para empresas](switch-to-a-different-plan.md).

## <a name="use-the-upgrade-tab"></a>Usar a guia atualização

Ao usar a guia **atualização** , você é orientado pelo processo de compra de um novo plano. Todos os usuários recebem licenças automaticamente no novo plano e seu plano antigo é cancelado para você.

1. No centro de administração, vá para a página **cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">de seus produtos</a> .

2. Selecione a assinatura que você deseja atualizar.

3. Na página detalhes da assinatura, selecione **atualização**.

4. Encontre o plano para o qual você deseja atualizar e, em seguida, selecione o botão **Atualizar** .

5. Insira o número de licenças necessárias, escolha se deseja pagar a cada mês ou pelo ano inteiro e, em seguida, selecione **ir para checkout**.

    > [!NOTE]
    > Certifique-se de comprar licenças suficientes para abranger todos os usuários.

6. Na próxima página, verifique o endereço **vendido para** , as informações **cobradas** e os **itens nesta ordem**. Você pode alterar o método de pagamento padrão nesta etapa. Se você precisar fazer alterações, selecione **alterar** ao lado da seção aplicável.

7. Quando tiver terminado, selecione **fazer pedido**.

Ao concluir o check-out, pode levar alguns minutos para finalizar a atualização. Você pode começar a usar sua nova assinatura imediatamente. Selecione **verificar status da atualização** para verificar o progresso da atualização. Você será notificado quando a atualização for concluída. A notificação é exibida na página **seus produtos** , ao lado de sua nova assinatura.

## <a name="the-upgrade-tab-is-empty"></a>A guia atualização está vazia

Se a guia **atualização** estiver vazia, você verá uma explicação do motivo pelo qual não é possível atualizar no momento. Você pode tentar [alterar os planos manualmente](change-plans-manually.md). Para obter mais informações, consulte [por que não é possível atualizar planos?](#why-cant-i-upgrade-plans).

## <a name="i-dont-see-the-plan-i-want"></a>Não vejo o plano que desejo

Quando você usa a guia **atualização** , os planos para os quais você pode atualizar são exibidos com base nos serviços do seu plano atual. Você só pode usar a guia **atualização** para mover para um plano que tenha os mesmos serviços relacionados a dados ou para uma versão superior. Isso garante que os usuários não percam dados relacionados a esses serviços durante a alteração.

Se você quiser mudar para um plano com menos serviços, pode alterar os [planos manualmente](change-plans-manually.md)ou chamar o [suporte](../../admin/contact-support-for-business-products.md) para obter ajuda.

## <a name="why-some-changes-take-longer"></a>Por que algumas alterações levam mais tempo

**Número de usuários atribuídos:** Se você tiver um grande número de usuários atribuídos, levará mais tempo para fazer a atualização para movê-lo para o novo plano.

**Verificações de crédito ao mudar de planos:** Se você pagar por fatura ou atingir um determinado nível de custo, uma verificação de crédito poderá ser necessária. Uma verificação de crédito pode levar até dois dias úteis. Os usuários terão acesso total ao plano atual até serem movidos para o novo. Você receberá uma notificação se for necessário fazer uma verificação de crédito.

## <a name="why-cant-i-upgrade-plans"></a>Por que não posso atualizar os planos?

Se você não vir nenhum plano na guia **atualização** , significa que seu plano não pode ser atualizado automaticamente. Em alguns casos, talvez seja possível resolver o problema para que você possa exibir os planos disponíveis para atualização, ou talvez seja possível atualizar ou alterar os planos manualmente.

 ### <a name="why-are-there-no-plans-listed-to-upgrade"></a>Por que não há planos listados para atualizar?

#### <a name="you-cant-upgrade-subscriptions-now-because-you-have-more-users-than-licenses"></a>Não é possível atualizar assinaturas agora porque você tem mais usuários do que as licenças.

Para atualizar planos automaticamente, todos os seus usuários precisam ter licenças válidas atribuídas. Se você tiver atribuído mais licenças do que comprou, verá um alerta na página <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças</a> informando que há um conflito de licenças que precisa ser resolvido. [Saiba como resolver conflitos de licença](../../admin/manage/resolve-license-conflicts.md). Depois de resolver os conflitos de licenciamento, você deve ver os planos listados na guia **atualização** . Caso contrário, você pode [alterar os planos manualmente](change-plans-manually.md)ou [ligar para o suporte](../../admin/contact-support-for-business-products.md).

#### <a name="you-cant-upgrade-subscriptions-right-now-because-this-subscription-isnt-fully-set-up-or-the-service-isnt-available"></a>Você não pode atualizar as assinaturas imediatamente porque essa assinatura não está totalmente configurada ou o serviço não está disponível.

Por exemplo, se um dos serviços tiver um incidente, você não poderá atualizar até que todos os serviços estejam íntegros. Para ver se há problemas de integridade do serviço ou de provisionamento, no centro de administração, vá para a página <a href="https://go.microsoft.com/fwlink/p/?linkid=842900" target="_blank">integridade do serviço</a> de **integridade** \> .

Se você acha que um serviço não está totalmente provisionado ou que está com um problema de integridade, aguarde algumas horas para que o serviço fique disponível e tente novamente. Se você ainda tiver um problema, entre em contato com o [suporte](../../admin/contact-support-for-business-products.md).

#### <a name="you-cant-upgrade-plans-because-another-plan-is-in-the-process-of-being-upgraded-or-is-pending-a-credit-check"></a>Você não pode atualizar planos porque outro plano está no processo de atualização ou está aguardando uma verificação de crédito.

Aguarde até que a verificação de crédito tenha sido concluída antes de atualizar os planos. As verificações de crédito podem levar até dois dias úteis.

#### <a name="currently-this-subscription-is-not-eligible-to-upgrade"></a>No momento, esta assinatura não está qualificada para atualização.

Você pode [alterar planos manualmente](change-plans-manually.md) ou [ligar para o suporte](../../admin/contact-support-for-business-products.md).

#### <a name="i-see-a-different-message-than-whats-listed-here"></a>Eu vejo uma mensagem diferente da listada aqui.

Você pode [alterar planos manualmente](change-plans-manually.md) ou [ligar para o suporte](../../admin/contact-support-for-business-products.md).

### <a name="additional-reasons-you-cant-upgrade"></a>Motivos adicionais pelos quais não é possível atualizar

#### <a name="you-have-two-or-more-plans-for-the-same-product"></a>Você tem dois ou mais planos para o mesmo produto

Você só poderá usar a guia **atualização** se todos os usuários se inscreverem no mesmo plano. Por exemplo, se você tiver dois planos do Microsoft 365 Business Standard, não será possível atualizar automaticamente um deles para outro plano.

#### <a name="you-have-a-prepaid-plan"></a>Você tem um plano pré-pago

Se você tiver pago sua assinatura com antecedência, talvez seja possível [alterar os planos manualmente](change-plans-manually.md). No entanto, você não receberá um crédito por tempo não usado em sua assinatura atual se atualizar planos antes do plano atual expirar.

Você também pode [ligar](../../admin/contact-support-for-business-products.md) para o suporte da ajuda.

#### <a name="you-have-a-government-or-non-profit-plan"></a>Você tem um plano para instituições sem fins lucrativos ou governamentais

Se você tiver um plano governamental ou sem fins lucrativos, poderá [alterar os planos manualmente](change-plans-manually.md) ou [chamar o suporte](../../admin/contact-support-for-business-products.md) para obter ajuda.

#### <a name="the-subscription-that-you-want-to-upgrade-from-has-a-temporary-issue"></a>A assinatura da qual você deseja atualizar tem um problema temporário

Talvez você não veja planos na guia **atualização** porque o serviço está no processo de atualização de um grande volume de planos. Tente novamente depois de cerca de uma hora após sua primeira tentativa.

#### <a name="the-plan-that-you-want-to-upgrade-to-isnt-a-supported-option"></a>O plano para o qual você deseja atualizar não é uma opção com suporte

Quando você atualiza planos, os planos que estão disponíveis para atualização são exibidos com base nos serviços do seu plano atual. Você só pode atualizar para um plano que tenha os mesmos serviços relacionados a dados, como o Exchange Online ou o SharePoint Online, ou para uma versão superior deles. Isso garante que os usuários\'Don ' t percam dados relacionados a esses serviços durante a atualização.

Se seu plano não estiver qualificado para atualizar planos automaticamente, talvez você possa [alterar os planos manualmente](change-plans-manually.md). Você também pode [ligar](../../admin/contact-support-for-business-products.md) para o suporte da ajuda.

#### <a name="your-subscription-has-an-add-on"></a>Sua assinatura tem um complemento

Se você tiver um complemento com sua assinatura, talvez seja possível [alterar os planos manualmente](change-plans-manually.md).

#### <a name="your-subscription-has-an-unpaid-balance"></a>Sua assinatura tem um saldo não pago

Para resolver isso, encontre a assinatura na página <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">seus produtos</a> e selecione o link **pagar agora** na seção **cobrança** . Depois que o pagamento tiver sido feito, verifique a guia **atualização** novamente.

## <a name="what-does-upgrading-a-plan-do-to-my-service-and-billing"></a>O que a atualização de um plano faz com o meu serviço e cobrança?

Quando você atualiza planos automaticamente usando o botão **mudar de plano** (ou a guia **atualização** no novo centro de administração), seus serviços e cobrança são afetados.

### <a name="access-to-services"></a>Acesso aos serviços

 Os **Administradores** não poderão usar o centro de administração enquanto o plano estiver sendo atualizado. Isso pode levar até uma hora.
  
 Os **Usuários** não perceberão qualquer interrupção do serviço. Eles continuarão a ter o serviço existente até que a atualização seja totalmente concluída.
  
### <a name="users-and-licenses"></a>Usuários e licenças

Os usuários com assinaturas antigas serão movidos automaticamente para as novas assinaturas.
  
Se sua assinatura antiga incluir vários serviços e se você tiver alterado a quais desses serviços seus usuários estão atribuídos, convém tomar nota disso antes de atualizar os planos para que você possa recriar essas alterações posteriormente. Todos os usuários terão acesso a todos os serviços da nova assinatura. Por exemplo, se você comprou anteriormente o Microsoft 365 Business Premium para todos os 100 de seus usuários, mas não atribuiu o serviço do SharePoint Online de 50 deles, essa alteração não será mantida após a atualização dos planos.
  
Se você tiver mais de uma assinatura antes de atualizar os planos e ter os usuários com licenças atribuídas a mais de uma assinatura, esse padrão de atribuição será mantido o máximo possível na nova assinatura.
  
Todos os dados do usuário serão mantidos durante a atualização, incluindo caixas de correio do Exchange e documentos do SharePoint Online, listas e outras informações.
  
### <a name="billing"></a>Cobrança

O dia em que a atualização do plano está concluída, a cobrança de sua assinatura antiga será desativada e a cobrança na nova assinatura será ativada. Você receberá um crédito rateado para qualquer serviço não usado na assinatura antiga. Você receberá uma nova fatura que inclui o crédito de sua assinatura antiga dentro de 30 dias após a atualização para a nova assinatura.
  
> [!NOTE]
> O período de tempo que levará para receber o crédito na conta de pagamento pode variar de acordo com a forma de pagamento usada na assinatura.
  
**Atualizando de uma assinatura pré-paga antes de expirar?** Se o custo total da nova assinatura for maior ou igual ao valor do restante da assinatura pré-paga, você não perderá o tempo pré-pago. Na página de finalização da compra, você verá um crédito referente ao tempo não usado. No entanto, se o custo total da nova assinatura for menor do que o valor restante da assinatura pré-paga atual, você perderá parte do tempo não usado. Você será notificado antes de fazer o check-out, e você pode aguardar para atualizar até mais de perto da data de expiração da sua assinatura pré-paga.

## <a name="call-support-to-help-you-upgrade-plans"></a>Ligar para o suporte para ajudá-lo a atualizar os planos

[Chamar o suporte da Microsoft](../../admin/contact-support-for-business-products.md)

## <a name="related-articles"></a>Artigos relacionados

[Alterar planos manualmente](change-plans-manually.md)

[Fazer backup dos dados antes de mudar o Microsoft 365 para planos de negócios](back-up-data-before-switching-plans.md)
