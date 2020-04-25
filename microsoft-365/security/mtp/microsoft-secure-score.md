---
title: Microsoft Secure Score
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
ms.openlocfilehash: 56c3187999d34ac6d84c1b3857053f82bb40b2a9
ms.sourcegitcommit: 1e9ce51efa583c33625299d17e37f58048a4169c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/24/2020
ms.locfileid: "43804762"
---
# <a name="microsoft-secure-score"></a>Microsoft Secure Score

A pontuação segura da Microsoft é uma medida da postura de segurança de uma organização, com um número maior indicando ações mais aprimoradas. Seguir as recomendações de Pontuação de segurança podem proteger sua organização contra ameaças. A partir de um painel centralizado no centro de segurança do Microsoft 365, as organizações podem monitorar e trabalhar com a segurança de suas identidades, dados, aplicativos, dispositivos e infraestrutura do Microsoft 365.

A pontuação segura ajuda as organizações:

* Relatar o estado atual da postura de segurança da organização.
* Melhorar a postura de segurança fornecendo descoberta, visibilidade, orientação e controle.  
* Compare com benchmarks e estabeleça indicadores de desempenho principais (KPIs).

As organizações obtêm acesso a visualizações robustas de métricas e tendências, integração com outros produtos da Microsoft, comparação de pontos com organizações similares e muito mais. A pontuação também pode refletir quando soluções de terceiros solucionaram as ações recomendadas.

Além disso, você pode acessar suas recomendações e pontuações por meio da [API do Microsoft Graph](https://www.microsoft.com/security/partnerships/graph-security-api). Saiba mais sobre o [tipo de recurso de Pontuação segura](https://go.microsoft.com/fwlink/?linkid=2092996).

## <a name="how-it-works"></a>Como funciona

Você receberá pontos para configurar os recursos de segurança recomendados, executar tarefas relacionadas à segurança (como exibir relatórios) ou abordar a ação de aperfeiçoamento com um aplicativo ou software de terceiros. Algumas ações de melhoria só dão pontos quando estão totalmente concluídas, e algumas fornecem pontos parciais se forem concluídas para alguns dispositivos ou usuários.

Mostramos o conjunto completo de possíveis aprimoramentos, independentemente da licença, para que você possa entender as práticas recomendadas de segurança e aprimorar sua pontuação. Sua postura de segurança absoluta é representada pela pontuação segura, que permanece a mesma, não importa quais licenças de produto sua organização possui. Tenha em mente que a segurança deve ser balanceada com usabilidade, e nem todas as recomendações podem funcionar para seu ambiente.

Sua pontuação é atualizada em tempo real para refletir as informações apresentadas nas páginas de ações de visualizações e melhorias. A pontuação segura também sincroniza diariamente para receber dados do sistema sobre seus pontos obtidos para cada ação.

### <a name="how-improvement-actions-are-scored"></a>Como as ações de aperfeiçoamento são pontuadas

A maioria é classificada de forma binária, se você implementar a ação de melhoria, como criar uma nova política ou ativar uma configuração específica, obterá 100% dos pontos. Para outras ações de melhoria, os pontos são fornecidos como uma porcentagem da configuração total. Por exemplo, se a ação de melhoria diz que você obtém 30 pontos protegendo todos os seus usuários com a autenticação multifator e tem apenas 5 de 100 total de usuários protegidos, você receberia uma pontuação parcial de cerca de 2 pontos (5 protegidos/100 total * 30 pts = 2 pt de Pontuação parcial).

### <a name="products-included-in-secure-score"></a>Produtos incluídos na pontuação segura

No momento, há recomendações para incluir o SharePoint Online, o Exchange Online, o OneDrive for Business, o Microsoft Information Protection e outros, o Azure AD e o Cloud app Security. As recomendações para outros produtos de segurança, como o Azure ATP e o Microsoft defender ATP, serão disponibilizadas em breve. As recomendações não abrangem todas as superfícies de ataque associadas a cada produto, mas são uma boa linha de base. Você também pode marcar as ações de melhoria como cobertas por terceiros.

## <a name="required-permissions"></a>Permissões obrigatórias

Para ter permissão para acessar a pontuação segura da Microsoft, você deve receber uma das seguintes funções no Azure Active Directory.

### <a name="read-and-write-roles"></a>Funções de leitura e gravação

Com acesso de leitura e gravação, você pode fazer alterações e interagir diretamente com a pontuação segura. Você também pode atribuir acesso somente leitura a outros usuários.

* Administrador global
* Administrador de segurança
* Administrador do Exchange
* Administrador do SharePoint

### <a name="read-only-roles"></a>Funções somente leitura

Com acesso somente leitura, você não pode editar o status ou as anotações de uma ação de melhoria, editar zonas de pontuação ou editar comparações personalizadas.

* Administrador de assistência técnica
* Administrador de usuários
* Administrador de serviço
* Leitor de segurança
* Operador de segurança
* Leitor global

### <a name="graph-api"></a>API do Graph

Para acessar a API do Graph, você precisa ter um dos seguintes escopos, além de uma função:

* Escopo securityevents. Read. All (para função somente leitura)
* Escopo securityevents. ReadWrite. All (para função de leitura e gravação)

## <a name="gain-visibility-into-your-security-posture"></a>Obter visibilidade da postura de segurança

Para ajudá-lo a obter mais rapidamente as informações de que você precisa, as ações de melhoria da Microsoft são organizadas em grupos:

* Identidade (contas do Azure AD & funções)
* Dados (proteção de informações da Microsoft)
* Dispositivo (sem ações de melhoria por enquanto)
* Aplicativo (aplicativos de email e de nuvem, incluindo o Office 365 e o Microsoft Cloud app Security)
* Infraestrutura (sem ações de melhoria por enquanto)

Na página de visão geral de Pontuação segura da Microsoft, você pode ver como os pontos são divididos entre esses grupos e que pontos estão disponíveis. A página de visão geral também é o local para obter uma visão completa da pontuação total, tendência histórica de sua pontuação segura com comparações de benchmark e ações de melhoria priorizadas que podem ser tomadas para melhorar sua pontuação.

![Home Page](../../media/secure-score/homepage-original.png)
de Pontuação segura*Figura 1: página de visão geral de Pontuação segura da Microsoft*

## <a name="take-action-to-improve-your-score"></a>Executar uma ação para melhorar sua pontuação

A guia ações de melhoria lista as recomendações de segurança que lidam com possíveis superfícies de ataque, juntamente com o status (concluído, não concluído, resolvido por terceiros e ignorado). Você pode pesquisar, filtrar e agrupar todas as ações de aperfeiçoamento.

### <a name="ranking"></a>Classificação

A classificação baseia-se no número de outros pontos restantes para atingir, dificuldade de implementação, impacto do usuário e complexidade. As ações mais altas de melhoria da classificação têm um grande número de pontos restantes com baixa dificuldade, impacto do usuário e complexidade.

### <a name="actions"></a>Ações

As ações rotuladas como [not score] não são rastreadas pela pontuação segura da Microsoft. Você ainda pode tomar ações, mas concluí-las não afetará sua pontuação. Se uma ação for rastreada pela pontuação segura da Microsoft no futuro e você já a tiver concluído, sua pontuação segura refletirá automaticamente a alteração.

Quando você seleciona uma ação de aprimoramento específica, uma saída é exibida. Para concluir a ação, você tem algumas opções:

1. Selecione **configurações de exibição** para ir para a tela de configuração e fazer a alteração. Em seguida, você obtém os pontos que a ação vale a pena, visível na parte superior da saída. Os pontos podem levar até 24 horas para serem atualizados.

2. Selecione **resolver por meio** de terceiros, pois a ação de aprimoramento já foi abordada por um aplicativo ou software de terceiros. Você ganha os pontos que a ação vale, para que sua pontuação segura reflita melhor a postura geral de segurança. Se um terceiro não mais cobrir o controle, você poderá marcar a ação de melhoria como não concluída. Lembre-se de que a Microsoft não tem visibilidade de que os requisitos de Pontuação foram atendidos se a ação de aprimoramento for marcada como resolvida por terceiros.

3. Selecione **ignorar** porque você optou por aceitar o risco e não enact a ação de aperfeiçoamento. Após ignorar uma ação de melhoria, o número total de pontos de Pontuação segura que você pode alcançar é reduzido. Você pode exibir essa ação no histórico ou desfazê-la a qualquer momento.

![Exemplo de ação de melhoria da Pontuação de segurança](../../media/secure-score/secure-score1x450.png)

*Figuras 2 & 3: aprimorar submenus de ação*

## <a name="monitor-improvements-over-time"></a>Monitorar melhorias ao longo do tempo

Você pode exibir um gráfico da pontuação da sua organização ao longo do tempo na guia **histórico** . abaixo do gráfico, há uma lista de todas as ações realizadas no intervalo de tempo selecionado e seus atributos, como pontos e categorias resultantes. Você pode personalizar um intervalo de datas e filtrar por categoria.

## <a name="risk-awareness"></a>Reconhecimento de risco

A pontuação segura da Microsoft é um resumo numérico de sua postura de segurança com base nas configurações do sistema, no comportamento do usuário e em outras medidas relacionadas à segurança; Não é uma medida absoluta da probabilidade de que seu sistema ou dados seja violado. Em vez disso, ele representa a extensão à qual você adotou os controles de segurança no seu ambiente Microsoft, o que pode ajudar a reduzir o risco de ser violado. Nenhum serviço online é totalmente imune às brechas de segurança e a pontuação segura não deve ser interpretada como uma garantia contra violação de segurança de qualquer forma.

## <a name="whats-new"></a>Quais são as novidades?

Para tornar a pontuação segura da Microsoft um melhor representante da postura de segurança, fizemos algumas alterações. Para saber mais sobre as alterações planejadas, confira [o que está acontecendo na pontuação segura da Microsoft?](microsoft-secure-score-whats-coming.md)

### <a name="april-21st-2020"></a>21 de abril de 2020

#### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Removendo ações de melhoria que não atendem às expectativas para uma medição confiável ou não oferecem uma representação útil de postura de segurança

Para garantir que a pontuação segura da Microsoft seja significativa e que cada ação de melhoria seja mensurável e confiável, estamos removendo as seguintes ações de aprimoramento.

- Aplicar proteções de IRM a documentos
- Aplicar políticas de prevenção contra perda de dados

### <a name="january---march-2020"></a>Janeiro-Março de 2020

#### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a>Padrões de segurança de suporte para ações de melhoria do Azure AD

A pontuação segura da Microsoft atualizará as ações de aperfeiçoamento para suportar os [padrões de segurança no Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), o que facilita a proteção da sua organização com configurações de segurança pré-configuradas para ataques comuns.

Isso afetará as seguintes ações de melhoria:

- Garantir que todos os usuários possam concluir a autenticação multifator para acesso seguro
- Exigir MFA para funções administrativas
- Habilitar política para bloquear autenticação herdada

#### <a name="removed-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Ações de melhoria removidas que não atendem às expectativas para uma medição confiável ou não oferecem uma representação útil de postura de segurança

Para garantir que a pontuação segura da Microsoft seja significativa e que cada ação de melhoria seja mensurável e confiável, estamos removendo as seguintes ações de aprimoramento.

- Armazenar documentos de usuário no OneDrive for Business
- Configurar as políticas de anexo seguro do Office 365 ATP
- Configurar links seguros do Office 365 para verificar URLs
- Não permitir a delegação de caixa de correio
- Permitir links de compartilhamento de convidados anônimos para sites e documentos
- Ativar console do Cloud app Security
- Configurar tempo de expiração para links de compartilhamento externos
- Ativar a gravação de dados de auditoria
- Descobrir aplicativos de ti de sombra arriscados e não compatíveis
- Examinar permissões & bloquear aplicativos OAuth arriscados conectados ao seu ambiente
- Configurar o controle de versão em bibliotecas de documentos do SharePoint Online
- Excluir/bloquear contas não usadas nos últimos 30 dias
- Designar menos de 5 administradores globais

#### <a name="removed-not-scored-improvement-actions"></a>Ações de melhoria "não classificadas" removidas

Um dos princípios de Pontuação segura é que a pontuação deve ser padronizada e fácil de se relacionar. Ter ações de melhoria que não podem ser mensuráveis ou acionável está causando confusão. A pontuação segura da Microsoft faz sentido quando cada recomendação pode ter um efeito claro na pontuação. As ações de melhoria não pontuadas não são mensuráveis.  

Por esses motivos, todas as ações de melhoria que não foram pontuadas foram removidas. Nenhuma ação é necessária em sua parte.

#### <a name="removed-device-improvement-actions"></a>Ações de melhoria de dispositivo removidas

Após uma avaliação da categoria dispositivo de Pontuação segura da Microsoft de ações de melhoria, foi determinado que essas ações atualmente avaliam o estado da política e não o estado de configuração dos dispositivos. Como a configuração está diretamente ligada à postura de segurança, as ações de dispositivo existentes foram determinadas para não representar totalmente a postura organizacional.  Iremos remover as ações atuais na categoria do dispositivo à medida que trabalhamos para fornecer um conjunto de recomendações que usam diretamente dados de diagnóstico para representar uma postura de segurança de dispositivos.

As seguintes ações aprimoradas foram removidas:

- Habilitar o gerenciamento de dispositivos móveis do Microsoft Intune
- Criar uma política de conformidade do Microsoft Intune para Android
- Criar uma política de conformidade do Microsoft Intune para Android para trabalho
- Criar uma política de proteção de aplicativos do Microsoft Intune para Android
- Criar uma política de proteção de aplicativos do Microsoft Intune para iOS
- Marcar dispositivos sem política de conformidade do Microsoft Intune atribuída como não compatível
- Criar uma política de conformidade do Microsoft Intune para iOS
- Criar uma política de conformidade do Microsoft Intune para o macOS
- Criar uma política de conformidade do Microsoft Intune para o Windows
- Criar um perfil de configuração do Microsoft Intune para Android
- Criar um perfil de configuração do Microsoft Intune para Android para trabalho
- Criar um perfil de configuração do Microsoft Intune para o macOS
- Criar um perfil de configuração do Microsoft Intune para iOS
- Criar um perfil de configuração do Microsoft Intune para Windows
- Habilitar a detecção avançada do jailbreak no Microsoft Intune
- Exigir que todos os dispositivos sejam corrigidos, ter antivírus e firewalls habilitados
- Habilitar a integração ATP do Windows Defender no Microsoft Intune
- Criar uma política de proteção de informações do Windows do Microsoft Intune
- Exigir que todos os dispositivos tenham configurações de segurança avançadas
- Examinar o relatório de dispositivos bloqueados semanalmente

#### <a name="mfa-improvement-action-updates"></a>Atualizações das ações de melhoria da MFA

Para refletir a necessidade de que as empresas garantam o máximo de segurança durante a aplicação de políticas que funcionam com seus negócios, a pontuação segura da Microsoft removeu três ações de melhoria centralizada em relação à autenticação multifator e a adição de duas.

Ações de melhoria removidas:

- Registrar todos os usuários para autenticação multifator
- Exigir MFA para todos os usuários
- Exigir MFA para funções privilegiadas do Azure AD

Ações aprimoradas foram adicionadas:

- Garantir que todos os usuários possam concluir a autenticação multifator para acesso seguro
- Exigir MFA para funções administrativas

 Essas novas ações de melhoria exigem o registro de seus usuários ou administradores para autenticação multifator (MFA) em seu diretório e o estabelecimento do conjunto certo de políticas que atendam às suas necessidades organizacionais. O objetivo principal é ter flexibilidade enquanto garante que todos os seus usuários e administradores podem autenticar com vários fatores ou solicitações de verificação de identidade baseadas em risco. Isso pode ter a forma de ter várias políticas que aplicam decisões com escopo ou definir padrões de segurança (chegando a 16 de março) que permitem que a Microsoft decida quando desafiar os usuários para a MFA.

#### <a name="removed-review-improvement-actions"></a>Foram removidas ações de melhoria de "análise"

Um dos princípios de Pontuação segura é que a pontuação deve ser padronizada e fácil de se relacionar. Ter ações de melhoria que não podem ser mensuráveis ou acionável está causando confusão. Uma pontuação segura da Microsoft faz sentido quando cada recomendação pode ter um efeito claro na pontuação. Revisar as ações de melhoria não são medidas para o mesmo padrão que outras ações de aprimoramento.  

Por esses motivos, todas as ações de melhoria que exigiram uma cadência de revisão foram temporariamente removidas. Nenhuma ação é necessária em sua parte.

### <a name="preview-features"></a>Visualização prévia de recursos

Os seguintes recursos serão incluídos na [versão prévia](microsoft-secure-score-preview.md):

* Todos os novos modos de exibição de métricas e tendências para discussões de nível de líder e CISO
* Novas maneiras de acompanhar e avaliar a sua pontuação
* Melhor controle e monitoramento para regressões de Pontuação
* Filtrar, marcar, Pesquisar e agrupar suas ações de aperfeiçoamento
* Gerenciar em direção às suas metas futuras usando pontuações de Pontuação e ações planejadas
* Simplificação do sistema de pontos
* E muito mais!

## <a name="we-want-to-hear-from-you"></a>Queremos ouvir sua opinião

Se você tiver problemas, informe-nos por postagem na Comunidade de [segurança, privacidade & conformidade](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . Estamos monitorando a Comunidade e forneceremos ajuda.
