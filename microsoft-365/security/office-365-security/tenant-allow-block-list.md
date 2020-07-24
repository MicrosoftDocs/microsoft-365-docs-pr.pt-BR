---
title: Gerenciar seus arquivos e URLs permitidos e bloqueados na lista de permissões/bloqueios de locatários
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
ms.collection:
- M365-security-compliance
description: Os administradores podem saber como configurar as entradas de URL e de arquivo na lista de permissões/bloqueios de locatários no centro de conformidade de & de segurança.
ms.openlocfilehash: db34abf28b5ead8106eb0b1447052d63072b2da3
ms.sourcegitcommit: 41eb898143286755cd36df9f7e769de641263d73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "45391561"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a>Gerenciar URLs e arquivos na Lista de Permissões/Bloqueios de Locatários

> [!NOTE]
> Os recursos descritos neste tópico estão em visualização, estão sujeitos a alterações e não estão disponíveis em todas as organizações.

Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, você pode discordar do veredicto de filtragem EOP. Por exemplo, uma boa mensagem pode ser marcada como ruim (falso positivo) ou uma mensagem inválida pode ser permitida por meio de (falso negativo).

A lista de permissões/bloqueios de locatários no centro de conformidade do & de segurança oferece uma maneira de substituir manualmente o Microsoft 365 Filtering verdicts. A lista de permissões/bloqueios de locatários é usada durante o fluxo de emails e no momento em que o usuário clica. Você pode especificar URLs e arquivos para permitir ou bloquear na lista de permissões/bloqueios de locatários.

Este tópico descreve como configurar entradas na lista de permissões/bloqueios de locatário no centro de conformidade & segurança ou no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com caixas de correio no Exchange Online; autônomo do EOP PowerShell para organizações sem caixas de correio do Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a página **lista de permissões/bloqueios de locatários** , use <https://protection.office.com/tenantAllowBlockList> .

- Você especifica arquivos usando o valor de hash SHA256 do arquivo. Para localizar o valor de hash SHA256 de um arquivo no Windows, execute o seguinte comando em um prompt de comando:

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  Um valor de exemplo é `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` . Os valores de hash perceptual (pHash) não são permitidos.

- Os valores de URL disponíveis são descritos na [sintaxe da URL para a seção lista de permissões/bloqueios de locatário](#url-syntax-for-the-tenant-allowblock-list) mais adiante neste tópico.

- A lista de permissões/bloqueios de locatários permite um máximo de 500 entradas para URLs e 500 entradas para hashes de arquivo.

- Uma entrada deve estar ativa em 15 minutos.

- As entradas de bloco têm precedência sobre as entradas de permissão.

- Por padrão, as entradas na lista de permissões/bloqueios de locatários expirarão após 30 dias. Você pode especificar uma data ou defini-las para nunca expirar.

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa ter permissões atribuídas antes de poder executar os procedimentos neste tópico:

  - Para adicionar e remover valores da lista de permissões/bloqueios de locatário, você precisa ser membro de um dos seguintes grupos de função:

    - **Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).
    - **Gerenciamento de organizações** ou **Gerenciamento de higiene** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Para acesso somente leitura à lista de permissões/bloqueios de locatário, você precisa ser membro de um dos seguintes grupos de função:

    - **Leitor de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).
    - **Gerenciamento da organização Somente visualização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>Usar o centro de conformidade de & de segurança para criar entradas de URL na lista de permissões/bloqueios de locatários

Para obter detalhes sobre a sintaxe das entradas de URL, consulte a sintaxe da URL da seção [lista de permissões/bloqueios de locatário](#url-syntax-for-the-tenant-allowblock-list) mais adiante neste tópico.

1. No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **listas de permissões/bloqueios de locatários**de política de gerenciamento de ameaça.

2. Na página **lista de permissões/bloqueios de locatários** , verifique se a guia **URLs** está selecionada e clique em **Adicionar**

3. No submenu **adicionar novas URLs** que aparece, defina as seguintes configurações:

   - **Adicionar URLs com curingas**: Insira uma URL por linha, até um máximo de 20.

   - **Bloquear/permitir**: selecione se você deseja **permitir** ou **Bloquear** as URLs especificadas.

   - **Nunca expira**: execute uma das seguintes etapas:

     - Verifique se a configuração está desativada (desative ![ ](../../media/scc-toggle-off.png) ) e use a caixa **expira em** para especificar a data de vencimento das entradas.

     ou

     - Mova a opção para a direita para configurar as entradas para nunca expirar: ![Ativar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **Observação opcional**: insira texto descritivo para as entradas.

4. Quando tiver concluído, clique em **Adicionar**.

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a>Usar o centro de conformidade de & de segurança para criar entradas de arquivo na lista de permissões/bloqueios de locatários

1. No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **listas de permissões/bloqueios de locatários**de política de gerenciamento de ameaça.

2. Na página **lista de permissões/bloqueios de locatários** , selecione **arquivos** e clique em **Adicionar**.

3. No submenu **Adicionar novos arquivos** que aparece, defina as seguintes configurações:

   - **Adicionar hashes de arquivo**: Insira um valor de hash SHA256 por linha, até um máximo de 20.

   - **Bloquear/permitir**: selecione se você deseja **permitir** ou **Bloquear** os arquivos especificados.

   - **Nunca expira**: execute uma das seguintes etapas:

     - Verifique se a configuração está desativada (desative ![ ](../../media/scc-toggle-off.png) ) e use a caixa **expira em** para especificar a data de vencimento das entradas.

     ou

     - Mova a opção para a direita para configurar as entradas para nunca expirar: ![Ativar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **Observação opcional**: insira texto descritivo para as entradas.

4. Quando tiver concluído, clique em **Adicionar**.

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a>Use o centro de conformidade de & de segurança para exibir entradas de URL e de arquivo na lista de permissões/bloqueios de locatários

1. No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **listas de permissões/bloqueios de locatários**de política de gerenciamento de ameaça.

2. Selecione a guia **URLs** ou a guia **arquivos** .

Clique nos seguintes títulos de coluna para classificar em ordem crescente ou decrescente:

- **Valor**: a URL ou o hash do arquivo.
- **Ação**: **Bloquear** ou **permitir**.
- **Data da última atualização**
- **Data de vencimento**
- **Observação**

Clique em **Agrupar** para agrupar as entradas **por ação** (**Bloquear** ou **permitir**) ou **nenhum**.

Clique em **Pesquisar**, digite todo ou parte de um valor de URL ou de arquivo e pressione ENTER para localizar um valor específico. Quando tiver terminado, clique em **limpar** o ![ ícone pesquisa limpar pesquisa ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .

Clique em **filtro**. No submenu de **filtro** que aparece, configure qualquer uma das seguintes configurações:

- **Ação**: selecione **permitir**, **Bloquear** ou ambos.

- **Nunca expirar**: selecione Desativado (desativar ![ ](../../media/scc-toggle-off.png) ) ou ativado ( ![ Ativar/desativar ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).

- **Última atualização**: selecione uma data de início (**de**), uma data de término (**para**) ou ambas.

- **Data de validade**: selecione uma data de início (**de**), uma data de término (**para**) ou ambas.

Quando tiver concluído, clique em **aplicar**.

Para limpar filtros existentes, clique em **Filtrar**e, no submenu de **filtro** que aparece, clique em **limpar filtros**.

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a>Use o centro de conformidade de & de segurança para modificar as entradas de URL e de arquivo na lista de permissões/bloqueios de locatários

Você não pode modificar a URL ou o valor do arquivo propriamente dito. Em vez disso, você precisa excluir a entrada e recriá-la.

1. No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **listas de permissões/bloqueios de locatários**de política de gerenciamento de ameaça.

2. Selecione a guia **URLs** ou a guia **arquivos** .

3. Selecione a entrada que você deseja modificar e clique em **Editar** ![ ícone de edição ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .

4. No submenu exibido, defina as seguintes configurações:

   - **Bloquear/permitir**: selecione **permitir** ou **Bloquear**.

   - **Nunca expira**: execute uma das seguintes etapas:

     - Verifique se a configuração está desativada (desative ![ ](../../media/scc-toggle-off.png) ) e use a caixa **expira em** para especificar a data de vencimento da entrada.

     ou

     - Mova a opção para a direita para configurar a entrada para nunca expirar: ![Ativar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **Observação opcional**: insira texto descritivo para a entrada.

5. Quando concluir, clique em **Salvar**.

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a>Use o centro de conformidade de & de segurança para remover entradas de URL e arquivos da lista de permissões/bloqueios de locatários

1. No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **listas de permissões/bloqueios de locatários**de política de gerenciamento de ameaça.

2. Selecione a guia **URLs** ou a guia **arquivos** .

3. Selecione a entrada que você deseja remover e clique em **excluir** ![ excluir ícone ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .

4. Na caixa de diálogo de aviso que aparece, clique em **excluir**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Usar o PowerShell do Exchange Online ou o PowerShell do EOP para configurar a lista de permissões/bloqueios de locatários

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a>Usar o PowerShell para adicionar entradas de URL e de arquivo na lista de permissões/bloqueios de locatários

Para adicionar entradas de URL e de arquivo na lista de permissões/bloqueios de locatários, use a seguinte sintaxe:

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

Este exemplo adiciona uma entrada de bloco de URL para contoso.com e todos os subdomínios (por exemplo, contoso.com, www.contoso.com e xyz.abc.contoso.com). Como não usamos os parâmetros ExpirationDate ou noexpiration, a entrada expira após 30 dias.

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

Este exemplo adiciona uma entrada de permissão de arquivo para os arquivos especificados que nunca expiram.

Para informações detalhadas de sintaxes e de parâmetros, consulte [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a>Use o PowerShell para exibir as entradas de arquivo e URL na lista de permissões/bloqueios de locatários

Para exibir as entradas de arquivo e URL na lista de permissões/bloqueios de locatários, use a seguinte sintaxe:

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

Este exemplo retorna todas as URLs bloqueadas.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

Este exemplo retorna informações para o valor de hash do arquivo especificado.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a>Usar o PowerShell para modificar as entradas de arquivo e URL na lista de permissões/bloqueios de locatários

Você não pode modificar a URL ou o valor do arquivo propriamente dito. Em vez disso, você precisa excluir a entrada e recriá-la.

Para modificar as entradas de URL e de arquivo na lista de permissões/bloqueios de locatários, use a seguinte sintaxe:

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

Este exemplo altera a data de vencimento da entrada especificada.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a>Use o PowerShell para remover as entradas de arquivo e URL da lista de permissões/bloqueios de locatários

Para remover as entradas de arquivo e URL da lista de permissões/bloqueios de locatários, use a seguinte sintaxe:

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

Este exemplo remove a entrada de URL especificada da lista de permissões/bloqueios de locatário.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>Sintaxe da URL para a lista de permissões/bloqueios de locatário

- Os endereços IPv6 e IP4v são permitidos, mas as portas TCP/UDP não são.

- Extensões de nome de arquivo não são permitidas (por exemplo, test.pdf).

- Unicode não é suportado, mas Punycode é.

- Os nomes de host são permitidos se todas as instruções a seguir forem verdadeiras:

  - O nome do host contém um ponto.
  - Há pelo menos um caractere à esquerda do ponto.
  - Há pelo menos dois caracteres à direita do ponto.

  Por exemplo, `t.co` é permitido; `.com` ou `contoso.` não são permitidos.

- Os subcaminhos não são inferidos.

  Por exemplo, não `contoso.com` inclui `contoso.com/a` .

- Caracteres curinga (*) são permitidos nos seguintes cenários:

  - Um caractere curinga à esquerda deve ser seguido por um ponto para especificar um subdomínio.

    Por exemplo, `*.contoso.com` é permitido; `*contoso.com` não é permitido.

  - Um caractere curinga à direita deve seguir uma barra (/) para especificar um caminho.

    Por exemplo, `contoso.com/*` é permitido; `contoso.com*` ou `contoso.com/ab*` não são permitidos.

  - Todos os subcaminhos não são inferidos por um caractere curinga correto.

    Por exemplo, não `contoso.com/*` inclui `contoso.com/a` .

  - `*.com*`é inválido (não é um domínio resolvível e o caractere curinga correto não segue uma barra).

  - Curingas não são permitidos em endereços IP.

- O caractere til (~) está disponível nos seguintes cenários:

  - Um til esquerdo implica um domínio e todos os subdomínios.

    Por exemplo `~contoso.com` inclui `contoso.com` e `*.contoso.com` .

- As entradas de URL que contêm protocolos (por exemplo,, `http://` `https://` ou `ftp://` ) falharão, porque as entradas de URL se aplicam a todos os protocolos.

- Um nome de usuário ou senha não são suportados ou necessários.

- Aspas ("ou") são caracteres inválidos.

- Uma URL deve incluir todos os redirecionamentos onde for possível.

### <a name="url-entry-scenarios"></a>Cenários de entrada de URL

Entradas de URL válidas e seus resultados são descritos nas seções a seguir.

#### <a name="scenario-no-wildcards"></a>Cenário: sem curingas

**Entrada**:`contoso.com`

- **Permitir correspondência**: contoso.com

- **Permitir não correspondente**:

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www. contoso. com/q = a@contoso. com
  
- **Correspondência de bloco**:

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www. contoso. com/q = a@contoso. com

- **Bloquear não correspondente**: ABC-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Cenário: curinga esquerdo (subdomínio)

**Entrada**:`*.contoso.com`

- **Permitir** correspondência de correspondência e **bloqueio**:

  - www.contoso.com
  - xyz.abc.contoso.com

- **Permitir não correspondente** e **Bloquear não correspondente**:

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a>Cenário: caractere curinga à direita na parte superior do caminho

**Entrada**:`contoso.com/a/*`

- **Permitir** correspondência de correspondência e **bloqueio**:

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso. com/a/? q = joe@t. com

- **Permitir não correspondente** e **Bloquear não correspondente**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www. contoso. com/q = a@contoso. com
  
#### <a name="scenario-left-tilde"></a>Cenário: til esquerdo

**Entrada**:`~contoso.com`

- **Permitir** correspondência de correspondência e **bloqueio**:

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Permitir não correspondente** e **Bloquear não correspondente**:

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Cenário: sufixo curinga à direita

**Entrada**:`contoso.com/*`

- **Permitir** correspondência de correspondência e **bloqueio**:

  - contoso. com/? q = whatever@fabrikam. com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Permitir não correspondente** e **Bloquear não correspondente**: contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Cenário: subdomínio curinga esquerdo e sufixo curinga direito

**Entrada**:`*.contoso.com/*`

- **Permitir** correspondência de correspondência e **bloqueio**:

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Permitir não correspondente** e **Bloquear não correspondente**: contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Cenário: til esquerdo e direito

**Entrada**:`~contoso.com~`

- **Permitir** correspondência de correspondência e **bloqueio**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Permitir não correspondente** e **Bloquear não correspondente**:

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Cenário: endereço IP

**Entrada**:`1.2.3.4`

- **Permitir** correspondência de correspondência e **bloqueio**: 1.2.3.4

- **Permitir não correspondente** e **Bloquear não correspondente**:

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>Endereço IP com caractere curinga direito

**Entrada**:`1.2.3.4/*`

- **Permitir** correspondência de correspondência e **bloqueio**:

  - 1.2.3.4/b
  - 1.2.3.4/Baaaa

### <a name="examples-of-invalid-entries"></a>Exemplos de entradas inválidas

As entradas a seguir são inválidas:

- **Valores de domínio ausentes ou inválidos**:

  - contoso
  - \*contoso.\*
  - \*. com
  - \*.pdf

- **Curinga no texto ou sem caracteres de espaçamento**:

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **Endereços IP com portas**:

  - contoso.com:443
  - abc.contoso.com:25

- **Curingas não descritivos**:

  - \*
  - \*.\*

- **Curingas médios**:

  - conta \* so.com
  - cont ~ so. com

- **Curingas duplos**

  - contoso.com/\*\*
  - contoso.com/\*/\*
