---
title: Novidades na Pontuação Segura da Microsoft
description: Descreve quais novas alterações aconteceram com a Pontuação Segura da Microsoft no centro de Microsoft 365 segurança.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.openlocfilehash: 2f02de4b738d9d61ef9f98cd03d15bd91709339e
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314423"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Novidades na Pontuação Segura da Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Para tornar a Pontuação Segura da Microsoft um representante melhor da sua postura de segurança, fizemos algumas alterações. Para saber mais sobre as alterações planejadas, consulte [O que está por vir na Pontuação Segura da Microsoft?](microsoft-secure-score-whats-coming.md)

A Pontuação Segura da Microsoft pode ser https://security.microsoft.com/securescore encontrada no centro de Microsoft 365 [segurança.](overview-security-center.md)

## <a name="june-2021"></a>Junho de 2021

### <a name="remove-improvement-action-related-to-microsoft-cloud-app-security"></a>Remover a ação de melhoria relacionada ao Microsoft Cloud App Security

- Use Cloud App Security para detectar comportamentos anômalos.

## <a name="february-2021"></a>Fevereiro de 2021

### <a name="compatibility-with-graph-api"></a>Compatibilidade com Graph API

As recomendações de Pontuação Segura da Microsoft entregues por meio da API Graph serão ponderadas da mesma forma que as recomendações que você vê no Microsoft 365 de segurança.

## <a name="january-2021"></a>Janeiro de 2021

### <a name="added-our-first-security-recommendation-for-microsoft-teams"></a>Adicionada nossa primeira recomendação de segurança para Microsoft Teams

Microsoft Teams os clientes verão "Restringir usuários anônimos de ingressar em reuniões" como uma nova ação de melhoria na Pontuação Segura.

## <a name="december-2020"></a>Dezembro de 2020

### <a name="added-six-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint"></a>Foram adicionadas seis ações de melhoria relacionadas a contas para o Microsoft Defender para o Ponto de Extremidade:

- Definir 'Tamanho mínimo da senha' como '14 ou mais caracteres'
- Definir 'Impor histórico de senhas' como '24 ou mais senhas)'
- Definir 'Idade máxima da senha' como '60 ou menos dias, mas não 0'
- Definir 'Idade mínima da senha' como '1 ou mais dias''
- Desabilitar a conta de Administrador integrado
- Desabilitar a conta de convidado criada

## <a name="november-2020"></a>Novembro de 2020

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a>Removida a capacidade de criar tíquetes serviceNow por meio da Pontuação Segura 

A capacidade de criar tíquetes serviceNow por meio da Pontuação Segura indo **para o Share > ServiceNow** não está mais disponível. Obrigado por seus comentários e suporte contínuo enquanto determinamos as próximas etapas.

### <a name="added-three-services-related-improvement-actions-for-microsoft-defender-for-endpoint"></a>Adicionadas três ações de melhoria relacionadas a serviços para o Microsoft Defender para Ponto de Extremidade:

- Corrigir o caminho de serviço não Windows serviços
- Alterar o caminho executável do serviço para um local protegido comum
- Alterar a conta de serviço para evitar senha armazenada em cache no Registro do Windows

## <a name="october-2020"></a>Outubro de 2020

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a>Remover a ação de melhoria relacionada ao Microsoft Defender para Ponto de Extremidade

- Definir Microsoft Defender SmartScreen Windows verificação de conteúdo da Web do aplicativo da Loja para avisar

## <a name="august-2020"></a>Agosto de 2020

### <a name="updated-improvement-action-for-azure-active-directory"></a>Ação de melhoria atualizada para Azure Active Directory

- Habilitar a política para bloquear a autenticação herdado

## <a name="incompatibility-with-identity-secure-score"></a>Incompatibilidade com a Pontuação Segura de Identidade

Na versão recente do Microsoft Secure Score, um modelo de pontuação aprimorado foi lançado. Essas alterações permitem uma visão mais flexível e precisa de sua postura de segurança. No entanto, essas atualizações fizeram a Pontuação Segura da Microsoft temporariamente incompatível com a Pontuação Segura de Identidade.

Com o tempo, a Pontuação Segura de Identidade adotará o novo modelo de pontuação. Até lá, os clientes verão diferenças nas pontuações relatadas pela Pontuação Segura da Microsoft e na Pontuação de Segurança de Identidade. Pedimos desculpas por qualquer inconveniente que isso causa e estamos trabalhando para garantir que essas experiências sejam mais compatíveis no futuro.

## <a name="updated-improvement-actions"></a>Ações de melhoria atualizadas

- Adicionadas Azure Active Directory de melhoria
- Adicionadas ações de melhoria de identidade do Microsoft Defender
- Suporte para o Microsoft Defender para Ameaças [de Ponto de Extremidade & recomendações](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) de segurança do Gerenciamento de Vulnerabilidades
    - Todas as recomendações de segurança lançadas fornecidas pela TVM agora estão disponíveis

## <a name="updated-interface-and-functionality"></a>Interface e funcionalidade atualizadas

* Todas as novas métricas e exibições de tendências para discussões de nível de líder e CISO
* Novas maneiras de rastrear e fazer um benchmark de sua pontuação
* Melhor controle e compreensão para regressões de pontuação
* Filtrar, marcar, pesquisar e agrupar suas ações de melhoria
* Gerenciar para suas metas futuras usando projeções de pontuação e ações planejadas
* E mais!

## <a name="we-want-to-hear-from-you"></a>Queremos ouvir de você

Se você tiver algum problema, nos avise postando na comunidade [Segurança, Privacidade & Conformidade.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Estamos monitorando a comunidade e forneceremos ajuda.

## <a name="related-resources"></a>Recursos relacionados

- [Avaliar postura de segurança](microsoft-secure-score-improvement-actions.md)
- [Rastrear seu histórico de Pontuação Segura da Microsoft e cumprir metas](microsoft-secure-score-history-metrics-trends.md)
- [O que estar por vir.](microsoft-secure-score-whats-coming.md)
