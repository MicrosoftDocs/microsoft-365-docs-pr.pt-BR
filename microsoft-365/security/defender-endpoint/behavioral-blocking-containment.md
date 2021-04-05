---
title: Bloqueio e contenção comportamental
description: Saiba mais sobre os recursos de bloqueio comportamental e de contenção no Microsoft Defender para Ponto de Extremidade
keywords: Microsoft Defender ATP, EDR no modo de bloqueio, bloqueio de modo passivo
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 7cea65292c427cb953e2e8e3ca866c89f83128b1
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587162"
---
# <a name="behavioral-blocking-and-containment"></a>Bloqueio e contenção comportamental

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>Visão Geral

O cenário de ameaças de hoje é ultrapassado por [malware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats) sem arquivo e que vive fora da terra, ameaças altamente polimórficas que se mutam mais rápido do que as soluções tradicionais podem acompanhar e ataques operados por humanos que se adaptam ao que os adversários encontram em dispositivos comprometidos. Soluções de segurança tradicionais não são suficientes para parar esses ataques; você precisa de recursos com suporte de inteligência artificial (AI) e aprendizado de dispositivo (ML), como bloqueio comportamental e contenção, incluídos no [Defender for Endpoint](https://docs.microsoft.com/windows/security). 

Os recursos de bloqueio e contenção comportamentais podem ajudar a identificar e parar ameaças, com base em seus comportamentos e árvores de processo, mesmo quando a ameaça iniciou a execução. Os recursos de proteção de última geração, EDR e Defender para Endpoint funcionam em conjunto em recursos de bloqueio comportamental e contenção. 

:::image type="content" source="images/mdatp-next-gen-EDR-behavblockcontain.png" alt-text="Bloqueio e contenção comportamental":::

Os recursos de bloqueio comportamental e de contenção funcionam com vários componentes e recursos do Defender for Endpoint para interromper os ataques imediatamente e impedir que os ataques avancem.

- [A proteção de última geração](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) (que inclui o Microsoft Defender Antivírus) pode detectar ameaças analisando comportamentos e interromper ameaças que começaram a ser executados.

- [A detecção e resposta](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) do ponto de extremidade (EDR) recebe sinais de segurança em toda a rede, dispositivos e comportamento do kernel. À medida que as ameaças são detectadas, os alertas são criados. Vários alertas do mesmo tipo são agregados em incidentes, o que facilita que sua equipe de operações de segurança investigue e responda.

- [O Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) tem uma ampla variedade de óticas entre identidades, emails, dados e aplicativos, além dos sinais de comportamento de rede, ponto de extremidade e kernel recebidos por meio de EDR. Um componente do [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection), Defender for Endpoint processa e correlaciona esses sinais, gera alertas de detecção e conecta alertas relacionados em incidentes.

Com esses recursos, mais ameaças podem ser impedidas ou bloqueadas, mesmo que comecem a ser executados. Sempre que um comportamento suspeito é detectado, a ameaça é contida, alertas são criados e as ameaças são interrompidas em seus caminhos. 

A imagem a seguir mostra um exemplo de alerta que foi disparado por recursos de bloqueio e contenção comportamentais:

:::image type="content" source="images/blocked-behav-alert.png" alt-text="Exemplo de alerta por bloqueio comportamental e contenção":::

## <a name="components-of-behavioral-blocking-and-containment"></a>Componentes de bloqueio comportamental e contenção

- **Regras de redução [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)** de superfície de ataque orientadas por política no cliente Comportamentos de ataque comuns predefinidos são impedidos de executar, de acordo com suas regras de redução de superfície de ataque. Quando esses comportamentos tentam ser executados, eles podem ser vistos no Centro de Segurança do Microsoft Defender [https://securitycenter.windows.com](https://securitycenter.windows.com) como alertas informacionais. (As regras de redução de superfície de ataque não são habilitadas por padrão; você configura suas políticas no Centro de Segurança do Microsoft Defender.)

- **[Bloqueio comportamental do cliente](client-behavioral-blocking.md)** As ameaças nos pontos de extremidade são detectadas por meio do aprendizado de máquina e, em seguida, são bloqueadas e corrigidas automaticamente. (O bloqueio comportamental do cliente está habilitado por padrão.) 

- **[Bloqueio de loop de feedback](feedback-loop-blocking.md)** (também conhecido como proteção rápida) As detecções de ameaças são observadas por meio de inteligência comportamental. As ameaças são interrompidas e impedidas de executar em outros pontos de extremidade. (O bloqueio de loop de feedback está habilitado por padrão.) 

- **[Detecção e resposta do ponto de extremidade (EDR) no modo de bloqueio](edr-in-block-mode.md)** Artefatos mal-intencionados ou comportamentos observados por meio da proteção pós-violação são bloqueados e contidos. A EDR no modo de bloqueio funciona mesmo que o Microsoft Defender Antivírus não seja a solução antivírus principal. (A EDR no modo de bloqueio não está habilitada por padrão; você a ativa no Centro de Segurança do Microsoft Defender.) 

Espere mais na área de bloqueio comportamental e contenção, pois a Microsoft continua a melhorar recursos e recursos de proteção contra ameaças. Para ver o que está planejado e em implantação agora, visite o [roteiro do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).

## <a name="examples-of-behavioral-blocking-and-containment-in-action"></a>Exemplos de bloqueio comportamental e contenção em ação

Os recursos de bloqueio comportamental e de contenção bloquearam técnicas de invasores, como:

- Despejo de credenciais do LSASS
- Injeção entre processos
- Processo de esvaziamento
- Bypass de Controle de Conta de Usuário
- Adulteração de antivírus (como desabilitá-lo ou adicionar o malware como exclusão)
- Contacting Command and Control (C&C) para baixar cargas
- Mineração de moedas
- Modificação do registro de inicialização
- Ataques pass-the-hash
- Instalação do certificado raiz
- Tentativa de exploração para várias vulnerabilidades

A seguir estão dois exemplos reais de bloqueio comportamental e contenção em ação.

### <a name="example-1-credential-theft-attack-against-100-organizations"></a>Exemplo 1: ataque de roubo de credenciais contra 100 organizações

Conforme descrito em Em busca ativa de ameaças ilusórios: o bloqueio baseado em comportamento baseado em [AI](https://www.microsoft.com/security/blog/2019/10/08/in-hot-pursuit-of-elusive-threats-ai-driven-behavior-based-blocking-stops-attacks-in-their-tracks)interrompe ataques em suas faixas , um ataque de roubo de credenciais contra 100 organizações em todo o mundo foi interrompido por recursos de bloqueio comportamental e de contenção. As mensagens de email de phishing que continham um documento de adução foram enviadas para as organizações direcionadas. Se um destinatário abrisse o anexo, um documento remoto relacionado poderia executar o código no dispositivo do usuário e carregar malware do Lokibot, que roubava credenciais, dados roubados exfiltrados e aguardava mais instruções de um servidor de comando e controle. 

Modelos de aprendizado de dispositivo baseado em comportamento no Defender para Ponto de Extremidade foram capturados e pararam as técnicas do invasor em dois pontos da cadeia de ataque:
- A primeira camada de proteção detectou o comportamento de exploração. Os classificadores de aprendizado de dispositivo na nuvem identificaram corretamente a ameaça como e imediatamente instruiram o dispositivo cliente a bloquear o ataque.
- A segunda camada de proteção, que ajudou a parar os casos em que o ataque passou pela primeira camada, detectou o esvaziamento do processo, interrompeu esse processo e removeu os arquivos correspondentes (como o Desbot). 

Enquanto o ataque era detectado e interrompido, alertas, como um "alerta de acesso inicial", eram disparados e apareciam no Centro de Segurança do Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ):

:::image type="content" source="images/behavblockcontain-initialaccessalert.png" alt-text="Alerta de acesso inicial no Centro de Segurança do Microsoft Defender":::

Este exemplo mostra como os modelos de aprendizado de dispositivos baseados em comportamento na nuvem adicionam novas camadas de proteção contra ataques, mesmo depois de eles iniciarem a execução.

### <a name="example-2-ntlm-relay---juicy-potato-malware-variant"></a>Exemplo 2: retransmissão de NTLM - Variante de malware de batata suculenta

Conforme descrito na postagem recente do blog, bloqueio comportamental e [contenção:](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection)Transformando a ótica em proteção , em janeiro de 2020, o Defender for Endpoint detectou uma atividade de escalonamento de privilégios em um dispositivo em uma organização. Um alerta chamado "Possível escalonamento de privilégios usando retransmissão NTLM" foi disparado.

:::image type="content" source="images/NTLMalertjuicypotato.png" alt-text="Alerta NTLM para malware de batata suculenta":::

A ameaça acabou sendo malware; era uma nova variante, não vista antes de uma ferramenta de pirataria conhecida chamada Descarada, que é usada por invasores para obter a escalonamento de privilégios em um dispositivo. 

Minutos depois que o alerta foi disparado, o arquivo foi analisado e confirmado como mal-intencionado. Seu processo foi interrompido e bloqueado, conforme mostrado na imagem a seguir:

:::image type="content" source="images/Artifactblockedjuicypotato.png" alt-text="Artefato bloqueado":::

Alguns minutos depois que o artefato foi bloqueado, várias instâncias do mesmo arquivo foram bloqueadas no mesmo dispositivo, impedindo a implantação de invasores adicionais ou outros malwares no dispositivo. 

Este exemplo mostra que, com recursos de bloqueio e contenção comportamentais, as ameaças são detectadas, contidas e bloqueadas automaticamente. 

## <a name="next-steps"></a>Próximas etapas

- [Saiba mais sobre o Defender para Ponto de Extremidade](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)

- [Configurar suas regras de redução de superfície de ataque](attack-surface-reduction.md)

- [Habilitar eDR no modo de bloqueio](edr-in-block-mode.md)

- [Consulte atividade de ameaça global recente](https://www.microsoft.com/wdsi/threats)

- [Obter uma visão geral do Microsoft 365 Defender ](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)
