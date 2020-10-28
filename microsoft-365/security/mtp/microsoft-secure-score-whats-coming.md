---
title: O que está chegando à pontuação segura da Microsoft
description: Descreve quais novas alterações estão chegando à pontuação segura da Microsoft na central de segurança do Microsoft 365.
keywords: Pontuação segura da Microsoft, Pontuação segura, Pontuação segura do Office 365, pontuação de segurança da Microsoft, centro de segurança da Microsoft 365, ações de melhoria
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
ms.openlocfilehash: 82ec67cae86525c055b2232667cccb603830d15f
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779243"
---
# <a name="whats-coming-to-microsoft-secure-score"></a>O que está chegando à pontuação segura da Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Estamos fazendo algumas alterações em um futuro próximo para tornar a [Pontuação segura da Microsoft](microsoft-secure-score.md) um representante melhor da sua postura de segurança e melhorar a usabilidade. Sua pontuação e a pontuação máxima possível podem ser alteradas.

## <a name="proposed-changes"></a>Alterações propostas

### <a name="november-2020"></a>Novembro de 2020

Removendo a capacidade de criar tíquetes do ServiceNow por meio de Pontuação segura, acessando **> ServiceNow** .

- O período de visualização do conector do ServiceNow está terminando. Esse recurso não estará mais disponível até o final de 2020. Obrigado por seus comentários e suporte contínuo enquanto determinamos as próximas etapas.

Adicionando 18 ações aprimoradas relacionadas ao Microsoft defender para ponto de extremidade (anteriormente Microsoft defender ATP):

Recomendações relacionadas à redução da superfície de ataque (ASR):
- Bloquear conteúdo executável de cliente de email e webmail
- Bloquear todos os aplicativos do Office para criar processos filhos
- Impedir que aplicativos do Office criem conteúdo executável
- Bloquear aplicativos do Office de injetar código em outros processos
- Bloquear JavaScript ou VBScript de iniciar conteúdo executável baixado
- Bloquear a execução de scripts potencialmente ofuscados
- Bloquear chamadas de API Win32 de macros do Office
- Bloquear a execução de arquivos executáveis, a menos que eles atendam a um critério de lista de predominância, idade ou confiável
- Usar proteção avançada contra ransomware
- Bloquear o furto de credenciais do subsistema de autoridade de segurança local do Windows (lsass.exe)
- Bloquear criações de processo provenientes de comandos do PSExec e WMI
- Bloquear processos não confiáveis e não assinados executados no USB
- Bloquear o aplicativo de comunicação do Office para criar processos filhos
- Bloquear o Adobe Reader de criar processos filhos
- Bloquear persistência por meio de assinatura de evento WMI

Recomendações relacionadas a serviços:
- Corrigir o caminho de serviço sem cotação para os serviços do Windows
- Alterar o caminho do executável do serviço para um local protegido comum
- Alterar a conta de serviço para evitar a senha em cache no registro do Windows

## <a name="related-resources"></a>Recursos relacionados

- [Visão geral da Pontuação segura da Microsoft](microsoft-secure-score.md)
- [Avaliar sua postura de segurança](microsoft-secure-score-improvement-actions.md)
- [Acompanhar o histórico de Pontuação segura da Microsoft e atingir as metas](microsoft-secure-score-history-metrics-trends.md)
- [Novidades](microsoft-secure-score-whats-new.md)
