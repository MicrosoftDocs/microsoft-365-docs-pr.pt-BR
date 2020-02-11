---
title: Práticas recomendadas para configurar o EOP e o Office 365 ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Siga estas práticas recomendadas para a EOP (Proteção do Exchange Online) a fim de evitar erros comuns de configuração e obter êxito.
ms.openlocfilehash: b4b1f02e3b034b7e89d605a2164b6add3f20dae5
ms.sourcegitcommit: 3d17c1d6b80672719b1878e2f321f0de39595226
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887298"
---
# <a name="best-practices-for-configuring-eop-and-office-365-atp"></a>Práticas recomendadas para configurar o EOP e o Office 365 ATP

Siga estas práticas recomendadas para a EOP (Proteção do Exchange Online) a fim de evitar erros comuns de configuração e obter êxito. Este tópico supõe que você já concluiu o processo de configuração. Se ainda não realizou a configuração da EOP, confira [Configurar seu serviço EOP](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Usar um domínio de teste

Recomendamos que você use um domínio de teste, subdomínio ou domínio de baixo volume para testar os recursos de serviço antes de implementá-los nos seus domínios com maior volume de produção.

## <a name="synchronize-recipients"></a>Sincronizar destinatários

Se sua organização tiver contas de usuário existentes em um ambiente do Active Directory local, você poderá sincronizar essas contas no Azure Active Directory na nuvem. Recomendamos o uso da sincronização de diretórios. Para saber mais sobre os benefícios de usar a sincronização de diretórios e ver as etapas para configurá-la, confira [Gerenciar usuários de email no EOP](manage-mail-users-in-eop.md).

## <a name="recommended-settings"></a>Configurações recomendadas

Capacitamos os administradores de segurança a personalizar suas configurações de segurança para atender às necessidades de sua organização. Embora, como regra geral, há dois níveis de segurança no EOP e no Office 365 ATP que recomendamos: padrão e estrito. Essas configurações estão listadas nas [configurações recomendadas para o EOP e a segurança ATP do Office 365](recommended-settings-for-eop-and-office365-atp.md).

### <a name="miscellaneousnon-policy-settings"></a>Configurações diversas/não relacionadas à política

Estas configurações abrangem uma variedade de recursos fora das políticas de segurança.

|Nome do recurso de segurança|Standard|Impede|Comentário|
|---------|---------|---------|---------|
|[Configurar o SPF no Office 365 para ajudar a evitar falsificações](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Sim|Sim||
|[Usar DKIM para validar emails enviados de seu domínio personalizado no Office 365](use-dkim-to-validate-outbound-email.md)|Sim|Sim||
|[Usar DMARC para validar emails no Office 365](use-dmarc-to-validate-email.md)|Sim|Sim|Use Action = Quarantine para Standard e Action = Reject para Strict.|
|Implantar o complemento de mensagens de relatório para aprimorar o relatório do usuário final de emails suspeitos|Sim|Sim||
|Agendar relatórios de malware e spam|Sim|Sim||
|O encaminhamento automático para domínios externos deve ser não permitido ou monitorado|Sim|Sim||
|A auditoria unificada deve ser habilitada|Sim|Sim||
|[Conectividade IMAP para a caixa de correio](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Desabilitado|Desabilitado||
|[Conectividade POP para caixa de correio](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Desabilitado|Desabilitado||
|Envio autenticado SMTP para a caixa de correio|Desabilitado|Desabilitado||
|Conectividade do EWS à caixa de correio|Desabilitado|Desabilitado||
|[Conectividade do PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)|Desabilitado|Desabilitado|Disponível para usuários de caixa de correio ou usuários de email (objetos de usuário retornados pelo cmdlet [Get-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user) ).|
|Usar a inteligência de falsificação para os remetentes da lista branca sempre que possível|Sim|Sim||
|Bloqueio de borda baseado em diretório (DBEB)|Habilitado|Habilitado|Tipo de domínio = autoritativo|
|[Configurar a autenticação multifator para todas as contas de administrador](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)|Habilitado|Habilitado||

## <a name="troubleshooting"></a>Solução de problemas

Solucionar problemas gerais e tendências usando os relatórios no centro de administração. Encontre um ponto de dados específico sobre uma mensagem usando a ferramenta de Rastreamento de Mensagem. Saiba mais sobre relatórios em [Relatórios e rastreamento de mensagem no Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Saiba mais sobre a ferramenta de rastreamento de mensagens no [rastreamento de mensagens no centro de conformidade de & de segurança](message-trace-scc.md).

## <a name="reporting-false-positive-and-false-negatives-to-microsoft"></a>Relatar falsos positivos e falsos negativos para a Microsoft

Os administradores devem enviar falsos negativos (spam) e falsos positivos (não spam) para a Microsoft por meio do portal de envios do administrador. Emails, arquivos e URLs podem ser enviados para ajudar os administradores a determinar por que fornecemos ou não enviaram mensagens aos usuários finais. Para obter detalhes, consulte [como enviar spam, phishing, URLs e arquivos suspeitos para a verificação da Microsoft para o Office 365](admin-submission.md).

Os usuários finais também podem relatar diretamente falsos negativos (spam) e falsos positivos (não spam) para a Microsoft para análise quando eles descordam com verdicts fornecidos. Para obter detalhes, consulte [enviar mensagens de spam, não spam e golpes de phishing para a Microsoft para análise](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).

## <a name="create-mail-flow-rules"></a>Criar regras de fluxo de emails

Criar regras de fluxo de email ou filtros personalizados para atender às suas necessidades de negócios.

Ao implementar uma nova regra à produção, selecione um dos modos de teste primeiro para ver o efeito da regra. Quando tiver a certeza de que a regra está funcionando da maneira pretendida, altere o modo de regra para **Forçar**.

Ao implementar novas regras, considere adicionar outras ações de **Gerar Relatório de Incidente** para monitorar a regra em ação.

Em ambientes híbridos em que sua organização inclui o Exchange local e o Office 365, considere as condições que você usa nas regras de fluxo de emails. Se quiser que as regras sejam aplicadas a toda a organização, certifique-se de usar as condições que estão disponíveis no Exchange local e no Office 365. Enquanto a maioria das condições está disponível em ambos os ambientes, há alguns itens que estão disponíveis apenas em um ambiente ou no outro. Saiba mais em [regras de fluxo de emails (regras de transporte) no Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).
