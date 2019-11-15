---
title: Práticas recomendadas para configurações de segurança do EOP e do Office 365 ATP, recomendações, estrutura de política de remetente, relatórios e conformidade de mensagens baseadas em domínio, DomainKeys identificadas email, etapas, como funciona, etc.
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: Quais são as práticas recomendadas para as configurações de segurança do Exchange Online Protection (EOP) e da proteção avançada contra ameaças (ATP)? Quais são as recomendações atuais para a proteção padrão? O que deve ser usado se você deseja ser mais estrito? E quais são os extras obtidos se você também usa a proteção avançada contra ameaças (ATP)?
ms.openlocfilehash: 6f9d38f7f6200083983f42d74a54163566585a90
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640790"
---
# <a name="best-practices-for-eop-and-office-365-atp-security"></a>Práticas recomendadas para a segurança do EOP e do Office 365 ATP

O **proteção do Exchange Online (EOP)** é o núcleo de segurança para assinaturas do Office 365 e ajuda a impedir que emails mal-intencionados cheguem às caixas de entrada do funcionário. Mas com ataques novos e mais sofisticados surgindo todos os dias, as proteções aprimoradas costumam ser necessárias. **Proteção avançada contra ameaças do Office 365 (ATP)** O plano ATP 1 ou a ATP plano 2 contêm recursos adicionais que dão aos administradores mais camadas de segurança, controle e investigação. 

Embora possamos permitir que os administradores de segurança personalizem suas configurações de segurança, há dois níveis de segurança no EOP e no Office 365 ATP que recomendamos: **padrão** e **estrito**. O ambiente e as necessidades de cada cliente são diferentes, mas acreditamos que esses níveis de configurações de filtragem de email ajudarão a impedir que emails indesejados cheguem à caixa de entrada de seus funcionários na maioria das situações. 

Este tópico descreve estas configurações recomendadas pela Microsoft para ajudar a proteger os usuários do Office 365.

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Anti-spam, Antimalware e proteção contra phishing no EOP
Anti-spam, Antimalware e anti-phishing são recursos do EOP que podem ser configurados pelos administradores. Recomendamos as seguintes configurações.

### <a name="anti-spam-policy"></a>Política antispam

|Nome do recurso de segurança|Standard|Impede|Comentário|
|---------|---------|---------|---------|
|Ação de detecção de spam|Mover mensagem para a pasta Lixo Eletrônico|Mensagem em quarentena||
|Ação de detecção de spam de alta confiança|Mensagem em quarentena|Mensagem em quarentena||
|Ação de detecção de email de phishing|Mensagem em quarentena|Mensagem em quarentena||
|Ação de detecção de email de phishing de alta confiança|Mensagem em quarentena|Mensagem em quarentena||
|Ação de detecção de email em massa|Mover mensagem para a pasta Lixo Eletrônico|Mensagem em quarentena||
|Definir o limite de email em massa para|6|quatro||
|Período de retenção de quarentena|30 dias|30 dias||
|Dicas de segurança|Habilitado|Habilitado||
|Remetentes permitidos|Nenhum|Nenhum||
|Domínios de remetentes permitidos|Nenhum|Nenhum|A adição de domínios que você possui (também conhecido como _domínios aceitos_) à lista de remetentes permitidos não é necessária. Na verdade, ele é considerado de alto risco, pois cria oportunidades de atores incorretos para enviar emails que seriam filtrados de outra forma. Use a [inteligência de spoof](learn-about-spoof-intelligence.md) no centro de conformidade & segurança da página **configurações antispam** para examinar todos os remetentes que estão falsificando os domínios que fazem parte da sua organização ou falsificando domínios externos.|
|Remetentes bloqueados|Nenhum|Nenhum||
|Domínios de remetentes bloqueados|Nenhum|Nenhum||
|Frequência de notificação de spam do usuário final|Habilitado|Habilitado|3 dias|
|Limpeza automática de zero hora|Habilitado|Habilitado|Para obter spam e ZAP de phishing|
|MarkAsSpamBulkMail|Habilitado|Habilitado|Essa configuração só está disponível no PowerShell|

#### <a name="outbound-spam-filter-policy"></a>Política de filtro de spam de saída

|Nome do recurso de segurança|Standard|Impede|Comentário|
|---------|---------|---------|---------|
|Limites de destinatários de política de spam de saída-limite por hora externa|400|500||
|Limites de destinatários de política de spam de saída-limite por hora interna|800|1000||
|Limites de destinatários de política de spam de saída-limite diário|800|1000||
|Ação quando um usuário exceder os limites|Impedir que o usuário envie emails|Impedir que o usuário envie emails||

### <a name="anti-malware-policy"></a>Política Antimalware

|Nome do recurso de segurança|Standard|Impede|Comentário|
|---------|---------|---------|---------|
|Resposta de detecção de malware|Não|Não|Se o malware for detectado em um anexo de email, a mensagem será colocada em quarentena e só poderá ser liberada por um administrador.|
|"Filtro de tipo de anexo comum" para bloquear tipos de arquivo suspeitos|Habilitado|Habilitado||
|Limpeza automática de malware zero-hora|Habilitado|Habilitado||
|Notificar remetentes internos da mensagem não entregue|Desabilitado|Desabilitado||
|Notificar remetentes externos da mensagem não entregue|Desabilitado|Desabilitado||

### <a name="anti-phishing-policy"></a>Política anti-phishing

|Nome do recurso de segurança|Standard|Impede|Comentário|
|---------|---------|---------|---------|
|Habilitar proteção contra falsificação|Habilitado|Habilitado||
|Habilitar remetente não autenticado (marcação)|Habilitado|Habilitado||
|Se o email for enviado por alguém que não tenha permissão para falsificar seu domínio|Mover mensagem para pastas de lixo eletrônico dos destinatários|Colocar a mensagem em quarentena||

## <a name="office-365-advanced-threat-protection-atp-security"></a>Segurança de proteção avançada contra ameaças (ATP) do Office 365
Outros benefícios de segurança acompanham uma assinatura avançada de proteção contra ameaças do Office 365. Para obter as notícias e informações mais recentes, você pode ver [o que há de novo no Office 365 ATP](whats-new-in-office-365-atp.md). 

O Office 365 ATP inclui as políticas de anexo seguro e links seguros para impedir que emails com anexos possivelmente mal-intencionados sejam entregues e para impedir que os usuários cliquem em URLs potencialmente não seguras.

> [!IMPORTANT]
> O anti-phishing avançado é um dos benefícios de uma assinatura ATP do Office 365. Habilitado por padrão, o anti-phishing ***deve*** ser configurado usando políticas antes de começar a filtrar emails. Esquecer de configurar políticas anti-phishing pode expor os usuários a emails arriscados. Certifique-se de configurar suas políticas anti-phishing após adicionar uma assinatura ATP do Office 365.

Se você tiver adicionado uma assinatura ATP do Office 365 ao seu EOP, defina as seguintes configurações.

### <a name="office-atp-anti-phishing-policy"></a>Política anti-phishing do Office ATP
Os clientes do EOP obtêm um conjunto básico de políticas anti-phishing, mas com o Office 365 ATP, os administradores obtêm mais recursos e controle para ajudar a prevenir, detectar e remidi contra ataques.

|Nome do recurso de segurança de representação|Standard|Impede|Comentário|
|---------|---------|---------|---------|
|(Editar política de representação) Adicionar usuários para proteger|Habilitado|Habilitado|Depende da sua organização, mas recomendamos adicionar usuários em funções principais. Internamente, esses podem ser o CEO, CFO e outros líderes seniores. Externamente, elas podem incluir membros do Conselho ou seu Conselho de diretores.|
|(Editar política de representação) Incluir automaticamente os domínios que sou proprietário|Habilitado|Habilitado||
|(Editar política de representação) Incluir domínios personalizados|Habilitado|Habilitado|Depende da sua organização, mas recomendamos adicionar domínios que você interagem com a maioria que você não possui.|
|Se o email for enviado por um usuário representado que você especificou|Colocar a mensagem em quarentena|Colocar a mensagem em quarentena||
|Se o email for enviado por um domínio representado que você especificou|Colocar a mensagem em quarentena|Colocar a mensagem em quarentena||
|Mostrar dica para usuários representados|Habilitado|Habilitado||
|Mostrar dica para domínios representados|Habilitado|Habilitado||
|Mostrar dica para caracteres incomuns|Habilitado|Habilitado||
|Habilitar inteligência de caixa de correio|Habilitado|Habilitado||
|Habilitar proteção de representação baseada em inteligência de caixa de correio|Habilitado|Habilitado||
|Se o email for enviado por um usuário representado protegido por Mailbox Intelligence|Mover mensagem para pastas de lixo eletrônico dos destinatários|Colocar a mensagem em quarentena||
|(Editar política de representação) Adicionar domínios e remetentes confiáveis|Nenhum|Nenhum|Depende da sua organização, mas é recomendável adicionar usuários ou domínios que são marcados incorretamente como phishing devido à representação apenas e não a outros filtros.|

|Nome do recurso de segurança de spoof|Standard|Impede|Comentário|
|---------|---------|---------|---------|
|Habilitar proteção contra falsificação|Habilitado|Habilitado||
|Habilitar remetente não autenticado (marcação)|Habilitado|Habilitado||
|Se o email for enviado por alguém que não tenha permissão para falsificar seu domínio|Mover mensagem para pastas de lixo eletrônico dos destinatários|Colocar a mensagem em quarentena||
|EnableAuthenticationSafetyTip|Verdadeiro|Verdadeiro|Essa configuração só está disponível no PowerShell|
|EnableAuthenticationSoftPassSafetyTip|Falso|True|Essa configuração só está disponível no PowerShell|
|EnableSuspiciousSafetyTip|Falso|True|Essa configuração só está disponível no PowerShell|
|TreatSoftPassAsAuthenticated|True|Falso|Essa configuração só está disponível no PowerShell|

|Nome do recurso de segurança de configurações avançadas|Standard|Impede|Comentário|
|---------|---------|---------|---------|
|Limites avançados de phishing|2-agressivo|3-mais agressivo||

### <a name="safe-links-settings"></a>Configurações de links seguros

|Nome do recurso de segurança|Standard|Impede|Comentário|
|---------|---------|---------|---------|
|Usar links seguros de ATP nos aplicativos do Office 365, Office para iOS e Android|Habilitado|Habilitado|Isso se enquadra nas políticas de links seguros de ATP que se aplicam a toda a organização|
Não rastrear quando os usuários clicarem em links seguros|Desabilitado|Desabilitado|Isso se enquadra nas políticas de links seguros de ATP que se aplicam a toda a organização|
|Não permitir que os usuários cliquem por meio de links seguros para a URL original|Habilitado|Habilitado|Isso se enquadra nas políticas de links seguros de ATP que se aplicam a toda a organização|
|Ação para URLs potencialmente mal-intencionadas desconhecidas em mensagens|Habilitado|Habilitado||
|Aplicar verificação de URL em tempo real para links suspeitos e links que apontam para arquivos|Habilitado|Habilitado||
|Aguarde a conclusão da verificação de URL antes de entregar a mensagem|Habilitado|Habilitado||
|Aplicar links seguros a mensagens de email enviadas dentro da organização|Habilitado|Habilitado||

### <a name="safe-attachments"></a>Anexos Seguros

|Nome do recurso de segurança|Standard|Impede|Comentário|
|---------|---------|---------|---------|
|Ative a ATP para SharePoint, OneDrive e Microsoft Teams|Habilitado|Habilitado||
|Resposta de malware desconhecida de anexos seguros de ATP|Bloquear|Bloquear||
|Redirecionar o anexo na detecção|Habilitado|Habilitado|Redirecionar para o endereço de email de um administrador de segurança que sabe como determinar se o anexo é malware ou não|
|Resposta de anexos seguros de ATP se a verificação de malware para anexos expirar ou o erro ocorrer|Habilitado|Habilitado||

## <a name="miscellaneous-settings-for-eop-or-office-365-atp"></a>Configurações diversas para o EOP ou o Office 365 ATP

Estas configurações abrangem uma variedade de recursos que não se encaixam necessariamente em categorias específicas acima. Algumas das configurações são externas para o centro de conformidade de & de segurança.

Nome do recurso de segurança|Standard|Impede|Comentário|
|---------|---------|---------|---------|
|[Configurar o SPF no Office 365 para ajudar a evitar falsificações](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Sim|Sim||
|[Usar DKIM para validar emails enviados de seu domínio personalizado no Office 365](use-dkim-to-validate-outbound-email.md)|Sim|Sim||
|[Usar DMARC para validar emails no Office 365](use-dmarc-to-validate-email.md)|Sim|Sim|Use Action = Quarantine para Standard e Action = Reject para Strict.|
|Implantar o complemento de mensagens de relatório para aprimorar o relatório do usuário final de emails suspeitos|Sim|Sim||
|Agendar relatórios de malware e spam|Sim|Sim||
|O encaminhamento automático para domínios externos deve ser não permitido ou monitorado|Sim|Sim||
|A auditoria unificada deve ser habilitada|Sim|Sim||
|Conectividade IMAP para a caixa de correio|Desabilitado|Desabilitado||
|Conectividade POP para caixa de correio|Desabilitado|Desabilitado||
|Envio autenticado SMTP para a caixa de correio|Desabilitado|Desabilitado||
|Conectividade do EWS à caixa de correio|Desabilitado|Desabilitado||
|Conectividade do PowerShell|Desabilitado|Desabilitado||
|Usar a inteligência de falsificação para os remetentes da lista branca sempre que possível|Sim|Sim||
|Bloqueio de borda baseado em diretório (DBEB)|Habilitado|Habilitado|Tipo de domínio = autoritativo|
|[Configurar a autenticação multifator para todas as contas de administrador](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)|Habilitado|Habilitado||
