---
title: Criar regras de e-mail para ransomware
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como criar regras de email para evitar ransomware.
ms.openlocfilehash: 3b45af71aa26beb31e21f5db662091f46343f97d
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926109"
---
# <a name="create-email-rules-to-prevent-ransomware"></a>Criar regras de email para evitar ransomware

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

O Microsoft 365 ajuda a proteger sua empresa contra ransomware, impedindo que arquivos potencialmente perigosos, como JavaScript, lote e executáveis, seja abertos no Outlook. Para aumentar esse nível de proteção adicionando regras que bloqueiam ou avisam sobre tipos adicionais de arquivos, siga estas etapas.

## <a name="try-it"></a>Experimente!

1. No centro de administração em [https://admin.microsoft.com](https://admin.microsoft.com) , escolha **Exchange** em Centros **de administração**.
1. No menu à esquerda, escolha o **fluxo de emails.**
1. Na guia regras, escolha a seta ao lado do símbolo de adição (+) e, em seguida, **escolha Criar uma nova regra.**
1. Na nova **página de** regras, insira um nome para a regra, role até a parte inferior e escolha **Mais opções.**
1. Under **Apply this rule if**, select Any **attachment**, and then select file **extension includes these words**.
1. Na caixa abaixo, especifique palavras ou **frases,** insira as extensões de arquivo às quais você deseja que a regra seja aplicada, como extensões de arquivo que podem conter macros. Use o símbolo de adição (+) para adicioná-los um de cada vez.

    Saiba mais sobre tipos de arquivo lendo [Proteger contra ransomware.](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware)

1. Role para baixo para revisar sua lista e escolha **OK.**
1. Na nova **página de regras,** escolha **adicionar condição** e, em seguida, escolha uma condição em Fazer **o seguinte.**
1. Você tem muitas opções de regra para escolher, mas neste exemplo, escolheremos notificar o **destinatário com uma mensagem.**
1. Insira o texto da mensagem para a notificação e escolha **OK.**
1. Opcional: na nova página  **de** regras, escolha adicionar exceção e insira todos os detalhes das exceções à sua regra, como mensagens de envios confiáveis.
1. Na nova página de regras, escolha **Salvar** e revise as informações de resumo de regra fornecidas.