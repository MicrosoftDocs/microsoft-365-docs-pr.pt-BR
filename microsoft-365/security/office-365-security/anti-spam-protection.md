---
title: Proteção anti-spam de email do Office 365
ms.author: krowley
author: kccross
manager: dansimp
ms.date: 6/29/2018
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
description: Saiba mais sobre as configurações e filtros antispam que ajudarão você a evitar spam no Exchange Online e no Office 365. Obtendo muito spam no Office 365? Você pode personalizar suas configurações de política antispam e filtros de spam.
ms.openlocfilehash: a8dcdd5b92ed799f360200f7cb21161f47fc9bee
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073901"
---
# <a name="office-365-email-anti-spam-protection"></a>Proteção anti-spam de email do Office 365

Você está preocupado com muito spam no Office 365? Criamos vários filtros de spam no serviço do Office 365 ou do Exchange Online Protection (EOP), para que seu email fique protegido do momento em que você recebe a primeira mensagem. Para ajudar a evitar spam no Office 365, talvez você queira alterar uma configuração de proteção para lidar com um problema específico em sua organização, digamos que você esteja recebendo muitos spams de um remetente específico, por exemplo, ou simplesmente ajustar suas configurações para que elas sejam adaptado para atender melhor às necessidades da sua organização. Para fazer isso, você pode alterar as configurações antispam no centro de conformidade de segurança &amp; do Office 365.
  
Este artigo destina-se aos administradores do Office 365. Se você não é um administrador, mas é um usuário do Office 365 e deseja saber como lidar com o spam recebido, este não é o artigo que você está procurando. Em vez disso, se você usar o Outlook para PC ou o Outlook para Mac, comece com [visão geral do filtro de lixo eletrônico](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). Se você usar o Outlook na Web, comece com [saiba mais sobre lixo eletrônico e phishing](https://support.office.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31).
  
## <a name="these-options-help-you-prevent-spam-in-office-365"></a>Essas opções ajudam a evitar spam no Office 365

 **Filtragem de conexão**: quando você usa a filtragem de conexão, o Office 365 verifica a reputação do remetente antes de permitir que uma mensagem seja acessada. Você pode criar uma lista de permissões ou uma lista de remetentes confiáveis para certificar-se de receber todas as mensagens enviadas por um endereço IP ou intervalo de endereços IP específico. Você também pode criar uma lista de endereços IP a partir da qual bloquear mensagens, chamada lista de bloqueios. Para saber mais, veja [Configure the Connection Filter Policy](https://technet.microsoft.com/library/jj200718%28v=exchg.150%29.aspx). Se você estiver preocupado com o spam no Office 365, use a filtragem de conexão para ajudar a evitar spam.
  
Para os clientes que têm o Office 365 Enterprise E5 ou adquirir licenças de proteção avançada contra ameaças (ATP), a filtragem de conexão é usada pelo spoof Intelligence para criar listas de permissões e bloqueios de remetentes que estão falsificando seu domínio. Para obter mais informações, consulte [saiba mais sobre o spoof Intelligence](https://go.microsoft.com/fwlink/?LinkID=735009).
  
 **Filtragem de spam**: o Office 365 verifica se há características de mensagens consistentes com spam usando a filtragem de spam. Você pode alterar as ações a serem executadas em mensagens identificadas como spam e escolher se é para filtrar mensagens escritas em idiomas específicos ou enviadas de determinados países ou regiões. Também pode ativar as opções avançadas de filtragem de spam, caso queira adotar uma abordagem mais agressiva de filtragem de spam. Além disso, é possível configurar notificações de spam para usuários finais, para informá-los quando mensagens destinadas a eles forem enviadas para a quarentena. (Enviar mensagens para a quarentena é uma das ações configuráveis). A partir dessas notificações, os usuários finais podem liberar falsos positivos e relatá-los para a Microsoft para análise. Para saber mais, confira [Configure your spam filter policies](https://go.microsoft.com/fwlink/p/?LinkId=617147). Para ajudar a evitar spam no Office 365, use a filtragem de spam, se você estiver preocupado com muito spam no Office 365, use a filtragem de conexão para ajudar a evitar spam.
  
> [!NOTE]
> Para clientes autônomos do EOP: por padrão, os filtros de spam do EOP enviam mensagens detectadas por spam para a pasta lixo eletrônico de cada destinatário. No entanto, para garantir que a ação **mover mensagem para a pasta lixo eletrônico** funcione com caixas de correio locais, você deve configurar duas regras de fluxo de mensagens do Exchange (também conhecidas como regras de transporte) em seus servidores locais para detectar cabeçalhos de spam adicionados por EOP. Para obter detalhes, consulte [Garantir que o spam seja direcionado para a pasta Lixo Eletrônico de cada usuário](https://technet.microsoft.com/library/jj837173%28v=exchg.150%29.aspx). 
  
## <a name="extra-information-if-you-receive-too-much-spam-in-office-365"></a>Informações adicionais se você receber muito spam no Office 365

O vídeo a seguir fornece uma visão geral da configuração da filtragem de spam no EOP.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/608be94c-d763-4c47-af94-99e7cb277713?autoplay=false]
  
Para obter mais detalhes, consulte o tópico [Configurar políticas de filtro de spam](https://go.microsoft.com/fwlink/p/?LinkId=617147) .
  
## <a name="check-your-outgoing-messages-to-prevent-spam-in-office-365"></a>Verifique suas mensagens de saída para impedir spam no Office 365

 **Filtragem de saída**: o Office 365 também verifica se os usuários não enviam spam. Por exemplo, o computador de um usuário pode ser infectado com malware que faz com que ele envie mensagens de spam e, portanto, criamos proteção contra isso chamado *filtragem de saída*. Não é possível desativar a filtragem de saída, mas é possível definir as configurações descritas em [Configure the Outbound Spam Policy](https://technet.microsoft.com/library/jj200737%28v=exchg.150%29.aspx). Se você estiver preocupado com muito spam no Office 365, use a filtragem de saída para ajudar a evitar spam no Exchange Online.
  
## <a name="beyond-the-basics-more-ways-to-prevent-spam-in-office-365"></a>Além do básico: outras maneiras de evitar spam no Office 365

 **Regras de fluxo de email**: se você quiser ir além da filtragem de spam interna e criar regras personalizadas com base em suas políticas de negócios, _[as regras de fluxo de emails](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx)_ (também conhecidas como _regras de transporte_) são outro filtro que ajuda a evitar spam no Office 365. Por exemplo, você pode usar regras de fluxo de email para definir o valor do nível de confiança de spam (SCL) para mensagens que correspondem a condições específicas, conforme descrito em [usar regras de fluxo de emails para definir o SCL (nível de confiança de spam) em mensagens](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).
  
 **Autenticação de email**: técnicas que usam o DNS (sistema de nomes de domínio) para adicionar informações verificáveis a mensagens de email sobre o remetente de uma mensagem de email são chamadas de autenticação de email. Os administradores do Office 365 mais avançados podem fazer uso desses métodos de autenticação de email:
  
- **Estrutura de política de remetente (SPF)**: o SPF valida a origem de mensagens de email, verificando o endereço IP do remetente em relação ao proprietário supostamente do domínio de envio. Para obter uma introdução rápida sobre SPF e configurá-lo rapidamente, confira [Set up SPF in Office 365 to help prevent spoofing](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx). Para compreender melhor como o Office 365 usa SPF, para solucionar problemas, ou para saber mais sobre implantações incomuns, como implantações híbridas, comece com [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](https://technet.microsoft.com/library/mt712724%28v=exchg.150%29.aspx).

- **DomainKeys identificated mail (DKIM)**: DKIM permite anexar uma assinatura digital a mensagens de email no cabeçalho da mensagem de emails enviados. Sistemas de email que recebem emails de seu domínio usam essa assinatura digital para determinar se os emails de entrada recebidos são legítimos. Para obter informações sobre o DKIM e o Office 365, consulte [use DKIM para validar emails de saída enviados do seu domínio no Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx).

- **Autenticação de mensagens baseadas em domínio, relatórios e conformidade (DMARC)**: o DMARC ajuda a receber sistemas de email determinam o que fazer com as mensagens que falham no SPF ou no DKIM verifica e fornece outro nível de confiança para seus parceiros de email. Para obter informações sobre como configurar o DMARC, confira [usar o DMARC para validar emails no Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).

Se você estiver preocupado com spam, phishing e falsificação no Office 365, use SPF, DKIM e DMARC juntos para ajudar a evitar spam e falsificação indesejada.
  
 **Configurações gerenciadas pelo usuário final**: se você estiver procurando informações sobre como os usuários finais podem gerenciar suas próprias configurações de spam, confira [visão geral do filtro de lixo eletrônico](https://go.microsoft.com/fwlink/?LinkId=270065) (para usuários do Microsoft Outlook) ou [saiba mais sobre lixo eletrônico e phishing](https://go.microsoft.com/fwlink/?LinkId=270068) (para Outlook nos usuários da Web). Se você estiver usando o EOP para proteger caixas de correio locais, certifique-se de usar a sincronização de diretório para garantir que essas configurações sejam sincronizadas com o serviço. Para saber mais sobre como configurar a sincronização de diretório, consulte "Usar a sincronização de diretório para gerenciar usuários de email" em [Gerenciar usuários de email no EOP](https://technet.microsoft.com/library/dn636911%28v=exchg.150%29.aspx).
  
## <a name="for-more-information"></a>Para saber mais

[Blog: por que spam e phishing são obtidos através do Office 365?](https://go.microsoft.com/fwlink/?LinkId=528179 )
  
[Perguntas frequentes sobre a proteção antispam](https://technet.microsoft.com/library/jj937231%28v=exchg.150%29.aspx)
  
[Impedir falsos positivos marcados como spam usando uma lista confiável ou outras técnicas](../../compliance/prevent-email-from-being-marked-as-spam.md)
  
[Como configurar a filtragem de spam do Office 365 para ajudar a bloquear mensagens de lixo eletrônico](reduce-spam-email.md)
  
[Qual é a diferença entre lixo eletrônico e email em massa?](https://technet.microsoft.com/library/dn720441%28v=exchg.150%29.aspx)
  
[Cabeçalhos de mensagem antispam](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx)
  
[Mensagens de dispersão e EOP](https://technet.microsoft.com/library/dn499795%28v=exchg.150%29.aspx)

## <a name="more-resources"></a>Mais recursos

[Obter ajuda de fóruns da comunidade do Office 365](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[Administradores: Entrar e criar uma solicitação de serviço](https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[Administradores: Ligar para o Suporte](https://go.microsoft.com/fwlink/p/?LinkID=518322)
