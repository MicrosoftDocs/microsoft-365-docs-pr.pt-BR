---
title: Microsoft Secure Score
description: Descreve a pontuação segura da Microsoft na central de segurança do Microsoft 365, como melhorar a postura de segurança e quais administradores de segurança podem esperar.
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
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 7fe5be065ee45700a1f08a39c8050757c3843f7b
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682566"
---
# <a name="microsoft-secure-score"></a>Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

A pontuação segura da Microsoft é uma medida da postura de segurança de uma organização, com um número maior indicando ações mais aprimoradas. Ele pode ser encontrado no https://security.microsoft.com/securescore na [central de segurança do Microsoft 365](overview-security-center.md).

Seguindo as recomendações de Pontuação segura podem proteger sua organização contra ameaças. A partir de um painel centralizado no centro de segurança do Microsoft 365, as organizações podem monitorar e trabalhar com a segurança de suas identidades, aplicativos e dispositivos da 365 Microsoft.

A pontuação segura ajuda as organizações:  

* Relatar o estado atual da postura de segurança da organização.
* Melhorar a postura de segurança fornecendo descoberta, visibilidade, orientação e controle.  
* Compare com benchmarks e estabeleça indicadores de desempenho principais (KPIs).

As organizações obtêm acesso a visualizações robustas de métricas e tendências, integração com outros produtos da Microsoft, comparação de pontos com organizações similares e muito mais. A pontuação também pode refletir quando soluções de terceiros solucionaram as ações recomendadas.

![Home Page de Pontuação segura](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>Como funciona

Você tem pontos para as seguintes ações:

- Configurando recursos de segurança recomendados
- Executando tarefas relacionadas à segurança
- Lidando com a ação de melhoria com um aplicativo ou software de terceiros, ou uma atenuação alternativa

Algumas ações de melhoria só dão pontos quando totalmente concluídas. Alguns dão pontos parciais se eles forem concluídos para alguns dispositivos ou usuários. Se não for possível ou não quiser enactr uma das ações de aperfeiçoamento, você pode optar por aceitar o risco ou o risco restante.

Se você tiver uma licença para um dos produtos da Microsoft com suporte, verá recomendações para esses produtos. Mostramos o conjunto completo de possíveis aprimoramentos de um produto, independentemente da edição da licença, assinatura ou planejamento. Dessa forma, você pode entender as práticas recomendadas de segurança e melhorar sua pontuação. Sua postura de segurança absoluta, representada pela pontuação segura, permanece o mesmo que as licenças que sua organização possui para um produto específico. Tenha em mente que a segurança deve ser balanceada com usabilidade, e nem todas as recomendações podem funcionar para seu ambiente.

Sua pontuação é atualizada em tempo real para refletir as informações apresentadas nas páginas de ações de visualizações e melhorias. A pontuação segura também sincroniza diariamente para receber dados do sistema sobre seus pontos obtidos para cada ação.

### <a name="key-scenarios"></a>Principais cenários

- [Verificar sua pontuação atual](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [Comparar sua pontuação com organizações como a sua](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [Exibir ações de aprimoramento e decidir um plano de ação](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [Iniciar fluxos de trabalho para investigar ou implementar](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [Centro de segurança do Microsoft 365 e integração com o ServiceNow](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a>Como as ações de aperfeiçoamento são pontuadas

Cada ação de melhoria vale 10 pontos ou menos, e a maioria é classificada de forma binária. Se você implementar a ação de melhoria, como criar uma nova política ou ativar uma configuração específica, obterá 100% dos pontos. Para outras ações de melhoria, os pontos são fornecidos como uma porcentagem da configuração total.

Por exemplo, uma ação de melhoria diz que você obtém 10 pontos protegendo todos os seus usuários com autenticação multifator. Você só tem 50 de 100 total de usuários protegidos, portanto, obteria uma pontuação parcial de cinco pontos (50 protegido/100 total * 10 máximo de 5 pontos).

### <a name="products-included-in-secure-score"></a>Produtos incluídos na pontuação segura

No momento, há recomendações para o Microsoft 365 (incluindo o Exchange Online), o Azure Active Directory, o Microsoft defender para ponto de extremidade, o Microsoft defender para identidade e o Cloud app Security. As recomendações para outros produtos de segurança serão disponibilizadas em breve. As recomendações não abrangem todas as superfícies de ataque associadas a cada produto, mas são uma boa linha de base. Você também pode marcar as ações de melhoria como cobertas por terceiros ou como atenuação alternativa.

### <a name="security-defaults"></a>Padrões de segurança

A pontuação segura da Microsoft atualiza as ações de aperfeiçoamento para suportar os [padrões de segurança no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), o que facilita a proteção da organização com configurações de segurança pré-configuradas para ataques comuns.

Se você ativar os padrões de segurança, receberá pontos completos para as seguintes ações de aprimoramento:

- Garantir que todos os usuários possam concluir a autenticação multifator para acesso seguro (9 pontos)
- Exigir MFA para funções administrativas (10 pontos)
- Habilitar política para bloquear autenticação herdada (7 pontos)

>[!IMPORTANT]
>Os padrões de segurança incluem recursos de segurança que oferecem segurança semelhante às ações de aperfeiçoamento "política de risco de entrada" e "política de risco de usuário". Em vez de configurar essas políticas na parte superior dos padrões de segurança, recomendamos atualizar seus status para "resolvido por meio de atenuação alternativa".

## <a name="required-permissions"></a>Permissões obrigatórias

Para ter permissão para acessar a pontuação segura da Microsoft, você deve receber uma das seguintes funções no Azure Active Directory.

### <a name="read-and-write-roles"></a>Funções de leitura e gravação

Com acesso de leitura e gravação, você pode fazer alterações e interagir diretamente com a pontuação segura. Você também pode atribuir acesso somente leitura a outros usuários.

* Administrador global
* Administrador de segurança
* Administrador do Exchange
* Administrador do SharePoint
* Administrador de contas

### <a name="read-only-roles"></a>Funções somente leitura

Com acesso somente leitura, não é possível editar o status ou as anotações de uma ação de melhoria, editar zonas de pontuação ou editar comparações personalizadas.

* Administrador da assistência técnica
* Administrador de usuários
* Administrador de serviço
* Leitor de segurança
* Operador de segurança
* Leitor global

## <a name="risk-awareness"></a>Reconhecimento de risco

A pontuação segura da Microsoft é um resumo numérico de sua postura de segurança com base nas configurações do sistema, no comportamento do usuário e em outras medidas relacionadas à segurança. Não é uma medida absoluta da probabilidade de que seu sistema ou dados seja violado. Em vez disso, ele representa a extensão à qual você adotou os controles de segurança no seu ambiente Microsoft que podem ajudar a reduzir o risco de ser violado. Nenhum serviço online é totalmente imune às brechas de segurança e a pontuação segura não deve ser interpretada como uma garantia contra violação de segurança de qualquer forma.

## <a name="we-want-to-hear-from-you"></a>Queremos ouvir de você

Se você tiver problemas, fale conosco postando na Comunidade [segurança, privacidade & conformidade](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . Estamos monitorando a Comunidade e forneceremos ajuda.

## <a name="related-resources"></a>Recursos relacionados

- [Avaliar sua postura de segurança](microsoft-secure-score-improvement-actions.md)
- [Acompanhar o histórico de Pontuação segura da Microsoft e atingir as metas](microsoft-secure-score-history-metrics-trends.md)
- [O que estar por vir.](microsoft-secure-score-whats-coming.md)
- [Novidades](microsoft-secure-score-whats-new.md)
