---
title: Comparação de versão da Criptografia de Mensagens (OME)
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
description: Este artigo ajuda a explicar as diferenças entre as diferentes versões da Criptografia de Mensagens do Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 30344a9cbe8629804f5026fc809577923965b7bc
ms.sourcegitcommit: b3bb5bf5efa197ef8b16a33401b0b4f5663d3aa0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/28/2021
ms.locfileid: "50032618"
---
# <a name="compare-versions-of-ome"></a>Comparar versões de OME

> [!IMPORTANT]
> Em 28 de fevereiro de 2021, a Microsoft preterirá o suporte ao AD RMS no Exchange Online. Se você implantou um ambiente híbrido em que suas caixas de correio do Exchange estão online e está usando o IRM com o Active Directory RMS no local, será necessário migrar para o Azure. As organizações que implantaram no ambiente moderado GCC também são afetadas. Consulte "Visão geral da preteração do AD RMS no Exchange Online" neste artigo para obter informações.

O restante deste artigo compara a criptografia de mensagens herdadas do Office 365 (OME) com os novos recursos do OME e a Criptografia Avançada de Mensagens do Office 365. Os novos recursos são uma fusão e uma versão mais recente do OME e do Gerenciamento de Direitos de Informação (IRM). Características exclusivas da implantação no GCC High também são descritas. Os dois podem coexistir em sua organização. Para obter informações sobre como os novos recursos funcionam, consulte Criptografia de Mensagens [do Office 365 (OME).](ome.md)

Este artigo faz parte de uma série maior de artigos sobre a Criptografia de Mensagens do Office 365. Este artigo destina-se a administradores e itpros. Se você estiver apenas procurando informações sobre como enviar ou receber uma mensagem criptografada, confira a lista de artigos no OME (Criptografia de Mensagens [do Office 365)](ome.md) e localize o artigo que melhor se ajusta às suas necessidades.

## <a name="overview-of-ad-rms-deprecation-in-exchange-online"></a>Visão geral da preteração do AD RMS no Exchange Online

O Exchange Online inclui a funcionalidade gerenciamento de direitos de informação (IRM) que fornece proteção online e offline de mensagens de email e anexos. Por padrão, o Exchange Online usa a Proteção de Informações do Azure. No entanto, sua organização pode ter configurado o IRM do Exchange Online para usar o Active Directory Rights Management Service (AD RMS) local. O suporte ao AD RMS no Exchange Online está se retirando. Em vez disso, a Proteção de Informações do Azure substituirá totalmente o AD RMS.

Antes de começar, revise e avalie o impacto para sua organização. Se sua organização já estiver usando a Proteção de Informações do Azure para criptografar emails no Exchange Online, não há nada a fazer. Se você criptografar seu email usando regras de fluxo de emails do Exchange, por exemplo, usando a Criptografia de Mensagens do Office 365, não será preciso alterar seu email seguro. Caso contrário, você precisará se preparar para a preteridação do AD RMS alternando para a Proteção de Informações do Azure.

### <a name="prepare-for-ad-rms-deprecation"></a>Preparar-se para a preteração do AD RMS

Se você já tiver definido a Proteção de Informações do Azure, mas não a estiver usando, habilita o serviço usando o PowerShell do Exchange Online. No computador local, usando uma conta de trabalho ou de estudante que tenha permissões de administrador global em sua organização, conecte-se ao [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) do Exchange Online em uma janela do Windows PowerShell.

Para habilitar a Proteção de Informações do Azure, use o cmdlet Set-IrmConfiguration digitando o comando a seguir.

```powershell
Set-IrmConfiguration -AzureRMSLicensingEnabled $true
```

Se sua organização ainda não tiver definido a Proteção de Informações do Azure, você precisará migrar do AD RMS para a Proteção de Informações do Azure. Para obter instruções, confira [Migrar do AD RMS para a Proteção de Informações do Azure.](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms)

## <a name="side-by-side-comparison-of-features-and-capabilities"></a>Comparação lado a lado de recursos e recursos

|           **Situação**           | **OME Herdado**    | **IRM no AD RMS**        | **Novos recursos do OME** |
|-----------------------------------|-------------------|-------------------|--------------------------|
|*Enviar um email criptografado*        |Por meio de regras de fluxo de emails do Exchange|Usuário final iniciado a partir da área de trabalho do Outlook ou do Outlook na Web; ou por meio de regras de fluxo de emails do Exchange|Usuário final iniciado do Outlook para área de trabalho, Outlook para Mac ou Outlook na Web; por meio de regras de fluxo de emails do Exchange (também conhecidas como regras de transporte) e Prevenção contra Perda de Dados (DLP)|
|*Modelo de gerenciamento de direitos*       |   N/D      |Opção Não Encaminhar e modelos personalizados|Opção Não Encaminhar, Encrypt-Only e modelos personalizados|
|*Tipo de destinatário*                   |Destinatários internos e externos|Somente destinatários internos         |Destinatários internos e externos|
|*Experiência para destinatário interno*|Os destinatários recebem uma mensagem HTML, que eles baixam e abrem em um navegador da Web ou aplicativo móvel|Experiência em linha nativa em clientes do Outlook|Experiência em linha nativa para destinatários na mesma organização que usam clientes do Outlook.  Os destinatários podem ler mensagens do portal do OME usando clientes que não o Outlook (sem download ou aplicativo necessário).|
|*Experiência para destinatário externo*|Os destinatários recebem uma mensagem HTML, que eles baixam e abrem em um navegador da Web ou aplicativo móvel|N/D|Experiência em linha nativa para destinatários do Microsoft 365. Todos os outros destinatários podem ler a mensagem do portal do OME (sem download ou aplicativo necessário).|
|*Permissões de anexo*           |Sem restrições sobre anexos|Anexos são protegidos|Os anexos são protegidos para a opção Não Encaminhar e modelos personalizados. Os administradores podem escolher se os anexos da Encrypt-Only estão protegidos ou não.|
|*Suporte byOK (traga sua própria chave)*|Nenhum                |Nenhum               |BYOK com suporte          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>Vantagens dos novos recursos do OME em relação ao OME herddo

Os novos recursos oferecem as seguintes vantagens:

- Capacidade de usar Encrypt-Only (que permite a colaboração segura), Não Encaminhar e restrições personalizadas.
- Os envios podem enviar emails criptografados com os novos recursos manualmente a partir da Área de Trabalho do Outlook, do Outlook para Mac e dos clientes do Outlook na Web.
- Os destinatários do Microsoft 365 podem usar uma experiência em linha nos clientes do Outlook com suporte. Como alternativa, os administradores podem optar por mostrar aos destinatários do Microsoft 365 uma experiência de identidade visual.
- Contas fora do Microsoft 365, como contas do Gmail, Yahoo e Microsoft, são federadas com o portal OME, que oferece uma melhor experiência de usuário para esses destinatários. Todas as outras identidades usam um código de acesso único para acessar mensagens criptografadas.
- Os administradores podem personalizar a identidade visual e criar vários modelos de identidade visual.
- Os administradores podem revogar emails criptografados com os novos recursos.
- Os novos recursos fornecem relatórios de uso detalhados por meio do Centro de &amp; Conformidade de Segurança.

## <a name="office-365-advanced-message-encryption-capabilities"></a>Recursos avançados de Criptografia de Mensagens do Office 365

A Criptografia Avançada de Mensagens do Office 365 oferece recursos adicionais sobre os novos recursos do OME. Você deve ter os novos recursos de Criptografia de Mensagem do Office 365 definidos em sua organização para usar os recursos de Criptografia avançada de mensagens. Além disso, para usar esses recursos, os destinatários devem exibir e responder a emails seguros por meio do Portal do OME. Os recursos avançados incluem:

- Revogação de mensagem

- Expiração de mensagem

- Vários modelos de identidade visual

A Criptografia Avançada de Mensagens do Office 365 não é suportada na GCC High.

Para obter informações sobre como usar a Criptografia Avançada de Mensagens, consulte Criptografia de Mensagem Avançada [do Office 365.](ome-advanced-message-encryption.md)

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>Características exclusivas da Criptografia de Mensagens do Office 365 em uma implantação GCC High

Se você planeja usar a Criptografia de Mensagens do Office 365 em um ambiente GCC High, há algumas características exclusivas em relação à experiência do destinatário.

### <a name="encrypted-email-between-gcc-high-and-gcc-high-recipients"></a>Email criptografado entre destinatários GCC High e GCC High

Os envios podem criptografar emails manualmente no Outlook para PC e Mac e no Outlook na Web, ou as organizações podem configurar uma política para criptografar emails usando regras de fluxo de emails do Exchange.

Os destinatários dentro da GCC High recebem a mesma experiência de leitura em linha no Outlook para PC e Mac e no Outlook na Web como todos os outros usuários.

### <a name="encrypted-email-between-gcc-high-and-non-gcc-high-recipients"></a>Email criptografado entre destinatários GCC Alto e Não-GCC Alto

Os envios dentro da GCC High podem enviar emails criptografados fora do limite do GCC High e vice-versa.

Todos os destinatários fora do GCC High, incluindo usuários comerciais do Microsoft 365, Outlook.com usuários do Outlook.com e outros usuários de outros provedores de email, como Gmail e Yahoo, recebem um email de wrapper. Esse wrapper mail redireciona o destinatário para o Portal OME onde o destinatário pode ler e responder à mensagem. Isso também é verdadeiro para os envios fora da GCC High enviando emails criptografados OME para GCC High.

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>Coexistência do OME herddo e os novos recursos no mesmo locatário

Você pode usar o OME herddo e os novos recursos no mesmo locatário. Como administrador, você faz isso escolhendo qual versão do OME deseja usar ao criar suas regras de fluxo de emails.

- Para especificar a versão herdada do OME, use a ação de regra de fluxo de emails do Exchange **Aplicar a versão anterior do OME.**

- Para especificar os novos recursos, use a ação de regra de fluxo de emails do Exchange Aplicar Criptografia de Mensagem do **Office 365** e proteção por direitos.

Os usuários podem enviar manualmente emails criptografados com os novos recursos da Área de Trabalho do Outlook, do Outlook para Mac e do Outlook na Web.

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>Migrar do OME herdado para os novos recursos

Embora ambas as versões do OME possam coexistir, é altamente recomendável que você edite suas regras de fluxo de emails antigas que usam a ação de regra Aplique a versão anterior do **OME** para usar os novos recursos. Atualize essas regras para usar a ação de regra de fluxo de emails Aplicar Criptografia de Mensagem do **Office 365 e proteção de direitos.** Para obter instruções, confira [Definir regras de fluxo de emails para criptografar mensagens de email no Office 365.](define-mail-flow-rules-to-encrypt-email.md)

## <a name="get-started-with-ome"></a>Começar a trabalhar com OME

Normalmente, os novos recursos do OME são habilitados automaticamente para sua organização. Para obter mais informações sobre os novos recursos do OME em sua organização, consulte Configurar novos recursos de Criptografia de Mensagem do [Office 365.](set-up-new-message-encryption-capabilities.md)

A versão herdada do OME será habilitada automaticamente para sua organização se você tiver habilitado a Proteção de Informações do Azure. No passado, o OME herdado funcionava mesmo se a Proteção de Informações do Azure não estivesse habilitada. Isso não acontece mais.

Para começar a usar o OME herdado, se você tiver habilitado a Proteção de Informações do Azure, configure regras de fluxo de emails que usam a ação de regra Aplique a versão **anterior do OME.** Para obter instruções, consulte [Definir regras de fluxo de emails para criptografar mensagens de email.](define-mail-flow-rules-to-encrypt-email.md)
