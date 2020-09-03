---
title: Controles de acesso corporativo do Microsoft 365 Yammer
ms.author: robmazz
author: robmazz
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
ms.openlocfilehash: b7e1ceae1b7ddda4c2eac96cd581a612768f1461
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332659"
---
# <a name="yammer-enterprise-access-controls"></a>Controles de acesso corporativo do Yammer 

O acesso físico e lógico ao ambiente de produção do Yammer é restrito a um pequeno conjunto de pessoas (infraestrutura e operações). Como em outros engenheiros da Microsoft 365, os engenheiros do Yammer têm zero acesso à dados dos clientes. O acesso deve ser solicitado usando um sistema de controle de acesso just-in-time baseado em aprovação semelhante ao Lockbox com um número limitado de aprovadores. Os aprovadores verificam a solicitação (por exemplo, eles verificam se a solicitação é legítima com base em necessidade, caso de negócios, hora etc.) e, em seguida, aprovar ou negar a solicitação. Se a solicitação for aprovada, o acesso JIT será concedido para um tempo definido e limitado. Após o tempo de acesso ser excedido, o acesso expira automaticamente.

Como em outros serviços do Microsoft 365, todo o acesso ao ambiente de produção do Yammer usa a autenticação multifator. Todos os acessos e o histórico de comandos são atribuídos a um usuário e registrados e revisados regularmente pela equipe de segurança do Yammer.

Para obter mais informações sobre administração e gerenciamento do Yammer, consulte [ajuda do administrador do Yammer](https://docs.microsoft.com/yammer/yammer-landing-page).