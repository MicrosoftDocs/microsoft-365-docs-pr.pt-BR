---
title: Lidar com falsos positivos ou falsos negativos no ar no Microsoft Threat Protection
description: Algo estava perdido ou foi detectado incorretamente pelo ar na proteção contra ameaças da Microsoft? Saiba como enviar falsos positivos ou falsos negativos para a Microsoft para análise.
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
ms.date: 01/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 90651aa258adb9f7fe46f99bcadf1d4d552a5b76
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955656"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Lidar com falsos positivos/negativos em recursos de investigação e resposta automatizados

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

Os [recursos de investigação e resposta automatizados](mtp-autoir.md) na proteção contra ameaças da Microsoft perdem ou detectam incorretamente algo? Há etapas que você pode executar para corrigi-lo. Você pode:

- [Relatar um falso positivo/negativo para a Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);

- [Ajustar seus alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (se necessário); e 

- [Desfazer ações de correção que foram tomadas nos dispositivos](#undo-a-remediation-action-that-was-taken-on-a-device). 

Use este artigo como uma guia. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Relatar um falso positivo/negativo para a Microsoft para análise

|Item perdido ou detectado incorretamente |Serviço  |O que fazer  |
|---------|---------|---------|
|-Mensagem de email <br/>-Anexo de email <br/>-URL em uma mensagem de email<br/>-URL em um arquivo do Office      |[Proteção Avançada contra Ameaças do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[Enviar spam, phishing, URLs e arquivos suspeitos à Microsoft para a verificação do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|Arquivo ou aplicativo em um dispositivo    |[Proteção Avançada contra Ameaças do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection)         |[Enviar um arquivo para a Microsoft para análise de malware](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Ajustar um alerta para impedir que falsos positivos sejam recorrentes

|Cenário |Serviço |O que fazer |
|--------|--------|--------|
|-Um alerta é disparado por uso legítimo <br/>-Um alerta é impreciso    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> ou <br/>[Detecção avançada de ameaças do Azure](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Gerenciar alertas no portal do Cloud app Security](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|Um arquivo, um endereço IP, uma URL ou um domínio é tratado como um malware em um dispositivo, mesmo que seja seguro|[Proteção Avançada contra Ameaças do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) |[Criar um indicador personalizado com uma ação "permitir"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Desfazer uma ação de correção executada em um dispositivo

Se uma ação de correção foi realizada em um dispositivo (como um dispositivo Windows 10) e o item não for uma ameaça, a equipe de operações de segurança poderá desfazer a ação de correção na [central de ações](mtp-action-center.md).

> [!IMPORTANT]
> Verifique se você tem as [permissões necessárias](mtp-action-center.md#required-permissions-for-action-center-tasks) antes de tentar executar a tarefa a seguir.

1. Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre. 

2. No painel de navegação, escolha **Central de ações**. 

3. Na guia **histórico** , selecione uma ação que você deseja desfazer. Isso abre um submenu.<br/>
    > [!TIP]
    > Use filtros para restringir a lista de resultados. 

4. No submenu do item selecionado, selecione **página de investigação aberta**.

5. No modo de exibição detalhes da investigação, selecione a guia **ações** .

6. Selecione um item com status **concluído**e procure um link, como **aprovado**, na coluna **decisões** . Isso abre um submenu com mais detalhes sobre a ação.

7. Para desfazer a ação, selecione **excluir correção**.

## <a name="related-articles"></a>Artigos relacionados

- [Aprovar ou rejeitar ações relacionadas a investigações e respostas automatizadas](mtp-autoir-actions.md)

- [Saiba mais sobre a Central de Ações](mtp-action-center.md)

- [Faça buscas proativas por ameaças com a busca avançada da Proteção contra Ameaças da Microsoft](advanced-hunting-overview.md)
