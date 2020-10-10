---
title: Executar ações na busca avançada de resultados de consulta na proteção contra ameaças da Microsoft
description: Resolver rapidamente as ameaças e os ativos afetados nos resultados da consulta de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, executar ação
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 3d2df325198c420cb2444a74b6c3507657355012
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412089"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>Executar ações nos resultados da consulta de busca avançada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Você pode facilmente conter ameaças ou lidar com os ativos comprometidos encontrados em [busca avançada](advanced-hunting-overview.md) usando opções de ações poderosas e abrangentes. Com essas opções, você pode:

- Executar várias ações em dispositivos
- Arquivos de quarentena

## <a name="required-permissions"></a>Permissões obrigatórias
Para executar ações por meio de busca avançada, você precisa de uma função no Microsoft defender ATP com [permissões para enviar ações de correção em dispositivos](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options). Se você não puder executar uma ação, entre em contato com um administrador global para obter a seguinte permissão:

*Ações de correção ativas > gerenciamento de vulnerabilidades e ameaças-tratamento de correção*

## <a name="take-various-actions-on-devices"></a>Executar várias ações em dispositivos
Você pode executar as seguintes ações nos dispositivos identificados pela `DeviceId` coluna nos resultados de consulta:

- Isolar dispositivos afetados para que contenham uma infecção ou impedir que ataques sejam movidos de forma mais tarde
- Coletar pacote de investigação para obter informações mais legais
- Execute uma verificação antivírus para encontrar e remover ameaças usando as atualizações de inteligência de segurança mais recentes
- Iniciar uma investigação automatizada para verificar e corrigir ameaças no dispositivo e possivelmente outros dispositivos afetados
- Restringir a execução do aplicativo apenas a arquivos executáveis assinados pela Microsoft, impedindo a atividade de ameaça subsequente por malware ou outros executáveis não confiáveis

Para saber mais sobre como essas ações de resposta são executadas por meio do Microsoft defender ATP, [Leia sobre as ações de resposta nos dispositivos](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).
   
## <a name="quarantine-files"></a>Arquivos de quarentena
Você pode implantar a ação de *quarentena* nos arquivos para que eles sejam automaticamente colocados em quarentena quando encontrados. Ao selecionar essa ação, você pode escolher entre as seguintes colunas para identificar quais arquivos da sua consulta resultam em quarentena:

- `SHA1` — Na maioria das tabelas de caça avançadas, este é o SHA-1 do arquivo que foi afetado pela ação gravada. Por exemplo, se um arquivo foi copiado, esse será o arquivo copiado.
- `InitiatingProcessSHA1` — Na maioria das tabelas de busca avançada, este é o arquivo responsável por iniciar a ação gravada. Por exemplo, se um processo filho foi iniciado, esse seria o processo pai. 
- `SHA256` — Este é o equivalente SHA-256 do arquivo identificado pela `SHA1` coluna.
- `InitiatingProcessSHA256` — Este é o equivalente SHA-256 do arquivo identificado pela `InitiatingProcessSHA1` coluna.

Para saber mais sobre como as ações de quarentena são tomadas e como os arquivos podem ser restaurados, [Leia sobre as ações de resposta nos arquivos](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).

>[!NOTE]
>Para localizar arquivos e Quarantine-los, os resultados da consulta também devem incluir `DeviceId` valores como identificadores de dispositivo.  

## <a name="take-action"></a>Executar ação
Para executar qualquer uma das ações descritas, selecione um ou mais registros nos resultados da consulta e selecione **executar ações**. Um assistente orientará você pelo processo de seleção e envio de suas ações preferidas.

![Imagem do registro selecionado com painel para inspecionar o registro](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a>Revisar ações executadas
Cada ação é registrada individualmente na [central de ações](mtp-action-center.md) , em histórico da **central de ações**  >  **History** ([Security.Microsoft.com/Action-Center/History](https://security.microsoft.com/action-center/history)). Vá para a central de ações para verificar o status de cada ação.
 
## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Trabalhar com os resultados da consulta](advanced-hunting-query-results.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Visão geral da central de ações](mtp-action-center.md)
