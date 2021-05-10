---
title: Microsoft Defender Antivírus compatibilidade com outros produtos de segurança
description: Saiba mais Microsoft Defender Antivírus outros produtos de segurança e sistemas operacionais.
keywords: windows defender, defender para ponto de extremidade, próxima geração, antivírus, compatibilidade, modo passivo
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: tewchen, pahuijbr
ms.topic: article
manager: dansimp
ms.technology: mde
ms.date: 05/08/2021
ms.openlocfilehash: 072ad4e536f753550462fa80650bef392a147e64
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52301747"
---
# <a name="microsoft-defender-antivirus-compatibility"></a>Microsoft Defender Antivírus compatibilidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

## <a name="summary"></a>Resumo

Microsoft Defender Antivírus é automaticamente habilitado e instalado em pontos de extremidade e dispositivos que estão executando Windows 10. Mas o que acontece quando outra solução antivírus/antimalware (não Microsoft) é usada? Depende se você está usando o Microsoft Defender para Ponto de Extremidade [juntamente](microsoft-defender-endpoint.md) com sua proteção antivírus. Este artigo descreve o que acontece com soluções antivírus/antimalware quando os pontos de extremidade são integrados ao Microsoft Defender para Ponto de Extremidade.

## <a name="keep-the-following-points-in-mind"></a>Lembre-se dos seguintes pontos

- No modo ativo, Microsoft Defender Antivírus é usado como o aplicativo antivírus no computador. Todas as configurações feitas com o Configuration Manager, a Política de Grupo, o Intune ou outros produtos de gerenciamento serão aplicadas. Os arquivos são verificados e as ameaças são remediadas e as informações de detecção são relatadas na ferramenta de configuração (como o Configuration Manager ou o Microsoft Defender Antivírus aplicativo no próprio computador).

- No modo passivo, Microsoft Defender Antivírus não é usado como o aplicativo antivírus e as ameaças não são remediadas por Microsoft Defender Antivírus. Os arquivos são verificados e os relatórios são fornecidos para detecções de ameaças que são compartilhadas com o serviço Microsoft Defender para Ponto de Extremidade. Você pode ver alertas no [centro](microsoft-defender-security-center.md) de segurança mostrando Microsoft Defender Antivírus como uma fonte, mesmo quando Microsoft Defender Antivírus está no modo passivo.

- Quando [EDR no](edr-in-block-mode.md) modo de bloqueio estiver ligado e Microsoft Defender Antivírus não for a solução antivírus principal, ele detectará e remediará itens mal-intencionados. EDR no modo de bloqueio requer Microsoft Defender Antivírus ser habilitado no modo ativo ou no modo passivo.

- Quando desabilitado, Microsoft Defender Antivírus não é usado como o aplicativo antivírus. Os arquivos não são verificados e as ameaças não são remediadas. Desabilitar/desinstalar Microsoft Defender Antivírus não é recomendado em geral; se possível, mantenha Microsoft Defender Antivírus no modo passivo se você estiver usando uma solução antimalware/antivírus que não seja da Microsoft.

- Se você estiver inscrito no Microsoft Defender para Ponto de Extremidade e estiver usando um produto antimalware de terceiros, o modo passivo será habilitado. O serviço exige o compartilhamento de informações comuns Microsoft Defender Antivírus serviço para monitorar corretamente seus dispositivos e rede para tentativas e ataques de intrusão. Para saber mais, confira [Microsoft Defender Antivírus compatibilidade com o Microsoft Defender para Ponto de Extremidade](defender-compatibility.md). 

- Quando Microsoft Defender Antivírus está no modo passivo, você ainda pode [gerenciar atualizações para](manage-updates-baselines-microsoft-defender-antivirus.md)Microsoft Defender Antivírus; no entanto, você não pode mover o Microsoft Defender Antivírus para o modo ativo se seus dispositivos têm um produto antivírus atualizado que não seja da Microsoft que está fornecendo proteção em tempo real contra malware. Para obter uma eficácia ideal de defesa e detecção em camadas de segurança, atualize a proteção de Microsoft Defender Antivírus [(atualização de](manage-updates-baselines-microsoft-defender-antivirus.md) inteligência de segurança, Mecanismo e Plataforma) mesmo que o Microsoft Defender Antivírus seja executado no modo passivo.

- Quando o Microsoft Defender Antivírus é desabilitado automaticamente, ele pode ser reabilitar automaticamente se a proteção oferecida por um produto antivírus que não seja da Microsoft expirar ou se deixar de fornecer proteção em tempo real contra vírus, malware ou outras ameaças. A rehabilitação automática ajuda a garantir que a proteção antivírus seja mantida em seus dispositivos. Ele também permite que você habilita a verificação periódica limitada [,](limited-periodic-scanning-microsoft-defender-antivirus.md)que usa o mecanismo Microsoft Defender Antivírus para verificar periodicamente se há ameaças além do seu aplicativo antivírus principal.

## <a name="microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions"></a>Microsoft Defender Antivírus e soluções antimalware que não são da Microsoft

A tabela a seguir resume o que acontece com o Microsoft Defender Antivírus quando soluções antimalware/antivírus não-Microsoft são usadas juntas ou sem o Microsoft Defender para Ponto de Extremidade. 

| Versão do Windows   | Solução antivírus/antimalware  | Onboarded to <br/> Defender para Ponto de Extremidade? | Microsoft Defender Antivírus estado     |
|------|------|-------|-------|
| Windows 10  | Microsoft Defender Antivírus | Sim  | Modo ativo | 
| Windows 10  | Microsoft Defender Antivírus | Não   | Modo ativo |
| Windows 10  | Uma solução antivírus/antimalware que não seja da Microsoft | Sim  | Modo passivo (automaticamente) |
| Windows 10  | Uma solução antivírus/antimalware que não seja da Microsoft | Não   | Modo desabilitado (automaticamente)    |
| Windows Servidor, versão 1803 ou mais recente <p> Windows Server 2019 | Microsoft Defender Antivírus  | Sim |         Modo ativo  |
| Windows Servidor, versão 1803 ou mais recente <p> Windows Server 2019 | Microsoft Defender Antivírus | Não  | Modo ativo |
| Windows Servidor, versão 1803 ou mais recente <p> Windows Server 2019 | Uma solução antivírus/antimalware que não seja da Microsoft | Sim  | Microsoft Defender Antivírus deve ser definido como modo passivo (manualmente) <sup> [[1](#fn1)]<sup>  | 
| Windows Servidor, versão 1803 ou mais recente <p> Windows Server 2019 | Uma solução antivírus/antimalware que não seja da Microsoft | Não  | Microsoft Defender Antivírus deve ser desabilitado (manualmente) <sup> [[2](#fn2)]<sup></sup>  |
| Windows Server 2016 | Microsoft Defender Antivírus | Sim | Modo ativo |
| Windows Server 2016 | Microsoft Defender Antivírus | Não | Modo ativo |
| Windows Server 2016 | Uma solução antivírus/antimalware que não seja da Microsoft | Sim | Microsoft Defender Antivírus deve ser desabilitado (manualmente) <sup> [[2](#fn2)]<sup> |
| Windows Server 2016 | Uma solução antivírus/antimalware que não seja da Microsoft | Não | Microsoft Defender Antivírus deve ser desabilitado (manualmente) <sup> [[2](#fn2)]<sup> |

(<a id="fn1">1</a>) No Windows Server, versão 1803 ou mais recente, ou Windows Server 2019, o Microsoft Defender Antivírus não entra no modo passivo automaticamente quando você instala um produto antivírus que não seja da Microsoft. Nesses casos, [dejuste Microsoft Defender Antivírus modo passivo](microsoft-defender-antivirus-on-windows-server.md#need-to-set-microsoft-defender-antivirus-to-passive-mode) para evitar problemas causados por ter vários produtos antivírus instalados em um servidor. Você pode definir Microsoft Defender Antivírus modo passivo usando o PowerShell, a Política de Grupo ou uma chave do Registro.

Se você estiver usando o Windows Server, versão 1803 ou mais recente, ou Windows Server 2019, poderá definir o Microsoft Defender Antivírus para o modo passivo definindo a seguinte chave do Registro:
- Caminho: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Nome: `ForceDefenderPassiveMode`
- Digite: `REG_DWORD`
- Valor: `1`

> [!NOTE]
> O modo passivo não é suportado no Windows Server 2016. A chave do Registro pode ser usada no Windows Server, versão 1803 ou mais recente, ou `ForcePassiveMode` Windows Server 2019, mas não Windows Server 2016. 

(<a id="fn2">2</a>) No Windows Server 2016, se você estiver usando um produto antivírus que não seja da Microsoft, não poderá executar Microsoft Defender Antivírus no modo passivo ou no modo ativo. Nesses casos, [desabilite/desinstale](microsoft-defender-antivirus-on-windows-server.md#are-you-using-windows-server-2016) Microsoft Defender Antivírus manualmente para evitar problemas causados pela instalação de vários produtos antivírus em um servidor.

Consulte [Microsoft Defender Antivírus no Windows Server](microsoft-defender-antivirus-on-windows-server.md) para saber mais sobre as principais diferenças e opções de gerenciamento para instalações Windows Server.

> [!IMPORTANT]
> Microsoft Defender Antivírus está disponível apenas em dispositivos que executam Windows 10, Windows Server 2016, Windows Server, versão 1803 ou posterior e Windows Server 2019.
>
> No Windows 8.1 e Windows Server 2012, a proteção antivírus de ponto de extremidade de nível empresarial é oferecida como [System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10)), que é gerenciada por meio Microsoft Endpoint Configuration Manager.
>
> Windows Defender também é oferecido para dispositivos de consumidor em Windows 8.1 e [Windows Server 2012](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender), embora não forneça gerenciamento de nível empresarial (ou uma interface em instalações do Windows Server 2012 Server Core).

## <a name="how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality"></a>Como Microsoft Defender Antivírus afeta a funcionalidade do Defender para Ponto de Extremidade

A tabela nesta seção resume a funcionalidade e os recursos disponíveis em cada estado. A tabela foi projetada para ser apenas informacional. Ele se destina a descrever os recursos & recursos que estão funcionando ativamente ou não, de acordo com o Microsoft Defender Antivírus está no modo ativo, no modo passivo ou está desabilitado/desinstalado. 

> [!IMPORTANT]
> Não desativar recursos, como proteção em tempo real, proteção entregue na nuvem ou verificação periódica limitada, se você estiver usando o Microsoft Defender Antivírus no modo passivo ou estiver usando EDR no modo de bloqueio. 

|Proteção |Modo ativo |Modo passivo |EDR em modo de bloco |Desabilitado ou desinstalado |
|:---|:---|:---|:---|:---|
| [Proteção em tempo real e](configure-real-time-protection-microsoft-defender-antivirus.md) proteção entregue na [nuvem](enable-cloud-protection-microsoft-defender-antivirus.md) | Sim | Não <sup> [[3](#fn3)]<sup> | Não | Não |
| [Disponibilidade limitada de verificação periódica](limited-periodic-scanning-microsoft-defender-antivirus.md) | Não | Não | Não | Sim |
| [Informações de verificação e detecção de arquivos](customize-run-review-remediate-scans-microsoft-defender-antivirus.md) | Sim | Sim | Sim | Não |
|  [Correção de ameaças](configure-remediation-microsoft-defender-antivirus.md) | Sim | Consulte observação <sup> [[4](#fn4)]<sup> | Sim | Não |
| [Atualizações de inteligência de segurança](manage-updates-baselines-microsoft-defender-antivirus.md) | Sim | Sim | Sim | Não |

(<a id="fn3">3</a>) Em geral, quando o Microsoft Defender Antivírus está no modo passivo, a proteção em tempo real não fornece qualquer bloqueio ou imposição, mesmo que ela seja habilitada e no modo passivo. 

(<a id="fn4">4</a>) Quando Microsoft Defender Antivírus no modo passivo, os recursos de correção de ameaças ficam ativos somente durante verificações agendadas ou sob demanda.

> [!NOTE]
> [Microsoft 365 proteção de prevenção](/microsoft-365/compliance/endpoint-dlp-learn-about) contra perda de dados do ponto de extremidade continua a funcionar normalmente quando Microsoft Defender Antivírus está no modo ativo ou passivo.

## <a name="why-defender-for-endpoint-matters"></a>Por que o Defender para Ponto de Extremidade importa

Considere a integração de seus pontos de extremidade com o Defender para Ponto de Extremidade, mesmo se você estiver usando uma solução antivírus/antimalware que não seja da Microsoft. Na maioria dos casos, quando você integra seus dispositivos no Defender para Ponto de Extremidade, você pode usar o Microsoft Defender Antivírus juntamente com sua solução antivírus não Microsoft para proteção adicionada. Por exemplo, você pode usar [EDR](edr-in-block-mode.md)modo de bloqueio , que bloqueia e remedia artefatos mal-intencionados que sua solução antivírus principal pode ter perdido. 

Veja como funciona:

- Se os dispositivos cliente da sua organização estão protegidos por uma solução antivírus/antimwalware que não seja da Microsoft, quando esses dispositivos estão a bordo do Defender para Ponto de Extremidade, o Microsoft Defender Antivírus entra no modo passivo automaticamente. Nesse caso, ocorrem detecções de ameaças, mas a proteção e as ameaças em tempo real não são remediadas por Microsoft Defender Antivírus. **OBSERVAÇÃO**: Este cenário específico não se aplica aos pontos de extremidade que executam Windows Server.

- Se os dispositivos cliente da sua organização estão protegidos por uma solução antivírus/antimalware que não seja da Microsoft e esses dispositivos não estão integradas ao Microsoft Defender para Ponto de Extremidade, Microsoft Defender Antivírus entra no modo desabilitado automaticamente. Nesse caso, as ameaças não são detectadas ou remediadas por Microsoft Defender Antivírus. **OBSERVAÇÃO**: Este cenário específico não se aplica aos pontos de extremidade que executam Windows Server.

- Se os pontos de extremidade da sua organização estão executando o Windows Server e esses pontos de extremidade são protegidos por uma solução antivírus/antimalware que não seja da Microsoft, quando esses pontos de extremidade são aderido ao Defender para Ponto de Extremidade, o Microsoft Defender Antivírus não entra no modo passivo ou desabilitado automaticamente. Nesse cenário específico, você deve configurar seus pontos de extremidade Windows Server adequadamente. 

   - No Windows Server, versão 1803 ou mais recente e Windows Server 2019, você pode definir Microsoft Defender Antivírus para ser executado no modo passivo. 
   - No Windows Server 2016, Microsoft Defender Antivírus deve ser desabilitado (o modo passivo não é suportado no Windows Server 2016).

- Se os pontos de extremidade da sua organização estão protegidos por uma solução antivírus/antimalware que não seja da Microsoft, quando esses dispositivos são integradas ao Defender para Ponto de Extremidade [com EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode) no modo de bloqueio habilitado, o Defender for Endpoint bloqueia e correção de artefatos mal-intencionados. **OBSERVAÇÃO**: Este cenário específico não se aplica a Windows Server 2016. EDR no modo de bloqueio requer Microsoft Defender Antivírus ser habilitado no modo ativo ou no modo passivo.


> [!WARNING]
> Não desabilite, pare ou modifique nenhum dos serviços associados que são usados pelo Microsoft Defender Antivírus, Microsoft Defender para Ponto de Extremidade ou pelo aplicativo Segurança do Windows. Esta recomendação inclui os processos e serviços *wscsvc,* *SecurityHealthService,* *MsSense*, *Sense,* *WinDefend* ou *MsMpEng.* Modificar manualmente esses serviços pode causar grave instabilidade em seus dispositivos e pode tornar sua rede vulnerável. Desabilitar, interromper ou modificar esses serviços também pode causar problemas ao usar soluções antivírus que não são da Microsoft e como suas informações são exibidas no aplicativo [Segurança do Windows .](microsoft-defender-security-center-antivirus.md)


## <a name="see-also"></a>Confira também

- [Microsoft Defender Antivirus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivírus no Windows Server](microsoft-defender-antivirus-on-windows-server.md)
- [EDR em modo de bloco](edr-in-block-mode.md)
- [Configurar Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
- [Endereços falsos positivos/negativos no Microsoft Defender para Ponto de Extremidade](defender-endpoint-false-positives-negatives.md)
- [Saiba mais sobre a prevenção contra Perda de Dados de Ponto de Extremidade do Microsoft 365](/microsoft-365/compliance/endpoint-dlp-learn-about)
