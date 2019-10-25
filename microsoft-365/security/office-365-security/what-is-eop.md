---
title: O que é EOP
ms.author: tracyp
author: msfttracyp
ms.reviewer: andypunt
manager: dansimp
ms.date: 02/25/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 393b0050-7c7e-49e6-a03d-b1e09fe4de9e
description: Este documento introdutório o ajudará a entender o Exchange Online Protection (EOP) e uma terminologia importante. Isso se aplica aos clientes do Office 365 que estão protegendo caixas de correio hospedadas em nuvem do Exchange Online e clientes autônomos do EOP que estão protegendo caixas de correio locais, como o Exchange Server 2016.
ms.openlocfilehash: 2e4de0b62b24498b1153c713523418193e8694b4
ms.sourcegitcommit: 83b919f8a7fcc4f75044ffc09fecd66fb4ed35b5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2019
ms.locfileid: "37662517"
---
# <a name="what-is-exchange-online-protection-eop"></a>O que é proteção do Exchange Online (EOP)

O Exchange Online Protection (EOP) é um serviço de filtragem de email baseado em nuvem que ajuda a proteger sua organização contra spam e malware. Se você tiver caixas de correio no Office 365, elas serão automaticamente protegidas por EOP, uma vez que ela faz parte do serviço. Isso inclui as organizações que têm caixas de correio no Office 365 e no local, que costuma ser conhecido como um cenário híbrido. O EOP autônomo também está disponível para clientes que não têm caixas de correio na nuvem, mas querem proteger suas caixas de correio locais.

O EOP tenta filtrar o lixo eletrônico, mantendo a caixa de entrada limpa do conteúdo que os usuários não desejam ver. Normalmente, o lixo eletrônico é enviado para a pasta lixo eletrônico. Alguns usuários gostam de verificar se a filtragem está fazendo o que eles desejam, para que a pasta lixo eletrônico seja uma maneira fácil de os usuários verificarem por conta própria.  

> [!TIP]
> É uma boa coisa quando o lixo eletrônico ou emails mal incorretos entram na pasta lixo eletrônico automaticamente. O serviço fará o que for necessário com base no que o padrão ou o estado de configurações personalizadas do administrador. Em outras palavras, os usuários não devem se preocupar em ver uma grande quantidade de mensagens de spam na pasta lixo eletrônico. Se os administradores preferem mover todo o lixo eletrônico para fora da visão, então a quarentena deve ser configurada. Para obter mais detalhes, consulte o artigo sobre [mensagens de email em quarentena no Office 365](quarantine-email-messages.md) .

## <a name="important-terms"></a>Termos importantes

**Entrada**: mensagens que estão chegando no Office 365.

**Saída**: mensagens que estão saindo do Office 365.

**Interno**: mensagens de alguém dentro da organização para alguém dentro da organização. Isso inclui os clientes que estão em cenários híbridos e uma caixa de correio pode ser local e a outra caixa de correio está na nuvem.

**Falso negativo (FN)**: spam e outros lixos que são enviados incorretamente para a caixa de entrada.

**Falso positivo (FP)**: mensagens legítimas que são marcadas incorretamente como spam e colocadas na pasta ou quarentena do lixo eletrônico.

**Spam, também conhecido como email não solicitado**: isso vem na forma de propaganda comercial, correntes, correspondências políticas, etc. Essa é uma mensagem de email informando que os usuários não se inscrevem e de spammers que estão tentando solicitar produtos ou tentar confirmar a fraude.

**Phish**: phishing é um tipo especial de spam destinado a induzir você a fornecer informações pessoais com o objetivo de confirmar o roubo de identidade ou fraude. Esse tipo de mensagem normalmente contém um link ou anexo mal-intencionado, mas nem sempre.

**Spoof**: o spoofing é quando os spammers forjam o cabeçalho from para que as mensagens pareçam ter sido originadas de alguém ou de outro lugar que não seja a fonte real. Isso pode ser spam, mas usado com mais frequência para usuários de Phish.

**Representação**: esse tipo de spam também é uma maneira de forjar o endereço do remetente, mas isso é feito modificando parte do nome ou domínio de forma que ele se pareça com a fonte real. Por exemplo, Bi11@micr0s0ft.com, onde "l" no Bill foi realmente o número onze e o "o" no Microsoft foi substituído pelo número zero.

**Em massa**: o email em massa geralmente é solicitado por usuários, embora às vezes as empresas vendem as informações para outras empresas. É comum que os usuários se inscrevam intencionalmente no email em massa (ou seja, newletters), mas se esqueçam mais tarde e pense que é spam. O email em massa se torna spam quando os emails em massa enviam mais do que os níveis de inscrição e de reclamação ficam muito altos.
