---
title: Controles de acesso corporativo do Microsoft 365 Yammer
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Este artigo contém um breve resumo sobre os controles de acesso corporativo do Yammer no ambiente de produção.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8bdf357ddd7f5c0b549d291fd4732924608085b9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695399"
---
# <a name="yammer-enterprise-access-controls"></a>Controles de acesso corporativo do Yammer 

O acesso físico e lógico ao ambiente de produção do Yammer é restrito a um pequeno conjunto de pessoas (infraestrutura e operações). Como em outros engenheiros da Microsoft 365, os engenheiros do Yammer têm zero acesso à dados dos clientes. O acesso deve ser solicitado usando um sistema de controle de acesso just-in-time baseado em aprovação semelhante ao Lockbox com um número limitado de aprovadores. Os aprovadores verificam a solicitação (por exemplo, eles verificam se a solicitação é legítima com base em necessidade, caso de negócios, hora etc.) e, em seguida, aprovar ou negar a solicitação. Se a solicitação for aprovada, o acesso JIT será concedido para um tempo definido e limitado. Após o tempo de acesso ser excedido, o acesso expira automaticamente.

Como em outros serviços do Microsoft 365, todo o acesso ao ambiente de produção do Yammer usa a autenticação multifator. Todos os acessos e o histórico de comandos são atribuídos a um usuário e registrados e revisados regularmente pela equipe de segurança do Yammer.

Para obter mais informações sobre administração e gerenciamento do Yammer, consulte [ajuda do administrador do Yammer](https://docs.microsoft.com/yammer/yammer-landing-page).