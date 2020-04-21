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
description: Veja como a compreensão da inteligência de falsificação funciona na proteção avançada contra ameaças do Office 365.
ms.openlocfilehash: 4ad3de8812e09b73018c02232e3e66e4bec9d041
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630924"
---
# <a name="walkthrough---atp-spoof-intelligence-insight-in-microsoft-365"></a>Walkthrough-visão geral da inteligência de fraudes ATP no Microsoft 365

Nas organizações Microsoft 365 com a proteção avançada contra ameaças (ATP), você pode usar a compreensão de inteligência de falsificação para determinar rapidamente quais remetentes estão enviando legitimamente emails não autenticados. Ao permitir que eles enviem mensagens falsificadas, você pode reduzir o risco de qualquer falso positivo para os seus usuários. Você também pode usar a compreensão de inteligência de falsificação para monitorar e gerenciar os pares de domínio permitidos para fornecer uma camada adicional de segurança e impedir que mensagens não seguras cheguem à sua organização.

Se você for novo para [relatórios e insights no centro de conformidade e segurança &](reports-and-insights-in-security-and-compliance.md), poderá ajudar a ver como você pode navegar facilmente de um painel para uma compreensão e ações recomendadas.

Este passo a passo é um dos vários para o centro de conformidade de & de segurança. Para sobre como navegar por relatórios e insights, consulte as orientações na seção Tópicos relacionados.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a página do **painel** de segurança <https://protection.office.com/searchandinvestigation/dashboard>, use.

  Você pode exibir a percepção de inteligência de falsificação de mais de um painel no centro de conformidade & segurança. Independentemente de qual painel você está vendo, a percepção fornece os mesmos detalhes e permite que você realize rapidamente as mesmas tarefas.

- Você precisa receber permissões para executar esses procedimentos. Para usar o spoof Intelligence percepção, você precisa ser membro dos grupos de função de **Gerenciamento da organização**, administrador de **segurança**ou leitor de **segurança** . Para obter mais informações sobre grupos de função no centro de conformidade de & de segurança, consulte [permissões no centro de conformidade de & de segurança](permissions-in-the-security-and-compliance-center.md).

- Você habilita e desabilita a inteligência de spoof em políticas anti-phishing da ATP. Para obter mais informações, consulte [Configure ATP anti-phishing Policies in Microsoft 365](configure-atp-anti-phishing-policies.md).

- Nas organizações do Microsoft 365 com caixas de correio do Exchange Online e em proteção autônoma do Exchange Online (EOP) sem caixas de correio do Exchange Online, você pode usar a inteligência de spoof para monitorar e gerenciar remetentes que está enviando mensagens não autenticadas. Para obter mais informações, consulte [Configure spoof Intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Abrir a percepção de compreensão da falsificação no centro de conformidade & segurança

1. No centro de conformidade & segurança, vá para o painel **Gerenciamento** \> de ameaças **.**

2. Na linha **insights** , procure um dos seguintes itens:

   - O **spoof Intelligence está habilitado**: a percepção é denominada **domínios falsificados que falharam na autenticação dos últimos 30 dias**. É o padrão.

   - A **inteligência de falsificação está desabilitada**: a percepção em chamado **habilitar proteção contra falsificação**e clicar nele permite habilitar a inteligência de falsificação.

3. A percepção do painel mostra as informações como esta:

   ![Captura de tela do spoof Intelligence percepção](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Esta percepção tem dois modos:

   - **Modo de percepção**. Se você tiver uma política de falsificação habilitada, a percepção mostrará quantas mensagens foram impactadas por nossos recursos de inteligência de fraude nos últimos 30 dias.

   - **Se Mode**. Se você não tiver uma política de falsificação habilitada, a percepção mostrará a você quantos emails *teriam* sido afetados por nossos recursos de inteligência de fraude nos últimos 30 dias.

   De qualquer forma, os domínios falsificados exibidos na percepção são separados em duas categorias: **pares de domínios suspeitos** e **pares de domínios não suspeitos**. Essas categorias são subdivididas em três buckets diferentes para revisão.

   Um **par de domínio** é uma combinação do endereço de e da infraestrutura de envio:

   - O endereço de é o endereço de email do remetente que é exibido em clientes de email. Esse endereço identifica o autor do email. Ou seja, a caixa de correio da pessoa ou sistema responsável por escrever a mensagem. Esse endereço também é conhecido como o `5322.From` endereço.

   - A infraestrutura de envio, ou remetente, é o domínio organizacional da pesquisa de DNS inversa (registro PTR) do endereço IP de envio. Se o endereço IP de envio não tiver um registro PTR, o remetente será identificado pelo IP de envio com a máscara de sub-rede 255.255.255.0 em notação CIDR (/24). Por exemplo, se o endereço IP for 192.168.100.100, o endereço IP completo do remetente será 192.168.100.100/24.

   Os **pares de domínios suspeitos** incluem:

   - **Falsificação de alta confiança**: a Microsoft 365 recebeu sinais fortes que esses domínios são suspeitos, com base nos padrões de envio históricos e na pontuação de reputação dos domínios. O Microsoft 365 é altamente seguro de que os domínios estão falsificando e que as mensagens enviadas desses domínios têm menos probabilidade de ser legítimas.

   - **Falsificação de confiança moderada**: a Microsoft 365 recebeu sinais moderados de que esses domínios são suspeitos, com base nos padrões de envio históricos e na pontuação de reputação dos domínios. O Office 365 está razoavelmente seguro de que os domínios estão falsificando e que as mensagens enviadas desses domínios são legítimas. Esse Bucket tem uma chance maior de conter falsos positivos (FPs) do que o Bucket de falsificação de alta confiança.

   - **Pares de domínios não suspeitos** (inclui **falsificação**reposta): a falsificação reposta são domínios que falharam nas verificações de autenticação explícitas [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), [DMARC](use-dmarc-to-validate-email.md)), mas passaram nossas verificações de autenticação de email implícito ([autenticação composta](email-validation-and-authentication.md#composite-authentication)). Como resultado, a Microsoft 365 resmeteu o email em seu nome e nenhuma ação de anti-falsificação foi tomada na mensagem.

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>Exibir informações detalhadas sobre pares de domínio suspeitos da compreensão da inteligência de falsificação

1. Na percepção de inteligência de falsificação, clique em qualquer um dos pares de domínio (alto, moderado ou cogatado).

   A página de **informações sobre spoof Intelligence** aparece mostrando uma lista de remetentes que estão enviando emails não autenticados para sua organização. As informações nesta página ajudam a determinar se as mensagens falsificadas são autorizadas ou se você precisa tomar mais ações. Você pode classificar as informações por contagem de mensagens, a data em que a falsificação foi detectada pela última vez e muito mais. (Clique em cabeçalhos de coluna, como **contagem de mensagens** ou **última vista**, por exemplo).

2. Selecione um item na tabela para abrir um painel de detalhes que contenha informações avançadas sobre o par de domínio, incluindo por que detectamos isso, o que você precisa fazer, um resumo de domínio, dados de WhoIs sobre o remetente e emails semelhantes que vimos no seu locatário do mesmo remetente. A partir daqui, você também pode optar por adicionar ou remover o par de domínio da lista de remetentes confiáveis do **AllowedToSpoof** .

   ![Captura de tela de um domínio no painel de detalhes do spoof Intelligence Insight](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a>Adicionar ou remover um domínio da lista de remetentes confiáveis do AllowedToSpoof

Você adiciona ou remove um domínio da lista de remetentes confiáveis do AllowedToSpoof ao examinar o par de domínios no painel de detalhes da percepção de inteligência de falsificação. Basta definir a opção de alternância.

Isso modifica a combinação exclusiva de par de domínio do domínio falsificado e da infraestrutura de envio e não fornece cobertura para todo o domínio falsificado ou para a infraestrutura de envio isoladamente.

Por exemplo, se você adicionar o seguinte par de domínios à lista de permissões de remetente "AllowedToSpoof": *domínio falsificado* "gmail.com" e de *envio de infraestrutura* "TMS *. MX.com",* somente os emails desse par de domínio poderão ser falsificados. Outros remetentes que tentam falsificar "gmail.com" e outros domínios que "tms.mx.com" tentam falsificar continuarão a ser protegidos por spoof Intelligence.

## <a name="related-topics"></a>Tópicos relacionados

[Proteção contra falsificação no Microsoft 365](anti-spoofing-protection.md)

[Passo a passo – de um painel para um insight](from-a-dashboard-to-an-insight.md)

[Passo a passo – De um relatório detalhado para um insight](from-a-detailed-report-to-an-insight.md)

[Passo a passo – de um insight para um relatório detalhado](from-an-insight-to-a-detailed-report.md)