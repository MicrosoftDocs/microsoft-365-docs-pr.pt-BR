---
title: Microsoft Secure Score
description: Descreve a Pontuação Segura da Microsoft no centro de segurança do Microsoft 365, como melhorar sua postura de segurança e o que os administradores de segurança podem esperar.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center, improvement actions
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
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
ms.openlocfilehash: 98f335a38b2e4f581d4b08def39353e53e1bafd4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053486"
---
# <a name="microsoft-secure-score"></a>Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

O Microsoft Secure Score é uma medição da postura de segurança de uma organização, com um número maior indicando mais ações de melhoria adotadas. Ele pode ser encontrado no centro de segurança do https://security.microsoft.com/securescore [Microsoft 365.](overview-security-center.md)

Seguir as recomendações do Secure Score pode proteger sua organização contra ameaças. Em um painel centralizado no centro de segurança do Microsoft 365, as organizações podem monitorar e trabalhar na segurança de suas identidades, aplicativos e dispositivos do Microsoft 365.

O Secure Core ajuda as organizações a:  

* Relatar o estado atual da situação de segurança da organização.
* Melhorar sua situação de segurança fornecendo capacidade de descoberta, visibilidade, orientação e controle.  
* Comparar com os benchmarks e estabelecer KPIs (indicadores chave de desempenho).

As organizações têm acesso a visualizações robustas de métricas e tendências, integração com outros produtos da Microsoft, comparação de pontuação com organizações semelhantes e muito mais. A pontuação também pode refletir quando soluções de terceiros abordaram ações recomendadas.

![Homepage de Pontuação Segura](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>Como funciona

Você recebe pontos para as seguintes ações:

- Configurando recursos de segurança recomendados
- Fazendo tarefas relacionadas à segurança
- Endereçamento da ação de aperfeiçoamento com um aplicativo ou software de terceiros ou uma mitigação alternativa

Algumas ações de melhoria só dão pontos quando concluídas totalmente. Alguns dão pontos parciais se eles são concluídos para alguns dispositivos ou usuários. Se você não puder ou não quiser aprovar uma das ações de melhoria, poderá optar por aceitar o risco ou o risco restante.

Se você tiver uma licença para um dos produtos da Microsoft com suporte, verá recomendações para esses produtos. Mostramos o conjunto completo de possíveis melhorias para um produto, independentemente da edição de licença, assinatura ou plano. Dessa forma, você pode entender as práticas recomendadas de segurança e melhorar sua pontuação. Sua postura de segurança absoluta, representada pela Pontuação Segura, permanece a mesma, independentemente das licenças que sua organização possui para um produto específico. Tenha em mente que a segurança deve ser equilibrada com a usabilidade e nem todas as recomendações podem funcionar para o seu ambiente.

Sua pontuação é atualizada em tempo real para refletir as informações apresentadas nas páginas de visualizações e ações de aperfeiçoamento. A Pontuação Segura também sincroniza diariamente para receber dados do sistema sobre seus pontos alcançados para cada ação.

### <a name="key-scenarios"></a>Cenários principais

- [Verificar sua pontuação atual](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [Comparar sua pontuação com organizações como a sua](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [Exibir ações de melhoria e decidir um plano de ação](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [Iniciar fluxos de trabalho para investigar ou implementar](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a>Como as ações de melhoria são pontuadas

Cada ação de melhoria vale 10 pontos ou menos e a maioria é pontuada de forma binária. Se você implementar a ação de melhoria, como criar uma nova política ou ativar uma configuração específica, você obterá 100% dos pontos. Para outras ações de melhoria, os pontos são dados como um percentual da configuração total.

Por exemplo, uma ação de melhoria afirma que você tem 10 pontos protegendo todos os usuários com autenticação multifatória. Você só tem 50 dos 100 usuários totais protegidos, para obter uma pontuação parcial de 5 pontos (50 protegidos / 100 total * 10 pts máximos = 5 pts).

### <a name="products-included-in-secure-score"></a>Produtos incluídos na Pontuação Segura

Atualmente, há recomendações para os seguintes produtos:

- Microsoft 365 (incluindo o Exchange Online)
- Azure Active Directory
- Microsoft Defender para Ponto de Extremidade
- Microsoft Defender para Identidade?
- Segurança no Aplicativo na Nuvem
- Microsoft Teams

As recomendações para outros produtos de segurança estão chegando em breve. As recomendações não abrangem todas as superfícies de ataque associadas a cada produto, mas são uma boa linha de base. Você também pode marcar as ações de melhoria como cobertas por terceiros ou mitigação alternativa.

### <a name="security-defaults"></a>Padrões de segurança

O Microsoft Secure Score atualizou as ações de melhoria para dar suporte aos padrões de segurança no [Azure Active Directory](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), o que facilita a proteção da sua organização com configurações de segurança pré-configuradas para ataques comuns.

Se você ativar os padrões de segurança, você receberá pontos completos pelas seguintes ações de melhoria:

- Certifique-se de que todos os usuários possam concluir a autenticação multifa factor para acesso seguro (9 pontos)
- Exigir MFA para funções administrativas (10 pontos)
- Habilitar a política para bloquear a autenticação herdado (7 pontos)

>[!IMPORTANT]
>Os padrões de segurança incluem recursos de segurança que fornecem segurança semelhante às ações de melhoria "política de risco de entrar" e "política de risco do usuário". Em vez de configurar essas políticas em cima dos padrões de segurança, recomendamos atualizar seus status para "Resolvido por meio de mitigação alternativa".

## <a name="required-permissions"></a>Permissões obrigatórias

Para ter permissão para acessar a Pontuação Segura da Microsoft, você deve ter uma das seguintes funções no Azure Active Directory.

### <a name="read-and-write-roles"></a>Funções de leitura e gravação

Com o acesso de leitura e gravação, você pode fazer alterações e interagir diretamente com a Pontuação Segura. Você também pode atribuir acesso somente leitura a outros usuários.

* Administrador global
* Administrador de segurança
* Administrador do Exchange
* Administrador do SharePoint
* Administrador de contas

### <a name="read-only-roles"></a>Funções somente leitura

Com o acesso somente leitura, você não é capaz de editar status ou anotações para uma ação de melhoria, editar zonas de pontuação ou editar comparações personalizadas.

* Administrador da assistência técnica
* Administrador de usuários
* Administrador de serviço
* Leitor de segurança
* Operador de segurança
* Leitor global

## <a name="risk-awareness"></a>Conscientização de riscos

A Pontuação Segura da Microsoft é um resumo numérico da postura de segurança com base nas configurações do sistema, no comportamento do usuário e em outras medidas relacionadas à segurança. Não é uma medida absoluta de como o sistema ou os dados serão violados. Em vez disso, ele representa a extensão em que você adotou controles de segurança em seu ambiente da Microsoft que podem ajudar a evitar o risco de violação. Nenhum serviço online é imune a violações de segurança e a pontuação segura não deve ser interpretada como uma garantia contra violações de segurança de qualquer maneira.

## <a name="we-want-to-hear-from-you"></a>Queremos ouvir de você

Se você tiver algum problema, nos avise postando na comunidade [Segurança, Privacidade & Conformidade.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Estamos monitorando a comunidade e forneceremos ajuda.

## <a name="related-resources"></a>Recursos relacionados

- [Avaliar sua postura de segurança](microsoft-secure-score-improvement-actions.md)
- [Rastrear seu histórico de Pontuação Segura da Microsoft e cumprir metas](microsoft-secure-score-history-metrics-trends.md)
- [O que estar por vir.](microsoft-secure-score-whats-coming.md)
- [Novidades](microsoft-secure-score-whats-new.md)