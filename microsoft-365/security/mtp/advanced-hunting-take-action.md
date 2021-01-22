---
title: Tomar medidas em busca avançada de resultados de consulta no Microsoft 365 Defender
description: Resolver rapidamente ameaças e ativos afetados em seus resultados de consulta de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, tomar medidas
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
ms.openlocfilehash: 9e8ad544cfe17d0d8e5c895e208b42ec56555565
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932173"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>Tomar medidas em resultados de consulta de busca avançada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Você pode rapidamente conter ameaças ou resolver ativos comprometidos que encontra na busca avançada [usando](advanced-hunting-overview.md) opções de ação avançadas e abrangentes. Com essas opções, você pode:

- Tomar várias ações em dispositivos
- Arquivos de quarentena

## <a name="required-permissions"></a>Permissões obrigatórias
Para poder realizar ações por meio da busca avançada, você precisa de uma função no Microsoft Defender for Endpoint com permissões para enviar ações de correção [em dispositivos.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options) Se não for possível tomar medidas, entre em contato com um administrador global para obter a seguinte permissão:

*Ações de correção ativas > gerenciamento de ameaças e vulnerabilidades - Tratamento de correção*

## <a name="take-various-actions-on-devices"></a>Tomar várias ações em dispositivos
Você pode tomar as seguintes ações em dispositivos identificados pela `DeviceId` coluna nos resultados da consulta:

- Isolar dispositivos afetados para conter uma infecção ou impedir que ataques se movem lateralmente
- Coletar pacote de investigação para obter mais informações forenses
- Executar uma verificação antivírus para encontrar e remover ameaças usando as atualizações mais recentes de inteligência de segurança
- Iniciar uma investigação automatizada para verificar e remediar ameaças no dispositivo e possivelmente outros dispositivos afetados
- Restringir a execução do aplicativo somente a arquivos executáveis assinados pela Microsoft, impedindo a atividade subsequente de ameaças por meio de malware ou outros executáveis não-confianças

Para saber mais sobre como essas ações de resposta são executadas por meio do Microsoft Defender para Ponto de Extremidade, [leia sobre ações de resposta em dispositivos.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
   
## <a name="quarantine-files"></a>Arquivos de quarentena
Você pode implantar a *ação de* quarentena em arquivos para que eles sejam automaticamente colocados em quarentena quando encontrados. Ao selecionar essa ação, você pode escolher entre as seguintes colunas para identificar quais arquivos em sua consulta serão colocados em quarentena:

- `SHA1` — Nas tabelas de busca mais avançadas, este é o SHA-1 do arquivo que foi afetado pela ação gravada. Por exemplo, se um arquivo foi copiado, esse seria o arquivo copiado.
- `InitiatingProcessSHA1` — Nas tabelas de busca mais avançadas, esse é o arquivo responsável por iniciar a ação gravada. Por exemplo, se um processo filho foi lançado, esse seria o processo pai. 
- `SHA256` — Este é o equivalente SHA-256 do arquivo identificado pela `SHA1` coluna.
- `InitiatingProcessSHA256` — Este é o equivalente SHA-256 do arquivo identificado pela `InitiatingProcessSHA1` coluna.

Para saber mais sobre como as ações de quarentena são tomadas e como os arquivos podem ser restaurados, [leia sobre ações de resposta em arquivos.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)

>[!NOTE]
>Para localizar arquivos e coloca-los em quarentena, os resultados da consulta também devem incluir `DeviceId` valores como identificadores de dispositivo.  

## <a name="take-action"></a>Tomar medidas
To take any of the described actions, select one or more records in your query results and then select **Take actions**. Um assistente o orientará durante o processo de seleção e envio de suas ações preferidas.

![Imagem do registro selecionado com painel para inspecionar o registro](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a>Revisar as ações tomadas
Cada ação é registrada individualmente na central de ações [em](mtp-action-center.md) **Histórico da Central** de Ações (  >   [security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)). Vá para a central de ações para verificar o status de cada ação.
 
## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Trabalhar com os resultados da consulta](advanced-hunting-query-results.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Visão geral da Central de Ações](mtp-action-center.md)
