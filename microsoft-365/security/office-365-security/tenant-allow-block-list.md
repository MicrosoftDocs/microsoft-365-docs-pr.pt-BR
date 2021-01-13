---
title: Gerenciar suas autorizações e blocos na Lista de Bloqueios/Permitir Locatários
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a configurar os bloqueios e as autorizações na Lista de Bloqueios/Permitir Locatários no portal de Segurança.
ms.openlocfilehash: c789b09224d00f5bb41ae29d6d2a6efa64d23a8d
ms.sourcegitcommit: 495b66b77d6dbe6d69e5b06b304089e4e476e568
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799708"
---
# <a name="managing-allows-and-blocks-in-the-tenant-allowblock-list"></a>Gerenciar permite e bloqueia na Lista de Bloqueios/Permitir Locatários

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Os recursos descritos neste artigo estão em Visualização, estão sujeitos a alterações e não estão disponíveis em todas as organizações.

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, você pode não concordar com o veredito de filtragem do EOP. Por exemplo, uma boa mensagem pode ser marcada como ruim (um falso positivo) ou uma mensagem ruim pode ser permitida (um falso negativo).

A Lista de Bloqueio & s/Bloqueios de Locatários no Centro de Conformidade e Segurança oferece uma maneira de substituir manualmente os vereditos de filtragem do Microsoft 365. A Lista de Bloqueios/Permitir Locatários é usada durante o fluxo de emails e no momento em que o usuário clica. Você pode especificar URLs para permitir ou bloquear na Lista de Bloqueios/Bloqueios de Locatários.

Este tópico descreve como configurar entradas na Lista de Bloqueios/Permitir Locatários no Centro de Conformidade do & de Segurança ou no PowerShell (Organizações do PowerShell do Exchange Online para Microsoft 365 com caixas de correio no Exchange Online; PowerShell do EOP autônomo para organizações sem caixas de correio do Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Você abrir o Centro de conformidade e segurança em <https://protection.office.com/>. Para ir diretamente para a página **Permitir/Bloquear Lista** de Locatários, use <https://protection.office.com/tenantAllowBlockList> .

- Os valores de URL disponíveis são descritos na sintaxe da URL para a seção [Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) posteriormente neste artigo.

- A Lista de Bloqueios/Permitir Locatários permite um máximo de 500 entradas para URLs.

- Uma entrada deve estar ativa dentro de 15 minutos.

- As entradas de bloco têm precedência sobre as entradas de autorização.

- Por padrão, as entradas na Lista de Bloqueios/Bloqueios de Locatários expiram após 30 dias. Você pode especificar uma data ou defini-la para nunca expirar.

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos deste artigo:
  - Para adicionar e remover valores da Lista de Bloqueios/Permitir  Locatários, você precisa ser membro dos grupos de função Gerenciamento da Organização ou **Administrador de** Segurança.
  - Para acesso somente leitura à Lista de Locatários Permitir/Bloquear, você precisa ser membro dos grupos de funções Leitor **Global** ou **Leitor de** Segurança.

  Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

  **Observações**:

  - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>Usar o Centro de Conformidade & segurança para criar entradas de URL na Lista de Bloqueios/Bloqueios de Locatários

Para obter detalhes sobre a sintaxe para entradas de URL, consulte a sintaxe da URL para a seção [Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) posteriormente neste artigo.

1. No Centro de Conformidade e Segurança &, vá para **Listas** de \>  \> **Bloqueios/Permitir** Locatários da Política de Gerenciamento de Ameaças.

2. Na página **Permitir/Bloquear Lista** de Locatários, verifique se a **guia URLs** está selecionada e clique em **Adicionar**

3. No menu Defina as seguintes configurações no menu Adicionar novas **URLs:**

   - **Adicione URLs com caracteres curinga:** insira uma URL por linha, até um máximo de 20.

   - **Bloquear/Permitir:** selecione se deseja **permitir** ou **bloquear** as URLs especificadas.

   - **Nunca expirar:** faça uma das seguintes etapas:

     - Verifique se a configuração está desligada ( Alternar) e use a caixa Expira na caixa Para especificar a data de expiração ![ ](../../media/scc-toggle-off.png) para as entradas. 

     ou

     - Mova o alternância para a direita para configurar as entradas para nunca expirar: ![Ativar](../../media/scc-toggle-on.png).

   - **Observação opcional:** insira texto descritivo para as entradas.

4. Quando terminar, clique em **Adicionar.**

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>Usar o Centro de Conformidade & segurança para exibir entradas na Lista de Bloqueios/Bloqueios de Locatários

1. No Centro de Conformidade e Segurança &, vá para **Listas** de \>  \> **Bloqueios/Permitir** Locatários da Política de Gerenciamento de Ameaças.

2. Selecione a **guia URLs.**

Clique nos seguintes títulos de coluna para classificar em ordem crescente ou decrescente:

- **Valor**
- **Ação:** **Bloquear** ou **Permitir.**
- **Data da última atualização**
- **Data de expiração**
- **Observação**

Clique **em** Grupo para agrupar as entradas **por Ação** (**Bloquear** ou **Permitir**) ou **Nenhum**.

Clique **em** Pesquisar, insira todo ou parte de um valor e pressione ENTER para encontrar um valor específico. Quando terminar, clique em Limpar ícone **Limpar** ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) pesquisa.

Clique **em Filtro**. No  menu desdopante Filtro exibido, de configure qualquer uma das seguintes configurações:

- **Ação:** selecione **Permitir**, **Bloquear** ou ambos.

- **Nunca expirar**: Selecione desligado: ![ Alternar ](../../media/scc-toggle-off.png) ou desligar: ![ ](../../media/scc-toggle-on.png) Alternar.

- **Last updated:** Select a start date (**From**), an end date (**To**) or both.

- **Data de expiração:** selecione uma data de início (**De**), uma data de término (**Para**) ou ambas.

Quando terminar, clique em **Aplicar.**

Para limpar os filtros existentes, clique em **Filtro** e, no flyout **Filtro** exibido, clique em **Limpar filtros.**

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a>Usar o Centro de Conformidade & segurança para modificar entradas na Lista de Bloqueios/Bloqueios de Locatários

Você não pode modificar o valor da URL em si. Em vez disso, você precisa excluir a entrada e recriá-la.

1. No Centro de Conformidade e Segurança &, vá para **Listas** de \>  \> **Bloqueios/Permitir** Locatários da Política de Gerenciamento de Ameaças.

2. Selecione a **guia URLs.**

3. Selecione a entrada que você deseja modificar e clique em **Editar** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) ícone.

4. No menu desdopo que aparece, de configure as seguintes configurações:

   - **Bloquear/Permitir:** Selecionar **Permitir** ou **Bloquear.**

   - **Nunca expirar:** faça uma das seguintes etapas:

     - Verifique se a configuração está desligada ( Alternar) e use a caixa Expira na caixa para especificar a data de ![ ](../../media/scc-toggle-off.png) expiração da entrada. 

     ou

     - Mova o alternância para a direita para configurar a entrada para nunca expirar: ![Ativar](../../media/scc-toggle-on.png).

   - **Observação opcional:** insira texto descritivo para a entrada.

5. Quando concluir, clique em **Salvar**.

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a>Usar o Centro de Conformidade & segurança para remover entradas da Lista de Bloqueios/Bloqueios de Locatários

1. No Centro de Conformidade e Segurança &, vá para **Listas** de \>  \> **Bloqueios/Permitir** Locatários da Política de Gerenciamento de Ameaças.

2. Selecione a **guia URLs.**

3. Selecione a entrada que você deseja remover e clique em **Excluir** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) ícone.

4. Na caixa de diálogo de aviso exibida, clique em **Excluir.**

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Usar o PowerShell do Exchange Online ou o PowerShell do EOP autônomo para configurar a Lista de Bloqueios/Permitir Locatários

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a>Usar o PowerShell para adicionar entradas na Lista de Bloqueios/Permitir Locatários

Para adicionar entradas na Lista de Bloqueios/Permitir Locatários, use a seguinte sintaxe:

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

Este exemplo adiciona uma entrada de bloco de URL para contoso.com e todos os sub-contoso.com (por exemplo, contoso.com, www.contoso.com e xyz.abc.contoso.com). Como não usamos os parâmetros ExpirationDate ou NoExpiration, a entrada expira após 30 dias.

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>Usar o PowerShell para exibir entradas na Lista de Locatários Permitir/Bloquear

Para exibir entradas na Lista de Bloqueios/Permitir Locatários, use a seguinte sintaxe:

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

Este exemplo retorna todas as URLs bloqueadas.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a>Usar o PowerShell para modificar entradas na Lista de Locatários Permitir/Bloquear

Você não pode modificar o valor da URL em si. Em vez disso, você precisa excluir a entrada e recriá-la.

Para modificar entradas na Lista de Bloqueios/Permitir Locatários, use a seguinte sintaxe:

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

Este exemplo altera a data de expiração da entrada especificada.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a>Usar o PowerShell para remover entradas da Lista de Locatários Permitir/Bloquear

Para remover entradas da Lista de Bloqueios/Permitir Locatários, use a seguinte sintaxe:

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

Este exemplo remove a entrada de URL especificada da Lista de Bloqueios/Permitir Locatários.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>Sintaxe de URL para a Lista de Bloqueios/Permitir Locatários

- Os endereços IP4v e IPv6 são permitidos, mas as portas TCP/UDP não.

- Extensões de nome de arquivo não são permitidas (por exemplo, test.pdf).

- Unicode não é suportado, mas Punycode é.

- Os nomes de host serão permitidos se todas as instruções a seguir são verdadeiras:

  - O nome do host contém um ponto.
  - Há pelo menos um caractere à esquerda do ponto.
  - Há pelo menos dois caracteres à direita do ponto.

  Por exemplo, `t.co` é permitido; `.com` ou não são `contoso.` permitidos.

- Os subcaminhos não estão implícitos.

  Por exemplo, `contoso.com` não inclui `contoso.com/a` .

- Caracteres curinga (*) são permitidos nos seguintes cenários:

  - Um caractere curinga esquerdo deve ser seguido por um ponto para especificar um subdomínio.

    Por exemplo, `*.contoso.com` é permitido; `*contoso.com` não é permitido.

  - Um curinga direito deve seguir uma barra (/) para especificar um caminho.

    Por exemplo, `contoso.com/*` é permitido; `contoso.com*` ou não são `contoso.com/ab*` permitidos.

  - Todos os subcaminhos não estão implícitos por um caractere curinga direito.

    Por exemplo, `contoso.com/*` não inclui `contoso.com/a` .

  - `*.com*` é inválido (não é um domínio que pode ser resolvido e o curinga direito não segue uma barra).

  - Caracteres curinga não são permitidos em endereços IP.

- O caractere til (~) está disponível nos seguintes cenários:

  - Um til à esquerda implica em um domínio e em todos os sub-domínios.

    Por `~contoso.com` exemplo, inclui `contoso.com` e `*.contoso.com` .

- Entradas de URL que contêm protocolos (por exemplo, , ou ) falharão, porque as entradas de URL se `http://` aplicam a todos os `https://` `ftp://` protocolos.

- Um nome de usuário ou senha não tem suporte ou é necessário.

- Aspas (' ou ") são caracteres inválidos.

- Uma URL deve incluir todos os redirecionamentos sempre que possível.

### <a name="url-entry-scenarios"></a>Cenários de entrada de URL

Entradas de URL válidas e seus resultados são descritos nas seções a seguir.

#### <a name="scenario-no-wildcards"></a>Cenário: sem caracteres curinga

**Entrada:**`contoso.com`

- **Permitir a combinação**: contoso.com

- **Allow not matched**:

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Block match**:

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Bloqueio não corresponder**: abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Cenário: curinga esquerdo (subdomínio)

**Entrada:**`*.contoso.com`

- **Permitir a match** e **a block match:**

  - www.contoso.com
  - xyz.abc.contoso.com

- **Allow not matched** and **Block not matched**:

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>Cenário: caractere curinga direito na parte superior do caminho

**Entrada:**`contoso.com/a/*`

- **Permitir a match** e **a block match:**

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **Allow not matched** and **Block not matched**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>Cenário: bloco esquerdo

**Entrada:**`~contoso.com`

- **Permitir a match** e **a block match:**

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Allow not matched** and **Block not matched**:

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Cenário: sufixo curinga direito

**Entrada:**`contoso.com/*`

- **Permitir a match** e **a block match:**

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Allow not matched** and **Block not matched**: contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Cenário: subdomínio de curinga esquerdo e sufixo curinga direito

**Entrada:**`*.contoso.com/*`

- **Permitir a match** e **a block match:**

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Allow not matched** and **Block not matched**: contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Cenário: til esquerdo e direito

**Entrada:**`~contoso.com~`

- **Permitir a match** e **a block match:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Allow not matched** and **Block not matched**:

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Cenário: endereço IP

**Entrada:**`1.2.3.4`

- **Permitir match** e **Block match:** 1.2.3.4

- **Allow not matched** and **Block not matched**:

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>Endereço IP com curinga direito

**Entrada:**`1.2.3.4/*`

- **Permitir a match** e **a block match:**

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Exemplos de entradas inválidas

As entradas a seguir são inválidas:

- **Valores de domínio ausentes ou inválidos:**

  - contoso
  - \*.contoso.\*
  - \*.com
  - \*.pdf

- **Caractere curinga no texto ou sem caracteres de espaçamento:**

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **Endereços IP com portas:**

  - contoso.com:443
  - abc.contoso.com:25

- **Caracteres curinga não descritivos:**

  - \*
  - \*.\*

- **Curingas intermediários:**

  - conto \* so.com
  - conto~so.com

- **Curingas duplos**

  - contoso.com/\*\*
  - contoso.com/\*/\*
