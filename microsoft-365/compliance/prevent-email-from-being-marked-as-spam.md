---
title: Como impedir que falsos positivos aconteçam no Office 365
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Saiba como impedir os falsos positivos e manter os emails livres de lixo eletrônico no Office 365.
ms.openlocfilehash: 18b360f4cb3900aad3a6dbf7cc0a098750099f01
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073341"
---
# <a name="how-to-prevent-real-email-from-being-marked-as-spam-in-office-365"></a>Como impedir que emails reais sejam marcados como spam no Office 365

 **Seu email real está sendo marcado como spam no Office 365? Faça isso.**
  
Se você receber um falso positivo, relate a mensagem à Microsoft usando [o suplemento de mensagem de relatório ](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). Além disso, você pode encaminhar a mensagem usando [Explorador de Envios](/security/office-365-security/admin-submission.md).
    
## <a name="determine-the-reason-why-the-message-was-marked-as-spam"></a>Determinar o motivo pelo qual a mensagem foi marcada como spam

Para resolver muitos problemas de spam no Office 365, confira o artigo [Exibir cabeçalhos de mensagens de email](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c) e determine o que deu errado. Procure um cabeçalho chamado X-Forefront-Antispam-Report. [Saiba mais sobre cabeçalhos de mensagem antispam](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx).
  
No cabeçalho, procure os cabeçalhos e os valores a seguir.
  
### <a name="x-forefront-antispam-report"></a>X-Forefront-Antispam-Report

- **SFV:SPM** Indica que a mensagem foi marcada como spam devido aos filtros de spam da Proteção do Exchange Online. 

- **SFV:BLK** Indica que a mensagem foi marcada como spam porque o endereço de envio está na lista de Remetentes Bloqueados do destinatário. 
    
- **SFV:SKS** Indica que a mensagem foi marcada como spam antes do filtro de conteúdo. Isso pode incluir uma regra de fluxo de emails (também conhecida como regra de transporte) marcando a mensagem como spam. Execute um rastreamento de mensagens para ver se uma regra de fluxo de emails disparada pode ter definido um nível de confiança alto de spam (SCL). 
    
- **SFV:SKB** Indica que a mensagem foi marcada como spam porque correspondeu a uma lista de bloqueios na política de filtro de spam. 
    
- **SFV:Bulk** Indica que o valor do Nível de Reclamação em Massa (BCL) localizado no cabeçalho x-microsoft-antispam está acima do limite de massa que foi definido para o filtro de conteúdo. Emails em massa são emails que os usuários podem ter se inscrito para receber, mas ainda assim podem ser indesejados. No cabeçalho da mensagem, localize a propriedade BCL (Nível de Confiança em Massa) no cabeçalho X-Microsoft-Antispam. Se o valor de BCL for menor que o limite definido no filtro de spam, ajuste o limite para marcar esses tipos de mensagens em massa como spam. Usuários diferentes têm tolerâncias e preferências diferentes para [como o email em massa é tratado](https://docs.microsoft.com/pt-BR/office365/SecurityCompliance/bulk-complaint-level-values). Você pode criar regras ou políticas diferentes para atender a diferentes preferências do usuário.
    
- **CAT:SPOOF** ou **CAT:PHISH** Indica que a mensagem parece ser falsa, ou seja, a fonte da mensagem não pode ser validada e pode ser suspeita. Se for válida, o remetente precisará garantir que ele tenha a configuração correta de DKIM e SPF. Verifique o cabeçalho Authentication-Results para obter mais informações. Embora possa ser difícil fazer todos os remetentes usarem métodos adequados de autenticação de email, ignorar essas verificações podem ser muito perigoso e é a principal causa de comprometimentos. 
    
### <a name="x-customspam"></a>x-customspam

- A presença desse cabeçalho indica que a mensagem foi marcada como spam porque uma das [opções avançadas de spam está habilitada](https://technet.microsoft.com/library/jj200750%28v=exchg.150%29.aspx) no filtro de spam. A menos que você precise desses recursos, recomendamos usar as configurações padrão. 
    
## <a name="solutions-to-additional-causes-of-too-much-spam"></a>Soluções para outras causas de excesso de spam

Para trabalhar com eficiência, a Proteção do Exchange Online (EOP) exige que os administradores concluam algumas tarefas. Se você não for o administrador do locatário do Office 365 e estiver recebendo muito spam, fale com seu administrador sobre essas tarefas. Caso contrário, ignore e vá até a seção do usuário.
  
### <a name="for-admins"></a>Para administradores

- **Aponte seus registros de DNS para o Office 365** Para que o EOP ofereça proteção, os registros DNS do seu servidor de mensagens (MX) para todos os domínios devem apontar para o Office 365 e apenas para o Office 365. Se seu MX não apontar para o Office 365, o EOP não fornecerá filtragem de spam para seus usuários. Se você desejar usar outro dispositivo ou serviço para fornecer a filtragem de spam do seu domínio, desabilite a proteção contra spam no EOP. Você pode fazer isso criando uma regra de fluxo de emails que defina o valor do SCL como -1. Se você mais tarde decidir usar o EOP, remova essa regra de fluxo de emails. 
    
- **Habilitar um suplemento de mensagem de relatório para usuários** Recomendamos habilitar [o suplemento de mensagem de relatório para os seus usuários.](/security/office-365-security/enable-the-report-message-add-in.md).

- **Use [o Explorador de envios](/security/office-365-security/admin-submission.md)** Agora os administradores podem enviar emails usando a ID da mensagem de arquivo ou rede, URLs e arquivos para verificação pela Microsoft no Office 365. Como administrador, você também pode visualizar o comentário que seus usuários estão enviando e usar qualquer padrão para ajustar as configurações que podem causar problemas.

- **Verifique se os usuários estão dentro dos limites permitidos** para enviar e receber emails como mostrou [aqui](https://docs.microsoft.com/pt-BR/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).

 - **Verifique os níveis em massa** conforme especificado [aqui](/security/office-365-security/bulk-complaint-level-values.md)
    
### <a name="for-users"></a>Para usuários
    
- **Crie uma lista de remetentes confiáveis** Os usuários podem adicionar endereços de remetentes seguros em sua lista de remetentes confiáveis no [Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065) ou [Outlook na Web](https://go.microsoft.com/fwlink/p/?LinkId=294862). Para começar no Outlook na Web, escolha **Configurações**![ConfigureAPowerBIAnalysisServicesConnector_settingsIcon](media/24bd5467-c8d2-4936-9c37-a179bd0e21ec.png) \> **Opções** \> **Bloquear ou permitir**. O diagrama a seguir mostra um exemplo de como adicionar alguém a uma lista de remetentes confiáveis.
  
![Adicionar um remetente seguro no Outlook na web](media/8de6b24e-429e-4e8f-8ce8-53ba659cbfcb.png)
  
O EOP aceita os Remetentes e destinatários confiáveis dos seus usuários, mas não aceita Domínios confiáveis. Isso acontece independentemente do domínio ser adicionado através do Outlook na web ou adicionado no Outlook e sincronizado usando o Diretório de Sincronização.

- **Desabilitar a filtragem de SmartScreen no Outlook** Se você estiver usando o antigo cliente de área de trabalho do Outlook, desabilite a funcionalidade de filtragem de SmartScreen, que foi descontinuada. Se estiver habilitado, ela poderá causar falsos positivos. Isso não será necessário se o cliente de área de trabalho do Outlook estiver atualizado.

## <a name="troubleshooting-a-message-ends-up-in-the-junk-folder-even-though-eop-marked-the-message-as-non-spam"></a>Solução de problemas: Uma mensagem termina na pasta de Lixo eletrônico embora EOP tenha marcado a mensagem como não spam

Se os usuários tem o Outlook habilitado para “Somente listas seguras: Somente emails de pessoas ou domínios na sua lista de Remetentes e destinatários confiáveis serão entregues na sua caixa de entrada”, todos os outros emails irão para a pasta de lixo eletrônico. Isso acontecerá independentemente do EOP marcar a mensagem como não spam, ou de você ter configurado uma regra no EOP para marcar uma mensagem como não spam.
  
Você pode desabilitar a opção Apenas Listas de Confiança para seus usuários do Outlook seguindo as instruções em [Outlook: política de configuração para desabilitar a UI do lixo eletrônico e do mecanismo de filtragem](https://support.microsoft.com/pt-BR/kb/2180568).
  
Se você visualizar a mensagem no Outlook na Web, existirá um aviso de segurança em amarelo indicando que a mensagem está na pasta Lixo eletrônico porque o remetente não está na lista de remetentes confiáveis do destinatário.
  
Se você observar o cabeçalho de uma mensagem verá que ela pode incluir o carimbo SFV:SKN  (permissões de IP ou permissões ETR) ou SFV:NSPM (não spam), mas ela ainda estará na pasta Lixo eletrônico do usuário. Não há nada no cabeçalho da mensagem que indica que o usuário tenha  "Apenas listas de confiança" habilitado. Isso acontece porque a opção "Apenas listas de confiança" definida pelos usuários no Outlook substituem a configuração do EOP. 
  
 **Para verificar por que uma mensagem de um remetente seguro é marcada como não spam no cabeçalho da mensagem mas ainda assim termina na pasta de lixo eletrônico do usuário**
  
1. Para aprender a se conectar ao Exchange Online PowerShell, confira [Conectar ao Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554). 
    
2. Execute o seguinte comando para exibir as configurações de lixo eletrônico do usuário:
    
  ```Powershell
  Get-MailboxJunkEmailConfiguration example@contoso.com | fl TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
  ```

- Se TrustedListsOnly é definido como verdadeiro, significa que essa configuração está ativada
- Se ContactsTrusted é definido como verdadeiro, isso significa que o usuário confia em remetentes confiáveis e contatos
- O TrustedSendersAndDomains lista o conteúdo da lista de remetentes confiáveis do usuário


## <a name="eop-only-customers-use-directory-synchronization"></a>Clientes somente EOP: usar a sincronização de diretório

Se você for um cliente somente EOP, ou seja inscrito no serviço EOP para uso com o servidor de email (Exchange) no local, você deve sincronizar as configurações de usuário com o serviço usando a sincronização de diretórios. Isso garante que sua lista de remetentes confiáveis seja respeitada pelo EOP. Para saber mais, confira "Utilizar a sincronização de diretórios para gerenciar usuários de email" em [Gerenciar usuários de email no EOP](https://go.microsoft.com/fwlink/?LinkId=534098).
