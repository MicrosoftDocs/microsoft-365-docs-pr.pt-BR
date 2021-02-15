---
title: Criar e usar um modelo para adicionar usuários
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Você pode criar e usar um modelo para economizar tempo e padronizar as configurações ao adicionar vários usuários.
ms.openlocfilehash: aef5085da603c38b37544b76c5336c9bfe4edd24
ms.sourcegitcommit: 2d3e85173c65a9e0ce92624a80ed7a9839f5b8bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49123412"
---
# <a name="create-and-use-a-template-to-add-users"></a>Criar e usar um modelo para adicionar usuários

Você pode criar e usar um modelo para economizar tempo e padronizar as configurações ao adicionar vários usuários. Os modelos são particularmente úteis se você tiver usuários que compartilham muitas propriedades comuns, como aqueles que têm a mesma função e trabalham no mesmo local e aqueles que exigem o mesmo software. Por exemplo, você pode ter uma equipe de engenheiros de suporte que trabalham no mesmo escritório.  

## <a name="create-a-template"></a>Criar um modelo

Templates are easy to create you &mdash; can select **Users**  >  **Active users** User  >  **templates**, and then select Add a **template** from the drop-down list, or you can add a new user and when you are finished, you will have the option of saving the entry as a template.

Quando você cria um modelo após adicionar um usuário, os valores que você escolhe para as seguintes configurações são salvos no modelo:

- Nome de domínio
- Opção de configurações de senha: você pode optar por criar senhas ou gerar automaticamente
- Opção de senha única: você pode exigir que o usuário crie uma nova senha após o primeiro login
- Local da licença
- Opções de licença
- Opções do aplicativo
- Função
- Most profile information, such as **Job profile**, **Department**, **Office**, **Office phone,** and **Street address** 

As informações a seguir são específicas do usuário e não são salvas no modelo:

- Nome e sobrenome
- Nome de exibição
- Nome de usuário
- Opção para enviar a senha por email e para quem o email de senha é enviado
- Número de telefone celular

Se você optar por não inserir informações para uma configuração em uma seção, esse valor ficará em branco e essa configuração não será exibida no modelo. Por exemplo, se você deixar **o** cargo em branco, ao revisar seu modelo e ao usar seu **modelo,** o cargo não aparecerá. Se você deixar todas as **configurações da** seção Perfil em branco, a seção **Perfil** exibirá **Nenhum fornecido** em seu modelo final.

Ao criar um modelo selecionando **a opção Adicionar um** modelo, você pode escolher quais valores preencher. Tudo o que for deixado em branco aparecerá **como Nenhum fornecido** no modelo.

## <a name="use-a-template-to-add-a-user"></a>Usar um modelo para adicionar um usuário

Para usar um modelo existente para adicionar um usuário:

1. No centro de administração, selecione **Usuários**  >  **Ativos.**

2. Selecione **Modelos de usuário** e selecione um modelo na lista lista listada. (A lista conterá apenas os modelos que você criou, não aqueles criados por outros administradores.)

   > [!NOTE]
   > Você também pode usar um modelo para adicionar um usuário selecionando Modelos de usuário Gerenciar modelos, selecionando um modelo e  >  selecionando **Usar modelo.**

3. Siga as etapas para criar um usuário a partir do modelo selecionado.

   > [!NOTE]
   > Se você tiver licenças insuficientes disponíveis para um usuário que você adicionar e suas informações de pagamento estão disponíveis, tentaremos comprar outra licença usando suas informações de pagamento existentes. Se suas informações de pagamento não estão disponíveis, o usuário será criado como um usuário não licençado.

## <a name="manage-templates"></a>Gerenciar modelos

Você só pode excluir modelos de que não precisa mais e adicionar novos. Para excluir um modelo:

1. No centro de administração, selecione **Usuários**  >  **Ativos.**

2. Selecione **Modelos** e, em **seguida, selecione Gerenciar modelos** na lista drop-down.

3. Uma lista de modelos será exibida. Você pode excluir um modelo fazendo o seguinte:
    - Selecione um ou mais modelos e selecione **Excluir.** 
    - Selecione os três pontos à direita do nome do modelo e selecione **Excluir**.
    - Selecione o nome do modelo. Quando os detalhes do modelo aparecerem no lado direito da tela, selecione **Excluir modelo.**

## <a name="related-articles"></a>Artigos relacionados

[Adicionar usuários e atribuir licenças ao mesmo tempo](add-users.md)

[Remover um ex-funcionário do Microsoft 365](remove-former-employee.md)
  
