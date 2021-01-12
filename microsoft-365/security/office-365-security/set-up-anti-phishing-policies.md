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
description: Os administradores podem saber mais sobre as políticas anti-phishing disponíveis no Exchange Online Protection (EOP) e no Microsoft Defender para Office 365.
ms.openlocfilehash: dadb41e1f0ff9e18681b13ad3d265f3f436c2052
ms.sourcegitcommit: f40378013757d560d5566a11ad4e6f527c018cc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49796189"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Políticas anti-phishing no Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


As políticas para definir configurações de proteção anti-phishing estão disponíveis nas organizações do Microsoft 365 com caixas de correio do Exchange Online, organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online e organizações do Microsoft Defender para Office 365.

As políticas anti-phishing no Microsoft Defender para Office 365 só estão disponíveis em organizações que têm o Defender para Office 365. Por exemplo:

- Microsoft 365 Enterprise E5, Microsoft 365 Education A5, etc.
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)
- [Microsoft Defender para Office 365 como um complemento](https://products.office.com/exchange/advance-threat-protection)

As diferenças de alto nível entre as políticas anti-phishing no EOP e as políticas anti-phishing no Microsoft Defender para Office 365 são descritas na tabela a seguir:

****

|Recurso|Políticas anti-phishing no EOP|Políticas anti-phishing no Microsoft Defender para Office 365|
|---|:---:|:---:|
|Política padrão criada automaticamente|![Marca de seleção](../../media/checkmark.png)|![Marca de seleção](../../media/checkmark.png)|
|Criar políticas personalizadas|![Marca de seleção](../../media/checkmark.png)|![Marca de seleção](../../media/checkmark.png)|
|Configurações de política<sup>\*</sup>|![Marca de seleção](../../media/checkmark.png)|![Marca de seleção](../../media/checkmark.png)|
|Configurações de representação||![Marca de seleção](../../media/checkmark.png)|
|Configurações de spoof|![Marca de seleção](../../media/checkmark.png)|![Marca de seleção](../../media/checkmark.png)|
|Limites avançados de phishing||![Marca de seleção](../../media/checkmark.png)|
|

<sup>\*</sup> Na política padrão, o nome e a descrição da política são somente leitura (a descrição está em branco) e você não pode especificar a quem a política se aplica (a política padrão se aplica a todos os destinatários).

Para configurar políticas anti-phishing, consulte os seguintes artigos:

- [Configurar políticas anti-phishing em EOP](configure-anti-phishing-policies-eop.md)

- [Configurar políticas anti-phishing no Microsoft Defender para Office 365](configure-atp-anti-phishing-policies.md)

O restante deste artigo descreve as configurações disponíveis nas políticas anti-phishing no EOP e no Defender para Office 365.

## <a name="policy-settings"></a>Configurações de política

As seguintes configurações de política estão disponíveis em políticas anti-phishing no EOP e no Microsoft Defender para Office 365:

- **Nome:** você não pode renomear a política anti-phishing padrão, mas pode nomear e renomear as políticas personalizadas que criar.

- **Descrição** Não é possível adicionar uma descrição à política anti-phishing padrão, mas você pode adicionar e alterar a descrição das políticas personalizadas que criar.

- **Aplicado a:** identifica destinatários internos aos que a política anti-phishing se aplica. Esse valor é necessário em políticas personalizadas e não está disponível na política padrão (a política padrão se aplica a todos os destinatários).

  Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção. Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_). Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).

  - **O destinatário é:** uma ou mais caixas de correio, usuários de email ou contatos de email em sua organização.
  - **O destinatário é membro de:** um ou mais grupos em sua organização.
  - **O domínio do destinatário** é: um ou mais dos domínios aceitos configurados no Microsoft 365.

  - **Exceto quando:** Exceções para a regra. As configurações e o comportamento são exatamente como as condições:

    - **O destinatário é**
    - **O destinatário é membro do**
    - **O domínio do destinatário é**

  > [!NOTE]
  > A **configuração Aplicada à** configuração é necessária em políticas anti-phishing personalizadas para identificar os **destinatários** da mensagem aos quais a política <u>se aplica.</u> As políticas anti-phishing no Microsoft Defender para Office 365 também têm configurações de representação <u></u> onde você pode especificar endereços de email ou domínios de remetentes [individuais](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) que receberão proteção contra representação, conforme descrito mais adiante neste artigo.

## <a name="spoof-settings"></a>Configurações de spoof

A falsa é quando o endereço De em uma mensagem de email (o endereço do remetente que aparece em clientes de email) não combina com o domínio da fonte de email. Para obter mais informações sobre a spoofing, consulte [Proteção anti-spoofing no Microsoft 365.](anti-spoofing-protection.md)

As seguintes configurações de spoof estão disponíveis em políticas anti-phishing no EOP e no Microsoft Defender para Office 365:

- **Proteção anti-spoofing:** Habilita ou desabilita a proteção anti-spoofing. Recomendamos que você o deixe habilitado. Use a política **de inteligência contra spoof para** permitir ou bloquear determinados envios internos e externos. Para obter mais informações, contra [Configurar a inteligência contra falsificação no Microsoft 365](learn-about-spoof-intelligence.md).

  > [!NOTE]
  >
  > - A proteção antifalsagem está habilitada por padrão na política anti-phishing padrão e em todas as novas políticas anti-phishing personalizadas que você criar.
  >
  > - Você não precisará desabilitar a proteção anti-spoofing se seu registro MX não apontar para o Microsoft 365; em vez disso, você habilita a Filtragem Aprimorada para Conectores. Para obter instruções, consulte [Filtragem aprimorada para conectores no Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)
  >
  > - Desabilitar a proteção anti-spoofing desabilita apenas a proteção contra spoofing implícita de verificações [de autenticação compostas.](email-validation-and-authentication.md#composite-authentication) Se o remetente falhar em verificações explícitas do [DMARC](use-dmarc-to-validate-email.md) em que a política está definida como quarentena ou rejeição, a mensagem ainda será colocada em quarentena ou rejeitada.

  Para mensagens de remententes bloqueados, você também pode especificar a ação a ser tomada nas mensagens:

  - **Mover mensagem para a pasta Lixo Eletrônico:** esse é o valor padrão. A mensagem é entregue à caixa de correio e movida para a pasta Lixo Eletrônico. No Exchange Online, a mensagem é movida para a pasta Lixo Eletrônico se a regra de lixo eletrônico estiver habilitada na caixa de correio (ela é habilitada por padrão). Para obter mais informações, consulte [Definir configurações de lixo eletrônico em caixas de correio do Exchange Online no Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

  - **Colocar a mensagem em quarentena:** envia a mensagem para a quarentena em vez dos destinatários pretendido. Para obter informações sobre a quarentena, consulte os seguintes artigos:

    - [Quarentena no Microsoft 365](quarantine-email-messages.md)
    - [Gerenciar mensagens e arquivos em quarentena como administrador no Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Encontrar e liberar mensagens em quarentena como um usuário no Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

- **Remetente não autenticado:** consulte as informações na próxima seção.

### <a name="unauthenticated-sender"></a>Remetente não autenticado

A identificação de remetente não autenticado faz parte das configurações de [Spoof](#spoof-settings) disponíveis nas políticas anti-phishing no EOP e no Microsoft Defender para Office 365, conforme descrito na seção anterior.

A **configuração Remetente** Não Autenticado habilita ou desabilita a identificação de remetente não autenticado no Outlook. Especificamente:

- Um ponto de interrogação (?) será adicionado à foto do remetente se a  mensagem não passar nas verificações SPF ou DKIM e a mensagem não passar no DMARC ou na autenticação [composta.](email-validation-and-authentication.md#composite-authentication) Desabilitar a identificação do remetente não autenticado impede que o ponto de interrogação seja adicionado à foto do remetente.

- A marca via (chris@contoso.com <u>via</u> fabrikam.com) será adicionada se o domínio no endereço De (o remetente da mensagem exibido em clientes de email) for diferente do domínio na assinatura DKIM ou no endereço **MAIL FROM.** Para obter mais informações sobre esses endereços, consulte [Uma visão geral dos padrões de mensagens de email.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

  Desabilitar a identificação do remetente não autenticado não impede que a marca via seja adicionada se o domínio no endereço De for diferente do domínio na assinatura DKIM ou no endereço MAIL FROM.

Para impedir que o ponto de interrogação ou marca seja adicionado às mensagens de determinados envios, você tem as seguintes opções:

- Permitir que o remetente spoof na política de inteligência de spoof. Essa ação impedirá que a marca via apareça em mensagens do remetente quando a identificação do remetente não autenticado estiver desabilitada. Para obter instruções, [confira Configurar a inteligência contra spoof no Microsoft 365.](learn-about-spoof-intelligence.md)

- [Configure a autenticação](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) de email para o domínio do remetente.
  - Para o ponto de interrogação na foto do remetente, SPF ou DKIM são os mais importantes.
  - Para a marca via, confirme se o domínio na assinatura DKIM ou no endereço **MAIL FROM** corresponde (ou é um subdomínio de) ao domínio no endereço De.

Para saber mais, confira [Identificar mensagens suspeitas no Outlook.com e no Outlook na Web](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configurações exclusivas em políticas anti-phishing no Microsoft Defender para Office 365

Esta seção descreve as configurações de política que só estão disponíveis em políticas anti-phishing no Microsoft Defender para Office 365.

> [!NOTE]
> A política anti-phishing padrão no Microsoft Defender para Office 365 fornece proteção contra [spoof](set-up-anti-phishing-policies.md#spoof-settings) e inteligência de caixa de correio para todos os destinatários. No entanto, os outros recursos de proteção [contra](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) representação disponíveis e configurações avançadas não estão configurados ou [habilitados](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) na política padrão. Para habilitar todos os recursos de proteção, modifique a política anti-phishing padrão ou crie políticas anti-phishing adicionais.

### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configurações de representação em políticas anti-phishing no Microsoft Defender para Office 365

A representação é onde o remetente ou o domínio de email do remetente em uma mensagem se parece com um remetente ou domínio real:

- Um exemplo de representação do domínio contoso.com é ćóntoso.com.
- Um exemplo de representação do usuário michelle@contoso.com é michele@contoso.com.

Caso contrário, um domínio representado pode ser considerado legítimo (domínios registrados, registros de autenticação de email configurados, etc.), exceto pelo intuito de enganar os destinatários.

As seguintes configurações de representação só estão disponíveis em políticas anti-phishing no Microsoft Defender para Office 365:

- **Usuários para proteger:** impede que os endereços de email internos ou externos especificados sejam personificados **como envios de mensagens.** Por exemplo, você recebe uma mensagem de email do vice-presidente da empresa solicitando que você envie algumas informações internas da empresa para ela. Você faria isso? Muitas pessoas enviariam a resposta sem pensar.

  Você pode usar usuários protegidos para adicionar endereços de email internos e externos do remetente para se proteger contra representação. Essa lista  de destinatários protegidos contra a representação de usuário é diferente da lista de **destinatários** aos quais a política se  aplica (todos [](#policy-settings) os destinatários da política padrão; destinatários específicos conforme configurado na configuração Aplicado à configuração na seção Configurações de política).

  > [!NOTE]
  >
  > - Em cada política anti-phishing, você pode especificar um máximo de 60 usuários protegidos (endereços de email do remetente). Você não pode especificar o mesmo usuário protegido em várias políticas.
  >
  > - A proteção contra representação de usuário não funcionará se o remetente e o destinatário se comunicaram anteriormente por email. Se o remetente e o destinatário nunca se comunicarem por email, a mensagem será identificada como uma tentativa de representação.

  Por padrão, nenhum endereço de email do remetente está configurado para proteção contra representação em **Usuários para proteger.** Portanto, por padrão, nenhum endereço de email do remetente é coberto pela proteção contra representação, seja na política padrão ou em políticas personalizadas.

  Quando você adiciona endereços de  email internos ou externos aos Usuários para proteger a lista, as mensagens desses envios estão sujeitas a verificações de proteção contra representação.  A mensagem será verificada  quanto à representação se **a** mensagem for enviada a um destinatário a que a política se aplica (todos os destinatários da política padrão; **Aplicado a destinatários** em políticas personalizadas). Se a representação for detectada no endereço de email do remetente, as ações de proteção de representação para os usuários serão aplicadas à mensagem (o que fazer com a mensagem, se mostrar dicas de segurança de usuários personificados etc.).

- **Domínios a serem protegidos:** impede que os domínios especificados sejam personificados no **domínio do remetente da mensagem.** Por exemplo, todos os domínios que você possui[(domínios aceitos)](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)ou domínios específicos (domínios que você possui ou domínios de parceiros). Essa lista de domínios de **remetentes protegidos** contra representação é diferente da lista de **destinatários** aos quais a política se aplica  (todos os [](#policy-settings) destinatários da política padrão; destinatários específicos conforme configurado na configuração Aplicada à seção Configurações de política).

  > [!NOTE]
  > O número máximo de domínios protegidos que você pode definir em todas as políticas anti-phishing é 50.

  Por padrão, nenhum domínio do remetente está configurado para proteção contra representação em **Domínios para proteger.** Portanto, por padrão, nenhum domínio do remetente é coberto pela proteção contra representação, seja na política padrão ou em políticas personalizadas.

  Quando você adiciona domínios aos **Domínios** para proteger a lista, as mensagens dos envios nesses domínios estão **sujeitas** a verificações de proteção contra representação. A mensagem será verificada  quanto à representação se **a** mensagem for enviada a um destinatário a que a política se aplica (todos os destinatários da política padrão; **Aplicado a destinatários** em políticas personalizadas). Se a representação for detectada no domínio do remetente, as ações de proteção contra representação de domínios serão aplicadas à mensagem (o que fazer com a mensagem, se os usuários personificados serão ou não protegidos, etc.).

- Ações para usuários ou **domínios protegidos:** escolha a ação a ser tomada em mensagens de entrada que contenham tentativas de representação contra os usuários protegidos e domínios protegidos na política. Você pode especificar diferentes ações para representação de usuários protegidos versus representação de domínios protegidos:

  - **Não aplicar nenhuma ação**

  - **Redirecionar mensagem para outros endereços de email:** envia a mensagem para os destinatários especificados em vez dos destinatários pretendido.

  - **Mover mensagem para a pasta Lixo** Eletrônico: a mensagem é entregue à caixa de correio e movida para a pasta Lixo Eletrônico. No Exchange Online, a mensagem é movida para a pasta Lixo Eletrônico se a regra de lixo eletrônico estiver habilitada na caixa de correio (ela é habilitada por padrão). Para obter mais informações, consulte [Definir configurações de lixo eletrônico em caixas de correio do Exchange Online no Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

    - **Colocar a mensagem em quarentena:** envia a mensagem para a quarentena em vez dos destinatários pretendido. Para obter informações sobre a quarentena, consulte os seguintes artigos:

    - [Quarentena no Microsoft 365](quarantine-email-messages.md)
    - [Gerenciar mensagens e arquivos em quarentena como administrador no Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Encontrar e liberar mensagens em quarentena como um usuário no Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

  - **Entregar a mensagem e adicionar outros** endereços à linha Cc: entregar a mensagem aos destinatários pretendido e entregar silenciosamente a mensagem aos destinatários especificados.

  - **Exclua a mensagem antes de ser entregue:** exclui silenciosamente a mensagem inteira, incluindo todos os anexos.

- **Dicas de** segurança: Habilita ou desabilita as seguintes dicas de segurança de representação que aparecerão mensagens reprovadas nas verificações de representação:

  - **Usuários personificados:** o endereço De contém um usuário protegido.
  - **Domínios personificados:** o endereço De contém um domínio protegido.
  - **Caracteres** incomuns: O endereço De contém conjuntos de caracteres incomuns (por exemplo, símbolos matemáticos e texto ou uma mistura de letras maiúsculas e minúsculas) em um remetente ou domínio protegido.

  > [!IMPORTANT]
  >
  > Mesmo quando as dicas de segurança de representação estão desligadas, recomendamos que você use uma regra de fluxo de emails (também conhecida como regra  de transporte) para adicionar um header de mensagem chamado **X-MS-Exchange-EnableFirstContactSafetyTip** com valor habilitado para mensagens.  Uma dica de segurança notificará os destinatários na primeira vez em que receberem uma mensagem do remetente ou se eles não receberem mensagens com frequência do remetente.
  > :::image type="content" source="../../media/safety-tip-first-contact-multiple-recipients.png" alt-text="O texto da dica de segurança para proteção contra representação com vários destinatários.":::

- **Inteligência de** caixa de correio: habilita ou desabilita inteligência artificial (AI) que determina os padrões de email do usuário com seus contatos frequentes. Essa configuração ajuda a IA a distinguir emails legítimos e spoofed desses contatos. A inteligência de caixa de correio só está disponível para caixas de correio do Exchange Online.

- **Proteção contra representação baseada em inteligência** de caixa de correio: habilita ou desabilita os resultados de representação aprimorados com base no mapa de remetentes individuais de cada usuário. Essa inteligência permite que o Microsoft 365 personalize a detecção de representação de usuário e lida melhor com falsos positivos. Quando a representação de usuário é detectada, você pode definir uma ação específica a ser tomada na mensagem:

  - **Não aplicar nenhuma ação**
  - **Redirecionar mensagem para outros endereços de email**
  - **Mover mensagem para a pasta Lixo Eletrônico**
  - **Colocar a mensagem em quarentena**
  - **Entregar a mensagem e adicionar outros endereços à linha Cc**
  - **Excluir a mensagem antes de ser entregue**

- **Senders e domínios confiáveis:** exceções às configurações de proteção contra representação. As mensagens dos remetentes e domínios de remetente especificados nunca são classificadas como ataques baseados em representação pela política. Em outras palavras, a ação para remetentes protegidos, domínios protegidos ou proteção de inteligência de caixa de correio não é aplicada a esses remetentes ou domínios de remetente confiáveis. O limite máximo para essas listas é de aproximadamente 1.000 entradas.

### <a name="advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Limites avançados de phishing em políticas anti-phishing no Microsoft Defender para Office 365

Os seguintes limites avançados de phishing só estão disponíveis em políticas anti-phishing no Microsoft Defender para Office 365. Esses limites controlam a sensibilidade para a aplicação de modelos de aprendizado de máquina a mensagens para determinar um veredito de phishing:

- **1 - Padrão:** este é o valor padrão. A gravidade da ação que é realizada na mensagem depende do grau de confiança de que a mensagem é phishing (confiança baixa, média, alta ou muito alta). Por exemplo, as mensagens identificadas como phishing com um grau muito alto de confiança têm as ações mais graves aplicadas, enquanto as mensagens identificadas como phishing com um baixo grau de confiança têm ações menos graves aplicadas.

- **2 - Agressivo:** as mensagens identificadas como phishing com um alto grau de confiança são tratadas como se fossem identificadas com um grau muito alto de confiança.

- **3 - Mais agressivo:** as mensagens identificadas como phishing com um grau médio ou alto de confiança são tratadas como se fossem identificadas com um grau de confiança muito alto.

- **4 - Mais** agressivos: as mensagens identificadas como phishing com um baixo, médio ou alto grau de confiança são tratadas como se fossem identificadas com um grau muito alto de confiança.

A chance de falsos positivos (mensagens boas marcadas como ruins) aumenta à medida que você aumenta essa configuração. Para obter informações sobre as configurações recomendadas, consulte a política [anti-phishing no Microsoft Defender para configurações do Office 365.](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)
