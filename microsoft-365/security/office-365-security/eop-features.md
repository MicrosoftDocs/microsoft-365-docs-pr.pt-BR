---
title: Recursos EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 599b8048-1056-457b-aae4-c063138fd319
description: A tabela a seguir fornece uma lista dos recursos que estão disponíveis no serviço de filtragem de email hospedado da Proteção do Exchange Online (EOP).
ms.openlocfilehash: 58893cd4a4d6c90c8d19de5a6b2f0d108ee797e0
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202922"
---
# <a name="eop-features"></a>Recursos EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


A tabela a seguir fornece uma lista dos recursos que estão disponíveis no serviço de filtragem de email hospedado da Proteção do Exchange Online (EOP).

> [!TIP]
> O [mapa do Microsoft 365 for Business](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) é um bom recurso para encontrar informações sobre os novos recursos do futuro. Para ter uma visão mais ampla sobre quais recursos estão disponíveis com os diferentes planos de assinatura da EOP, veja [Descrição do serviço de Proteção do Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

****

|Recurso|Descrição|
|---|---|
|**Proteção antispam**||
|Detecção de entrada de spam|Para obter mais informações, consulte [proteção antispam no Microsoft 365](anti-spam-protection.md). <br/><br/> Em ambientes da EOP autônoma, em que a EOP protege as caixas de correio locais do Exchange, é preciso configurar regras de fluxo de email (também conhecidas como regras de transporte) no Exchange local para traduzir o veredito de filtragem de spam do EOP, de modo que a regra do lixo eletrônico possa mover as mensagens para a pasta de Lixo Eletrônico. Para obter detalhes, consulte [Configure standalone EOP to entregar spam para a pasta lixo eletrônico em ambientes híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)|
|Detecção de saída de spam|A proteção antispam de saída está sempre habilitada se você usar o serviço para enviar emails de saída. Para obter mais informações, consulte [proteção contra spam de saída](outbound-spam-controls.md).|
|Proteção de dispersão|Para obter mais informações, consulte [dispersão e EOP](backscatter-messages-and-eop.md).|
|Filtragem de email em massa|O EOP usa o limite de reclamações em massa (BCL) para marcar mensagens de email em massa como spam. Para obter mais informações, consulte os seguintes tópicos: <br/><br/> [Qual é a diferença entre lixo eletrônico e e-mail em massa?](what-s-the-difference-between-junk-email-and-bulk-email.md) <br/> [Nível de reclamação em massa (BCL) no EOP](bulk-complaint-level-values.md) <br/> [Configurar políticas antispam](configure-your-spam-filter-policies.md)|
|Listas de bloqueio de URLs mal-intencionadas|A EOP usa várias listas de bloqueio de URL que ajudam a detectar links mal-intencionados conhecidos nas mensagens.|
|Proteção antiphishing|A EOP inclui 750.000 domínios de remetentes de spam conhecidos.|
|Proteção antifalsificação|Para obter mais informações, consulte [proteção contra falsificação](anti-spoofing-protection.md).|
|**Gerenciamento de spam**||
|Configurar remetentes confiáveis e remetentes bloqueados|Para obter mais informações, consulte [criar listas de remetentes confiáveis](create-safe-sender-lists-in-office-365.md) e [criar listas de remetentes bloqueados](create-block-sender-lists-in-office-365.md).|
|Criar políticas antispam personalizadas|Para maior granularidade, você pode criar políticas antispam personalizadas e aplicá-las a usuários, grupos ou domínios especificados em sua organização. Diretrizes personalizadas sempre prevalecem sobre as diretrizes padrão, mas você pode alterar a prioridade (isto é, a ordem de execução) das suas diretrizes personalizadas. Para saber mais, confira [Configurar políticas anti-spam](configure-your-spam-filter-policies.md).|
|Configurar as ações em mensagens filtradas por spam|Por exemplo, você pode excluir mensagens de conteúdo filtrado ou enviá-las para a pasta Lixo eletrônico ou para a quarentena. Para saber mais, confira [Configurar políticas anti-spam](configure-your-spam-filter-policies.md).|
|Filtragem de spam internacional|Você pode configurar a filtragem antispam para filtrar mensagens escritas em idiomas específicos ou enviadas de países ou regiões específicos. Para saber mais, confira [Configurar políticas anti-spam](configure-your-spam-filter-policies.md).|
|Gerenciar spam via Outlook ou Outlook na Web (anteriormente conhecido como Outlook Web App)|Os administradores e usuários finais podem criar listas de remetentes confiáveis e listas de remetentes bloqueados. Para obter mais informações, consulte [sobre configurações de lixo eletrônico no Outlook](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook). <br/><br/> Se você estiver usando o EOP para ajudar a proteger caixas de correio locais, certifique-se de usar a sincronização de diretório para ajudar a garantir que essas configurações sejam sincronizadas com o serviço. Para saber mais sobre como configurar a sincronização de diretório, consulte "Usar a sincronização de diretório para gerenciar usuários de email" em [Gerenciar usuários de email no EOP](manage-mail-users-in-eop.md).|
|Relatar falsos positivos e falsos negativos à Microsoft.|Para mais informações, confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).|
|Notificações da quarentena de spam para usuário final|Para saber mais, confira [notificações de spam do usuário final](use-spam-notifications-to-release-and-report-quarantined-messages.md) e [Configure notificações de spam para o usuário final](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications).|
|Exibir, localizar e gerenciar mensagens no portal de quarentena.|Para obter mais informações, consulte [gerenciar mensagens em quarentena e arquivos como um administrador no EOP](manage-quarantined-messages-and-files.md) ou [Localizar e liberar mensagens em quarentena como um usuário](find-and-release-quarantined-messages-as-a-user.md).|
|Exibir cabeçalhos de mensagem de spam em quarentena|Depois de exibir o cabeçalho da mensagem na quarentena, você também pode copiar e colar o texto do cabeçalho no [analisador de cabeçalho de mensagem](https://mha.azurewebsites.net/) para descobrir o que aconteceu com a mensagem.|
|**Proteção antimalware**||
|Proteção antimalware de múltiplos mecanismos|Vários mecanismos antimalware ajudam a proteger automaticamente nossos clientes o tempo todo.|
|A capacidade de desabilitar a filtragem de malware|Não é possível desabilitar a filtragem de malware. Consideramos que ajudar a fornecer um nível de proteção consistente e rigoroso para todos nossos clientes seja uma parte essencial da estratégia de defesa avançada necessária para ajudar a proteger seu ambiente de mensagens de email. Como resultado, a filtragem de malware fica automaticamente habilitada para todos os clientes.|
|Inspeção de malware nos anexos e no corpo da mensagem|O serviço inspeciona a carga ativa no corpo da mensagem e todos os anexos de mensagens em busca de malware.|
|Notificações de alerta de malware padrão ou personalizadas|Você pode enviar uma mensagem de notificação para remetentes ou administradores. Para obter mais informações, consulte [Configure anti-malware Policies](configure-anti-malware-policies.md).|
|Notificações de destinatário|Colocar silenciosamente a mensagem em quarentena ou colocar a mensagem em quarentena e também fornecê-la com todos os anexos substituídos por um único arquivo de texto contendo texto padrão ou personalizado. Para obter mais informações, consulte [Configure anti-malware Policies](configure-anti-malware-policies.md).|
|Filtragem de anexos comuns|Você pode habilitar e personalizar uma lista de tipos de arquivo que são sempre presumidos como malware. Para obter mais informações, consulte [proteção Antimalware no EOP](anti-malware-protection.md).|
|Proteção antispyware|A proteção antimalware abrange a proteção antivírus e antispyware.|
|Criar políticas personalizadas de filtro de malware|Para uma maior granularidade, você pode criar políticas personalizadas de filtro de malware e aplicá-las a usuários, grupos ou domínios específicos na sua organização. As políticas personalizadas têm precedência sobre a política padrão da empresa, mas você pode mudar a prioridade (ou seja, a ordem de execução) das suas políticas personalizadas. Para obter mais informações, consulte [Configure anti-malware Policies](configure-anti-malware-policies.md).|
|**Roteamento e conectores de email**||
|Roteamento de e-mail condicional|Para obter mais informações, consulte [cenário: roteamento de email condicional no Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).|
|TLS oportunista ou forçado|O TLS oportunista ou forçado está disponível com conectores. O TLS oportunista tenta uma conexão TLS, mas usará uma conexão SMTP se não tiver êxito com a conexão TLS. Forçar o TLS impõe conexões TLS, o que significa que a mensagem será rejeitada se a conexão TLS for bem-sucedida. Para saber mais sobre TLS, segurança e conectores, confira [Set up connectors for secure mail flow with a partner organization](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner).|
|Roteamento regional (fluxo de email restrito a uma determinada região)|Para saber mais, consulte a seção «datacenter da EOP» na [Visão geral do Exchange Online Protection](exchange-online-protection-overview.md).|
|A ferramenta Verificador de Conectividade SMTP|Para obter mais informações sobre como usar essa ferramenta para testar seu fluxo de email, consulte [testar o fluxo de emails, Validando seus conectores do Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).|
|Corresponder subdomínios|Para obter mais informações sobre como habilitar o fluxo de emails de e para subdomínios de seus domínios aceitos, consulte [Mail Flow in EOP](mail-flow-in-eop.md).|
|**Regras de fluxo de emails**||
|Filtragem e ações baseadas em política|As políticas personalizadas são baseadas nas regras de fluxo de emails do Exchange (também conhecidas como regras de transporte). Você pode filtrar por domínio, palavra-chave, nome do arquivo, tipo de arquivo, linha de assunto, corpo da mensagem, remetente, destinatário, cabeçalho e endereço IP. Para obter mais informações, consulte [regras de fluxo de emails (regras de transporte) no Exchange Online Protection](mail-flow-rules-transport-rules-0.md).|
|Filtrar por padrões de texto|As regras de fluxo de emails podem usar uma matriz ou expressões regulares para corresponder ao texto. Você também pode usar uma cadeia de caracteres ou uma matriz de cadeias de caracteres para corresponder às muitas propriedades de mensagem, como os nomes de endereço, assunto, corpo ou anexo. Para obter mais informações, consulte [regras de fluxo de emails (regras de transporte) no Exchange Online Protection](mail-flow-rules-transport-rules-0.md)|
|Dicionários personalizados|As regras de fluxo de emails podem incluir listas longas de texto e palavras-chave, fornecendo a mesma funcionalidade que um dicionário personalizado.|
|Regras de política por domínio|O escopo de uma regra de fluxo de emails pode ser personalizado para corresponder a nomes de domínio de remetentes ou destinatários, intervalos de endereços IP, palavras-chave de endereço ou padrões, associações de grupo e outras condições.|
|Verificação de anexo|As regras podem ser criadas para verificar o nome do arquivo, a extensão e o conteúdo do anexo.|
|Enviar notificações da regra de política para o remetente|Você pode rejeitar mensagens e enviar uma notificação de falha na entrega (também conhecida como notificação de falha na entrega ou mensagem de devolução) ao remetente por meio da **rejeição da mensagem com a explicação** ou **rejeitar a mensagem com a ação de código de status avançado** . Para obter mais informações, consulte [Mail Flow Rule Actions in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).|
|Redirecionar ou copiar mensagens|Regras de fluxo de emails podem redirecionar, Adicionar destinatários por CC ou Cco, simplesmente adicionar destinatários e outras opções. Para obter mais informações, consulte [Mail Flow Rule Actions in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).|
|Ajustar a prioridade de regra em várias regras|Use o Centro de administração do Exchange para alterar a ordem na qual as regras são processadas.|
|Filtrar mensagens e alterar o roteamento ou atributos de uma mensagem|Você pode filtrar mensagens com base em uma ampla variedade de condições e, em seguida, aplicar uma série de ações para cada mensagem. Para obter mais informações, consulte [regras de fluxo de emails (regras de transporte) no Exchange Online Protection](mail-flow-rules-transport-rules-0.md).|
|Altere o nível de confiança de spam (SCL) de uma mensagem por regra.|Você pode inspecionar uma mensagem em trânsito e atribuir um nível de confiança de spam com base nos critérios que você escolher. Para obter mais informações, consulte [usar regras de fluxo de emails para definir o nível de confiança de spam (SCL) em mensagens](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).|
|Inspecionar anexos de mensagens|Você pode examinar o conteúdo de um anexo ou as características de um arquivo anexado e definir uma ação a ser tomada com base naquilo que for encontrado. Para obter mais informações, consulte [usar regras de fluxo de emails para inspecionar anexos de mensagens no Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments).|
|**Administração**||
|Administração com base na Web|Os administradores podem gerenciar o serviço no centro de administração do Exchange (Eat), que é suportado em idiomas 60. Para obter mais informações, consulte [centro de administração do Exchange em EOP autônomo](exchange-admin-center-in-exchange-online-protection-eop.md).|
|Sincronização de diretório|A sincronização de diretório está disponível por meio do Ferramenta de Sincronização do Microsoft Azure Active Directory. Para saber mais, veja a seção «Usar a sincronização de diretório para gerenciar usuários de email» em [Gerenciar usuários de email no EOP](manage-mail-users-in-eop.md).  |
|Bloqueio de borda baseado em diretório (DBEB)|O recurso DBEB permite rejeitar mensagens de destinatários inválidos no perímetro da rede do serviço. O DBEB permite que os administradores adicionem destinatários habilitados para email ao Microsoft 365 e Bloqueiem todas as mensagens enviadas para endereços de email que não estão presentes no Microsoft 365. Para obter mais informações sobre como configurar o DBEB, consulte [usar o bloqueio de borda baseado em diretório para rejeitar mensagens enviadas a destinatários inválidos](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).|
|PowerShell|A funcionalidade completa do EOP está disponível no PowerShell autônomo do EOP. Para obter mais informações, consulte [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell).|
|**Criação de relatórios e registro em log**||
|Rastreamento de mensagens|Os administradores podem seguir mensagens de email à medida que eles passam pelo serviço. Você pode determinar se uma mensagem de email direcionada foi recebida, rejeitada, adiada ou entregue pelo serviço. Isso permite responder com eficiências às perguntas dos usuários, solucionar problemas de fluxo de emails, validar alterações nas políticas e diminuir a necessidade de entrar em contato com o suporte técnico para solicitar assistência. Para obter mais informações, consulte [Rastreamento de mensagens no Centro de conformidade e segurança](message-trace-scc.md).|
|Relatórios com base na Web|Os relatórios de proteção de email no centro de conformidade de & de segurança fornecem dados de mensagens. Por exemplo, você pode monitorar o quanto spam e malware está sendo detectado ou com que frequência suas regras de fluxo de emails estão sendo atendidas. Com esses relatórios interativos, você pode obter rapidamente um relatório visual de dados resumidos e obter detalhes sobre mensagens individuais de até 90 dias. Para obter mais informações, consulte [usar relatórios de proteção de email para exibir dados sobre detecções de malware, spam e regras](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports).|
|Registro em log de auditoria|O relatório de grupo de função do administrador e o log de auditoria do administrador estão disponíveis para administradores da EOP. Para saber mais, veja [Relatórios de auditoria no EOP](auditing-reports-in-eop.md).  |
|**Contratos de Nível de Serviço (SLAs) e suporte**||
|SLA da eficácia do spam|\> 99%|
|SLA da taxa de falsos positivos|\< 1:250000|
|SLA de detecção de vírus e bloqueio|100% de vírus conhecidos|
|SLA do tempo de atividade mensal|99,999%|
|Suporte técnico por telefone e pela Web 24 horas por dia, sete dias por semana|Para saber mais sobre a ajuda da EOP e as opções de suporte, consulte [Ajuda e suporte para EOP](help-and-support-for-eop.md).|
|**Outros recursos**||
|Uma rede global com redundância geográfica de servidores|O EOP é executado em uma rede mundial de datacenters projetados para ajudar a fornecer a melhor disponibilidade. Para saber mais, veja a seção "datacenter da EOP" em [Visão geral do Exchange Online Protection](exchange-online-protection-overview.md).  |
|Enfileiramento de mensagens quando o servidor local não consegue aceitar emails|As mensagens no adiamento permanecem em nossas filas por um dia. As tentativas de repetição de mensagens baseiam-se no tipo de erro recebido do sistema de mensagens do destinatário. Em média, as mensagens são repetidas a cada 5 minutos. Para saber mais, veja [Perguntas frequentes sobre mensagens enfileiradas, adiadas e retornadas do EOP](eop-queued-deferred-and-bounced-messages-faq.md).|
|Criptografia de mensagem do Office 365 disponível como um serviço complementar|Para saber mais informações, consulte [Criptografia no Office 365](../../compliance/encryption.md).|
|
