---
title: Políticas anti-phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender sobre as políticas anti-phishing que estão disponíveis no Exchange Online Protection (EOP) e no Office 365 Advanced Threat Protection (Office 365 ATP).
ms.openlocfilehash: a7db287b8a8efb5c41488529fcaa8789b2f594b5
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46652712"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Políticas anti-phishing no Microsoft 365

As políticas para definir as configurações de proteção anti-phishing estão disponíveis nas organizações do Microsoft 365 com caixas de correio do Exchange Online, organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online e organizações do Office 365 Advanced Threat Protection (Office 365 ATP).

As políticas de anti-phishing do ATP só estão disponíveis em organizações que têm o Office 365 ATP. Por exemplo:

- Microsoft 365 Enterprise e5, Microsoft 365 Education a5, etc.
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)
- [Office 365 ATP como um complemento](https://products.office.com/exchange/advance-threat-protection)

Todas as outras organizações têm políticas anti-phishing.

As diferenças de alto nível entre as políticas anti-phishing e as políticas anti-phishing do ATP são descritas na tabela a seguir:

****

|Recurso|Políticas anti-phishing|Políticas de anti-phishing da ATP|
|---|:---:|:---:|
|Política padrão criada automaticamente|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Criar políticas personalizadas|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Configurações de política<sup>\*</sup>|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Configurações de representação||![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Configurações de spoof|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Limites avançados de phishing||![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<sup>\*</sup>Na política padrão, o nome e a descrição da política são somente leitura (a descrição está em branco) e não é possível especificar a quem a política se aplica (a política padrão se aplica a todos os destinatários).

Para configurar as políticas anti-phishing, consulte os seguintes tópicos:

- [Configurar políticas anti-phishing no EOP](configure-anti-phishing-policies-eop.md)

- [Configurar as políticas de anti-phishing do ATP no Microsoft 365](configure-atp-anti-phishing-policies.md)

O restante deste tópico descreve as configurações disponíveis nas políticas anti-phishing e nas políticas antiphishing da ATP.

## <a name="spoof-settings"></a>Configurações de spoof

Falsificação é quando o endereço de em uma mensagem de email (o endereço do remetente que é exibido em clientes de email) não corresponde ao domínio da fonte de email. Para obter mais informações sobre falsificação, consulte [proteção contra falsificação no Microsoft 365](anti-spoofing-protection.md).

As seguintes configurações de spoof estão disponíveis em políticas anti-phishing e políticas antiphishing da ATP:

- **Proteção contra falsificação**: habilita ou desabilita a proteção contra falsificação. Recomendamos que você deixe-o habilitado. Você usa a **política de inteligência de spoof** para permitir ou bloquear remetentes internos e externos falsificados específicos. Para obter mais informações, contra [Configurar a inteligência contra falsificação no Microsoft 365](learn-about-spoof-intelligence.md).

  > [!NOTE]
  > As configurações de spoof são habilitadas por padrão na política anti-phishing padrão no EOP, na política anti-phishing padrão da ATP e em novas políticas antiphishing personalizadas ou políticas antiphishing da ATP que você criar. <br/><br/> Você não precisa desabilitar a proteção contra falsificação se o registro MX não apontar para o Microsoft 365; em vez disso, habilite a filtragem avançada de conectores. Para obter instruções, consulte [filtragem avançada para conectores no Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

  Para mensagens de remetentes falsificados bloqueados, você também pode especificar a ação a ser tomada nas mensagens:

  - **Mover mensagem para a pasta de lixo eletrônico**: Este é o valor padrão. A mensagem é entregue à caixa de correio e movida para a pasta lixo eletrônico. No Exchange Online, a mensagem é movida para a pasta lixo eletrônico se a regra de lixo eletrônico estiver habilitada na caixa de correio (habilitada por padrão). Para obter mais informações, consulte [Configurar definições de lixo eletrônico em caixas de correio do Exchange Online no Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

  - **Colocar a mensagem em quarentena**: envia a mensagem para quarentena em vez dos destinatários pretendidos. Para obter informações sobre quarentena, confira os seguintes tópicos:

    - [Quarentena no Microsoft 365](quarantine-email-messages.md)
    - [Gerenciar arquivos e mensagens em quarentena como um administrador no Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Localizar e liberar mensagens em quarentena como um usuário no Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

- **Remetente não autenticado**: habilita ou desabilita a identificação de remetente não identificado no Outlook. Especificamente:

  - Um ponto de interrogação (?) será adicionado à foto do remetente se a mensagem não passar verificações SPF ou DKIM **e** a mensagem não passar DMARC ou [autenticação composta](email-validation-and-authentication.md#composite-authentication).

  - A marca via (chris@contoso.com <u>via</u> Michelle@fabrikam.com) será adicionada se o domínio no endereço de (o remetente da mensagem exibido em clientes de email) for diferente do domínio na assinatura do DKIM ou do endereço **de email do** remetente. Para obter mais informações sobre esses endereços, consulte [uma visão geral dos padrões de mensagens de email](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

  Para impedir que esses identificadores sejam adicionados às mensagens de remetentes específicos, você tem as seguintes opções:

  - Permitir que o remetente falsifique na política de inteligência de falsificação. Para obter instruções, consulte [Configure spoof Intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

  - [Configurar a autenticação de email](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) para o domínio do remetente.
  
    - Para o ponto de interrogação na foto, SPF ou DKIM do remetente são os mais importantes.
    - Para a marca via, confirme se o domínio na assinatura DKIM ou o endereço **de email from** corresponde (ou é um subdomínio de) no endereço de.

  Para obter mais informações, consulte [identificar mensagens suspeitas no Outlook.com e no Outlook na Web](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-atp-anti-phishing-policies"></a>Configurações exclusivas nas políticas anti-phishing da ATP

Esta seção descreve as configurações de política que estão disponíveis somente em políticas anti-phishing da ATP.

> [!NOTE]
> Por padrão, as configurações exclusivas de ATP não são configuradas ou ativadas, mesmo na política padrão. Para aproveitar esses recursos, é necessário habilitá-los e configurá-los na política de anti-phishing padrão ATP, ou criar e configurar políticas anti-phishing personalizadas da ATP.

### <a name="policy-settings-in-atp-anti-phishing-policies"></a>Configurações de política nas políticas anti-phishing da ATP

As configurações de política a seguir estão disponíveis apenas em políticas anti-phishing da ATP:

- **Name**: não é possível renomear a política anti-phishing padrão, mas você pode nomear e renomear políticas personalizadas que você criou.

- **Descrição** Não é possível adicionar uma descrição à política anti-phishing padrão, mas você pode adicionar e alterar a descrição das políticas personalizadas criadas.

- **Aplicado a**: identifica destinatários internos aos quais a política anti-phishing do ATP se aplica. Esse valor é necessário em políticas personalizadas e não está disponível na política padrão (a política padrão se aplica a todos os destinatários).

    Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção. Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_). Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).

  - O **destinatário é**: uma ou mais caixas de correio, usuários de email ou contatos de email em sua organização.
  - **O destinatário é um membro de**: um ou mais grupos em sua organização.
  - **O domínio do destinatário é**: um ou mais dos domínios aceitos configurados no Microsoft 365.

  - **Exceto quando**: exceções da regra. As configurações e o comportamento são exatamente semelhantes às condições:

    - **O destinatário é**
    - **O destinatário é um membro de**
    - **O domínio do destinatário é**

### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>Configurações de representação nas políticas anti-phishing da ATP

A representação é onde o remetente ou o domínio de email do remetente em uma mensagem é semelhante a um remetente ou domínio real:

- Um exemplo de representação do domínio contoso.com é ćóntoso.com.

- Um exemplo de representação do usuário michelle@contoso.com é michele@contoso.com.

Um domínio representado pode ser considerado legítimo (domínio registrado, registros de autenticação de email configurados, etc.), exceto pelo intuito de enganar destinatários.

As configurações de representação a seguir estão disponíveis apenas em políticas anti-phishing da ATP:

- **Usuários a serem protegidos**: impede que os usuários internos ou externos especificados sejam representados. Por exemplo, executivos (internos) e membros da diretoria (externos). Você pode adicionar até 60 endereços internos e externos. Essa lista de usuários protegidos é diferente da lista de destinatários aos quais a política se aplica na configuração **aplica** -se a.

  Por exemplo, você especifica Felipe Apodaca (felipea@contoso.com) como um usuário protegido em uma política que se aplica ao grupo chamado executivos. Mensagens de entrada enviadas para membros do grupo executivos onde o Felipe Apodaca é representado será acionado pela política (a ação que você configurou para usuários representados).

- **Domínios para proteger**: impedir que os domínios especificados sejam representados. Por exemplo, todos os domínios que você possui ([domínios aceitos](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) ou domínios específicos (domínios que você possui ou domínios de parceiros). Essa lista de domínios protegidos é diferente da lista de domínios aos quais a política se aplica na configuração **aplica** -se a.

  Por exemplo, você especifica tailspintoys.com como um domínio protegido em uma política que se aplica aos membros do grupo chamado executivos. As mensagens de entrada enviadas para membros do grupo executivos onde o tailspintoys.com é representado serão acionadas pela política (a ação que você configura para domínios representados).

- **Ações para usuários ou domínios protegidos**: escolha a ação a ser realizada em mensagens de entrada que contenham tentativas de representação em relação aos usuários protegidos e domínios protegidos na política. Você pode especificar ações diferentes para representação de usuários protegidos vs. representação de domínios protegidos:

  - **Não aplicar nenhuma ação**

  - **Redirecionar mensagem para outros endereços de email**: envia a mensagem para os destinatários especificados, e não para os destinatários pretendidos.

  - **Mover mensagem para a pasta lixo eletrônico**: a mensagem é entregue à caixa de correio e movida para a pasta lixo eletrônico. No Exchange Online, a mensagem é movida para a pasta lixo eletrônico se a regra de lixo eletrônico estiver habilitada na caixa de correio (habilitada por padrão). Para obter mais informações, consulte [Configurar definições de lixo eletrônico em caixas de correio do Exchange Online no Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

    - **Colocar a mensagem em quarentena**: envia a mensagem para quarentena em vez dos destinatários pretendidos. Para obter informações sobre quarentena, confira os seguintes tópicos:

    - [Quarentena no Microsoft 365](quarantine-email-messages.md)
    - [Gerenciar arquivos e mensagens em quarentena como um administrador no Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Localizar e liberar mensagens em quarentena como um usuário no Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

  - **Entregar a mensagem e adicionar outros endereços à linha Cco**: entregar a mensagem aos destinatários pretendidos e entregar silenciosamente a mensagem aos destinatários especificados.

  - **Excluir a mensagem antes de ser entregue**: exclui silenciosamente a mensagem inteira, incluindo todos os anexos.

- **Dicas de segurança**: habilita ou desabilita as seguintes dicas de segurança de representação que irão aparecer mensagens que falham em verificações de representação:

  - **Usuários representados**: o endereço de contém um usuário protegido.
  - **Domínios representados**: o endereço de contém um domínio protegido.
  - **Caracteres incomuns**: o endereço de contém conjuntos de caracteres usuais (por exemplo, símbolos matemáticos e texto ou uma mistura de letras maiúsculas e minúsculas) em um remetente ou domínio protegido.

- **Inteligência de caixa de correio**: habilita ou desabilita a inteligência artificial (ai) que determina os padrões de email do usuário com seus contatos frequentes. Essa configuração ajuda o AI a distinguir entre emails legítimos e falsificados desses contatos. O Mailbox Intelligence só está disponível para caixas de correio do Exchange Online.

- **Proteção de representação baseada em inteligência de caixa de correio**: habilita ou desabilita os resultados de representação avançada com base no mapa de remetentes individuais de cada usuário. Esta inteligência permite que a Microsoft 365 Personalize a detecção de representação de usuário e manipule melhor os falsos positivos. Quando a representação do usuário é detectada, você pode definir uma ação específica a ser executada na mensagem:

  - **Não aplicar nenhuma ação**
  - **Redirecionar mensagem para outros endereços de email**
  - **Mover mensagem para a pasta Lixo Eletrônico**
  - **Colocar a mensagem em quarentena**
  - **Entregar a mensagem e adicionar outros endereços à linha Cco**
  - **Excluir a mensagem antes de ser entregue**

- **Remetentes e domínios confiáveis**: exceções às configurações de proteção de representação. As mensagens dos domínios remetentes e remetentes especificados nunca são classificadas como ataques baseados na representação pela política. Em outras palavras, a ação para remetentes protegidos, domínios protegidos ou proteção de inteligência de caixa de correio não é aplicada a esses remetentes confiáveis ou domínios de remetente. O limite máximo para essas listas é de aproximadamente 1000 entradas.

### <a name="advanced-phishing-thresholds-in-atp-anti-phishing-policies"></a>Limites avançados de phishing nas políticas anti-phishing da ATP

Os seguintes limites avançados de phishing estão disponíveis apenas em políticas anti-phishing da ATP para controlar a sensibilidade para aplicar modelos de aprendizado de máquina às mensagens para determinar uma veredicto de phishing:

- **1-padrão**: Este é o valor padrão. A gravidade da ação tomada na mensagem depende do grau de confiança de que a mensagem é phishing (baixa, média, alta ou muito alta confiança). Por exemplo, as mensagens identificadas como phishing com um nível muito elevado de confiança têm as ações mais severas aplicadas, enquanto as mensagens identificadas como phishing com um baixo grau de confiança têm menos ações aplicadas.

- **2-agressivo**: as mensagens identificadas como phishing com um alto grau de confiança são tratadas como se tivessem sido identificadas com um nível muito alto de confiança.

- **3-mais agressivo**: as mensagens que são identificadas como phishing com um grau de confiança médio ou alto são tratadas como se tivessem sido identificadas com um grau muito alto de confiança.

- **4-mais agressivo**: as mensagens identificadas como phishing com um nível de confiança baixo, médio ou alto são tratadas como se tivessem sido identificadas com um grau muito alto de confiança.

A chance de falsos positivos (boas mensagens marcadas como ruins) aumenta à medida que você aumenta essa configuração. Para obter informações sobre as configurações recomendadas, consulte [configurações de política de anti-phishing do Office ATP](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).
