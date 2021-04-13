---
title: Descoberta de dispositivo perguntas frequentes
description: Encontre respostas para perguntas frequentes sobre a descoberta de dispositivos
keywords: descoberta de dispositivo, descoberta, passiva, proativa, rede, visibilidade, servidor, estação de trabalho, a integração, dispositivos não gerenciamento
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 7165d943fd39e298894531f1dabdec408144898d
ms.sourcegitcommit: 72ae1b49e7a3d3199272fcb4c39f5daec0d66f1a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51698407"
---
# <a name="device-discovery-frequently-asked-questions"></a>Descoberta de dispositivo perguntas frequentes

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

Encontre respostas para perguntas frequentes sobre a descoberta de dispositivos.

## <a name="what-is-basic-discovery-mode"></a>O que é o modo de descoberta básico?
Esse modo permite que todos os dispositivos do Microsoft Defender para Ponto de Extremidade abordem dados de rede e descubram dispositivos vizinhos. Os pontos de extremidade integrados coletam passivamente eventos na rede e extraem informações do dispositivo deles. Nenhum tráfego de rede será iniciado. Os pontos de extremidade integrados simplesmente extrairão dados de todos os tráfegos de rede que são vistos por um dispositivo conectado. Esses dados usados para listar dispositivos não utilizados em sua rede.

## <a name="can-i-disable-basic-discovery"></a>Posso desabilitar a descoberta básica?
Você tem a opção de desativar a descoberta de dispositivo por meio da [página Recursos Avançados.](advanced-features.md) No entanto, você perderá a visibilidade em dispositivos nãomanados em sua rede. 

## <a name="what-is-standard-discovery-mode"></a>O que é o modo de descoberta padrão?
 Nesse modo, os pontos de extremidade conectados ao Microsoft Defender para Ponto de Extremidade podem sondar ativamente os dispositivos observados na rede para enriquecer dados coletados (com uma quantidade insignificante de tráfego de rede). Esse modo é altamente recomendado para a criação de um inventário de dispositivo confiável e coerente. Se você optar por desabilitar esse modo e selecionar Modo de descoberta básico, provavelmente só terá visibilidade limitada dos pontos de extremidade nãomanados em sua rede.

## <a name="can-i-control-which-devices-perform-standard-discovery"></a>Posso controlar quais dispositivos executam a descoberta padrão?
 Você pode personalizar a lista de dispositivos usados para executar a descoberta padrão. Você pode habilitar a descoberta padrão em todos os dispositivos conectados que também suportam esse recurso (atualmente apenas dispositivos Windows 10) ou selecionar um subconjunto ou subconjunto de seus dispositivos especificando suas marcas de dispositivo. Nesse caso, todos os outros dispositivos serão configurados para executar somente a descoberta básica. A configuração está disponível na página configurações de descoberta de dispositivo.

## <a name="which-onboarded-devices-can-perform-discovery"></a>Quais dispositivos conectados podem realizar a descoberta?
 Dispositivos conectados em execução no Windows 10 versão 1809 ou posterior podem executar a descoberta.

## <a name="what-happens-if-my-onboarded-devices-is-connected-to-my-home-network-or-to-public-access-point"></a>O que acontece se meus dispositivos conectados estão conectados à minha rede principal ou ao ponto de acesso público?
 O mecanismo de descoberta diferencia os eventos de rede recebidos na rede corporativa e fora da rede corporativa. Ao correlacionar identificadores de rede em todos os clientes do locatário, os eventos são diferenciados entre os que foram recebidos de redes privadas e redes corporativas. Os dispositivos de rede privada não serão listados no inventário e não serão sondados ativamente.

## <a name="what-protocols-are-you-capturing-and-analyzing"></a>Quais protocolos você está capturando e analisando?
 Por padrão, todos os dispositivos conectados em execução no Windows 10 versão 1809 ou posterior estão capturando e analisando os seguintes protocolos: ARP, CDP, DHCP, DHCPv6, IP (headers), LLDP, LLMNR, mDNS, MNDP, NBNS, SSDP, TCP (headers), UDP (headers), WSD

## <a name="which-protocols-do-you-use-for-active-probing-in-standard-discovery"></a>Quais protocolos você usa para sondagem ativa na descoberta padrão?
 Quando um dispositivo é configurado para executar a descoberta padrão, os serviços expostos estão sendo sondados usando os seguintes protocolos: ARP, FTP, HTTP, ICMP, LLMNR, NBNS, RDP, SIP, SMTP, SNMP, SSH, Telnet, UPNP, WSD, SMB, NBSS, IPP, PJL

## <a name="how-can-i-exclude-targets-from-being-probed-with-standard-discovery"></a>Como posso excluir destinos de serem sondados com a descoberta padrão?
 Se houver dispositivos em sua rede que não devem ser sondados ativamente, você também pode definir uma lista de exclusões para impedir que eles sejam verificados. A configuração está disponível na página configurações de descoberta de dispositivo.

## <a name="can-i-exclude-devices-from-being-discovered"></a>Posso excluir dispositivos de serem descobertos?
 À medida que a descoberta de dispositivo usa métodos passivos para descobrir dispositivos na rede, qualquer dispositivo que se comunica com seus dispositivos conectados na rede corporativa pode ser descoberto e listado no inventário. Você só pode excluir dispositivos de sondagem ativa.

## <a name="how-frequent-is-the-active-probing"></a>Qual é a frequência da sondagem ativa?
 Os dispositivos serão sondados ativamente quando as alterações nas características do dispositivo são observadas e uma vez por semana para garantir que as informações existentes estão atualizadas.

## <a name="my-security-tool-raised-alert-on-unicastscannerps1-or-port-scanning-activity-initiated-by-it-what-should-i-do"></a>Minha ferramenta de segurança acionou alerta UnicastScanner.ps1 atividade de verificação de porta ou porta iniciada por ela, o que devo fazer?
 Os scripts de sondagem ativos são assinados pela Microsoft e são seguros. Você pode adicionar o seguinte caminho à sua lista de exclusão: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`


## <a name="what-is-the-amount-of-traffic-being-generated-by-the-standard-discovery-active-probe"></a>Qual é a quantidade de tráfego gerada pela sonda ativa de descoberta padrão?
 A sondagem ativa pode gerar até 5K de tráfego entre o dispositivo conectado e o dispositivo sondado, cada tentativa de sondagem

## <a name="why-is-there-a-discrepancy-between-can-be-onboarded-devices-in-the-device-inventory-and-the-number-of-devices-to-onboard-in-the-dashboard-tile"></a>Por que há uma discrepância entre os dispositivos "podem estar conectados" no inventário de dispositivos e o número de "dispositivos para integração" no painel?
Você pode observar diferenças entre o número de dispositivos listados em "pode ser incorporado" no inventário de dispositivos, a recomendação de segurança "onboard to Microsoft Defender for Endpoint" e o widget de painel "dispositivos para integração".

 A recomendação de segurança e o widget do painel são para dispositivos estáveis na rede; excluindo dispositivos efêmeros, dispositivos convidados e outros. A ideia é recomendar em dispositivos persistentes, que também implicam na pontuação geral de segurança da organização.

## <a name="can-i-onboard-unmanaged-devices-that-were-found"></a>Posso fazer a integração de dispositivos nãomanageados que foram encontrados?
 Sim. Os pontos de extremidade nãomanageados em sua rede apresentam vulnerabilidades e riscos à sua rede. A integração deles ao serviço pode aumentar a visibilidade de segurança neles. 


