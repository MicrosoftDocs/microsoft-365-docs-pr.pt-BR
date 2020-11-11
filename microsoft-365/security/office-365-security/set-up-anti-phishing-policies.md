---
title: Políticas anti-phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender sobre as políticas anti-phishing que estão disponíveis no Exchange Online Protection (EOP) e no Microsoft defender para Office 365.
ms.openlocfilehash: b54f452fb984f61913f2ade53ad45ed169a43832
ms.sourcegitcommit: f941495e9257a0013b4a6a099b66c649e24ce8a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993349"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Políticas anti-phishing no Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


As políticas para definir as configurações de proteção anti-phishing estão disponíveis nas organizações do Microsoft 365 com caixas de correio do Exchange Online, organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online e organizações do Microsoft defender para Office 365.

As políticas anti-phishing no Microsoft defender para Office 365 só estão disponíveis em organizações que tenham o defender for Office 365. Por exemplo:

- Microsoft 365 Enterprise e5, Microsoft 365 Education a5, etc.
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)
- [Microsoft defender para Office 365 como um complemento](https://products.office.com/exchange/advance-threat-protection)

As diferenças de alto nível entre políticas anti-phishing no EOP e nas políticas anti-phishing no Microsoft defender para Office 365 são descritas na tabela a seguir:

****

|Recurso|Políticas anti-phishing no EOP|Políticas anti-phishing no Microsoft defender para Office 365|
|---|:---:|:---:|
|Política padrão criada automaticamente|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Criar políticas personalizadas|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Configurações de política<sup>\*</sup>|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Configurações de representação||![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Configurações de spoof|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Limites avançados de phishing||![Marca de seleção](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<sup>\*</sup> Na política padrão, o nome e a descrição da política são somente leitura (a descrição está em branco) e não é possível especificar a quem a política se aplica (a política padrão se aplica a todos os destinatários).

Para configurar as políticas anti-phishing, consulte os seguintes artigos:

- [Configurar políticas anti-phishing no EOP](configure-anti-phishing-policies-eop.md)

- [Configurar políticas anti-phishing no Microsoft defender para Office 365](configure-atp-anti-phishing-policies.md)

O restante deste artigo descreve as configurações disponíveis em políticas anti-phishing no EOP e no defender para Office 365.

## <a name="policy-settings"></a>Configurações de política

As configurações de política a seguir estão disponíveis em políticas anti-phishing no EOP e no Microsoft defender para Office 365:

- **Name** : não é possível renomear a política anti-phishing padrão, mas você pode nomear e renomear políticas personalizadas que você criou.

- **Descrição** Não é possível adicionar uma descrição à política anti-phishing padrão, mas você pode adicionar e alterar a descrição das políticas personalizadas criadas.

- **Aplicado a** : identifica destinatários internos aos quais a política anti-phishing se aplica. Esse valor é necessário em políticas personalizadas e não está disponível na política padrão (a política padrão se aplica a todos os destinatários).

  Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção. Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_ ). Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_ ).

  - O **destinatário é** : uma ou mais caixas de correio, usuários de email ou contatos de email em sua organização.
  - **O destinatário é um membro de** : um ou mais grupos em sua organização.
  - **O domínio do destinatário é** : um ou mais dos domínios aceitos configurados no Microsoft 365.

  - **Exceto quando** : exceções da regra. As configurações e o comportamento são exatamente semelhantes às condições:

    - **O destinatário é**
    - **O destinatário é um membro de**
    - **O domínio do destinatário é**

  > [!NOTE]
  > A configuração **aplica-se a** é necessária em políticas anti-phishing personalizadas para identificar os **destinatários** da mensagem <u>a que a política se aplica</u>. As políticas anti-phishing no Microsoft defender para Office 365 também têm [configurações de representação](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) nas quais você pode especificar endereços de email de remetente individuais ou domínios <u>de remetente que receberão a proteção de representação</u> , conforme descrito mais adiante neste tópico.

## <a name="spoof-settings"></a>Configurações de spoof

Falsificação é quando o endereço de em uma mensagem de email (o endereço do remetente que é exibido em clientes de email) não corresponde ao domínio da fonte de email. Para obter mais informações sobre falsificação, consulte [proteção contra falsificação no Microsoft 365](anti-spoofing-protection.md).

As seguintes configurações de spoof estão disponíveis em políticas anti-phishing no EOP e no Microsoft defender para Office 365:

- **Proteção contra falsificação** : habilita ou desabilita a proteção contra falsificação. Recomendamos que você deixe-o habilitado. Você usa a **política de inteligência de spoof** para permitir ou bloquear remetentes internos e externos falsificados específicos. Para obter mais informações, contra [Configurar a inteligência contra falsificação no Microsoft 365](learn-about-spoof-intelligence.md).

  > [!NOTE]
  >
  > - A proteção contra falsificação é habilitada por padrão na política anti-phishing padrão e em qualquer nova política anti-phishing personalizada que você criar.
  >
  > - Você não precisa desabilitar a proteção contra falsificação se o registro MX não apontar para o Microsoft 365; em vez disso, habilite a filtragem avançada de conectores. Para obter instruções, consulte [filtragem avançada para conectores no Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

  Para mensagens de remetentes falsificados bloqueados, você também pode especificar a ação a ser tomada nas mensagens:

  - **Mover mensagem para a pasta de lixo eletrônico** : Este é o valor padrão. A mensagem é entregue à caixa de correio e movida para a pasta lixo eletrônico. No Exchange Online, a mensagem é movida para a pasta lixo eletrônico se a regra de lixo eletrônico estiver habilitada na caixa de correio (habilitada por padrão). Para obter mais informações, consulte [Configurar definições de lixo eletrônico em caixas de correio do Exchange Online no Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

  - **Colocar a mensagem em quarentena** : envia a mensagem para quarentena em vez dos destinatários pretendidos. Para obter informações sobre a quarentena, consulte os seguintes artigos:

    - [Quarentena no Microsoft 365](quarantine-email-messages.md)
    - [Gerenciar arquivos e mensagens em quarentena como um administrador no Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Localizar e liberar mensagens em quarentena como um usuário no Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

- **Remetente não autenticado** : Confira as informações na próxima seção.

### <a name="unauthenticated-sender"></a>Remetente não autenticado

A identificação de remetentes não autenticados faz parte das [configurações de spoof](#spoof-settings) que estão disponíveis em políticas anti-phishing no EOP e Microsoft defender para Office 365, conforme descrito na seção anterior.

A configuração de **remetente não autenticado** habilita ou desabilita a identificação de remetente não autenticado no Outlook. Especificamente:

- Um ponto de interrogação (?) será adicionado à foto do remetente se a mensagem não passar verificações SPF ou DKIM **e** a mensagem não passar DMARC ou [autenticação composta](email-validation-and-authentication.md#composite-authentication). Desabilitar a identificação de remetentes não autenticados impede que o ponto de interrogação seja adicionado à foto do remetente.

- A marca via (chris@contoso.com <u>via</u> Michelle@fabrikam.com) será adicionada se o domínio no endereço de (o remetente da mensagem exibido em clientes de email) for diferente do domínio na assinatura do DKIM ou do endereço **de email do** remetente. Para obter mais informações sobre esses endereços, consulte [uma visão geral dos padrões de mensagens de email](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).

  Desabilitar a identificação de remetente não autenticado não impede que a marca via seja adicionada se o domínio no endereço de for diferente do domínio na assinatura do DKIM ou do endereço de email do remetente.

Para impedir que o ponto de interrogação ou por meio da marca seja adicionado a mensagens de remetentes específicos, você tem as seguintes opções:

- Permitir que o remetente falsifique na política de inteligência de falsificação. Esta ação impedirá que a marca via seja exibida em mensagens do remetente quando a identificação de remetente não autenticado estiver desabilitada. Para obter instruções, consulte [Configure spoof Intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

- [Configurar a autenticação de email](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) para o domínio do remetente.
  
  - Para o ponto de interrogação na foto, SPF ou DKIM do remetente são os mais importantes.
  - Para a marca via, confirme se o domínio na assinatura DKIM ou o endereço **de email from** corresponde (ou é um subdomínio de) no endereço de.

Para obter mais informações, consulte [identificar mensagens suspeitas no Outlook.com e no Outlook na Web](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configurações exclusivas em políticas anti-phishing no Microsoft defender para Office 365

Esta seção descreve as configurações de política que estão disponíveis somente em políticas anti-phishing no Microsoft defender para Office 365.

> [!NOTE]
> Por padrão, as configurações exclusivas no defender para Office 365 não estão configuradas ou ativadas, mesmo na política padrão. Para aproveitar esses recursos, é necessário habilitá-los e configurá-los na política anti-phishing padrão ou criar e configurar políticas anti-phishing personalizadas.

### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configurações de representação em políticas anti-phishing no Microsoft defender para Office 365

A representação é onde o remetente ou o domínio de email do remetente em uma mensagem é semelhante a um remetente ou domínio real:

- Um exemplo de representação do domínio contoso.com é ćóntoso.com.
- Um exemplo de representação do usuário michelle@contoso.com é michele@contoso.com.

Caso contrário, um domínio representado pode ser considerado legítimo (domínios registrados, registros de autenticação de email configurados, etc.), exceto pelo intuito de enganar os destinatários.

As configurações de representação a seguir estão disponíveis apenas em políticas anti-phishing no Microsoft defender para Office 365:

- **Usuários a serem protegidos** : impede que os endereços de email internos ou externos especificados sejam representados **como remetentes de mensagens**. Por exemplo, você recebe uma mensagem de email do vice-presidente de sua empresa solicitando que você envie algumas informações internas da empresa. Você faria isso? Muitas pessoas enviariam a resposta sem pensar.

  Você pode usar usuários protegidos para adicionar endereços de email de remetente internos e externos para proteção contra representação. Esta lista de **remetentes** que são protegidos da representação do usuário é diferente da lista de **destinatários** aos quais a política se aplica (todos os destinatários da política padrão; destinatários específicos conforme configurados na configuração **aplica-se a à** , na seção [configurações de política](#policy-settings) ).

  > [!NOTE]
  >
  > - Em cada política anti-phishing, você pode especificar um máximo de 60 usuários protegidos (endereços de email do remetente). Você não pode especificar o mesmo usuário protegido em várias políticas.
  >
  > - A proteção de representação do usuário não funciona se o remetente e o destinatário tiverem sido comunicados anteriormente por email. Se o remetente e o destinatário nunca tiverem sido comunicados por email, a mensagem será identificada como uma tentativa de representação.

  Por padrão, nenhum endereço de email do remetente é configurado para proteção de representação nos **usuários para** proteção. Portanto, por padrão, nenhum endereço de email do remetente é coberto pela proteção de representação, seja na política padrão ou em políticas personalizadas.

  Quando você adiciona endereços de email internos ou externos à lista de **usuários para proteger** , as mensagens desses **remetentes** estão sujeitas às verificações de proteção de representação. A mensagem será verificada quanto à representação **se** a mensagem for enviada a um **destinatário** ao qual a política se aplica (todos os destinatários da política padrão; **Aplicado a** destinatários em políticas personalizadas). Se a representação for detectada no endereço de email do remetente, as ações de proteções de representação para os usuários serão aplicadas à mensagem (o que fazer com a mensagem, se mostrar dicas de segurança de usuários representados, etc.).

- **Domínios a serem protegidos** : impede que os domínios especificados sejam representados **no domínio do remetente da mensagem**. Por exemplo, todos os domínios que você possui ([domínios aceitos](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) ou domínios específicos (domínios que você possui ou domínios de parceiros). Esta lista de **domínios de remetentes** que são protegidos contra representação é diferente da lista de **destinatários** aos quais a política se aplica (todos os destinatários da política padrão; destinatários específicos conforme configurados na configuração **aplica-se a à** , na seção [configurações de política](#policy-settings) ).

  > [!NOTE]
  > O número máximo de domínios protegidos que você pode definir em todas as políticas anti-phishing é de 50.

  Por padrão, nenhum domínio de remetente é configurado para proteção de representação em **domínios para proteção**. Portanto, por padrão, nenhum domínio remetente é coberto pela proteção de representação, seja na política padrão ou em políticas personalizadas.

  Quando você adiciona domínios à lista de **domínios para proteger** , as mensagens de **remetentes nesses domínios** estão sujeitas às verificações de proteção de representação. A mensagem será verificada quanto à representação **se** a mensagem for enviada a um **destinatário** ao qual a política se aplica (todos os destinatários da política padrão; **Aplicado a** destinatários em políticas personalizadas). Se a representação for detectada no domínio do remetente, as ações de proteção de representação para domínios serão aplicadas à mensagem (o que fazer com a mensagem, se mostrará as dicas de segurança de usuários representados, etc.).

- **Ações para usuários ou domínios protegidos** : escolha a ação a ser realizada em mensagens de entrada que contenham tentativas de representação em relação aos usuários protegidos e domínios protegidos na política. Você pode especificar ações diferentes para representação de usuários protegidos vs. representação de domínios protegidos:

  - **Não aplicar nenhuma ação**

  - **Redirecionar mensagem para outros endereços de email** : envia a mensagem para os destinatários especificados, e não para os destinatários pretendidos.

  - **Mover mensagem para a pasta lixo eletrônico** : a mensagem é entregue à caixa de correio e movida para a pasta lixo eletrônico. No Exchange Online, a mensagem é movida para a pasta lixo eletrônico se a regra de lixo eletrônico estiver habilitada na caixa de correio (habilitada por padrão). Para obter mais informações, consulte [Configurar definições de lixo eletrônico em caixas de correio do Exchange Online no Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

    - **Colocar a mensagem em quarentena** : envia a mensagem para quarentena em vez dos destinatários pretendidos. Para obter informações sobre a quarentena, consulte os seguintes artigos:

    - [Quarentena no Microsoft 365](quarantine-email-messages.md)
    - [Gerenciar arquivos e mensagens em quarentena como um administrador no Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Localizar e liberar mensagens em quarentena como um usuário no Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

  - **Entregar a mensagem e adicionar outros endereços à linha Cco** : entregar a mensagem aos destinatários pretendidos e entregar silenciosamente a mensagem aos destinatários especificados.

  - **Excluir a mensagem antes de ser entregue** : exclui silenciosamente a mensagem inteira, incluindo todos os anexos.

- **Dicas de segurança** : habilita ou desabilita as seguintes dicas de segurança de representação que irão aparecer mensagens que falham em verificações de representação:

  - **Usuários representados** : o endereço de contém um usuário protegido.
  - **Domínios representados** : o endereço de contém um domínio protegido.
  - **Caracteres incomuns** : o endereço de contém conjuntos de caracteres usuais (por exemplo, símbolos matemáticos e texto ou uma mistura de letras maiúsculas e minúsculas) em um remetente ou domínio protegido.

  > [!NOTE]
  > Mesmo quando as dicas de segurança de representação estiverem desativadas, você poderá usar uma regra de fluxo de emails (também conhecida como regra de transporte) para adicionar um cabeçalho de mensagem chamado **X-MS-Exchange-EnableFirstContactSafetyTip** a mensagens. Dicas de segurança específicas serão exibidas notificando os destinatários de que geralmente não recebem emails do remetente ou em casos em que o destinatário recebe um email pela primeira vez do remetente.

- **Inteligência de caixa de correio** : habilita ou desabilita a inteligência artificial (ai) que determina os padrões de email do usuário com seus contatos frequentes. Essa configuração ajuda o AI a distinguir entre emails legítimos e falsificados desses contatos. O Mailbox Intelligence só está disponível para caixas de correio do Exchange Online.

- **Proteção de representação baseada em inteligência de caixa de correio** : habilita ou desabilita os resultados de representação avançada com base no mapa de remetentes individuais de cada usuário. Esta inteligência permite que a Microsoft 365 Personalize a detecção de representação de usuário e manipule melhor os falsos positivos. Quando a representação do usuário é detectada, você pode definir uma ação específica a ser executada na mensagem:

  - **Não aplicar nenhuma ação**
  - **Redirecionar mensagem para outros endereços de email**
  - **Mover mensagem para a pasta Lixo Eletrônico**
  - **Colocar a mensagem em quarentena**
  - **Entregar a mensagem e adicionar outros endereços à linha Cco**
  - **Excluir a mensagem antes de ser entregue**

- **Remetentes e domínios confiáveis** : exceções às configurações de proteção de representação. As mensagens dos domínios remetentes e remetentes especificados nunca são classificadas como ataques baseados na representação pela política. Em outras palavras, a ação para remetentes protegidos, domínios protegidos ou proteção de inteligência de caixa de correio não é aplicada a esses remetentes confiáveis ou domínios de remetente. O limite máximo para essas listas é de aproximadamente 1000 entradas.

### <a name="advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Limites avançados de phishing em políticas anti-phishing no Microsoft defender para Office 365

Os seguintes limites avançados de phishing estão disponíveis apenas em políticas anti-phishing no Microsoft defender para Office 365. Esses limites controlam a sensibilidade para aplicar modelos de aprendizado de máquina às mensagens para determinar uma veredicto de phishing:

- **1-padrão** : Este é o valor padrão. A gravidade da ação tomada na mensagem depende do grau de confiança de que a mensagem é phishing (baixa, média, alta ou muito alta confiança). Por exemplo, as mensagens identificadas como phishing com um nível muito elevado de confiança têm as ações mais severas aplicadas, enquanto as mensagens identificadas como phishing com um baixo grau de confiança têm menos ações aplicadas.

- **2-agressivo** : as mensagens identificadas como phishing com um alto grau de confiança são tratadas como se tivessem sido identificadas com um nível muito alto de confiança.

- **3-mais agressivo** : as mensagens que são identificadas como phishing com um grau de confiança médio ou alto são tratadas como se tivessem sido identificadas com um grau muito alto de confiança.

- **4-mais agressivo** : as mensagens identificadas como phishing com um nível de confiança baixo, médio ou alto são tratadas como se tivessem sido identificadas com um grau muito alto de confiança.

A chance de falsos positivos (boas mensagens marcadas como ruins) aumenta à medida que você aumenta essa configuração. Para obter informações sobre as configurações recomendadas, consulte [política anti-phishing no Microsoft defender para Office 365 Settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).
