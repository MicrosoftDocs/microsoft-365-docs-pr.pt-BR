---
title: Criar e usar um modelo para adicionar usuários
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
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: Você pode criar e usar um modelo para economizar tempo e padronizar configurações ao adicionar vários usuários.
ms.openlocfilehash: 3ce70f6d37036a2f71bdc2d41bfb5677a54b8db9
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579381"
---
# <a name="create-and-use-a-template-to-add-users"></a>Criar e usar um modelo para adicionar usuários

Você pode criar e usar um modelo para economizar tempo e padronizar configurações ao adicionar vários usuários. Os modelos são particularmente úteis se você tiver usuários que compartilham muitas propriedades comuns, como aqueles que têm a mesma função e trabalham no mesmo local e aqueles que exigem o mesmo software. Por exemplo, você pode ter uma equipe de engenheiros de suporte que trabalham no mesmo escritório.  

## <a name="create-a-template"></a>Criar um modelo

Os modelos são fáceis de criar, você pode selecionar Usuários Usuários ativos Modelos de usuário e, em seguida, selecione Adicionar um modelo na listada, ou você pode adicionar um novo usuário e, quando terminar, você terá a opção de salvar a entrada como &mdash;   >    >  um modelo. 

Quando você cria um modelo depois de adicionar um usuário, os valores escolhidos para as seguintes configurações são salvos no modelo:

- Nome de domínio
- Opção de configurações de senha: você pode optar por criar senhas ou fazer com que elas tenham sido geradas automaticamente
- Opção de senha única: você pode exigir que o usuário crie uma nova senha após o primeiro login
- Local da licença
- Opções de licença
- Opções de aplicativo
- Função
- A maioria das informações de perfil, como **Perfil de** Trabalho, **Departamento,** **Office,** **Office telefone** e **endereço street** 

As informações a seguir são específicas do usuário e não são salvas no modelo:

- Nome e sobrenome
- Nome de exibição
- Nome de usuário
- Escolha enviar a senha por email e para quem o email de senha é enviado
- Número de telefone celular

Se você optar por não inserir informações para uma configuração dentro de uma seção, esse valor ficará em branco e essa configuração não será exibida no modelo. Por exemplo, se você deixar **o cargo** em branco, ao revisar seu modelo e quando usar seu modelo, **o** cargo não aparecerá. Se você deixar todas as **configurações** da seção Perfil em branco, a seção **Perfil** exibirá **Nenhum fornecido** no modelo final.

Ao criar um modelo selecionando **a opção Adicionar um modelo,** você pode escolher quais valores serão concluídos. Tudo o que for deixado em branco aparecerá como **Nenhum fornecido** no modelo.

## <a name="use-a-template-to-add-a-user"></a>Usar um modelo para adicionar um usuário

Para usar um modelo existente para adicionar um usuário:

1. No centro de administração, selecione **Usuários**  >  **Usuários ativos**.

2. Selecione **Modelos de usuário** e selecione um modelo na listada. (A lista conterá apenas os modelos criados, não aqueles criados por outros administradores.)

   > [!NOTE]
   > Você também pode usar um modelo para adicionar um usuário selecionando Modelos de usuário  >  **Gerenciar** modelos, selecionando um modelo e selecionando **Usar modelo**.

3. Siga as etapas para criar um usuário a partir do modelo selecionado.

   > [!NOTE]
   > Se você tiver licenças insuficientes disponíveis para um usuário que você adiciona e suas informações de pagamento estão disponíveis, tentaremos comprar outra licença usando suas informações de pagamento existentes. Se suas informações de pagamento não estão disponíveis, o usuário será criado como um usuário não licençado.

## <a name="manage-templates"></a>Gerenciar modelos

Você só pode excluir modelos que não precisa mais e adicionar novos. Para excluir um modelo:

1. No centro de administração, selecione **Usuários**  >  **Usuários ativos**.

2. Selecione **Modelos** e selecione **Gerenciar modelos** na listada.

3. Uma lista de modelos será exibida. Você pode excluir um modelo fazendo o seguinte:
    - Selecione um ou mais modelos e selecione **Excluir**. 
    - Selecione os três pontos à direita do nome do modelo e selecione **Excluir**.
    - Selecione o nome do modelo. Quando os detalhes do modelo aparecerem no lado direito da tela, selecione **Excluir modelo**.

## <a name="related-articles"></a>Artigos relacionados

[Adicionar usuários e atribuir licenças ao mesmo tempo](add-users.md)

[Remover um ex-funcionário do Microsoft 365](remove-former-employee.md)
  
