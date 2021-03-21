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
description: Siga estas recomendações de práticas práticas para o EOP (Proteção autônoma do Exchange Online) para se configurar para obter êxito e evitar erros comuns de configuração.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6a6a9fd0dfc654ca37fdd5168b3ecc0c4486f9d0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924451"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>Práticas recomendadas para configurar o EOP autônomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
-  [Proteção autônoma do Exchange Online](exchange-online-protection-overview.md)

Siga estas recomendações de práticas práticas para o EOP (Proteção autônoma do Exchange Online) para se configurar para obter êxito e evitar erros comuns de configuração. Este tópico supõe que você já concluiu o processo de configuração. Se ainda não realizou a configuração da EOP, confira [Configurar seu serviço EOP](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Usar um domínio de teste

Recomendamos que você use um domínio de teste, subdomínio ou domínio de baixo volume para testar os recursos de serviço antes de implementá-los nos seus domínios com maior volume de produção.

## <a name="synchronize-recipients"></a>Sincronizar destinatários

Se sua organização tiver contas de usuário existentes em um ambiente do Active Directory local, você poderá sincronizar essas contas com o Azure Active Directory na nuvem. Recomendamos o uso da sincronização de diretórios. Para saber mais sobre os benefícios de usar a sincronização de diretórios e ver as etapas para configurá-la, confira [Gerenciar usuários de email no EOP](manage-mail-users-in-eop.md).

## <a name="recommended-settings"></a>Configurações recomendadas

Capacitamos os administradores de segurança a personalizar suas configurações de segurança para atender às necessidades de sua organização. Embora, como regra geral, haja dois níveis de segurança no EOP e no Microsoft Defender para Office 365 que recomendamos: Padrão e Estrito. Essas configurações estão listadas nas configurações recomendadas para [segurança do EOP e do Microsoft Defender para Office 365.](recommended-settings-for-eop-and-office365-atp.md)

### <a name="miscellaneousnon-policy-settings"></a>Configurações diversas/não políticas

Essas configurações abrangem um intervalo de recursos que estão fora das políticas de segurança.

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
|[Conectividade IMAP à caixa de correio](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Desabilitado|Desabilitado||
|[Conectividade POP à caixa de correio](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Desabilitado|Desabilitado||
|Envio SMTP autenticado|Desabilitado|Desabilitado|O envio SMTP do cliente autenticado (também conhecido como envio SMTP do cliente ou AUTH SMTP) é necessário para que os clientes POP3 e IMAP4 enviem emails.|
|Conectividade EWS à caixa de correio|Desabilitado|Desabilitado||
|[Conectividade do PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell)|Desabilitado|Desabilitado|Disponível para usuários de caixa de correio ou usuários de email (objetos de usuário retornados pelo cmdlet [Get-User).](/powershell/module/exchange/get-user)|
|Usar [a inteligência de spoof](learn-about-spoof-intelligence.md) para adicionar os envios à sua lista de permitir|Sim|Sim||
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

Em ambientes híbridos em que sua organização inclui o Exchange local e o Exchange Online, considere as condições que você usa nas regras de fluxo de emails. Se você quiser que as regras se apliquem a toda a organização, certifique-se de usar as condições disponíveis no Exchange local e no Exchange Online. Embora a maioria das condições está disponível em ambos os ambientes, há algumas que estão disponíveis apenas em um ambiente ou em outro. Saiba mais em [Regras de fluxo de email (regras de transporte) no Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).