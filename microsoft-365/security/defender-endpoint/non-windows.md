---
title: Microsoft Defender para Ponto de Extremidade para plataformas que não são Windows
description: Saiba mais sobre os recursos do Microsoft Defender for Endpoint para plataformas Windows não Windows
keywords: não windows, mac, macos, linux, android
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4793f3c84ddda0db7f4d67ac96cb31a6e2108c57
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53326994"
---
# <a name="microsoft-defender-for-endpoint-for-non-windows-platforms"></a>Microsoft Defender para Ponto de Extremidade para plataformas que não são Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

A Microsoft está em uma jornada para estender seus principais recursos de segurança do ponto de extremidade do setor além Windows e Windows Server para macOS, Linux, Android e iOS.

As organizações enfrentam ameaças em várias plataformas e dispositivos. Nossas equipes se comprometeram a criar soluções de segurança não apenas para a *Microsoft,* mas também para permitir que nossos clientes protejam e protejam seus ambientes heterogêneos.  Estamos escutando os comentários dos clientes e fazendo parcerias com nossos clientes para criar soluções que atendem às suas necessidades.

Com o Microsoft Defender para Ponto de Extremidade, os clientes se beneficiam de uma visão unificada de todas as ameaças e alertas no Central de Segurança do Microsoft Defender, em plataformas Windows e não Windows, permitindo que eles recebam uma visão completa do que está acontecendo em seu ambiente, o que os capacita a avaliar e responder mais rapidamente a ameaças.

## <a name="microsoft-defender-for-endpoint-on-macos"></a>Microsoft Defender para Ponto de Extremidade no macOS 

O Microsoft Defender para Ponto de Extremidade no macOS oferece recursos antivírus, detecção e resposta de ponto de extremidade (EDR) e Gerenciamento de Vulnerabilidades para as três versões mais recentes lançadas do macOS. Os clientes podem implantar e gerenciar a solução por meio Microsoft Endpoint Manager e Jamf. Assim como com Microsoft Office aplicativos no macOS, o Microsoft Auto Update é usado para gerenciar o Microsoft Defender para Endpoint em atualizações do Mac. Para obter informações sobre os principais recursos e benefícios, leia nossos [comunicados](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/macOS).

Para obter mais detalhes sobre como começar, visite o Defender for Endpoint na documentação do [macOS](microsoft-defender-endpoint-mac.md).

>[!NOTE]
>No momento, os seguintes recursos não são suportados nos pontos de extremidade do macOS:
>- Prevenção contra a perda de dados
>- Resposta ao vivo
>- SIEM


## <a name="microsoft-defender-for-endpoint-on-linux"></a>Microsoft Defender para Ponto de Extremidade para Linux

O Microsoft Defender para Ponto de Extremidade no Linux oferece recursos preventivos (AV), detecção e resposta de ponto de extremidade (EDR) e Gerenciamento de Vulnerabilidades para servidores Linux. Isso inclui uma experiência de linha de comando completa para configurar e gerenciar o agente, iniciar verificações e gerenciar ameaças. Suportamos versões recentes das seis distribuições mais comuns do Linux Server: RHEL 7.2+, CentOS Linux 7.2+, Ubuntu 16 LTS ou LTS superior, SLES 12+, Debian 9+, e Oracle Linux 7.2. O Microsoft Defender para Ponto de Extremidade no Linux pode ser implantado e configurado usando o Puppet, Ansible ou usando a ferramenta de gerenciamento de configuração do Linux existente. Para obter informações sobre os principais recursos e benefícios, leia nossos [comunicados](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Linux).

Para obter mais detalhes sobre como começar, visite o Microsoft Defender for Endpoint na [documentação](microsoft-defender-endpoint-linux.md)do Linux.

>[!NOTE]
>No momento, os seguintes recursos não são suportados em pontos de extremidade do Linux:
>- Prevenção contra a perda de dados
>- Resposta ao vivo
>- SIEM



## <a name="microsoft-defender-for-endpoint-on-android"></a>Microsoft Defender para Ponto de Extremidade para Android

O Microsoft Defender para Ponto de Extremidade no Android é nossa solução de defesa contra ameaças móveis para dispositivos que executam o Android 6.0 e superior. Os modos Android Enterprise (Perfil de Trabalho) e Administrador de Dispositivos são suportados. No Android, oferecemos proteção da Web, que inclui anti-phishing, bloqueio de conexões não seguras e configuração de indicadores personalizados. A solução verifica se há malware e aplicativos potencialmente indesejados (PUA) e oferece recursos adicionais de prevenção de violações por meio da integração com o Microsoft Endpoint Manager e o Acesso Condicional. Para obter informações sobre os principais recursos e benefícios, leia nossos [comunicados](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Android).

Para obter mais detalhes sobre como começar, visite o Microsoft Defender for Endpoint na documentação [do](microsoft-defender-endpoint-android.md)Android .

## <a name="microsoft-defender-for-endpoint-on-ios"></a>Microsoft Defender para Ponto de Extremidade para iOS

O Microsoft Defender para Ponto de Extremidade no iOS é nossa solução de defesa contra ameaças móveis para dispositivos que executam o iOS 11.0 ou superior. Há suporte para dispositivos supervisionados e não supervisionados. No iOS, oferecemos proteção da Web que inclui anti-phishing, bloqueio de conexões não seguras e definição de indicadores personalizados. Para obter mais informações sobre os principais recursos e benefícios, leia nossos [comunicados](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/bg-p/MicrosoftDefenderATPBlog/label-name/iOS). 

Para obter mais detalhes sobre como começar, visite o Microsoft Defender for Endpoint na documentação do [iOS.](microsoft-defender-endpoint-ios.md)

## <a name="licensing-requirements"></a>Requisitos de licenciamento 

Usuários licenciados qualificados podem usar o Microsoft Defender para Ponto de Extremidade em até cinco dispositivos simultâneos. O Microsoft Defender para Ponto de Extremidade também está disponível para compra de um Provedor de Soluções na Nuvem (CSP).

Os clientes podem obter o Microsoft Defender para Ponto de Extremidade no macOS por meio de uma licença autônoma do Microsoft Defender para Ponto de Extremidade, como parte do Microsoft 365 A5/E5 ou Microsoft 365 Segurança.

Os recursos anunciados recentemente do Microsoft Defender para Ponto de Extremidade no Android e iOS estão incluídos nas ofertas acima mencionadas como parte dos cinco dispositivos qualificados para usuários licenciados qualificados.

O Defender para Ponto de Extremidade no Linux está disponível por meio da SKU do Defender for Endpoint Server que está disponível para clientes comerciais e de educação.

Entre em contato com sua equipe de conta ou CSP para obter preços e requisitos de qualificação adicionais.
