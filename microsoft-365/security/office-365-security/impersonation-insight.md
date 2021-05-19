---
title: Insight de representação
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender como o insight de representação funciona. Eles podem determinar rapidamente quais enviadores estão enviando emails legítimos para suas organizações de domínios que não passam verificações de autenticação de email (SPF, DKIM ou DMARC).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a11dd30030ccce886abd50ff72b5a09b10938ece
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535753"
---
# <a name="impersonation-insight-in-defender-for-office-365"></a>Visão de representação no Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Os recursos descritos neste artigo estão em Visualização, estão sujeitos a alterações e não estão disponíveis em todas as organizações.

Representação é onde o remetente de uma mensagem de email é muito semelhante a um endereço de email de remetente real ou esperado. Os invasores geralmente personificam endereços de email de remetente em phishing ou outros tipos de ataques em um esforço para obter a confiança do destinatário. Há basicamente dois tipos de representação:

- **Representação de domínio**: em vez de lila@contoso.com, o endereço de email do remetente personificado é lila@ćóntoso.com.
- **Representação do usuário**: em vez de michelle@contoso.com, o endereço de email do remetente personificado é rnichell@contoso.com.

A representação de domínio é diferente [da spoofing](anti-spoofing-protection.md)de domínio , porque o domínio personificado normalmente é um domínio real registrado. Mensagens de senders no domínio personificado podem e geralmente passam verificações regulares de autenticação de email que identificariam tentativas de spoofing (SPF, DKIM e DMARC).

A proteção contra representação faz parte das configurações de política anti-phishing) que são exclusivas do Microsoft Defender para Office 365. Para obter mais informações sobre essas configurações, consulte [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

Você pode usar o insight de representação para identificar rapidamente mensagens de remetentes ou domínios remetentes personificados que você configurou para proteção de representação.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente ao insight de representação na página **Anti-phishing,** use <https://protection.office.com/antiphishing> .

- Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos deste artigo:
  - **Organization Management**
  - **Administrador de Segurança**
  - **Leitor de Segurança**
  - **Leitor Global**

  Para saber mais, confira [Permissões no Centro de Conformidade e Segurança](permissions-in-the-security-and-compliance-center.md).

  **Observação**: a adição de usuários à função de Azure Active Directory correspondente no centro de administração Microsoft 365 fornece  aos usuários as permissões necessárias no Centro de Conformidade & segurança e permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).

- Você habilita e configura a proteção de representação em políticas anti-phishing no Microsoft Defender para Office 365. A proteção de representação não está habilitada por padrão. Para obter mais informações, consulte [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

## <a name="open-the-impersonation-insight-in-the-security--compliance-center"></a>Abra o insight de representação no Centro de Conformidade & Segurança

1. No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **Anti-phishing**.

2. Na página **principal Anti-phishing**, o insight de representação tem a seguinte aparência:

   Esse insight tem dois modos:

    - **Modo de** visão: se a proteção de representação estiver habilitada e configurada em qualquer política anti-phishing, o insight mostrará o número de mensagens detectadas de senders personificados nos últimos sete dias. Esse é o total de todos os envios personificados detectados de todas as políticas anti-phishing.
    - **E** se o modo : se a proteção de representação não estiver habilitada e  configurada em nenhuma política anti-phishing ativa, a visão mostra quantas mensagens teriam sido detectadas pelos nossos recursos de proteção de representação nos últimos sete dias.

   De qualquer forma, **Domínios personificados** mostra o número de  mensagens de senders em domínios protegidos, enquanto Usuários personificados mostram o número de mensagens de usuários protegidos.

## <a name="view-information-about-messages-from-senders-in-impersonated-domains"></a>Exibir informações sobre mensagens de senders em domínios personificados

No insight de representação, clique **em Domínios personificados**. A **página de perspicácia** de representação aberta contém as seguintes informações:

- **Domínio do Remetente**: o domínio de representação, que é o domínio usado para enviar a mensagem de email. 
- **Contagem de** mensagens : o número de mensagens de representação do domínio do remetente nos últimos 7 dias.
- **Tipo de representação**: esse valor mostra o local detectado da representação (por exemplo, **Domínio no endereço**).
- **Domínios personificados:** o domínio personificado, que deve se parecer muito com o domínio configurado para proteção de representação na política anti-phishing.
- **Tipo de** domínio : esse valor é **domínio da** empresa para domínios internos ou **domínio personalizado** para domínios personalizados.
- **Política**: a política anti-phishing que detectou o domínio personificado.
- **Permissão para representar**: um dos seguintes valores:
  - **Sim**: o domínio foi configurado como domínio confiável (uma exceção para proteção de representação) na política anti-spam. Mensagens de senders no domínio personificado foram detectadas, mas permitidas.
  - **Não**: o domínio foi configurado para proteção de representação na política anti-spam. As mensagens de remetentes no domínio personificado foram detectadas e agidas com base na ação para domínios personificados na política anti-spam.

Você pode clicar em títulos de coluna selecionados para classificar os resultados.

Para filtrar os resultados, você pode usar a caixa de domínio **Filter** para inserir uma lista separada por vírgulas de valores para filtrar os resultados.

### <a name="view-details-about-messages-from-senders-in-impersonated-domains"></a>Exibir detalhes sobre mensagens de senders em domínios personificados

Na página **Percepção de representação,** selecione uma das linhas disponíveis. O sobremenu de detalhes que aparece contém as seguintes informações e recursos:

- **Política de representação de seleção para modificar**: Selecione a política anti-phishing afetada que você deseja modificar. Somente as políticas em que o domínio personificado é definido na política estão disponíveis. Consulte a página anterior para ver qual política foi realmente responsável por detectar o domínio personificado (provavelmente com base no destinatário e na prioridade da política).

- **Adicionar à** lista de representação permitida : use essa alternância para adicionar ou remover o remetente dos remetentes e **domínios** confiáveis (exceções de representação) para a política anti-phishing selecionada:
  - Se o **valor Allowed para representar essa** entrada for **Não**, a alternância será desligada. Para isentar todos os envios neste domínio de avaliação por proteção de representação, deslize a alternância para: ![ Alternar em ](../../media/scc-toggle-on.png) . O domínio é adicionado à lista **Domínios Confiáveis** nas configurações de proteção de representação da política anti-phishing.
  - Se o **valor Permitido para representar essa** entrada foi **Sim**, a alternância está em. Para retornar todos os senders neste domínio para avaliação por meio da proteção de representação, deslize a alternância para off: ![ Alternar ](../../media/scc-toggle-off.png) para fora . O domínio é removido da lista **Domínios Confiáveis** nas configurações de proteção de representação da política anti-phishing.

- Por que pegamos isso.
- O que você precisa fazer.
- Um resumo de domínio que lista o domínio personificado.
- WhoIs dados sobre o remetente.
- Um link para abrir [o Explorador de Ameaças](threat-explorer.md) para ver detalhes adicionais sobre o remetente.
- Mensagens semelhantes do mesmo remetente que foram entregues à sua organização.

## <a name="view-information-about-messages-from-impersonated-senders"></a>Exibir informações sobre mensagens de senders personificados

No insight de representação, clique em **Usuários personificados**. A **página de perspicácia** de representação aberta contém as seguintes informações:

- **Remetente**: o endereço de email do remetente que representa o remetente que enviou a mensagem de email.
- **Contagem de** mensagens : o número de mensagens do remetente que representa nos últimos 7 dias.
- **Tipo de representação**: esse valor é **Usuário em nome de exibição**.
- **Usuários** personificados: o endereço de email do remetente personificado, que deve se parecer muito com o usuário configurado para proteção de representação na política anti-phishing.
- **Tipo de** usuário : esse valor mostra o tipo de proteção aplicada (por exemplo, **Usuário protegido** ou Inteligência de Caixa **de Correio**).
- **Política**: a política anti-phishing que detectou o remetente personificado.
- **Permissão para representar**: um dos seguintes valores:
  - **Sim**: o remetente foi configurado como usuário confiável (uma exceção para proteção de representação) na política anti-spam. As mensagens do remetente personificado foram detectadas, mas permitidas.
  - **Não**: o remetente foi configurado para proteção de representação na política anti-spam. As mensagens do remetente personificado foram detectadas e agidas com base na ação para usuários personificados na política anti-spam.

Você pode clicar em títulos de coluna selecionados para classificar os resultados.

Para filtrar os resultados, você pode usar a caixa Filtro **remetente** para inserir uma lista separada por vírgulas de valores para filtrar os resultados.

### <a name="view-details-about-messages-from-impersonated-senders"></a>Exibir detalhes sobre mensagens de senders personificados

Na página **Percepção de representação,** selecione uma das linhas disponíveis. O sobremenu de detalhes que aparece contém as seguintes informações e recursos:

- **Política de representação de seleção para modificar**: Selecione a política anti-phishing afetada que você deseja modificar. Somente as políticas em que o remetente personificado está definido na política estão disponíveis. Consulte a página anterior para ver qual política foi realmente responsável por detectar o remetente personificado (provavelmente com base no destinatário e na prioridade da política).

- **Adicionar à** lista de representação permitida : use essa alternância para adicionar ou remover o remetente dos remetentes e **domínios** confiáveis (exceções de representação) para a política anti-phishing selecionada:
  - Se o **valor Allowed para representar essa** entrada for **Não**, a alternância será desligada. Para isentar o remetente da avaliação pela proteção de representação, deslize a alternância para: ![ Alternar ](../../media/scc-toggle-on.png) em . O remetente é adicionado à lista **Usuários** confiáveis nas configurações de proteção de representação da política anti-phishing.
  - Se o **valor Permitido para representar essa** entrada foi **Sim**, a alternância está em. Para retornar o remetente à avaliação pela proteção de representação, deslize a alternância para off: ![ Alternar ](../../media/scc-toggle-off.png) para fora . O remetente é removido da lista **Usuários** confiáveis nas configurações de proteção de representação da política anti-phishing.

- Por que pegamos isso.
- O que você precisa fazer.
- Um resumo do remetente que lista o remetente personificado.
- WhoIs dados sobre o remetente.
- Um link para abrir [o Explorador de Ameaças](threat-explorer.md) para ver detalhes adicionais sobre o remetente.
- Mensagens semelhantes do mesmo remetente que foram entregues à sua organização.
