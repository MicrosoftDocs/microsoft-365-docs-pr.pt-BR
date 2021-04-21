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
description: Saiba como adicionar outro domínio à sua assinatura.
ms.openlocfilehash: a641005913f7dfd866366f0f8065019dd5c17fe8
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903737"
---
# <a name="add-another-domain"></a>Adicionar outro domínio

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

Sua empresa pode precisar de vários nomes de domínio para finalidades diferentes. Por exemplo, talvez você queira adicionar uma ortografia diferente do nome da sua empresa, pois os clientes já o estão usando e suas comunicações falharam ao entrar em contato com você.

## <a name="try-it"></a>Experimente!

1. No Centro de administração do Microsoft 365, escolha **Configurar**.
1. Em **Obter sua configuração de domínio personalizado,** selecione **Exibir**.
1. Escolha **Gerenciar** e, em seguida, **Adicionar domínio**.
1. Insira o novo nome de domínio que você deseja adicionar e selecione **Next**.
1. Entre no registrador de domínios, nesse caso, GoDaddy e selecione **Next**.
1. Se solicitado, entre no registrador e escolha **Autorizar**.
1. Escolha **Adicionar os registros DNS para mim** e selecione **Next**.
1. Escolha os serviços para seu novo domínio e desempure as caixas de seleção de todos os serviços que serão manipulados por um domínio diferente. Por exemplo, se você quiser apenas usar o novo domínio para email, escolha **Exchange** e des limpar as caixas de seleção do **Skype for Business** e gerenciamento de dispositivos móveis para o Office **365**.
1. Selecione **Próximo,** **Autorizar**, **Próximo** e, em **seguida, Concluir**. Seu novo domínio foi adicionado.

Para receber emails em seu novo domínio, você precisará adicionar um novo alias de email para cada usuário:

1. Selecione **Usuários,** **Usuários ativos** e selecione o usuário que receberá o novo alias.
1. Escolha **Gerenciar aliases de email** e adicione um **alias**.
1. Insira o nome de usuário e escolha o novo domínio na listada.
1. Selecione **Salvar alterações** e feche a janela.
1. Repita estas etapas para cada usuário que deve receber emails no novo domínio.

## <a name="related-content"></a>Conteúdo relacionado

Adicionar um domínio ao [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) (artigo) Adicionar registros [DNS](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) para conectar seu domínio (artigo) Alterar nameservers para configurar o [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar) com qualquer registrador de domínios (artigo) [Perguntas frequentes](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) sobre domínios (artigo)