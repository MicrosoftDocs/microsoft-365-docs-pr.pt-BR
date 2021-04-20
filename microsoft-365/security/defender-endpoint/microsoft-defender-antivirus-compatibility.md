---
title: Compatibilidade do Microsoft Defender Antivírus com outros produtos de segurança
description: O que esperar do Microsoft Defender Antivírus com outros produtos de segurança e os sistemas operacionais que você está usando.
keywords: windows defender, próxima geração, antivírus, compatibilidade, modo passivo
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: tewchen, pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8e179135f12ad6f4ea765eaf975a40534446b51f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893384"
---
# <a name="microsoft-defender-antivirus-compatibility"></a>Compatibilidade com o Microsoft Defender Antivírus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

## <a name="overview"></a>Visão Geral

O Microsoft Defender Antivírus é habilitado e instalado automaticamente em pontos de extremidade e dispositivos que executam o Windows 10. Mas o que acontece quando outra solução antivírus/antimalware é usada? Depende se você está usando o Microsoft Defender para Ponto de Extremidade [juntamente](microsoft-defender-endpoint.md) com sua proteção antivírus.
- Se os pontos de extremidade e os dispositivos da sua organização estão protegidos com uma solução antivírus/antimalware que não seja da Microsoft e o Microsoft Defender para Ponto de Extremidade não é usado, o Microsoft Defender Antivírus entra automaticamente no modo desabilitado.
- Se sua organização estiver usando o Microsoft Defender para Ponto de Extremidade juntamente com uma solução antimalware/antivírus que não seja da Microsoft, o Microsoft Defender Antivírus entra automaticamente no modo passivo. (Proteção e ameaças em tempo real não são remediadas pelo Microsoft Defender Antivírus.)
- Se sua organização estiver usando o Microsoft Defender para Ponto de Extremidade juntamente com uma solução antivírus/antimalware que não seja da Microsoft e você tiver a [EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode) no modo de bloqueio habilitada, sempre que um artefato mal-intencionado for detectado, o Microsoft Defender for Endpoint tomará medidas para bloquear e remediar o artefato.

## <a name="antivirus-and-microsoft-defender-for-endpoint"></a>Antivírus e Microsoft Defender para Ponto de Extremidade

A tabela a seguir resume o que acontece com o Microsoft Defender Antivírus quando produtos antivírus de terceiros são usados juntos ou sem o Microsoft Defender para Ponto de Extremidade. 


| Versão do Windows   | Proteção antimalware  | Registro do Microsoft Defender para Ponto de Extremidade | Estado do Microsoft Defender Antivírus     |
|------|------|-------|-------|
| Windows 10  | Um produto de terceiros que não é oferecido ou desenvolvido pela Microsoft | Sim  | Modo passivo  |
| Windows 10  | Um produto de terceiros que não é oferecido ou desenvolvido pela Microsoft | Não   | Modo desabilitado automaticamente     |
| Windows 10  | Microsoft Defender Antivírus | Sim  | Modo ativo | 
| Windows 10  | Microsoft Defender Antivírus | Não   | Modo ativo |
| Windows Server, versão 1803 ou mais recente, ou Windows Server 2019 | Um produto de terceiros que não é oferecido ou desenvolvido pela Microsoft | Sim  | Deve ser definido como modo passivo (manualmente) <sup> [[1](#fn1)]<sup>  | 
| Windows Server, versão 1803 ou mais recente, ou Windows Server 2019 | Um produto de terceiros que não é oferecido ou desenvolvido pela Microsoft | Não  | Deve ser desabilitado (manualmente) <sup> [[2](#fn2)]<sup></sup>  |
| Windows Server, versão 1803 ou mais recente, ou Windows Server 2019 | Microsoft Defender Antivírus  | Sim |         Modo ativo  |
| Windows Server, versão 1803 ou mais recente, ou Windows Server 2019 | Microsoft Defender Antivírus | Não  | Modo ativo |
| Windows Server 2016 | Microsoft Defender Antivírus | Sim | Modo ativo |
| Windows Server 2016 | Microsoft Defender Antivírus | Não | Modo ativo |
| Windows Server 2016 | Um produto de terceiros que não é oferecido ou desenvolvido pela Microsoft | Sim | Deve ser desabilitado (manualmente) <sup> [[2](#fn2)]<sup> |
| Windows Server 2016 | Um produto de terceiros que não é oferecido ou desenvolvido pela Microsoft | Não | Deve ser desabilitado (manualmente) <sup> [[2](#fn2)]<sup> |

(<a id="fn1">1</a>) No Windows Server, versão 1803 ou mais recente, ou Windows Server 2019, o Microsoft Defender Antivírus não entra no modo passivo automaticamente quando você instala um produto antivírus que não seja da Microsoft. Nesses casos, [dejuste o Microsoft Defender Antivírus](microsoft-defender-antivirus-on-windows-server.md#need-to-set-microsoft-defender-antivirus-to-passive-mode) para o modo passivo para evitar problemas causados por ter vários produtos antivírus instalados em um servidor.

Se você estiver usando o Windows Server, versão 1803 ou mais recente, ou o Windows Server 2019, poderá definir o Microsoft Defender Antivírus como modo passivo definindo a seguinte chave do Registro:
- Caminho: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Nome: `ForceDefenderPassiveMode`
- Digite: `REG_DWORD`
- Valor: `1`

> [!NOTE]
> A `ForcePassiveMode` chave do Registro não é suportada no Windows Server 2016.

(<a id="fn2">2</a>) No Windows Server 2016, o Microsoft Defender Antivírus não entra no modo passivo automaticamente quando você instala um produto antivírus que não seja da Microsoft. Além disso, o Microsoft Defender Antivírus não tem suporte no modo passivo. Nesses casos, desabilite/desinstale o [Microsoft Defender Antivírus manualmente](microsoft-defender-antivirus-on-windows-server.md#are-you-using-windows-server-2016) para evitar problemas causados pela instalação de vários produtos antivírus em um servidor.

Consulte [o Microsoft Defender Antivírus no Windows Server para](microsoft-defender-antivirus-on-windows-server.md) saber mais sobre as principais diferenças e opções de gerenciamento para instalações do Windows Server.

> [!IMPORTANT]
> O Microsoft Defender Antivírus só está disponível em dispositivos que executam o Windows 10, o Windows Server 2016, o Windows Server, a versão 1803 ou posterior e o Windows Server 2019.
>
> No Windows 8.1 e no Windows Server 2012, a proteção antivírus de ponto de extremidade de nível empresarial é oferecida como Proteção de Ponto de Extremidade do [System Center](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10)), que é gerenciada por meio do Microsoft Endpoint Configuration Manager.
>
> Windows Defender também é oferecido para dispositivos de consumo no [Windows 8.1 e no Windows Server 2012](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender), embora não forneça gerenciamento de nível empresarial (ou uma interface nas instalações do Windows Server 2012 Server Core).

## <a name="functionality-and-features-available-in-each-state"></a>Funcionalidade e recursos disponíveis em cada estado

A tabela nesta seção resume a funcionalidade e os recursos disponíveis em cada estado. A tabela foi projetada para ser apenas informacional. Ele se destina a descrever os recursos & recursos que estão funcionando ativamente ou não, de acordo com se o Microsoft Defender Antivírus está no modo ativo, no modo passivo ou está desabilitado/desinstalado. 

> [!IMPORTANT]
> Não desativar recursos, como proteção em tempo real, proteção entregue na nuvem ou verificação periódica limitada, se você estiver usando o Microsoft Defender Antivírus no modo passivo ou estiver usando eDR no modo de bloqueio. 

|Proteção |Modo ativo |Modo passivo |EDR em modo de bloco |Desabilitado ou desinstalado |
|:---|:---|:---|:---|:---|
| [Proteção em tempo real e](./configure-real-time-protection-microsoft-defender-antivirus.md) proteção entregue na [nuvem](./enable-cloud-protection-microsoft-defender-antivirus.md) | Sim | Não <sup> [[3](#fn3)]<sup> | Não | Não |
| [Disponibilidade limitada de verificação periódica](./limited-periodic-scanning-microsoft-defender-antivirus.md) | Não | Não | Não | Sim |
| [Informações de verificação e detecção de arquivos](./customize-run-review-remediate-scans-microsoft-defender-antivirus.md) | Sim | Sim | Sim | Não |
|  [Correção de ameaças](./configure-remediation-microsoft-defender-antivirus.md) | Sim | Consulte observação <sup> [[4](#fn4)]<sup> | Sim | Não |
| [Atualizações de inteligência de segurança](./manage-updates-baselines-microsoft-defender-antivirus.md) | Sim | Sim | Sim | Não |

(<a id="fn3">3</a>) Em geral, quando o Microsoft Defender Antivírus está no modo passivo, a proteção em tempo real não fornece qualquer bloqueio ou imposição, mesmo que ele seja habilitado e no modo passivo. 

(<a id="fn4">4</a>) Quando o Microsoft Defender Antivírus está no modo passivo, os recursos de correção de ameaças ficam ativos somente durante verificações agendadas ou sob demanda.

> [!NOTE]
> A proteção de prevenção contra perda de dados do [Microsoft 365 Endpoint](/microsoft-365/compliance/endpoint-dlp-learn-about) continua a funcionar normalmente quando o Microsoft Defender Antivírus está no modo ativo ou passivo.

## <a name="keep-the-following-points-in-mind"></a>Lembre-se dos seguintes pontos

- No modo ativo, o Microsoft Defender Antivírus é usado como o aplicativo antivírus no computador. Todas as configurações feitas com o Configuration Manager, a Política de Grupo, o Intune ou outros produtos de gerenciamento serão aplicadas. Os arquivos são verificados e as ameaças são remediadas, e as informações de detecção são relatadas em sua ferramenta de configuração (como o Configuration Manager ou o aplicativo Microsoft Defender Antivírus no próprio computador).

- No modo passivo, o Microsoft Defender Antivírus não é usado como o aplicativo antivírus e as ameaças não são remediadas pelo Microsoft Defender Antivírus. Os arquivos são verificados e os relatórios são fornecidos para detecções de ameaças que são compartilhadas com o serviço Microsoft Defender para Ponto de Extremidade. Portanto, você pode encontrar alertas no console da Central de Segurança com o Microsoft Defender Antivírus como fonte, mesmo quando o Microsoft Defender Antivírus está no modo Passivo.

- Quando [o EDR no](/microsoft-365/security/defender-endpoint/edr-in-block-mode) modo de bloqueio é ligado e o Microsoft Defender Antivírus não é a solução antivírus principal, ele ainda pode detectar e remediar itens mal-intencionados.

- Quando desabilitado, o Microsoft Defender Antivírus não é usado como o aplicativo antivírus. Os arquivos não são verificados e as ameaças não são remediadas. Desabilitar/desinstalar o Microsoft Defender Antivírus não é recomendado em geral; se possível, mantenha o Microsoft Defender Antivírus no modo passivo se você estiver usando uma solução antimalware/antivírus que não seja da Microsoft.

- Se você estiver inscrito no Microsoft Defender para Ponto de Extremidade e estiver usando um produto antimalware de terceiros, o modo passivo será habilitado. [O serviço requer compartilhamento de informações comuns do serviço Microsoft Defender Antivírus](/microsoft-365/security/defender-endpoint/defender-compatibility) para monitorar corretamente seus dispositivos e rede para tentativas e ataques de intrusão.

- Quando o Microsoft Defender Antivírus é desabilitado automaticamente, ele pode ser reabilitar automaticamente se a proteção oferecida por um produto antivírus não Microsoft expirar ou, de outra forma, deixar de fornecer proteção em tempo real contra vírus, malware ou outras ameaças. A rehabilitação automática ajuda a garantir que a proteção antivírus seja mantida em seus dispositivos. Ele também permite que você habilita a verificação periódica [limitada,](limited-periodic-scanning-microsoft-defender-antivirus.md)que usa o mecanismo do Microsoft Defender Antivírus para verificar periodicamente as ameaças além do seu aplicativo antivírus principal.

- Quando o Microsoft Defender Antivírus está no modo passivo, você ainda pode [gerenciar atualizações do Microsoft Defender Antivírus;](manage-updates-baselines-microsoft-defender-antivirus.md) no entanto, você não pode mover o Microsoft Defender Antivírus para o modo ativo se seus dispositivos têm um produto antivírus atualizado que não seja da Microsoft fornecendo proteção em tempo real contra malware. Para uma melhor eficácia de defesa e detecção em camadas de segurança, certifique-se de atualizar a proteção do [Microsoft Defender Antivírus (atualização](./manage-updates-baselines-microsoft-defender-antivirus.md) de inteligência de segurança, Mecanismo e Plataforma) mesmo se o Microsoft Defender Antivírus estiver em execução no modo passivo.

   Se você desinstalar o produto antivírus que não é da Microsoft e usar o Microsoft Defender Antivírus para fornecer proteção para seus dispositivos, o Microsoft Defender Antivírus retornará automaticamente ao seu modo ativo normal.

> [!WARNING]
> Não desabilite, pare ou modifique nenhum dos serviços associados usados pelo Microsoft Defender Antivírus, Microsoft Defender para Ponto de Extremidade ou pelo aplicativo segurança do Windows. Esta recomendação inclui os processos e serviços *wscsvc,* *SecurityHealthService,* *MsSense*, *Sense,* *WinDefend* ou *MsMpEng.* Modificar manualmente esses serviços pode causar grave instabilidade em seus dispositivos e pode tornar sua rede vulnerável. Desabilitar, interromper ou modificar esses serviços também pode causar problemas ao usar soluções antivírus que não são da Microsoft e como suas informações são exibidas no aplicativo [segurança do Windows.](microsoft-defender-security-center-antivirus.md)


## <a name="see-also"></a>Confira também

- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivírus no Windows Server](microsoft-defender-antivirus-on-windows-server.md)
- [EDR em modo de bloco](edr-in-block-mode.md)
- [Configurar a Proteção de Ponto de Extremidade](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
- [Endereços falsos positivos/negativos no Microsoft Defender para Ponto de Extremidade](defender-endpoint-false-positives-negatives.md)
- [Saiba mais sobre a prevenção contra Perda de Dados de Ponto de Extremidade do Microsoft 365](/microsoft-365/compliance/endpoint-dlp-learn-about)
