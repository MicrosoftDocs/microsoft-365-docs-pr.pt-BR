---
title: Criar regras de e-mail para ransomware
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Saiba como criar regras de email para evitar ransomware.
ms.openlocfilehash: 96822916753f2f70d481c213e7e31046f7081446
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580493"
---
# <a name="create-email-rules-to-prevent-ransomware"></a>Criar regras de email para evitar ransomware

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

Microsoft 365 ajuda a proteger sua empresa contra ransomware, impedindo que arquivos potencialmente perigosos, como JavaScript, lote e executáveis, seja aberto em Outlook. Para aumentar esse nível de proteção adicionando regras que bloqueiam ou avisam sobre tipos adicionais de arquivos, siga estas etapas.

## <a name="try-it"></a>Experimente!

1. No centro de administração em [https://admin.microsoft.com](https://admin.microsoft.com) , escolha **Exchange** em Centros **de administração**.
1. No menu à esquerda, escolha **fluxo de emails**.
1. Na guia regras, escolha a seta ao lado do símbolo de mais (+) e escolha **Criar uma nova regra**.
1. Na nova **página de** regra, insira um nome para sua regra, role até a parte inferior e escolha **Mais opções**.
1. Em **Aplicar esta regra se**, selecione Qualquer **anexo** e selecione extensão de arquivo inclui **essas palavras**.
1. Na caixa em especificar palavras ou **frases,** insira as extensões de arquivo às quais você deseja que a regra seja aplicada, como extensões de arquivo que podem conter macros. Use o símbolo plus (+) para adicioná-los um por vez.

    Saiba mais sobre tipos de arquivo lendo [Proteger contra ransomware](../admin/security-and-compliance/secure-your-business-data.md#ransomware).

1. Role para baixo para revisar sua lista e escolha **OK**.
1. Na nova **página de** regra, escolha **adicionar condição** e escolha uma condição em Fazer **o seguinte.**
1. Você tem muitas opções de regra para escolher, mas neste exemplo, optaremos por **Notificar** o destinatário com uma mensagem .
1. Insira o texto da mensagem para sua notificação e escolha **OK**.
1. Opcional: na nova página **de** regra, escolha **adicionar** exceção e insira qualquer detalhe para exceções à sua regra, como mensagens de senders confiáveis.
1. Na nova página de regra, escolha **Salvar** e revise as informações de resumo de regras fornecidas.