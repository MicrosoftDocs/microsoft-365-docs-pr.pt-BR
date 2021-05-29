---
title: Proteção do Exchange Online (EOP) visão geral
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Saiba como Proteção do Exchange Online (EOP) pode ajudar a proteger sua organização de email local em ambientes autônomos e híbridos.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ad083e828fbed27cce4b8929c1bee3081c983c17
ms.sourcegitcommit: 76c91e7b0d3172de57988eb4576d2b91c2f9ce18
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2021
ms.locfileid: "52707279"
---
# <a name="exchange-online-protection-overview"></a>Visão geral do Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Proteção do Exchange Online (EOP) é o serviço de filtragem baseado em nuvem que protege sua organização contra spam, malware e outras ameaças de email. O EOP está incluído em todas as organizações Microsoft 365 com Exchange Online caixas de correio.

> [!NOTE]
> O EOP também está disponível por si só para proteger caixas de correio locais e em ambientes híbridos para proteger as caixas de correio locais Exchange local. Para obter mais informações, consulte [Autônomo Proteção do Exchange Online](/exchange/standalone-eop/standaonline-eop).

As etapas para configurar os recursos de segurança do EOP e uma comparação com a segurança adicionada que você obter no Microsoft Defender para Office 365, consulte [protect against threats](protect-against-threats.md). As configurações recomendadas para recursos EOP estão disponíveis em [Configurações recomendadas](recommended-settings-for-eop-and-office365.md)para EOP e Microsoft Defender para Office 365 segurança .

O restante deste artigo explica como o EOP funciona e os recursos disponíveis no EOP.

## <a name="how-eop-works"></a>Como o EOP funciona

Para entender como o EOP funciona, ele o ajuda a ver como processa o email de entrada:

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="Gráfico de emails da Internet ou comentários do cliente que passam para o EOP e por meio do Connection, Anti-malware, Mailflow Rules-slash-Policy Filtering e Filtragem de Conteúdo, antes do veredito de lixo eletrônico ou quarentena ou entrega de email de usuário final.":::

1. Quando uma mensagem de entrada entra no EOP, ela passa inicialmente pela filtragem de conexão, que verifica a reputação do remetente. A maioria dos spams é interrompida neste ponto e rejeitada pelo EOP. Para obter mais informações, confira [Configurar a filtragem da conexão](configure-the-connection-filter-policy.md).

2. Em seguida, a mensagem é inspecionada para malware. Se o malware for encontrado na mensagem ou nos anexos, a mensagem será roteada para um armazenamento de quarentena somente de administrador. Para saber mais sobre a proteção contra malware, consulte [Proteção anti-malware no EOP](anti-malware-protection.md).

3. A mensagem continua através da filtragem de política, onde é avaliada em relação a quaisquer regras de fluxo de emails (também conhecidas como regras de transporte) que você criou. Por exemplo, uma regra pode enviar uma notificação para um gerente quando uma mensagem chega de um remetente específico.

   Na organização local com Exchange Enterprise cal com licenças de Serviços, as verificações de prevenção contra perda de dados [(DLP)](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention) no EOP também ocorrem neste ponto.

4. A mensagem passa pela filtragem de conteúdo (anti-spam e anti-spoofing) onde mensagens prejudiciais são identificadas como spam, spam de alta confiança, phishing, phishing de alta confiança ou em massa (políticas anti-spam) ou spoofing (configurações de spoof em políticas anti-phishing). Você pode configurar a ação a ser tomada na mensagem com base no veredito de filtragem (quarentena, mover para a pasta Lixo Eletrônico, etc.). Para obter mais informações, consulte [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).

Uma mensagem que passa com êxito todas essas camadas de proteção é entregue aos destinatários.

Para obter mais informações, [consulte Order and precedence of email protection](how-policies-and-protections-are-combined.md).

### <a name="eop-datacenters"></a>Datacenters EOP

O EOP é executado em uma rede mundial de data center projetados para fornecer a melhor disponibilidade. Por exemplo, se um data center ficar indisponível, mensagens de email são automaticamente roteadas para um outro data center sem qualquer interrupção no serviço. Os servidores em cada datacenter aceitam mensagens em seu nome, fornecendo uma camada de separação entre sua organização e a Internet, reduzindo assim a carga em seus servidores. Por meio dessa rede altamente disponível, a Microsoft pode assegurar que esse email chegue a sua organização pontualmente.

EOP realiza balanceamento de carga entre data centers, mas apenas dentro de uma região. Se você for aprovisionado em uma região, todas as suas mensagens serão processadas usando o roteamento de email para essa região. A lista a seguir mostra como o roteamento de email regional funciona para os data centers EOP:

- Na Europa, Oriente Médio e África (EMEA), todas as caixas de correio do Exchange Online são localizadas nos data centers da EMEA e todas as mensagens são roteadas através de data centers da EMEA para filtragem do EOP.
- No Asia-Pacific (APAC), todas as caixas de correio Exchange Online estão localizadas em datacenters APAC, e as mensagens atualmente são roteadas por meio de datacenters APAC para filtragem de EOP.
- Nas Américas, os serviços são distribuídos nos seguintes locais:
  - América do Sul: Exchange Online caixas de correio estão localizadas em datacenters no Brasil e no Chile. Todas as mensagens são roteadas por datacenters locais para filtragem EOP. As mensagens em quarentena são armazenadas no datacenter onde o locatário está localizado.
  - Canadá: Exchange Online caixas de correio estão localizadas em datacenters no Canadá. Todas as mensagens são roteadas por datacenters locais para filtragem EOP. As mensagens em quarentena são armazenadas no datacenter onde o locatário está localizado.
  - Estados Unidos: Exchange Online caixas de correio estão localizadas em datacenters dos EUA. Todas as mensagens são roteadas por datacenters locais para filtragem EOP. As mensagens em quarentena são armazenadas no datacenter onde o locatário está localizado.
- Para a Nuvem de Comunidade Governamental (GCC), todas as caixas de correio do Exchange Online localizadas em data centers dos EUA e todas as mensagens são roteadas através de data centers dos EUA para filtragem do EOP.

### <a name="eop-features"></a>Recursos EOP

Esta seção fornece uma visão geral de alto nível dos principais recursos disponíveis no EOP.

Para obter informações sobre requisitos, limites importantes e disponibilidade de recursos em todos os planos de assinatura do EOP, consulte Proteção do Exchange Online [descrição do serviço.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

**Observações**:

- A EOP usa várias listas de bloqueio de URL que ajudam a detectar links mal-intencionados conhecidos nas mensagens.
- O EOP usa uma vasta lista de domínios conhecidos por enviar spam.
- O EOP usa vários mecanismos anti-malware para proteger automaticamente nossos clientes o tempo todo.
- O EOP inspeciona a carga ativa no corpo da mensagem e todos os anexos de mensagem para malware.
- Para saber os valores recomendados para políticas de proteção, consulte [Configurações recomendadas para EOP](recommended-settings-for-eop-and-office365.md)e Microsoft Defender para Office 365 segurança.
- Para obter instruções rápidas para configurar políticas de proteção, consulte [Protect against threats](protect-against-threats.md).

<br>

****
|Recurso|Comentários|
|---|---|
|**Protection**||
|Antimalware|[Proteção anti-malware no EOP](anti-malware-protection.md) <p> [Perguntas frequentes sobre proteção antimalware](anti-malware-protection-faq-eop.yml) <p> [Configurar políticas anti-malware no EOP](configure-anti-malware-policies.md)|
|Anti-spam de entrada|[Proteção anti-spam no EOP](anti-spam-protection.md) <p> [Perguntas frequentes sobre a proteção antispam](anti-spam-protection-faq.yml) <p> [Configurar políticas antispam no EOP](configure-your-spam-filter-policies.md)|
|Anti-spam de saída|[Proteção contra spam de saída no EOP](outbound-spam-controls.md) <p> [Configurar a filtragem de spam de saída no EOP](configure-the-outbound-spam-policy.md) <p> [Controlar o encaminhamento automático de email externo em Microsoft 365](external-email-forwarding.md)|
|Filtragem de conexão|[Configurar a filtragem de conexão](configure-the-connection-filter-policy.md)|
|Anti-phishing|[Políticas anti-phishing no Microsoft 365](set-up-anti-phishing-policies.md) <p> [Configurar políticas anti-phishing em EOP](configure-anti-phishing-policies-eop.md)|
|Proteção antifalsificação|[Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md) <p> [Gerenciar a lista de Permissões/Bloqueios do Locatário](tenant-allow-block-list.md)|
|Limpeza automática zero hora (ZAP) para mensagens de malware, spam e phishing entregues|[ZAP no Exchange Online](zero-hour-auto-purge.md)|
|Predefinir políticas de segurança|[Políticas de segurança predefinidas no EOP e no Microsoft Defender para Office 365](preset-security-policies.md) <p> [Analisador de configuração para políticas de proteção no EOP e no Microsoft Defender para Office 365](configuration-analyzer-for-security-policies.md)|
|Lista de locatários que permitem/bloqueiam|[Gerenciar a lista de Permissões/Bloqueios do Locatário](tenant-allow-block-list.md)|
|Bloquear listas de envios de mensagens|[Criar listas de remetentes bloqueados no EOP](create-block-sender-lists-in-office-365.md)|
|Permitir listas para envios de mensagens|[Criar listas de remetentes seguros no EOP](create-safe-sender-lists-in-office-365.md)|
|Directory Based Edge Blocking (DBEB)|[Usar o Bloqueio de Borda com Base em diretório para rejeitar mensagens enviadas a destinatários inválidos](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|
|**Quarentena e envios**||
|Envio de administrador|[Usar o envio de administrador para enviar spam, phishing, URLs e arquivos suspeitos para a Microsoft](admin-submission.md)|
|Envios de usuário (caixa de correio personalizada)|[Política de envios de usuários](user-submission.md)|
|Quarentena - administradores|[Gerenciar arquivos e mensagens em quarentena como administrador no EOP](manage-quarantined-messages-and-files.md) <p> [Perguntas frequentes sobre mensagens em quarentena](quarantine-faq.yml) <p> [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md) <p> [Cabeçalhos de mensagens anti-spam no Office 365](anti-spam-message-headers.md) <p> Você pode analisar os headers de mensagens em quarentena usando o [Analisador de Header de Mensagens em](https://mha.azurewebsites.net/).|
|Quarentena - usuários finais|[Localizar e liberar mensagens em quarentena como usuário no EOP](find-and-release-quarantined-messages-as-a-user.md) <p> [Usar notificações de spam do usuário para liberar e relatar mensagens em quarentena](use-spam-notifications-to-release-and-report-quarantined-messages.md)|
|**Fluxo de mensagens**||
|Regras do fluxo de email|[Regras de fluxo de emails (regras de transporte) no Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) <p> [Condições e exceções da regra de fluxo de Email do Outlook (predicates) no Exchange Online](/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions) <p> [Ações da regra de fluxo de Email do Outlook no Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions) <p> [Gerenciar regras de fluxo de email no Exchange Online](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules) <p> [Email procedimentos de regra de fluxo no Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-procedures)|
|Domínios aceitos|[Gerenciar domínios aceitos no Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)|
|Conectores|[Configurar o fluxo de emails usando conectores Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)|
|Filtragem avançada para conectores|[Filtragem aprimorada para conectores Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)|
|**Monitoramento**||
|Rastreamento de mensagens|[Rastreamento de mensagens](message-trace-scc.md) <p> [Rastreamento de mensagens no centro de Exchange de administração](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)|
|Relatórios de colaboração & email|[Exibir relatórios de segurança de email](view-email-security-reports.md)|
|Relatórios de fluxo de emails|[Exibir relatórios de fluxo de email](view-mail-flow-reports.md) <p> [Relatórios de fluxo de emails no Exchange de administração](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|Insights de fluxo de emails|[Insights de fluxo de emails](mail-flow-insights-v2.md) <p> [Insights de fluxo de emails no centro de administração Exchange de email](/exchange/monitoring/mail-flow-insights/mail-flow-insights)|
|Relatórios de auditoria|[Relatórios de auditoria no Exchange de administração](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)|
|Políticas de alerta|[Políticas de alerta](../../compliance/alert-policies.md)|
|**Contratos de Nível de Serviço (SLAs) e suporte**||
|SLA da eficácia do spam|\> 99%|
|SLA da taxa de falsos positivos|\< 1:250,000|
|SLA de detecção de vírus e bloqueio|100% de vírus conhecidos|
|SLA do tempo de atividade mensal|99,999%|
|Suporte técnico por telefone e pela Web 24 horas por dia, sete dias por semana|[Ajuda e suporte para EOP](help-and-support-for-eop.md).|
|**Outros recursos**||
|Uma rede global com redundância geográfica de servidores|O EOP é executado em uma rede mundial de datacenters projetados para ajudar a fornecer a melhor disponibilidade. Para obter mais informações, consulte a [seção datacenters EOP](#eop-datacenters) anteriormente neste artigo.|
|Enfileiramento de mensagens quando o servidor local não consegue aceitar emails|As mensagens em adiamento permanecem em nossas filas por um dia. As tentativas de repetição de mensagens baseiam-se no tipo de erro recebido do sistema de mensagens do destinatário. Em média, as mensagens são repetidas a cada 5 minutos. Para saber mais, veja [Perguntas frequentes sobre mensagens enfileiradas, adiadas e retornadas do EOP](eop-queued-deferred-and-bounced-messages-faq.yml).|
|Criptografia de Mensagens do Office 365 disponível como complemento|Para saber mais informações, consulte [Criptografia no Office 365](../../compliance/encryption.md).|
|||
