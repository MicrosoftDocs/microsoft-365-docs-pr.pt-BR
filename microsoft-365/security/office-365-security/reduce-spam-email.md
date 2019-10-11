---
title: Como reduzir emails de spam no Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/07/2018
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: 07824c51-2c45-4005-8596-03c0d7c4ff2a
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_IP
description: Aprenda as maneiras mais comuns de reduzir spam e lixo eletrônico no Office 365.
ms.openlocfilehash: 759d56862497444c27d0cc0f081731a3581337bd
ms.sourcegitcommit: ef5bcfe1e3d7d5a2a3c476477a0f82c84ed709e9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2019
ms.locfileid: "37428422"
---
# <a name="how-to-reduce-spam-email-in-office-365"></a>Como reduzir emails de spam no Office 365

 **Você está recebendo muito spam no Office 365? Faça o seguinte.**
  
É altamente recomendável que você relate mensagens de[falso negativo usando o suplemento](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) de mensagem de relatório para nos ajudar a melhorar os filtros. Além disso, você pode enviar a mensagem usando os[Envios do Explorador.](admin-submission.md)

> [!TIP]
> Se você acha que a mensagem é lixo eletrônico e está na pasta Lixo eletrônico, isso não deve ser um problema. Se você não deseja vê-la na caixa de correio, altere a política antispam para colocar a mensagem em quarentena. Mais informações sobre como colocar as mensagens em quarentena podem ser encontradas em [Colocar mensagens de email em quarentena no Office 365](quarantine-email-messages.md).

## <a name="fixing-allowed-spam"></a>Corrigir spam permitido

Geralmente, vemos que os clientes recebem lixo eletrônico em sua caixa de entrada devido às configurações incorretas. O mais comum é configurar seus domínios em uma regra de fluxo de emails (também conhecida como regra de transporte) para ignorar filtros ou listar os domínios na lista de permissão/remetentes. Isso não é bom porque essas mensagens ignoram a filtragem de spam e poderiam ter sido detectadas, por isso, a criação de [listas seguras de remetentes](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365) deve ser considerada uma solução temporária.  

## <a name="solutions-to-other-common-causes-of-getting-too-much-spam"></a>Soluções para outras causas comuns de recebimento de muito spam

Para evitar que você receba muito spam, a Proteção do Exchange Online (EOP) exige que os administradores concluam algumas tarefas. Se você não for o administrador do locatário do Office 365 e estiver recebendo muito spam, fale com seu administrador sobre essas tarefas. Caso contrário, ignore e vá até a seção do usuário.
  
### <a name="for-admins"></a>Para administradores

- **Aponte os registros DNS para o Office 365** Para que a Proteção do Exchange Online forneça a proteção ideal, os registros DNS do servidor de mensagens (MX) de todos os domínios devem ser apontados para o Office 365 e somente para ele. Confira [Criar registros DNS para o Office 365 ao gerenciar os registros DNS](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23).
    
- **Habilitar a regra de lixo eletrônico em todas as caixas de correio** Por padrão, a ação de filtragem de spam é definida como **Mover mensagem para a pasta Lixo eletrônico**. Se esta for a ação de política de spam preferida e atual, toda caixa de correio [também deverá ter a regra de lixo eletrônico habilitada](https://support.office.com/pt-BR/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). Para verificar isso, você pode executar o cmdlet Get-MailboxJunkEmailConfiguration em uma ou mais caixas de correio. Por exemplo, você pode verificar se isso se aplica a todas as caixas de correio executando o seguinte: Get-MailboxJunkEmailConfiguration -Identity \* | Where {$_.Enabled -eq $false}
    
    Ao visualizar a saída, a propriedade Habilitar deve ser definida como Verdadeiro. Se estiver definida como Falso, você poderá executar Set-MailboxJunkEmailConfiguration para alterá-la para Verdadeiro da seguinte forma: Set-MailboxJunkEmailConfiguration -Identity $values.UserPrincipalName -Enabled $true.
    
- **Criar regras de fluxo de email no servidor Exchange no local** Se você estiver usando a Proteção do Exchange Online, mas suas caixas de correio estiverem localizadas no Exchange Server Local, você precisará criar algumas regras de fluxo de emails no Exchange Server Local. Confira as [instruções para somente EOP](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/jj900470(v=exchg.150)).
    
- **Marcar emails em massa como spam** Emails em massa são emails de serviços nos quais os usuários podem ter se inscrito, mas que ainda assim podem ser indesejados. No cabeçalho da mensagem, localize a propriedade BCL (Nível de confiança em massa) no cabeçalho X-Microsoft-Antispam. Se o valor de BCL for menor que o limite definido no filtro de spam, ajuste o limite para marcar esses tipos de mensagens em massa como spam. Usuários diferentes têm tolerâncias e preferências diferentes para [como o email em massa é tratado](https://docs.microsoft.com/pt-BR/office365/SecurityCompliance/bulk-complaint-level-values). Você pode criar regras ou políticas diferentes para atender a diferentes preferências do usuário. 
    
- **Bloquear um remetente imediatamente** Caso você precise bloquear imediatamente um remetente, poderá fazê-lo pelo endereço de email, domínio ou endereço IP. Confira [Criar listas de bloqueio de remetentes no Office 365](create-block-sender-lists-in-office-365.md). Uma entrada em uma lista de permissão de usuário final pode substituir um bloqueio definido pelo administrador.
    
- **Habilitar um suplemento de mensagem de relatório para usuários** Recomendamos habilitar [o suplemento de mensagem de relatório para os seus usuários.](enable-the-report-message-add-in.md).

- **Use [o Explorador de envios](admin-submission.md)** Agora os administradores podem enviar emails usando a ID da mensagem de arquivo ou rede, URLs e arquivos para verificação pela Microsoft no Office 365. Como administrador, você também pode visualizar o comentário que seus usuários estão enviando e usar qualquer padrão para ajustar as configurações que podem causar problemas.

- **Habilite [DKIM](use-dkim-to-validate-outbound-email.md)** para assinar todas as suas mensagens de saída e aumentar a segurança no seu domínio e locatário.
 > [!TIP]
> Depois de habilitar o DKIM, habilite o [ DMARC ](use-dkim-to-validate-outbound-email.md), pois esse registro validará se o DKIM e o SPF estão funcionando do modo correto e, geralmente, os e-mails de falsificação não têm assinatura, pois o O365 gerencia sua chave simétrica pública e privada.
    
### <a name="for-users"></a>Para usuários

- **Habilitar a regra de lixo eletrônico e verificar sua lista de permissões** Verifique se a regra de ação de lixo eletrônico está habilitada e se o remetente ou domínio do remetente não está definido para ignorar em sua lista de permissões pessoal. A melhor maneira de acessar essas configurações é em [Bloquear ou permitir (configurações de lixo eletrônico)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46). Enquanto estiver ali, você também pode optar por bloquear o endereço de email ou domínio do remetente.
    
- **Reportar spam para a Microsoft** Reporte as mensagens de spam para a Microsoft usando o [suplemento Relatar Mensagem](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).
       
- **Cancelar inscrição de emails em massa** Se a mensagem foi um newsletter no qual você se inscreveu (boletins informativos, lançamentos de produto etc.) e contiver um link Cancelar inscrição de uma fonte respeitável, basta cancelar a inscrição. O Office 365 normalmente não trata essas mensagens como spam. Você também pode optar por bloquear o remetente ou pedir para seu administrador fazer uma alteração que fará com que todos os emails em massa sejam tratados como spam.
