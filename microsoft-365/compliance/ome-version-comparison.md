---
title: Comparação de versões de criptografia de mensagens (OME)
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
description: Este artigo ajuda a explicar as diferenças entre diferentes versões da criptografia de mensagem do Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a52d0c0164dfddb9f678bffa088760a271bc28e3
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754125"
---
# <a name="compare-versions-of-ome"></a>Comparar versões de OME

Este artigo compara a criptografia de mensagens do Office 365 (OME) herdada para os novos recursos do OME e a criptografia de mensagem avançada do Office 365. Os novos recursos são uma fusão e uma versão mais recente do OME e do gerenciamento de direitos de informação (IRM). As características exclusivas de implantação no GCC alto também são descritas. Os dois podem coexistir em sua organização. Para obter informações sobre como os novos recursos funcionam, consulte [Office 365 Message Encryption (ome)](ome.md).

||
|:-----|
|Este artigo faz parte de uma série maior de artigos sobre a criptografia de mensagens do Office 365. Este artigo destina-se a administradores e ITPros. Se você estiver apenas procurando informações sobre como enviar ou receber uma mensagem criptografada, consulte a lista de artigos na [ome (criptografia de mensagens do Office 365)](ome.md) e localize o artigo que melhor atende às suas necessidades. |
||

## <a name="side-by-side-comparison-of-features-and-capabilities"></a>Comparação de recursos e recursos lado a lado

|                                   |Recursos antigos       |                   |Novos recursos              |
|-----------------------------------|-------------------|-------------------|--------------------------|
|**Funcionalidade**                     | **OME Herdado**    | **IRM**           | **Novos recursos do OME** |
|*Enviar um email criptografado*        |Por meio de regras de fluxo de email do Exchange|O usuário final iniciou a partir do Outlook na Web ou do Outlook na Web; ou por meio de regras de fluxo de email do Exchange|Usuário final iniciado a partir da área de trabalho do Outlook, Outlook para Mac ou Outlook na Web; por meio de regras de fluxo de email do Exchange (também conhecidas como regras de transporte) e prevenção de perda de dados (DLP)|
|*Modelo de gerenciamento de direitos*       |   N/D      |Opção não encaminhar e modelos personalizados|Opção não encaminhar, Encrypt-Only e modelos personalizados|
|*Tipo de destinatário*                   |Destinatários internos e externos|Somente destinatários internos         |Destinatários internos e externos|
|*Experiência para o destinatário interno*|Os destinatários recebem uma mensagem HTML, que eles baixam e abrem em um navegador da Web ou aplicativo móvel|Experiência interna nativa em clientes do Outlook|Experiência nativa em linha para destinatários na mesma organização usando clientes do Outlook.  Os destinatários podem ler a mensagem do portal OME usando clientes que não o Outlook (sem download ou aplicativo necessário).|
|*Experiência para destinatário externo*|Os destinatários recebem uma mensagem HTML, que eles baixam e abrem em um navegador da Web ou aplicativo móvel|N/D|Experiência interna nativa para destinatários do Microsoft 365. Todos os outros destinatários podem ler a mensagem do portal do OME (sem download ou aplicativo necessário).|
|*Permissões de anexo*           |Sem restrições em anexos|Os anexos estão protegidos|Os anexos são protegidos para a opção não encaminhar e modelos personalizados. Os administradores podem escolher se os anexos da opção Encrypt-Only estão protegidos ou não.|
|*Dê suporte a sua própria chave (BYOK)*|Nenhum                |Nenhum               |BYOK com suporte          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>Vantagens dos novos recursos do OME sobre o OME herdado

Os novos recursos oferecem as seguintes vantagens:

- Capacidade de usar Encrypt-Only (que permite colaboração segura), não encaminhar e restrições personalizadas.
- Os remetentes podem enviar emails criptografados com os novos recursos manualmente da área de trabalho do Outlook, do Outlook para Mac e do Outlook nos clientes Web.
- Os destinatários 365 da Microsoft utilizam uma experiência embutida em clientes do Outlook com suporte. Como alternativa, os administradores podem optar por mostrar a Microsoft 365 Recipients uma experiência com marca.
- As contas fora do Microsoft 365, como Gmail, Yahoo e contas da Microsoft, são federadas com o portal do OME, que oferece uma experiência de usuário melhor para esses destinatários. Todas as outras identidades usam um código de passagem única para acessar mensagens criptografadas.
- Os administradores podem personalizar a identidade visual e criar vários modelos de identidade visual.
- Os administradores podem revogar emails criptografados com os novos recursos.
- Os novos recursos fornecem relatórios de uso detalhados por meio do centro de conformidade de segurança &amp; .

## <a name="office-365-advanced-message-encryption-capabilities"></a>Recursos de criptografia avançada de mensagens do Office 365

Office 365 Advanced Message Encryption oferece recursos adicionais sobre os novos recursos do OME. Você deve ter os novos recursos de criptografia de mensagem do Office 365 configurados em sua organização para usar os recursos avançados de criptografia de mensagens. Além disso, para usar esses recursos, os destinatários devem exibir e responder a mensagens seguras através do portal do OME. Os recursos avançados incluem:

- Revogação de mensagem

- Expiração de mensagem

- Vários modelos de identidade visual

O Office 365 Advanced Message Encryption não é suportado no GCC High.

Para obter informações sobre como usar a criptografia de mensagem avançada, consulte [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md).

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>Características exclusivas da criptografia de mensagem do Office 365 em uma implantação avançada GCC

Se você planeja usar a criptografia de mensagem do Office 365 em um ambiente de maior GCC, há algumas características exclusivas sobre a experiência do destinatário.

### <a name="encrypted-email-between-gcc-high-and-gcc-high-recipients"></a>Email criptografado entre os destinatários de GCC alta e GCC alto

Os remetentes podem criptografar manualmente emails no Outlook para PC e Mac e Outlook na Web, ou as organizações podem configurar uma política para criptografar emails usando regras de fluxo de email do Exchange.

Os destinatários dentro do GCC têm alta recepção da mesma experiência de leitura embutida no Outlook para PC e Mac e Outlook na Web como todos os outros usuários.

### <a name="encrypted-email-between-gcc-high-and-non-gcc-high-recipients"></a>Email criptografado entre destinatários de GCC elevado e não GCC alto

Os remetentes com GCC alta podem enviar emails criptografados fora do maior limite e vice-versa.

Todos os destinatários fora do GCC, incluindo os usuários do Microsoft 365 comercial, os usuários do Outlook.com e outros usuários de outros provedores de email, como o Gmail e o Yahoo, recebem um email de conteúdo adicional. Este email de invólucro redireciona o destinatário para o portal do OME, onde o destinatário pode ler e responder à mensagem. Isso também se aplica aos remetentes fora do GCC de envio de emails do OME para o GCC alto.

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>A coexistência de OME herdados e os novos recursos no mesmo locatário

Você pode usar o OME herdado e os novos recursos no mesmo locatário. Como administrador, você faz isso escolhendo qual versão do OME você deseja usar ao criar suas regras de fluxo de emails.

- Para especificar a versão herdada do OME, use a ação regra de fluxo de email do Exchange **aplicar a versão anterior do ome**.

- Para especificar os novos recursos, use a ação de regra de fluxo de email do Exchange **aplica a criptografia de mensagem do Office 365 e a proteção de direitos**.

Os usuários podem enviar emails manualmente, que são criptografados com os novos recursos da área de trabalho do Outlook, do Outlook para Mac e do Outlook na Web.

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>Migrar do OME herdado para os novos recursos

Embora ambas as versões do OME possam coexistir, é altamente recomendável que você edite suas regras de fluxo de email antigas que usam a ação de regra **aplique a versão anterior do ome** para usar os novos recursos. Atualizar essas regras para usar a ação de regra de fluxo de emails **aplique a criptografia de mensagens e a proteção de direitos do Office 365**. Para obter instruções, consulte [definir regras de fluxo de emails para criptografar mensagens de email no Office 365](define-mail-flow-rules-to-encrypt-email.md).

## <a name="get-started-with-ome"></a>Introdução ao OME

Normalmente, os novos recursos do OME são automaticamente habilitados para sua organização. Para obter mais informações sobre os novos recursos do OME em sua organização, consulte [configurar novos recursos de criptografia de mensagens do Office 365](set-up-new-message-encryption-capabilities.md).

A versão herdada do OME é automaticamente habilitada para sua organização se você tiver habilitado a proteção de informações do Azure. No passado, o OME herdado funcionou, mesmo se a proteção de informações do Azure não estivesse habilitada. Isso não acontece mais.

Para começar a usar o OME herdado, se você tiver habilitado a proteção de informações do Azure, configure as regras de fluxo de email que usam a ação de regra **aplique a versão anterior do ome**. Para obter instruções, consulte [definir regras de fluxo de emails para criptografar mensagens de email](define-mail-flow-rules-to-encrypt-email.md).
