---
title: O que há de novo na pontuação segura da Microsoft
description: Descreve quais novas alterações ocorreram na pontuação segura da Microsoft na central de segurança do Microsoft 365.
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
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 4f9f4f40b9cd88cad1676417d467d04367eaa0be
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/21/2020
ms.locfileid: "45200098"
---
# <a name="whats-new-in-microsoft-secure-score"></a>O que há de novo na pontuação segura da Microsoft

Para tornar a pontuação segura da Microsoft um melhor representante da postura de segurança, fizemos algumas alterações. Para saber mais sobre as alterações planejadas, confira [o que está acontecendo na pontuação segura da Microsoft?](microsoft-secure-score-whats-coming.md).

## <a name="june-2020"></a>Junho de 2020

### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Ação de aprimoramento removida para a proteção avançada contra ameaças do Microsoft defender

* Ativar as regras de redução da superfície de ataque

### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Foram adicionadas ações de melhoria para a proteção avançada contra ameaças do Microsoft defender

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
* Bloquear o furto de credenciais do subsistema de autoridade de segurança local do Windows (lsass.exe)
* Bloquear chamadas de API Win32 de macros do Office

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Incompatibilidade com Pontuação segura de identidade e API de gráfico

Na versão recente da Pontuação segura da Microsoft, um modelo de Pontuação aprimorado foi lançado. Essas alterações permitem uma visão mais flexível e precisa de sua postura de segurança. No entanto, essas atualizações tornaram a pontuação segura da Microsoft temporariamente incompatível com a pontuação segura de identidade e a API do Graph.

No momento, a pontuação segura de identidade e a API do Graph adotarão o novo modelo de pontuação. Até lá, os clientes verão as diferenças nas pontuações relatadas pela pontuação segura da Microsoft, Pontuação segura de identidade e API do Graph. Lamentamos as inconveniências possíveis, e estamos trabalhando para garantir que essas experiências sejam mais compatíveis no futuro.

## <a name="updated-improvement-actions"></a>Ações de aprimoramento atualizadas

- Foram adicionadas ações de melhoria do Azure Active Directory
- Foram adicionadas ações aprimoradas para proteção avançada contra ameaças do Azure
- Suporte para recomendações de segurança de [Gerenciamento de vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) do Microsoft Defender ATP &
    - Todas as recomendações de segurança lançadas fornecidas pelo TVM estão disponíveis agora

## <a name="updated-interface-and-functionality"></a>Interface e funcionalidade atualizadas

* Todos os novos modos de exibição de métricas e tendências para discussões de nível de líder e CISO
* Novas maneiras de acompanhar e avaliar a sua pontuação
* Melhor controle e compreensão para regressões de Pontuação
* Filtrar, marcar, Pesquisar e agrupar suas ações de aperfeiçoamento
* Gerenciar em direção às suas metas futuras usando pontuações de Pontuação e ações planejadas
* E muito mais!

## <a name="we-want-to-hear-from-you"></a>Queremos ouvir sua opinião

Se você tiver problemas, informe-nos por postagem na Comunidade de [segurança, privacidade & conformidade](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . Estamos monitorando a Comunidade e forneceremos ajuda.

## <a name="related-resources"></a>Recursos relacionados

- [Avaliar a postura de segurança](microsoft-secure-score-improvement-actions.md)
- [Acompanhar o histórico de Pontuação segura da Microsoft e atingir as metas](microsoft-secure-score-history-metrics-trends.md)
- [O que estar por vir.](microsoft-secure-score-whats-coming.md)
