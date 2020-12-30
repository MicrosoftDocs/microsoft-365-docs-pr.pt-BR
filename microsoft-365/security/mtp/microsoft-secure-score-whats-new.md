---
title: O que há de novo na pontuação segura da Microsoft
description: Descreve quais novas alterações ocorreram na pontuação segura da Microsoft na central de segurança do Microsoft 365.
keywords: Pontuação segura da Microsoft, Pontuação segura, Pontuação segura do Office 365, pontuação de segurança da Microsoft, centro de segurança da Microsoft 365
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
ms.openlocfilehash: 61ac8c627dd701ac354a5d60d4774a6443b4d41e
ms.sourcegitcommit: a8f3c633714e934f9ad026c3bc72157ed535dcfc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/29/2020
ms.locfileid: "49737982"
---
# <a name="whats-new-in-microsoft-secure-score"></a>O que há de novo na pontuação segura da Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Para tornar a pontuação segura da Microsoft um melhor representante da postura de segurança, fizemos algumas alterações. Para saber mais sobre as alterações planejadas, confira [o que está acontecendo na pontuação segura da Microsoft?](microsoft-secure-score-whats-coming.md)

A pontuação segura da Microsoft pode ser encontrada em https://security.microsoft.com/securescore na [central de segurança do Microsoft 365](overview-security-center.md).

## <a name="december-2020"></a>Dezembro de 2020

### <a name="added-six-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Foram adicionadas seis ações de melhoria relacionadas a contas para o Microsoft defender para ponto de extremidade (anteriormente Microsoft defender ATP):

- Defina ' comprimento mínimo da senha ' para ' 14 ou mais caracteres '
- Defina ' Aplicar histórico de senhas ' como ' 24 ou mais senha (s) '
- Defina "duração máxima da senha" como "60" ou menos dias, mas não 0 "
- Defina "duração mínima da senha" como "1 ou mais dia (s)"
- Desabilitar a conta de administrador interna
- Desabilitar a conta de convidado interna

## <a name="november-2020"></a>Novembro de 2020

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a>Foi removida a capacidade de criar tíquetes do ServiceNow por meio de Pontuação segura 

A capacidade de criar ingressos do ServiceNow por meio de Pontuação segura, indo para **compartilhar > o ServiceNow** não está mais disponível. Obrigado por seus comentários e suporte contínuo enquanto determinamos as próximas etapas.

### <a name="added-three-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Foram adicionadas três ações de melhoria relacionadas aos serviços para o Microsoft defender para ponto de extremidade (anteriormente Microsoft defender ATP):

- Corrigir o caminho de serviço sem cotação para os serviços do Windows
- Alterar o caminho do executável do serviço para um local protegido comum
- Alterar a conta de serviço para evitar a senha em cache no registro do Windows

## <a name="october-2020"></a>Outubro de 2020

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a>Remover ação de melhoria relacionada ao Microsoft defender para ponto de extremidade

- Definir a verificação de conteúdo da Web do aplicativo Windows Store SmartScreen do Microsoft defender

## <a name="august-2020"></a>Agosto de 2020

### <a name="updated-improvement-action-for-azure-active-directory"></a>Ação de aprimoramento atualizada para o Azure Active Directory

- Habilitar política para bloquear autenticação herdada

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Incompatibilidade com Pontuação segura de identidade e API de gráfico

Na versão recente da Pontuação segura da Microsoft, um modelo de Pontuação aprimorado foi lançado. Essas alterações permitem uma visão mais flexível e precisa de sua postura de segurança. No entanto, essas atualizações tornaram a pontuação segura da Microsoft temporariamente incompatível com a pontuação segura de identidade e a API do Graph.

No momento, a pontuação segura de identidade e a API do Graph adotarão o novo modelo de pontuação. Até lá, os clientes verão as diferenças nas pontuações relatadas pela pontuação segura da Microsoft, Pontuação segura de identidade e API do Graph. Lamentamos as inconveniências possíveis, e estamos trabalhando para garantir que essas experiências sejam mais compatíveis no futuro.

## <a name="updated-improvement-actions"></a>Ações de aprimoramento atualizadas

- Foram adicionadas ações de melhoria do Azure Active Directory
- Foram adicionadas ações de melhoria de identidade para o Microsoft defender
- Suporte para recomendações de segurança de [Gerenciamento de vulnerabilidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) do Microsoft defender for Endpoint &
    - Todas as recomendações de segurança lançadas fornecidas pelo TVM estão disponíveis agora

## <a name="updated-interface-and-functionality"></a>Interface e funcionalidade atualizadas

* Todos os novos modos de exibição de métricas e tendências para discussões de nível de líder e CISO
* Novas maneiras de acompanhar e avaliar a sua pontuação
* Melhor controle e compreensão para regressões de Pontuação
* Filtrar, marcar, Pesquisar e agrupar suas ações de aperfeiçoamento
* Gerenciar em direção às suas metas futuras usando pontuações de Pontuação e ações planejadas
* E muito mais!

## <a name="we-want-to-hear-from-you"></a>Queremos ouvir de você

Se você tiver problemas, fale conosco postando na Comunidade [segurança, privacidade & conformidade](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . Estamos monitorando a Comunidade e forneceremos ajuda.

## <a name="related-resources"></a>Recursos relacionados

- [Avaliar sua postura de segurança](microsoft-secure-score-improvement-actions.md)
- [Acompanhar o histórico de Pontuação segura da Microsoft e atingir as metas](microsoft-secure-score-history-metrics-trends.md)
- [O que estar por vir.](microsoft-secure-score-whats-coming.md)
