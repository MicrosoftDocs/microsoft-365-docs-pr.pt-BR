---
title: Como relatar falsos positivos ou falsos negativos após investigação automatizada no Microsoft Defender para Office 365
description: Algo foi perdido ou detectado incorretamente pelo AIR no Microsoft Defender para Office 365? Saiba como enviar falsos positivos ou falsos negativos à Microsoft para análise.
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
ms.date: 01/29/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 4ccc023a72ca450b1f0a433410206ccce59cb5f1
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142969"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Como relatar falsos positivos/negativos em recursos automatizados de investigação e resposta

**Aplica-se a:**
- Microsoft Defender para Office 365

Se os recursos de investigação e resposta [automatizadas (AIR) no Office 365](automated-investigation-response-office.md) perderam ou detectaram incorretamente algo, há etapas que sua equipe de operações de segurança pode seguir para corrigi-lo. Essas ações incluem:

- [Relatar um falso positivo/negativo para a Microsoft;](#report-a-false-positivenegative-to-microsoft-for-analysis)
- [Ajustando alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (se necessário); e
- [Desfazer ações de correção que foram tomadas.](#undo-a-remediation-action)

Use este artigo como guia.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Relatar um falso positivo/negativo à Microsoft para análise

Se o AIR no Microsoft Defender para Office 365 perdeu uma mensagem de email, um anexo de email, uma URL em uma mensagem de email ou uma URL em um arquivo do Office, você pode enviar [spam, phishing, URLs](admin-submission.md)e arquivos suspeitos para a verificação do Microsoft para Office 365.

Você também pode [enviar um arquivo à Microsoft para análise de malware.](https://www.microsoft.com/wdsi/filesubmission)

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Ajustar um alerta para evitar que falsos positivos se repitam

Se um alerta for disparado por uso legítimo ou se o alerta for impreciso, você poderá gerenciar alertas no portal do [Cloud App Security.](https://docs.microsoft.com/cloud-app-security/managing-alerts)

Se sua organização estiver usando o [Microsoft Defender para](https://docs.microsoft.com/windows/security/threat-protection) Ponto de Extremidade, além do Office 365, e um arquivo, endereço IP, URL ou domínio for tratado como malware em um dispositivo, mesmo que seja seguro, você pode criar um indicador personalizado com uma ação ["Permitir"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)para seu dispositivo.

## <a name="undo-a-remediation-action"></a>Desfazer uma ação de correção

Na maioria dos casos, se uma ação de correção tiver sido realizada em uma mensagem de email, um anexo de email ou uma URL, e o item não for realmente uma ameaça, sua equipe de operações de segurança poderá desfazer a ação de correção e tomar medidas para evitar que o falso positivo se repita. Você pode usar o [Explorador de Ameaças](#undo-an-action-using-threat-explorer) ou a guia Ações para uma investigação [desfazer](#undo-an-action-in-the-action-center) uma ação.

> [!IMPORTANT]
> Certifique-se de que você tenha as permissões necessárias antes de tentar executar as tarefas a seguir.

### <a name="undo-an-action-using-threat-explorer"></a>Desfazer uma ação usando o Explorador de Ameaças

Com o Explorador de Ameaças, sua equipe de operações de segurança pode encontrar um email afetado por uma ação e potencialmente desfazer a ação.

|Cenário|Opções de desfazer|Saiba mais|
|---|---|---|
|Uma mensagem de email foi roteada para a pasta Lixo Eletrônico de um usuário|- Mover a mensagem para a pasta Itens Excluídos do usuário<br/>- Mover a mensagem para a Caixa de Entrada do usuário<br/>- Excluir a mensagem|[Encontrar e investigar emails mal-intencionados que foram entregues no Office 365](investigate-malicious-email-that-was-delivered.md)|
|Uma mensagem de email ou um arquivo foi colocado em quarentena|- Liberar o email ou arquivo<br/>- Excluir o email ou arquivo|[Gerenciar mensagens em quarentena como administrador](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a>Desfazer uma ação na Central de ações

Na Central de ações, você pode ver as ações de correção que foram tomadas e potencialmente desfazer a ação.

1. Vá para a central de segurança do Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ).
2. No painel de navegação, selecione Central **de ações.** 
3. Selecione a **guia Histórico** para exibir a lista de ações concluídas.
4. Selecione um item. Seu painel de sobrevoo é aberto. 
5. No painel do flyout, selecione **Desfazer**. (Somente ações que podem ser desfeitas terão um **botão Desfazer.)**

## <a name="see-also"></a>Confira também

- [Microsoft Defender para Office 365](office-365-atp.md)
- [Investigações automatizadas no Microsoft Defender para Office 365](office-365-air.md)
