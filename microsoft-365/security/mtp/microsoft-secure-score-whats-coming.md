---
title: O que está acontecendo na pontuação segura da Microsoft?
description: Descreve a pontuação segura da Microsoft na central de segurança do Microsoft 365, como os detalhes são calculados e quais administradores de segurança podem esperar.
keywords: segurança, malware, Microsoft 365, M365, Pontuação segura, central de segurança, ações de melhoria
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f9bca47c6a47468d0a5a37b77e4f587745bf619d
ms.sourcegitcommit: c696852da06d057dba4f5147bbf46521910de3ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44545924"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>O que está acontecendo na pontuação segura da Microsoft?

Para tornar a [Pontuação segura da Microsoft](microsoft-secure-score-new.md) um melhor representante da postura de segurança e melhorar a usabilidade, estamos fazendo algumas alterações em um futuro próximo. Sua pontuação e a pontuação máxima possível mudarão. No entanto, isso não implica uma alteração na postura de segurança.

Para saber mais sobre as alterações recentes, confira [o que há de novo na pontuação segura da Microsoft?](microsoft-secure-score-new.md#whats-new)

## <a name="june-2020"></a>Junho de 2020

### <a name="remove-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Remover ação de melhoria para a proteção avançada contra ameaças do Microsoft defender

* Ativar as regras de redução da superfície de ataque

### <a name="add-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Adicionar ações de melhoria para a proteção avançada contra ameaças do Microsoft defender

* Bloquear o Adobe Reader de criar processos filhos
* Usar proteção avançada contra ransomware
* Bloquear todos os aplicativos do Office para criar processos filhos
* Impedir que aplicativos do Office criem conteúdo executável
* Bloquear JavaScript ou VBScript de iniciar conteúdo executável baixado
* Bloquear a execução de scripts potencialmente ofuscados
* Bloquear conteúdo executável de cliente de email e webmail
* Bloquear o aplicativo de comunicação do Office para criar processos filhos
* Bloquear processos não confiáveis e não assinados executados no USB
* Bloquear persistência por meio de assinatura de evento WMI
* Bloquear aplicativos do Office de injetar código em outros processos
* Bloquear a execução de arquivos executáveis, a menos que eles atendam a um critério de lista de predominância, idade ou confiável
* Bloquear criações de processo provenientes de comandos do PSExec e WMI
* Bloquear a roubo de credenciais do subsistema de autoridade de segurança local do Windows (Lsass. exe)
* Bloquear chamadas de API Win32 de macros do Office
