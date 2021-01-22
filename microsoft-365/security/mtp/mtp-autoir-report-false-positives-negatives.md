---
title: Tratar falsos positivos ou falsos negativos no AIR no Microsoft 365 Defender
description: Algo foi perdido ou detectado incorretamente pelo AIR no Microsoft 365 Defender? Saiba como enviar falsos positivos ou falsos negativos à Microsoft para análise.
keywords: automatizado, investigação, alerta, gatilho, ação, correção, falso positivo, falso negativo
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 09/16/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: dbef240e28258d1ac4000c05538d0ce073a9d910
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930349"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Lidar com falsos positivos/negativos em recursos automatizados de investigação e resposta

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Os [recursos automatizados de investigação e resposta](mtp-autoir.md) no Microsoft 365 Defender falharam ou detectaram algo incorretamente? Há etapas que você pode seguir para corrigi-lo. Você pode:

- [Relatar um falso positivo/negativo para a Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);

- [Ajuste seus alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (se necessário); e 

- [Desfazer ações de correção que foram realizadas em dispositivos.](#undo-a-remediation-action-that-was-taken-on-a-device) 

Use este artigo como guia. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Relatar um falso positivo/negativo à Microsoft para análise

|Item perdido ou detectado incorretamente |Serviço  |O que fazer  |
|---------|---------|---------|
|- Mensagem de email <br/>- Anexo de email <br/>- URL em uma mensagem de email<br/>- URL em um arquivo do Office      |[Obter o Microsoft Defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[Enviar spam, phishing, URLs e arquivos suspeitos à Microsoft para verificação](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|Arquivo ou aplicativo em um dispositivo    |[Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection)         |[Enviar um arquivo à Microsoft para análise de malware](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Ajustar um alerta para evitar que falsos positivos se repitam

|Cenário |Serviço |O que fazer |
|--------|--------|--------|
|- Um alerta é acionado por uso legítimo <br/>- Um alerta é impreciso    |[Segurança no Aplicativo da Nuvem da Microsoft](https://docs.microsoft.com/cloud-app-security)<br/> ou <br/>[Detecção avançada de ameaças do Azure](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Gerenciar alertas no portal do Cloud App Security](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|Um arquivo, endereço IP, URL ou domínio é tratado como malware em um dispositivo, mesmo que seja seguro|[Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection) |[Criar um indicador personalizado com uma ação "Permitir"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Desfazer uma ação de correção que foi realizada em um dispositivo

Se uma ação de correção tiver sido tomada em um dispositivo (como um dispositivo Windows 10) e o item não for realmente uma ameaça, sua equipe de operações de segurança poderá desfazer a ação de correção na Central de [ações.](mtp-action-center.md)

> [!IMPORTANT]
> Certifique-se de que você [tenha as permissões necessárias](mtp-action-center.md#required-permissions-for-action-center-tasks) antes de tentar executar a tarefa a seguir.

1. Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre. 

2. No painel de navegação, escolha **Central de ações**. 

3. Na guia **Histórico,** selecione uma ação que você deseja desfazer. Isso abre um flyout.<br/>
    > [!TIP]
    > Use filtros para restringir a lista de resultados. 

4. No flyout do item selecionado, selecione **a página Abrir investigação.**

5. Na exibição de detalhes da investigação, selecione a **guia** Ações.

6. Selecione um item que tenha o status **concluído** e procure um link, como **Aprovado,** na coluna **Decisões.** Isso abre um flyout com mais detalhes sobre a ação.

7. Para desfazer a ação, selecione **Excluir correção.**

## <a name="see-also"></a>Confira também

- [Exibir os detalhes e resultados de uma investigação automatizada](mtp-autoir-results.md)
- [Busca proativa por ameaças com busca avançada no Microsoft 365 Defender](advanced-hunting-overview.md)
