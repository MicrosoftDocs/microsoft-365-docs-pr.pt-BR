---
title: Visão geral da central de segurança do Microsoft 365
description: Vantagens na central de segurança do Microsoft 365, combinando o Microsoft Defender para Office 365 (MDO) e o Microsoft Defender for Endpoint (MDE), com o Microsoft Defender for Identity (MDI) e o Microsoft Cloud App Security (MCAS). Este artigo descreve os avanços da central de segurança do Microsoft 365 para os administradores.
keywords: segurança, malware, Microsoft 365, M365, centro de segurança, monitorar, relatório, identidades, dados, dispositivos, aplicativos
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.date: 02/02/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 89e72d703bd70647d6c2b00732315b8e5f015cc7
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167166"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a>Visão geral da central de segurança unificada do Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Aplica-se a:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)

> Deseja experimentar o Microsoft 365 Defender? Você pode [avaliá-lo em um ambiente de laboratório](https://aka.ms/mtp-trial-lab) ou executar seu projeto piloto em [produção.](https://aka.ms/m365d-pilotplaybook)

O centro de segurança aprimorado do **Microsoft 365** ( ) combina proteção, detecção, investigação e resposta a emails , colaboração, identidade e ameaças de dispositivo, em [https://security.microsoft.com](https://security.microsoft.com) um portal central.    

O centro de segurança do Microsoft 365 reúne a funcionalidade de portais de segurança da Microsoft existentes, como a Central de Segurança do Microsoft Defender e o Centro de Conformidade e Segurança do Office 365 & Segurança. A central de segurança enfatiza o acesso rápido a informações, layouts mais simples e reunir informações relacionadas para facilitar o uso. Esse centro inclui:

- **[Microsoft Defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)** O Microsoft Defender para Office 365 ajuda as organizações a proteger sua empresa com um conjunto de recursos de prevenção, detecção, investigação e busca para proteger emails e recursos do Office 365.
- **[O Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)** oferece proteção preventiva, detecção pós-violação, investigação automatizada e resposta para dispositivos em sua organização.
- **[O Microsoft 365 Defender](microsoft-threat-protection.md)** faz parte da solução XDR *(Detecção* e Resposta Estendida) da Microsoft que aproveita o portfólio de segurança do Microsoft 365 para analisar automaticamente os dados de ameaças entre domínios e criar uma imagem de um ataque em um único painel.

Se você precisar de informações sobre o que mudou no Centro de Conformidade e Segurança do Office 365 & ou na Central de Segurança do Microsoft Defender, confira:

- [Defender para Office 365 na central de segurança do Microsoft 365](microsoft-365-security-center-mdo.md)
- [Defender para Ponto de Extremidade na central de segurança do Microsoft 365](microsoft-365-security-center-mde.md)

## <a name="what-to-expect"></a>O que esperar

Todo o conteúdo de segurança que você usa no Centro de Conformidade e Segurança do Office 365 (protection.office.com) e no centro de segurança do Microsoft Defender (securitycenter.microsoft.com) agora pode ser encontrado no centro de segurança do *Microsoft 365.*

O centro de segurança do Microsoft 365 ajuda as equipes de segurança a investigar e responder a ataques ao se transformar em sinais de diferentes cargas de trabalho em uma única experiência unificada:

- Incidentes & alertas
- Busca
- Central de Ações
- Análise de ameaças

A central de segurança do Microsoft 365 enfatiza a *unidade,* clareza e metas comuns à medida que mescla o Microsoft Defender para Office 365 e o Microsoft Defender para o Ponto de Extremidade. A mesclagem foi baseada nas prioridades listadas abaixo e feita sem comprometer os recursos que cada pacote de segurança trouxe à combinação:

- blocos de construção comuns
- terminologia comum
- entidades comuns
- paridade de recursos com outras cargas de trabalho

## <a name="unified-investigations"></a>Investigações unificadas

O alinhamento de centros de segurança cria um único painel para investigar incidentes em uma organização do Microsoft 365. Um exemplo principal é o **nó Incidentes** no início rápido da central de segurança do Microsoft 365.

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="A página Incidentes no MDO.":::

Por exemplo, clicar duas vezes em  um nome de incidente com Alta gravidade leva você a uma página que demonstra a vantagem de convergir centros.

![Incidentes em vários estágios que envolvem o escalonamento de privilégios em vários pontos de extremidade, mostrando 16 dispositivos afetados e 9 usuários afetados.](../../media/converged-incident-info-3.png)

> [!TIP]
> A guia **Usuários convergentes** é um bom lugar para começar suas perguntas. Esta página única apresenta informações para usuários de cargas de trabalho convergentes (Microsoft Defender para Ponto de Extremidade, Microsoft Defender para Identidade e MCAS, se você aproveitar) e uma variedade de fontes, como o Active Directory local, o Azure Active Directory, sincronizados, locais e usuários de terceiros. Saiba mais sobre [a nova experiência de usuários.](investigate-users.md)

As informações sobre incidentes mostram as especificidades do usuário/identidade e os dispositivos em risco, ao lado das caixas de correio afetadas. Ele também relaciona quaisquer informações **de investigação e** evidências **coletadas.** Isso torna mais fácil para administradores e equipes de operações de segurança girar de um alerta de alto risco para os usuários e caixas de correio afetados. Observando as **guias incidentes** na parte superior desta página, há outros pivôs de segurança principais disponíveis neste único local.

> [!IMPORTANT]
> Na parte superior de qualquer página de um incidente específico, você verá as guias Resumo,  **Alertas, Dispositivos,** Usuários **,** Caixas de **Correio,** **Investigações** e Evidências.

Selecionar **Investigações** abre uma página que apresenta um gráfico da análise que está ocorrendo e lista um status (como aprovação **pendente)** para correção. Tome tempo para selecionar incidentes específicos em seu ambiente, detalhar essas guias e praticar a criação de um perfil para diferentes tipos de ameaças. A familiaridade beneficiará as investigações posteriores.

## <a name="improved-processes"></a>Processos aprimorados

Controles comuns e conteúdo aparecem no mesmo lugar ou são condensados em um feed de dados, facilitando a pesquisa. Por exemplo, configurações unificadas.

### <a name="unified-settings"></a>Configurações unificadas

![clicou em "Funções" e abriu a página Configurações, que inclui Configurações Gerais, Permissões, APIs e Regras. Abra Permissões e, em seguida, Funções. Mostra todas as funções](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>Permissões & funções

![Permissions & Roles page showing Endpoints roles & groups, Roles, and Device groups.](../../media/converged-roles-5.png)

 O acesso à central de segurança do Microsoft 365 está configurado com funções globais do Azure Active Directory ou usando funções personalizadas. Para o Defender para Ponto de Extremidade, confira [Atribuir acesso de usuário à Central de Segurança do Microsoft Defender.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/assign-portal-access) Para o Defender para Office 365, confira Permissões no centro de conformidade do Microsoft 365 e no centro de segurança [do Microsoft 365.](../office-365-security/permissions-microsoft-365-compliance-security.md)

- Saiba mais sobre como gerenciar [o acesso ao Microsoft 365 Defender](mtp-permissions.md)
- Saiba mais sobre como criar [funções personalizadas no](custom-roles.md) centro de segurança do Microsoft 365

### <a name="integrated-reports"></a>Relatórios integrados

Os relatórios também são unificados no centro de segurança do Microsoft 365. Os administradores podem começar com um relatório de segurança geral e ramificar em relatórios específicos sobre pontos de extremidade, email & colaboração. Os links aqui são gerados dinamicamente com base na configuração da carga de trabalho.

### <a name="quickly-view-your-microsoft-365-environment"></a>Exibir rapidamente seu ambiente do Microsoft 365

A **home** page mostra muitos dos cartões comuns de que as equipes de segurança precisam. A composição de cartões e dados depende da função de usuário. Como a central de segurança do Microsoft 365 usa controle de acesso baseado em função, funções diferentes verão cartões mais significativos para seus trabalhos do dia a dia.  

Essas informações rápidas ajudam você a acompanhar as atividades mais recentes em sua organização. O centro de segurança do Microsoft 365 reúne sinais de diferentes fontes para apresentar uma visão holística do seu ambiente do Microsoft 365.

Os cartões se enquadram nessas categorias:

- **Identidades**- Monitore as identidades em sua organização e acompanhe comportamentos suspeitos ou arriscados. [Saiba mais sobre a proteção de identidade.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)
- **Dados** - Ajuda a controlar a atividade do usuário que pode levar à divulgação não autorizada de dados.
- **Dispositivos** - Obter informações atualizadas sobre alertas, atividade de violação e outras ameaças em seus dispositivos.
- **Aplicativos** - Obtenha informações sobre como os aplicativos de nuvem estão sendo usados em sua organização. [Saiba mais sobre o Cloud App Security descobertos aplicativos.](https://docs.microsoft.com/cloud-app-security/discovered-apps)

## <a name="threat-analytics-with-better-data-coverage"></a>Análise de ameaças com melhor cobertura de dados
Acompanhe e responda a ameaças emergentes com a seguinte experiência integrada de análise de ameaças do Microsoft 365 Defender:

- Melhor cobertura de dados entre o Microsoft Defender para Ponto de Extremidade e o Microsoft Defender para Office 365, possibilitando o gerenciamento combinado de incidentes, investigação automática, correção e busca proativa ou reativa de ameaças em todo o domínio. 
- Detecções e mitigações relacionadas a email do Microsoft Defender para Office 365, além dos dados de ponto de extremidade já disponíveis no Microsoft Defender para Ponto de Extremidade.
- Uma exibição de incidentes relacionados a ameaças que agrega alertas em histórias de ataque de ponta a ponta no Microsoft Defender para Ponto de Extremidade e no Microsoft Defender para Office 365 para reduzir a fila de trabalho, além de simplificar e acelerar sua investigação.
- Tentativas de ataque detectadas e bloqueadas pelas soluções do Microsoft 365 Defender. Também há dados que você pode usar para impulsionar ações preventivas que atenuam o risco de mais exposição e aumentam a resiliência. 
- Design aprimorado que coloca as informações a actionable no destaque para ajudá-lo a identificar rapidamente os dados a fim de se concentrar, investigar e aproveitar os relatórios com rapidez.

## <a name="a-centralized-learning-hub"></a>Um Hub de Aprendizagem centralizado

O centro de segurança do Microsoft 365 inclui um hub de aprendizado que se direciona por recursos como o blog de segurança da Microsoft, a comunidade de segurança da Microsoft no YouTube e a documentação oficial em docs.microsoft.com.

Dentro do hub de aprendizagem, as diretrizes de colaboração de & de email (Microsoft Defender para Office 365 ou MDO) estão lado a lado com o Ponto de Extremidade (Microsoft Defender para Ponto de Extremidade ou MDE) e recursos de aprendizagem do Microsoft 365 Defender.

O hub de aprendizagem é aberto com os caminhos de aprendizagem organizados em torno de tópicos como "Como investigar usando o Microsoft 365 Defender?" e "Práticas recomendadas do Microsoft Defender para Office 365". Esta seção é atualmente controlada pelo Grupo de Produtos de segurança dentro da Microsoft. Cada caminho de aprendizagem reflete um tempo projetado que leva para passar pelos conceitos. Por exemplo, "Etapas a serem tomadas quando uma conta de usuário do Microsoft Defender para Office 365 é comprometida" é projetada para levar 8 minutos e é um aprendizado valioso em tempo real.

Depois de clicar no conteúdo, pode ser útil marcar esse site e organizar indicadores em uma pasta 'Segurança' ou 'Crítica'. Para ver todos os caminhos de aprendizagem, clique no link Mostrar tudo no painel principal.

> [!NOTE]
> Há filtros úteis na parte superior do hub de aprendizagem do centro de segurança do Microsoft 365 que permitirão que você escolha entre produtos (atualmente, Microsoft 365 Defender, Microsoft Defender para Ponto de Extremidade e Microsoft Defender para Office 365).  Observe que o número de recursos de aprendizagem para cada seção está listado, o que pode ajudar os alunos a controlar quantos recursos eles têm à mão para treinamento e aprendizagem.
>
> Junto com o filtro Produto, tópicos atuais, tipos de recursos (de vídeos a webinars), os níveis de familiaridade ou experiência com áreas de segurança, funções de segurança e recursos do produto são listados.

## <a name="send-us-your-feedback"></a>Envie-nos seus comentários

Precisamos de seus comentários. We're always looking to improve, so if there's something you'd like to see, [send us your Microsoft 365 Defender feedback](https://www.microsoft.com/videoplayer/embed/RE4K5Ci).

Você também pode deixar comentários deste artigo. Na seção "Comentários" no final em "Enviar e exibir comentários", as opções são *Este* produto ou *Esta página.*

Use o **botão Este produto** para comentários *sobre* o produto:

1. Selecione *Este produto* na parte inferior do artigo.
    1. Clique com o botão direito do mouse no botão e clique em "Abrir em uma nova guia" se quiser continuar lendo estas instruções.
2. Isso navegará para o **fórum UserVoice**.
3. Você tem duas opções:
    1. Role para baixo até a caixa de texto Como podemos melhorar a conformidade ou proteger melhor seus usuários no *Office 365?* e colar na central de segurança do *Microsoft 365.* Você pode pesquisar os resultados para uma ideia como a sua e vote nele ou usar o botão para **postar uma nova ideia.**
    1. Se você tiver certeza de que esse problema já foi relatado e quiser elevar seu perfil com um voto (ou votos), use a caixa Dar *Comentários* no lado direito do UserVoice. Pesquise o centro de segurança do *Microsoft 365,* encontre o problema e use o botão de **votação** para elevar seu status.

Use *Esta página* para comentários sobre o próprio artigo. Obrigado por seus comentários. Sua voz nos ajuda a melhorar os produtos.

### <a name="explore-what-the-security-center-has-to-offer"></a>Explore o que a central de segurança tem a oferecer

Continue explorando os recursos no centro de segurança do Microsoft 365:

- [Gerenciar incidentes e alertas](manage-incidents.md)
- [Acompanhar e responder a ameaças emergentes com a análise de ameaças](threat-analytics.md)
- [A Central de Ações](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [Busca por ameaças em dispositivos, emails, aplicativos e identidades](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-query-emails-devices)
- [Regras de detecção personalizadas](https://docs.microsoft.com/microsoft-365/security/mtp/custom-detection-rules)
- [Alertas & colaboração de email](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies)
- [Criar uma simulação de ataque de phishing](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training) [e criar uma carga para treinar suas equipes](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training-payloads)
 
### <a name="related-information"></a>Informações relacionadas
- [Centro de segurança do Microsoft 365](overview-security-center.md)
- [Microsoft Defender para Office 365 no centro de segurança do Microsoft 365](microsoft-365-security-center-mdo.md)
- [Microsoft Defender para Ponto de Extremidade no centro de segurança do Microsoft 365](microsoft-365-security-center-mde.md)
- [Redirecionando contas do Microsoft Defender para o Ponto de Extremidade para a central de segurança do Microsoft 365](microsoft-365-security-mde-redirection.md)
