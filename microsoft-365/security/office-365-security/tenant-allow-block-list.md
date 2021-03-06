---
title: Gerenciar suas autorizações e bloqueios na Lista de Locatários Permitir/Bloquear
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
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a configurar as permites e os bloqueios na Lista de Locatários de Permitir/Bloquear no portal de Segurança.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 20e460f4e93f7b87faaead8b87ba561224e38938
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515203"
---
# <a name="manage-the-tenant-allowblock-list"></a>Gerenciar a lista de Permissões/Bloqueios do Locatário

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> Os recursos descritos neste artigo estão em Visualização, estão sujeitos a alterações e não estão disponíveis em todas as organizações.
>
> Não é possível **configurar itens** permitidos na Lista de Locatários Permitidos/Bloqueados no momento.

Em organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, você pode discordar do veredito de filtragem do EOP. Por exemplo, uma boa mensagem pode ser marcada como ruim (um falso positivo) ou uma mensagem ruim pode ser permitida através (um falso negativo).

A Lista de Permitir/Bloquear Locatários no Centro de Conformidade & segurança oferece uma maneira de substituir manualmente os vereditos de filtragem do Microsoft 365. A Lista de Locatários Permite/Bloquear é usada durante o fluxo de emails e no momento dos cliques do usuário. Você pode especificar URLs ou arquivos a ser sempre bloqueados.

Este artigo descreve como configurar entradas na Lista de Locatários Permitir/Bloquear no Centro de Conformidade de Segurança & ou no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a página **Lista de Locatários Permitir/Bloquear,** use <https://protection.office.com/tenantAllowBlockList> .

- Você especifica arquivos usando o valor de hash SHA256 do arquivo. Para encontrar o valor de hash SHA256 de um arquivo no Windows, execute o seguinte comando em um Prompt de Comando:

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  Um valor de exemplo é `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` . Os valores de hash perceptual (pHash) não são suportados.

- Os valores de URL disponíveis são descritos na sintaxe de URL da seção [Lista de Locatários/Bloqueios](#url-syntax-for-the-tenant-allowblock-list) posteriormente neste artigo.

- A Lista de Permitir/Bloquear Locatários permite no máximo 500 entradas para URLs e 500 entradas para hashes de arquivo.

- O número máximo de caracteres para cada entrada é:
  - Hashes de arquivo = 64
  - URL = 250

- Uma entrada deve estar ativa dentro de 30 minutos.

- Por padrão, as entradas na Lista de Locatários Permitir/Bloquear expiram após 30 dias. Você pode especificar uma data ou defini-la para nunca expirar.

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa de permissões em **Exchange Online** antes de poder realizar os procedimentos neste artigo:
  - Para adicionar e remover valores da Lista de Permitir/Bloquear Locatários, você precisa ser membro dos grupos de função Gerenciamento da Organização ou Administrador **de** Segurança. 
  - Para acesso somente leitura à Lista de Locatários Permitir/Bloquear, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.

  Para obter mais informações, confira [Permissões no Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  > 
  > - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).
  > - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>Use o Centro de Conformidade & segurança para criar entradas de URL na Lista de Locatários Permitir/Bloquear

Para obter detalhes sobre a sintaxe para entradas de [URL,](#url-syntax-for-the-tenant-allowblock-list) consulte a sintaxe de URL para a seção Lista de Locatários/Bloqueios posteriormente neste artigo.

1. No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**

2. Na página Lista de Locatários **Permitir/Bloquear,** verifique se a **guia URLs** está selecionada e clique em **Bloquear**

3. No **sobrevoo Bloquear URLs** que aparece, configure as seguintes configurações:

   - **Adicionar URLs para bloquear**: Insira uma URL por linha, até um máximo de 20.

   - **Nunca expire**: Faça uma das seguintes etapas:

     - Verifique se a configuração está desligada ( Alternar ) e use a caixa Expira na caixa para especificar a data de ![ ](../../media/scc-toggle-off.png) expiração para as entradas. 

       or

     - Mova a alternância para a direita para configurar as entradas para nunca expirar: ![Ativar](../../media/scc-toggle-on.png).

   - **Observação opcional**: insira texto descritivo para as entradas.

4. Quando terminar, clique em **Adicionar**.

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a>Use o Centro de Conformidade & segurança para criar entradas de arquivo na Lista de Locatários Permitir/Bloquear

1. No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**

2. Na página **Lista de Locatários Permitir/Bloquear,** selecione **Arquivos** e clique em **Bloquear**.

3. No menu **Adicionar arquivos para bloquear o** sobrevoo que aparece, configure as seguintes configurações:

   - **Adicionar hashes de arquivo**: insira um valor de hash SHA256 por linha, até um máximo de 20.

   - **Nunca expire**: Faça uma das seguintes etapas:

     - Verifique se a configuração está desligada ( Alternar ) e use a caixa Expira na caixa para especificar a data de ![ ](../../media/scc-toggle-off.png) expiração para as entradas. 

     or

     - Mova a alternância para a direita para configurar as entradas para nunca expirar: ![Ativar](../../media/scc-toggle-on.png).

   - **Observação opcional**: insira texto descritivo para as entradas.

4. Quando terminar, clique em **Adicionar**.

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>Use o Centro de Conformidade & segurança para exibir entradas na Lista de Locatários Permitir/Bloquear

1. No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**

2. Selecione a **guia URLs** ou a **guia Arquivos.**

Clique nos seguintes títulos de coluna para classificar em ordem crescente ou decrescente:

- **Valor**: a URL ou o hash de arquivo.
- **Data da última atualização**
- **Data de expiração**
- **Observação**

Clique **em Pesquisar**, insira todo ou parte de um valor e pressione ENTER para encontrar um valor específico. Quando terminar, clique em Limpar o **ícone de pesquisa** Limpar pesquisa ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .

Clique **em Filtrar**. No flyout **Filter** exibido, configure qualquer uma das seguintes configurações:

- **Nunca expire**: selecione off: ![ Alternar ](../../media/scc-toggle-off.png) ou desligar: ![ Alternar em ](../../media/scc-toggle-on.png) .

- **Last updated**: Select a start date (**From**), an end date (**To**) or both.

- **Data de** expiração : selecione uma data de início (**De**), uma data de término (**Para**) ou ambos.

Quando terminar, clique em **Aplicar**.

Para limpar os filtros existentes,  clique em **Filtrar** e, no sobrevoo Filtro que aparece, clique em **Limpar filtros**.

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a>Use o Centro de Conformidade & segurança para modificar entradas de bloco na lista De permitir/bloquear locatários

Não é possível modificar a URL ou os valores de arquivo bloqueados existentes em uma entrada. Para modificar esses valores, você precisa excluir e recriar a entrada.

1. No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**

2. Selecione a **guia URLs** ou a **guia Arquivos.**

3. Selecione a entrada de bloco que você deseja modificar e clique em **Editar** ![ ícone editar ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .

4. No sobrevoo exibido, configure as seguintes configurações:

   - **Nunca expire**: Faça uma das seguintes etapas:

     - Verifique se a configuração está desligada ( Alternar ) e use a caixa Expira na caixa para especificar a data ![ ](../../media/scc-toggle-off.png) de expiração da entrada. 

       or

     - Mova a alternância para a direita para configurar a entrada para nunca expirar: ![Ativar](../../media/scc-toggle-on.png).

   - **Observação opcional**: insira texto descritivo para a entrada.

5. Quando concluir, clique em **Salvar**.

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a>Use o Centro de Conformidade & segurança para remover entradas de bloqueio da lista De permitir/bloquear locatários

1. No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**

2. Selecione a **guia URLs** ou a **guia Arquivos.**

3. Selecione a entrada de bloco que você deseja remover e clique em **Excluir** ![ ícone ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) Excluir.

4. Na caixa de diálogo de aviso exibida, clique em **Excluir**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Use o PowerShell do Exchange Online ou o EOP PowerShell autônomo para configurar a lista de locatários de permitir/bloquear

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a>Usar o PowerShell para adicionar entradas de bloco à lista de locatários permitir/bloquear

Para adicionar entradas de bloco na Lista de Locatários Permitir/Bloquear, use a seguinte sintaxe:

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

Este exemplo adiciona uma entrada de URL de bloco para contoso.com e todos os subdomas (por exemplo, contoso.com, www.contoso.com e xyz.abc.contoso.com). Como não usamos os parâmetros ExpirationDate ou NoExpiration, a entrada expira após 30 dias.

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

Este exemplo adiciona uma entrada de arquivo de bloqueio para os arquivos especificados que nunca expiram.

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>Usar o PowerShell para exibir entradas na Lista de Locatários Permitir/Bloquear

Para exibir entradas na Lista de Locatários Permitir/Bloquear, use a seguinte sintaxe:

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

Este exemplo retorna todas as URLs bloqueadas.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

Este exemplo retorna informações para o valor de hash de arquivo especificado.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a>Usar o PowerShell para modificar entradas de bloco na Lista de Locatários Permitir/Bloquear

Não é possível modificar a URL ou os valores de arquivo existentes em uma entrada de bloco. Para modificar esses valores, você precisa excluir e recriar a entrada.

Para modificar entradas de bloco na Lista de Locatários Permitir/Bloquear, use a seguinte sintaxe:

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

Este exemplo altera a data de expiração da entrada de bloco especificada.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a>Usar o PowerShell para remover entradas de bloco da lista De locatários permitir/bloquear

Para remover entradas de bloco da Lista de Locatários de Permitir/Bloquear, use a seguinte sintaxe:

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

Este exemplo remove a entrada de URL de bloco especificada da Lista de Locatários de Bloqueio/Autorização.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>Sintaxe de URL para a Lista de Locatários de Permitir/Bloquear

- Os endereços IP4v e IPv6 são permitidos, mas as portas TCP/UDP não são.

- Extensões de nome de arquivo não são permitidas (por exemplo, test.pdf).

- Unicode não tem suporte, mas Punycode é.

- Os nomes de host são permitidos se todas as instruções a seguir são verdadeiras:
  - O nomedo host contém um ponto.
  - Há pelo menos um caractere à esquerda do período.
  - Há pelo menos dois caracteres à direita do ponto.

  Por exemplo, `t.co` é permitido; `.com` ou não são `contoso.` permitidos.

- Subpaths não estão implícitos.

  Por exemplo, `contoso.com` não inclui `contoso.com/a` .

- Os caracteres curinga (*) são permitidos nos seguintes cenários:

  - Um curinga esquerdo deve ser seguido por um ponto para especificar um subdomínio.

    Por exemplo, `*.contoso.com` é permitido; `*contoso.com` não é permitido.

  - Um curinga direito deve seguir uma barra (/) para especificar um caminho.

    Por exemplo, `contoso.com/*` é permitido; `contoso.com*` ou não são `contoso.com/ab*` permitidos.

  - Todos os subcamadas não estão implícitos por um caractere curinga direito.

    Por exemplo, `contoso.com/*` não inclui `contoso.com/a` .

  - `*.com*` é inválido (não é um domínio resolvêvel e o caractere curinga direito não segue uma barra de encaminhamento).

  - Caracteres curinga não são permitidos em endereços IP.

- O caractere tilde (~) está disponível nos seguintes cenários:

  - Um bloco esquerdo implica um domínio e todos os subdomas.

    Por `~contoso.com` exemplo, inclui `contoso.com` e `*.contoso.com` .

- As entradas de URL que contêm protocolos (por exemplo, , , ou ) falharão, pois as entradas de URL se `http://` aplicam a todos os `https://` `ftp://` protocolos.

- Um nome de usuário ou senha não é suportado ou necessário.

- Aspas (' ou ") são caracteres inválidos.

- Uma URL deve incluir todos os redirecionamentos sempre que possível.

### <a name="url-entry-scenarios"></a>Cenários de entrada de URL

Entradas de URL válidas e seus resultados são descritos nas seções a seguir.

#### <a name="scenario-no-wildcards"></a>Cenário: sem caracteres curinga

**Entrada**: `contoso.com`

- **Permitir match**: contoso.com

- **Permitir não corresponder**:

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

- **Bloquear não corresponder :** abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Cenário: curinga esquerdo (subdomínio)

**Entrada**: `*.contoso.com`

- **Permitir match** e **Block match**:

  - www.contoso.com
  - xyz.abc.contoso.com

- **Permitir não corresponder e** **Bloquear não corresponder**:

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>Cenário: curinga direito na parte superior do caminho

**Entrada**: `contoso.com/a/*`

- **Permitir match** e **Block match**:

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **Permitir não corresponder e** **Bloquear não corresponder**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>Cenário: bloco esquerdo

**Entrada**: `~contoso.com`

- **Permitir match** e **Block match**:

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Permitir não corresponder e** **Bloquear não corresponder**:

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Cenário: sufixo curinga correto

**Entrada**: `contoso.com/*`

- **Permitir match** e **Block match**:

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Permitir não corresponder e** **Bloquear não corresponder**: contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Cenário: subdomínio curinga esquerdo e sufixo curinga direito

**Entrada**: `*.contoso.com/*`

- **Permitir match** e **Block match**:

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Permitir não corresponder e** **Bloquear não corresponder**: contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Cenário: bloco esquerdo e direito

**Entrada**: `~contoso.com~`

- **Permitir match** e **Block match**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Permitir não corresponder e** **Bloquear não corresponder**:

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Cenário: endereço IP

**Entrada**: `1.2.3.4`

- **Permitir match** e **Block match**: 1.2.3.4

- **Permitir não corresponder e** **Bloquear não corresponder**:

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>Endereço IP com curinga direito

**Entrada**: `1.2.3.4/*`

- **Permitir match** e **Block match**:

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Exemplos de entradas inválidas

As seguintes entradas são inválidas:

- **Valores de domínio ausentes ou inválidos:**

  - contoso
  - \*.contoso.\*
  - \*.com
  - \*.pdf

- **Caractere curinga em texto ou sem caracteres de espaçamento**:

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **Endereços IP com portas**:

  - contoso.com:443
  - abc.contoso.com:25

- **Caracteres curinga não descritivos:**

  - \*
  - \*.\*

- **Caracteres curinga intermediários**:

  - conto \* so.com
  - conto~so.com

- **Caracteres curinga duplos**

  - contoso.com/\*\*
  - contoso.com/\*/\*
