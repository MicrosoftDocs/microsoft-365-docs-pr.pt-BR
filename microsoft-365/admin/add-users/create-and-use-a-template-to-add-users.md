---
title: Criar e usar um modelo para adicionar usuários
f1.keywords:
- NOCSH
ms.author: v-sharos
author: shars
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
search.appverid:
- MET150
- MOE150
description: Você pode criar e usar um modelo para economizar tempo e padronizar as configurações ao adicionar vários usuários.
ms.openlocfilehash: 340d0ae3329b441c2b9773ba06e4f9e69be88526
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42353242"
---
# <a name="create-and-use-a-template-to-add-users"></a>Criar e usar um modelo para adicionar usuários

Você pode criar e usar um modelo para economizar tempo e padronizar as configurações ao adicionar vários usuários. Os modelos são particularmente úteis se você tiver usuários que compartilham muitas propriedades comuns, como aqueles que têm a mesma função e funcionam no mesmo local e aqueles que exigem o mesmo software. Por exemplo, você pode ter uma equipe de engenheiros de suporte que trabalham no mesmo escritório.  

## <a name="create-a-template"></a>Criar um modelo

Os modelos são fáceis de&mdash;criar é possível selecionar **os** > **modelos de usuário****ativos** > dos usuários e, em seguida, selecionar **Adicionar um modelo** na lista suspensa ou adicionar um novo usuário e quando terminar, você terá a opção de salvar a entrada como um modelo.

Quando você cria um modelo após adicionar um usuário, os valores escolhidos para as seguintes configurações são salvos no modelo:

- Nome de domínio
- Opção de configurações de senha: você pode optar por criar senhas ou fazer com que elas sejam geradas automaticamente
- Opção de senha de uso único: você pode exigir que o usuário crie uma nova senha após a primeira entrada
- Local da licença
- Opções de licença
- Opções de aplicativo
- Role
- A maioria das informações de perfil, como **perfil de trabalho**, **Departamento**, **escritório**, **telefone comercial**e **endereço** 

As informações a seguir são específicas do usuário e não são salvas no modelo:

- Nome e sobrenome
- Nome diferenciado (DN)
- Nome de usuário
- Escolha para enviar a senha por email e para quem o email de senha é enviado
- Número de telefone celular

Se você optar por não inserir informações para uma configuração dentro de uma seção, esse valor ficará em branco e essa configuração não será exibida no modelo. Por exemplo, se você deixar o **título do trabalho** em branco, quando você revisar seu modelo e quando você usa o modelo, o **cargo** não aparecerá. Se você deixar todas as configurações da seção de **perfil** em branco, a seção de **perfil** exibirá **nenhuma fornecida** no modelo final.

Ao criar um modelo selecionando a opção **Adicionar um modelo** , você pode escolher quais valores serão concluídos. Tudo o que for deixado em branco aparecerá como **nenhum fornecido** no modelo.

## <a name="use-a-template-to-add-a-user"></a>Usar um modelo para adicionar um usuário

Para usar um modelo existente para adicionar um usuário:

1. No centro de administração, selecione usuários**ativos**do **usuário** > .

2. Selecione **modelos de usuário**e, em seguida, selecione um modelo na lista suspensa. (A lista conterá apenas os modelos criados, e não os criados por outros administradores.)

 > [!NOTE]
 > Você também pode usar um modelo para adicionar um usuário selecionando **modelos** > de usuário**gerenciar modelos**, selecionando um modelo e, em seguida, selecionando **usar modelo**.

3. Siga as etapas para criar um usuário a partir do modelo selecionado.

> [!NOTE]
> Se você tiver licenças insuficientes disponíveis para um usuário que você adicionar e suas informações de pagamento estiverem disponíveis, tentaremos comprar outra licença usando suas informações de pagamento existentes. Se suas informações de pagamento não estiverem disponíveis, o usuário será criado como um usuário não licenciado.

## <a name="manage-templates"></a>Gerenciar modelos

Você pode excluir facilmente modelos que não são mais necessários e adicionar novos. Para excluir um modelo:

1. No centro de administração, selecione usuários**ativos**do **usuário** > .

2. Selecione **modelos**e, em seguida, selecione **gerenciar modelos** na lista suspensa.

3. Uma lista de modelos será exibida. Você pode excluir um modelo executando qualquer um dos seguintes procedimentos:
    - Selecione um ou mais modelos e, em seguida, selecione **excluir**. 
    - Selecione os três pontos à direita do nome do modelo e, em seguida, selecione **excluir**.
    - Selecione o nome do modelo. Quando os detalhes do modelo aparecem no lado direito da tela, selecione **excluir modelo**.

## <a name="related-articles"></a>Artigos relacionados

[Adicionar usuários individualmente ou em massa ao Office 365](add-users.md)

[Remover um ex-funcionário do Office 365](remove-former-employee.md)
  
