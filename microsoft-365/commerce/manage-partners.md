---
title: Gerenciar relações de parceiros
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
description: Saiba como trabalhar com provedores de soluções certificados pela Microsoft (parceiros) para comprar e gerenciar produtos e serviços para sua organização ou escola.
ms.openlocfilehash: d43aadf938cddfd5382fe4b3474eb92cc2b2763c
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114736"
---
# <a name="manage-partner-relationships"></a>Gerenciar relações de parceiros

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Você pode trabalhar com provedores de soluções certificados pela Microsoft (parceiros) para comprar e gerenciar produtos e serviços para sua organização ou escola. Há algumas etapas envolvidas na configuração das coisas.

1. Os administradores encontram e contatem um parceiro usando o formulário em <a href="https://www.microsoft.com/solution-providers/home" target="_blank">https://www.microsoft.com/solution-providers/home</a> .
2. Os parceiros enviam uma solicitação de email aos clientes para estabelecer uma relação de parceiro.
3. Os clientes aceitam o convite no Centro de administração do Microsoft 365 e começam a trabalhar com o parceiro.

## <a name="before-you-begin"></a>Antes de começar

Você deve ser um administrador global ou de cobrança para seguir estas etapas. Para obter mais informações, confira o artigo [Sobre funções de administrador](../admin/add-users/about-admin-roles.md).

## <a name="what-can-a-partner-do-for-my-organization-or-school"></a>O que um parceiro pode fazer para minha organização ou escola?

Há várias maneiras de um parceiro trabalhar com você. Com base nas suas necessidades comerciais afirmadas, eles escolhem um desses tipos quando enviam a solicitação para trabalhar com você.

| Tipo de parceiro | Descrição |
| ------ | ------------------- |
| Revendedor | Parceiros que vendem produtos da Microsoft para sua organização ou escola. |
| Administrador delegado | Parceiros que gerenciam produtos e serviços para sua organização ou escola. No Azure Active Directory (AD), o parceiro é um Administrador Global para seu locatário. Essa função permite que eles gerenciem serviços como criar contas de usuário, atribuir e gerenciar licenças e redefinições de senha. |
| Revendedor & administrador delegado | Parceiros que vendem e gerenciam produtos e serviços da Microsoft para sua organização ou escola. |
| Parceiro | Você pode dar uma conta de usuário ao seu parceiro em seu locatário e ele trabalhará com outros serviços Microsoft em seu nome. |
| Advisor | Os parceiros podem redefinir senhas e lidar com incidentes de suporte para você. |
| Parceiro mpSA (Contrato de Serviços & Serviços de & Microsoft) | Se você tiver trabalhado com vários parceiros por meio do programa MPSA, poderá permitir que eles vejam compras feitas uns pelos outros. |
| Parceiro de linha de negócios (LOB) | Os parceiros podem desenvolver, enviar e gerenciar aplicativos LOB específicos para sua organização ou escola. |

## <a name="find-a-partner"></a>Encontrar um parceiro

1. Acesse <a href="https://www.microsoft.com/en-us/solution-providers/home" target="_blank">https://www.microsoft.com/en-us/solution-providers/home</a>.
2. Insira seu local, escolha o tamanho da sua organização, adicione palavras-chave para os tipos de serviços necessários e selecione **Ir.**
3. Escolha um ou mais parceiros e, em seguida, selecione **Contato provedores selecionados.**
4. Preencha o formulário para descrever suas necessidades comerciais e selecione **Enviar.**

O parceiro contata você e oferece a oportunidade de saber mais sobre eles. Se você decidir trabalhar com eles, eles enviarão um convite por email para estabelecer uma relação de parceiro.

## <a name="review-and-accept-a-partner-relationship-and-microsoft-customer-agreement"></a>Analisar e aceitar um relacionamento de parceiro e o Contrato de Cliente Microsoft

Depois de encontrar um parceiro e decidir trabalhar com ele, ele envia um convite por email.

1. No email, selecione o link para ir para o Centro de administração do Microsoft 365.
2. Na página **Aceitar contrato & autorizar** parceiro, selecione o link para o Contrato de Cliente **Microsoft** e leia o documento.
3. Marque a caixa para confirmar que você leu o contrato.
4. Selecione **Aceitar & Autorizar.**
5. A lista de parceiros com quem você está trabalhando é exibida. Selecione qualquer parceiro para ver detalhes.

## <a name="review-and-accept-a-microsoft-customer-agreement"></a>Analisar e aceitar um Contrato de Cliente microsoft

Se você já tiver um parceiro, mas ainda não tiver assinado um Contrato de Cliente Microsoft, deverá aceitar o contrato antes que ele possa fazer compras ou gerenciar suas assinaturas em seu nome.

1. Se você receber um email do seu parceiro, selecione o link para ir para o centro de administração do Microsoft 365 ou vá para a página Aceitar <a href="https://go.microsoft.com/fwlink/?linkid=2116573" target="_blank">contrato.</a>
2. Selecione o link para o **Contrato de Cliente Microsoft** e leia o documento.
3. Marque a caixa para confirmar que você leu o contrato.
4. Selecione **Aceitar**.
5. A lista de parceiros com quem você está trabalhando é exibida. Selecione qualquer parceiro para ver detalhes.

## <a name="remove-partner-admin-roles"></a>Remover funções de administrador de parceiro

Dependendo da solicitação feita pelo parceiro, ao aceitar o convite, você concorda em dar a eles funções de administrador global e de helpdesk. Ao dar essas funções de administrador a um parceiro, você concede automaticamente a ele privilégios de administrador delegado no Azure AD. Para saber mais, confira Privilégios de administrador [delegado no Azure AD.](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad)

Se você não quiser dar as funções de administrador ao parceiro, cancele o convite em vez de aceitá-lo.

Você pode remover funções de administrador de um parceiro a qualquer momento. Remover as funções de administrador não remove a relação de parceiros. Eles ainda podem trabalhar com você em uma capacidade diferente, como um Revendedor. Se você decidir que não deseja mais trabalhar com um parceiro, entre em contato com seu parceiro para encerrar a relação.

1. No centro de administração, vá para a página **Relacionamentos**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">de Parceiro de</a> Cobrança.
2. Na página **Relações de parceiro,** selecione a linha que contém o nome do parceiro que você deseja remover.
3. Selecione a linha que contém o nome do parceiro.
4. Na página do parceiro, selecione **Remover funções.**
5. Na caixa **de diálogo Remover funções?** , selecione **Sim**.
