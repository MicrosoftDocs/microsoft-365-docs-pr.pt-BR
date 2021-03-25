---
title: APIs de resposta avançada contra ameaças do Microsoft Defender com suporte
description: Saiba mais sobre as chamadas específicas da API de Proteção Avançada contra Ameaças do Microsoft Defender.
keywords: apis de resposta, api gráfica, apis com suporte, ator, alertas, dispositivo, usuário, domínio, ip, arquivo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: a290c431f6d81b23896ddf77e7c7a47de378de22
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185546"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a>APIs de consulta com suporte do Microsoft Defender para Ponto de Extremidade 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!TIP]
> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-supported-response-apis-abovefoldlink) 

Saiba mais sobre as chamadas de API relacionadas à resposta com suporte que você pode executar e detalhes como os headers de solicitação necessários e a resposta esperada das chamadas.

## <a name="in-this-section"></a>Nesta seção
Tópico | Descrição
:---|:---
Coletar pacote de investigação | Execute essa API para coletar um pacote de investigação de um dispositivo.
Isolar dispositivo | Execute essa API para isolar um dispositivo da rede.
Dispositivo unisolado | Remova um dispositivo do isolamento. 
Restringir a execução de código | Execute essa API para conter um ataque interrompendo processos mal-intencionados. Você também pode bloquear um dispositivo e impedir a execução de tentativas subsequentes de programas potencialmente mal-intencionados.
Execução de código desconsumentado | Execute isso para reverter a restrição da política de aplicativos depois de verificar se o dispositivo comprometido foi remediado.
Executar verificação antivírus | Inicie remotamente uma verificação antivírus para ajudar a identificar e correção de malware que pode estar presente em um dispositivo comprometido.
Arquivo stop and quarantine |  Execute essa chamada para interromper a execução de processos, arquivos de quarentena e excluir a persistência, como chaves do Registro.
Exemplo de solicitação | Execute essa chamada para solicitar um exemplo de um arquivo de um dispositivo específico. O arquivo será coletado do dispositivo e carregado em um armazenamento seguro.
Bloquear arquivo | Execute essa API para evitar a propagação de um ataque em sua organização, proibindo arquivos potencialmente mal-intencionados ou suspeitas de malware. 
Desbloquear arquivo | Permitir que um arquivo seja executado na organização usando o Microsoft Defender Antivírus.
Obter URI do SAS do pacote | Execute essa API para obter um URI que permita baixar um pacote de investigação.
Obter objeto MachineAction | Execute essa API para obter o objeto MachineAction.
Obter coleção MachineActions | Execute isso para obter a coleção MachineAction.
Obter coleção FileActions | Execute essa API para obter a coleção FileActions.
Obter objeto FileMachineAction | Execute essa API para obter o objeto FileMachineAction.
Obter coleção FileMachineActions | Execute essa API para obter a coleção FileMachineAction.
