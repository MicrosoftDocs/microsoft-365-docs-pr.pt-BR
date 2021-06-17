---
title: Avaliar as regras da redução da superfície de ataque
description: Veja como a redução de superfície de ataque bloquearia e impediria ataques com a ferramenta de demonstração personalizada.
keywords: Redução de superfície de ataque, quadris, sistema de prevenção contra invasões de host, regras de proteção, antiexploit, exploração, prevenção de infecção, avaliação, teste, demonstração
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a5fa8e46de0a6561d3377ce77e38bd59aa97f3c4
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984719"
---
# <a name="evaluate-attack-surface-reduction-rules"></a>Avaliar as regras da redução da superfície de ataque

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

As regras de redução de superfície de ataque ajudam a evitar ações normalmente usadas pelo malware para comprometer dispositivos ou redes. As regras de redução de superfície de ataque ajudam a fechar muitos dos pontos de entrada comuns usados por malware e ransomware.

Definir regras de redução de superfície de ataque para dispositivos que executam qualquer uma das seguintes edições e versões de Windows:

- Windows 10 Pro, versão [1709](/windows/whats-new/whats-new-windows-10-version-1709) ou posterior
- Windows 10 Enterprise, versão [1709](/windows/whats-new/whats-new-windows-10-version-1709) ou posterior
- Windows Servidor, [versão 1803 (Canal Semesanuais)](/windows-server/get-started/whats-new-in-windows-server-1803) ou posterior
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

> [!WARNING]
> Habilitando regras de redução de serviço de ataque Windows Server 2016 pode levar a resultados inesperados e afetar o desempenho do servidor. Não recomendamos a habilitação ou a implantação de regras de redução de superfície de ataque em plataformas sem suporte.

Saiba como avaliar as regras de redução de superfície de ataque [habilitando o](audit-windows-defender.md) modo de auditoria para testar o recurso diretamente em sua organização.

> [!TIP]
> Você também pode visitar o site de [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) cenário de demonstração do Microsoft Defender para Ponto de Extremidade no demo.wd.microsoft.com para confirmar se o recurso está funcionando e ver como ele funciona.

## <a name="use-audit-mode-to-measure-impact"></a>Usar o modo de auditoria para medir o impacto

Habilita as regras de redução de superfície de ataque no modo de auditoria para exibir um registro de aplicativos que teriam sido bloqueados se o recurso estivesse totalmente habilitado. Teste como o recurso funcionará em sua organização para garantir que ele não afeta seus aplicativos de linha de negócios. Você também pode ter uma ideia de com que frequência as regras serão a disparar durante o uso normal.

Para habilitar uma regra de redução de superfície de ataque no modo de auditoria, use o seguinte cmdlet do PowerShell:

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

Onde `<rule ID>` está um valor GUID da regra de [redução de superfície de ataque](attack-surface-reduction.md#attack-surface-reduction-rules).

Para habilitar todas as regras de redução de superfície de ataque adicionadas no modo de auditoria, use o seguinte cmdlet do PowerShell:

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> Se você quiser auditar totalmente como as regras de redução de superfície de ataque funcionarão em sua organização, você precisará usar uma ferramenta de gerenciamento para implantar essa configuração em dispositivos em sua rede.

Você também pode usar a Política de Grupo, o Intune ou os provedores de serviços de configuração (CSPs) de gerenciamento de dispositivo móvel (CSPs) para configurar e implantar a configuração. Saiba mais no artigo principal [Regras de redução de superfície de](attack-surface-reduction.md) ataque.

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>Revisar eventos de redução de superfície de ataque Windows Visualizador de Eventos

Para revisar aplicativos que teriam sido bloqueados, abra o Visualizador de Eventos e filtre a ID do Evento 1121 no log Microsoft-Windows-Windows Defender/Operacional. A tabela a seguir lista todos os eventos de proteção de rede.

ID do Evento | Descrição
-|-
 5007 | Evento quando as configurações são alteradas
 1121 | Evento quando uma regra de redução de superfície de ataque dispara no modo de bloqueio
 1122 | Evento quando uma regra de redução de superfície de ataque é ativas no modo de auditoria

## <a name="customize-attack-surface-reduction-rules"></a>Personalizar regras da redução da superfície de ataque

Durante sua avaliação, você pode querer configurar cada regra individualmente ou excluir determinados arquivos e processos de serem avaliados pelo recurso.

Consulte [Personalizar regras de redução de superfície de](customize-attack-surface-reduction.md) ataque para obter informações sobre como configurar o recurso com ferramentas de gerenciamento, incluindo políticas de Política de Grupo e CSP MDM.

## <a name="see-also"></a>Confira também

- [Reduzir superfícies de ataque com regras de redução de superfície de ataque](attack-surface-reduction.md)
- [Usar o modo de auditoria para avaliar Windows Defender](audit-windows-defender.md)
- [Perguntas frequentes sobre a redução da superfície de ataque](attack-surface-reduction.md)
