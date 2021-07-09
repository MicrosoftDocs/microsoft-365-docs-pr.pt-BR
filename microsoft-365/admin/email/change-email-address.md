---
title: Mudar seu endereço de email para usar seu domínio personalizado
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: Altere seu endereço de email para um endereço de email amigável como tom@fourthcoffee.com comprando um nome de domínio e adicionando-o a Microsoft 365.
ms.openlocfilehash: 7fb113c0efd6462c4c703956a20c390f2d555d5f
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341455"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>Mudar seu endereço de email para usar seu domínio personalizado

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**. 
  
::: moniker range="o365-worldwide"

Seu endereço de email inicial Microsoft 365 inclui .onmicrosoft.com, como tom@fourthcoffee.onmicrosoft.com. Você pode alterá-lo para um endereço mais fácil de memorizar, como pedro@fourthcoffee.com. Você primeiro precisará do seu próprio nome de domínio, como fourthcoffee.com. Se você já possui um, excelente! Caso contrário, você pode aprender como [comprar um de um registrador de domínios](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-germany"

Seu endereço de email inicial Office 365 Alemanha inclui .onmicrosoft.de, como tom@fourthcoffee.onmicrosoft.de. Você pode alterá-lo para um endereço mais amigável como tom@fourthcoffee.de. Você precisará de seu próprio nome de domínio, como fourthcoffee.de primeiro. Se você já possui um, excelente! Caso contrário, você pode aprender como [comprar um de um registrador de domínios](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-21vianet"

Seu endereço de email inicial no Office 365 operado pela 21Vianet inclui partner.onmschina.cn, como tom@fourthcoffee.partner.onmschina.cn. Você pode alterá-lo para um endereço mais amigável como tom@fourthcoffee.cn. Você precisará de seu próprio nome de domínio, como fourthcoffee.cn primeiro. Se você já possui um, excelente! Caso contrário, você pode aprender como [comprar um de um registrador de domínios](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

Quando você alterar o email do seu domínio para chegar ao Microsoft 365, atualizando o registro MX do seu domínio durante a instalação, TODOS os emails enviados para esse domínio começarão a Microsoft 365. Certifique-se de ter adicionado usuários e criado caixas de correio no Microsoft 365 para todos que têm email em seu domínio ANTES de alterar o registro MX. Não deseja mover emails para todos em seu domínio para Microsoft 365? Você pode tomar medidas para [Microsoft 365 com apenas alguns endereços de email.](../misc/pilot-microsoft-365-from-my-custom-domain.md)
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Altere seu endereço de email para usar seu domínio personalizado usando o Centro de administração do Microsoft 365

Você deve ser um administrador global para executar essas etapas.

::: moniker range="o365-worldwide"

1. Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Vá para o <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>centro de administração em .

::: moniker-end

2. Vá para a **página**  >  **Domínios de** Instalação.

3. Na página **Domínios**, selecione **Adicionar domínio**.

4. Siga as etapas para confirmar se você é o seu domínio. Você será orientado a configurar tudo corretamente com seu domínio Microsoft 365.

5. Vá para **Usuários**  >  **Usuários ativos**.

6. Selecione um usuário para editar seu nome de usuário e alterá-lo para o domínio que você acabou de adicionar.

> [!NOTE]
> Se você não estiver usando uma licença Exchange, não poderá usar o domínio para enviar ou receber emails do Microsoft 365 locatário.
  
## <a name="related-content"></a>Conteúdo relacionado

[Comprar um domínio personalizado usando Microsoft 365](../get-help-with-domains/buy-a-domain-name.md) (artigo)\
[Gerenciar domínios](../get-help-with-domains/index.yml) (página de link)\
[Perguntas frequentes sobre domínios](../setup/domains-faq.yml) (artigo)