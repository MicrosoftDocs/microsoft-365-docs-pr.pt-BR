---
title: Práticas recomendadas para a configuração do EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Siga estas recomendações de práticas recomendadas para proteção autônoma do Exchange Online (EOP) a fim de configurar o sucesso e evitar erros de configuração comuns.
ms.openlocfilehash: e5e87883e9c8aad21552ebf306a9716f14532884
ms.sourcegitcommit: 9ea67fd2e02af760d4fb62e3d09c93b446173f9d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2020
ms.locfileid: "44739092"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>Práticas recomendadas para configurar o EOP autônomo

Siga estas recomendações de práticas recomendadas para proteção autônoma do Exchange Online (EOP) a fim de configurar o sucesso e evitar erros de configuração comuns. Este tópico supõe que você já concluiu o processo de configuração. Se ainda não realizou a configuração da EOP, confira [Configurar seu serviço EOP](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Usar um domínio de teste

Recomendamos que você use um domínio de teste, subdomínio ou domínio de baixo volume para testar os recursos de serviço antes de implementá-los nos seus domínios com maior volume de produção.

## <a name="synchronize-recipients"></a>Sincronizar destinatários

Se sua organização tiver contas de usuário existentes em um ambiente do Active Directory local, você poderá sincronizar essas contas no Azure Active Directory na nuvem. Recomendamos o uso da sincronização de diretórios. Para saber mais sobre os benefícios de usar a sincronização de diretórios e ver as etapas para configurá-la, confira [Gerenciar usuários de email no EOP](manage-mail-users-in-eop.md).

## <a name="recommended-settings"></a>Configurações recomendadas

Capacitamos os administradores de segurança a personalizar suas configurações de segurança para atender às necessidades de sua organização. Embora, como regra geral, há dois níveis de segurança no EOP e no Office 365 ATP que recomendamos: padrão e estrito. Essas configurações estão listadas nas [configurações recomendadas para o EOP e a segurança ATP do Office 365](recommended-settings-for-eop-and-office365-atp.md).

### <a name="miscellaneousnon-policy-settings"></a>Configurações diversas/não relacionadas à política

Estas configurações abrangem uma variedade de recursos fora das políticas de segurança.

|||||
|---|---|---|---|
|**Nome do recurso de segurança**|**Standard**|**Impede**|**Comment**|
|[Configure o SPF para ajudar a evitar falsificações](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Sim|Sim||
|[Usar DKIM para validar emails enviados de seu domínio personalizado no Office 365](use-dkim-to-validate-outbound-email.md)|Sim|Sim||
|[Usar DMARC para validar emails no Office 365](use-dmarc-to-validate-email.md)|Sim|Sim|Use `action=quarantine` para padrão e `action=reject` para estrito.|
|Implantar o [suplemento de mensagem de relatório](enable-the-report-message-add-in.md) para melhorar o relatório do usuário final de emails suspeitos|Sim|Sim||
|Agendar relatórios de malware e spam|Sim|Sim||
|O encaminhamento automático para domínios externos deve ser não permitido ou monitorado|Sim|Sim||
|A auditoria unificada deve ser habilitada|Sim|Sim||
|[Conectividade IMAP para a caixa de correio](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Desabilitado|Desabilitado||
|[Conectividade POP para caixa de correio](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Desabilitado|Desabilitado||
|Envio SMTP autenticado|Desabilitado|Desabilitado|O envio SMTP de cliente autenticado (também conhecido como Envio SMTP de cliente ou autenticação SMTP) é necessário para que clientes POP3 e IMAP4 enviem email.|
|Conectividade do EWS à caixa de correio|Desabilitado|Desabilitado||
|[Conectividade do PowerShell](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)|Desabilitado|Desabilitado|Disponível para usuários de caixa de correio ou usuários de email (objetos de usuário retornados pelo cmdlet [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user) ).|
|Usar o [spoof Intelligence](learn-about-spoof-intelligence.md) para adicionar remetentes à sua lista de permissões|Sim|Sim||
|[Bloqueio de borda baseado em diretório (DBEB)](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|Habilitado|Habilitado|Tipo de domínio = autoritativo|
|[Configurar a autenticação multifator para todas as contas de administrador](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)|Habilitado|Habilitado||
|

## <a name="troubleshooting"></a>Solução de problemas

Solucionar problemas gerais e tendências usando os relatórios no centro de administração. Encontre um ponto de dados específico sobre uma mensagem usando a ferramenta de Rastreamento de Mensagem. Saiba mais sobre relatórios em [Relatórios e rastreamento de mensagem no Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Saiba mais sobre a ferramenta de rastreamento de mensagens no [rastreamento de mensagens no centro de conformidade de & de segurança](message-trace-scc.md).

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>Relatar falsos positivos e falsos negativos à Microsoft

Para ajudar a melhorar a filtragem de spam no serviço para todos, você deve relatar falsos positivos (emails satisfatórios marcados como defeituosos) e falsos negativos (emails inválidos permitidos) para a Microsoft para análise. Para mais informações, confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="create-mail-flow-rules"></a>Criar regras de fluxo de emails

Criar regras de fluxo de emails (também conhecidas como regras de transporte) ou filtros personalizados para atender às suas necessidades de negócios.

When you deploy a new rule to production, select one of the test modes first to see the effect of the rule. Once you are satisfied that the rule is working in the manner intended, change the rule mode to **Enforce**.

Ao implementar novas regras, considere adicionar outras ações de **Gerar Relatório de Incidente** para monitorar a regra em ação.

Em ambientes híbridos em que sua organização inclui o Exchange local e o Exchange Online, considere as condições que você usa nas regras de fluxo de emails. Se quiser que as regras sejam aplicadas a toda a organização, certifique-se de usar as condições que estão disponíveis no Exchange local e no Exchange Online. Enquanto a maioria das condições está disponível em ambos os ambientes, há alguns itens que estão disponíveis apenas em um ambiente ou no outro. Saiba mais em [regras de fluxo de emails (regras de transporte) no Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).
