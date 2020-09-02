---
title: Gerenciar métodos de pagamento
f1.keywords:
- CSH
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
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: Saiba como gerenciar seus métodos de pagamento no centro de administração do Microsoft 365.
ms.date: ''
ms.openlocfilehash: 81c7509fb2f3be982890ec6b68dafb83ff0c1876
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324229"
---
# <a name="manage-payment-methods"></a>Gerenciar métodos de pagamento

::: moniker range="o365-21vianet"
> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).
::: moniker-end

Ao comprar produtos ou serviços de negócios da Microsoft, você pode usar um método de pagamento existente ou adicionar um novo. Você pode usar um cartão de crédito ou débito ou uma conta bancária para pagar pelas coisas que comprar.

Se sua conta comercial tiver um perfil de cobrança e você for um proprietário de perfil de cobrança ou um colaborador de perfil de cobrança, você poderá usar o perfil de cobrança que tem o respaldo de um cartão de crédito ou pagamento de fatura para fazer compras ou pagar as contas. Se você é um gerente de fatura de cobrança, você só pode usar um perfil de cobrança para pagar as contas. Para saber mais sobre perfis e funções de cobrança, confira [gerenciar perfis de cobrança](manage-billing-profiles.md).

Se sua conta comercial não tiver um perfil de cobrança, qualquer administrador global ou de cobrança poderá gerenciar e usar qualquer conta bancária adicionada à conta comercial. No entanto, você só pode gerenciar ou usar cartões de crédito que você adicionar.

> [!NOTE]
> A opção de pagamento com uma conta bancária não está disponível em alguns países ou regiões.
>
> Você deve usar um método de pagamento emitido do mesmo país do seu locatário.

## <a name="before-you-begin"></a>Antes de começar

Você deve ser um administrador global ou de cobrança para realizar as tarefas neste artigo. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="add-a-payment-method"></a>Adicionar uma forma de pagamento

A adição de um método de pagamento não associa nenhuma assinatura a ela. Para atribuir uma única assinatura ao método de pagamento, confira [alterar um método de pagamento para uma única assinatura](#change-a-payment-method-for-a-single-subscription). Para substituir todas as assinaturas que usam outra forma de pagamento com a nova, confira [substituir um método de pagamento](#replace-a-payment-method).

1. No centro de administração, acesse a página **Cobrança** > **Cobranças e pagamentos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Formas de pagamento</a>.
2. Selecione **Adicionar um método de pagamento**.
3. Na página **Método de pagamento**, escolha um método de pagamento do menu suspenso.
4. Insira as informações para o novo cartão ou conta bancária e, em seguida, selecione **Adicionar**.

## <a name="update-payment-method-details"></a>Atualizar detalhes de método de pagamento

Você pode alterar o nome no cartão de crédito ou débito, no endereço de cobrança ou na data de vencimento de uma forma de pagamento existente. No entanto, não é possível alterar o número do cartão ou da conta. Se o número da conta tiver sido alterado, [substitua-o por outro método de pagamento](#replace-a-payment-method)e [exclua o antigo](#delete-a-payment-method).

1. No centro de administração, acesse a página **Cobrança** > **Cobranças e pagamentos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Formas de pagamento</a>.
2. Selecione a linha do método de pagamento a ser atualizado. No painel direito, selecione **Editar**.
3. Atualize suas informações de método de pagamento, inclusive o nome no cartão de crédito ou de débito, no endereço de cobrança ou na data de vencimento e selecione **Salvar**.

## <a name="replace-a-payment-method"></a>Substituir uma método de pagamento

Ao substituir uma forma de pagamento, você a substitui por todas as assinaturas e perfis de cobrança que usam a mesma forma de pagamento. A substituição de um método de pagamento não exclui o método de pagamento existente. Ainda está disponível para você selecionar e usar para outras assinaturas e perfis de cobrança.

Para alterar a forma de pagamento de uma única assinatura, confira [alterar um método de pagamento para uma única assinatura](#change-a-payment-method-for-a-single-subscription).

1. No centro de administração, acesse a página **Cobrança** > **Cobranças e pagamentos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Formas de pagamento</a>.
2. Selecione a linha do método de pagamento a ser substituído. O painel direito lista todos os perfis de cobrança e assinaturas individuais que usam o método de pagamento selecionado.
3. No painel direito, marque **Substituir o método de pagamento para todos os itens**.
4. Para usar um método de pagamento existente, escolha um na lista suspensa e selecione **Substituir**.
    > [!NOTE]
    > Se você tiver assinaturas associadas a um perfil de cobrança, só poderá usar um cartão de crédito ou débito para pagar por eles. Se você tiver contas bancárias listadas na página **Métodos de pagamento**, elas não estarão disponíveis para seleção na lista suspensa.
5. Para adicionar um novo método de pagamento, marque**Adicionar método de pagamento**.
6. No painel **Adicionar um método de pagamento**, insira as informações da conta e, em seguida, selecione **Salvar**. Você deve usar um método de pagamento do mesmo país do seu locatário.
7. O novo método de pagamento já está selecionado na lista suspensa. Selecione **Substituir**.

## <a name="change-a-payment-method-for-a-single-subscription"></a>Alterar um método de pagamento para uma única assinatura

Você pode alterar o método de pagamento usado para pagar uma única assinatura.

1. No centro de administração, vá para a página **cobrança**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">de seus produtos</a> .
2. Na guia **produtos** , encontre a assinatura que deseja pagar com a forma de pagamento alternativo.
3. Selecione **mais ações** (três pontos) e selecione **substituir método de pagamento**.
4. No painel **substituir método de pagamento** , na lista suspensa, escolha uma forma de pagamento alternativa ou escolha Adicionar uma forma de pagamento.
5. Se você adicionar um método de pagamento, insira os detalhes do cartão ou da conta e selecione **salvar**.
6. Verifique se o método de pagamento selecionado está correto e, em seguida, selecione **substituir**.

## <a name="delete-a-payment-method"></a>Excluir um método de pagamento

Você só pode excluir um método de pagamento que não esteja anexado a uma assinatura ou a um perfil de cobrança. Isso se aplica a todas as assinaturas, seja qual for o status.

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a>Excluir um método de pagamento sem assinaturas ou perfis de cobrança anexados

Se um método de pagamento não estiver associado a qualquer assinatura ou perfil de cobrança, você poderá excluí-lo imediatamente.

1. No centro de administração, acesse a página **Cobrança** > **Cobranças e pagamentos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Formas de pagamento</a>.
2. Encontre o método de pagamento a ser excluído, selecione os três pontos e, em seguida, selecione **excluir**.
3. Na parte inferior do painel direito, selecione **excluir**.

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a>Excluir um método de pagamento com assinaturas ou perfis de cobrança anexados

Se um método de pagamento estiver anexado a qualquer assinatura ou perfil de cobrança, primeiro substitua-o por um método de pagamento existente, ou adicione um novo, e exclua o antigo método de pagamento.

1. No centro de administração, acesse a página **Cobrança** > **Cobranças e pagamentos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Formas de pagamento</a>.
2. Selecione a linha para o método de pagamento a ser excluído. O painel direito lista as assinaturas existentes que usam essa forma de pagamento.
3. No painel direito, selecione **excluir**.
4. Para usar um método de pagamento existente, escolha um na lista suspensa, selecione **Avançar**e, em seguida, selecione **excluir**.
    > [!NOTE]
    > Se você tiver assinaturas associadas a um perfil de cobrança, só poderá usar um cartão de crédito para pagar por elas. Se você tiver contas bancárias listadas na página **métodos de pagamento** , elas não estarão disponíveis para escolher na lista suspensa.
5. Para adicionar um novo método de pagamento, marque**Adicionar método de pagamento**.
6. Escolha o tipo de método de pagamento que você deseja adicionar, insira as informações da conta e, em seguida, selecione **salvar**.
7. O novo método de pagamento já está selecionado na lista suspensa. Selecione **Avançar**.
8. Selecione **Excluir**.

## <a name="troubleshoot-payment-methods"></a>Solucionar problemas de formas de pagamento

|**Problema**|**Etapas de solução de problemas**|
|:----------|:-----|
|**Recebo uma mensagem de erro que diz: "o navegador está definido atualmente para bloquear cookies".** |Configure seu navegador para permitir cookies de terceiros e tente novamente. |
|**Meu cartão de crédito ou débito foi recusado.** |Se você pagar por cartão de crédito ou débito e seu cartão for recusado, você receberá um email dizendo que a Microsoft não pôde processar o pagamento. Verifique se o número do cartão de detalhes do cartão &mdash; , a data de vencimento, o nome no cartão e o endereço, incluindo cidade, estado e CEP, &mdash; aparecem exatamente como eles fazem no cartão e na instrução. Você pode atualizar as informações do cartão e enviar o pagamento imediatamente usando o link de **equilíbrio de liquidação** na seção **cobrança** da página detalhes da assinatura. Para obter mais informações, consulte e [se meu cartão de crédito foi recusado e se o meu pagamento está](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due) vencido?  <br/><br/>  Se você continuar a ver a mensagem "recusada", entre em contato com seu banco. É possível que o cartão não esteja ativo. Se você recebeu recentemente o cartão no email com uma data de validade atualizada, verifique se ele está ativado. Seu banco também pode informá-lo se o cartão não está aprovado para transações online, internacionais ou recorrentes. |
|**Desejo atualizar um cartão ou número de conta bancária.** |Não é possível alterar o número do cartão ou da conta em um método de pagamento existente. Se o seu número de cartão ou conta tiver sido alterado, [substitua-o por outro método de pagamento](#replace-a-payment-method), que move todas as assinaturas ativas da forma de pagamento para a nova e, em seguida, [exclua o antigo método de pagamento](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached). |
|**Só tenho um cartão ou conta bancária em minha conta e desejo removê-lo.** |Se você tiver apenas uma forma de pagamento, deverá [substituí-la por uma nova método de pagamento antes de](#replace-a-payment-method) excluí-la. |
|**Não consigo adicionar meu cartão ou minha conta bancária.**  |Você deve usar um método de pagamento emitido do mesmo país do seu locatário. Se você tiver problemas para inserir as informações do cartão ou da conta bancária, você pode [entrar em contato com o suporte](../../admin/contact-support-for-business-products.md). |

## <a name="related-content"></a>Conteúdo relacionado

[Pague sua assinatura comercial](pay-for-your-subscription.md) (artigo) \
[Gerenciar perfis de cobrança](manage-billing-profiles.md) (artigo) \
[Alterar sua frequência de cobrança](change-payment-frequency.md) (artigo)