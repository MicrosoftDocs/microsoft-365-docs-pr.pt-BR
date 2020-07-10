---
title: Microsoft Secure Score
description: Descreve a pontuação segura da Microsoft na central de segurança do Microsoft 365, como melhorar a postura de segurança e quais administradores de segurança podem esperar.
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
ms.openlocfilehash: 212cefebfa3b4954f30d114419f82a5862e98a4f
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094793"
---
# <a name="microsoft-secure-score"></a>Microsoft Secure Score

A pontuação segura da Microsoft é uma medida da postura de segurança de uma organização, com um número maior indicando ações mais aprimoradas. Ele pode ser encontrado no https://security.microsoft.com/securescore na [central de segurança do Microsoft 365](overview-security-center.md).

Seguindo as recomendações de Pontuação segura podem proteger sua organização contra ameaças. A partir de um painel centralizado no centro de segurança do Microsoft 365, as organizações podem monitorar e trabalhar com a segurança de suas identidades, dados, aplicativos, dispositivos e infraestrutura do Microsoft 365.

A pontuação segura ajuda as organizações:  

* Relatar o estado atual da postura de segurança da organização.
* Melhorar a postura de segurança fornecendo descoberta, visibilidade, orientação e controle.  
* Compare com benchmarks e estabeleça indicadores de desempenho principais (KPIs).

As organizações obtêm acesso a visualizações robustas de métricas e tendências, integração com outros produtos da Microsoft, comparação de pontos com organizações similares e muito mais. A pontuação também pode refletir quando soluções de terceiros solucionaram as ações recomendadas.

![Home Page de Pontuação segura](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>Como funciona

Você receberá pontos para configurar os recursos de segurança recomendados, executar tarefas relacionadas à segurança ou abordar a ação de aperfeiçoamento com um aplicativo ou software de terceiros, ou uma atenuação alternativa. Algumas ações de melhoria só dão pontos quando estão totalmente concluídas, e algumas fornecem pontos parciais se forem concluídas para alguns dispositivos ou usuários. Se você não pode ou não deseja enactr uma das ações de aperfeiçoamento, você pode optar por aceitar o risco ou o risco restante.

Mostramos o conjunto completo de possíveis aprimoramentos, independentemente da licença, para que você possa entender as práticas recomendadas de segurança e aprimorar sua pontuação. Sua postura de segurança absoluta é representada pela pontuação segura, que permanece a mesma, não importa quais licenças de produto sua organização possui. Tenha em mente que a segurança deve ser balanceada com usabilidade, e nem todas as recomendações podem funcionar para seu ambiente.

Sua pontuação é atualizada em tempo real para refletir as informações apresentadas nas páginas de ações de visualizações e melhorias. A pontuação segura também sincroniza diariamente para receber dados do sistema sobre seus pontos obtidos para cada ação.

### <a name="key-scenarios"></a>Principais cenários

- [Verificar sua pontuação atual](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [Comparar sua pontuação com organizações como a sua](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [Exibir ações de aprimoramento e decidir um plano de ação](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [Iniciar fluxos de trabalho para investigar ou implementar](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [Centro de segurança do Microsoft 365 e integração com o ServiceNow](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a>Como as ações de aperfeiçoamento são pontuadas

Cada ação de melhoria vale 10 pontos ou menos. A maioria é classificada de forma binária, se você implementar a ação de melhoria, como criar uma nova política ou ativar uma configuração específica, obterá 100% dos pontos. Para outras ações de melhoria, os pontos são fornecidos como uma porcentagem da configuração total. Por exemplo, se a ação de melhoria diz que você obtém 10 pontos protegendo todos os seus usuários com a autenticação multifator e só tem 50 de 100 total de usuários protegidos, você receberia uma pontuação parcial de 5 pontos (50 protegido/100 total * 10 pt de Pontuação parcial).

### <a name="products-included-in-secure-score"></a>Produtos incluídos na pontuação segura

No momento, há recomendações para o Microsoft 365 (incluindo o Exchange Online), o Azure AD, o Microsoft defender ATP, o Azure ATP e o Cloud app Security. As recomendações para outros produtos de segurança serão disponibilizadas em breve. As recomendações não abrangem todas as superfícies de ataque associadas a cada produto, mas são uma boa linha de base. Você também pode marcar as ações de melhoria como cobertas por terceiros ou como atenuação alternativa.

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

Com acesso somente leitura, você não pode editar o status ou as anotações de uma ação de melhoria, editar zonas de pontuação ou editar comparações personalizadas.

* Administrador de assistência técnica
* Administrador de usuários
* Administrador de serviço
* Leitor de segurança
* Operador de segurança
* Leitor global

## <a name="risk-awareness"></a>Reconhecimento de risco

A pontuação segura da Microsoft é um resumo numérico de sua postura de segurança com base nas configurações do sistema, no comportamento do usuário e em outras medidas relacionadas à segurança; Não é uma medida absoluta da probabilidade de que seu sistema ou dados seja violado. Em vez disso, ele representa a extensão à qual você adotou os controles de segurança no seu ambiente Microsoft, o que pode ajudar a reduzir o risco de ser violado. Nenhum serviço online é totalmente imune às brechas de segurança e a pontuação segura não deve ser interpretada como uma garantia contra violação de segurança de qualquer forma.

## <a name="whats-new"></a>Quais são as novidades? 

Para tornar a pontuação segura da Microsoft um melhor representante da postura de segurança, fizemos algumas alterações. Para saber mais sobre as alterações planejadas, confira [o que está acontecendo na pontuação segura da Microsoft?](microsoft-secure-score-whats-coming.md).

### <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Incompatibilidade com Pontuação segura de identidade e API de gráfico

Na versão recente da Pontuação segura da Microsoft, um modelo de Pontuação aprimorado foi lançado. Essas alterações permitem uma visão mais flexível e precisa de sua postura de segurança. No entanto, essas atualizações tornaram a pontuação segura da Microsoft temporariamente incompatível com a pontuação segura de identidade e a API do Graph.

No momento, a pontuação segura de identidade e a API do Graph adotarão o novo modelo de pontuação. Até lá, os clientes verão as diferenças nas pontuações relatadas pela pontuação segura da Microsoft, Pontuação segura de identidade e API do Graph. Lamentamos as inconveniências possíveis, e estamos trabalhando para garantir que essas experiências sejam mais compatíveis no futuro.

### <a name="updated-improvement-actions"></a>Ações de aprimoramento atualizadas

- Foram adicionadas ações de melhoria do Azure Active Directory
- Foram adicionadas ações aprimoradas para proteção avançada contra ameaças do Azure
- Suporte para recomendações de segurança de [Gerenciamento de vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) do Microsoft Defender ATP &
    - Todas as recomendações de segurança lançadas fornecidas pelo TVM estão disponíveis agora

### <a name="updated-interface-and-functionality"></a>Interface e funcionalidade atualizadas

* Todos os novos modos de exibição de métricas e tendências para discussões de nível de líder e CISO
* Novas maneiras de acompanhar e avaliar a sua pontuação
* Melhor controle e compreensão para regressões de Pontuação
* Filtrar, marcar, Pesquisar e agrupar suas ações de aperfeiçoamento
* Gerenciar em direção às suas metas futuras usando pontuações de Pontuação e ações planejadas
* E muito mais!

### <a name="june-2020"></a>Junho de 2020

#### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Ação de aprimoramento removida para a proteção avançada contra ameaças do Microsoft defender

* Ativar as regras de redução da superfície de ataque

#### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Foram adicionadas ações de melhoria para a proteção avançada contra ameaças do Microsoft defender

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

## <a name="we-want-to-hear-from-you"></a>Queremos ouvir sua opinião

Se você tiver problemas, informe-nos por postagem na Comunidade de [segurança, privacidade & conformidade](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . Estamos monitorando a Comunidade e forneceremos ajuda.

## <a name="related-resources"></a>Recursos relacionados

- [Obter visibilidade da postura de segurança](microsoft-secure-score-improvement-actions.md)
- [Acompanhar o histórico de Pontuação segura da Microsoft e atingir as metas](microsoft-secure-score-history-metrics-trends.md)
- [O que estar por vir.](microsoft-secure-score-whats-coming.md)
