---
title: Solucionar problemas com a proteção de rede
description: Recursos e código de exemplo para solucionar problemas com a proteção de rede no Microsoft Defender para Ponto de Extremidade.
keywords: troubleshoot, error, fix, windows defender eg, asr, rules, hips, troubleshoot, audit, exclusion, false positive, broken, blocking, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: f77ce94fda63a9e7e8a9484a67a22eeec136d619
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935876"
---
# <a name="troubleshoot-network-protection"></a>Solucionar problemas de proteção de rede

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


Ao usar a [proteção de rede,](network-protection.md) você pode encontrar problemas, como:

- A proteção de rede bloqueia um site seguro (falso positivo)
- A proteção de rede falha ao bloquear um site mal-intencionado suspeito ou conhecido (falso negativo)

Há quatro etapas para solucionar esses problemas:

1. Confirmar pré-requisitos
2. Usar o modo de auditoria para testar a regra
3. Adicionar exclusões para a regra especificada (para falsos positivos)
4. Enviar logs de suporte

## <a name="confirm-prerequisites"></a>Confirmar pré-requisitos

A proteção de rede funcionará apenas em dispositivos com as seguintes condições:

>[!div class="checklist"]
> - Os pontos de extremidade estão executando o Windows 10 Pro ou Enterprise edition, versão 1709 ou superior.
> - Os pontos de extremidade estão usando o Microsoft Defender Antivírus como o único aplicativo de proteção antivírus. [Veja o que acontece quando você está usando uma solução antivírus que não seja da Microsoft.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
> - [A proteção em tempo real](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) está habilitada.
> - [A proteção entregue na nuvem](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) está habilitada.
> - O modo de auditoria não está habilitado. Use [a Política de](enable-network-protection.md#group-policy) Grupo para definir a regra como **Desabilitada** (valor: **0**).

## <a name="use-audit-mode"></a>Usar o modo de auditoria

Você pode habilitar a proteção de rede no modo de auditoria e visitar um site que criamos para demonstração do recurso. Todas as conexões de site serão permitidas pela proteção de rede, mas um evento será registrado para indicar qualquer conexão que tenha sido bloqueada se a proteção de rede estivesse habilitada.

1. Definir a proteção de rede como **modo de auditoria.**

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. Execute a atividade de conexão que está causando um problema (por exemplo, tente visitar o site ou conecte-se ao endereço IP que você faz ou não deseja bloquear).

3. [Revise os logs de eventos de](network-protection.md#review-network-protection-events-in-windows-event-viewer) proteção de rede para ver se o recurso teria bloqueado a conexão se tivesse sido definido como **Habilitado**.
   
   Se a proteção de rede não estiver bloqueando uma conexão que você espera que ela bloqueie, habilita o recurso.

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a>Relatar um falso positivo ou falso negativo

Se você testou o recurso com o site de demonstração e com o modo de auditoria, e a proteção de rede está funcionando em cenários pré-configurados, mas não está funcionando conforme o esperado para uma conexão específica, use o formulário de envio baseado na Web do [Windows Defender Security Intelligence](https://www.microsoft.com/wdsi/filesubmission) para relatar um falso negativo ou falso positivo para proteção de rede. Com uma assinatura do E5, você também pode fornecer um [link para qualquer alerta associado.](alerts-queue.md)

Consulte [Address false positives/negatives in Microsoft Defender for Endpoint](defender-endpoint-false-positives-negatives.md).

## <a name="exclude-website-from-network-protection-scope"></a>Excluir site do escopo de proteção de rede

Para permitir que o site que está sendo bloqueado (falso positivo), adicione sua URL à [lista de sites confiáveis](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/). Os recursos da Web desta lista ignoram a verificação de proteção de rede.

## <a name="collect-diagnostic-data-for-file-submissions"></a>Coletar dados de diagnóstico para envios de arquivos

Quando você relata um problema com a proteção de rede, é solicitado a coletar e enviar dados de diagnóstico que podem ser usados pelas equipes de suporte e engenharia da Microsoft para ajudar a solucionar problemas.

1. Abra um prompt de comando elevado e altere para o Windows Defender diretório:

   ```console
   cd c:\program files\windows defender
   ```

2. Execute este comando para gerar os logs de diagnóstico:

   ```console
   mpcmdrun -getfiles
   ```

3. Anexe o arquivo ao formulário de envio. Por padrão, os logs de diagnóstico são salvos em `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` . 

## <a name="resolve-connectivity-issues-with-network-protection-for-e5-customers"></a>Resolver problemas de conectividade com a proteção de rede (para clientes E5)

Devido ao ambiente em que a proteção de rede é executado, a Microsoft não consegue ver as configurações de proxy do sistema operacional. Em alguns casos, os clientes de proteção de rede não conseguem alcançar o serviço de nuvem. Para resolver problemas de conectividade com a proteção de rede, configure uma das seguintes chaves do Registro para que a proteção de rede fique ciente da configuração de proxy:

```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
```

---OR---


```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f
```

Você pode configurar a chave do Registro usando o PowerShell, o Microsoft Endpoint Manager ou a Política de Grupo. Aqui estão alguns recursos para ajudar:
- [Trabalhando com chaves do Registro](/powershell/scripting/samples/working-with-registry-keys)
- [Configurar configurações de cliente personalizadas para a Proteção de Ponto de Extremidade](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client)
- [Usar configurações de Política de Grupo para gerenciar a Proteção de Ponto de Extremidade](/mem/configmgr/protect/deploy-use/endpoint-protection-group-policies)

## <a name="see-also"></a>Confira também

- [Proteção de rede](network-protection.md)
- [Avaliar a proteção de rede](evaluate-network-protection.md)
- [Habilitar a proteção de rede](enable-network-protection.md)
- [Resolver falsos positivos/negativos no Defender para Ponto de Extremidade](defender-endpoint-false-positives-negatives.md)
