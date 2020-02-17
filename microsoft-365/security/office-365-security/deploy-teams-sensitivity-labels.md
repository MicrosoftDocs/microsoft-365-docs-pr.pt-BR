---
title: Proteger arquivos em equipes com rótulos de confidencialidade
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 'Resumo: aplique rótulos confidenciais para proteger arquivos em uma equipe altamente confidencial.'
ms.openlocfilehash: b263aeae335b83cadb45b16d70a2a45d56f1cbd3
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083360"
---
# <a name="protect-files-in-teams-with-sensitivity-labels"></a>Proteger arquivos em equipes com rótulos de confidencialidade


Ao contrário de um rótulo de confidencialidade para dados altamente regulamentados que qualquer pessoa pode aplicar a qualquer arquivo, uma equipe altamente segura precisa de seu próprio rótulo ou sub-rótulo para que os arquivos atribuídos:

- Sejam individualmente criptografados.
- Contenham permissões personalizadas para que somente membros da equipe possam abri-lo.

Para obter esse nível de segurança adicional para arquivos armazenados no site subjacente do SharePoint de uma equipe, configure um rótulo de confidencialidade personalizado que seja seu próprio rótulo ou um sub-rótulo do rótulo geral para dados altamente regulamentados. Somente os membros da equipe verão o rótulo ou o sub-rótulo personalizado na lista de rótulos.

Use um rótulo de confidencialidade quando precisar de um pequeno número de rótulos para uso global e equipes privadas individuais. 

Use um sub-rótulo de confidencialidade quando houver um grande número de rótulos ou quiser organizar rótulos paras equipes altamente confidenciais sob o rótulo altamente regulamentado.

Use [estas instruções](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) para configurar um rótulo separado ou um sub-rótulo com as seguintes configurações:

- O nome do rótulo ou do sub-rótulo contém o nome da equipe
- A criptografia está ativada
- O grupo do Office 365 para a equipe tem permissões de coautoria

Depois de criar, publique o novo rótulo ou sub-rótulo para seus usuários, que poderão, aplicá-los a arquivos localmente antes de carregá-los para a equipe ou, posteriormente, quando o arquivo estiver armazenado na equipe.

Esta é a configuração da equipe altamente confidencial que usa rótulos de confidencialidade para criptografia e permissões de arquivos.

![Proteção de nível de linha de base para uma equipe pública.](../../media/highly-confidential-team-dlp-sensitivity-labels.png)


## <a name="see-also"></a>Confira também

[Proteger arquivos no Microsoft Teams](secure-files-in-teams.md)
  
[Adoção da nuvem e de soluções híbridas](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
