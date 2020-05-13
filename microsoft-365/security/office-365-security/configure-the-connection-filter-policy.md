---
title: Configurar a política de filtro de conexão padrão
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a configurar a filtragem de conexão na proteção do Exchange Online (EOP) para permitir ou bloquear emails de servidores de email.
ms.openlocfilehash: b9fd8c1b365f59647618e397a511873aae40146f
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213431"
---
# <a name="configure-connection-filtering"></a>Configurar a filtragem da conexão

Se você for um cliente Microsoft 365 com caixas de correio no Exchange Online ou um cliente autônomo do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, use a filtragem de conexão no EOP (especificamente a política de filtro de conexão padrão) para identificar servidores de email de origem bons ou defeituosos por seus endereços IP. Os principais componentes da política de filtro de conexão padrão são:

- **Lista de permissões de IP**: ignorar a filtragem de spam para todas as mensagens de entrada dos servidores de email de origem que você especificar por endereço IP ou intervalo de endereços IP. Para cenários em que a filtragem de spam ainda pode ocorrer em mensagens dessas fontes, consulte os [cenários em que as mensagens de fontes na lista de IPs permitidos ainda serão filtradas](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) posteriormente neste tópico. Para obter mais informações sobre como a lista de IPs permitidos deve se encaixar em sua estratégia geral de remetentes confiáveis, consulte [criar listas de remetentes seguros no EOP](create-safe-sender-lists-in-office-365.md).

- **Lista de IPs bloqueados**: bloquear todas as mensagens de entrada dos servidores de email de origem que você especificar por endereço IP ou intervalo de endereços IP. As mensagens de entrada são rejeitadas, não são marcadas como spam e nenhuma filtragem adicional ocorre. Para obter mais informações sobre como a lista de bloqueios de IP deve se encaixar em sua estratégia de remetentes gerais bloqueados, consulte [criar listas de remetentes bloqueados no EOP](create-block-sender-lists-in-office-365.md).

- **Lista segura**: a *lista segura* é uma lista de permissões dinâmicas no datacenter da Microsoft que não requer nenhuma configuração de cliente. A Microsoft identifica essas fontes de email confiáveis de assinaturas para várias listas de terceiros. Você habilita ou desabilita o uso da lista segura; Não é possível configurar os servidores de email de origem na lista de confiança. A filtragem de spam é ignorada nas mensagens de entrada dos servidores de email na lista de confiança.

Este tópico descreve como configurar a política de filtro de conexão padrão no centro de conformidade e segurança & ou no PowerShell (PowerShell do Exchange Online para organizações do Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online). Para obter mais informações sobre como o EOP usa a filtragem de conexão faz parte das configurações antispam gerais da sua organização, consulte See [anti-spam Protection](anti-spam-protection.md).

> [!NOTE]
> A lista de IPs permitidos, a lista segura e a lista de IPs bloqueados são uma parte de sua estratégia geral para permitir ou bloquear emails em sua organização. Para obter mais informações, consulte [criar listas de remetentes confiáveis](create-safe-sender-lists-in-office-365.md) e [criar listas de remetentes bloqueados](create-block-sender-lists-in-office-365.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente à página de **Configurações antispam**, use <https://protection.office.com/antispam>.

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Para se conectar ao PowerShell do EOP autônomo, confira [conectar-se ao PowerShell do Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Você precisa receber permissões para executar esses procedimentos. Para modificar a política de filtro de conexão padrão, você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de **administrador de segurança** . Para acesso somente leitura à política de filtro de conexão padrão, você precisa ser membro do grupo de função **leitor de segurança** . Para obter mais informações sobre grupos de funções no Centro de Conformidade e Segurança, confira [Permissões no Centro de Conformidade e Segurança](permissions-in-the-security-and-compliance-center.md).

- Para localizar os endereços IP de origem dos servidores de email (remetentes) que você deseja permitir ou bloquear, você pode verificar o campo de cabeçalho IP de conexão (**CIP**) no cabeçalho da mensagem. Para exibir um cabeçalho de mensagem em vários clientes de email, confira [exibir cabeçalhos de mensagens da Internet no Outlook](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c).

- A lista de IPs permitidos tem precedência sobre a lista de bloqueios de IP (um endereço em ambas as listas não é bloqueado).

- A lista de permissões de IP e a lista de bloqueios de IP oferecem suporte a um máximo de 1273 entradas, em que uma entrada é um único endereço IP, um intervalo de endereços IP ou um IP CIDR (roteamento entre domínios sem classificação).

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a>Usar o centro de conformidade de & de segurança para modificar a política de filtro de conexão padrão

1. No centro de conformidade & segurança e vá para **Threat management** \> **Policy** \> **anti-spam**da política de gerenciamento de ameaças.

2. Na página **configurações antispam** , expanda política de **filtro de conexão** clicando em ![ expandir ícone ](../../media/scc-expand-icon.png) e, em seguida, clique em **Editar política**.

3. No submenu **padrão** que aparece, configure qualquer uma das seguintes configurações:

   - **Descrição**: insira texto descritivo opcional.

   - **Lista de permissões de IP**: clique em **Editar**. No submenu da **lista de IPs permitidos** que aparece, insira um endereço IPv4 na caixa **endereço ou intervalo de endereços** usando a seguinte sintaxe:

     - IP único: por exemplo, 192.168.1.1.

     - Intervalo de IP: por exemplo, 192.168.0.1-192.168.0.254.

     - IP CIDR: por exemplo, 192.168.0.1/25. Os valores válidos da máscara de rede são/24 a/32. Para ignorar a filtragem de spam para valores de máscara de IP CIDR/1 a/23, confira a seção [ignorar filtragem de spam para um IP CIDR fora da seção intervalo disponível](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) mais adiante neste tópico.

     Para adicionar o endereço IP ou o intervalo de endereços, clique em **Adicionar** ![ ícone de adição ](../../media/ITPro-EAC-AddIcon.png) . Para remover uma entrada, selecione a entrada em **endereço IP permitido** e, em seguida, clique em **remover** ![ remoção ](../../media/scc-remove-icon.png) . Quando concluir, clique em **Salvar**.

   - **Lista de IPs bloqueados**: clique em **Editar**. No submenu da **lista de bloqueios de IP** exibido, insira um único IP, intervalo IP ou IP CIDR na caixa **endereço ou intervalo de endereços** , conforme descrito anteriormente na configuração da lista de permissões de **IP** .

     Para adicionar o endereço IP ou o intervalo de endereços, clique em **Adicionar** ![ ícone de adição ](../../media/ITPro-EAC-AddIcon.png) . Para remover uma entrada, selecione a entrada em **endereço IP bloqueado** e, em seguida, clique em **remover** ![ remoção ](../../media/scc-remove-icon.png) . Quando concluir, clique em **Salvar**.

   - **Ativar a lista segura**: habilitar ou desabilitar o uso da lista segura para identificar bons remetentes conhecidos que irão ignorar a filtragem de spam.

4. Quando concluir, clique em **Salvar**.

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a>Usar o centro de conformidade de & de segurança para exibir a política de filtro de conexão padrão

1. No centro de conformidade & segurança e vá para **Threat management** \> **Policy** \> **anti-spam**da política de gerenciamento de ameaças.

2. Na página **configurações antispam** , clique na lista suspensa ao lado da política padrão chamada **diretiva de filtro de conexão**.

3. As configurações de política são exibidas no menu suspenso que é aberto.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Usar o PowerShell do Exchange Online ou o PowerShell do EOP para modificar a política de filtro de conexão padrão

Use a seguinte sintaxe:

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**Observações**:

- Os valores válidos de endereço IP ou intervalo de endereços são:

  - IP único: por exemplo, 192.168.1.1.

  - Intervalo de IP: por exemplo, 192.168.0.1-192.168.0.254.

  - IP CIDR: por exemplo, 192.168.0.1/25. Os valores válidos da máscara de rede são/24 a/32.

- Para *substituir* as entradas existentes pelos valores que você especificar, use a seguinte sintaxe: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` .

- Para *Adicionar ou remover* endereços IP ou intervalos de endereços sem afetar outras entradas existentes, use a seguinte sintaxe: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` .

- Para esvaziar a lista de IPs permitidos ou a lista de IPs bloqueados, use o valor `$null` .

Este exemplo configura a lista de permissões de IP e a lista de IPs bloqueados com os endereços IP e intervalos de endereços especificados.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

Este exemplo adiciona e remove os endereços IP e os intervalos de endereços especificados da lista de IPs permitidos.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedconnectionfilterpolicy).

## <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se você modificou com êxito a política de filtro de conexão padrão, execute uma das seguintes etapas:

- No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** \> **Policy** \> **anti-spam** \> clique na lista suspensa ao lado da **política de filtro de conexão (AlwaysOn**) e verifique as configurações.

- No PowerShell do Exchange Online ou no PowerShell do EOP autônomo, execute o seguinte comando e verifique as configurações:

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- Envie uma mensagem de teste de uma entrada na lista de IPs permitidos.

## <a name="additional-considerations-for-the-ip-allow-list"></a>Considerações adicionais para a lista de IPs permitidos

As seções a seguir identificam itens adicionais que você precisa saber ao configurar a lista de IPs permitidos.

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>Ignorar a filtragem de spam para um IP CIDR fora do intervalo disponível

Conforme descrito anteriormente neste tópico, você só pode usar um IP CIDR com a máscara de rede/24 a/32 na lista de IPs permitidos. Para ignorar a filtragem de spam em mensagens de servidores de email de origem no intervalo/1 a/23, você precisa usar as regras de fluxo de email do Exchange (também conhecidas como regras de transporte). Mas recomendamos que você não faça isso se for possível, porque as mensagens serão bloqueadas se um endereço IP no intervalo de/1 a/23 de IP CIDR aparecer em qualquer uma das listas de bloqueios de terceiros ou proprietários da Microsoft.

Agora que você está totalmente ciente dos possíveis problemas, você pode criar uma regra de fluxo de email com as seguintes configurações (no mínimo) para garantir que as mensagens desses endereços IP ignorem a filtragem de spam:

- Condição da regra: **aplique esta regra se** \> **o** \> **endereço IP do remetente estiver em qualquer um desses intervalos ou correspondências exatas** \> (Insira seu IP de CIDR com uma máscara de rede de/1 a/23).

- Ação de regra: **modificar as propriedades de mensagem** \> **defina o nível de confiança de spam (SCL)** \> **ignorar filtragem de spam**.

Você pode auditar a regra, testar a regra, ativar a regra durante um período de tempo específico e outras seleções. Recomendamos testar a regra por um período antes de aplicá-la. Para obter mais informações, consulte [Manage Mail Flow Rules in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>Ignorar filtragem de spam em domínios de email seletivos da mesma fonte

Normalmente, a adição de um endereço IP ou intervalo de endereços à lista de IPs permitidos significa que você confia em todas as mensagens de entrada dessa fonte de email. Mas e se essa fonte enviar emails de vários domínios e você quiser ignorar a filtragem de spam para alguns desses domínios, mas não para outros? Você não pode usar a lista de permissões de IP sozinho para fazer isso, mas pode usar a lista de IPs permitidos em combinação com uma regra de fluxo de emails.

Por exemplo, o servidor de email de origem 192.168.1.25 envia emails dos domínios contoso.com, fabrikam.com e tailspintoys.com, mas você só deseja ignorar a filtragem de spam para mensagens de remetentes no fabrikam.com. Para fazer isso, use as seguintes etapas:

1. Adicione 192.168.1.25 à lista de IPs permitidos.

2. Configure uma regra de fluxo de emails com as seguintes configurações (no mínimo):

   - Condição de regra: **aplique esta regra se** \> **o** \> **endereço IP do remetente estiver em qualquer um desses intervalos ou corresponder exatamente** \> a 192.168.1.25 (o mesmo endereço IP ou intervalo de endereços adicionado à lista de IPs permitidos na etapa anterior).

   - Ação de regra: **modificar as propriedades da mensagem** \> **defina o nível de confiança de spam (SCL)** \> **0**.

   - Exceção de regra: **o domínio do remetente** \> **é** \> fabrikam.com (somente o domínio ou domínios que você deseja ignorar a filtragem de spam).

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>Cenários em que as mensagens de fontes na lista de IPs permitidos ainda estão filtradas

As mensagens de um servidor de email na lista de IPs permitidos ainda estão sujeitas à filtragem de spam nos seguintes cenários:

- Um endereço IP na sua lista de IPs permitidos também é configurado em um conector de entrada baseado em IP ou local em *qualquer* locatário no Microsoft 365 (Vamos chamar este locatário a **) e o locatário a** e o servidor do EOP que encontra primeiro a mensagem acontecerem na *mesma* floresta do Active Directory nos datacenters da Microsoft. Neste cenário, **IPV: Cal** *é* adicionado aos cabeçalhos da mensagem [antispam](anti-spam-message-headers.md) da mensagem (indicando a mensagem de filtragem de spam ignorada), mas a mensagem ainda está sujeita à filtragem de spam.

- Seu locatário que contenha a lista de permissões de IP e o servidor EOP que primeiro encontra a mensagem acontecerá em florestas *diferentes* do Active Directory nos datacenters da Microsoft. Neste cenário, **IPV: Cal** *não é* adicionado aos cabeçalhos da mensagem, portanto, a mensagem ainda está sujeita à filtragem de spam.

Se você encontrar um desses cenários, poderá criar uma regra de fluxo de email com as seguintes configurações (no mínimo) para garantir que as mensagens dos endereços IP problemáticos ignorem a filtragem de spam:

- Condição de regra: **aplique esta regra se** \> **o** \> **endereço IP do remetente estiver em qualquer um desses intervalos ou correspondências exatas** \> (seu endereço IP ou endereços).

- Ação de regra: **modificar as propriedades de mensagem** \> **defina o nível de confiança de spam (SCL)** \> **ignorar filtragem de spam**.

## <a name="new-to-microsoft-365"></a>Novo no Microsoft 365?

||
|:-----|
|![O ícone curto do LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?** Descubra cursos de vídeo gratuitos para **Administradores e profissionais de ti**, trazidos para você pelo LinkedIn Learning.|
