---
title: Configurar a política de filtro de conexão padrão
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a configurar a filtragem de conexão no Exchange Online Protection (EOP) para permitir ou bloquear emails de servidores de email.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c6ec8b4adcdda692ee561f7d50bacf0511642269
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290040"
---
# <a name="configure-connection-filtering"></a>Configurar a filtragem de conexão

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)


Se você for um cliente do Microsoft 365 com caixas de correio no Exchange Online ou um cliente autônomo do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, use a filtragem de conexão no EOP (especificamente, a política de filtro de conexão padrão) para identificar servidores de email de origem boas ou ruins por seus endereços IP. Os principais componentes da política de filtro de conexão padrão são:

- **Lista de I Ip Allow:** Ignorar a filtragem de spam para todas as mensagens de entrada dos servidores de email de origem que você especificar por endereço IP ou intervalo de endereços IP. Para cenários em que a filtragem de spam ainda pode ocorrer em mensagens dessas fontes, consulte a seção [Cenários](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) em que as mensagens de fontes na Lista de IIs Permitem IP ainda são filtradas posteriormente neste artigo. Para obter mais informações sobre como a Lista de IPIs deve se ajustar à sua estratégia geral de remetentes seguros, consulte Criar listas de remetentes [seguros no EOP.](create-safe-sender-lists-in-office-365.md)

- **Lista de IIs Bloqueados:** Bloquear todas as mensagens de entrada dos servidores de email de origem especificados por endereço IP ou intervalo de endereços IP. As mensagens de entrada são rejeitadas, não são marcadas como spam e nenhuma filtragem adicional ocorre. Para obter mais informações sobre como a Lista de Bloqueios de IP deve se ajustar à sua estratégia geral de remetentes bloqueados, consulte Criar listas de remetentes bloqueados [no EOP.](create-block-sender-lists-in-office-365.md)

- **Lista segura:** a *lista segura é* uma lista dinâmica de autorizações no datacenter da Microsoft que não requer configuração do cliente. A Microsoft identifica essas fontes de email confiáveis de assinaturas para várias listas de terceiros. Você habilita ou desabilita o uso da lista de segurança; você não pode configurar os servidores de email de origem na lista de segurança. A filtragem de spam é ignorada nas mensagens de entrada dos servidores de email na lista de segurança.

Este tópico descreve como configurar a política de filtro de conexão padrão no Centro de Conformidade e Segurança ou no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com caixas de correio no Exchange Online; PowerShell do EOP autônomo para organizações sem caixas de correio do Exchange Online). & Para obter mais informações sobre como o EOP usa a filtragem de conexão faz parte das configurações anti-spam gerais da sua organização, consulte [Proteção anti-spam.](anti-spam-protection.md)

> [!NOTE]
> A Lista de Ip Allow, a lista de segurança e a Lista de IIs Bloqueados fazem parte de sua estratégia geral para permitir ou bloquear emails em sua organização. Para obter mais informações, [consulte Criar listas de remetentes seguros](create-safe-sender-lists-in-office-365.md) e Criar listas de [remetentes bloqueados.](create-block-sender-lists-in-office-365.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente à página de **Configurações antispam**, use <https://protection.office.com/antispam>.

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos deste artigo:
  - Para modificar a política de filtro de conexão  padrão, você precisa ser membro dos grupos de função Gerenciamento da Organização ou **Administrador de** Segurança.
  - Para acesso somente leitura à política de filtro de conexão padrão, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.

  Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

  **Observações**:

  - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).
  - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

- Para encontrar os endereços IP de origem dos servidores de email (senders) que você deseja permitir ou bloquear, você pode verificar o campo de header IP **(CIP)** de conexão no header da mensagem. To view a message header in various email clients, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).

- A Lista de I Ip Allow tem precedência sobre a Lista de I Ip Bloqueados (um endereço em ambas as listas não está bloqueado).

- A Lista de IIs Permitidas e a Lista de IIs Bloqueados suportam um máximo de 1273 entradas, onde uma entrada é um único endereço IP, um intervalo de endereços IP ou um IP CIDR (Roteamento entre Domínios sem Classes).

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a>Usar o Centro de Conformidade & segurança para modificar a política de filtro de conexão padrão

1. No Centro de Conformidade & Segurança e vá para Política **de** Gerenciamento \> **de Ameaças** \> **Anti-Spam.**

2. Na página **configurações anti-spam,** **expanda** a política de filtro de conexão clicando no ícone Expandir e clique ![ em Editar ](../../media/scc-expand-icon.png) **política.**

3. No flyout **Padrão** exibido, de configure qualquer uma das seguintes configurações:

   - **Descrição:** insira um texto descritivo opcional.

   - **Lista de I Ip Allow:** Clique **em Editar**. In the **IP Allow List** flyout that appears, enter an IPV4 address in the Address or address **range** box using the following syntax:

     - IP único: Por exemplo, 192.168.1.1.

     - Intervalo IP: Por exemplo, 192.168.0.1-192.168.0.254.

     - IP CIDR: Por exemplo, 192.168.0.1/25. Os valores válidos da máscara de rede são de /24 a /32. Para ignorar a filtragem de spam para valores de máscara DE IP CIDR /1 a /23, consulte a seção Ignorar filtragem de spam para um [IP CIDR](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) fora da seção de intervalo disponível mais adiante neste artigo.

     Para adicionar o endereço IP ou intervalo de endereços, clique **em Adicionar** ![ Ícone ](../../media/ITPro-EAC-AddIcon.png) . Para remover uma entrada, selecione a entrada no **Endereço IP Permitido e** clique em  ![ ](../../media/scc-remove-icon.png) Remover. Quando concluir, clique em **Salvar**.

   - **Lista de IIs Bloqueados:** Clique **em Editar**. No  flyout lista de IIs Bloqueados que aparece, insira um  único IP, intervalo de IP ou IP CIDR na caixa Endereço ou intervalo de endereços, conforme descrito anteriormente na configuração de Lista de I Ip **Permitir.**

     Para adicionar o endereço IP ou intervalo de endereços, clique **em Adicionar** ![ Ícone ](../../media/ITPro-EAC-AddIcon.png) . Para remover uma entrada, selecione a entrada no Endereço **IP Bloqueado** e clique em  ![ ](../../media/scc-remove-icon.png) Remover. Quando concluir, clique em **Salvar**.

   - **Ativar a lista de segurança:** habilitar ou desabilitar o uso da lista de segurança para identificar remetentes conhecidos e bons que ignorarão a filtragem de spam.

4. Quando concluir, clique em **Salvar**.

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a>Usar o Centro de Conformidade & segurança para exibir a política de filtro de conexão padrão

1. No Centro de Conformidade & Segurança e vá para Política **de** Gerenciamento \> **de Ameaças** \> **Anti-Spam.**

2. Na página **Configurações anti-spam,** clique no menu de lista ao lado da política padrão chamada Política de filtro **de conexão.**

3. As configurações de política são exibidas no menu drop down que é aberto.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Usar o PowerShell do Exchange Online ou o PowerShell do EOP autônomo para modificar a política de filtro de conexão padrão

Use a seguinte sintaxe:

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**Observações**:

- Os valores válidos de endereço IP ou intervalo de endereços são:

  - IP único: Por exemplo, 192.168.1.1.

  - Intervalo IP: Por exemplo, 192.168.0.1-192.168.0.254.

  - IP CIDR: Por exemplo, 192.168.0.1/25. Os valores válidos da máscara de rede são de /24 a /32.

- Para *substituir quaisquer entradas* existentes com os valores especificados, use a seguinte sintaxe: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` .

- Para *adicionar ou remover endereços* IP ou intervalos de endereços sem afetar outras entradas existentes, use a seguinte sintaxe: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` .

- Para esvaziar a Lista de I Ip Permitir ou a Lista de I Ip Bloqueados, use o `$null` valor.

Este exemplo configura a Lista de I Ip Allow e a Lista de I Ip Bloqueados com os endereços IP e intervalos de endereços especificados.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

Este exemplo adiciona e remove os endereços IP e intervalos de endereços especificados da Lista de I Ip Permitir.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy).

## <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se você modificou com êxito a política de filtro de conexão padrão, faça uma das seguintes etapas:

- No Centro de Conformidade & Segurança,  vá para Política de Gerenciamento de Ameaças \>  \> **Anti-Spam,** clique no menu de lista ao lado da política de filtro de conexão \> **(sempre** LIGADO) e verifique as configurações.

- No PowerShell do Exchange Online ou no EOP PowerShell autônomo, execute o seguinte comando e verifique as configurações:

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- Envie uma mensagem de teste de uma entrada na Lista de I Ip Permitir.

## <a name="additional-considerations-for-the-ip-allow-list"></a>Considerações adicionais para a Lista de I Ip Allow

As seções a seguir identificam itens adicionais que você precisa saber ao configurar a Lista de IIs.

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>Ignorar a filtragem de spam para um IP CIDR fora do intervalo disponível

Conforme descrito anteriormente neste artigo, você só pode usar um IP CIDR com a máscara de rede /24 a /32 na Lista de IIs. Para ignorar a filtragem de spam em mensagens de servidores de email de origem no intervalo de /1 a /23, você precisa usar regras de fluxo de emails do Exchange (também conhecidas como regras de transporte). No entanto, recomendamos que você não faça isso se possível, porque as mensagens serão bloqueadas se um endereço IP no intervalo de IP CIDR /1 a /23 aparecer em qualquer uma das listas de bloqueio proprietárias ou de terceiros da Microsoft.

Agora que você está totalmente ciente dos possíveis problemas, pode criar uma regra de fluxo de emails com as seguintes configurações (no mínimo) para garantir que as mensagens desses endereços IP ignorem a filtragem de spam:

- Condição de regra: **Aplique** esta regra se o endereço IP do remetente estiver em qualquer um desses intervalos ou exatamente corresponde (insira seu IP CIDR com uma máscara de rede \>  \>  \> /1 a /23).

- Ação de regra: **Modificar as propriedades da mensagem** Definir o nível de confiança de spam \> **(SCL)** Ignorar \> **filtragem de spam.**

Você pode auditar a regra, testar a regra, ativar a regra durante um período de tempo específico e outras seleções. Recomendamos testar a regra por um período antes de aplicá-la. Para obter mais informações, consulte [Gerenciar regras de fluxo de emails no Exchange Online.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>Ignorar a filtragem de spam em domínios de email seletivos da mesma fonte

Normalmente, adicionar um endereço IP ou um intervalo de endereços à Lista de IIs Permitir significa que você confia em todas as mensagens de entrada dessa fonte de email. Mas e se essa fonte enviar emails de vários domínios e você quiser ignorar a filtragem de spam para alguns desses domínios, mas não para outros? Não é possível usar a Lista de IIs Que Permitem IP para fazer isso, mas você pode usar a Lista de IIs Em combinação com uma regra de fluxo de emails.

Por exemplo, o servidor de email de origem 192.168.1.25 envia emails dos domínios contoso.com, fabrikam.com e tailspintoys.com, mas você só deseja ignorar a filtragem de spam para mensagens de remetentes no fabrikam.com. Para fazer isso, use as seguintes etapas:

1. Adicione 192.168.1.25 à Lista de IIs.

2. Configure uma regra de fluxo de emails com as seguintes configurações (no mínimo):

   - Condição de **regra:** Aplique esta regra se o endereço IP do remetente estiver em qualquer um desses intervalos ou se estiver exatamente igual a \>  \> 192.168.1.25 (o mesmo endereço IP ou intervalo de **endereços** que você adicionou à Lista de I Ip Permitir na etapa \> anterior).

   - Ação de regra: **Modificar as propriedades da mensagem** Definir o nível de confiança de spam \> **(SCL)** \> **0**.

   - Exceção de regra: **O domínio** do remetente é fabrikam.com (somente o domínio ou domínios que você \>  \> deseja ignorar a filtragem de spam).

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>Cenários em que as mensagens de fontes na Lista de I Ip Permitem ainda são filtradas

As mensagens de um servidor de email em sua Lista de IIs Ainda estão sujeitas à filtragem de spam nos seguintes cenários:

- Um endereço IP na lista de IIs também é configurado em um conector  de entrada local baseado em IP em qualquer locatário no Microsoft 365 (vamos chamar esse locatário **A),** e o locatário A e o servidor EOP que primeiro encontram a mensagem estão na mesma floresta do *Active* Directory nos datacenters da Microsoft. Nesse cenário, **IPV:CAL**  é adicionado aos headers de mensagem [anti-spam](anti-spam-message-headers.md) da mensagem (indicando que a mensagem foi ignorada pela filtragem de spam), mas a mensagem ainda está sujeita à filtragem de spam.

- O locatário que contém a Lista de IPIs e o servidor EOP que primeiro encontra a mensagem ocorrem em florestas diferentes do *Active* Directory nos datacenters da Microsoft. Nesse cenário, **IPV:CAL** *não* é adicionado aos headers de mensagem, portanto, a mensagem ainda está sujeita à filtragem de spam.

Se você encontrar qualquer um desses cenários, poderá criar uma regra de fluxo de emails com as seguintes configurações (no mínimo) para garantir que as mensagens dos endereços IP problemáticos ignorem a filtragem de spam:

- Condição de regra: **Aplique esta regra** se o endereço IP do remetente estiver em qualquer um desses intervalos ou se ele estiver exatamente coincidente \>  \>  \> (seu endereço IP ou endereços).

- Ação de regra: **Modificar as propriedades da mensagem** Definir o nível de confiança de spam \> **(SCL)** Ignorar \> **filtragem de spam.**

## <a name="new-to-microsoft-365"></a>Novo no Microsoft 365?

****

![O ícone curto do LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Novo para o Microsoft 365?** Descubra cursos em vídeo **gratuitos para administradores do Microsoft 365** e profissionais de TI, oferecidos pelo LinkedIn Learning.
