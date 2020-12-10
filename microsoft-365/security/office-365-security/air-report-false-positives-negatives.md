---
title: Como relatar falsos positivos ou falsos negativos seguindo a investigação automatizada no Microsoft defender para Office 365
description: Algo estava perdido ou erroneamente detectado pelo ar no Microsoft defender para Office 365? Saiba como enviar falsos positivos ou falsos negativos para a Microsoft para análise.
keywords: automatizado, investigação, alerta, gatilho, ação, correção, falso positivo, falso negativo
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 09/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: conceptual
ms.custom:
- autoir
ms.openlocfilehash: 0fe8891f5ea6af215791c5f4321a93667a9d58f0
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616171"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Como relatar falsos positivos/negativos em recursos de investigação e resposta automatizados

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Aplica-se a:**
- Microsoft defender para Office 365

Os [recursos de investigação e resposta automatizados (Air) do Office 365](automated-investigation-response-office.md) perdem ou detectou erroneamente algo? Há etapas que você pode executar para corrigi-lo. Você pode:

- [Relatar um falso positivo/negativo para a Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [Ajustar seus alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (se necessário); e
- [Desfazer ações de correção que foram tomadas](#undo-a-remediation-action).

Use este artigo como uma guia.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Relatar um falso positivo/negativo para a Microsoft para análise

Se o AIR no Microsoft defender para Office 365 perder uma mensagem de email, um anexo de email, uma URL em uma mensagem de email ou uma URL em um arquivo do Office, você poderá [enviar spam, Phish, URLs e arquivos suspeitos para a Microsoft para a verificação de 365 do Office](admin-submission.md).

Você também pode [enviar um arquivo para a Microsoft para análise de malware](https://www.microsoft.com/wdsi/filesubmission).

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Ajustar um alerta para impedir que falsos positivos sejam recorrentes

Se um alerta for disparado por uso legítimo ou se o alerta for impreciso, você poderá [Gerenciar alertas no portal do Cloud app Security](https://docs.microsoft.com/cloud-app-security/managing-alerts).

Se sua organização estiver usando o [Microsoft defender para ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection) , além do Office 365, e um arquivo, endereço IP, URL ou domínio for tratado como malware em um dispositivo, mesmo que seja seguro, você poderá [criar um indicador personalizado com uma ação "permitir" para o dispositivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).

## <a name="undo-a-remediation-action"></a>Desfazer uma ação de correção

Na maioria dos casos, se uma ação de correção foi realizada em uma mensagem de email, anexo de email ou URL, e o item não é uma ameaça, a equipe de operações de segurança pode desfazer a ação de correção e realizar etapas para evitar o falso positivo de recorrência. Você pode usar o [Gerenciador de ameaças](#undo-an-action-using-threat-explorer) ou a [guia ações para uma investigação](#undo-an-action-using-the-actions-tab-for-an-investigation) para desfazer uma ação.

> [!IMPORTANT]
> Verifique se você tem as permissões necessárias antes de tentar executar as tarefas a seguir.

### <a name="undo-an-action-using-threat-explorer"></a>Desfazer uma ação usando o explorador de ameaças

Com o Gerenciador de ameaças, a equipe de operações de segurança pode encontrar um email afetado por uma ação e possivelmente desfazer a ação.

****

|Cenário|Opções de desfazer|Saiba mais|
|---|---|---|
|Uma mensagem de email foi encaminhada para a pasta lixo eletrônico de um usuário|<ul><li>Mover a mensagem para a pasta itens excluídos do usuário</li><li>Mover a mensagem para a caixa de entrada do usuário</li><li>Excluir a mensagem</li></ul>|[Encontre e investigue emails mal-intencionados que foram entregues no Office 365](investigate-malicious-email-that-was-delivered.md)|
|Uma mensagem de email ou um arquivo foi colocado em quarentena|<ul><li>Liberar o email ou o arquivo</li><li>Excluir o email ou arquivo</li></ul>|[Gerenciar mensagens em quarentena como um administrador](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a>Desfazer uma ação usando a guia ações para uma investigação

Na central de ações, você pode ver ações de correção que foram tomadas e possivelmente desfazer a ação.

1. Acesse <https://protection.office.com> e entre. Isso leva você para o centro de conformidade & segurança.

2. Vá para investigações de **Gerenciamento de ameaças** \> .

3. Na lista de investigações, selecione o ícone **abrir na nova janela** ao lado da ID de um item.

4. Selecione a guia **ações** .

5. Selecione um item com status **concluído** e procure um link, como **aprovado**, na coluna **decisão** . Isso abre um submenu com mais detalhes sobre a ação.

6. Para desfazer a ação, selecione **excluir correção**.

## <a name="related-articles"></a>Artigos relacionados

[Microsoft defender para Office 365](office-365-atp.md)

[AR no Microsoft defender para Office 365](office-365-air.md)
