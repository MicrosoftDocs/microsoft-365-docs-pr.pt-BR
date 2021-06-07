---
title: Proteção fornecida na nuvem e Microsoft Defender Antivírus
description: Saiba mais sobre proteção entregue na nuvem e Microsoft Defender Antivírus
keywords: Microsoft Defender Antivírus, tecnologias de última geração, av de última geração, aprendizado de máquina, antimalware, segurança, defensor, nuvem, proteção entregue na nuvem
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: shwjha
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 836025b42bbe6142f462ee31f266a636f5101fe9
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52783000"
---
# <a name="cloud-delivered-protection-and-microsoft-defender-antivirus"></a>Proteção fornecida na nuvem e Microsoft Defender Antivírus

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender Antivírus

As tecnologias de próxima geração Microsoft Defender Antivírus oferecem proteção quase instantânea e automatizada contra ameaças novas e emergentes. Para identificar novas ameaças dinamicamente, as tecnologias de próxima geração trabalham com grandes conjuntos de dados interconectados nos sistemas de inteligência artificial (AI) da Microsoft Intelligent Graph Security e da inteligência artificial avançada, orientados por modelos avançados de aprendizado de máquina. Microsoft Defender Antivírus usa várias tecnologias de detecção e prevenção para oferecer proteção precisa, em tempo real e inteligente. 

> [!TIP]
> Deseja saber mais? Consulte a postagem do blog, Conheça as tecnologias avançadas no núcleo do [Microsoft Defender para Endpoint de proteção de próxima geração.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)

Microsoft Defender Antivírus funciona perfeitamente com os serviços de nuvem da Microsoft. Esses serviços de proteção na nuvem, também chamados de Serviço de Proteção Avançada da Microsoft (MAPS), aprimora a proteção padrão em tempo real, fornecendo, sem dúvida, a melhor defesa antivírus. 

> [!NOTE]
> O Microsoft Defender Antivírus de nuvem é um mecanismo para fornecer proteção atualizada para sua rede e pontos de extremidade. Como um serviço de nuvem, ele não é simplesmente proteção para arquivos armazenados na nuvem; em vez disso, o serviço de nuvem usa recursos distribuídos e aprendizado de máquina para oferecer proteção aos seus pontos de extremidade em uma taxa muito mais rápida do que as atualizações tradicionais de inteligência de segurança.

Com a proteção entregue na nuvem, as tecnologias de última geração fornecem identificação rápida de novas ameaças, às vezes até mesmo antes de um único computador ser infectado. As postagens de blog a seguir ilustram como funciona a proteção entregue na nuvem:

- [Por Microsoft Defender Antivírus é o mais implantado na empresa](https://www.microsoft.com/security/blog/2018/03/22/why-windows-defender-antivirus-is-the-most-deployed-in-the-enterprise) 
- [O monitoramento de comportamento combinado com o aprendizado de máquina despojosa uma campanha de mineração de moedas em massa](https://www.microsoft.com/security/blog/2018/03/07/behavior-monitoring-combined-with-machine-learning-spoils-a-massive-dofoil-coin-mining-campaign)
- [Como a inteligência artificial interrompeu um surto de "Emotet"](https://www.microsoft.com/security/blog/2018/02/14/how-artificial-intelligence-stopped-an-emotet-outbreak)
- [Detonando um coelhinha ruim: Microsoft Defender Antivírus e defesas de aprendizado de máquina em camadas](https://www.microsoft.com/security/blog/2017/12/11/detonating-a-bad-rabbit-windows-defender-antivirus-and-layered-machine-learning-defenses)
- [Microsoft Defender Antivírus de proteção na nuvem: defesa avançada em tempo real contra malware nunca visto antes](https://www.microsoft.com/security/blog/2017/07/18/windows-defender-antivirus-cloud-protection-service-advanced-real-time-defense-against-never-before-seen-malware) 
 
## <a name="how-to-get-cloud-delivered-protection"></a>Como obter proteção entregue na nuvem 

A proteção entregue na nuvem está habilitada por padrão. No entanto, talvez seja necessário reabilitar se ele tiver sido desabilitado como parte de políticas organizacionais anteriores. Para saber mais, confira [Ativar a proteção entregue na nuvem.](enable-cloud-protection-microsoft-defender-antivirus.md)

As organizações Windows 10 E5 também podem tirar proveito das atualizações de inteligência dinâmica de emergência, que fornecem proteção quase em tempo real contra ameaças emergentes. Quando você ativar a proteção entregue na nuvem, correções para problemas de malware podem ser entregues por meio da nuvem em minutos, em vez de aguardar a próxima atualização. [Configure Microsoft Defender Antivírus para receber automaticamente novas atualizações](manage-event-based-updates-microsoft-defender-antivirus.md#cloud-report-updates)de proteção com base em relatórios do nosso serviço de nuvem.

> [!TIP]
> Visite o site Windows Defender Testground [no](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) demo.wd.microsoft.com para confirmar se o recurso está funcionando e ver como ele funciona.

## <a name="next-steps"></a>Próximas etapas

1. [Habilitar a proteção entregue na nuvem](enable-cloud-protection-microsoft-defender-antivirus.md). Você pode habilitar a proteção entregue na nuvem com Microsoft Endpoint Manager (que agora inclui Microsoft Endpoint Configuration Manager e Microsoft Intune), Política de Grupo ou cmdlets do PowerShell.

2. [Especifique o nível de proteção entregue na nuvem](specify-cloud-protection-level-microsoft-defender-antivirus.md). Você pode especificar o nível de proteção oferecido pela nuvem usando o Microsoft Endpoint Manager ou a Política de Grupo. O nível de proteção afeta a quantidade de informações compartilhadas com a nuvem e o quão agressivamente novos arquivos são bloqueados.

3. [Configurar e validar conexões de rede para Microsoft Defender Antivírus](configure-network-connections-microsoft-defender-antivirus.md). Há certas URLs da Microsoft às que sua rede e pontos de extremidade devem ser capazes de se conectar para que a proteção entregue na nuvem funcione efetivamente. Este artigo lista as URLs que devem ser permitidas por meio de regras de filtragem de rede ou firewall e instruções para confirmar que sua rede está corretamente matriculada na proteção entregue na nuvem.

4. [Configure o recurso "bloquear à primeira vista".](configure-block-at-first-sight-microsoft-defender-antivirus.md) O recurso "bloquear à primeira vista" pode bloquear um novo malware em segundos, sem ter que esperar horas pela inteligência de segurança tradicional. Você pode habilita-lo e configurá-lo usando Microsoft Endpoint Manager ou Política de Grupo.

5. [Configure o período de tempo de bloqueio na nuvem](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md). Microsoft Defender Antivírus pode impedir a execução de arquivos suspeitos enquanto consulta nosso serviço de proteção entregue na nuvem. Você pode configurar a quantidade de tempo em que o arquivo será impedido de ser executado usando o Microsoft Endpoint Manager ou a Política de Grupo.