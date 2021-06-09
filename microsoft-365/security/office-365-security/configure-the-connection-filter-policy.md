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
description: Os administradores podem aprender a configurar a filtragem de conexão no Proteção do Exchange Online (EOP) para permitir ou bloquear emails de servidores de email.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b5eb24377dd9f9ac304e1df7b2902d29e4a738b9
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821956"
---
# <a name="configure-connection-filtering"></a>Configurar a filtragem de conexão

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


Se você for um cliente Microsoft 365 com caixas de correio no Exchange Online ou um cliente autônomo Proteção do Exchange Online (EOP) sem caixas de correio Exchange Online, use a filtragem de conexão no EOP (especificamente, a política de filtro de conexão padrão) para identificar servidores de email de origem boa ou ruim por seus endereços IP. Os principais componentes da política de filtro de conexão padrão são:

- **Lista de IDs:** Ignorar a filtragem de spam para todas as mensagens de entrada dos servidores de email de origem especificados por endereço IP ou intervalo de endereços IP. Para cenários em que a filtragem de spam ainda pode ocorrer em mensagens dessas fontes, consulte a seção Cenários em que as mensagens de fontes na Lista de [IDS](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) ainda são filtradas posteriormente neste artigo. Para obter mais informações sobre como a Lista de IP Allow deve se ajustar à sua estratégia geral de remetentes seguros, consulte [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).

- **Lista de Bloqueios de IP**: Bloqueie todas as mensagens de entrada dos servidores de email de origem especificados por endereço IP ou intervalo de endereços IP. As mensagens de entrada são rejeitadas, não são marcadas como spam e nenhuma filtragem adicional ocorre. Para obter mais informações sobre como a Lista de Bloqueios de IP deve se ajustar à sua estratégia geral de remetentes bloqueados, consulte [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).

- **Cofre**: a lista *segura* é uma lista dinâmica de autorizações no datacenter da Microsoft que não requer configuração do cliente. A Microsoft identifica essas fontes de email confiáveis de assinaturas para várias listas de terceiros. Você habilita ou desabilita o uso da lista segura; você não pode configurar os servidores de email de origem na lista segura. A filtragem de spam é ignorada em mensagens de entrada dos servidores de email na lista segura.

Este artigo descreve como configurar a política de filtro de conexão padrão no centro de segurança do Microsoft 365 ou no PowerShell (Exchange Online PowerShell para organizações Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem Exchange Online caixas de correio). Para obter mais informações sobre como o EOP usa a filtragem de conexão faz parte das configurações gerais anti-spam da sua organização, consulte [Proteção anti-spam](anti-spam-protection.md).

> [!NOTE]
> A Lista de IDs, lista segura e a Lista de Bloqueios de IP fazem parte da estratégia geral para permitir ou bloquear emails em sua organização. Para obter mais informações, consulte [Create safe sender lists](create-safe-sender-lists-in-office-365.md) and Create blocked [sender lists](create-block-sender-lists-in-office-365.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Abra o centro de segurança em <https://security.microsoft.com>. Para ir diretamente à página de **Políticas antispam**, use <https://security.microsoft.com/antispam>.

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa de permissões em **Exchange Online** antes de poder realizar os procedimentos neste artigo:
  - Para modificar a política de filtro de conexão padrão, você precisa ser membro dos grupos de função Gerenciamento da Organização **ou** Administrador **de** Segurança.
  - Para acesso somente leitura à política de filtro de conexão padrão, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.

  Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Observações**:

  - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).
  - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

- Para encontrar os endereços IP de origem dos servidores de email (senders) que você deseja permitir ou bloquear, você pode verificar o campo de header ip (**CIP**) de conexão no header da mensagem. Para exibir um header de mensagem em vários clientes de email, consulte [Exibir os headers](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)de mensagens da Internet em Outlook .

- A Lista de IDS tem precedência sobre a Lista de Bloqueios de IP (um endereço em ambas as listas não está bloqueado).

- A Lista de ICs Permitidas e a Lista de Bloqueios de IP suportam no máximo 1273 entradas, onde uma entrada é um único endereço IP, um intervalo de endereços IP ou um IP CIDR (Roteamento Entre Domínios Sem Classes).

## <a name="use-the-security-center-to-modify-the-default-connection-filter-policy"></a>Use o centro de segurança para modificar a política de filtro de conexão padrão

1. No centro de segurança, acesse **Email e Colaboração** \> **Políticas e Regras** \> **Políticas de ameaças** \> **seção** Políticas \> **Anti-spam**.

2. Na página **Políticas anti-spam,** selecione Política de filtro de conexão **(Padrão)** na lista clicando no nome da política.

3. No sobremenu de detalhes da política exibido, configure qualquer uma das seguintes configurações:

   - **Seção Descrição:** Clique **em Editar nome e descrição.** No **flyout Editar nome e descrição** que aparece, insira texto descritivo opcional na caixa **Descrição.**

     Quando concluir, clique em **Salvar**.

   - **Seção Filtragem de conexão**: Clique em **Editar política de filtro de conexão.** No sobrevoo exibido, configure as seguintes configurações:

     - **Sempre permita mensagens dos seguintes endereços IP ou intervalo de endereços:** esta é a lista de IDS. Clique na caixa, insira um valor e pressione Enter ou selecione o valor completo exibido abaixo da caixa. Os valores válidos são:
       - IP único: por exemplo, 192.168.1.1.
       - Intervalo ip: por exemplo, 192.168.0.1-192.168.0.254.
       - IP CIDR: Por exemplo, 192.168.0.1/25. Os valores válidos da máscara de sub-rede são /24 a /32. Para ignorar a filtragem de spam de /1 a /23, consulte a seção Ignorar filtragem de spam para um [IP CIDR](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) fora do intervalo disponível posteriormente neste artigo.

       Repita essa etapa quantas vezes forem necessárias. Para remover uma entrada existente, clique em Remover ![Ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) ao lado do valor.

     Para adicionar o endereço IP ou o intervalo de endereços, clique na caixa e digite itclick **Add** ![ Add Icon ](../../media/ITPro-EAC-AddIcon.png) . Para remover uma entrada, selecione a entrada em **Endereço IP Permitido** e clique em **Remover** ![ Remover ](../../media/scc-remove-icon.png) . Quando concluir, clique em **Salvar**.

   - **Sempre bloqueie mensagens dos seguintes endereços IP ou intervalo de endereços**: esta é a Lista de Bloqueios de IP. Insira um único IP, intervalo IP ou IP CIDR na caixa conforme descrito anteriormente na configuração Sempre permitir mensagens dos seguintes endereços IP ou **intervalo de** endereços.

   - **Ativar lista segura**: Habilitar ou desabilitar o uso da lista segura para identificar remetentes conhecidos e bons que ignorarão a filtragem de spam. Para usar a lista segura, marque a caixa de seleção.

   Quando concluir, clique em **Salvar**.

4. De volta ao submenu de detalhes da política, clique em **Fechar**.

## <a name="use-the-security-center-to-view-the-default-connection-filter-policy"></a>Use o centro de segurança para exibir a política de filtro de conexão padrão

1. No centro de segurança, acesse **Email e Colaboração** \> **Políticas e Regras** \> **Políticas de ameaças** \> **seção** Políticas \> **Anti-spam**.

2. Na página **Políticas anti-spam,** as seguintes propriedades são exibidas na lista de políticas:

   - **Nome**: Esse valor é Política de filtro **de conexão (Padrão)** para a política de filtro de conexão padrão.
   - **Status**: esse valor é **Always on para** a política de filtro de conexão padrão.
   - **Prioridade**: esse valor é **Mais baixo para** a política de filtro de conexão padrão.
   - **Tipo**: esse valor está em branco para a política de filtro de conexão padrão.

3. Quando você seleciona a política de filtro de conexão padrão, as configurações de política são exibidas em um sobrevoo.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Use Exchange Online PowerShell ou EOP PowerShell autônomo para modificar a política de filtro de conexão padrão

Use a seguinte sintaxe:

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**Observações**:

- Os valores válidos de endereço IP ou intervalo de endereços são:
  - IP único: por exemplo, 192.168.1.1.
  - Intervalo ip: por exemplo, 192.168.0.1-192.168.0.254.
  - IP CIDR: Por exemplo, 192.168.0.1/25. Os valores válidos da máscara de rede são /24 a /32.
- Para *substituir qualquer entrada* existente com os valores especificados, use a seguinte sintaxe: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` .
- Para *adicionar ou remover* endereços IP ou intervalos de endereços sem afetar outras entradas existentes, use a seguinte sintaxe: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` .
- Para esvaziar a Lista de IDS ou a Lista de Bloqueios de IP, use o valor `$null` .

Este exemplo configura a Lista de Ip Allow e a Lista de Bloqueios de IP com os endereços IP especificados e intervalos de endereços.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

Este exemplo adiciona e remove os endereços IP especificados e os intervalos de endereços da Lista de Ip Allow.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-HostedConnectionFilterPolicy](/powershell/module/exchange/set-hostedconnectionfilterpolicy).

## <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se você modificou com êxito a política de filtro de conexão padrão, faça qualquer uma das seguintes etapas:

- No centro de segurança, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \>  \> **Anti-spam** selecione Política de filtro de conexão \> **(Padrão)** na lista clicando no nome da política e verifique as configurações.

- No Exchange Online PowerShell ou no EOP PowerShell autônomo, execute o seguinte comando e verifique as configurações:

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- Envie uma mensagem de teste de uma entrada na Lista de IDS.

## <a name="additional-considerations-for-the-ip-allow-list"></a>Considerações adicionais para a Lista de IDS

As seções a seguir identificam itens adicionais que você precisa saber ao configurar a Lista de Ip Allow.

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>Ignorar a filtragem de spam para um IP CIDR fora do intervalo disponível

Conforme descrito anteriormente neste artigo, você só pode usar um IP CIDR com a máscara de rede /24 a /32 na Lista de Ip Allow. Para ignorar a filtragem de spam em mensagens de servidores de email de origem no intervalo /1 a /23, você precisa usar Exchange de fluxo de emails (também conhecidas como regras de transporte). No entanto, recomendamos que você não faça isso se possível, pois as mensagens serão bloqueadas se um endereço IP no intervalo IP CIDR /1 a /23 aparecer em qualquer uma das listas de bloqueio proprietárias ou de terceiros da Microsoft.

Agora que você está totalmente ciente dos possíveis problemas, pode criar uma regra de fluxo de emails com as seguintes configurações (no mínimo) para garantir que as mensagens desses endereços IP pulem a filtragem de spam:

- Condição de regra: **aplique essa** regra se o endereço IP do remetente estiver em qualquer um desses intervalos ou se corresponde exatamente (insira seu IP CIDR com uma máscara de rede \>  \>  \> de /1 a /23).
- Ação de regra: **Modificar as propriedades da mensagem** Definir o nível de confiança de spam \> **(SCL) Ignorar** a \> **filtragem de spam**.

Você pode auditar a regra, testar a regra, ativar a regra durante um período de tempo específico e outras seleções. Recomendamos testar a regra por um período antes de aplicá-la. Para obter mais informações, consulte [Manage mail flow rules in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>Ignorar a filtragem de spam em domínios de email seletivos da mesma fonte

Normalmente, a adição de um endereço IP ou intervalo de endereços à Lista de IDS significa que você confia em todas as mensagens de entrada dessa fonte de email. Mas e se essa fonte enviar emails de vários domínios e você quiser ignorar a filtragem de spam para alguns desses domínios, mas não para outros? Você não pode usar a Lista de IDS somente para fazer isso, mas pode usar a Lista de IDS em combinação com uma regra de fluxo de emails.

Por exemplo, o servidor de email de origem 192.168.1.25 envia emails dos domínios contoso.com, fabrikam.com e tailspintoys.com, mas você só deseja ignorar a filtragem de spam para mensagens de remetentes no fabrikam.com. Para fazer isso, use as seguintes etapas:

1. Adicione 192.168.1.25 à Lista de Ip Allow.

2. Configurar uma regra de fluxo de emails com as seguintes configurações (no mínimo):
   - Condição de **regra:** aplique essa regra se o endereço IP do remetente estiver em qualquer um desses intervalos ou corresponde exatamente a \>  \> 192.168.1.25 (o mesmo endereço **IP** ou intervalo de endereços que você adicionou à Lista de I Ip \> Allow na etapa anterior).
   - Ação de regra: **Modificar as propriedades da mensagem** Definir o nível de confiança de spam \> **(SCL)** \> **0**.
   - Exceção de regra: **o domínio** do remetente é fabrikam.com (somente o domínio ou domínios que você deseja ignorar \>  \> a filtragem de spam).

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>Cenários em que as mensagens de fontes na Lista de IDS ainda são filtradas

As mensagens de um servidor de email em sua Lista de IDS ainda estão sujeitas à filtragem de spam nos seguintes cenários:

- Um endereço IP em sua Lista de IDIs também é configurado em  um conector de entrada local baseado em IP em qualquer locatário no Microsoft 365 (vamos chamar esse Locatário **A),** e o Locatário A e o servidor EOP que primeiro encontra a mensagem estão na mesma floresta do *Active* Directory nos datacenters da Microsoft. Nesse cenário, **IPV:CAL**  é adicionado aos headers de mensagens [anti-spam](anti-spam-message-headers.md) da mensagem (indicando a filtragem de spam ignorada pela mensagem), mas a mensagem ainda está sujeita à filtragem de spam.

- Seu locatário que contém a Lista de Permitir IP e o servidor EOP que encontra pela primeira vez a mensagem ocorre em florestas diferentes do *Active* Directory nos datacenters da Microsoft. Nesse cenário, **IPV:CAL**  não é adicionado aos headers da mensagem, portanto, a mensagem ainda está sujeita à filtragem de spam.

Se você encontrar qualquer um desses cenários, poderá criar uma regra de fluxo de emails com as seguintes configurações (no mínimo) para garantir que as mensagens dos endereços IP problemáticos pulem a filtragem de spam:

- Condição de regra: **aplique essa regra** se o endereço IP do remetente estiver em qualquer um desses intervalos ou se corresponde exatamente \>  \>  \> (seu endereço IP ou endereço).
- Ação de regra: **Modificar as propriedades da mensagem** Definir o nível de confiança de spam \> **(SCL) Ignorar** a \> **filtragem de spam**.

## <a name="new-to-microsoft-365"></a>Novo para Microsoft 365?

****

![O ícone curto do LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New para Microsoft 365?** Descubra cursos de vídeo **gratuitos Microsoft 365 administradores** e profissionais de TI , trazidos para você pelo LinkedIn Learning.
