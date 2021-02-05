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
description: Saiba como gerenciar seus métodos de pagamento no Centro de administração do Microsoft 365.
ms.date: ''
ms.openlocfilehash: 6cba5e33ba99212cb6e67a90d1535120ccac3c38
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114844"
---
# <a name="manage-payment-methods"></a>Gerenciar métodos de pagamento

::: moniker range="o365-21vianet"
> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).
::: moniker-end

Ao comprar produtos ou serviços da Microsoft, você pode usar uma forma de pagamento existente ou adicionar uma nova. Você pode usar um cartão de crédito ou débito ou uma conta bancária para pagar pelo que compra.

Se sua conta comercial tiver um perfil de cobrança e você for um proprietário de perfil de cobrança ou colaborador de perfil de cobrança, poderá usar o perfil de cobrança com o suporte de um cartão de crédito ou de um pagamento por fatura para fazer compras ou pagar faturas. Se você for um gerente de fatura de cobrança, só poderá usar um perfil de cobrança para pagar faturas. Para saber mais sobre perfis e funções de cobrança, consulte [Gerenciar perfis de cobrança.](manage-billing-profiles.md)

Se sua conta comercial não tiver um perfil de cobrança, qualquer administrador global ou de cobrança poderá gerenciar e usar qualquer conta bancária adicionada à conta comercial. No entanto, você só pode gerenciar ou usar cartões de crédito que adicionar.

> [!NOTE]
> A opção de pagamento com uma conta bancária não está disponível em alguns países ou regiões.
>
> Você deve usar um método de pagamento emitido do mesmo país do seu locatário.

## <a name="before-you-begin"></a>Antes de começar

Você deve ser um administrador global ou de cobrança para realizar as tarefas neste artigo. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="add-a-payment-method"></a>Adicionar uma forma de pagamento

Adicionar uma forma de pagamento não associa nenhuma assinatura a ela. Para atribuir uma única assinatura ao método de pagamento, consulte [Alterar um método de pagamento para uma única assinatura.](#change-a-payment-method-for-a-single-subscription) Para substituir todas as assinaturas que usam outra forma de pagamento pela nova, consulte [Substituir um método de pagamento.](#replace-a-payment-method)

1. No centro de administração, acesse a página **Cobrança** > **Cobranças e pagamentos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Formas de pagamento</a>.
2. Selecione **Adicionar um método de pagamento**.
3. Na página **Método de pagamento**, escolha um método de pagamento do menu suspenso.
4. Insira as informações para o novo cartão ou conta bancária e selecione **Adicionar**.

## <a name="update-payment-method-details"></a>Atualizar detalhes de método de pagamento

Você pode alterar o nome no cartão de crédito ou débito, no endereço de cobrança ou na data de vencimento de uma forma de pagamento existente. No entanto, você não pode alterar o cartão ou o número da conta. Se o número da conta tiver sido alterado, [substitua-o](#replace-a-payment-method)por um método de pagamento diferente e [exclua o antigo.](#delete-a-payment-method)

1. No centro de administração, acesse a página **Cobrança** > **Cobranças e pagamentos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Formas de pagamento</a>.
2. Selecione a linha do método de pagamento a ser atualizado. No painel direito, selecione **Editar**.
3. Atualize suas informações de método de pagamento, inclusive o nome no cartão de crédito ou de débito, no endereço de cobrança ou na data de vencimento e selecione **Salvar**.

## <a name="replace-a-payment-method"></a>Substituir um método de pagamento

Quando você substitui um método de pagamento, ele é substituído por todas as assinaturas e perfis de cobrança que usam a mesma forma de pagamento. Substituir um método de pagamento não exclui a forma de pagamento existente. Ele ainda está disponível para você selecionar e usar para outras assinaturas e perfis de cobrança.

Para alterar a forma de pagamento de uma única assinatura, consulte [Alterar um método de pagamento para uma única assinatura.](#change-a-payment-method-for-a-single-subscription)

1. No centro de administração, acesse a página **Cobrança** > **Cobranças e pagamentos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Formas de pagamento</a>.
2. Selecione a linha do método de pagamento a ser substituído. O painel direito lista todos os perfis de cobrança e assinaturas individuais que usam o método de pagamento selecionado.
3. No painel direito, marque **Substituir o método de pagamento para todos os itens**.
4. Para usar um método de pagamento existente, escolha um na lista suspensa e selecione **Substituir**.
    > [!NOTE]
    > Se você tiver assinaturas associadas a um perfil de cobrança, só poderá usar um cartão de crédito ou débito para pagar por eles. Se você tiver contas bancárias listadas na página **Métodos de pagamento**, elas não estarão disponíveis para seleção na lista suspensa.
5. Para adicionar um novo método de pagamento, marque **Adicionar método de pagamento**.
6. No painel **Adicionar um método de pagamento**, insira as informações da conta e, em seguida, selecione **Salvar**. Você deve usar um método de pagamento do mesmo país do seu locatário.
7. O novo método de pagamento já está selecionado na lista suspensa. Selecione **Substituir**.

## <a name="change-a-payment-method-for-a-single-subscription"></a>Alterar um método de pagamento para uma única assinatura

Você pode alterar a forma de pagamento usada para pagar uma única assinatura.

1. No centro de administração, acesse a página **Cobrança de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">seus produtos</a>.
2. Na guia **Produtos,** encontre a assinatura que você deseja pagar com a forma de pagamento alternativa.
3. Selecione **Mais ações** (três pontos) e, em seguida, substitua o método de **pagamento.**
4. No painel **Substituir método de** pagamento, na lista drop-down, escolha uma forma de pagamento alternativa ou escolha adicionar uma forma de pagamento.
5. Se você adicionar um método de pagamento, insira o cartão ou os detalhes da conta e selecione **Salvar.**
6. Verifique se o método de pagamento selecionado está correto e selecione **Substituir.**

## <a name="delete-a-payment-method"></a>Excluir um método de pagamento

Você só pode excluir um método de pagamento que não está anexado a uma assinatura ou perfil de cobrança. Isso se aplica a todas as assinaturas, independentemente de seu status.

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a>Excluir um método de pagamento sem assinaturas ou perfis de cobrança anexados

Se uma forma de pagamento não estiver associada a assinaturas ou perfis de cobrança, você poderá excluí-la imediatamente.

1. No centro de administração, acesse a página **Cobrança** > **Cobranças e pagamentos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Formas de pagamento</a>.
2. Encontre a forma de pagamento a ser excluído, selecione os três pontos e selecione **Excluir**.
3. Na parte inferior do painel direito, selecione **Excluir**.

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a>Excluir um método de pagamento com assinaturas ou perfis de cobrança anexados

Se um método de pagamento for anexado a assinaturas ou perfis de cobrança, substitua-o primeiro por um método de pagamento existente ou adicione um novo e exclua o método de pagamento antigo.

1. No centro de administração, acesse a página **Cobrança** > **Cobranças e pagamentos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Formas de pagamento</a>.
2. Selecione a linha do método de pagamento a ser excluído. O painel direito lista as assinaturas existentes que usam esse método de pagamento.
3. No painel direito, selecione **Excluir**.
4. To use an existing payment method, choose one from the drop-down list, select **Next**, and then select **Delete**.
    > [!NOTE]
    > Se você tiver assinaturas associadas a um perfil de cobrança, só poderá usar um cartão de crédito para pagar por elas. Se você tiver contas **bancárias** listadas na página Métodos de pagamento, elas não estarão disponíveis para escolha na lista lista.
5. Para adicionar um novo método de pagamento, marque **Adicionar método de pagamento**.
6. Escolha o tipo de método de pagamento que você deseja adicionar, insira as informações da conta e selecione **Salvar.**
7. O novo método de pagamento já está selecionado na lista suspensa. Selecione **Avançar**.
8. Selecione **Excluir**.

## <a name="troubleshoot-payment-methods"></a>Solucionar problemas de formas de pagamento

| Problema | Etapas para a solução de problemas |
|:----------|:-----|
|**Uma mensagem de erro diz: "O navegador está atualmente definido para bloquear cookies".** |Configure seu navegador para permitir cookies de terceiros e tente novamente. |
|**Meu cartão de crédito ou débito foi recusado.** |Se você pagar por cartão de crédito ou débito e seu cartão for recusado, você receberá um email informando que a Microsoft não pôde processar o pagamento. Verifique se o número do cartão de detalhes do cartão, a data de expiração, o nome no cartão e o endereço, incluindo cidade, estado e CEP aparecem exatamente como aparecem no cartão e no &mdash; &mdash; seu extrato. Você pode atualizar suas informações de cartão e enviar imediatamente o pagamento usando o **link** Liquidar saldo na seção **Cobrança** da página de detalhes da assinatura. Para obter mais informações, [consulte E se eu tiver um saldo pendente?](pay-for-your-subscription.md#what-if-i-have-an-outstanding-balance)  <br/><br/>  Se você continuar a ver a mensagem "recusada", entre em contato com o seu banco. É possível que seu cartão não está ativo. Se você recebeu recentemente o cartão no email com uma data de expiração atualizada, certifique-se de que ele está ativado. Seu banco também pode dizer se seu cartão não é aprovado para transações online, internacionais ou recorrentes. |
|**Quero atualizar um número de cartão ou conta bancária.** |Não é possível alterar o número do cartão ou da conta em uma forma de pagamento existente. Se o número do cartão ou da conta tiver sido alterado, substitua-o por um método de pagamento diferente, que move todas as assinaturas ativas do método de pagamento para o novo e exclua [o](#replace-a-payment-method)método de [pagamento antigo.](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached) |
|**Só tenho um cartão ou uma conta bancária na minha conta e quero removê-lo.** |Se você tiver apenas um método de pagamento, deverá [substituí-lo](#replace-a-payment-method) por um novo método de pagamento antes de excluí-lo. |
|**Não consigo adicionar meu cartão ou conta bancária.**  |Você deve usar um método de pagamento emitido do mesmo país do seu locatário. Se você tiver problemas para inserir suas informações de cartão ou conta bancária, entre em contato [com o suporte.](../../admin/contact-support-for-business-products.md) |

## <a name="related-content"></a>Conteúdo relacionado

[Pagar sua assinatura comercial](pay-for-your-subscription.md) (artigo)\
[Gerenciar perfis de cobrança](manage-billing-profiles.md) (artigo)\
[Alterar a frequência de cobrança](change-payment-frequency.md) (artigo)
