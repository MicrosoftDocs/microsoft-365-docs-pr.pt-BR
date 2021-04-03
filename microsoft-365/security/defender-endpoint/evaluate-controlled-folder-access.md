---
title: Avaliar o acesso controlado a pastas
description: Veja como o acesso controlado a pastas pode ajudar a proteger os arquivos de serem alterados por aplicativos mal-intencionados.
keywords: Exploit protection, windows 10, windows defender, ransomware, protect, evaluate, test, demo, try
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f996a8fdaf630c8ea389ac9648369cc955a6e95d
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51569892"
---
# <a name="evaluate-controlled-folder-access"></a>Avaliar o acesso controlado a pastas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


[O acesso controlado](controlled-folders.md) a pastas é um recurso que ajuda a proteger seus documentos e arquivos contra modificação por aplicativos suspeitos ou mal-intencionados. O acesso controlado a pastas é suportado nos clientes do Windows Server 2019 e do Windows 10.

É especialmente útil ajudar a proteger contra [ransomware](https://www.microsoft.com/wdsi/threats/ransomware) que tenta criptografar seus arquivos e mantê-los como reféns.

Este artigo ajuda você a avaliar o acesso controlado a pastas. Ele explica como habilitar o modo de auditoria para que você possa testar o recurso diretamente em sua organização.

> [!TIP]
> Você também pode visitar o site de [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) cenário de demonstração do Microsoft Defender para Ponto de Extremidade no demo.wd.microsoft.com para confirmar se o recurso está funcionando e ver como ele funciona.

## <a name="use-audit-mode-to-measure-impact"></a>Usar o modo de auditoria para medir o impacto

Habilita o acesso controlado a pastas no modo de auditoria para ver um registro do que *teria* ocorrido se estivesse totalmente habilitado. Teste como o recurso funcionará em sua organização para garantir que ele não afeta seus aplicativos de linha de negócios. Você também pode ter uma ideia de quantas tentativas suspeitas de modificação de arquivo geralmente ocorrem em um determinado período de tempo.

Para habilitar o modo de auditoria, use o seguinte cmdlet do PowerShell:

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> Se você quiser auditar totalmente como o acesso controlado a pastas funcionará em sua organização, você precisará usar uma ferramenta de gerenciamento para implantar essa configuração em dispositivos em sua rede.
Você também pode usar a Política de Grupo, o Intune, o gerenciamento de dispositivo móvel (MDM) ou o Microsoft Endpoint Manager para configurar e implantar a configuração, conforme descrito no tópico principal de acesso controlado [a pastas.](controlled-folders.md)

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>Revisar eventos de acesso controlado a pastas no Visualizador de Eventos do Windows

Os seguintes eventos de acesso controlado a pastas aparecem no Visualizador de Eventos do Windows na pasta Microsoft/Windows/Windows Defender/Operacional.

ID de evento | Descrição
-|-
 5007 | Evento quando as configurações são alteradas
 1124 | Evento de acesso controlado a pastas auditadas
 1123 | Evento de acesso controlado de pasta bloqueado

> [!TIP]
> Você pode configurar uma assinatura [de Encaminhamento de](https://docs.microsoft.com/windows/win32/wec/setting-up-a-source-initiated-subscription) Eventos do Windows para coletar os logs centralmente. 

## <a name="customize-protected-folders-and-apps"></a>Personalizar pastas e aplicativos protegidos

Durante sua avaliação, você pode desejar adicionar à lista de pastas protegidas ou permitir que determinados aplicativos modifiquem arquivos.

Consulte [Proteger pastas importantes](controlled-folders.md) com acesso controlado a pastas para configurar o recurso com ferramentas de gerenciamento, incluindo A Política de Grupo, PowerShell e provedores de serviços de configuração de MDM (CSPs).

## <a name="see-also"></a>Confira também

* [Proteger pastas importantes com acesso controlado a pastas](controlled-folders.md)
* [Avaliar o Microsoft Defender para Ponto de Extremidade](evaluate-mde.md)
* [Usar o modo de auditoria](audit-windows-defender.md)
