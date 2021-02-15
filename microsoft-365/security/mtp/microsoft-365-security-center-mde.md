---
title: Microsoft Defender para Ponto de Extremidade no centro de segurança do Microsoft 365
description: Saiba mais sobre as alterações da Central de Segurança do Microsoft Defender para a central de segurança do Microsoft 365
keywords: Getting started with the Microsoft 365 security center, OATP, MDATP, MDO, MDE, single pane of glass, converged portal, security portal, defender security portal
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 1fd32aa688256f1ac8e63eec902c3a18b2143f09
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242909"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a>Microsoft Defender para Ponto de Extremidade no centro de segurança do Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Aplica-se a:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Obter o Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)

A central de segurança aprimorada do [Microsoft 365](overview-security-center.md) combina recursos de segurança que protegem, detectam, investigam e respondem a emails, colaboração, identidade e ameaças [https://security.microsoft.com](https://security.microsoft.com) a dispositivos. Essa central de segurança reúne funcionalidades de portais de segurança da Microsoft existentes, incluindo a Central de Segurança do Microsoft Defender e o Centro de Conformidade e Segurança do Office 365 & Segurança.

Se você estiver familiarizado com a Central de Segurança do Microsoft Defender, este artigo ajuda a descrever algumas das alterações e melhorias na central de segurança aprimorada do Microsoft 365. No entanto, há alguns elementos novos e atualizados a serem cientes.

Historicamente, a [Central de Segurança do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/portal-overview) foi a casa do Microsoft Defender para o Ponto de Extremidade. As equipes de segurança corporativa o usaram para monitorar e ajudar a responder a alertas de possíveis atividades avançadas de ameaças persistentes ou violações de dados. Para ajudar a reduzir o número de portais, o centro de segurança do Microsoft 365 será a página de monitoramento e gerenciamento de segurança em suas identidades, dados, dispositivos, aplicativos e infraestrutura da Microsoft.

O Microsoft Defender para Ponto de Extremidade na central de segurança do Microsoft 365 dá suporte à concessão de acesso a [MSSPs (provedores](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) de serviços de segurança gerenciados) da mesma maneira que o acesso é concedido na central de segurança do [Microsoft Defender.](mssp-access.md)


> [!IMPORTANT]
> O que você vê na central de segurança do Microsoft 365 depende de suas assinaturas atuais. Por exemplo, se você não tiver uma licença do Microsoft Defender para Office 365, a seção colaboração de email & não será exibida.

Dê uma olhada na central de segurança aprimorada do Microsoft 365: [https://security.microsoft.com](https://security.microsoft.com) .

Saiba mais sobre os benefícios: [Visão geral da central de segurança do Microsoft 365](overview-security-center.md)

## <a name="whats-changed"></a>O que mudou

Esta tabela é uma referência rápida das alterações entre a Central de Segurança do Microsoft Defender e a central de segurança do Microsoft 365.

### <a name="alerts-and-actions"></a>Alertas e ações

|**Área**  |**Descrição da alteração**  |
|---------|---------|
| [Incidentes & alertas](incidents-overview.md)  | No centro de segurança do Microsoft 365, você pode gerenciar incidentes e alertas em todos os pontos de extremidade, email e identidades. Convergimos a experiência para ajudá-lo a encontrar eventos relacionados com mais facilidade. Para obter mais informações, consulte [Visão geral de incidentes.](incidents-overview.md)   |
| [Busca](advanced-hunting-overview.md)  |  A modificação de regras de detecção personalizadas criadas no Microsoft Defender para o Ponto de Extremidade para incluir tabelas de identidade e email as move automaticamente para o Microsoft 365 Defender. Os alertas correspondentes também aparecerão no Microsoft 365 Defender. Para obter mais detalhes sobre essas alterações, leia [Migrar regras de detecção personalizadas.](advanced-hunting-migrate-from-mdatp.md#migrate-custom-detection-rules) A `DeviceAlertEvents` tabela para busca avançada não está disponível no Microsoft 365 Defender. Para consultar informações de alerta específicas do dispositivo no Microsoft 365 Defender, você pode usar as tabelas e as tabelas para acomodar ainda mais informações de um conjunto `AlertInfo` `AlertEvidence` diversificado de fontes. Crie sua próxima consulta relacionada ao dispositivo seguindo as [consultas write sem DeviceAlertEvents](advanced-hunting-migrate-from-mdatp.md#write-queries-without-devicealertevents).|
|[Central de ações](mtp-action-center.md)    | Lista as ações pendentes e concluídas que foram realizadas após investigações automatizadas e ações de correção. Anteriormente, a Central de Ações na Central de Segurança do Microsoft Defender listava ações pendentes e concluídas para ações de correção realizadas apenas em dispositivos, enquanto investigações automatizadas listaram alertas e status. No centro de segurança aprimorado do Microsoft 365, a Central de ações reúne ações de correção e investigações em emails, dispositivos e usuários, tudo em um único local.  |
| [Análise de ameaças](threat-analytics.md) |  Movido para a parte superior da barra de navegação para facilitar a descoberta e o uso. Agora inclui informações de ameaças para pontos de extremidade e email e colaboração.    |

### <a name="endpoints"></a>Pontos de extremidade

|**Área**  |**Descrição da alteração**  |
|---------|---------|
|Pesquisar   |  Em vez de estar no título, a barra de pesquisa do Microsoft Defender para Ponto de Extremidade está se movendo abaixo da seção Pontos de extremidade. Você pode continuar a pesquisar dispositivos, arquivos, usuários, URLs, IPs, vulnerabilidades, software e recomendações.  |
|[Painel](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  Este é o painel de operações de segurança. Veja uma visão geral de quantos alertas ativos foram disparados, quais dispositivos estão em risco, quais usuários estão em risco e nível de gravidade para alertas, dispositivos e usuários. Você também pode ver se algum dispositivo tem problemas de sensor, sua saúde geral do serviço e como quaisquer alertas não resolvidos foram detectados. |
|Inventário de dispositivos | Nenhuma alteração. |
|[Gerenciamento de Ameaças e Vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    O nome foi reduzido para se ajustar ao painel de navegação. É o mesmo que a seção de gerenciamento de ameaças e vulnerabilidades, com todas as páginas abaixo.     |
| Parceiros e APIs | Nenhuma alteração. |
| Avaliações & tutoriais    |     Novos recursos de teste e aprendizagem.     |
| Gerenciamento de configuração   |  Nenhuma alteração.  |

> [!NOTE]
> **A investigação e a correção automática** agora fazem parte dos incidentes. Você pode ver eventos de investigação e correção automatizadas na guia **Investigação > Incidente.**

### <a name="access-and-reporting"></a>Acesso e relatórios

|**Área**  |**Descrição da alteração**  |
|---------|---------|
| Relatórios  | Consulte relatórios para pontos de extremidade e colaboração de &, incluindo proteção contra ameaças, conformidade e conformidade do dispositivo e dispositivos vulneráveis. |
| Integridade  |  Atualmente, os links para a página "Serviço de saúde" no Centro [de administração do Microsoft 365.](https://admin.microsoft.com/) |
| Configurações |  Gerencie suas configurações para a central de segurança do Microsoft 365, o Microsoft 365 Defender, pontos de extremidade, colaboração de email &, identidades e descoberta de dispositivos.   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a>Recursos e navegação de segurança do Microsoft 365

A navegação à esquerda ou a barra de início rápido parece familiar. No entanto, há alguns elementos novos e atualizados neste centro de segurança.

### <a name="incidents-and-alerts"></a>Incidentes e alertas

Reúne o gerenciamento de incidentes e alertas em seus emails, dispositivos e identidades. A página de alerta fornece contexto completo ao alerta combinando sinais de ataque para construir uma história detalhada. Uma nova experiência unificada agora reúne uma exibição consistente de alertas entre cargas de trabalho. Você pode rapidamente fazer triagem, investigar e tomar medidas efetivas.

- [Saiba mais sobre incidentes](incidents-overview.md)
- [Saiba mais sobre como gerenciar alertas](investigate-alerts.md)

![A barra de início rápido alertas e ações](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a>Busca

Pesquise proativamente por ameaças, malware e atividades mal-intencionadas em seus pontos de extremidade, caixas de correio do Office 365 e muito mais usando consultas [de busca avançada.](advanced-hunting-overview.md) Essas consultas poderosas podem ser usadas para localizar e revisar indicadores de ameaças e entidades para ameaças conhecidas e em potencial.

[As regras de detecção](custom-detection-rules.md) personalizadas podem ser criadas a partir de consultas avançadas de busca para ajudá-lo a observar proativamente eventos que podem ser indicativos de atividade de violação e dispositivos configurados incorretamente.


### <a name="action-center"></a>Central de ações

A Central de Ações mostra as investigações criadas por recursos automatizados de investigação e resposta. Essa autorecução automatizada no Microsoft 365 Defender pode ajudar as equipes de segurança respondendo automaticamente a eventos específicos.

[Saiba mais sobre a Central de Ações](mtp-action-center.md)

### <a name="threat-analytics"></a>Análise de Ameaças

Obter inteligência contra ameaças de especialistas em segurança da Microsoft. A Análise de Ameaças ajuda as equipes de segurança a serem mais eficientes ao enfrentar ameaças emergentes. A Análise de Ameaças inclui:

- Detecções e mitigações relacionadas a email do Microsoft Defender para Office 365. Isso é um acréscimo aos dados do ponto de extremidade já disponíveis no Microsoft Defender para Ponto de Extremidade.
- Exibição de incidentes relacionados às ameaças.
- Experiência aprimorada para identificar rapidamente e usar informações a actionable nos relatórios.

Você pode acessar a análise de ameaças na barra de navegação superior esquerda no centro de segurança do Microsoft 365 ou em um cartão de painel dedicado que mostra as principais ameaças para sua organização.

Saiba mais sobre como acompanhar [e responder a ameaças emergentes com a análise de ameaças](https://docs.microsoft.com/microsoft-365/security/mtp/threat-analytics)

### <a name="endpoints-section"></a>Seção Endpoints

Exibir e gerenciar a segurança dos pontos de extremidade em sua organização. Se você tiver usado a Central de Segurança do Microsoft Defender, ela ficará familiar.

![The Endpoints quick launch bar](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a>Acesso e relatórios

Exibir relatórios, alterar suas configurações e modificar funções de usuário.

![Barra de quicklaunch do Access e relatórios](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a>Conexões da API SIEM

Se você usar o [Defender para a API SIEM do ponto](/windows/security/threat-protection/microsoft-defender-atp/enable-siem-integration.md)de extremidade, poderá continuar a fazê-lo. Adicionamos novos links à carga da API que apontam para a página de alerta ou para a página de incidentes no portal de segurança do Microsoft 365. Os novos campos da API incluem LinkToMTP e IncidentLinkToMTP. Para obter mais informações, consulte Redirecionando contas do Microsoft Defender para o Ponto de [Extremidade para a central de segurança do Microsoft 365.](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md)

### <a name="email-alerts"></a>Alertas de email

Você pode continuar a usar alertas de email para o Defender para Ponto de Extremidade. Adicionamos novos links nos emails que apontam para a página de alerta ou para a página de incidentes no centro de segurança do Microsoft 365. Para obter mais informações, consulte Redirecionando contas do Microsoft Defender para o Ponto de [Extremidade para a central de segurança do Microsoft 365.](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md)

## <a name="related-information"></a>Informações relacionadas

- [Centro de segurança do Microsoft 365](overview-security-center.md)
- [Microsoft Defender para Ponto de Extremidade no centro de segurança do Microsoft 365](microsoft-365-security-center-mde.md)
- [Redirecionando contas do Microsoft Defender para o Ponto de Extremidade para a central de segurança do Microsoft 365](microsoft-365-security-mde-redirection.md)
