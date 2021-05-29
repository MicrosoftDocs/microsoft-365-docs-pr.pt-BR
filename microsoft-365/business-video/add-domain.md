---
title: Adicionar um domínio
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Sua organização pode precisar de vários domínios para que os clientes possam encontrá-lo. Saiba como adicionar outro domínio à sua assinatura.
ms.openlocfilehash: 13fc3cf73a112945db4372231cce70c1837c1321
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706425"
---
# <a name="add-another-domain"></a>Adicionar outro domínio

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

Sua empresa pode precisar de vários nomes de domínio para finalidades diferentes. Por exemplo, talvez você queira adicionar uma ortografia diferente do nome da sua empresa, pois os clientes já o estão usando e suas comunicações falharam ao entrar em contato com você.

## <a name="try-it"></a>Experimente!

1. No centro Microsoft 365 de administração, escolha **Configurar**.
1. Em **Obter sua configuração de domínio personalizado,** selecione **Exibir**.
1. Escolha **Gerenciar** e, em seguida, **Adicionar domínio**.
1. Insira o novo nome de domínio que você deseja adicionar e selecione **Next**.
1. Entre no registrador de domínios, nesse caso, GoDaddy e selecione **Next**.
1. Se solicitado, entre no registrador e escolha **Autorizar**.
1. Escolha **Adicionar os registros DNS para mim** e selecione **Next**.
1. Escolha os serviços para seu novo domínio e desempure as caixas de seleção de todos os serviços que serão manipulados por um domínio diferente. Por exemplo, se você deseja apenas usar o novo domínio para email, escolha **Exchange**, e desem vez das caixas de seleção para **Skype for Business** e **Gerenciamento de Dispositivo Móvel do Office 365**.
1. Selecione **Próximo,** **Autorizar**, **Próximo** e, em **seguida, Concluir**. Seu novo domínio foi adicionado.

Para receber emails em seu novo domínio, você precisará adicionar um novo alias de email para cada usuário:

1. Selecione **Usuários,** **Usuários ativos** e selecione o usuário que receberá o novo alias.
1. Escolha **Gerenciar aliases de email** e adicione um **alias**.
1. Insira o nome de usuário e escolha o novo domínio na listada.
1. Selecione **Salvar alterações** e feche a janela.
1. Repita estas etapas para cada usuário que deve receber emails no novo domínio.

## <a name="related-content"></a>Conteúdo relacionado

[Adicionar um domínio a Microsoft 365](../admin/setup/add-domain.md) (artigo)\
[Adicionar registros DNS para conectar seu domínio](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) (artigo)\
[Alterar os servidores de nomes para configurar o Microsoft 365 com qualquer registrador de domínio ](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md) (artigo)\
[Perguntas frequentes sobre domínios](../admin/setup/domains-faq.yml) (artigo)