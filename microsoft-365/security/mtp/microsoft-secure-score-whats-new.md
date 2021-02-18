---
title: Novidades no Microsoft Secure Score
description: Descreve as novas alterações que aconteceram com o Microsoft Secure Score no centro de segurança do Microsoft 365.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 520a5627d2cd280f28c4e2c3db0e565640a1eace
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289156"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Novidades no Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Para tornar o Microsoft Secure Score um representante melhor da postura de segurança, fizemos algumas alterações. Para saber mais sobre as alterações planejadas, confira [O que está chegando no Microsoft Secure Score?](microsoft-secure-score-whats-coming.md)

O Microsoft Secure Score pode ser encontrado https://security.microsoft.com/securescore no centro de segurança do Microsoft [365.](overview-security-center.md)
    
## <a name="february-2021"></a>Fevereiro de 2021

### <a name="compatibility-with-graph-api"></a>Compatibilidade com a API do Graph

As recomendações da Pontuação de Segurança da Microsoft fornecidas por meio da API do Graph terão o mesmo peso que as recomendações que você vê atualmente na central de segurança do Microsoft 365.

## <a name="january-2021"></a>Janeiro de 2021

### <a name="added-our-first-security-recommendation-for-microsoft-teams"></a>Foi adicionada nossa primeira recomendação de segurança para o Microsoft Teams

Os clientes do Microsoft Teams verão "Restringir usuários anônimos de ingressar em reuniões" como uma nova ação de melhoria no Secure Score.

## <a name="december-2020"></a>Dezembro de 2020

### <a name="added-six-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Seis ações de melhoria relacionadas a contas adicionadas ao Microsoft Defender para Ponto de Extremidade (anteriormente Microsoft Defender ATP):

- Definir 'Tamanho mínimo da senha' como '14 ou mais caracteres'
- Definir 'Impor histórico de senhas' como '24 ou mais senhas)'
- Definir 'Idade máxima da senha' como '60 ou menos dias, mas não 0'
- Definir 'Idade mínima da senha' como '1 ou mais dias''
- Desabilitar a conta de Administrador integrado
- Desabilitar a conta de convidado integrado

## <a name="november-2020"></a>Novembro de 2020

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a>Foi removida a capacidade de criar tíquetes do ServiceNow por meio do Secure Score 

A capacidade de criar tíquetes do ServiceNow por meio da Classificação de Segurança **indo para Compartilhar > ServiceNow** não está mais disponível. Agradecemos por seus comentários e suporte contínuo enquanto determinamos as próximas etapas.

### <a name="added-three-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Três ações de melhoria relacionadas a serviços adicionadas ao Microsoft Defender para Ponto de Extremidade (anteriormente Microsoft Defender ATP):

- Corrigir caminho de serviço sem aspas para serviços do Windows
- Alterar o caminho executável do serviço para um local protegido comum
- Alterar a conta de serviço para evitar senha armazenada em cache no Registro do Windows

## <a name="october-2020"></a>Outubro de 2020

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a>Remover ação de melhoria relacionada ao Microsoft Defender para Ponto de Extremidade

- Definir a verificação de conteúdo da Web de aplicativos da Windows Store do Microsoft Defender SmartScreen para avisar

## <a name="august-2020"></a>Agosto de 2020

### <a name="updated-improvement-action-for-azure-active-directory"></a>Ação de melhoria atualizada para o Azure Active Directory

- Habilitar política para bloquear autenticação herdado

## <a name="incompatibility-with-identity-secure-score"></a>Incompatibilidade com a Pontuação de Segurança de Identidade

Na versão recente do Microsoft Secure Score, um modelo de pontuação aprimorado foi lançado. Essas alterações permitem uma visão mais flexível e precisa da postura de segurança. No entanto, essas atualizações tornou o Microsoft Secure Score temporariamente incompatível com o Identity Secure Score.

No tempo, a Pontuação de Segurança de Identidade adotará o novo modelo de pontuação. Até lá, os clientes verão diferenças nas pontuações relatadas pelo Microsoft Secure Score e pela Identity Secure Score. Lamentamos qualquer inconveniente que isso cause e estamos trabalhando para garantir que essas experiências sejam mais compatíveis no futuro.

## <a name="updated-improvement-actions"></a>Ações de melhoria atualizadas

- Adicionadas ações de aperfeiçoamento do Azure Active Directory
- Adicionadas ações de melhoria de identidade do Microsoft Defender
- Suporte para o Microsoft Defender para Endpoint Threat & de segurança de Gerenciamento de [Vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
    - Todas as recomendações de segurança lançadas fornecidas pelo TVM agora estão disponíveis

## <a name="updated-interface-and-functionality"></a>Interface e funcionalidade atualizadas

* Todas as novas métricas e exibições de tendências para CISO e discussões em nível de liderança
* Novas maneiras de acompanhar e fazer o comparativo de sua pontuação
* Melhor rastreamento e compreensão para regressões de pontuação
* Filtrar, marcar, pesquisar e agrupar suas ações de melhoria
* Gerencie suas metas futuras usando projeções de pontuação e ações planejadas
* E muito mais!

## <a name="we-want-to-hear-from-you"></a>Queremos ouvir de você

Se você tiver algum problema, deixe-nos saber postando na comunidade segurança, privacidade [& conformidade.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Estamos monitorando a comunidade e forneceremos ajuda.

## <a name="related-resources"></a>Recursos relacionados

- [Avaliar sua postura de segurança](microsoft-secure-score-improvement-actions.md)
- [Acompanhar o histórico do Microsoft Secure Score e cumprir as metas](microsoft-secure-score-history-metrics-trends.md)
- [O que estar por vir.](microsoft-secure-score-whats-coming.md)
