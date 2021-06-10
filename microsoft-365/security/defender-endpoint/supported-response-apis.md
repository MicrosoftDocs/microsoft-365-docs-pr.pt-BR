---
title: APIs de resposta do Microsoft Defender para Ponto de Extremidade com suporte
description: Saiba mais sobre as chamadas de API específicas relacionadas à resposta do Microsoft Defender para Endpoint.
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
ms.openlocfilehash: 36ed1f624fda7ae413ffbbf807925cf00e0a23ca
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933764"
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
Executar verificação de antivírus | Inicie remotamente uma verificação antivírus para ajudar a identificar e correção de malware que pode estar presente em um dispositivo comprometido.
Interromper e colocar o arquivo em quarentena |  Execute essa chamada para interromper a execução de processos, arquivos de quarentena e excluir a persistência, como chaves do Registro.
Exemplo de solicitação | Execute essa chamada para solicitar um exemplo de um arquivo de um dispositivo específico. O arquivo será coletado do dispositivo e carregado em um armazenamento seguro.
Bloquear arquivo | Execute essa API para evitar a propagação de um ataque em sua organização, proibindo arquivos potencialmente mal-intencionados ou suspeitas de malware. 
Desbloquear arquivo | Permitir que um arquivo seja executado na organização usando Microsoft Defender Antivírus.
Obter URI do SAS do pacote | Execute essa API para obter um URI que permita baixar um pacote de investigação.
Obter objeto MachineAction | Execute essa API para obter o objeto MachineAction.
Obter coleção MachineActions | Execute isso para obter a coleção MachineAction.
Obter coleção FileActions | Execute essa API para obter a coleção FileActions.
Obter objeto FileMachineAction | Execute essa API para obter o objeto FileMachineAction.
Obter coleção FileMachineActions | Execute essa API para obter a coleção FileMachineAction.
