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
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
description: Saiba como gerenciar seus métodos de pagamento no Centro de Administração do Microsoft 365.
ms.date: ''
ms.openlocfilehash: a6866a9691e42928a5712c3069704f11fac0546f
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741384"
---
# <a name="manage-payment-methods"></a>Gerenciar métodos de pagamento

::: moniker range="o365-21vianet"
> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).
::: moniker-end

Ao comprar produtos ou serviços empresariais da Microsoft, você pode usar uma forma de pagamento existente ou adicionar uma nova. Você pode usar um cartão de crédito ou débito ou uma conta bancária para pagar por suas compras.

Se sua conta comercial tiver um perfil de cobrança e você for proprietário de perfil de cobrança ou colaborador de perfil de cobrança, você pode usar o perfil de cobrança que tem um cartão de crédito ou fatura para fazer compras ou pagar faturas. Se você for um gerente de cobrança de fatura, só poderá usar um perfil de cobrança para pagar contas. Para saber mais sobre funções e perfis de cobrança, consulte [Gerenciar perfis de cobrança](manage-billing-profiles.md).

Se sua conta comercial não tiver um perfil de cobrança, qualquer administrador Global ou de Cobrança poderá gerenciar e usar qualquer conta bancária adicionada à conta comercial. No entanto, você só pode gerenciar ou usar cartões de crédito que adicionar.

> [!NOTE]
> O pagamento por conta bancária não está disponível em alguns países ou regiões.
>
> Você deve usar um método de pagamento do mesmo país do seu locatário.

## <a name="before-you-begin"></a>Antes de começar

Você deve ser um administrador Global ou de Cobrança para realizar as etapas descritas neste artigo. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="add-a-payment-method"></a>Adicionar uma forma de pagamento

Adicionar uma forma de pagamento sem assinaturas associadas. Para atribuir uma única assinatura ao método de pagamento, consulte [Alterar um método de pagamento para uma única assinatura](#change-a-payment-method-for-a-single-subscription). Para substituir todas as assinaturas que usam outro método de pagamento pela nova, consulte [Substituir uma forma de pagamento](#replace-a-payment-method).

1. No centro de administração, acesse a página **Cobrança** > **Cobranças e pagamentos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Formas de pagamento</a>.
2. Selecione **Adicionar um método de pagamento**.
3. Na página **Método de pagamento**, escolha um método de pagamento do menu suspenso.
4. Insira as informações do novo cartão de crédito ou da nova conta e selecione **Adicionar**.

## <a name="update-payment-method-details"></a>Atualizar detalhes de método de pagamento

Você pode alterar o nome no cartão de crédito ou débito, no endereço para cobrança ou na data de vencimento de um método de pagamento existente. No entanto, não é possível alterar o número do cartão ou da conta. Se o número da conta tiver sido alterado, [substitua-o por outra forma de pagamento](#replace-a-payment-method)e, em seguida, [exclua o antigo](#delete-a-payment-method).

1. No centro de administração, acesse a página **Cobrança** > **Cobranças e pagamentos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Formas de pagamento</a>.
2. Selecione a linha do método de pagamento a ser atualizado. No painel direito, selecione **Editar**.
3. Atualize suas informações de método de pagamento, inclusive o nome no cartão de crédito ou de débito, no endereço de cobrança ou na data de vencimento e selecione **Salvar**.

## <a name="replace-a-payment-method"></a>Substituir um método de pagamento

Quando você substitui um método de pagamento, ele é substituído em todas as assinaturas e perfis de cobrança que usam a mesma forma de pagamento. Substituir um método de pagamento não exclui a forma de pagamento existente. Ele ainda está disponível para seleção e uso para outras assinaturas e perfis de cobrança.

Para alterar a forma de pagamento de uma única assinatura, consulte [Alterar um método de pagamento de uma única assinatura](#change-a-payment-method-for-a-single-subscription).

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

Você pode alterar o método de pagamento usado para uma única assinatura.

1. No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.
2. Na guia **Produtos**, encontre a assinatura que você deseja pagar com a forma de pagamento alternativa.
3. Selecione **Mais ações** (três pontos) e, em seguida, selecione **Substituir método de pagamento**.
4. No painel **Substituir método de pagamento**, na lista suspensa, escolha uma forma de pagamento alternativa ou opte por adicionar um método de pagamento.
5. Se você adicionar um método de pagamento, insira os detalhes do cartão ou da conta e selecione **Salvar**.
6. Verifique se a forma de pagamento selecionada está correta e selecione **Substituir**.

## <a name="delete-a-payment-method"></a>Excluir um método de pagamento

Você só pode excluir uma forma de pagamento que não está vinculada a uma assinatura ou perfil de cobrança. Isso se aplica a todas as assinaturas, seja qual for seu status.

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a>Excluir um método de pagamento sem assinaturas ou perfis vinculados

Se a forma de pagamento não estiver associada a nenhuma assinatura ou perfis de cobrança, você pode excluí-la imediatamente.

1. No centro de administração, acesse a página **Cobrança** > **Cobranças e pagamentos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Formas de pagamento</a>.
2. Encontre a forma de pagamento a excluir, selecione os três pontos e selecione **Excluir**.
3. Na parte inferior direita do painel, selecione **Excluir**.

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a>Excluir um método de pagamento sem assinaturas ou perfis de cobrança vinculados

Se um método de pagamento for vinculado a qualquer assinatura ou perfil de cobrança, primeiro substitua-o por um método de pagamento existente ou adicione um novo e, em seguida, exclua o antigo método de pagamento.

1. No centro de administração, acesse a página **Cobrança** > **Cobranças e pagamentos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Formas de pagamento</a>.
2. Selecione a linha do método de pagamento a ser excluído. O painel direito lista as assinaturas existentes que usam esse método de pagamento.
3. No painel direito, selecione **Excluir**.
4. Para usar um método de pagamento existente, escolha um na lista suspensa e selecione **Avançar** e então selecione **Excluir**.
    > [!NOTE]
    > Se você tiver assinaturas associadas a um perfil de cobrança, só poderá usar um cartão de crédito ou débito para pagar por eles. Se você tiver contas bancárias listadas na página **Métodos de pagamento**, elas não estarão disponíveis para seleção na lista suspensa.
5. Para adicionar um novo método de pagamento, marque **Adicionar método de pagamento**.
6. Escolha o tipo de pagamento que você deseja adicionar, insira as informações da conta e selecione **Salvar**.
7. O novo método de pagamento já está selecionado na lista suspensa. Selecione **Avançar**.
8. Selecione **Excluir**.

## <a name="troubleshoot-payment-methods"></a>Solucionar problemas de formas de pagamento

| Problema | Etapas para a solução de problemas |
|:----------|:-----|
|**Recebi uma mensagem de erro "O navegador está configurado para bloquear cookies".** |Configure seu navegador para permitir cookies de terceiros e tente novamente. |
|**Meu cartão de crédito ou débito foi recusado.** |Se você pagar com cartão de crédito ou débito e ele for recusado, você receberá um email informando que a Microsoft não conseguiu processar o pagamento. Primeiro, verifique se os detalhes do cartão &mdash;número, data de vencimento, nome no cartão e endereço, incluindo cidade, estado e CEP&mdash; são exibidos exatamente como no cartão e no extrato do cartão de crédito. Você pode atualizar as informações do seu cartão e enviar o pagamento imediatamente usando o link **Saldo devedor** na seção **Cobrança** da página de detalhes da assinatura. Para obter mais informações, confira [E se eu tiver um saldo pendente?](pay-for-your-subscription.md#what-if-i-have-an-outstanding-balance)  <br/><br/>  Se a mensagem "recusado" continuar sendo exibida, entre em contato com o seu banco.  É possível que seu cartão não esteja ativo. Se você recebeu recentemente o cartão pelo correio com uma data de validade atualizada, certifique-se de que ele está ativado. Seu banco também pode informar se seu cartão não está aprovado para transações online, internacionais ou recorrentes. |
|**Quero atualizar o número do cartão de crédito ou da conta bancária.** |Você não pode alterar o número em um cartão de crédito ou conta bancária existente. Se o número do seu cartão ou da sua conta tiver sido alterado, [substitua-o por uma forma de pagamento diferente](#replace-a-payment-method), que move todas as assinaturas ativas da forma de pagamento para a nova e, então, [exclua a forma de pagamento antiga](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached). |
|**Tenho apenas um cartão ou uma conta bancária associados à minha conta e desejo remover o cartão ou a conta.** |Se tiver apenas uma forma de pagamento, você deve [substituí-la por uma nova forma de pagamento](#replace-a-payment-method) antes de poder excluí-la. |
|**Não consigo adicionar meu cartão de crédito ou conta bancária.**  |Você deve usar um método de pagamento do mesmo país do seu locatário. Se tiver problemas para inserir seu cartão de crédito ou conta bancária, você poderá [contatar o suporte](../../admin/contact-support-for-business-products.md). |

## <a name="related-content"></a>Conteúdo relacionado

[Pague sua assinatura comercial](pay-for-your-subscription.md) (artigo)\
[Gerenciar perfis de cobrança](manage-billing-profiles.md) (artigo)\
[Alterar a frequência de cobrança](change-payment-frequency.md) (artigo)
