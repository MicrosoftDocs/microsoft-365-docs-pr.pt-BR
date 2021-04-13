---
title: Habilitar o recurso de verificação periódica limitada do Microsoft Defender Antivírus
description: A verificação periódica limitada permite que você use o Microsoft Defender Antivírus, além de outros provedores AV instalados
keywords: lps, limited, periodic, scan, scanning, compatibility, 3rd party, other av, disable
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 64b65363ff53773f73cbbdc33b05a0a1beaf7f92
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689861"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a>Usar verificação periódica limitada no Microsoft Defender Antivírus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

A verificação periódica limitada é um tipo especial de detecção e correção de ameaças que pode ser habilitado quando você instalou outro produto antivírus em um dispositivo Windows 10.

Ele só pode ser habilitado em determinadas situações. Para obter mais informações sobre a verificação periódica limitada e como o Microsoft Defender Antivírus funciona com outros produtos antivírus, consulte [Microsoft Defender Antivírus compatibility](microsoft-defender-antivirus-compatibility.md).

**A Microsoft não recomenda usar esse recurso em ambientes corporativos. Esse é um recurso destinado principalmente aos consumidores.** Esse recurso usa apenas um subconjunto limitado dos recursos do Microsoft Defender Antivírus para detectar malware e não será capaz de detectar a maioria dos malwares e softwares potencialmente indesejados. Além disso, os recursos de gerenciamento e relatório serão limitados. A Microsoft recomenda que as empresas escolham sua solução antivírus principal e a usem exclusivamente.

## <a name="how-to-enable-limited-periodic-scanning"></a>Como habilitar a verificação periódica limitada

Por padrão, o Microsoft Defender Antivírus se habilitará em um dispositivo Windows 10 se não houver outro produto antivírus instalado, ou se o outro produto estiver desaprivado, expirado ou não funcionando corretamente.

Se o Microsoft Defender Antivírus estiver habilitado, as opções usuais aparecerão para configurá-lo nesse dispositivo:

![Aplicativo de Segurança do Windows mostrando opções do Microsoft Defender AV, incluindo opções de verificação, configurações e opções de atualização](images/vtp-wdav.png)

Se outro produto antivírus estiver instalado e funcionando corretamente, o Microsoft Defender Antivírus se desabilitará. O aplicativo segurança do Windows alterará a seção Proteção contra **&** vírus para mostrar o status sobre o produto AV e fornecerá um link para as opções de configuração do produto.

Sob qualquer produto AV de terceiros, um novo link aparecerá como opções do **Microsoft Defender Antivírus.** Clicar neste link será expandido para mostrar a alternância que permite a verificação periódica limitada. Observe que a opção periódica limitada é uma alternância para habilitar ou desabilitar a verificação periódica. 

Deslizar a opção para **On** mostrará as opções padrão do Microsoft Defender AV abaixo do produto AV de terceiros. A opção de verificação periódica limitada aparecerá na parte inferior da página.

## <a name="related-articles"></a>Artigos relacionados

- [Configurar proteção comportamental, heurística e em tempo real](configure-protection-features-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)