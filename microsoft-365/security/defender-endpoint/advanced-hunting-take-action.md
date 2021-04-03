---
title: Tomar medidas em resultados avançados de consulta de busca na Proteção contra Ameaças da Microsoft
description: Resolver rapidamente ameaças e ativos afetados em seus resultados de consulta de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, mdatp, microsoft defender atp, pesquisa wdatp, consulta, telemetria, detecções personalizadas, esquema, kusto, evitar tempo de espera, linhas de comando, id de processo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: d1dbe226cef5e94b36fcd6c35b839118b200f85e
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500529"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>Tomar medidas nos resultados avançados da consulta de busca

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Você pode conter rapidamente ameaças ou resolver ativos comprometidos que você encontra na busca [avançada](advanced-hunting-overview.md) usando opções de ação avançadas e abrangentes. Com essas opções, você pode:

- Tomar várias ações em dispositivos
- Arquivos de quarentena

## <a name="required-permissions"></a>Permissões obrigatórias

Para poder realizar ações por meio da busca avançada, você precisa de uma função no Defender para Ponto de Extremidade com permissões para enviar ações de [correção em dispositivos](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options). Se você não puder tomar uma ação, contate um administrador global sobre como obter a seguinte permissão:

*Ações de correção ativas > gerenciamento de ameaças e vulnerabilidades - Tratamento de correção*

## <a name="take-various-actions-on-devices"></a>Tomar várias ações em dispositivos

Você pode tomar as seguintes ações em dispositivos identificados pela `DeviceId` coluna nos resultados da consulta:

- Isolar dispositivos afetados para conter uma infecção ou impedir que os ataques se movem lateralmente
- Coletar pacote de investigação para obter mais informações forenses
- Executar uma verificação antivírus para encontrar e remover ameaças usando as atualizações mais recentes de inteligência de segurança
- Inicie uma investigação automatizada para verificar e remediar ameaças no dispositivo e, possivelmente, em outros dispositivos afetados
- Restringir a execução de aplicativos somente a arquivos executáveis assinados pela Microsoft, impedindo atividades de ameaças subsequentes por meio de malware ou outros executáveis não-confiança

Para saber mais sobre como essas ações de resposta são executadas por meio do Defender for Endpoint, [leia sobre ações de resposta em dispositivos](respond-machine-alerts.md).

## <a name="quarantine-files"></a>Arquivos de quarentena

Você pode implantar a *ação de* quarentena em arquivos para que eles sejam automaticamente colocados em quarentena quando encontrados. Ao selecionar essa ação, você pode escolher entre as seguintes colunas para identificar quais arquivos em sua consulta resulta em quarentena:

- `SHA1` — Nas tabelas de busca mais avançadas, este é o SHA-1 do arquivo que foi afetado pela ação gravada. Por exemplo, se um arquivo foi copiado, esse seria o arquivo copiado.
- `InitiatingProcessSHA1` — Nas tabelas de busca mais avançadas, esse é o arquivo responsável por iniciar a ação gravada. Por exemplo, se um processo filho foi lançado, esse seria o processo pai. 
- `SHA256` — Esse é o equivalente sha-256 do arquivo identificado pela `SHA1` coluna.
- `InitiatingProcessSHA256` — Esse é o equivalente sha-256 do arquivo identificado pela `InitiatingProcessSHA1` coluna.

Para saber mais sobre como as ações de quarentena são tomadas e como os arquivos podem ser restaurados, [leia sobre ações de resposta em arquivos](respond-file-alerts.md).

>[!NOTE]
>Para localizar arquivos e colocar em quarentena, os resultados da consulta também devem incluir `DeviceId` valores como identificadores de dispositivo.  

## <a name="take-action"></a>Tomar uma ação

Para tomar qualquer uma das ações descritas, selecione um ou mais registros nos resultados da consulta e selecione **Tomar ações**. Um assistente o guiará pelo processo de seleção e, em seguida, enviará suas ações preferenciais.

![Imagem do registro selecionado com painel para inspecionar o registro](images/ah-take-actions.png)

## <a name="review-actions-taken"></a>Revisar ações realizadas

Cada ação é registrada individualmente no centro de ações, em **Histórico do Centro de** Ações (  >   [security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)). Vá para o centro de ações para verificar o status de cada ação.
 
## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Compreender o esquema](advanced-hunting-schema-reference.md)
- [Trabalhar com os resultados da consulta](advanced-hunting-query-results.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
- [Visão geral de detecções personalizadas](overview-custom-detections.md)
