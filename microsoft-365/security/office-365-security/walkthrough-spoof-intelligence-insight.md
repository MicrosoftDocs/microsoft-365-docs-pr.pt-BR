---
title: Passo a passo – Informações sobre Inteligência contra Falsificação
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
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender como funciona o insight de inteligência Spoof. Eles podem determinar rapidamente quais enviadores estão enviando emails legítimos para suas organizações de domínios que não passam verificações de autenticação de email (SPF, DKIM ou DMARC).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cc53d49401afe3a0d7871bf5f294126315aacfec
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908089"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>Passo a passo - Visão de inteligência de spoof no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Nas organizações do Microsoft 365 com o Defender para Office 365, você pode usar o insight de inteligência Spoof para determinar rapidamente quais envios externos estão enviando emails não autenticados (mensagens de domínios que não passam verificações SPF, DKIM ou DMARC).

Ao permitir que os envios externos conhecidos enviem mensagens falsas de locais conhecidos, você pode reduzir falsos positivos (bons emails marcados como ruins). Monitorando os envios permitidos, você fornece uma camada adicional de segurança para impedir que mensagens não seguras chegam à sua organização.

Para obter mais informações sobre relatórios e insights, consulte Relatórios e insights no Centro de Conformidade & [Segurança.](reports-and-insights-in-security-and-compliance.md)

Este passo a passo é um dos vários para o Centro de Conformidade & Segurança. Para saber mais sobre como navegar relatórios e insights, consulte os passo a passo na seção [Tópicos relacionados.](#related-topics)

> [!NOTE]
> O insight de inteligência de spoof mostra dados dos últimos 7 dias. A política de inteligência de [spoof](learn-about-spoof-intelligence.md) e o cmdlet [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy) correspondente no PowerShell do Exchange Online mostram dados dos últimos 30 dias. O [Get-SpoofMailReport](/powershell/module/exchange/get-spoofmailreport) mostra dados por até 90 dias.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a página **Painel de segurança,** use <https://protection.office.com/searchandinvestigation/dashboard> .

  Você pode exibir a visão de inteligência Spoof de mais de um painel no Centro de Conformidade & Segurança. Independentemente de qual painel você esteja olhando, o insight fornece os mesmos detalhes e permite que você faça rapidamente as mesmas tarefas.

- Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos deste artigo:
  - **Organization Management**
  - **Administrador de Segurança**
  - **Leitor de Segurança**
  - **Leitor Global**

  Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

  **Observação**: a adição de usuários à função correspondente do Azure Active Directory no Centro de administração do  Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Conformidade & Segurança e permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).

- Você habilita e desabilita a inteligência de spoof em políticas anti-phishing no Microsoft Defender para Office 365. A inteligência de spoof está habilitada por padrão. Para obter mais informações, consulte [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

- Para usar a inteligência falsa para monitorar e gerenciar os envios que estão enviando mensagens não autenticadas, consulte [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Abra o insight de inteligência de spoof no Centro de Conformidade & Segurança

1. No Centro de Conformidade & segurança, vá para **Painel de Gerenciamento de** \> **Ameaças.**

2. Na linha **Insights,** procure um dos seguintes itens:

   - **Domínios provavelmente desfalsados** nos últimos sete dias : Essa visão indica que a inteligência de spoof está habilitada (ela está habilitada por padrão).
   - **Habilitar** a Proteção contra Spoof : essa visão indica que a inteligência de spoof está desabilitada e clicar no insight permite que você habilita a inteligência de spoof.

3. O insight no painel mostra informações como esta:

   ![Captura de tela do insight de inteligência de spoof](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Esse insight tem dois modos:

   - **Modo de** visão : se a inteligência falsa estiver habilitada, a visão mostra quantas mensagens foram impactadas por nossos recursos de inteligência falsa nos últimos sete dias.
   - **E se o modo**: se a inteligência falsa estiver  desabilitada, a visão mostra quantas mensagens teriam sido impactadas por nossos recursos de inteligência falsas nos últimos sete dias.

   De qualquer forma, os domínios despojados exibidos no insight são separados em duas **categorias: domínios** suspeitos e domínios não **suspeitos.**

   - **Domínios suspeitos** incluem:

     - Spoof de alta confiança: com base nos padrões de envio históricos e na pontuação de reputação dos domínios, estamos altamente confiantes de que os domínios são falsas, e as mensagens desses domínios são mais propensas a serem mal-intencionadas.

     - Spoof de confiança moderada: com base nos padrões de envio históricos e na pontuação de reputação dos domínios, estamos moderadamente confiantes de que os domínios são falsas e que as mensagens enviadas desses domínios são legítimas. Falsos positivos são mais prováveis nessa categoria do que falsos falsos.

   **Domínios não suspeitos**: O domínio com falha na autenticação de email explícito verifica [SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC](use-dmarc-to-validate-email.md)). No entanto, o domínio passou nossas verificações implícitas de autenticação de email ([autenticação composta](email-validation-and-authentication.md#composite-authentication)). Como resultado, nenhuma ação anti-spoofing foi tomada na mensagem.

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a>Exibir informações detalhadas sobre domínios suspeitos do insight de inteligência de Spoof

1. No insight de inteligência de spoof, clique em **Domínios** suspeitos ou **domínios** não suspeitos para ir para a página de informações de **inteligência de Spoof.** A página de informações **do Spoof Intelligence** contém as seguintes informações:

   - **Domínio spoofed**: O domínio do usuário que é exibido na caixa **De** em clientes de email. Esse endereço também é conhecido como `5322.From` endereço.
   - **Infraestrutura**: Também conhecida como infraestrutura _de envio._ O domínio encontrado em um registro DNS reverso (registro PTR) do endereço IP do servidor de email de origem. Se o endereço IP de origem não tiver registro PTR, a infraestrutura de envio será identificada como \<source IP\> /24 (por exemplo, 192.168.100.100/24).
   - **Contagem de** mensagens : o número de mensagens da infraestrutura de envio para sua organização que contêm o domínio empoeirado especificado nos últimos 7 dias.
   - **Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed domain.
   - **Tipo de spoof**: esse valor é **Externo**.
   - **Permitido a spoof?**: Os valores que você vê aqui são:
     - **Sim**: As mensagens da combinação do domínio do usuário falsa e da infraestrutura de envio são permitidas e não tratadas como emails falsas.
     - **Não**: As mensagens da combinação do domínio do usuário falsa e da infraestrutura de envio são marcadas como falsas. A ação é controlada pela política anti-phishing padrão ou políticas anti-phishing personalizadas (o valor padrão é Mover mensagem para a pasta **Lixo Eletrônico**).

     Para obter mais informações, consulte [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

2. Selecione um item na lista para exibir detalhes sobre o par de infraestrutura de envio/domínio em um sobremenu. As informações incluem:
   - Por que pegamos isso.
   - O que você precisa fazer.
   - Um resumo de domínio.
   - WhoIs dados sobre o remetente.
   - Mensagens semelhantes que vimos em seu locatário do mesmo remetente.

   A partir daqui, você também pode optar por adicionar ou remover o par de infraestrutura de envio/domínio da lista de permissão Permitido para **spoof** remetente. Basta definir a alternância de acordo.

   ![Captura de tela de um domínio no painel de detalhes de informações de inteligência de Spoof](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a>Adicionar um domínio à lista Permitido para spoof

A adição de um domínio à lista Permitido para despocar a partir do  insight de inteligência de spoof permite apenas a combinação do domínio e da infraestrutura de envio. Ele não permite emails do domínio spoofed de qualquer origem, nem permite emails da infraestrutura de envio para qualquer domínio.

Por exemplo, você permite que o domínio a seguir para a lista Permitido para spoof:

- **Domínio**: gmail.com
- **Infraestrutura**: tms.mx.com

Somente emails desse par de infraestrutura de envio/domínio terão permissão para fazer a spoof. Outros senders que tentam gmail.com não são permitidos. As mensagens em outros domínios tms.mx.com são verificadas por inteligência falsa.

## <a name="related-topics"></a>Tópicos relacionados

[Proteção anti-spoofing no Microsoft 365](anti-spoofing-protection.md)