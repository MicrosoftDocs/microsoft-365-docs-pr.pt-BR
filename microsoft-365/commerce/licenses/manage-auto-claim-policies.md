---
title: Gerenciar políticas de declaração automática
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
description: Saiba como criar e gerenciar políticas de declaração automática que atribuem automaticamente licenças a usuários para determinados aplicativos.
ms.custom:
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
ms.openlocfilehash: 001b612820bb13873ec18733d68828837fcecd78
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599446"
---
# <a name="manage-auto-claim-policies"></a>Gerenciar políticas de declaração automática

Uma política de declaração automática permite que os usuários reclamem automaticamente uma licença para um produto na primeira vez que entrar em um aplicativo. Como administrador, você normalmente atribui licenças aos usuários manualmente ou usando licenciamento baseado em grupo. Usando políticas de declaração automática, você gerencia os produtos para os quais os usuários podem solicitar licenças automaticamente. Você também pode controlar de quais produtos essas licenças vêm.

Depois de criar uma política de declaração automática, você pode fazer as seguintes tarefas para gerenciar a política:

- [Ativar ou desativar a política](#turn-a-policy-on-or-off)
- [Editar o nome amigável da política](#edit-the-policy-friendly-name)
- [Adicionar ou remover produtos de backup](#add-or-remove-backup-products)
- [Gerenciar os aplicativos e serviços de atribuição](#change-the-assigning-apps-and-services)
- [Alterar a ordem de atribuição](#change-the-assigning-order-for-backup-products)
- [Exibir um relatório de política](#view-an-auto-claim-policy-report)

> [!IMPORTANT]
> No momento, as políticas de declaração automática estão disponíveis apenas para o Microsoft Teams. Mais produtos estarão disponíveis para uso no futuro.

## <a name="before-you-begin"></a>Antes de começar

Você deve ser um administrador Global, Usuário ou Licença para criar e gerenciar políticas de declaração automática. Para obter mais informações, consulte [Sobre as funções de administrador do Microsoft 365](../../admin/add-users/about-admin-roles.md).

## <a name="turn-the-auto-claim-policy-feature-on-or-off"></a>Ativar ou desativar o recurso de política de declaração automática

Por padrão, o recurso de política de declaração automática está desligado. Antes de poder usar o recurso, primeiro você deve a turn-lo. Depois de ativar o recurso, você pode criar uma política de declaração automática.

### <a name="turn-on-auto-claim-policies"></a>Ativar políticas de declaração automática

1. No centro de administração, vá para a página **Licenças** de Cobrança \>  e selecione a guia Política <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">de Declaração</a> Automática.
2. No centro da página, selecione o **botão Ativar configuração.**

### <a name="turn-off-auto-claim-policies"></a>Desativar políticas de declaração automática

Somente um administrador global pode desativar uma configuração de política de declaração automática.

1. No centro de administração, vá para a página **Configurações** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">da Organização.</a>
2. Na parte inferior da tabela, selecione **Aplicativos e serviços de propriedade do usuário.**
3. No painel direito, despeque a caixa para Permitir que os usuários reclamem automaticamente **licenças na primeira vez em que entrar**.

Se você já tiver uma política ativa, mas não quiser que mais usuários reclame licenças, [desligue a política](#turn-a-policy-on-or-off). Quando você desativar uma política de declaração automática, nenhum usuário poderá reivindicar uma licença desse ponto em diante. Os usuários que já reivindicaram uma licença não perdem a licença.

## <a name="create-an-auto-claim-policy"></a>Criar uma política de declaração automática

A <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">guia Política de Declaração Automática</a> lista as políticas criadas. Nesta guia, você pode ver: o nome da política, o aplicativo associado à política, o produto atribuído à política, o número de licenças disponíveis e o status da política.

Ao criar uma política de declaração automática, você pode adicionar um produto de backup a ela. Se o produto principal estiver sem licenças, o produto de backup será usado para atribuir licenças aos usuários. Você pode adicionar até quatro produtos de backup e [alterar a ordem na qual eles são usados](#change-the-assigning-order-for-backup-products). Para saber mais, confira [Adicionar ou remover produtos de backup.](#add-or-remove-backup-products)

> [!NOTE]
> Atualmente, você só pode criar uma política de declaração automática. O número de políticas que você pode criar aumentará à medida que mais produtos puderem usar esse recurso.

1. No centro de administração, vá para a página **Licenças** de Cobrança \>  e selecione a guia Política <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">de Declaração</a> Automática.
2. Selecione **Adicionar uma política**.
3. Na página **Nomear essa política de declaração** automática, insira um nome para a política e selecione **Próximo**.
4. Na página **Definir um aplicativo de declaração automática** e produto, selecione um aplicativo e a assinatura de onde atribuir licenças.
5. Se você quiser adicionar um produto de backup, selecione **Adicionar um produto de backup a essa política** e selecione o produto na lista.
6. Selecione **Próximo**.
7. Na página **Selecionar aplicativos,** deslele ou selecione as caixas para os aplicativos excluirem ou incluirem com a licença e selecione **Próximo**.
8. Se você adicionou um ou mais produtos de backup, repita a etapa 7 para cada produto. Caso contrário, vá para a etapa 9.
9. Na página **Revisar e** concluir, verifique as novas informações de política, faça as alterações necessárias e selecione **Criar política**.
10. Selecione **Fechar**.

## <a name="turn-a-policy-on-or-off"></a>Ativar ou desativar uma política

Quando você desativar uma política, nenhum usuário poderá reivindicar licenças sob essa política. A alteração não afeta os usuários que já reivindicaram licenças nessa política.

1. No centro de administração, vá para a página **Licenças** de Cobrança \>  e selecione a guia Política <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">de Declaração</a> Automática.
2. Selecione a política que você deseja editar.
3. No painel de detalhes, em Ativar ou desativar essa **política,** selecione ou desimple a caixa de seleção.
4. Selecione **Salvar** para fechar o painel de detalhes.

## <a name="edit-the-policy-friendly-name"></a>Editar o nome amigável da política

1. No centro de administração, vá para a página **Licenças** de Cobrança \>  e selecione a guia Política <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">de Declaração</a> Automática.
2. Selecione a política que você deseja editar.
3. No painel de detalhes, na seção **Nome da** política, selecione **Editar**.
4. Insira um novo nome de política e selecione **Salvar**.
5. Selecione **Salvar** para fechar o painel de detalhes.

## <a name="add-or-remove-backup-products"></a>Adicionar ou remover produtos de backup

Quando você cria uma política, adiciona um produto a ela. Em seguida, as licenças são atribuídas automaticamente aos usuários desse pool de licenças. Você pode adicionar ou remover produtos para uma política de declaração automática a qualquer momento. Se você já tiver um produto associado à política, todos os produtos que você adicionar serão considerados produtos de backup. Quando o número disponível de licenças do primeiro produto é usado, a política usa o próximo produto de backup na lista para atribuir licenças. Você [pode reordenar a lista de produtos](#change-the-assigning-apps-and-services) conforme quiser.

Quando você remove um produto de backup, ele não é mais usado para atribuir licenças. Os usuários com uma licença existente ainda têm essa licença, mas nenhum novo usuário pode receber licenças para esse produto.

> [!NOTE]
> Uma política de declaração automática deve conter pelo menos um produto. Não é possível remover todos os produtos de uma política. Se você não quiser mais atribuir licenças de uma política de declaração automática específica, [desligue a política](#view-an-auto-claim-policy-report).

### <a name="add-a-backup-product"></a>Adicionar um produto de backup

1. No centro de administração, vá para a página **Licenças** de Cobrança \>  e selecione a guia Política <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">de Declaração</a> Automática.
2. Selecione a política que você deseja editar.
3. No painel de detalhes, na parte inferior, selecione **Adicionar um produto de backup a esta política**.
    > [!NOTE]
    > Se você não vir esse link, será porque você só tem um produto associado à sua conta.
4. No painel **Adicionar um produto,** use o drop-down para escolher um produto para adicionar à política e selecione **Adicionar**.
5. Selecione **Salvar** para fechar o painel de detalhes.

### <a name="remove-a-backup-product"></a>Remover um produto de backup

1. No centro de administração, vá para a página **Licenças** de Cobrança \>  e selecione a guia Política <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">de Declaração</a> Automática.
2. Selecione a política que você deseja editar.
3. No painel de detalhes, na parte inferior, selecione **Remover um produto**.
4. No painel **Remover um produto** do painel de política, selecione a caixa da política que você deseja remover e selecione **Salvar**.
5. Feche o painel de detalhes.

## <a name="change-the-assigning-apps-and-services"></a>Alterar os aplicativos e serviços de atribuição

Cada produto tem uma coleção de aplicativos e serviços associados a ele.
Para cada produto em sua política de declaração automática, você pode especificar quais aplicativos e serviços incluir quando um usuário recebe automaticamente uma licença para esse produto.

1. No centro de administração, vá para a página **Licenças** de Cobrança \>  e selecione a guia Política <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">de Declaração</a> Automática.
2. Selecione a política que você deseja editar.
3. No painel de detalhes, em **Aplicativos e serviços,** selecione **Editar**.
4. No painel **Aplicativos e serviços,** no **drop-down** Produto, selecione um único produto ou selecione Todos os **produtos**.
5. Verifique ou limpe as caixas para aplicativos e serviços aos quais você deseja que os usuários tenham ou não acesso.
6. Quando terminar, selecione **Salvar** e, em seguida, feche o painel de detalhes.

## <a name="change-the-assigning-order-for-backup-products"></a>Alterar a ordem de atribuição de produtos de backup

Se você tiver produtos de backup atribuídos à política, poderá alterar a ordem na qual eles são usados para atribuir licenças quando os usuários entrarem no aplicativo.

1. No centro de administração, vá para a página **Licenças** de Cobrança \>  e selecione a guia Política <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">de Declaração</a> Automática.
2. Selecione a política que você deseja editar.
3. No painel de detalhes, na seção **Licenças** do produto, selecione a caixa ao lado do produto que você deseja mover e selecione Mover para **cima** ou **Mover para baixo**.
4. Repita a etapa 3 para cada produto que você deseja reordenar.
5. Quando terminar de reordenar os produtos, selecione **Salvar** para fechar o painel de detalhes.

## <a name="view-an-auto-claim-policy-report"></a>Exibir um relatório de política de declaração automática

1. No centro de administração, vá para a página **Licenças** de Cobrança \>  e selecione a guia Política <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">de Declaração</a> Automática.
2. Selecione **Exibir relatório**. A **página Relatório de política** de declaração automática lista todas as licenças atribuídas de cada política nos últimos 90 dias. Por padrão, a página mostra os últimos 90 dias.
3. Para alterar o período de tempo mostrado, selecione a lista lista de **30** dias. Você pode exibir relatórios nos últimos 1, 7, 30 e 90 dias.

## <a name="next-steps"></a>Próximas etapas

Você pode retornar periodicamente à guia **Política** de Declaração Automática para ver uma lista de usuários que reivindicaram licenças nas políticas criadas.

## <a name="related-content"></a>Conteúdo relacionado

[Atribuir licenças aos usuários](../../admin/manage/assign-licenses-to-users.md) (artigo) \
[Comprar ou remover licenças de assinatura](buy-licenses.md) (artigo)\
[Compreender assinaturas e licenças](subscriptions-and-licenses.md) (artigo)