---
title: Informações sobre usurpação de identidade
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
ms.openlocfilehash: 53baecd100851eb5ab05fe79751961baef3acd5c
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029664"
---
# <a name="impersonation-insight-in-defender-for-office-365"></a>Visão de representação no Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Os recursos descritos neste artigo estão em Visualização, estão sujeitos a alterações e não estão disponíveis em todas as organizações.

Representação é onde o remetente de uma mensagem de email é muito semelhante a um endereço de email de remetente real ou esperado. Os invasores geralmente personificam endereços de email de remetente em phishing ou outros tipos de ataques em um esforço para obter a confiança do destinatário. Há basicamente dois tipos de representação:

- **Representação de domínio**: em vez de lila@contoso.com, o endereço de email do remetente personificado é lila@ćóntoso.com.
- **Representação do usuário**: em vez de michelle@contoso.com, o endereço de email do remetente personificado é rnichell@contoso.com.

A representação de domínio é diferente [da spoofing](anti-spoofing-protection.md)de domínio , porque o domínio personificado normalmente é um domínio real registrado. Mensagens de senders no domínio personificado podem e geralmente passam verificações regulares de autenticação de email que identificariam tentativas de spoofing (SPF, DKIM e DMARC).

A proteção contra representação faz parte das configurações de política anti-phishing que são exclusivas do Microsoft Defender para Office 365. Para obter mais informações sobre essas configurações, consulte [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

Você pode usar o insight de representação no portal Microsoft 365 Defender para identificar rapidamente mensagens de remetentes ou domínios de remetentes personificados que você configurou para proteção de representação.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com>. Para ir diretamente ao insight de representação na página **Anti-phishing,** use <https://security.microsoft.com/antiphishing> . Para ir diretamente para a página **de visão de representação,** use <https://security.microsoft.com/impersonationinsight> .

- Você precisa ter permissões atribuídas no portal Microsoft 365 Defender antes de poder fazer os procedimentos neste artigo:
  - **Organization Management**
  - **Administrador de Segurança**
  - **Leitor de Segurança**
  - **Leitor Global**

  Para obter mais informações, consulte [Permissões no portal Microsoft 365 Defender .](permissions-in-the-security-and-compliance-center.md)

  **Observação**: adicionar usuários à função Active Directory do Azure correspondente no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no _portal_ do Microsoft 365 Defender e permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).

- Você habilita e configura a proteção de representação em políticas anti-phishing no Microsoft Defender para Office 365. A proteção de representação não está habilitada por padrão. Para obter mais informações, consulte [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md).

## <a name="open-the-impersonation-insight-in-the-microsoft-365-defender-portal"></a>Abra o insight de representação no Microsoft 365 Defender portal

1. No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \>  \> **Anti-phishing**.

2. Na página **Anti-phishing,** o insight de representação tem a seguinte aparência:

   ![Visão de representação e inteligência falsa na página política anti-phishing](../../media/m365-sc-impersonation-and-spoof-intelligence-insight.png)

   O insight tem dois modos:

    - **Modo** de visão: se a proteção de representação estiver habilitada e configurada em qualquer política anti-phishing, o insight mostrará o número de mensagens detectadas de domínios personificados e usuários personificados (senders) nos últimos sete dias. Esse é o total de todos os envios personificados detectados de todas as políticas anti-phishing.
    - **E** se o modo : se a proteção de representação não estiver habilitada e  configurada em nenhuma política anti-phishing ativa, a visão mostra quantas mensagens teriam sido detectadas pelos nossos recursos de proteção de representação nos últimos sete dias.

Para exibir informações sobre as detecções de representação, clique em **Exibir** personificações no insight de representação.

   > [!NOTE]
   > Para obter informações sobre a visão de inteligência falsa, consulte [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md).

## <a name="view-information-about-messages-from-senders-in-impersonated-domains"></a>Exibir informações sobre mensagens de senders em domínios personificados

Na página **Percepção de representação** que aparece depois de clicar em **Exibir** personificações no insight de representação, verifique se a guia **Domínios** está selecionada. A **guia Domínios** contém as seguintes informações:

- **Domínio do Remetente**: o domínio de representação, que é o domínio usado para enviar a mensagem de email.
- **Contagem de** mensagens : o número de mensagens de representação do domínio do remetente nos últimos 7 dias.
- **Tipo de representação**: esse valor mostra o local detectado da representação (por exemplo, **Domínio no endereço**).
- **Domínios personificados:** o domínio personificado, que deve se parecer muito com o domínio configurado para proteção de representação na política anti-phishing.
- **Tipo de** domínio : esse valor é **domínio da** empresa para domínios internos ou **domínio personalizado** para domínios personalizados.
- **Política**: a política anti-phishing que detectou o domínio personificado.
- **Permissão para representar**: um dos seguintes valores:
  - **Sim**: o domínio foi configurado como domínio confiável (uma exceção para proteção de representação) na política anti-phishing. Mensagens de senders no domínio personificado foram detectadas, mas permitidas.
  - **Não**: o domínio foi configurado para proteção de representação na política anti-phishing. As mensagens dos senders no domínio personificado foram detectadas e agidas com base na ação para domínios personificados na política anti-phishing.

Você pode clicar em títulos de coluna selecionados para classificar os resultados.

Para filtrar os resultados, você pode usar a caixa Pesquisar ícone de pesquisa para inserir uma lista de valores separada por ![ ](../../media/m365-cc-sc-search-icon.png)  vírgulas para filtrar os resultados.

### <a name="view-details-about-messages-from-senders-in-impersonated-domains"></a>Exibir detalhes sobre mensagens de senders em domínios personificados

Na guia **Domínios** na página **Percepção de representação,** selecione uma das detecções de representação disponíveis. O sobremenu de detalhes que aparece contém as seguintes informações e recursos:

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

Na página **Percepção de representação** que aparece depois de clicar em **Exibir** personificações no insight de representação, clique na **guia Usuários.** A **guia Usuários** contém as seguintes informações:

- **Remetente**: o endereço de email do remetente que representa o remetente que enviou a mensagem de email.
- **Contagem de** mensagens : o número de mensagens do remetente que representa nos últimos 7 dias.
- **Tipo de representação**: esse valor é **Usuário em nome de exibição**.
- **Usuários** personificados: o endereço de email do remetente personificado, que deve se parecer muito com o usuário configurado para proteção de representação na política anti-phishing.
- **Tipo de** usuário : esse valor mostra o tipo de proteção aplicada (por exemplo, **Usuário protegido** ou Inteligência de Caixa **de Correio**).
- **Política**: a política anti-phishing que detectou o remetente personificado.
- **Permissão para representar**: um dos seguintes valores:
  - **Sim**: o remetente foi configurado como usuário confiável (uma exceção para proteção de representação) na política anti-phishing. As mensagens do remetente personificado foram detectadas, mas permitidas.
  - **Não**: o remetente foi configurado para proteção de representação na política anti-phishing. As mensagens do remetente personificado foram detectadas e agidas com base na ação para usuários personificados na política anti-phishing.

Você pode clicar em títulos de coluna selecionados para classificar os resultados.

Para filtrar os resultados, você pode usar a caixa Filtro **remetente** para inserir uma lista separada por vírgulas de valores para filtrar os resultados.

### <a name="view-details-about-messages-from-impersonated-senders"></a>Exibir detalhes sobre mensagens de senders personificados

Na guia **Usuários** na página **Percepção de representação,** selecione uma das detecções de representação disponíveis. O sobremenu de detalhes que aparece contém as seguintes informações e recursos:

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
