---
title: Walkthrough-visão geral da inteligência de falsificação
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender como funciona a compreensão da inteligência de falsificação. Eles podem determinar rapidamente quais remetentes estão enviando emails legitimamente para suas organizações de domínios que não passam por verificações de autenticação de email (SPF, DKIM ou DMARC).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9139a2b4c3c7ed8262f3d75b445defb869371d07
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602087"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>Walkthrough-visão geral da inteligência de falsificação no Microsoft defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Nas organizações Microsoft 365 com o defender para Office 365, você pode usar a compreensão de inteligência de falsificação para determinar rapidamente quais remetentes externos estão enviando legitimamente emails não autenticados (mensagens de domínios que não passam verificações de SPF, DKIM ou DMARC).

Ao permitir que remetentes externos conhecidos enviem mensagens falsificadas de locais conhecidos, você pode reduzir falsos positivos (emails satisfatórios marcados como ruins). Ao monitorar os remetentes falsificados permitidos, você fornece uma camada adicional de segurança para impedir que mensagens não seguras cheguem à sua organização.

Para obter mais informações sobre relatórios e informações, consulte [relatórios e insights no centro de conformidade de & de segurança](reports-and-insights-in-security-and-compliance.md).

Este passo a passo é um dos vários para o centro de conformidade de & de segurança. Para sobre como navegar por relatórios e insights, consulte as orientações na seção [Tópicos relacionados](#related-topics) .

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Você abrir o Centro de conformidade e segurança em <https://protection.office.com/>. Para ir diretamente para a página do **painel de segurança** , use <https://protection.office.com/searchandinvestigation/dashboard> .

  Você pode exibir a percepção de inteligência de falsificação de mais de um painel no centro de conformidade & segurança. Independentemente de qual painel você está vendo, a percepção fornece os mesmos detalhes e permite que você realize rapidamente as mesmas tarefas.

- Você precisa receber permissões no centro de conformidade & de segurança antes de realizar os procedimentos deste artigo:
  - **Organization Management**
  - **Administrador de segurança**
  - **Leitor de segurança**
  - **Leitor global**

  **Observação**: a adição de usuários à função do Azure Active Directory correspondente no centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no centro de conformidade _e_ segurança & para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

- Você habilita e desabilita a inteligência de spoof em políticas anti-phishing no Microsoft defender para Office 365. A inteligência de falsificação é habilitada por padrão. Para obter mais informações, consulte [Configure anti-phishing Policies in Microsoft defender for Office 365](configure-atp-anti-phishing-policies.md).

- Para usar o spoof Intelligence para monitorar e gerenciar remetentes que estão enviando mensagens não autenticadas, consulte [Configure spoof Intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Abrir a percepção de compreensão da falsificação no centro de conformidade & segurança

1. No centro de conformidade & segurança, vá para o painel **Gerenciamento de ameaças** \> **.**

2. Na linha **insights** , procure um dos seguintes itens:

   - **Prováveis domínios falsificados nos últimos sete dias**: essa percepção indica que a inteligência de falsificação está habilitada (habilitada por padrão).
   - **Habilitar proteção contra falsificação**: esta percepção indica que a inteligência de falsificação está desabilitada e clicar na percepção permite que você habilite a inteligência de falsificação.

3. A percepção do painel mostra as informações como esta:

   ![Captura de tela do spoof Intelligence percepção](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Esta percepção tem dois modos:

   - **Modo de percepção**: se a inteligência de falsificação estiver habilitada, a percepção mostrará quantas mensagens foram impactadas por nossos recursos de inteligência de fraude nos últimos sete dias.
   - **E se modo**: se a inteligência de falsificação estiver desabilitada, a percepção mostrará quantas mensagens *teriam* sido impactadas por nossos recursos de inteligência de fraude nos últimos sete dias.

   De qualquer forma, os domínios falsificados exibidos na percepção são separados em duas categorias: **domínios suspeitos** e **domínios não suspeitos**.

   - **Domínios suspeitos** incluem:

     - Falsificação de alta confiança: com base nos padrões de envio históricos e na pontuação de reputação dos domínios, temos certeza de que os domínios estão falsificando, e as mensagens desses domínios provavelmente serão mal-intencionadas.

     - Falsificação de confiança moderada: com base nos padrões de envio históricos e na pontuação de reputação dos domínios, temos certeza de que os domínios estão sendo falsificados e que as mensagens enviadas desses domínios são legítimas. Falsos positivos são mais prováveis nesta categoria do que a falsificação de alta confiança.

   **Domínios não suspeitos**: o domínio falhou nas verificações de autenticação de email explícitas [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC](use-dmarc-to-validate-email.md)). No entanto, o domínio passou por nossas verificações de autenticação de email implícito ([autenticação composta](email-validation-and-authentication.md#composite-authentication)). Como resultado, nenhuma ação anti-falsificação foi tomada na mensagem.

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a>Exibir informações detalhadas sobre domínios suspeitos da compreensão da inteligência de falsificação

1. Na percepção de inteligência de falsificação, clique em **domínios suspeitos** ou **domínios não suspeitos** para ir para a página de **percepção de inteligência de falsificação** . A página de informações **sobre o spoof Intelligence** contém as seguintes informações:

   - **Domínio falsificado**: o domínio do usuário falsificado que é exibido na caixa **de** em clientes de email. Esse endereço também é conhecido como o `5322.From` endereço.
   - **Infraestrutura**: também conhecida como _infraestrutura de envio_. O domínio encontrado em uma pesquisa de DNS inversa (registro PTR) do endereço IP do servidor de email de origem. Se o endereço IP de origem não tiver um registro PTR, a infraestrutura de envio será identificada como \<source IP\> /24 (por exemplo, 192.168.100.100/24).
   - **Contagem de mensagens**: o número de mensagens da infraestrutura de envio para sua organização que contêm o domínio falsificado especificado nos últimos sete dias.
   - **Última vista**: a última data em que uma mensagem foi recebida da infraestrutura de envio que contém o domínio falsificado.
   - **Tipo de spoof**: esse valor é **externo**.
   - **Permitido para falsificar?**: os valores que você vê aqui são:
     - **Sim**: as mensagens da combinação de domínio do usuário falsificado e da infraestrutura de envio são permitidas e não são tratadas como email falsificado.
     - **No**: as mensagens da combinação de domínio do usuário falsificado e da infraestrutura de envio são marcadas como falsificadas. A ação é controlada pela política anti-phishing padrão ou políticas anti-phishing personalizadas (o valor padrão é **mover mensagem para a pasta lixo eletrônico**).

     Para obter mais informações, consulte [Configure anti-phishing Policies in Microsoft defender for Office 365](configure-atp-anti-phishing-policies.md).

2. Selecione um item na lista para exibir detalhes sobre o par de infraestrutura/envio de domínio em um submenu. As informações incluem:
   - Por que detectamos isso.
   - O que você precisa fazer.
   - Um resumo de domínio.
   - Dados de WhoIs sobre o remetente.
   - Mensagens semelhantes que vimos no seu locatário do mesmo remetente.

   Aqui, você também pode optar por adicionar ou remover o par de infraestrutura/envio de domínio da lista de permissões de remetentes **permitidos para falsificar** . Basta definir a opção de alternância.

   ![Captura de tela de um domínio no painel de detalhes do spoof Intelligence Insight](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a>Adicionar um domínio à lista permitir a falsificação

A adição de um domínio à lista de falsificações permitidas da compreensão da inteligência de spoof permite apenas a combinação do domínio falsificado *e* da infraestrutura de envio. Ele não permite o envio de emails do domínio falsificado de qualquer fonte, nem permite o envio de emails da infraestrutura de envio para qualquer domínio.

Por exemplo, você permite que o seguinte domínio seja permitido para a lista de falsificação:

- **Domínio**: gmail.com
- **Infraestrutura**: TMS.MX.com

Somente os emails desse par de infraestrutura/envio de domínio poderão ser falsificados. Outros remetentes tentando falsificar o gmail.com não são permitidos. As mensagens em outros domínios de tms.mx.com são verificadas por inteligência de falsificação.

## <a name="related-topics"></a>Tópicos relacionados

[Proteção contra falsificação no Microsoft 365](anti-spoofing-protection.md)
