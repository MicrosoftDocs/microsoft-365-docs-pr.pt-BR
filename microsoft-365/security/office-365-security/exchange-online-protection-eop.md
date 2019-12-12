---
title: Proteção do Exchange Online
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 70ab4af2-fec4-4886-8e12-27d348649204
description: Veja algumas coisas que você deve estar ciente antes de começar a trabalhar com o EOP.
ms.openlocfilehash: ae08ff17a3ef25f0b0903d02ffe396cd201bd06c
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970517"
---
# <a name="exchange-online-protection"></a>Proteção do Exchange Online

Bem-vindo ao serviço de filtragem de email hospedado no Microsoft Proteção do Exchange Online (EOP) . Aqui estão algumas coisas que você deve estar ciente antes de começar a trabalhar com o EOP e usar o seu conteúdo:

- Para saber mais sobre o EOP, confira a [Descrição do serviço de proteção do Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). Outros recursos úteis são o [Visão geral do Exchange Online Protection](exchange-online-protection-overview.md), [Perguntas frequentes gerais sobre o EOP](eop-general-faq.md) e [Recursos EOP](eop-features.md), além da [página inicial do Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection).

- Para começar com o EOP, os novos clientes devem dirigir-se ao [Configurar seu serviço EOP](set-up-your-eop-service.md). Este tópico fornece passos que vão ajudá-lo colocar o EOP em funcionamento.

- Se você precisar de mais ajuda ou deseja compartilhar ideias, o [Fórum de EOP](https://go.microsoft.com/fwlink/?LinkId=285351) é um ótimo lugar para começar.

## <a name="eop-help-for-administrators"></a>Ajuda do EOP para administradores

O conteúdo da Ajuda para administradores do EOP é composta pelas seguintes categorias de primeiro nível:

- [Visão geral do Exchange Online Protection](exchange-online-protection-overview.md): apresenta como o EOP funciona e fornece links para informações adicionais.

- [Recursos do EOP](eop-features.md): fornece uma lista de recursos disponíveis no EOP.

- [Set up your EOP Service](set-up-your-eop-service.md): fornece etapas para configurar o seu serviço do EOP e links para informações adicionais.

- [Vá para EOP do Google Postini, firewall de vírus e spam de Barracuda ou Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md): descreve o processo para mudar para EOP de outro produto de proteção de email.

- [Gerenciar destinatários e grupos de funções de administrador no EOP](manage-recipients-and-admin-role-groups-in-eop.md): descreve como gerenciar destinatários e como atribuir usuários a grupos de funções de administrador.

- [Fluxo de email no EOP](mail-flow-in-eop.md): descreve como configurar cenários de fluxo de email personalizados usando conectores, como gerenciar domínios associados ao serviço e como habilitar o recurso bloqueio de borda baseado em diretório (DBEB).

- [Práticas recomendadas para a configuração do EOP](best-practices-for-configuring-eop.md): descreve as definições de configuração e considerações recomendadas para depois de configurar e provisionar o serviço.

- [Políticas e conformidade de mensagens no EOP](messaging-policy-and-compliance-in-eop.md): descreve como usar as regras de fluxo de emails do Exchange (também conhecidas como regras de transporte) para impor políticas e regulamentações específicas da empresa e como usar relatórios de auditoria para rastrear as alterações de configuração para o serviço.

- [Anti-spam and Anti-Malware Protection in Office 365](anti-spam-and-anti-malware-protection.md): descreve a filtragem de spam e a filtragem de malware e mostra como personalizá-las para melhor atender às necessidades da sua organização. Descreve também as tarefas que os administradores e usuários finais podem realizar em mensagens em quarentena.

- [Relatórios e rastreamento de mensagens no Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): descreve os relatórios e as ferramentas de solução de problemas disponíveis.

- [Centro de administração do Exchange no Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md): descreve como acessar e navegar pela interface de gerenciamento do centro de administração do Exchange para gerenciar seu serviço do EOP.

- [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell): fornece informações sobre o PowerShell remoto, que permite gerenciar seu serviço do EOP a partir da linha de comando.

- [Ajuda e suporte para EOP](help-and-support-for-eop.md) Fornece informações sobre como obter ajuda e suporte técnico.

## <a name="eop-help-for-end-users"></a>Ajuda do EOP para usuários finais

O conteúdo da Ajuda para auxiliar usuários finais do EOP a gerenciar spam é composto pelos seguintes tópicos:

- [Localizar e liberar mensagens em quarentena como um usuário](find-and-release-quarantined-messages-as-a-user.md): descreve como os usuários finais podem localizar e liberar suas próprias mensagens em quarentena de spam na interface de usuário de quarentena de spam e, opcionalmente, relatá-las como não sendo lixo eletrônico para a Microsoft.

- [Enviar mensagens de spam, não spam e golpes de phishing para a Microsoft para análise](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md): descreve as diferentes maneiras como os usuários finais podem enviar mensagens de spam (lixo eletrônico) e não spam (não lixo eletrônico) para a Microsoft. Este tópico inclui links para as ferramentas de relatório disponíveis no Microsoft Outlook e no Outlook na Web (anteriormente conhecido como Outlook Web App).

- [Enviando malware e não malware para a Microsoft para análise](submitting-malware-and-non-malware-to-microsoft-for-analysis.md): descreve como os usuários finais podem enviar malwares que o fizeram após os filtros ou enviar um arquivo que foi identificado incorretamente como malware.

- Os usuários finais podem adicionar usuários ou domínios específicos a uma lista de remetentes seguros ou uma lista de remetentes bloqueados Configurando suas configurações de lixo eletrônico no Outlook ou no Outlook na Web. Observe que as mensagens enviadas de remetentes bloqueados são marcadas como spam, não rejeitadas, o que significa que elas podem ser recuperadas da pasta de lixo eletrônico ou quarentena (dependendo de onde o administrador configurou o serviço para enviar spam.) Para obter mais informações, consulte [use the Report Message Add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).

- [Ajuda e suporte para EOP](help-and-support-for-eop.md) Fornece informações sobre como obter ajuda e suporte técnico.
