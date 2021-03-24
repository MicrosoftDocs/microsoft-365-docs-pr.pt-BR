---
title: Avaliar a proteção de rede
description: Veja como a proteção de rede funciona testando cenários comuns contra os qual ela protege.
keywords: Proteção de rede, explorações, site mal-intencionado, ip, domínio, domínios, avaliar, testar, demonstração
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 41d1c9400720e20185922a97463e776c3ce0d80a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053382"
---
# <a name="evaluate-network-protection"></a>Avaliar a proteção de rede

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- - [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[A proteção de](network-protection.md) rede ajuda a impedir que os funcionários usem qualquer aplicativo para acessar domínios perigosos que podem hospedar esquemas de phishing, explorações e outros conteúdos mal-intencionados na Internet.

Este artigo ajuda você a avaliar a proteção de rede habilitando o recurso e orientando você para um site de teste. Os sites neste artigo de avaliação não são mal-intencionados. Eles são sites criados especialmente que se parecem mal-intencionados. O site replicará o comportamento que ocorreria se um usuário visitasse um site ou domínio mal-intencionado.

> [!TIP]
> Você também pode visitar o site do Microsoft Defender Testground [no](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) demo.wd.microsoft.com para ver como funcionam outros recursos de proteção.

## <a name="enable-network-protection-in-audit-mode"></a>Habilitar a proteção de rede no modo de auditoria

Habilita a proteção de rede no modo de auditoria para ver quais endereços IP e domínios teriam sido bloqueados. Você pode garantir que ele não afete aplicativos de linha de negócios ou ter uma ideia da frequência com que os bloqueios ocorrem.

1. Digite **o powershell** no menu Iniciar, clique com o botão direito do **mouse Windows PowerShell** e selecione Executar como **administrador**
2. Insira o seguinte cmdlet:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

### <a name="visit-a-fake-malicious-domain"></a>Visite um domínio mal-intencionado (falso)

1. Abra o Internet Explorer, o Google Chrome ou qualquer outro navegador de sua preferência.

1. Acesse [https://smartscreentestratings2.net](https://smartscreentestratings2.net).

A conexão de rede será permitida e uma mensagem de teste será exibida.

![Notificação de exemplo que diz Conexão bloqueada: o administrador de IT fez com que o Windows Security bloqueava essa conexão de rede. Entre em contato com seu help desk de IT.](/microsoft-365/security/defender-endpoint/images/np-notif)

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Revisar eventos de proteção de rede no Visualizador de Eventos do Windows

Para revisar aplicativos que teriam sido bloqueados, abra o Visualizador de Eventos e filtre a ID do Evento 1125 no log Microsoft-Windows-Windows-Defender/Operational. A tabela a seguir lista todos os eventos de proteção de rede.

| ID de evento | Fornecer/Fonte | Descrição |
|-|-|-|
|5007 | Windows Defender (Operacional) | Evento quando as configurações são alteradas |
|1125 | Windows Defender (Operacional) | Evento quando uma conexão de rede é auditada |
|1126 | Windows Defender (Operacional) | Evento quando uma conexão de rede é bloqueada |

## <a name="see-also"></a>Confira também

* [Proteção de rede](network-protection.md)
* [Habilitar a proteção de rede](enable-network-protection.md)
* [Solucionar problemas de proteção de rede](troubleshoot-np.md)
