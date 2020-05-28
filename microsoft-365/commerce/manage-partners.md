---
title: Gerenciar relacionamentos de parceiros
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
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Saiba como trabalhar com os fornecedores de soluções certificadas pela Microsoft (parceiros) para comprar e gerenciar produtos e serviços para sua organização ou escola.
keywords: parceiro, provedor de soluções
ms.openlocfilehash: 752c9e0237bbdde7be996b5675848e948e866dce
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402589"
---
# <a name="manage-partner-relationships"></a>Gerenciar relacionamentos de parceiros

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Você pode trabalhar com os fornecedores de soluções certificadas pela Microsoft (parceiros) para comprar e gerenciar produtos e serviços para sua organização ou escola. Há algumas etapas envolvidas na configuração das coisas.

- Os administradores localizam e contatam um parceiro usando o formulário em <a href="https://www.microsoft.com/en-us/solution-providers/home" target="_blank">https://www.microsoft.com/en-us/solution-providers/home</a> .
- Os parceiros enviam uma solicitação de email aos clientes para estabelecer uma relação de parceria.
- Os clientes aceitam o convite no centro de administração do Microsoft 365 e começam a trabalhar com o parceiro.

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
| Parceiro de computador OEM | Os parceiros podem carregar IDs de dispositivo para computadores que você está [Gerenciando com o AutoPilot](https://docs.microsoft.com/microsoft-store/add-profile-to-devices). |
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

## <a name="remove-partner-admin-privileges"></a>Remover privilégios de administrador de parceiro

Dependendo da solicitação feita pelo parceiro, parte da aceitação do convite inclui concordar em conceder privilégios de administrador delegados para eles. Para obter mais informações, confira [privilégios de administrador delegado no Azure ad](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad).

Se você não quiser delegar privilégios de administrador para o parceiro, cancele o convite em vez de aceitá-lo.

Se você delegar privilégios de administrador para um parceiro, poderá remover esses privilégios a qualquer momento. Remover privilégios de administrador não remove o relacionamento do parceiro. Eles ainda podem trabalhar com você, por exemplo, como revendedor.

1. No centro de administração, vá para a **Billing**  >  página<a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">contas de cobrança</a> de cobrança.
2. Na página **contas de cobrança** , selecione a guia **relacionamentos de parceiros** .
3. Selecione a linha que contém o nome do parceiro.
4. Na página parceiro, selecione **remover funções de administrador**.

## <a name="delete-a-partner-relationship"></a>Excluir uma relação de parceiro

Se você decidir que não deseja mais trabalhar com um parceiro, poderá finalizar a relação. No entanto, você só pode excluir as relações nas quais o parceiro é um administrador delegado ou um supervisor. Para todos os outros tipos de parceiros, entre em contato com seu parceiro para finalizar a relação.

1. No centro de administração, vá para a **Billing**  >  página<a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">contas de cobrança</a> de cobrança.
2. Na página **contas de cobrança** , selecione a guia **relacionamentos de parceiros** .
3. Selecione a linha que contém o nome do parceiro.
4. Na página detalhes do parceiro, selecione **excluir parceiro**.
