---
title: Práticas recomendadas para a configuração do EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Siga estas recomendações de práticas práticas para o Proteção do Exchange Online autônomo (EOP) para se configurar para o sucesso e evitar erros comuns de configuração.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 266da2d8fe6b8ede79e703e49e48d17fccdd2928
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537950"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>Práticas recomendadas para configurar o EOP autônomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
-  [Proteção do Exchange Online autônomo](exchange-online-protection-overview.md)

Siga estas recomendações de práticas práticas para o Proteção do Exchange Online autônomo (EOP) para se configurar para o sucesso e evitar erros comuns de configuração. Este tópico supõe que você já concluiu o processo de configuração. Se ainda não realizou a configuração da EOP, confira [Configurar seu serviço EOP](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Usar um domínio de teste

Recomendamos que você use um domínio de teste, subdomínio ou domínio de baixo volume para testar os recursos de serviço antes de implementá-los nos seus domínios com maior volume de produção.

## <a name="synchronize-recipients"></a>Sincronizar destinatários

Se sua organização tiver contas de usuário existentes em um ambiente do Active Directory local, você poderá sincronizar essas contas com Azure Active Directory na nuvem. Recomendamos o uso da sincronização de diretórios. Para saber mais sobre os benefícios de usar a sincronização de diretórios e ver as etapas para configurá-la, confira [Gerenciar usuários de email no EOP](manage-mail-users-in-eop.md).

## <a name="recommended-settings"></a>Configurações recomendadas

Capacitamos os administradores de segurança a personalizar suas configurações de segurança para atender às necessidades de sua organização. Embora, como regra geral, haja dois níveis de segurança no EOP e no Microsoft Defender para Office 365 que recomendamos: Padrão e Estrito. Essas configurações estão listadas nas configurações [recomendadas para EOP](recommended-settings-for-eop-and-office365.md)e Microsoft Defender para Office 365 segurança.

### <a name="miscellaneousnon-policy-settings"></a>Configurações diversas/não políticas

Essas configurações abrangem um intervalo de recursos que estão fora das políticas de segurança.

<br>

****

|Nome do recurso de segurança|Padrão|Estrito|Comentário|
|---|---|---|---|
|[Configurar o SPF para ajudar a prevenir falsificação](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Sim|Sim||
|[Usar DKIM para validar emails enviados de seu domínio personalizado no Office 365](use-dkim-to-validate-outbound-email.md)|Sim|Sim||
|[Usar DMARC para validar emails no Office 365](use-dmarc-to-validate-email.md)|Sim|Sim|Use `action=quarantine` para Standard e `action=reject` Strict.|
|Implante o [add-in de Mensagem de Relatório](enable-the-report-message-add-in.md) ou o [add-in Relatório phishing](enable-the-report-phish-add-in.md) para melhorar o relatório do usuário final de emails suspeitos|Sim|Sim||
|Agendar relatórios de malware e spam|Sim|Sim||
|O encaminhamento automático para domínios externos deve ser permitido ou monitorado|Sim|Sim||
|A Auditoria Unificada deve ser habilitada|Sim|Sim||
|[Conectividade IMAP à caixa de correio](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Desabilitada|Desabilitada||
|[Conectividade POP à caixa de correio](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Desabilitada|Desabilitada||
|Envio SMTP autenticado|Desabilitada|Desabilitada|O envio SMTP do cliente autenticado (também conhecido como envio SMTP do cliente ou AUTH SMTP) é necessário para clientes POP3 e IMAP4 e aplicativos e dispositivos que geram e enviam emails. <p> Para obter instruções para habilitar e desabilitar o AUTH SMTP global ou seletivamente, consulte [Enable or disable authenticated client SMTP submission in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission).|
|Conectividade EWS à caixa de correio|Desabilitada|Desabilitada|Outlook usa Exchange Web Services para configurações de livre/ocupado, fora do escritório e compartilhamento de calendário. Se você não puder desabilitar o EWS globalmente, terá as seguintes opções: <ul><li>Use [as políticas de autenticação](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) para impedir que o EWS use autenticação básica se seus clientes deem suporte à autenticação moderna (autenticação moderna).</li><li>Use [As Regras de Acesso para Cliente](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) para limitar o EWS a usuários específicos ou endereços IP de origem.</li><li>Controlar o acesso do EWS a aplicativos específicos globalmente ou por usuário. Para obter instruções, consulte [Control access to EWS in Exchange](/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange).</li></ul> <p> O [add-in](enable-the-report-message-add-in.md) de mensagem Relatório e o complemento Relatar [phishing](enable-the-report-phish-add-in.md) usam REST por padrão em ambientes com suporte, mas retornarão ao EWS se REST não estiver disponível. Os ambientes com suporte que usam REST são:<ul><li>Exchange Online</li><li>Exchange 2019 ou Exchange 2016</li><li>O Outlook atual para Windows de uma assinatura Microsoft 365 ou compra única Outlook 2019.</li><li>Atual Outlook para Mac de uma assinatura Microsoft 365 ou compra única Outlook para Mac 2016 ou posterior.</li><li>Outlook para iOS e Android</li><li>Outlook na Web</li></ul>|
|[Conectividade do PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell)|Desabilitada|Desabilitada|Disponível para usuários de caixa de correio ou usuários de email (objetos de usuário retornados pelo cmdlet [Get-User).](/powershell/module/exchange/get-user)|
|Use o [insight de inteligência de spoof](learn-about-spoof-intelligence.md) e a Lista de Locatários [Permitir/Bloquear](tenant-allow-block-list.md)para adicionar os senders à sua lista de permitir|Sim|Sim||
|[Bloqueio de Borda Baseado em Diretório (DBEB)](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|Habilitado|Habilitado|Tipo de Domínio = Autoritativo|
|[Configurar a autenticação multifatar para todas as contas de administrador](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)|Habilitado|Habilitado||
|

## <a name="troubleshooting"></a>Solução de problemas

Solucionar problemas gerais e tendências usando os relatórios no centro de administração. Encontre um ponto de dados específico sobre uma mensagem usando a ferramenta de Rastreamento de Mensagem. Saiba mais sobre relatórios em [Relatórios e rastreamento de mensagem no Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Saiba mais sobre a ferramenta de rastreamento de mensagens em Rastreamento de mensagens no Centro de [Conformidade & Segurança.](message-trace-scc.md)

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>Relatar falsos positivos e falsos negativos à Microsoft

Para ajudar a melhorar a filtragem de spam no serviço para todos, você deve relatar falsos positivos (emails bons marcados como ruins) e falsos negativos (email ruim permitido) para a Microsoft para análise. Para mais informações, confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="create-mail-flow-rules"></a>Criar regras de fluxo de emails

Crie regras de fluxo de emails (também conhecidas como regras de transporte) ou filtros personalizados para atender às suas necessidades comerciais.

Ao implementar uma nova regra à produção, selecione um dos modos de teste primeiro para ver o efeito da regra. Quando tiver a certeza de que a regra está funcionando da maneira pretendida, altere o modo de regra para **Forçar**.

Ao implementar novas regras, considere adicionar outras ações de **Gerar Relatório de Incidente** para monitorar a regra em ação.

Em ambientes híbridos em que sua organização inclui o Exchange local e Exchange Online, considere as condições que você usa nas regras de fluxo de emails. Se você quiser que as regras se apliquem a toda a organização, certifique-se de usar condições disponíveis no Exchange local e no Exchange Online. Embora a maioria das condições está disponível em ambos os ambientes, há algumas que estão disponíveis apenas em um ambiente ou em outro. Saiba mais em [Regras de fluxo de email (regras de transporte) em Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).