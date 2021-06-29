---
title: Microsoft 365 Defender visão geral, combinando MDO, MDE, MDI e MCAS
description: Vantagens no Microsoft 365 Defender, combinando o Microsoft Defender para Office 365 (MDO) e o Microsoft Defender para Ponto de Extremidade (MDE), com o Microsoft Defender for Identity (MDI) e o Microsoft Cloud App Security (MCAS). Este artigo descreve Microsoft 365 Defender para administradores.
keywords: segurança, malware, Microsoft 365, M365, central de segurança, monitor, relatório, identidades, dados, dispositivos, aplicativos
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.date: 04/21/2021
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
ms.openlocfilehash: 8e37572b07c6d81abc531e204a8cb060f1f6402c
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194980"
---
# <a name="microsoft-365-defender-overview"></a>Microsoft 365 Defender visão geral

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)

> Quer experimentar o Microsoft 365 Defender? Você pode [avaliá-lo em um ambiente de laboratório](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) ou [executar seu projeto piloto em produção](m365d-pilot.md?ocid=cx-evalpilot).

**Microsoft 365 Defender** ( ) combina proteção, detecção, investigação e resposta [https://security.microsoft.com](https://security.microsoft.com) a *emails,* colaboração, identidade e ameaças de dispositivo, em um portal central.   

Microsoft 365 Defender reúne funcionalidades de portais de segurança da Microsoft existentes, como o Central de Segurança do Microsoft Defender e o centro de conformidade Office 365 segurança & segurança. O centro de segurança enfatiza o acesso rápido a informações, layouts mais simples e a aproveitamento de informações relacionadas para facilitar o uso. Este centro inclui:

- **[Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)** O Microsoft Defender para Office 365 ajuda as organizações a proteger sua empresa com um conjunto de recursos de prevenção, detecção, investigação e busca para proteger o email e Office 365 recursos.
- **[O Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** oferece proteção preventiva, detecção pós-violação, investigação automatizada e resposta para dispositivos em sua organização.
- **[Microsoft 365 Defender](microsoft-365-defender.md)** faz parte da solução XDR *(Detecção* e Resposta Estendida) da Microsoft que aproveita o portfólio de segurança do Microsoft 365 para analisar automaticamente os dados de ameaças entre domínios e criar uma imagem de um ataque em um único painel.

Se você precisar de informações sobre o que foi alterado do centro de conformidade Office 365 segurança & ou do Central de Segurança do Microsoft Defender, consulte:

- [Microsoft Defender para Office 365 no Microsoft 365 Defender](microsoft-365-security-center-mdo.md)
- [Microsoft Defender para Ponto de Extremidade no Microsoft 365 Defender](microsoft-365-security-center-mde.md)

> [!NOTE]
> O Microsoft 365 de segurança usa e impõe o acesso baseado em funções existentes e move cada modelo de segurança para o portal unificado. Cada carga de trabalho convergida tem seu próprio acesso baseado em funções. As funções já nos produtos serão convergidas para o portal Microsoft 365 segurança, automaticamente. No entanto, as funções e permissões do MCAS ainda serão tratadas no MCAS.

## <a name="what-to-expect"></a>O que esperar

Todo o conteúdo de segurança que você usa no Centro de Conformidade e Segurança do Office 365 (protection.office.com) e no Centro de Segurança do Microsoft Defender (securitycenter.microsoft.com) agora pode ser encontrado no Microsoft 365 Defender *.*

Microsoft 365 Defender ajuda as equipes de segurança a investigar e responder a ataques trazendo sinais de cargas de trabalho diferentes para um conjunto de experiências unificadas para:

- Incidentes & alertas
- Busca
- Central de ações
- Análise de ameaças

Microsoft 365 Defender enfatiza a *unidade,* a clareza e as metas comuns à medida que mescla o Microsoft Defender para o Office 365 e o Microsoft Defender para o Ponto de Extremidade. A mesclagem foi baseada nas prioridades listadas abaixo e feita sem sacrificar os recursos que cada pacote de segurança trouxe para a combinação de:

- Blocos de construção comuns
- Terminologia comum
- Entidades comuns
- Paridade de recursos com outras cargas de trabalho

> [!NOTE]
> Microsoft 365 Defender estará acessível sem a necessidade de os clientes tomarem etapas de migração ou comprarem uma nova licença. Por exemplo, esse novo portal estará acessível aos administradores com uma assinatura E3, assim como para aqueles com o Microsoft Defender para Office 365 Plano 1 e Plano 2; no entanto, Proteção do Exchange Online, ou o Defender para Office 365 plano 1, os clientes verão apenas os recursos de segurança que sua licença de assinatura oferece suporte. O objetivo do novo centro é centralizar a segurança.

## <a name="unified-investigations"></a>Investigações unificadas

Convergir centros de segurança cria um único local para investigar incidentes de segurança em Microsoft 365. Um exemplo principal é **Incidentes** em **Incidentes & alertas** sobre o início rápido do Microsoft 365 Defender.

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="A página Incidentes no Microsoft 365 Defender.":::

Selecionar um nome de incidente exibe uma página que demonstra o valor dos centros de segurança convergentes.

:::image type="content" source="../../media/converged-incident-info-3.png" alt-text="Exemplo da página Resumo de um incidente em Microsoft 365 Defender":::

<!--
![Example of the Summary page for an incident in Microsoft 365 Defender](../../media/converged-incident-info-3.png)
--> 

Na parte superior de uma página de incidentes, você verá as guias **Resumo,** **Alertas, Dispositivos,** **Usuários,** Caixas de **Correio,** **Investigações** **e** Evidências. Selecione essas guias para obter informações mais detalhadas. Por exemplo,  a guia Usuários exibe informações para usuários de cargas de trabalho convergentes (Microsoft Defender para Ponto de Extremidade, Microsoft Defender para Identidade e Microsoft Cloud App Security) e um intervalo de fontes, como serviços de domínio do Active Directory local (AD DS), Azure Active Directory (Azure AD) e provedores de identidade de terceiros. Para obter mais informações, consulte [investigar usuários](investigate-users.md).

Aproveite o tempo para revisar os incidentes em seu ambiente, fazer uma análise dessas guias e praticar a criação de uma compreensão de como acessar as informações fornecidas para incidentes para diferentes tipos de ameaças.

Para obter mais informações, [consulte incidentes em Microsoft 365 Defender](incidents-overview.md).

## <a name="improved-processes"></a>Processos aprimorados

Controles comuns e conteúdo aparecem no mesmo local ou são condensados em um feed de dados, facilitando a encontrar. Por exemplo, configurações unificadas.

### <a name="unified-settings"></a>Configurações unificadas

![clicou em "Funções" e abriu a página Configurações, que inclui configurações gerais, Permissões, APIs e Regras. Abra Permissões e, em seguida, Funções. Mostra todas as funções](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>Permissões & funções

![Permissões & página Funções mostrando funções de pontos de extremidade & grupos, funções e grupos de dispositivos.](../../media/converged-roles-5.png)

 O acesso Microsoft 365 Defender é configurado com funções Azure Active Directory globais ou usando funções personalizadas. Para Defender para Ponto de Extremidade, consulte [Atribuir acesso do usuário a Central de Segurança do Microsoft Defender](/microsoft-365/security/defender-endpoint/assign-portal-access). Para Defender para Office 365, consulte [Permissões no Centro de conformidade do Microsoft 365 e Microsoft 365 Defender](../office-365-security/permissions-microsoft-365-compliance-security.md).

- Saiba mais sobre como gerenciar [o acesso ao Microsoft 365 Defender](m365d-permissions.md)
- Saiba mais sobre como criar [funções personalizadas](custom-roles.md) no Microsoft 365 Defender

> [!NOTE]
> O Microsoft Defender for Endpoint no Microsoft 365 Defender dá suporte à concessão de acesso a [MSSPs (provedores](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) de serviços de segurança gerenciados) da mesma forma que o acesso é concedido no Centro de segurança do [Microsoft Defender.](./mssp-access.md)

### <a name="integrated-reports"></a>Relatórios integrados

Os relatórios também são unificados Microsoft 365 Defender. Os administradores podem começar com um relatório de segurança geral e ramificar em relatórios específicos sobre pontos de extremidade, email & colaboração. Os links aqui são gerados dinamicamente com base na configuração da carga de trabalho.

### <a name="quickly-view-your-microsoft-365-environment"></a>Exibir rapidamente seu ambiente Microsoft 365 ambiente

A **home** page mostra muitos dos cartões comuns que as equipes de segurança precisam. A composição de cartões e dados depende da função de usuário. Como Microsoft 365 central de segurança usa controle de acesso baseado em função, diferentes funções verão cartões que são mais significativos para seus trabalhos do dia a dia.  

Essas informações rápidas ajudam você a acompanhar as atividades mais recentes em sua organização. Microsoft 365 Defender reúne sinais de fontes diferentes para apresentar uma visão holística do seu ambiente Microsoft 365 ambiente.

As cartas se enquadram nessas categorias:

- **Identidades**- Monitore as identidades em sua organização e acompanhe comportamentos suspeitos ou arriscados. [Saiba mais sobre a proteção de identidade.](/azure/active-directory/identity-protection/overview-identity-protection)
- **Dados** - Ajude a controlar a atividade do usuário que pode levar à divulgação de dados não autorizados.
- **Dispositivos** - Obter informações atualizadas sobre alertas, atividades de violação e outras ameaças em seus dispositivos.
- **Aplicativos** - Obtenha informações sobre como os aplicativos de nuvem estão sendo usados em sua organização. [Saiba mais sobre Cloud App Security aplicativos descobertos.](/cloud-app-security/discovered-apps)

## <a name="threat-analytics-with-better-data-coverage"></a>Análise de ameaças com melhor cobertura de dados
Acompanhe e responda a ameaças emergentes com a seguinte experiência integrada Microsoft 365 Defender análise de ameaças:

- Melhor cobertura de dados entre o Microsoft Defender para Ponto de Extremidade e o Microsoft Defender para Office 365, tornando possível o gerenciamento combinado de incidentes, investigação automática, correção e busca proativa ou reativa de ameaças entre domínios. 
- Detecções e mitigações relacionadas a email do Microsoft Defender para Office 365, além dos dados de ponto de extremidade já disponíveis do Microsoft Defender para Ponto de Extremidade.
- Uma exibição de incidentes relacionados a ameaças que agregam alertas em histórias de ataque de ponta a ponta no Microsoft Defender para Ponto de Extremidade e no Microsoft Defender para Office 365 para reduzir a fila de trabalho, bem como simplificar e acelerar sua investigação.
- Tentativas de ataque detectadas e bloqueadas por Microsoft 365 Defender soluções. Também há dados que você pode usar para impulsionar ações preventivas que atenuam o risco de exposição posterior e aumentam a resiliência. 
- Design aprimorado que coloca informações a ações em destaque para ajudá-lo a identificar rapidamente os dados para se concentrar, investigar e aproveitar com urgência os relatórios.

## <a name="a-centralized-learning-hub"></a>Um Hub Learning centralizado

Microsoft 365 centro de segurança inclui um hub de aprendizado que oferece orientações oficiais de recursos como o blog de segurança da Microsoft, a comunidade de segurança da Microsoft no YouTube e a documentação oficial no docs.microsoft.com.

Dentro do hub de aprendizagem, as diretrizes de colaboração de email & (Microsoft Defender para Office 365) estão lado a lado com o Ponto de Extremidade (Microsoft Defender para Ponto de Extremidade) e Microsoft 365 Defender recursos de aprendizagem.

O hub de aprendizagem é aberto Learning caminhos organizados em torno de tópicos como "Como investigar o uso Microsoft 365 Defender?" e "Microsoft Defender para Office 365 Práticas Recomendadas". Esta seção atualmente tem a curadoria do Grupo de Produtos de segurança dentro da Microsoft. Cada Learning caminho reflete um tempo projetado que leva para passar pelos conceitos. Por exemplo, "Etapas a serem tomadas quando uma conta de usuário do Microsoft Defender para Office 365 está comprometida" é projetada para levar 8 minutos e é um aprendizado valioso em tempo real.

Depois de clicar no conteúdo, pode ser útil marcar esse site e organizar indicadores em uma pasta "Segurança" ou "Crítico". Para ver todos os Learning, clique no link Mostrar tudo no painel principal.

> [!NOTE]
> Há **filtros** úteis na parte superior do hub de aprendizado Microsoft 365 Defender que permitirão que você escolha entre produtos (atualmente Microsoft 365 Defender, Microsoft Defender para Ponto de Extremidade e Microsoft Defender para Office 365). Observe que o número de recursos de aprendizagem para cada seção está listado, o que pode ajudar os alunos a controlar quantos recursos eles têm em mãos para treinamento e aprendizado.
>
> Junto com o filtro Produto, tópicos atuais, tipos de recursos (de vídeos a webinars), níveis de familiaridade ou experiência com áreas de segurança, funções de segurança e recursos do produto são listados.

> [!TIP]
> Há muitas outras oportunidades de aprendizado no [Microsoft Learn](/e/learn/). Você encontrará treinamentos de certificação como [o Curso MS-500T02-A: Implementando](/learn/certifications/courses/ms-500t02)Microsoft 365 Proteção contra Ameaças.

## <a name="send-us-your-feedback"></a>Envie seus comentários

Precisamos de seus comentários. Estamos sempre procurando melhorar, portanto, se houver algo que você gostaria de ver, [envie-nos](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)seus Microsoft 365 Defender comentários.

Você também pode deixar comentários deste artigo. Na seção 'Comentários' no final em 'Enviar e exibir comentários', as opções são Este produto *ou* *Esta página*.

Use o **botão Este produto** para comentários *do* produto:

1. Selecione *Este produto* na parte inferior do artigo.
    1. Clique com o botão direito do mouse e "Abra em uma nova guia" se quiser continuar lendo essas instruções.
2. Isso navegará até o **fórum UserVoice**.
3. Você tem duas opções:
    1. Role para baixo até a caixa de texto Como podemos melhorar a conformidade ou proteger melhor seus usuários *em Office 365?* e colar em *Microsoft 365 Defender*. Você pode pesquisar os resultados de uma ideia como a sua e in-locar ou usar o botão para **Postar uma nova ideia.**
    1. Se você tiver certeza de que esse problema já foi relatado e quiser elevar seu perfil com um voto (ou votos), use a caixa Dar *comentários* no lado direito do UserVoice. *Pesquise Microsoft 365 Defender*, encontre o problema e use o botão **de votação** para elevar seu status.

Use *Esta página para* comentários sobre o próprio artigo. Obrigado por seus comentários. Sua voz nos ajuda a melhorar os produtos.

### <a name="explore-what-the-security-center-has-to-offer"></a>Explorar o que o centro de segurança tem a oferecer

Continue explorando os recursos e recursos em Microsoft 365 Defender:

- [Gerenciar incidentes e alertas](manage-incidents.md)
- [Rastrear e responder a ameaças emergentes com análise de ameaças](threat-analytics.md)
- [A Central de Ações](m365d-action-center.md)
- [Buscar ameaças em dispositivos, e-mails, aplicativos e identidades](./advanced-hunting-query-emails-devices.md)
- [Regras de detecção personalizadas](./custom-detection-rules.md)
- [Alertas de email e colaboração](../../compliance/alert-policies.md#default-alert-policies)
- [Criar uma simulação de ataque de phishing](../office-365-security/attack-simulation-training.md) [e criar uma carga para treinar suas equipes](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)
 
### <a name="related-information"></a>Informações relacionadas
- [Microsoft Defender para Office 365 no Microsoft 365 Defender](microsoft-365-security-center-mdo.md)
- [Microsoft Defender para Ponto de Extremidade no Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Redirecionando contas do Microsoft Defender para o Ponto de Extremidade para Microsoft 365 Defender](microsoft-365-security-mde-redirection.md)