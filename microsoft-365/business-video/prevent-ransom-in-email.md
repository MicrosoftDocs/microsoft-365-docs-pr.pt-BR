---
title: Criar regras de email para ransomware
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: Saiba como criar regras de email para impedir o ransomware.
ms.openlocfilehash: 85898480438225848fc09db9a9c507045f8a182c
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701420"
---
# <a name="create-email-rules-to-prevent-ransomware"></a>Criar regras de email para impedir o ransomware

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

A Microsoft 365 ajuda a proteger sua empresa contra o ransomware, impedindo que arquivos potencialmente perigosos, como JavaScript, lote e executáveis, sejam abertos no Outlook. Para aumentar esse nível de proteção adicionando regras que bloqueiem ou avisem sobre tipos adicionais de arquivos, siga estas etapas.

## <a name="try-it"></a>Experimente!

1. No centro de administração [https://admin.microsoft.com](https://admin.microsoft.com) , escolha **Exchange** em **centros de administração**.
1. No menu à esquerda, escolha fluxo de **email**.
1. Na guia regras, escolha a seta ao lado do símbolo de adição (+) e, em seguida, escolha **criar uma nova regra**.
1. Na página **nova regra** , insira um nome para a regra, role até a parte inferior e, em seguida, escolha **mais opções**.
1. Em **aplicar esta regra se**, selecione **qualquer anexo** e, em seguida, selecione **extensão de arquivo inclui essas palavras**.
1. Na caixa em **especificar palavras ou frases**, insira as extensões de arquivo às quais você deseja aplicar a regra, como extensões de arquivo que podem conter macros. Use o símbolo de adição (+) para adicionar um de cada vez.

    Saiba mais sobre tipos de arquivo lendo [proteger contra ransomware](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware).

1. Role para baixo para revisar sua lista e, em seguida, escolha **OK**.
1. Na página **nova regra** , escolha **Adicionar condição** e, em seguida, escolha uma condição em **faça o seguinte**.
1. Você tem muitas opções de regra para escolher, mas neste exemplo, vamos optar por **notificar o destinatário com uma mensagem**.
1. Insira o texto da mensagem para sua notificação e, em seguida, escolha **OK**.
1. Opcional: na página **nova regra** , escolha **Adicionar exceção** e insira os detalhes para exceções à regra, como mensagens de remetentes confiáveis.
1. Na página nova regra, escolha **salvar** e revise as informações de resumo da regra fornecidas.