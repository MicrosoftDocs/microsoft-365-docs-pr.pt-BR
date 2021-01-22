---
title: Alterações de nomeação no esquema de busca avançada do Microsoft 365 Defender
description: Acompanhar e revisar as tabelas e colunas de alterações de nomeação no esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, dados, alterações de nomeação, renomear, Proteção contra Ameaças da Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 483fedd1fb152e3df5311c981b305e621ec2aec3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932197"
---
# <a name="advanced-hunting-schema---naming-changes"></a>Esquema de busca avançada - Alterações de nomeação

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

O [esquema de busca avançada é](advanced-hunting-schema-tables.md) atualizado regularmente para adicionar novas tabelas e colunas. Em alguns casos, os nomes de colunas existentes são renomeados ou substituídos para melhorar a experiência do usuário. Consulte este artigo para revisar as alterações de nomeação que podem afetar suas consultas.

As alterações de nomeação são aplicadas automaticamente às consultas salvas no centro de segurança, incluindo consultas usadas por regras de detecção personalizadas. Você não precisa atualizar essas consultas manualmente. No entanto, você precisará atualizar as seguintes consultas:
- Consultas que são executados usando a API
- Consultas salvas em outro lugar fora da central de segurança

## <a name="december-2020"></a>Dezembro de 2020

| Nome da tabela | Nome da coluna original | Novo nome de coluna | Motivo da alteração
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailAction | EmailAction | Comentários dos clientes |
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailActionPolicy | EmailActionPolicy | Comentários dos clientes |
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailActionPolicyGuid | EmailActionPolicyGuid | Comentários dos clientes |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)