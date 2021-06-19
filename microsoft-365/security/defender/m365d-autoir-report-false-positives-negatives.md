---
title: Resolver falsos positivos ou falsos negativos em Microsoft 365 Defender
description: Algo falhou ou errou ao ser detectado pelo AIR Microsoft 365 Defender? Saiba como enviar falsos positivos ou falsos negativos à Microsoft para análise.
keywords: automatizado, investigação, alerta, correção, falso positivo, falso negativo
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: f60208b06e66c1e9803e05ee1fc41376824e9b56
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022529"
---
# <a name="address-false-positives-or-false-negatives-in-microsoft-365-defender"></a>Resolver falsos positivos ou falsos negativos em Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**
- Microsoft 365 Defender

Falsos positivos ou negativos podem ocorrer ocasionalmente com qualquer solução de proteção contra ameaças. Se [os recursos automatizados de investigação](m365d-autoir.md) e resposta Microsoft 365 Defender algo perdido ou detectado incorretamente, há etapas que sua equipe de operações de segurança pode seguir:

- [Relatar um falso positivo/negativo para a Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis)
- [Ajustar seus alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (se necessário)
- [Desfazer ações de correção que foram tomadas em dispositivos](#undo-a-remediation-action-that-was-taken-on-a-device)

As seções a seguir descrevem como executar essas tarefas.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Relatar um falso positivo/negativo à Microsoft para análise

|Item perdido ou detectado incorretamente |Serviço  |O que fazer  |
|---------|---------|---------|
|- Mensagem de email <br/>- Anexo de email <br/>- URL em uma mensagem de email<br/>- URL em um arquivo Office de dados      |[Obter o Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)        |[Enviar spam, phishing, URLs e arquivos suspeitos à Microsoft para verificação](../office-365-security/admin-submission.md)         |
|Arquivo ou aplicativo em um dispositivo    |[Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection)         |[Enviar um arquivo à Microsoft para análise de malware](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Ajustar um alerta para evitar que falsos positivos se repitam

|Cenário |Serviço |O que fazer |
|--------|--------|--------|
|- Um alerta é disparado por uso legítimo <br/>- Um alerta é impreciso    |[Microsoft Cloud App Security](/cloud-app-security)<br/> ou <br/>[Proteção contra ameaças do Azure](/azure/security/fundamentals/threat-detection)         |[Gerenciar alertas no Cloud App Security portal](/cloud-app-security/managing-alerts)         |
|Um arquivo, endereço IP, URL ou domínio é tratado como malware em um dispositivo, mesmo que seja seguro|[Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection) |[Criar um indicador personalizado com uma ação "Permitir"](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Desfazer uma ação de correção que foi tomada em um dispositivo

Se uma ação de correção tiver sido tomada em uma entidade (como um dispositivo ou uma mensagem de email) e a entidade afetada não for realmente uma ameaça, sua equipe de operações de segurança poderá desfazer a ação de correção no Centro de Ações [.](m365d-action-center.md)

1. Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre. 
2. No painel de navegação, escolha **Central de ações**. 
3. Na guia **Histórico,** selecione uma ação que você deseja desfazer. Seu painel de sobrevoo é aberto.
4. No painel de sobrevoos, selecione **Desfazer**.

> [!TIP]
> Consulte [Desfazer ações concluídas](m365d-autoir-actions.md#undo-completed-actions).

## <a name="see-also"></a>Confira também

- [Exibir os detalhes e resultados de uma investigação automatizada](m365d-autoir-results.md)
- [Busca proativamente por ameaças com busca avançada em Microsoft 365 Defender](advanced-hunting-overview.md)
