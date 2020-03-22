---
title: Qual é a diferença entre lixo eletrônico e email em massa?
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/7/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
description: Os clientes às vezes askwhat a diferença entre lixo eletrônico e mensagens de email em massa? O objetivo deste tópico é explicar a diferença e fornecer informações sobre as diferentes opções disponíveis para o Exchange Online e o Exchange Online Protection (EOP).
ms.openlocfilehash: 55924ac5e83ca109fd66d1723cdb7c5f43f20df6
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895030"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a>Qual é a diferença entre lixo eletrônico e email em massa?

Às vezes, os clientes perguntam "qual é a diferença entre lixo eletrônico e mensagens de email em massa?" O objetivo deste tópico é explicar a diferença e fornecer informações sobre as várias opções disponíveis no Exchange Online e no Proteção do Exchange Online (EOP).
  
 **O que é lixo eletrônico?**
  
As mensagens de lixo eletrônico são mensagens de "spam", significando emails não solicitados (e geralmente indesejados) que são filtrados pelo serviço. Por padrão, o serviço rejeita a mensagem de spam com base na reputação do endereço IP de envio. Entretanto, se ele passa pela inspeção de IP, mas é classificado como spam pelos filtros de conteúdo, a mensagem é enviada para a pasta Lixo Eletrônico dos destinatários pretendidos. 
  
> [!NOTE]
> A ação executada em mensagens filtradas por conteúdo é configurável por meio de políticas de filtro de conteúdo no centro de administração do Exchange (Eat), conforme descrito em [Configure anti-spam Policies in Office 365](configure-your-spam-filter-policies.md). Além disso, se você discordar da classificação de spam, poderá relatar mensagens que você considerar como spam ou não spam para a Microsoft de várias maneiras, conforme descrito em [enviar mensagens de spam, não spam e golpes de phishing para a Microsoft para análise](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). 
  
 **O que é email em massa?**
  
Email em massa é um tipo de mensagem de email mais difícil de classificar. Embora o lixo eletrônico seja uma ameaça constante, o email em massa geralmente é composto por uma mensagem publicitária ou de marketing que, muito provavelmente, não será enviada repetidas vezes. O email em massa é de interesse de alguns usuários e, de fato, eles podem ter deliberadamente concordado em receber essas mensagens, embora outros usuários talvez considerem esse tipo de mensagem como spam. Por exemplo, alguns usuários querem receber emails publicitários da Contoso Corporation ou convites para uma conferência futura sobre segurança cibernética; já outros usuários consideram tais emails como spam.
  
## <a name="how-to-manage-bulk-email"></a>Como gerenciar o email em massa

A maneira de gerenciar o email em massa não é uma decisão clara - afinal, se todos os emails em massa forem classificados como spam, os usuários interessados poderão reclamar e enviá-los como um falso positivo (mensagem de não spam e que foi incorretamente marcada como spam). Por outro lado, se todos os emails em massa forem liberados, os usuários não interessados poderão reclamar e enviá-los como uma mensagem de spam que escapou à inspeção (falso negativo) e chegou inadvertidamente à caixa de entrada deles.
  
### <a name="enable-bulk-mail-sensitivity-control-in-the-content-filter-policy"></a>Habilitar o controle de sensibilidade de email em massa na política de filtro de conteúdo

Dependendo da política de sua empresa em relação a mensagens de email em massa, os administradores podem selecionar um limite para atribuir ao email em massa. A configuração é configurável por meio de políticas de filtro de conteúdo no Eat. Confira [Configurar políticas antispam no Office 365](configure-your-spam-filter-policies.md) para obter as etapas. Você pode escolher uma configuração de limite de 1-9, onde 1 marca a maior parte dos emails em massa como spam, e 9 permite que a maior parte dos emails em massa seja entregue. O serviço então executa a ação configurada; por exemplo, enviar a mensagem para a pasta Lixo Eletrônico do destinatário. 
  

