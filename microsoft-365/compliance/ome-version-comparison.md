---
title: Comparação de versão de criptografia de mensagens (OME)
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Este artigo ajuda a explicar as diferenças entre diferentes versões da Criptografia de Mensagens do Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5c8b0852220b2144c4ab92ec9b692299c9d2c860
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408564"
---
# <a name="compare-versions-of-ome"></a>Comparar versões de OME

> [!IMPORTANT]
> Em 28 de fevereiro de 2021, a Microsoft preterirá o suporte ao AD RMS no Exchange Online. Se você implantou um ambiente híbrido em que suas caixas de correio do Exchange estão online e está usando o IRM com o ACTIVE Directory RMS no local, será necessário migrar para o Azure. As organizações que implantaram no ambiente Moderado GCC também são afetadas. Consulte "Visão geral da precarização do AD RMS no Exchange Online" neste artigo para obter informações.

O restante deste artigo compara a criptografia de mensagens herdadas do Office 365 (OME) com os novos recursos OME e a Criptografia Avançada de Mensagens do Office 365. Os novos recursos são uma fusão e uma versão mais recente do OME e do GERENCIAMENTO de Direitos de Informação (IRM). Características exclusivas da implantação no GCC High também são descritas. Os dois podem coexistir em sua organização. Para obter informações sobre como os novos recursos funcionam, consulte [Office 365 Message Encryption (OME)](ome.md).

Este artigo faz parte de uma série maior de artigos sobre a Criptografia de Mensagens do Office 365. Este artigo destina-se a administradores e ITPros. Se você estiver apenas procurando informações sobre como enviar ou receber uma mensagem criptografada, consulte a lista de artigos no OME (Criptografia de Mensagens [do Office 365)](ome.md) e localize o artigo que melhor atende às suas necessidades.

## <a name="overview-of-ad-rms-deprecation-in-exchange-online"></a>Visão geral da precarização do AD RMS no Exchange Online

O Exchange Online inclui a funcionalidade de Gerenciamento de Direitos de Informação (IRM) que fornece proteção online e offline de mensagens de email e anexos. Por padrão, o Exchange Online usa a Proteção de Informações do Azure. No entanto, sua organização pode ter configurado o IRM do Exchange Online para usar o Serviço de Gerenciamento de Direitos do Active Directory (AD RMS) local. O suporte ao AD RMS no Exchange Online está se retirando. Em vez disso, a Proteção de Informações do Azure substituirá totalmente o AD RMS.

Para avaliar se essa depreciação afeta sua organização, consulte Como migrar o [AD RMS para o Azure RMS no Exchange Online](https://support.microsoft.com/help/5001237). Este artigo fornece recomendações sobre opções de migração.

## <a name="side-by-side-comparison-of-ome-features-and-capabilities"></a>Comparação lado a lado dos recursos e recursos do OME

|           **Situação**           | **OME Herdado**    | **IRM no AD RMS**        | **Novos recursos OME** |
|-----------------------------------|-------------------|-------------------|--------------------------|
|*Enviando um email criptografado*        |Por meio de regras de fluxo de emails do Exchange|Usuário final iniciado a partir da área de trabalho do Outlook ou do Outlook na Web; ou por meio de regras de fluxo de emails do Exchange|Usuário final iniciado a partir da área de trabalho do Outlook, do Outlook para Mac ou do Outlook na Web; por meio de regras de fluxo de emails do Exchange (também conhecidas como regras de transporte) e Prevenção contra Perda de Dados (DLP)|
|*Modelo de gerenciamento de direitos*       |   N/D      |Opção Não Encaminhar e modelos personalizados|Opção Não Encaminhar, somente criptografia e modelos personalizados|
|*Tipo de destinatário*                   |Destinatários internos e externos|Somente destinatários internos         |Destinatários internos e externos|
|*Experiência para destinatário interno*|Os destinatários recebem uma mensagem HTML, que baixam e abrem em um navegador da Web ou aplicativo móvel|Experiência em linha nativa em clientes do Outlook|Experiência em linha nativa para destinatários na mesma organização usando clientes do Outlook.  Os destinatários podem ler mensagens do portal OME usando clientes que não o Outlook (sem download ou aplicativo necessário).|
|*Experiência para destinatário externo*|Os destinatários recebem uma mensagem HTML, que baixam e abrem em um navegador da Web ou aplicativo móvel|N/D|Experiência em linha nativa para destinatários do Microsoft 365. Todos os outros destinatários podem ler mensagens do portal OME (sem download ou aplicativo necessário).|
|*Permissões de anexo*           |Sem restrições sobre anexos|Os anexos são protegidos|Os anexos são protegidos para a opção Não Encaminhar e modelos personalizados. Os administradores podem escolher se os anexos da opção somente criptografia estão protegidos ou não.|
|*Traga seu próprio suporte de chave (BYOK)*|Nenhum                |Nenhum               |BYOK com suporte          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>Vantagens dos novos recursos OME em relação ao OME herddo

Os novos recursos oferecem as seguintes vantagens:

- Capacidade de usar a opção somente criptografia (que permite a colaboração segura), a opção Não Encaminhar e as restrições personalizadas.
- Os envios podem enviar emails criptografados com os novos recursos manualmente da Área de Trabalho do Outlook, do Outlook para Mac e do Outlook nos clientes Web.
- Os destinatários do Microsoft 365 podem usar uma experiência em linha em clientes do Outlook com suporte. Como alternativa, os administradores podem optar por mostrar aos destinatários do Microsoft 365 uma experiência de identidade visual.
- Contas fora do Microsoft 365, como contas do Gmail, Yahoo e Microsoft, são federadas com o portal OME, que oferece uma melhor experiência de usuário para esses destinatários. Todas as outras identidades usam um código de passagem única para acessar mensagens criptografadas.
- Os administradores podem personalizar a identidade visual e criar vários modelos de identidade visual.
- Os administradores podem revogar emails criptografados com os novos recursos.
- Os novos recursos fornecem relatórios de uso detalhados por meio do Centro &amp; de Conformidade e Segurança.

## <a name="office-365-advanced-message-encryption-capabilities"></a>Recursos avançados de Criptografia de Mensagens do Office 365

A Criptografia Avançada de Mensagens do Office 365 oferece recursos adicionais além dos novos recursos OME. Você deve ter os novos recursos de Criptografia de Mensagens do Office 365 definidos em sua organização para usar os recursos de Criptografia de Mensagens Avançadas. Além disso, para usar esses recursos, os destinatários devem exibir e responder ao email seguro por meio do Portal OME. Os recursos avançados incluem:

- Revogação de mensagens

- Expiração da mensagem

- Vários modelos de identidade visual

A Criptografia Avançada de Mensagens do Office 365 não é suportada no GCC High.

Para obter informações sobre como usar a Criptografia Avançada de Mensagens, consulte Criptografia de Mensagem Avançada do [Office 365.](ome-advanced-message-encryption.md)

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>Características exclusivas da Criptografia de Mensagens do Office 365 em uma implantação GCC High

Se você planeja usar a Criptografia de Mensagens do Office 365 em um ambiente GCC High, há algumas características exclusivas em relação à experiência do destinatário.

### <a name="encrypted-email-between-gcc-high-and-gcc-high-recipients"></a>Email criptografado entre destinatários GCC High e GCC High

Os envios podem criptografar emails manualmente no Outlook para PC e Mac e Outlook na Web, ou as organizações podem configurar uma política para criptografar emails usando regras de fluxo de emails do Exchange.

Os destinatários dentro do GCC High recebem a mesma experiência de leitura em linha no Outlook para PC e Mac e Outlook na Web que todos os outros usuários.

### <a name="encrypted-email-between-gcc-high-and-non-gcc-high-recipients"></a>Email criptografado entre destinatários GCC High e Non-GCC High

Os envios dentro do GCC High podem enviar emails criptografados fora do limite da GCC High e vice-versa.

Todos os destinatários fora do GCC High, incluindo usuários comerciais do Microsoft 365, Outlook.com usuários e outros usuários de outros provedores de email, como Gmail e Yahoo, recebem um email de wrapper. Esse email de wrapper redireciona o destinatário para o Portal OME onde o destinatário pode ler e responder à mensagem. Isso também é verdadeiro para os envios fora do GCC High enviando emails criptografados OME para GCC High.

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>Coexistência do OME herddo e dos novos recursos no mesmo locatário

Você pode usar o OME herddo e os novos recursos no mesmo locatário. Como administrador, você faz isso escolhendo qual versão do OME deseja usar ao criar suas regras de fluxo de emails.

- Para especificar a versão herdada do OME, use a ação de regra de fluxo de emails do Exchange **Aplicar a versão anterior do OME**.

- Para especificar os novos recursos, use a ação de regra de fluxo de emails do Exchange Aplicar a Criptografia de Mensagens do **Office 365 e a** proteção de direitos.

Os usuários podem enviar emails criptografados manualmente com os novos recursos da Área de Trabalho do Outlook, do Outlook para Mac e do Outlook na Web.

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>Migrar do OME herdado para os novos recursos

Embora ambas as versões do OME possam coexistir, é altamente recomendável que você edite suas regras antigas de fluxo de emails que usam a ação de regra Aplique a versão anterior do **OME** para usar os novos recursos. Atualize essas regras para usar a ação de regra de fluxo de emails Aplicar Criptografia de Mensagem do **Office 365 e proteção de direitos.** Para obter instruções, consulte Definir regras de fluxo de emails [para criptografar mensagens de email no Office 365](define-mail-flow-rules-to-encrypt-email.md).

## <a name="get-started-with-ome"></a>Começar com o OME

Normalmente, os novos recursos OME são habilitados automaticamente para sua organização. Para obter mais informações sobre os novos recursos OME em sua organização, consulte Configurar novos recursos de Criptografia de Mensagens do [Office 365.](set-up-new-message-encryption-capabilities.md)

A versão herdada do OME será automaticamente habilitada para sua organização se você habilitar a Proteção de Informações do Azure. No passado, o OME herdado funcionava mesmo se a Proteção de Informações do Azure não estivesse habilitada. Isso não acontece mais.

Para começar a usar o OME herdado, se você habilitar a Proteção de Informações do Azure, configure as regras de fluxo de emails que usam a ação de regra Aplique a versão **anterior do OME**. Para obter instruções, consulte [Definir regras de fluxo de emails para criptografar mensagens de email](define-mail-flow-rules-to-encrypt-email.md).