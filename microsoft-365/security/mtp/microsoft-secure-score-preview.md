---
title: Pontuação segura da Microsoft (visualização)
description: Descreve a pontuação segura da Microsoft na central de segurança do Microsoft 365, como os detalhes são calculados e quais administradores de segurança podem esperar usá-lo.
keywords: segurança, malware, Microsoft 365, M365, Pontuação segura, central de segurança, ações de melhoria
ms.prod: w10
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
ms.openlocfilehash: 8277549c683da19dbbf915a7cf673fc731cb8803
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141400"
---
# <a name="microsoft-secure-score-preview"></a>Pontuação segura da Microsoft (visualização)

>[!IMPORTANT]
>Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

A pontuação segura da Microsoft é uma medida da postura de segurança de uma organização, com um número maior indicando ações mais aprimoradas. Ele pode ser encontrado no https://security.microsoft.com/securescore na [central de segurança do Microsoft 365](overview-security-center.md).

Seguir as recomendações de Pontuação de segurança podem proteger sua organização contra ameaças. A partir de um painel centralizado no centro de segurança do Microsoft 365, as organizações podem monitorar e trabalhar com a segurança de suas identidades, dados, aplicativos, dispositivos e infraestrutura do Microsoft 365.

A pontuação segura ajuda as organizações:  

* Relatar o estado atual da postura de segurança da organização.
* Melhorar a postura de segurança fornecendo descoberta, visibilidade, orientação e controle.  
* Compare com benchmarks e estabeleça indicadores de desempenho principais (KPIs).

As organizações obtêm acesso a visualizações robustas de métricas e tendências, integração com outros produtos da Microsoft, comparação de pontos com organizações similares e muito mais. A pontuação também pode refletir quando soluções de terceiros solucionaram as ações recomendadas.

Além disso, você pode acessar suas recomendações e pontuações por meio da [API do Microsoft Graph](https://www.microsoft.com/security/partnerships/graph-security-api). Saiba mais sobre o [tipo de recurso de Pontuação segura](https://go.microsoft.com/fwlink/?linkid=2092996).

## <a name="how-it-works"></a>Como funciona

Você receberá pontos para configurar os recursos de segurança recomendados, executar tarefas relacionadas à segurança ou abordar a ação de melhoria com um aplicativo ou software de terceiros. Algumas ações de melhoria só dão pontos quando estão totalmente concluídas, e algumas fornecem pontos parciais se forem concluídas para alguns dispositivos ou usuários. Se você não pode ou não deseja enactr uma das ações de aperfeiçoamento, você pode optar por aceitar o risco ou o risco restante.

Mostramos o conjunto completo de possíveis aprimoramentos, independentemente da licença, para que você possa entender as práticas recomendadas de segurança e aprimorar sua pontuação. Sua postura de segurança absoluta é representada pela pontuação segura, que permanece a mesma, não importa quais licenças de produto sua organização possui. Tenha em mente que a segurança deve ser balanceada com usabilidade, e nem todas as recomendações podem funcionar para seu ambiente.

Sua pontuação é atualizada em tempo real para refletir as informações apresentadas nas páginas de ações de visualizações e melhorias. A pontuação segura também sincroniza diariamente para receber dados do sistema sobre seus pontos obtidos para cada ação.

### <a name="how-improvement-actions-are-scored"></a>Como as ações de aperfeiçoamento são pontuadas

Cada ação de melhoria vale 10 pontos ou menos. A maioria é classificada de forma binária, se você implementar a ação de melhoria, como criar uma nova política ou ativar uma configuração específica, obterá 100% dos pontos. Para outras ações de melhoria, os pontos são fornecidos como uma porcentagem da configuração total. Por exemplo, se a ação de melhoria diz que você obtém 30 pontos protegendo todos os seus usuários com a autenticação multifator e tem apenas 5 de 100 total de usuários protegidos, você receberia uma pontuação parcial de cerca de 2 pontos (5 protegidos/100 total * 30 pts = 2 pt de Pontuação parcial).

### <a name="products-included-in-secure-score"></a>Produtos incluídos na pontuação segura

No momento, há recomendações para o Microsoft 365 (incluindo o Exchange Online), o Azure AD, o Microsoft defender ATP, o Azure ATP e o Cloud app Security. As recomendações para outros produtos de segurança serão disponibilizadas em breve. As recomendações não abrangem todas as superfícies de ataque associadas a cada produto, mas são uma boa linha de base. Você também pode marcar as ações de melhoria como cobertas por terceiros.

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

### <a name="graph-api"></a>API do Graph

Para acessar a API do Graph, você precisa ter um dos seguintes escopos, além de uma função:

* Escopo securityevents. Read. All (para funções somente leitura)
* Escopo securityevents. ReadWrite. All (para funções de leitura e gravação)

## <a name="gain-visibility-into-your-security-posture"></a>Obter visibilidade da postura de segurança

Para ajudá-lo a obter mais rapidamente as informações de que você precisa, as ações de melhoria da Microsoft são organizadas em grupos:

* Identidade (contas do Azure AD & funções)
* Dados (proteção de informações da Microsoft)
* Dispositivo (Microsoft defender ATP)
* Aplicativo (aplicativos de email e de nuvem, incluindo o Office 365 e o Microsoft Cloud app Security)
* Infraestrutura (sem ações de melhoria por enquanto)

Na página de visão geral de Pontuação segura da Microsoft, você pode ver como os pontos são divididos entre esses grupos e que pontos estão disponíveis. A página de visão geral também é o local para obter uma visão completa da pontuação total, tendência histórica de sua pontuação segura com comparações de benchmark e ações de melhoria priorizadas que podem ser tomadas para melhorar sua pontuação.

![Home Page](../../media/secure-score/secure-score-homepage.png)
de Pontuação segura*Figura 1: página de visão geral de Pontuação segura da Microsoft*

## <a name="take-action-to-improve-your-score"></a>Executar uma ação para melhorar sua pontuação

A guia **ações de melhoria** lista as recomendações de segurança que lidam com possíveis superfícies de ataque, juntamente com seu status (para endereços, planejados, riscos aceitos, resolvidos por terceiros, resolvidos por meio de atenuação alternativa e conclusão). Você pode pesquisar, filtrar e agrupar todas as ações de aperfeiçoamento.  

### <a name="ranking"></a>Classificação

A classificação baseia-se no número de outros pontos restantes para atingir, dificuldade de implementação, impacto do usuário e complexidade. As ações mais altas de melhoria da classificação têm um grande número de pontos restantes com baixa dificuldade, impacto do usuário e complexidade.

### <a name="view-improvement-action-details"></a>Exibir detalhes da ação de aprimoramento

Quando você seleciona uma ação de aprimoramento específica, um submenu de página inteira aparece.  

![Exemplo](../../media/secure-score/secure-score-improvement-action-details.png)
de submenu de ação de melhoria*Figura 2: exemplo de submenu de ação de melhoria*

Para concluir a ação, você tem algumas opções:

* Selecione **gerenciar** para ir para a tela de configuração e fazer a alteração. Em seguida, você obterá os pontos que a ação vale a pena, visível no surgimento. Os pontos geralmente levam cerca de 24 horas para atualização.

* Selecione **compartilhar** para copiar o link direto para a ação de aprimoramento ou escolha a plataforma para compartilhar o link, como email, Microsoft Teams, Microsoft Planner ou ServiceNow. Selecionar o ServiceNow permitirá que você crie um tíquete de alteração que ficará visível no ServiceNow e na página inicial da central de segurança do Microsoft 365. Para saber mais, confira [centro de segurança do Microsoft 365 e integração com o ServiceNow](tickets.md).

### <a name="choose-an-improvement-action-status"></a>Escolher um status de ação de melhoria

Escolha qualquer status e registre as anotações específicas da ação de aprimoramento. O Statues que você pode selecionar são os seguintes:

* **Para endereço** — você reconhece que a ação de melhoria é necessária e planeja fazê-lo em algum momento no futuro. Esse estado também se aplica às ações detectadas como parcialmente, mas não completamente concluídas.
* **Planejado** — há planos concretos in-loco para concluir a ação de melhoria.
* **Risco aceito** — a segurança deve sempre ser balanceada com usabilidade e nem todas as recomendações funcionarão para o seu ambiente. Quando esse for o caso, você pode optar por aceitar o risco ou o risco restante, e não enact a ação de aperfeiçoamento. Você não receberá nenhum ponto, mas a ação não estará mais visível na lista de ações de aprimoramento. Você pode exibir essa ação no histórico ou desfazê-la a qualquer momento.
* **Resolvido** por terceiros e **resolvido por meio de mitigação alternativa** — a ação de melhoria já foi abordada por um aplicativo ou software de terceiros, ou por uma ferramenta interna. Você ganhará os pontos que a ação vale a pena, de forma que sua pontuação reflita melhor a postura geral de segurança. Se um terceiro ou uma ferramenta interna não mais cobrir o controle, você poderá escolher outro status. Tenha em mente que a Microsoft não terá nenhuma visibilidade da integridade da implementação se a ação de aprimoramento estiver marcada como um desses status.

#### <a name="threat--vulnerability-management-improvement-actions"></a>Ações de melhoria de gerenciamento de vulnerabilidade & ameaça

Para ações de melhoria na categoria "dispositivo", você não poderá escolher status. Em vez disso, você será direcionado para a [recomendação de segurança TVM (gerenciamento de vulnerabilidades) associada à & ameaça](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) no centro de segurança do [Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) para executar a ação. A exceção escolhida e a justificação que você escreve serão específicas para esse portal e não estarão presentes no portal de Pontuação segura da Microsoft.

#### <a name="completed-improvement-actions"></a>Ações de aperfeiçoamento concluídas

Ações de melhoria têm um status de "concluído" uma vez que todos os pontos possíveis para a ação de aprimoramento foram atingidos. Ações de melhoria concluídas são confirmadas por meio de dados da Microsoft, e você não poderá alterar o status.

### <a name="assess-information-and-review-user-impact"></a>Avaliar informações e analisar o impacto do usuário

A seção de **visão geral** lhe informará a categoria, os ataques que ela pode proteger contra o e o produto.

O **impacto do usuário** mostra o que os usuários terão de enfrentar se a ação de aprimoramento for executada, e **os usuários afetados** mostrarão o que perceberão.

### <a name="implement-the-improvement-action"></a>Implementar a ação de melhoria

A seção **implementação** mostra todos os pré-requisitos, as próximas etapas passo a passo para concluir a ação de melhoria, o status da implementação atual da ação de aprimoramento e todos os mais links.

Os pré-requisitos serão quaisquer licenças que precisam ser obtidas ou ações que precisam ser concluídas antes de a ação de aprimoramento ser resolvida. Certifique-se de que você tem estações suficientes em sua licença para concluir a ação de melhoria e que essas licenças são aplicadas aos usuários necessários.  

## <a name="track-your-score-history-and-meet-goals"></a>Acompanhar o histórico de Pontuação e atingir as metas

Você pode exibir um gráfico da pontuação da sua organização ao longo do tempo na guia **histórico** . abaixo do gráfico, há uma lista de todas as ações realizadas no intervalo de tempo selecionado e seus atributos, como pontos e categorias resultantes. Você pode personalizar um intervalo de datas e filtrar por categoria.

Na guia **métricas & tendências** , há vários gráficos e gráficos para dar mais visibilidade às tendências e definir metas. Você pode definir o intervalo de datas para a página inteira de visualizações. As visualizações incluem:

* **Sua zona de Pontuação segura** — personalizada com base nas metas e definições da sua organização de intervalos de pontos bons, incorretos e ruins.
* **Tendência de regressão** — uma linha do tempo de pontos que foi regressivo devido às alterações de configuração, usuário ou dispositivo.  
* **Tendência de comparação** — como a pontuação segura da sua organização é comparada com as demais. Este modo de exibição pode incluir linhas que representam a média de Pontuação de organizações com contagem de assentos semelhante e uma exibição de comparação personalizada que você pode definir.
* **Tendência de aceitação de riscos** – linha do tempo de ações de aperfeiçoamento marcadas como "risco aceito".
* **Alterações de Pontuação** — o número de pontos alcançados, pontos redefinidos, juntamente com a pontuação subsequente mudar, no intervalo de datas especificado.

## <a name="risk-awareness"></a>Reconhecimento de risco

A pontuação segura da Microsoft é um resumo numérico de sua postura de segurança com base nas configurações do sistema, no comportamento do usuário e em outras medidas relacionadas à segurança; Não é uma medida absoluta da probabilidade de que seu sistema ou dados seja violado. Em vez disso, ele representa a extensão à qual você adotou os controles de segurança no seu ambiente Microsoft, o que pode ajudar a reduzir o risco de ser violado. Nenhum serviço online é totalmente imune às brechas de segurança e a pontuação segura não deve ser interpretada como uma garantia contra violação de segurança de qualquer forma.

## <a name="whats-new"></a>Quais são as novidades? 

Para tornar a pontuação segura da Microsoft um melhor representante da postura de segurança, fizemos algumas alterações. Para saber mais sobre as alterações planejadas, confira [o que está acontecendo na pontuação segura da Microsoft?](microsoft-secure-score-whats-coming.md).

### <a name="april-2020"></a>Abril de 2020

#### <a name="added-azure-active-directory-improvement-action"></a>Foi adicionada a ação de melhoria do Azure Active Directory

- Não permitir que os usuários conceda consentimento a aplicativos não gerenciados (atualmente disponível na versão lançada)

#### <a name="added-azure-advanced-threat-protection-improvement-actions"></a>Foram adicionadas ações aprimoradas para proteção avançada contra ameaças do Azure

- Desabilitar o serviço spooler de impressão em controladores de domínio
- Modificar as delegações Kerberos não seguras para impedir a representação
- Proteger e gerenciar senhas de administrador local com o Microsoft LAPS
- Reduzir o risco de caminho de movimento lateral para entidades confidenciais
- Remover contas inativas de grupos confidenciais
- Remover atributos de histórico de SID não seguros das entidades
- Resolver atributos de conta não seguros
- Parar exposição de credenciais de texto não criptografado
- Parar comunicação de protocolos herdados
- Interromper o uso de codificação fraca

#### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations"></a>Suporte para recomendações de segurança do TVM (gerenciamento de vulnerabilidades) do Microsoft defender & ATP

Todas as recomendações de segurança lançadas fornecidas pelo TVM estão disponíveis agora.

### <a name="january---march-2020"></a>Janeiro-Março de 2020

#### <a name="updated-interface-and-functionality"></a>Interface e funcionalidade atualizadas

* Todos os novos modos de exibição de métricas e tendências para discussões de nível de líder e CISO
* Novas maneiras de acompanhar e avaliar a sua pontuação
* Melhor controle e compreensão para regressões de Pontuação
* Filtrar, marcar, Pesquisar e agrupar suas ações de aperfeiçoamento
* Gerenciar em direção às suas metas futuras usando pontuações de Pontuação e ações planejadas
* E muito mais!

#### <a name="removed-not-scored-and-review-improvement-actions"></a>Ações de melhoria "não classificadas" e "revisar" removidas

Um dos princípios de Pontuação segura é que a pontuação deve ser padronizada e fácil de se relacionar. Ter ações de melhoria que não podem ser mensuráveis ou acionável está causando confusão. Uma pontuação segura da Microsoft faz sentido quando cada recomendação pode ter um efeito claro na pontuação. As ações de melhoria não pontuadas não são mensuráveis e as ações de análise de revisão não são medidas para o mesmo padrão como outras ações de aprimoramento.

Por esses motivos, todas as ações de melhoria que não foram pontuadas ou exigiam uma cadência de revisão foram temporariamente removidas. Nenhuma ação é necessária em sua parte.

#### <a name="simplification-of-the-point-system"></a>Simplificação do sistema de pontos

Para padronizar pontos em várias experiências, cada ponto de ação de melhoria de Pontuação segura foi atualizado para exceder 10 pontos ou menos. É necessário ser mais consistente em todo o espectro de controles de segurança que temos hoje e aqueles que iremos adicionar no futuro. Embora essa seja uma alteração significativa e você veja os totais de pontos de projeção, não haverá mudanças na sua postura de segurança.

## <a name="we-want-to-hear-from-you"></a>Queremos ouvir sua opinião

Se você tiver problemas, informe-nos por postagem na Comunidade de [segurança, privacidade & conformidade](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . Estamos monitorando a Comunidade e forneceremos ajuda.
