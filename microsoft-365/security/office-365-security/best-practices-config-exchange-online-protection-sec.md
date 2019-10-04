---
title: Práticas recomendadas de configuração para o EOP e o Office 365 ATP Security, práticas recomendadas, configurações, recomendações, estrutura de política de remetente, relatório e conformidade de mensagens baseadas em domínio, DomainKeys identificadas email, etapas, como funciona,
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 09/18/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: Quais são as práticas recomendadas para as configurações de segurança do Exchange Online Protection (EOP) e da proteção avançada contra ameaças (ATP)? O que é recomendado? O que deve ser usado agressivamente? E quais são os extras obtidos se você também usa a proteção avançada contra ameaças (ATP)?
ms.openlocfilehash: fb6a39756c54e46f5ac8208c9c92af30bc144a57
ms.sourcegitcommit: d4aa94716b33e6c270ae7adfbdc4c19cf4a0087d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2019
ms.locfileid: "37387144"
---
# <a name="best-practices-for-configuring-eop-and-office-365-atp-security"></a>Práticas recomendadas para configurar a segurança do EOP e do Office 365 ATP

O Exchange Online Protection (EOP) é o núcleo de segurança para assinaturas E3 do Office 365. É opcional, e até mesmo incentivamos os clientes do E3 a comprar uma assinatura para a proteção avançada contra ameaças do Office 365 (ATP), ex. Plano ATP 1 ou plano ATP 2 para aproveitar a segurança adicional disponível nas assinaturas do E5 Office 365.

Discutiremos dois níveis de segurança, chamados recomendados e agressivos no EOP, abrangendo comentários sobre como usar os recursos nos dois níveis de segurança. As seções começam com validação e autenticação de email, que envolvem algumas reformulação fora do Office 365, no DNS e protegem os emails de saída, tornando os locatários bons para os recursos que enviam. Essas configurações melhor protegem sua assinatura.


## <a name="email-authentication"></a>Autenticação de email

SPF, DKIM e DMARC são acrônimos para a estrutura de política de remetente, DomainKeys identificadas por email e autenticação de mensagens baseadas em domínio, relatórios e conformidade (bastante mouthful) e são a base da autenticação e validação de email.

Esses métodos tratam de email de saída do Office 365 e os sistemas de destino de ajuda confiam que os emails do seu domínio sejam válidos. Eles são as únicas práticas recomendadas que envolveremos as configurações a serem feitas *fora* do Office 365, em seu DNS. Para obter etapas de configuração específicas, consulte a seção [validação de email e autenticação](https://docs.microsoft.com/en-us/office365/securitycompliance/how-office-365-uses-spf-to-prevent-spoofing) no Sumário de segurança e conformidade.


|Nome do recurso de segurança  |Recomendado |Atraente  |Comentário  |
|---------|---------|---------|---------|
|[Criar registros SPF](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)    | S        |    S     |   -      |
|[Configurar a assinatura do DKIM para domínios](https://docs.microsoft.com/en-us/office365/securitycompliance/use-dkim-to-validate-outbound-email)     |  S       |    S     |  -       |
|[Implementar DMARC com ação rejeitar ou quarentena](https://docs.microsoft.com/en-us/office365/securitycompliance/use-dmarc-to-validate-email)     |   S      |     S    |   Use Action = None para recomendado e Action = Reject for agressivo.     |

> [!IMPORTANT]
> Para trabalhar com direitos e permissões de segurança, verifique se você tem a função ou as funções corretas no Office 365 ou no centro de segurança e conformidade. Se você for um *administrador de segurança* no Azure Active Directory, um *Administrador Global* no Office 365 ou um *gerente organizacional* do Exchange Online no Exchange Online/Exchange Online PowerShell, você está pronto para começar.

## <a name="anti-spam-anti-malware-and-anti-phishing"></a>Anti-spam, Antimalware e anti-phishing

O anti-spam e o antimalware são recursos do EOP. Filtragem de spam, por padrão no Office 365, examina todos os emails e atribui um valor de número de SCL (nível de confiança de spam) a cada email. Apenas para esclarecer, sua finalidade é enumerar a confiança do filtro de que o email é (ou não) spam. Valores baixos, como-1, são não spams de remetentes confiáveis e territórios em uma caixa de entrada do usuário. Recordes, como 7, 8 ou 9 são altamente suspeitos, ou remetentes de spam conhecidos e cabeçalhos para o lixo eletrônico de um usuário ou quarentena acessível pelo administrador.

A filtragem de malware também está ativada por padrão no Office 365. Como a filtragem antispam, os filtros Antimalware funcionam em emails de entrada e de saída. Em ambos os casos, essa proteção pode ser configurada para um melhor ajuste, por administradores.

Os filtros do phising são ativados por padrão no Office 365, mas devem ser configurados para um melhor ajuste. Veja o que recomendamos para anti-phishing no EOP.

### <a name="anti-spam"></a>Antispam

|Nome do recurso de segurança  |Recomendado |Atraente  |Comentário  |
|---------|---------|---------|---------|
|Período de retenção de quarentena    |   S      |     S    |   30 dias   |
|Frequência de notificação de spam do usuário final   |   S      |     S    |   3 dias   |
|A exclusão autolimpa de zero horas deve ser habilitada   |   S      |     S    |   True  |
|A ação de detecção de spam deve ser enviada para | JMF | Quarentena | - |
|A ação de detecção de spam de alta confiança deve ser enviada para | Quarentena | Quarentena| - |
|A ação de detecção em massa deve ser definida como | JMF | Quarentena | - |
|Definir o limite de email em massa para | 6 | quatro | - |
|Dicas de segurança devem ser habilitadas| Verdadeiro | Verdadeiro | - |
|Habilitar notificação de spam do usuário final| True | Falso | - |
|Remetentes permitidos | Nenhum | Nenhum | - |
|Domínios de remetentes permitidos | Nenhum | Nenhum | - |
|Remetentes bloqueados | Nenhum | Nenhum | - |
|Domínios de remetentes bloqueados | Nenhum | Nenhum | - |
|RRL da política de spam de saída | 500 | 500 | - |

Recomendado para **desativado** nos níveis recomendados e agressivos:

|Nome do recurso de segurança  |
|---------|
|IncreaseScoreWithImageLinks|
|IncreaseScoreWithNumericIps|
|IncreaseScoreWithRedirectToOtherPort|
|IncreaseScoreWithBizOrInfoUrls|
|MarkAsSpamEmptyMessages|
|MarkAsSpamJavaScriptInHtml|
|MarkAsSpamFramesInHtml|
|MarkAsSpamObjectTagsInHtml|
|MarkAsSpamEmbedTagsInHtml|
|MarkAsSpamFormTagsInHtml|
|MarkAsSpamWebBugsInHtml|
|MarkAsSpamSensitiveWordList|
|MarkAsSpamFromAddressAuthFail|
|MarkAsSpamNdrBackscatter|

Recomendado para **ativado** nos níveis recomendado e agressivo:

|Nome do recurso de segurança  |
|---------|
|MarkAsSpamSpfRecordHardFail|
|MarkAsSpamBulkMail|

### <a name="anti-malware"></a>Anti-malware

|Nome do recurso de segurança  |Recomendado |Atraente  |Comentário  |
|---------|---------|---------|---------|
|Configurar notificações de malware para fontes internas |Sim |Sim |- |
|Desabilitar a notificação de remetentes externos de detecção de malware |Sim |Sim |- |
|Use "filtro de tipo de anexo comum" para bloquear tipos de arquivo suspeitos | Sim |Sim |- |
|ZAP de malware |Verdadeiro |Verdadeiro |- |
|Ação de malware |Bloquear |Bloquear |- |

### <a name="anti-phishing"></a>Anti-phishing

|Nome do recurso de segurança  |Recomendado |Atraente  |Comentário  |
|---------|---------|---------|---------|
|A autolimpeza de zero horas deve estar habilitada-Phish| Verdadeiro | Verdadeiro | - | 
|A ação de detecção de phishing deve ser definida como | Quarantine-Request | Quarantine-admin | - |
|A ação de detecção de phishing de alta confiança deve ser definida como | Quarantine-admin | Quarantine-admin | - |
|EnableMailboxIntelligence | Verdadeiro | Verdadeiro | - |
|EnableSimilarUsersSafetyTips | Verdadeiro | Verdadeiro | - |
|EnableSimilarDomainsSafetyTips | Verdadeiro | Verdadeiro | - |
|EnableUnusualCharactersSafetyTips | Verdadeiro | Verdadeiro | - |
|TargetedUserProtectionAction |NoAction |Bloquear | - |
|MailboxIntelligenceProtectionAction |NoAction |Bloquear | - |
|TargetedDomainProtectionAction |NoAction |Bloquear | - |
|AuthenticationFailAction |MoveToJmf |Quarentena | - |
|AntiSpoofEnforcementType |Alto |Alto | - |
|EnableAuthenticationSafetyTip |Falso |True | - |
|EnableAntiSpoofEnforcement |Verdadeiro |Verdadeiro | - |
|EnableUnauthenticatedSender |Verdadeiro |Verdadeiro | - |
|EnableAuthenticationSoftPassSafetyTip |Falso |True | - |
|TreatSoftPassAsAuthenticated |True |Falso | - |
|EnableSuspiciousSafetyTip |Verdadeiro |Verdadeiro | - |

## <a name="office-365-advanced-threat-protection-atp-security"></a>Segurança de proteção avançada contra ameaças (ATP) do Office 365

Anteriormente, disse que foi incentivamos que as assinaturas E3 adicionem um plano de ATP 1 do Office 365 ou o plano ATP 2 mais completo. O anti-phishing avançado é um motivo pelo qual. Habilitado por padrão, o anti-phishing ***deve*** ser configurado com políticas para operar. Esquecer de configurar políticas anti-phishing expõe os usuários a riscos, certifique-se de que a etapa 2 depois de adicionar uma assinatura ATP.

> [!IMPORTANT]
>  Se você tiver uma assinatura e5, você tem o [plano ATP 2](https://products.office.com/en-us/exchange/advance-threat-protection)no momento. Marque este link quando quiser descobrir [o que há de novo na ATP](https://review.docs.microsoft.com/en-us/microsoft-365/security/office-365-security/whats-new-in-office-365-atp?branch=oatp-newstuff).

### <a name="advanced-anti-phishing"></a>Anti-phishing avançado

Phishing é uma tentativa de se mascarar como uma pessoa ou empresa respeitável pelo objetivo de roubar informações pessoais, como números de cartões de crédito, ou Pins ou senhas de computador ou dispositivo. O phishing pode envolver:

- **Falsificação**, onde os falsificadores tentam enviar emails em nome de um destino específico em um domínio (por exemplo, ellar@2020contoso.com tentando enviar email para ellar@2020litware.com (um cenário, os métodos de autenticação de email podem ajudar a frustrar). 

- **Representação**, onde mail é recebido, cujo remetente é visualmente semelhante (ou semelhante) a um domínio ou nome de usuário de destino. O ator ruim aqui, imita um nome de usuário específico ou finge o envio de emails de um domínio de destino. Aqui está um domínio do Pretense: ellar @ 2020 | itware. com e aqui está um Pretense usuário: ellαr @ 2020litware. com (examine atentamente os nomes de domínio e de usuário nesses exemplos para capturar a representação de domínio e de usuário).

Se você tiver adicionado uma assinatura ATP do Office 365 ao seu EOP, certifique-se de definir as configurações a seguir.

|Nome do recurso de segurança  |Recomendado |Atraente  |Comentário  |
|---------|---------|---------|---------|
|Definir o limite de phishing avançado para | duas | quatro | - |
|Habilitar a proteção contra representação | Sim | Sim | - |
|Habilitar a inteligência de caixa de correio em políticas de antipersonificação | Sim | Sim | - |
|Habilitar proteção de representação baseada em inteligência de caixa de correio | Sim | Sim | - |
|A ação de representação do domínio deve ser | JMF | Quarentena | - |
|A ação de representação do usuário deve ser | JMF | Qurantine | - |
|A ação de proteção de representação baseada em inteligência de caixa de correio deve ser |Tip  |JMF | - |

### <a name="safe-links-and-safe-attachments"></a>Links seguros e anexos seguros

 A ATP inclui as políticas de anexo seguro e de links seguros para impedir que emails com anexos potencialmente mal-intencionados sejam entregues e para impedir que os usuários cliquem e viajarm para URLs potencialmente não seguras.

#### <a name="safe-links"></a>Links seguros

|Nome do recurso de segurança  |Recomendado |Atraente  |Comentário  |
|---------|---------|---------|---------|
|Os links seguros de ATP devem rastrear cliques do usuário para fins de resposta |Sim |Sim |- |
|Os links seguros de ATP devem ser habilitados para aplicativos do Office |Sim |Sim |- |
|Links seguros de ATP devem ser habilitados para dentro do domínio |Sim |Sim |- |
|Os links seguros de ATP devem aplicar a verificação de URL em tempo real para links suspeitos e links que apontam para arquivos. |Sim |Sim |- |
|Os links seguros de ATP devem aguardar a conclusão da verificação de URL antes de entregar a mensagem. |Sim |Sim |- |
<!--
|URLs to block | | | |
|URLs not to wrap | | | |-->

#### <a name="safe-attachments"></a>Anexos Seguros

|Nome do recurso de segurança  |Recomendado |Atraente  |Comentário  |
|---------|---------|---------|---------|
|A ação de política de anexo seguro ATP deve ser |Quarentena |Quarentena |- |
|A proteção ATP deve ser habilitada para o OneDrive, o SharePoint e o Microsoft Teams |Sim |Sim |- |
<!--
|Allowed file hashes | | | |
|Blocked file hashes | | | |
-->

## <a name="miscellaneous-settings"></a>Configurações variadas

Estas configurações abrangem uma variedade de recursos que não se encaixam necessariamente em categorias específicas acima. Você também pode encontrar algumas configurações de 1.

Nome do recurso de segurança  |Recomendado |Atraente  |Comentário  |
|---------|---------|---------|---------|
|Criar registros SPF |Sim |Sim |- |
|Configurar a assinatura do DKIM para domínios |Sim |Sim |- |
|Implementar relatórios e conformidade de mensagens baseados em domínio (DMARC) com ação rejeitar ou quarentena |ação = nenhum |ação = rejeitar | |
|Implantar o complemento de mensagens de relatório para aprimorar o relatório do usuário final de emails suspeitos |Sim |Sim |- |
|Agendar relatórios de malware e spam |Sim |Sim |- |
|O fowarding automático para domínios externos deve ser não permitido ou monitorado |- |Sim |- |
|A auditoria unificada deve ser habilitada |Sim |Sim |- |
|O IMAP deve ser desativado, onde não é necessário |- |deficiência |- |
|O POP deve ser desativado, onde não é necessário |- |deficiência |- |
|O envio autenticado SMTP deve ser desativado quando não for exigido pelos aplicativos |- |deficiência |- |
|O EWS deve ser desabilitado |- |deficiência |- |
|PowerShell |- |deficiência |- |
|Configurar a estrutura de política de remetente para falha grave |-tudo |-tudo |- |
|Usar a inteligência de falsificação para os remetentes da lista branca sempre que possível |Sim |Sim |- |
|Bloqueio de borda baseado em diretório (DBEB) |Habilitado |Habilitado |Tipo de domínio = autoritativo |
