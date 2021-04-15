---
title: Visão geral do Centro de segurança do Microsoft 365
description: Vantagens no centro de segurança do Microsoft 365, combinando o Microsoft Defender para Office 365 (MDO) e o Microsoft Defender para Ponto de Extremidade (MDE), com o Microsoft Defender for Identity (MDI) e o Microsoft Cloud App Security (MCAS). Este artigo descreve os avanços do centro de segurança do Microsoft 365 para administradores.
keywords: segurança, malware, Microsoft 365, M365, central de segurança, monitor, relatório, identidades, dados, dispositivos, aplicativos
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.date: 04/07/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: d89e5dc29bfe7f980d40a9a5b139884750a966bc
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760009"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a>Visão geral da central de segurança unificada do Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)

> Quer experimentar o Microsoft 365 Defender? Você pode [avaliá-lo em um ambiente de laboratório](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) ou [executar seu projeto piloto em produção](m365d-pilot.md?ocid=cx-evalpilot).

O centro de segurança aprimorado do **Microsoft 365** ( ) combina proteção, detecção, investigação e resposta [https://security.microsoft.com](https://security.microsoft.com) a *emails,* colaboração,  identidade e ameaças de dispositivo, em um portal central. 

O Centro de segurança do Microsoft 365 reúne funcionalidades de portais de segurança da Microsoft existentes, como o Centro de Segurança do Microsoft Defender e o Centro de Conformidade e Segurança & do Office 365. O centro de segurança enfatiza o acesso rápido a informações, layouts mais simples e a aproveitamento de informações relacionadas para facilitar o uso. Este centro inclui:

- **[Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)** O Microsoft Defender para Office 365 ajuda as organizações a proteger sua empresa com um conjunto de recursos de prevenção, detecção, investigação e busca para proteger o email e os recursos do Office 365.
- **[O Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** oferece proteção preventiva, detecção pós-violação, investigação automatizada e resposta para dispositivos em sua organização.
- **[O Microsoft 365 Defender](microsoft-365-defender.md)** faz parte da solução XDR *(Detecção* Estendida e Resposta) da Microsoft que aproveita o portfólio de segurança do Microsoft 365 para analisar automaticamente os dados de ameaças entre domínios e criar uma imagem de um ataque em um único painel.

Se você precisar de informações sobre o que foi alterado do Centro de Conformidade e Segurança do Office 365 & ou do Centro de Segurança do Microsoft Defender, consulte:

- [Microsoft Defender para Office 365 no Centro de segurança do Microsoft 365](microsoft-365-security-center-mdo.md)
- [Microsoft Defender para ponto de extremidade no Centro de segurança do Microsoft 365](microsoft-365-security-center-mde.md)

## <a name="what-to-expect"></a>O que esperar

Todo o conteúdo de segurança que você usa no Centro de Conformidade e Segurança do Office 365 (protection.office.com) e no Centro de Segurança do Microsoft Defender (securitycenter.microsoft.com) agora pode ser encontrado no centro de segurança do *Microsoft 365.*

O Centro de segurança do Microsoft 365 ajuda as equipes de segurança a investigar e responder a ataques trazendo sinais de cargas de trabalho diferentes para um conjunto de experiências unificadas para:

- Incidentes & alertas
- Busca
- Central de Ações
- Análise de ameaças

O Centro de segurança do Microsoft 365 enfatiza a *unidade,* a clareza e as metas comuns à medida que mescla o Microsoft Defender para o Office 365 e o Microsoft Defender para o Ponto de Extremidade. A mesclagem foi baseada nas prioridades listadas abaixo e feita sem sacrificar os recursos que cada pacote de segurança trouxe para a combinação de:

- Blocos de construção comuns
- Terminologia comum
- Entidades comuns
- Paridade de recursos com outras cargas de trabalho

## <a name="unified-investigations"></a>Investigações unificadas

Convergir centros de segurança cria um único local para investigar incidentes de segurança no Microsoft 365. Um exemplo principal é **Incidentes** em **Incidentes & alertas** sobre o início rápido do centro de segurança do Microsoft 365.

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="A página Incidentes no centro de segurança do Microsoft 365.":::

Selecionar um nome de incidente exibe uma página que demonstra o valor dos centros de segurança convergentes.

:::image type="content" source="../../media/converged-incident-info-3.png" alt-text="Exemplo da página Resumo de um incidente no centro de segurança do Microsoft 365":::

<!--
![Example of the Summary page for an incident in the Microsoft 365 security center](../../media/converged-incident-info-3.png)
--> 

Na parte superior de uma página de incidentes, você verá as guias **Resumo,** **Alertas, Dispositivos,** **Usuários,** Caixas de **Correio,** **Investigações** **e** Evidências. Selecione essas guias para obter informações mais detalhadas. Por exemplo,  a guia Usuários exibe informações para usuários de cargas de trabalho convergentes (Microsoft Defender para Ponto de Extremidade, Microsoft Defender para Identidade e Segurança do Microsoft Cloud App) e um intervalo de fontes, como serviços de domínio do Active Directory local (AD DS), Azure Active Directory (Azure AD) e provedores de identidade de terceiros. Para obter mais informações, consulte [investigar usuários](investigate-users.md).

Aproveite o tempo para revisar os incidentes em seu ambiente, fazer uma análise dessas guias e praticar a criação de uma compreensão de como acessar as informações fornecidas para incidentes para diferentes tipos de ameaças.

Para obter mais informações, consulte incidentes no centro de segurança [do Microsoft 365.](incidents-overview.md)

## <a name="improved-processes"></a>Processos aprimorados

Controles comuns e conteúdo aparecem no mesmo local ou são condensados em um feed de dados, facilitando a encontrar. Por exemplo, configurações unificadas.

### <a name="unified-settings"></a>Configurações unificadas

![clicou em "Funções" e abriu a página Configurações, que inclui configurações gerais, Permissões, APIs e Regras. Abra Permissões e, em seguida, Funções. Mostra todas as funções](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>Permissões & funções

![Permissões & página Funções mostrando funções de pontos de extremidade & grupos, funções e grupos de dispositivos.](../../media/converged-roles-5.png)

 O access the Microsoft 365 security center is configured with Azure Active Directory global roles or by using custom roles. Para Defender para Ponto de Extremidade, consulte [Atribuir acesso do usuário ao Centro de Segurança do Microsoft Defender.](/microsoft-365/security/defender-endpoint/assign-portal-access) Para o Defender para Office 365, consulte Permissões no centro de conformidade do Microsoft 365 e no Centro de segurança [do Microsoft 365.](../office-365-security/permissions-microsoft-365-compliance-security.md)

- Saiba mais sobre como gerenciar [o acesso ao Microsoft 365 Defender](m365d-permissions.md)
- Saiba mais sobre como criar [funções personalizadas](custom-roles.md) no Centro de segurança do Microsoft 365

> [!NOTE]
> O Microsoft Defender for Endpoint no centro de segurança do Microsoft 365 dá suporte à concessão de acesso a [MSSPs (provedores](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) de serviços de segurança gerenciados) da mesma forma que o acesso é concedido no centro de segurança do [Microsoft Defender.](./mssp-access.md)

### <a name="integrated-reports"></a>Relatórios integrados

Os relatórios também são unificados no centro de segurança do Microsoft 365. Os administradores podem começar com um relatório de segurança geral e ramificar em relatórios específicos sobre pontos de extremidade, email & colaboração. Os links aqui são gerados dinamicamente com base na configuração da carga de trabalho.

### <a name="quickly-view-your-microsoft-365-environment"></a>Exibir rapidamente seu ambiente do Microsoft 365

A **home** page mostra muitos dos cartões comuns que as equipes de segurança precisam. A composição de cartões e dados depende da função de usuário. Como o centro de segurança do Microsoft 365 usa controle de acesso baseado em função, funções diferentes verão cartões que são mais significativos para seus trabalhos do dia a dia.  

Essas informações rápidas ajudam você a acompanhar as atividades mais recentes em sua organização. O Centro de segurança do Microsoft 365 reúne sinais de fontes diferentes para apresentar uma visão holística do seu ambiente do Microsoft 365.

As cartas se enquadram nessas categorias:

- **Identidades**- Monitore as identidades em sua organização e acompanhe comportamentos suspeitos ou arriscados. [Saiba mais sobre a proteção de identidade.](/azure/active-directory/identity-protection/overview-identity-protection)
- **Dados** - Ajude a controlar a atividade do usuário que pode levar à divulgação de dados não autorizados.
- **Dispositivos** - Obter informações atualizadas sobre alertas, atividades de violação e outras ameaças em seus dispositivos.
- **Aplicativos** - Obtenha informações sobre como os aplicativos de nuvem estão sendo usados em sua organização. [Saiba mais sobre o Cloud App Security descoberto aplicativos](/cloud-app-security/discovered-apps).

## <a name="threat-analytics-with-better-data-coverage"></a>Análise de ameaças com melhor cobertura de dados
Acompanhe e responda a ameaças emergentes com a seguinte experiência integrada de análise de ameaças do Microsoft 365 Defender:

- Melhor cobertura de dados entre o Microsoft Defender para Ponto de Extremidade e o Microsoft Defender para Office 365, tornando possível o gerenciamento combinado de incidentes, investigação automática, correção e busca proativa ou reativa de ameaças entre domínios. 
- Detecções e mitigações relacionadas a email do Microsoft Defender para Office 365, além dos dados de ponto de extremidade já disponíveis do Microsoft Defender para Ponto de Extremidade.
- Uma exibição de incidentes relacionados a ameaças que agregam alertas em histórias de ataque de ponta a ponta no Microsoft Defender para Ponto de Extremidade e no Microsoft Defender para Office 365 para reduzir a fila de trabalho, bem como simplificar e acelerar sua investigação.
- Tentativas de ataque detectadas e bloqueadas pelas soluções do Microsoft 365 Defender. Também há dados que você pode usar para impulsionar ações preventivas que atenuam o risco de exposição posterior e aumentam a resiliência. 
- Design aprimorado que coloca informações a ações em destaque para ajudá-lo a identificar rapidamente os dados para se concentrar, investigar e aproveitar com urgência os relatórios.

## <a name="a-centralized-learning-hub"></a>Um Hub de Aprendizagem centralizado

O Centro de segurança do Microsoft 365 inclui um hub de aprendizado que oferece orientações oficiais de recursos como o blog de segurança da Microsoft, a comunidade de segurança da Microsoft no YouTube e a documentação oficial no docs.microsoft.com.

Dentro do hub de aprendizagem, as diretrizes de Colaboração do Email & (Microsoft Defender para Office 365 ou MDO) estão lado a lado com o Ponto de Extremidade (Microsoft Defender para Ponto de Extremidade ou MDE) e recursos de aprendizagem do Microsoft 365 Defender.

O hub de aprendizagem é aberto com caminhos de aprendizagem organizados em torno de tópicos como "Como investigar o uso do Microsoft 365 Defender?" e "Práticas Recomendadas do Microsoft Defender para Office 365". Esta seção atualmente tem a curadoria do Grupo de Produtos de segurança dentro da Microsoft. Cada caminho de Aprendizagem reflete um tempo projetado que leva para passar pelos conceitos. Por exemplo, "Etapas a serem tomadas quando uma conta de usuário do Microsoft Defender para Office 365 é comprometida" é projetada para levar 8 minutos e é um aprendizado valioso em tempo real.

Depois de clicar no conteúdo, pode ser útil marcar esse site e organizar indicadores em uma pasta "Segurança" ou "Crítico". Para ver todos os caminhos de aprendizagem, clique no link Mostrar tudo no painel principal.

> [!NOTE]
> Há **filtros** úteis na parte superior do hub de aprendizado do centro de segurança do Microsoft 365 que permitem escolher entre produtos (atualmente, o Microsoft 365 Defender, o Microsoft Defender para o Ponto de Extremidade e o Microsoft Defender para Office 365). Observe que o número de recursos de aprendizagem para cada seção está listado, o que pode ajudar os alunos a controlar quantos recursos eles têm em mãos para treinamento e aprendizado.
>
> Junto com o filtro Produto, tópicos atuais, tipos de recursos (de vídeos a webinars), níveis de familiaridade ou experiência com áreas de segurança, funções de segurança e recursos do produto são listados.

## <a name="send-us-your-feedback"></a>Envie seus comentários

Precisamos de seus comentários. Estamos sempre procurando melhorar, portanto, se houver algo que você gostaria de ver, envie-nos seus comentários do [Microsoft 365 Defender.](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)

Você também pode deixar comentários deste artigo. Na seção 'Comentários' no final em 'Enviar e exibir comentários', as opções são Este produto *ou* *Esta página*.

Use o **botão Este produto** para comentários *do* produto:

1. Selecione *Este produto* na parte inferior do artigo.
    1. Clique com o botão direito do mouse e "Abra em uma nova guia" se quiser continuar lendo essas instruções.
2. Isso navegará até o **fórum UserVoice**.
3. Você tem duas opções:
    1. Role até a caixa de texto Como melhorar a conformidade ou proteger melhor seus usuários no *Office 365?* e colar no Centro de segurança *do Microsoft 365.* Você pode pesquisar os resultados de uma ideia como a sua e in-locar ou usar o botão para **Postar uma nova ideia.**
    1. Se você tiver certeza de que esse problema já foi relatado e quiser elevar seu perfil com um voto (ou votos), use a caixa Dar *comentários* no lado direito do UserVoice. Pesquise o Centro de Segurança do *Microsoft 365*, **localmente o problema e use** o botão de votação para aumentar seu status.

Use *Esta página para* comentários sobre o próprio artigo. Obrigado por seus comentários. Sua voz nos ajuda a melhorar os produtos.

### <a name="explore-what-the-security-center-has-to-offer"></a>Explorar o que o centro de segurança tem a oferecer

Continue explorando os recursos e recursos no centro de segurança do Microsoft 365:

- [Gerenciar incidentes e alertas](manage-incidents.md)
- [Rastrear e responder a ameaças emergentes com análise de ameaças](threat-analytics.md)
- [A Central de Ações](m365d-action-center.md)
- [Buscar ameaças em dispositivos, e-mails, aplicativos e identidades](./advanced-hunting-query-emails-devices.md)
- [Regras de detecção personalizadas](./custom-detection-rules.md)
- [Alertas de email e colaboração](../../compliance/alert-policies.md#default-alert-policies)
- [Criar uma simulação de ataque de phishing](../office-365-security/attack-simulation-training.md) [e criar uma carga para treinar suas equipes](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)
 
### <a name="related-information"></a>Informações relacionadas
- [Centro de segurança do Microsoft 365](overview-security-center.md)
- [Microsoft Defender para Office 365 no Centro de segurança do Microsoft 365](microsoft-365-security-center-mdo.md)
- [Microsoft Defender para Ponto de Extremidade no centro de segurança do Microsoft 365](microsoft-365-security-center-mde.md)
- [Redirecionando contas do Microsoft Defender para o Ponto de Extremidade para o centro de segurança do Microsoft 365](microsoft-365-security-mde-redirection.md)