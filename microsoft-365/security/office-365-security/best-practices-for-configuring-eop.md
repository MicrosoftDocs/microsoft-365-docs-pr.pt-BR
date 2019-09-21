---
title: Práticas recomendadas para a configuração do EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Siga estas práticas recomendadas para a EOP (Proteção do Exchange Online) a fim de evitar erros comuns de configuração e obter êxito.
ms.openlocfilehash: 30b956ff12b878d42971413fa4a2f610015d5c97
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072869"
---
# <a name="best-practices-for-configuring-eop"></a>Práticas recomendadas para a configuração do EOP
  
Siga estas práticas recomendadas para a EOP (Proteção do Exchange Online) a fim de evitar erros comuns de configuração e obter êxito. Recomendamos usar as configurações padrão como regra geral. Este tópico supõe que você já concluiu o processo de configuração. Se ainda não realizou a configuração da EOP, confira [Configurar seu serviço EOP](set-up-your-eop-service.md).
  
## <a name="use-a-test-domain"></a>Usar um domínio de teste

Recomendamos que você use um domínio de teste, subdomínio ou domínio de baixo volume para testar os recursos de serviço antes de implementá-los nos seus domínios com maior volume de produção.
  
## <a name="synchronize-recipients"></a>Sincronizar destinatários

Se sua organização tiver contas de usuário existentes em um ambiente local do Active Directory, você poderá sincronizar essas contas com o Azure Active Directory na nuvem. Recomendamos o uso da sincronização de diretórios. Para saber mais sobre os benefícios de usar a sincronização de diretórios e ver as etapas para configurá-la, confira [Gerenciar usuários de email no EOP](manage-mail-users-in-eop.md).
  
## <a name="spf-record-customization-to-help-prevent-spoofing"></a>Personalização de registro SPF para ajudar a evitar falsificação

Quando você configurou a EOP, adicionou um registro SPF (estrutura de diretiva de remetente) da EOP aos seus registros DNS. O registro SPF ajuda a evitar a falsificação. Para obter mais informações sobre como um registro SPF impede o spoofing e como você pode adicionar seus endereços IP locais ao registro SPF, consulte [set up SPF in Office 365 para ajudar a impedir a falsificação](set-up-spf-in-office-365-to-help-prevent-spoofing.md). 
  
## <a name="set-anti-spam-options"></a>Definir as opções de antispam

Gerencie as configurações de filtro de conexão adicionando endereços IP das listas de IPs Permitidos e de IPs Bloqueados e selecionando a opção **Habilitar lista de confiança**, o que deve reduzir o número de falsos positivos (emails bons que são classificados como spam) recebidos. Saiba mais em [Configurar a política de filtro de conexão](configure-the-connection-filter-policy.md). Para saber mais sobre configurações de spam que se aplicam a toda a organização, confira [como impedir que emails reais sejam marcados como spam no office 365](../../compliance/prevent-email-from-being-marked-as-spam.md) ou [como reduzir emails de spam no Office 365](reduce-spam-email.md)). Esses tópicos serão úteis se você tiver controle de nível de administrador e quiser impedir falsos positivos ou falsos negativos.
  
Gerencie seus filtros de conteúdo examinando e opcionalmente alterando as configurações padrão. Por exemplo, você pode alterar a ação para o que acontece com as mensagens detectadas por spam. Se você quiser buscar uma abordagem agressiva para a filtragem de spam, configure opções avançadas de filtragem de spam. Recomendamos que você teste essas opções primeiro antes de implementá-las em seu ambiente de produção (ligando-as), recomenda-se que as organizações que se preocupam com phishing ativem a opção **registro SPF: falha** grave. Saiba mais em [configurar suas políticas de filtro de spam](configure-your-spam-filter-policies.md) e [Opções avançadas de filtragem de spam](advanced-spam-filtering-asf-options.md).
  
> [!IMPORTANT]
> Se você estiver usando a ação de filtro de conteúdo padrão, **mover mensagem para a pasta lixo eletrônico**, para garantir que esta ação funcione com caixas de correio locais, você deve configurar regras de fluxo de emails (também conhecidas como regras de transporte) em seu Exchange local servidores para detectar cabeçalhos de spam adicionados pelo EOP. Para obter detalhes, consulte [Garantir que o spam seja direcionado para a pasta Lixo Eletrônico de cada usuário](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).
  
Recomendamos que você revise as [perguntas frequentes de proteção](anti-spam-protection-faq.md)antispam, incluindo a seção práticas recomendadas de envio de mensagens de saída, o que ajudará a garantir que seu email de saída seja entregue.
  
Você pode enviar falsos negativos (spam) e falsos positivos (não spam) para a Microsoft para análise de várias maneiras. Para obter detalhes, consulte [enviar mensagens de spam, não spam e golpes de phishing para a Microsoft para análise](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).
  
## <a name="set-anti-malware-options"></a>Definir opções de antimalware

Revise e ajuste as suas configurações de filtro de malware no EAC (Centro de administração do Exchange). Saiba mais em [Configure anti-malware Policies](configure-anti-malware-policies.md). Recomendamos também ler sobre outras perguntas frequentes e respostas referentes à proteção antimalware em nossas [perguntas frequentes de proteção contra malware ](anti-malware-protection-faq-eop.md).
  
Se estiver preocupado com arquivos executáveis que contêm malware, poderá criar uma regra de fluxo de emails do Exchange para bloquear os anexos de email que incluam conteúdo executável. Siga as etapas em [como reduzir as ameaças de malware através do bloqueio de anexo de arquivo no Exchange Online Protection](https://support.microsoft.com/kb/2959596) para bloquear os tipos de arquivo listados em [usar regras de fluxo de emails para inspecionar anexos de mensagens no Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).
  
Você pode usar o Filtro de Tipos de Anexos Comuns no EAC. Selecione **proteger** \> **filtros de malware**. Você pode criar uma regra de fluxo de emails que bloqueia qualquer anexo de email que tenha conteúdo executável.
  
Para aumentar a proteção, recomendamos também que você use regras de fluxo de emails para bloquear algumas ou todas as seguintes extensões: ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh. Isso pode ser feito usando a condição **Qualquer extensão de arquivo de anexo que inclua essas palavras**.
  
Os administradores e usuários finais podem enviar um malware que passou por filtros anteriores ou enviar um arquivo que você acha que foi identificado incorretamente como malware, enviando-o para a Microsoft para análise. Para saber mais, confira [Submitting malware and non-malware to Microsoft for analysis](submitting-malware-and-non-malware-to-microsoft-for-analysis.md).
  
## <a name="create-mail-flow-rules"></a>Criar regras de fluxo de emails

Criar regras de fluxo de email ou filtros personalizados para atender às suas necessidades de negócios.
  
Ao implementar uma nova regra à produção, selecione um dos modos de teste primeiro para ver o efeito da regra. Quando tiver a certeza de que a regra está funcionando da maneira pretendida, altere o modo de regra para **Forçar**.
  
Ao implementar novas regras, considere adicionar outras ações de **Gerar Relatório de Incidente** para monitorar a regra em ação.
  
Se estiver configurando uma implantação híbrida, com parte da organização no local e parte no Office 365, poderá criar regras que se apliquem a toda a empresa. Para fazer isso, use as condições que estão disponíveis no local e no Office 365. Embora a maioria das condições esteja disponível para ambas as implantações, há um pequeno conjunto específico para um determinado cenário de implantação. Saiba mais em [regras de fluxo de emails (regras de transporte) no Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).
  
Se desejar inspecionar anexos de mensagens de email em trânsito na sua organização, você poderá fazê-lo configurando regras de fluxo de emails. Em seguida, você poderá tomar as devidas providências nas mensagens inspecionadas com base no conteúdo ou nas características desses anexos. Saiba mais em [usar regras de fluxo de email para inspecionar anexos de mensagens no Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments).
  
### <a name="phishing-and-spoofing-prevention"></a>Prevenção contra phishing e falsificação

Você pode melhorar a proteção anti-phishing detectando quando informações pessoais saem da organização em um email. Por exemplo, você pode usar as expressões regulares a seguir em regras de fluxo de emails para detectar a transmissão de dados financeiros pessoais ou informações que podem comprometer a privacidade:
  
- `\d\d\d\d\s\d\d\d\d\s\d\d\d\d\s\d\d\d\d`(MasterCard ou Visa)

- `\d\d\d\d\s\d\d\d\d\d\d\s\d\d\d\d\d`(American Express)

- `\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d`(qualquer número de 16 dígitos)

- `\d\d\d\-\d\d\-\d\d\d\d`(Números de seguro social)

Campanhas bem-sucedidas de spam e phishing também podem ser reduzidas bloqueando emails de entrada e mal-intencionados que parecem ter sido enviados de seu próprio domínio. Por exemplo, você pode criar uma regra de fluxo de emails que rejeita mensagens do domínio de sua empresa enviadas para o mesmo domínio da empresa para bloquear este tipo de falsificação.
  
> [!CAUTION]
> Recomendamos criar esta regra de rejeição apenas nos casos em que você tem certeza de que nenhum email legítimo do seu domínio é enviado da Internet para seu servidor de emails. Isso pode acontecer nos casos em que uma mensagem é enviada de um usuário na sua organização para um destinatário externo e posteriormente encaminhada para outro destinatário na organização. 
  
### <a name="extension-blocking"></a>Bloqueio de Extensão

Se você estiver preocupado em relação a arquivos executáveis contendo malware, é possível configurar políticas anti-malware para bloquear qualquer anexo de email que contenha conteúdo executável. Siga as etapas em [Configure anti-malware Policies](configure-anti-malware-policies.md).
  
Para maior proteção, nós também recomendamos que você bloqueie algumas ou todas as extensões a seguir: ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh.
  
## <a name="reporting-and-troubleshooting"></a>Relatórios e solução de problemas

Solucionar problemas gerais e tendências usando os relatórios no centro de administração. Encontre um ponto de dados específico sobre uma mensagem usando a ferramenta de Rastreamento de Mensagem. Saiba mais sobre relatórios em [Relatórios e rastreamento de mensagem no Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Saiba mais sobre a ferramenta de Rastreamento de Mensagem em [Trace an Email Message](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message).
  
## <a name="for-more-information"></a>Para saber mais

[Perguntas frequentes gerais sobre o EOP](eop-general-faq.md)
  
[Ajuda e suporte para EOP](help-and-support-for-eop.md)
  
[Como impedir que emails reais sejam marcados como spam no Office 365](../../compliance/prevent-email-from-being-marked-as-spam.md)
  
[Como reduzir emails de spam no Office 365](reduce-spam-email.md)
