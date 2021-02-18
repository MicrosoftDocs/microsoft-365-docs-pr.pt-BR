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
description: Os administradores podem saber como funciona o insight de inteligência de Spoof. Eles podem determinar rapidamente quais enviam emails para suas organizações de forma legítima a partir de domínios que não passam em verificações de autenticação de email (SPF, DKIM ou DMARC).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 91cd26498b2a14166f1be10921b9d5b2ea8d583c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287966"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>Passo a passo - Insight de inteligência contra spoof no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Nas organizações do Microsoft 365 com o Defender para Office 365, você pode usar o insight de inteligência de Spoof para determinar rapidamente quais envios externos estão enviando emails não autenticados (mensagens de domínios que não passam em verificações SPF, DKIM ou DMARC).

Ao permitir que os envios externos conhecidos enviem mensagens falsas de locais conhecidos, você pode reduzir falsos positivos (emails válidos marcados como ruins). Ao monitorar os envios de spoofed permitidos, você fornece uma camada adicional de segurança para impedir que mensagens não seguras chegam em sua organização.

Para obter mais informações sobre relatórios e insights, consulte Relatórios e insights no [Centro de Conformidade e & Segurança.](reports-and-insights-in-security-and-compliance.md)

Este passo a passo é um dos vários para o Centro de Conformidade e & Segurança. Para saber mais sobre como navegar por relatórios e ideias, consulte os passo a passo na [seção tópicos relacionados.](#related-topics)

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a página **do painel segurança,** use <https://protection.office.com/searchandinvestigation/dashboard> .

  Você pode exibir o insight de inteligência contra & segurança em mais de um painel. Independentemente de qual painel você está olhando, o insight fornece os mesmos detalhes e permite que você faça rapidamente as mesmas tarefas.

- Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos deste artigo:
  - **Organization Management**
  - **Administrador de Segurança**
  - **Leitor de segurança**
  - **Leitor Global**

  Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

  **Observação:** a adição de usuários à função do Azure Active Directory correspondente no Centro de administração do  Microsoft 365 oferece aos usuários as permissões necessárias no Centro de Conformidade e Segurança & e permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).

- Você habilita e desabilita a inteligência contra spoof em políticas anti-phishing no Microsoft Defender para Office 365. A inteligência contra spoof é habilitada por padrão. Para obter mais informações, [consulte Configurar políticas anti-phishing no Microsoft Defender para Office 365.](configure-atp-anti-phishing-policies.md)

- Para usar a inteligência contra spoof para monitorar e gerenciar os envios de mensagens não autenticadas, confira Configurar a inteligência contra [spoof no Microsoft 365.](learn-about-spoof-intelligence.md)

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Abra o insight de inteligência contra & segurança

1. No Centro de Conformidade & segurança, vá para o **Painel de Gerenciamento de** \> **Ameaças.**

2. Na linha **Insights,** procure um dos seguintes itens:

   - **Domínios provavelmentefalsados** nos últimos sete dias: esse insight indica que a inteligência contra spoof está habilitada (ela é habilitada por padrão).
   - Habilitar a Proteção contra **Spoof:** esse insight indica que a inteligência contra spoof está desabilitada, e clicar no insight permite habilitar a inteligência contra spoof.

3. O insight no painel mostra informações como esta:

   ![Captura de tela do insight de inteligência contra spoof](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Esse insight tem dois modos:

   - **Modo de** informação: se a inteligência contra spoof está habilitada, o insight mostra quantas mensagens foram impactadas por nossos recursos de inteligência contra spoof nos últimos sete dias.
   - **E se o** modo : se a inteligência de spoof for desabilitada, o insight mostrará quantas mensagens teriam sido impactadas por nossos recursos de inteligência contra spoof nos últimos sete dias. 

   De qualquer forma, os domínios spoofed exibidos no insight são separados em duas **categorias: domínios** suspeitos e **domínios não suspeitos.**

   - **Domínios suspeitos** incluem:

     - Spoof de alta confiança: com base nos padrões de envio históricos e na pontuação de reputação dos domínios, temos certeza de que os domínios são falsas e as mensagens desses domínios são mais prováveis de serem mal-intencionadas.

     - Spoof de confiança moderada: com base nos padrões de envio históricos e na pontuação de reputação dos domínios, estamos moderadamente confiantes de que os domínios são falsas e que as mensagens enviadas desses domínios são legítimas. Os falsos positivos são mais prováveis nessa categoria do que a falsa de alta confiança.

   **Domínios não suspeitos:** O domínio falhou nas verificações explícitas de autenticação de email [SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC](use-dmarc-to-validate-email.md)). No entanto, o domínio passou em nossas verificações implícitas de autenticação de email[(autenticação composta).](email-validation-and-authentication.md#composite-authentication) Como resultado, nenhuma ação anti-spoofing foi tomada na mensagem.

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a>Exibir informações detalhadas sobre domínios suspeitos no insight de inteligência de spoof

1. No insight de inteligência de spoof, clique em **Domínios** suspeitos ou **domínios** não suspeitos para ir para a página de informações de **inteligência de spoof.** A **página de informações do Spoof Intelligence** contém as seguintes informações:

   - **Domínio spoofed**: o domínio do usuário spoofed que é exibido na caixa **De** em clientes de email. Esse endereço também é conhecido como `5322.From` endereço.
   - **Infraestrutura:** também conhecida como infraestrutura _de envio._ O domínio encontrado em um registro PTR (de dns reverso) do endereço IP do servidor de email de origem. Se o endereço IP de origem não tiver nenhum registro PTR, a infraestrutura de envio será identificada como \<source IP\> /24 (por exemplo, 192.168.100.100/24).
   - **Contagem de** mensagens: o número de mensagens da infraestrutura de envio para sua organização que contêm o domínio de spoofed especificado nos últimos 7 dias.
   - **Visto pela última** vez: a última data em que uma mensagem foi recebida da infraestrutura de envio que contém o domínio spoofed.
   - **Tipo de spoof:** este valor é **Externo**.
   - **Permissão para fazer spoof?**: Os valores que você vê aqui são:
     - **Sim:** as mensagens da combinação do domínio do usuário falsa e da infraestrutura de envio são permitidas e não tratadas como emails falsas.
     - **Não:** as mensagens da combinação do domínio do usuário falsa e da infraestrutura de envio são marcadas como falsas. A ação é controlada pela política anti-phishing padrão ou pelas políticas anti-phishing personalizadas (o valor padrão é Mover mensagem para a pasta **Lixo Eletrônico).**

     Para obter mais informações, [consulte Configurar políticas anti-phishing no Microsoft Defender para Office 365.](configure-atp-anti-phishing-policies.md)

2. Selecione um item na lista para exibir detalhes sobre o par de infraestrutura de domínio/envio em um flyout. As informações incluem:
   - Por que nós vimos isso.
   - O que você precisa fazer.
   - Um resumo de domínio.
   - Dados whoIs sobre o remetente.
   - Mensagens semelhantes que vimos no seu locatário do mesmo remetente.

   A partir daqui, você também pode optar por adicionar ou remover o par de infraestrutura de domínio/envio da lista de permissão de remetentes permitidos para **spoof.** Basta definir a alternância de acordo.

   ![Screenshot of a domain in the Spoof intelligence insight details pane](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a>Adding a domain to the Allowed to spoof list

Adicionar um domínio à lista De permissão para spoof do insight de inteligência de spoof só permite a combinação do domínio spoofed e da *infraestrutura* de envio. Ele não permite emails do domínio spoofed de qualquer fonte, nem permite emails da infraestrutura de envio para qualquer domínio.

Por exemplo, você permite que o seguinte domínio para a lista de permissão para spoof:

- **Domínio**: gmail.com
- **Infraestrutura:** tms.mx.com

Somente emails desse par de infraestrutura de envio/domínio terão permissão para fazer spoof. Não são permitidos outros gmail.com que tentarem gmail.com spoof. As mensagens em outros domínios tms.mx.com são verificadas por inteligência contra spoof.

## <a name="related-topics"></a>Tópicos relacionados

[Proteção anti-spoofing no Microsoft 365](anti-spoofing-protection.md)
