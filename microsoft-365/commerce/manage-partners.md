---
title: Gerenciar relacionamentos de parceiros
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
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Saiba como trabalhar com os fornecedores de soluções certificadas pela Microsoft (parceiros) para comprar e gerenciar produtos e serviços para sua organização ou escola.
ms.openlocfilehash: 6cce3640a321d1eab31d527369a303cfde646718
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430017"
---
# <a name="manage-partner-relationships"></a>Gerenciar relacionamentos de parceiros

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Você pode trabalhar com os fornecedores de soluções certificadas pela Microsoft (parceiros) para comprar e gerenciar produtos e serviços para sua organização ou escola. Há algumas etapas envolvidas na configuração das coisas.

1. Os administradores localizam e contatam um parceiro usando o formulário em <a href="https://www.microsoft.com/solution-providers/home" target="_blank">https://www.microsoft.com/solution-providers/home</a> .
2. Os parceiros enviam uma solicitação de email aos clientes para estabelecer uma relação de parceria.
3. Os clientes aceitam o convite no centro de administração do Microsoft 365 e começam a trabalhar com o parceiro.

## <a name="before-you-begin"></a>Antes de começar

Você deve ser um administrador global ou de cobrança para executar estas etapas. Para obter mais informações, confira o artigo [Sobre funções de administrador](../admin/add-users/about-admin-roles.md).

## <a name="what-can-a-partner-do-for-my-organization-or-school"></a>O que um parceiro pode fazer para minha organização ou escola?

Há várias maneiras pelas quais um parceiro pode trabalhar com você. Com base nas necessidades de negócios declaradas, eles escolhem um desses tipos quando enviam suas solicitações para trabalhar com você.

| Tipo de parceiro | Descrição |
| ------ | ------------------- |
| Vendedor | Parceiros que vendem produtos da Microsoft para sua organização ou escola. |
| Administrador delegado | Parceiros que gerenciam produtos e serviços para sua organização ou escola. No Azure Active Directory (AD), o parceiro é um administrador global para seu locatário. Essa função permite que eles gerenciem serviços como a criação de contas de usuário, a atribuição e o gerenciamento de licenças e redefinições de senha. |
| Revendedor & administrador delegado | Parceiros que vendem e gerenciam os produtos e serviços da Microsoft para sua organização ou escola. |
| Parceiro | Você dá ao seu parceiro uma conta de usuário em seu locatário e ele funciona com outros serviços da Microsoft em seu nome. |
| Supervisor | Os parceiros podem redefinir senhas e lidar com incidentes de suporte para você. |
| Microsoft Products MPSA (contrato de serviços de &) | Se você trabalhou com vários parceiros por meio do programa MPSA, poderá permitir que eles vejam as compras feitas por cada um. |
| Parceiro de linha de negócios (LOB) | Os parceiros podem desenvolver, enviar e gerenciar aplicativos LOB específicos para sua organização ou escola. |

## <a name="find-a-partner"></a>Localizar um parceiro

1. Acesse <a href="https://www.microsoft.com/en-us/solution-providers/home" target="_blank">https://www.microsoft.com/en-us/solution-providers/home</a>.
2. Insira seu local, escolha o tamanho da sua organização, adicione palavras-chave para o tipo de serviços que você precisa e, em seguida, selecione **ir**.
3. Escolha um ou mais parceiros e, em seguida, selecione **contatar provedores selecionados**.
4. Preencha o formulário para descrever suas necessidades de negócios e selecione **Enviar**.

O parceiro entra em contato com você e dá a você a oportunidade de aprender mais sobre eles. Se você decidir trabalhar com eles, ele enviará um convite por email para estabelecer uma relação de parceiro.

## <a name="review-and-accept-a-partner-relationship-and-microsoft-customer-agreement"></a>Revisar e aceitar uma relação de parceiro e um contrato de cliente da Microsoft

Depois que você encontrar um parceiro e optar por trabalhar com eles, ele enviará um convite por email.

1. No email, selecione o link para ir para o centro de administração do Microsoft 365.
2. Na página **aceitar contrato & autorizar parceiro** , selecione o link para o **contrato de cliente da Microsoft**e leia o documento.
3. Marque a caixa para confirmar que você leu o contrato.
4. Selecione **aceitar & autorizar**.
5. A lista de parceiros com os quais você está trabalhando é exibida. Selecione qualquer parceiro para ver detalhes.

## <a name="review-and-accept-a-microsoft-customer-agreement"></a>Revisar e aceitar um contrato de cliente da Microsoft

Se você já tem um parceiro, mas ainda não assinou um contrato de cliente da Microsoft, você deve aceitar o contrato antes que eles possam fazer compras ou gerenciar suas assinaturas em seu nome.

1. Se você receber um email do seu parceiro, selecione o link para acessar o centro de administração do Microsoft 365 ou vá para a página <a href="https://go.microsoft.com/fwlink/?linkid=2116573" target="_blank">aceitar contrato</a> .
2. Selecione o link para o **contrato de cliente da Microsoft** e leia o documento.
3. Marque a caixa para confirmar que você leu o contrato.
4. Selecione **aceitar**.
5. A lista de parceiros com os quais você está trabalhando é exibida. Selecione qualquer parceiro para ver detalhes.

## <a name="remove-partner-admin-roles"></a>Remover funções de administrador de parceiro

Dependendo da solicitação feita pelo parceiro, quando você aceita o convite, você concorda em fornecer funções de administrador global e de assistência técnica. Ao conceder essas funções de administrador a um parceiro, você concede automaticamente a elas privilégios de administrador delegados no Azure AD. Para saber mais, confira [privilégios de administrador delegados no Azure ad](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad).

Se você não quiser dar as funções de administrador ao parceiro, cancele o convite em vez de aceitá-lo.

Você pode remover as funções de administrador de um parceiro a qualquer momento. Remover as funções de administrador não remove o relacionamento do parceiro. Eles ainda podem trabalhar com você em uma capacidade diferente, como um revendedor. Se você decidir que não deseja mais trabalhar com um parceiro, entre em contato com seu parceiro para terminar a relação.

1. No centro de administração, vá para a **Billing**  >  página<a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">relações de parceiros</a> de cobrança.
2. Na página **relações de parceiros** , selecione a linha que contém o nome do parceiro que você deseja remover.
3. Selecione a linha que contém o nome do parceiro.
4. Na página parceiro, selecione **remover funções**.
5. Na caixa de diálogo **remover funções?** , selecione **Sim**.
