---
title: Microsoft Defender para Office 365 no Microsoft 365 Defender
description: Saiba mais sobre as alterações do centro Office 365 Segurança e Conformidade para Microsoft 365 Defender.
keywords: Microsoft 365 segurança, Iniciando com Microsoft 365 Defender, Microsoft Defender para Office 365, Microsoft Defender para Ponto de Extremidade, MDO, MDE, painel único de vidro, novo portal de segurança, novo portal de segurança do Defender
ms.date: 02/21/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.prod: m365-security
ms.technology: m365d
ms.openlocfilehash: 15b1b152966c9c09bf77bea15b9b651f739c3566
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028950"
---
# <a name="microsoft-defender-for-office-365-in-microsoft-365-defender"></a>Microsoft Defender para Office 365 no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Obter o Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)

## <a name="quick-reference"></a>Referência rápida

A tabela a seguir lista as alterações na navegação entre Office 365 o Centro de Conformidade & Segurança e Microsoft 365 Defender.

<br>

****

|[Office 365 Conformidade & segurança](https://protection.office.com)|[Microsoft 365 Defender](https://security.microsoft.com)|[Centro de conformidade do Microsoft 365](https://compliance.microsoft.com/homepage)|[Centro de administração do Exchange](https://admin.exchange.microsoft.com/#/)|
|---|---|---|---|
|Alertas|<ul><li>[Políticas de alerta](https://security.microsoft.com/alertpolicies)</li><li>[Incidentes & alertas](https://security.microsoft.com/alerts)</li></ul>|[Página Alertas](https://compliance.microsoft.com/homepage)||
|Classificação||Consulte [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com/homepage)||
|Prevenção contra perda de dados||Consulte [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com/homepage)||
|Gerenciamento de registros||Consulte [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com/homepage)||
|Governança de informações||Consulte [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com/homepage)||
|Gerenciamento de ameaças|[Colaboração & email](https://security.microsoft.com/homepage)|||
|Permissões|[Permissões & funções](https://security.microsoft.com/emailandcollabpermissions)|Consulte [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com/homepage)||
|Fluxo de mensagens|||Consulte [Exchange centro de administração](https://admin.exchange.microsoft.com/#/)|
|Privacidade de dados||Consulte [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com/homepage)||
|Pesquisar|[Auditoria](https://security.microsoft.com/auditlogsearch?viewid=Async%20Search)|Pesquisa (pesquisa de conteúdo)||
|Relatórios|[Relatório](https://security.microsoft.com/emailandcollabreport)|||
|Garantia do serviço||Consulte [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com/homepage)||
|Supervisão||Consulte [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com/homepage)||
|Descoberta eletrônica||Consulte [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com/homepage)||

[Microsoft 365 Defender](./overview-security-center.md) at combina os recursos de segurança de portais de segurança existentes da Microsoft, incluindo o Centro de Conformidade Office 365 <https://security.microsoft.com> Segurança & Segurança. Este centro aprimorado ajuda as equipes de segurança a proteger suas organizações de ameaças de maneira mais eficaz e eficiente.

Se você estiver familiarizado com o portal Office 365 segurança e conformidade (protection.office.com), este artigo descreve algumas das alterações e melhorias no Microsoft 365 Defender.

Saiba mais sobre os benefícios: [Visão geral do Microsoft 365 Defender](overview-security-center.md)

Se você estiver procurando itens relacionados à conformidade, visite o [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com/homepage).

## <a name="new-and-improved-capabilities"></a>Recursos novos e aprimorados

O painel de navegação esquerdo ou barra de início rápido parecerá familiar a você. No entanto, existem alguns elementos novos e atualizados neste centro de segurança.

Com a solução Microsoft 365 Defender unificada, você pode unir os sinais de ameaça e determinar o escopo completo e o impacto da ameaça e como ela está afetando a organização no momento.

:::image type="content" source="../../media/M365-defender-converge-experience.png" alt-text="Imagem da Microsoft 365 Defender convergida":::

O Defender para Office 365 protege sua organização contra ameaças mal-intencionadas colocadas por mensagens de email, links (URLs) e ferramentas de colaboração.

:::image type="content" source="../../media/Defender-for-O365.png" alt-text="Imagem do Defender para Office 365":::

### <a name="incidents-and-alerts"></a>Incidentes e alertas

Reúne o gerenciamento de alertas e incidentes em seu email, dispositivos e identidades. Agora, os alertas estão disponíveis no nó de Investigação e ajudam a dar uma visão mais ampla de um ataque. A página de alerta fornece contexto total ao alerta, combinando os sinais de ataque para criar uma história detalhada. Anteriormente, os alertas eram específicos para cargas de trabalho diferentes. Agora, uma experiência nova e unificada reúne uma exibição consistente de alertas em todas as cargas de trabalho. Você pode rapidamente fazer a triagem, investigar e tomar medidas eficazes.

- [Saiba mais sobre Investigações](incidents-overview.md)
- [Saiba mais sobre gerenciar alertas](/windows/security/threat-protection/microsoft-defender-atp/review-alerts)

![A barra de início rápido de Alertas e Ações](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a>Busca

Procure proativamente por ameaças e atividades mal-intencionadas em seus pontos de extremidade, caixas de correio do Office 365 e muito mais usando as [consultas de busca avançada](advanced-hunting-overview.md). Essas consultas poderosas podem ser usadas para localizar e analisar os indicadores de ameaça e entidades para possíveis ameaças e ameaças conhecidas.

[As regras de detecção personalizadas](/windows/security/threat-protection/microsoft-defender-atp/custom-detection-rules) podem ser criadas a partir de consultas avançadas de busca para ajudá-lo a observar proativamente eventos que podem indicar a atividade de violação e dispositivos configurados incorretamente.

Aqui está um [exemplo de busca avançada](advanced-hunting-example.md) no Microsoft Defender para Office 365.  

### <a name="action-center"></a>Central de ações

A Central de ações mostra a você as investigações criadas pelos recursos de investigação e resposta automatizadas. Esta autorrecuperação automatizada no Microsoft 365 Defender podem ajudar as equipes de segurança respondendo automaticamente a eventos específicos.

Saiba mais sobre [a Central de Ações](m365d-action-center.md).

#### <a name="threat-analytics"></a>Análise de Ameaças

Obtenha inteligência contra ameaças de pesquisadores especialistas em Segurança da Microsoft. A Análise de Ameaças ajuda as equipes de segurança a serem mais eficientes ao enfrentar ameaças emergentes. A Análise de Ameaças inclui:

- Detecções e mitigações relacionadas ao email do Microsoft Defender para Office 365. Isso é uma adição aos dados de ponto de extremidade já disponíveis no Microsoft Defender para Ponto de Extremidade.
- Exibição de incidentes relacionada às ameaças.
- Experiência avançada para rapidamente identificar e usar informações acionáveis nos relatórios.

Você pode acessar a análise de ameaças na barra de navegação superior esquerda no Microsoft 365 Defender ou em um cartão de painel dedicado que mostra as principais ameaças para sua organização.

Saiba mais sobre como rastrear e responder a ameaças [emergentes com análise de ameaças.](./threat-analytics.md)

### <a name="email--collaboration"></a>Email e colaboração

Acompanhe e investigue ameaças ao email de seus usuários, acompanhe campanhas e muito mais. Se você já usou o centro de Conformidade e Segurança do Office 365, isto será familiar para você.

:::image type="content" source="../../media/converge-3-email-and-collab-new.png" alt-text="O menu de início rápido para Email & Collab (ou MSDO), no lado esquerdo do Microsoft 365 Defender.":::

#### <a name="email-entity-page"></a>Página de entidade de email 

A [página entidade Email](../office-365-security/mdo-email-entity-page.md) unifica *informações* de email que foram espalhadas por diferentes páginas ou exibições no passado. A investigação de email para ameaças e tendências é *centralizada*. As informações do cabeçalho e a visualização do email são acessíveis através da mesma página de email, juntamente com outras informações úteis relacionadas ao email. Da mesma forma, o status de detonação para anexos de arquivos ou URLs mal-intencionados pode ser encontrado em uma guia da mesma página. A página de entidade de email empodera os administradores e as equipes de operações de segurança para entender uma ameaça de email e seu status e age rapidamente para determinar o tratamento.

### <a name="access-and-reports"></a>Acesso e Relatórios

Exibir relatórios, alterar suas configurações e modificar as funções de usuário.

:::image type="content" source="../../media/converge-4-access-and-reporting-new.png" alt-text="O menu de início rápido para Microsoft 365 Defender permissões e relatórios, no lado esquerdo do centro de segurança.":::

> [!NOTE]
> DomainKeys Identified Mail (DKIM) garante que os sistemas de email de destino confiem em mensagens enviadas de saída de seu domínio personalizado.
> Para o Defender para Office 365 usuários,  agora você pode gerenciar e girar chaves DKIM por meio de Microsoft 365 Defender: , ou navegar até Políticas de & regras Políticas de ameaça <https://security.microsoft.com/threatpolicy>  \>  \> **DKIM**.
> 
> Para obter mais informações, [consulte Use DKIM to validate outbound email sent from your custom domain](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email).

## <a name="whats-changed"></a>O que mudou

Esta tabela é uma referência rápida do gerenciamento  de ameaças em que ocorreu uma alteração entre o Centro de Conformidade & segurança e o portal **Microsoft 365 Defender** segurança. Clique nos links para ler mais sobre essas áreas.

<br>

****

|Área|Descrição da alteração|
|---|---|
|[Investigação](../office-365-security/office-365-air.md#changes-are-coming-soon-in-your-microsoft-365-defender-portal)|Reúne os recursos de AIR em [Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) e [Defender para Ponto de Extremidade](../defender-endpoint/automated-investigations.md). Com essas atualizações e melhorias, sua equipe de operações de segurança poderá exibir detalhes sobre investigações automatizadas e ações de remediação em todo o seu email, conteúdo de colaboração, contas de usuário e dispositivos, tudo em um só lugar.|
|[Fila de alertas](../../compliance/alert-policies.md)|O **painel exibir alertas** de sobrevoo no centro Office Segurança e Conformidade agora inclui links para Microsoft 365 Defender. Clique no link **Abrir Página de Alerta e** Microsoft 365 Defender abre. Você pode acessar a página **Exibir alertas** clicando em qualquer alerta do Office 365 na fila de Alertas.|
|[Treinamento de Simulação de Ataque](../office-365-security/attack-simulation-training-insights.md)|Use o treinamento de Simulação de Ataque para executar cenários de ataque realistas em sua organização. Esses ataques simulados podem ajudar a treinar a sua força de trabalho antes que um ataque real afete a sua organização. O treinamento de simulação de ataque inclui mais opções, relatórios avançados e fluxos de treinamento aprimorados que ajudam a tornar a simulação de ataque e os cenários de treinamento fáceis de realizar e gerenciar.|
|

Não há mudanças nessas áreas:

- [Explorador](../office-365-security/threat-explorer.md)
- [Políticas e Regras](../../compliance/alert-policies.md)
- [Campanha](../office-365-security/campaigns.md)
- [Envios](../office-365-security/admin-submission.md)
- [Análise](./m365d-action-center.md)
- [Controlador de Ameaças](../office-365-security/threat-trackers.md)

Verifique também a seção **Informações Relacionadas** na parte inferior deste artigo.

> [!IMPORTANT]
> O Microsoft 365 Defender portal ( <https://security.microsoft.com> ) combina recursos de segurança em e <https://securitycenter.windows.com> <https://protection.office.com> . No entanto, o que você verá vai depender da sua assinatura. Se você tem apenas o Plano 1 ou 2 do Microsoft Defender para Office 365, como assinaturas autônomas, por exemplo, não verá os recursos de Segurança para Pontos de Extremidade e Defender para Office. Os clientes do plano 1 não verão itens como Análise de Ameaças.

> [!TIP]
> Todas as Proteção do Exchange Online (EOP) serão incluídas no Microsoft 365 Defender, pois o EOP é um elemento principal do Defender para Office 365.

## <a name="microsoft-365-defender-home-page"></a>Microsoft 365 Defender Home page

A home page do portal revela informações de resumo importantes sobre o status de segurança do seu Microsoft 365 ambiente.

Usando o **Tour guiado**, você pode fazer um rápido tour pelo Ponto de Extremidade ou pelas páginas de Email e colaboração. Observe que o que você verá aqui vai depender de você ter a licença para o Defender para Office 365 e/ou Defender para Ponto de Extremidade.

Também há um link para o **centro de Conformidade e Segurança do Office 365** para comparação. O último link é para a página **Novidades** que descreve as atualizações recentes.

## <a name="related-information"></a>Informações relacionadas

- [Redirecionando o Centro de Conformidade e Segurança do Office 365 para o Microsoft 365 Defender](microsoft-365-security-mdo-redirection.md)
- [A Central de Ações](./m365d-action-center.md)
- [Alertas de email e colaboração](../../compliance/alert-policies.md#default-alert-policies)
- [Regras de detecção personalizadas](/microsoft-365/security/defender-endpoint/custom-detection-rules)
- [Criar uma simulação de ataque de phishing](../office-365-security/attack-simulation-training.md) e [criar um conteúdo para treinar sua equipe](../office-365-security/attack-simulation-training-payloads.md)
