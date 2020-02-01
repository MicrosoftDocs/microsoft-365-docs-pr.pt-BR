---
title: Combater lixo eletrônico enviado ao Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5fd7d05b-96db-456f-81d6-1ac0e5bff530
ms.collection:
- M365-security-compliance
description: O mapa de segurança de email da Microsoft envolve uma abordagem de vários produtos sem correspondência. A tecnologia de filtragem antispam e antispam do Exchange Online Protection (EOP) está sendo aplicada nas plataformas de email da Microsoft para fornecer aos usuários as ferramentas e inovações mais recentes antispam e anti-phishing em toda a rede. O objetivo do EOP é oferecer um serviço de email abrangente e útil que ajuda a detectar e proteger os usuários contra lixo eletrônico, ameaças de email fraudulentas (phishing) e malware.
ms.openlocfilehash: 888df6224007471db46b669ac4ffe33983057115
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599318"
---
# <a name="fighting-junk-email-sent-to-office-365"></a>Combater lixo eletrônico enviado ao Office 365

O mapa de segurança de email da Microsoft envolve uma abordagem de vários produtos sem correspondência. A tecnologia de filtragem antispam e antispam do Exchange Online Protection (EOP) está sendo aplicada nas plataformas de email da Microsoft para fornecer aos usuários as ferramentas e inovações mais recentes antispam e anti-phishing em toda a rede. O objetivo do EOP é oferecer um serviço de email abrangente e útil que ajuda a detectar e proteger os usuários contra lixo eletrônico, ameaças de email fraudulentas (phishing) e malware.
  
## <a name="the-challenge"></a>O desafio

O email se tornou uma ferramenta de comunicação importante não só para consumidores, mas também para os vendedores, equipe de suporte, organizações de vendas e empresas de todos os portes. Como o uso de email cresceu, isso tem abuso de email. O lixo eletrônico não monitorado pode obstruir as caixas de entrada e redes, impactar a satisfação do usuário e dificultar a eficácia de comunicações de email legítimas. É por isso que a Microsoft continua a investir em tecnologias antispam. Em suma, ele começa com a contém e filtra o lixo eletrônico. 
  
## <a name="our-efforts"></a>Nossos esforços

O EOP oferece várias etapas para minimizar o impacto negativo que o lixo eletrônico tem sobre a experiência de email dos usuários.
  
### <a name="exchange-online-protection-technology"></a>Tecnologia de proteção do Exchange Online

Para ajudar a reduzir o lixo eletrônico, o EOP inclui a proteção de lixo eletrônico usando tecnologias de filtragem EOP de proprietário, nas quais o email de tela identifica e separa lixo eletrônico de emails legítimos. O filtro de conteúdo do EOP aprende de ameaças conhecidas contra spam e phishing e comentários de usuários da nossa plataforma de consumidores, Outlook.com. Esses tipos de dados ajudam a treinar as tecnologias do EOP a reconhecer emails e lixo eletrônico legítimos e as principais entradas na reputação do remetente. Comentários contínuos dos usuários do EOP no programa de classificação de lixo eletrônico ajuda a garantir que as tecnologias do EOP sejam continuamente treinadas e aprimoradas.
  
#### <a name="how-does-eop-work"></a>Como o EOP funciona?

Quando um usuário externo envia uma mensagem de email para um usuário do EOP, as tecnologias de filtragem do EOP avaliam o conteúdo da mensagem e atribui uma classificação à mensagem com base na probabilidade de que a mensagem seja lixo eletrônico. Essa classificação é armazenada como uma propriedade de mensagem chamada SCL (nível de confiança de spam) dentro da própria mensagem. A classificação de SCL permanece com a mensagem à medida que é enviada para outras camadas de proteção antispam no EOP. 
  
As regras dentro do EOP são definidas para lidar com mensagens de email com várias classificações de SCL. Se uma mensagem tiver uma classificação de SCL superior a um determinado limite, ela será considerada spam. A mensagem será colocada em quarentena ou entregue à pasta lixo eletrônico do usuário, dependendo de como o administrador do sistema configura a opção de entrega de spam.
  
#### <a name="eop-filters"></a>Filtros EOP

Além das tecnologias de filtragem antispam, o EOP também dá ao administrador do sistema a capacidade de definir níveis de filtro para personalizar ainda mais a entrega de emails para suas contas de usuário. Os administradores podem facilmente adicionar um nome de domínio ou remetente à lista de remetentes e domínios confiáveis para que o email desse remetente ou domínio nunca seja tratado como lixo eletrônico independentemente do conteúdo da mensagem. Para saber mais, confira [listas de remetentes seguros e remetentes bloqueados no Exchange Online](safe-sender-and-blocked-sender-lists-faq.md).
  
### <a name="phishing-protection"></a>Proteção contra phishing

Phishing (pronuncia-se "pesca") é uma forma de roubo de identidade e uma das ameaças de crescimento mais rápido na Internet. Geralmente, você pode identificar uma mensagem de phishing ao solicitar informações pessoais ou financeiras ou inclui um link para um site que solicita essas informações. O EOP oferece proteção contra phishing como parte das tecnologias de filtragem de EOP de proprietário. As tecnologias de filtragem do EOP analisam o email para ajudar a detectar links fraudulentos ou domínios falsificados para ajudar a proteger os usuários contra esses tipos de golpes online.
  
#### <a name="how-does-phishing-protection-work"></a>Como funciona a proteção contra phishing?

Geralmente, um email de phishing será enviado contendo um link, depois de clicar no link redireciona os usuários para um site da Web fraudulento que parece válido (como sua instituição financeira ou serviço online). Este site de phishing normalmente solicita que os usuários insiram informações pessoais, como nomes de usuário, senhas e números de segurança social. Qualquer informação inserida no site de phishing ajuda o phishing a roubar sua identidade. Usando os nomes e logotipos conhecidos da marca confiável, os phishers podem parecer legítimos. A tecnologia de filtro de phishing oferecida no EOP verifica possíveis características de phishing no email. Se encontrado, o email será movido para a pasta lixo eletrônico.
  
A Microsoft está concentrando seus esforços de tecnologia anti-phishing em duas frentes: primeiro, ajudando a impedir que mensagens de email de phishing cheguem aos nossos usuários e segundo, ajudando a eliminar a possibilidade de os usuários serem induzidos por emails falsificados e sites da Web. 
  
> [!TIP]
> O Internet Explorer versão 7 e superior bloqueará ou avisará os usuários quando eles visitarem sites de phishing potenciais ou conhecidos para que não sejam induzidos a fornecer informações pessoais. [Verifique se você tem a versão mais recente do Internet Explorer](https://www.microsoft.com/windows/ie/default.mspx). 
  
#### <a name="authentication"></a>Autenticação

A falsificação de domínio é uma maneira de imitar um endereço de email legítimo para fazer com que o email fraudulento pareça legítimo. A falsificação é usada por pessoas ou organizações mal-intencionadas em golpes de phishing para atrair pessoas a divulgar informações pessoais confidenciais. A divulgação dessas informações pode levar à identificação de roubo e outros tipos de fraude.
  
O EOP usa a estrutura de proteção do remetente (SPF), o DomainKeys identificado mail (DKIM) e a autenticação de mensagens baseadas em domínio, relatórios e conformidade (DMARC) e outras autenticações implícitas para verificar se as mensagens são provenientes do domínio do qual dizem . Recomendamos que todos os remetentes usem o SPF e o DKIM para proteger seus destinatários contra spam e golpes de phishing. Recomendamos que os remetentes considerem publicar um DMARC para rejeitar ou colocar em quarentena os emails enviados de remetentes não autorizados.
  
- Para saber mais sobre o SPF, confira [RFC 7208](https://tools.ietf.org/html/rfc7208) e [Sender Policy Framework](https://www.openspf.org/).
    
- Para saber mais sobre o DKIM, confira [RFC 6376](https://tools.ietf.org/html/rfc6376) e [DKIM.org](https://dkim.org/).
    
- Para saber mais sobre o DMARC, confira [DMARC.org](https://dmarc.org/).
    
### <a name="legislation"></a>Legislação

Na Microsoft, acreditamos que o desenvolvimento de novas tecnologias e autoregulamentação requer o suporte da política governamental efetiva e estruturas legais. A proliferação mundial de spam tem spurred vários órgãos legislativos para regulamentar emails comerciais. Muitos países/regiões agora têm leis de combate de spam em vigor. Os Estados Unidos têm leis federais e estaduais que regem o spam, e essa abordagem complementar está ajudando a curtailr spam e, ao mesmo tempo, permitindo o e-commerce legítimo para o Prosper. O Act CAN-SPAM expande as ferramentas disponíveis para moderar mensagens de email fraudulentas e enganosas.
  

