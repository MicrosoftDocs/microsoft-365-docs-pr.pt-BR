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
ms.openlocfilehash: 4228bb8abb70bbd96605a7d0f021a1a483e8715c
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929726"
---
# <a name="manage-the-tenant-allowblock-list"></a>Gerenciar a lista de Permissões/Bloqueios do Locatário

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> Os recursos descritos neste artigo estão em Visualização, estão sujeitos a alterações e não estão disponíveis em todas as organizações.  Se a sua organização não tiver os recursos de spoof conforme descrito neste artigo, consulte a experiência de gerenciamento de spoof mais antiga em Gerenciar envios com spoofed usando a política de inteligência de spoof e informações de inteligência de [spoof no EOP](walkthrough-spoof-intelligence-insight.md).
>
> Não é possível configurar **a** URL ou os itens de arquivo permitidos na Lista de Locatários Permitidos/Bloqueados no momento.

Em organizações Microsoft 365 com caixas de correio em organizações Exchange Online ou autônomas Proteção do Exchange Online (EOP) sem Exchange Online caixas de correio, talvez você não concorde com o veredito de filtragem do EOP. Por exemplo, uma boa mensagem pode ser marcada como ruim (um falso positivo) ou uma mensagem ruim pode ser permitida através (um falso negativo).

A Lista de locatários de Microsoft 365 portal do Defender oferece uma maneira de substituir manualmente os Microsoft 365 de filtragem. A Lista de Locatários Permite/Bloquear é usada durante o fluxo de emails e no momento dos cliques do usuário. Você pode especificar os seguintes tipos de substituições:

- URLs a bloquear.
- Arquivos a bloquear.
- Envios com spoofed para permitir ou bloquear. Se você substituir o veredito de permitir ou bloquear no insight de inteligência de spoof , o remetente [spoofed](learn-about-spoof-intelligence.md)se tornará uma entrada manual de permitir ou bloquear que só aparece na guia **Spoof** na Lista de Locatários De Permitir/Bloquear. Você também pode criar manualmente entradas de permitir ou bloquear para os envios de spoofed aqui antes que eles são detectados pela inteligência spoof.

Este artigo descreve como configurar entradas na Lista de Locatários Permitir/Bloquear no portal do defender do Microsoft 365 ou no PowerShell (Exchange Online PowerShell para organizações Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem Exchange Online caixas de correio).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com/>. Para ir diretamente para a página **Listas de Locatários/Bloqueios,** use <https://security.microsoft.com/tenantAllowBlockList> .

- Você especifica arquivos usando o valor de hash SHA256 do arquivo. Para encontrar o valor de hash SHA256 de um arquivo Windows, execute o seguinte comando em um Prompt de Comando:

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

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa de permissões em Exchange Online  antes de poder realizar os procedimentos neste artigo:
  - **URLs e arquivos**:
    - Para adicionar e remover valores da Lista de Permitir/Bloquear Locatários, você precisa ser membro dos grupos de função Gerenciamento da Organização ou Administrador **de** Segurança. 
    - Para acesso somente leitura à Lista de Locatários Permitir/Bloquear, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.
  - **Spoofing**: uma das seguintes combinações:
    - **Organization Management**
    - **Administrador de Segurança** <u>e</u> **Configuração somente exibição** ou **Gerenciamento de organização somente exibição.**

  Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).
  >
  > - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

## <a name="use-the-microsoft-365-defender-portal-to-create-block-url-entries-in-the-tenant-allowblock-list"></a>Use o portal Microsoft 365 Defender para criar entradas de URL de bloqueio na Lista de Locatários de Permitir/Bloquear

1. No portal Microsoft 365 Defender, vá para **Políticas** & regras de locatários de políticas de ameaça listas de \>  \> **locatários.**

2. Na página Lista de Locatários **Permitir/Bloquear,** verifique se a **guia URLs** está selecionada e clique em **Bloquear**

3. No **sobrevoo Bloquear URLs** que aparece, configure as seguintes configurações:

   - **Adicionar URLs para bloquear**: Insira uma URL por linha, até um máximo de 20. Para obter detalhes sobre a sintaxe para entradas de [URL,](#url-syntax-for-the-tenant-allowblock-list) consulte a sintaxe de URL para a seção Lista de Locatários/Bloqueios posteriormente neste artigo.

   - **Nunca expire**: Faça uma das seguintes etapas:

     - Verifique se a configuração está desligada ( Alternar ) e use a caixa Expira na caixa para especificar a data de ![ ](../../media/scc-toggle-off.png) expiração para as entradas. 

       ou

     - Mova a alternância para a direita para configurar as entradas para nunca expirar: ![Ativar](../../media/scc-toggle-on.png).

   - **Observação opcional**: insira texto descritivo para as entradas.

4. Quando terminar, clique em **Adicionar**.

## <a name="use-the-microsoft-365-defender-portal-to-create-block-file-entries-in-the-tenant-allowblock-list"></a>Use o Microsoft 365 do Defender para criar entradas de arquivo de bloqueio na Lista de Locatários Permitir/Bloquear

1. No portal Microsoft 365 Defender, acesse Políticas & **políticas de ameaça** Listas de \>  \> **locatários de locatários.**

2. Na página **Lista de Locatários Permitir/Bloquear,** selecione a guia **Arquivos** e clique em **Bloquear**.

3. No menu **Adicionar arquivos para bloquear o** sobrevoo que aparece, configure as seguintes configurações:

   - **Adicionar hashes de arquivo**: insira um valor de hash SHA256 por linha, até um máximo de 20.

   - **Nunca expire**: Faça uma das seguintes etapas:

     - Verifique se a configuração está desligada ( Alternar ) e use a caixa Expira na caixa para especificar a data de ![ ](../../media/scc-toggle-off.png) expiração para as entradas. 

     ou

     - Mova a alternância para a direita para configurar as entradas para nunca expirar: ![Ativar](../../media/scc-toggle-on.png).

   - **Observação opcional**: insira texto descritivo para as entradas.

4. Quando terminar, clique em **Adicionar**.

## <a name="use-the-microsoft-365-defender-portal-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Use o Microsoft 365 do Defender para criar entradas de remetentes com spoofed ou de permitir ou bloquear na Lista de Locatários Permitir/Bloquear

**Observações**:

- Somente a _combinação_ do usuário  com a infraestrutura de envio, conforme definido no par de domínios, é especificamente permitida ou bloqueada da spoofing.
- Quando você configura uma entrada de permitir ou bloquear para um par de domínios, as mensagens desse par de domínios não aparecem mais no insight de inteligência falsa.
- As entradas para os envios com spoofed nunca expiram.

1. No portal Microsoft 365 Defender, acesse Políticas & **políticas de ameaça** Listas de \>  \> **locatários de locatários.**

2. Na página **Lista de Locatários Permitir/Bloquear,** selecione a guia **Spoofing** e clique em **Adicionar**.

3. No **flyout Adicionar novos pares de** domínio que aparece, configure as seguintes configurações:

   - **Adicionar novos pares de domínio com caracteres curinga**: Insira um par de domínios por linha, até um máximo de 20. Para obter detalhes sobre a sintaxe para entradas de remetentes com spoofed, consulte a sintaxe de par de domínios para entradas de remetentes com [spoofed](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) na seção Lista de Locatários Permitir/Bloquear mais adiante neste artigo.

   - **Tipo de spoof**: selecione um dos seguintes valores:
     - **Interno**: o remetente spoofed está em um domínio que pertence à sua organização [(um domínio aceito](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).
     - **Externo**: o remetente spoofed está em um domínio externo.

   - **Ação**: Selecione **Permitir** ou **Bloquear**.

4. Quando terminar, clique em **Adicionar**.

## <a name="use-the-microsoft-365-defender-portal-to-view-entries-in-the-tenant-allowblock-list"></a>Use o Microsoft 365 do Defender para exibir entradas na Lista de Locatários Permitir/Bloquear

1. No portal Microsoft 365 Defender, acesse Políticas & **políticas de ameaça** Listas de \>  \> **locatários de locatários.**

2. Selecione a guia que você deseja. As colunas disponíveis dependem da guia selecionada:

   - **URLs**:
     - **Valor**: A URL.
     - **Ação**: o valor **Bloquear**.
     - **Data da última atualização**
     - **Data de expiração**
     - **Observação**

   - **Files**
     - **Valor**: o hash do arquivo.
     - **Ação**: o valor **Bloquear**.
     - **Data da última atualização**
     - **Data de expiração**
     - **Observação**

   - **Spoofing**
     - **Usuário com spoofed**
     - **Enviando infraestrutura**
     - **Tipo de spoof**: o valor **Interno** ou **Externo**.
     - **Ação**: o valor **Bloquear** ou **Permitir**.

   Você pode clicar em um título de coluna para classificar em ordem crescente ou decrescente.

   Você pode clicar **em Grupo** para agrupar os resultados. Os valores disponíveis dependem da guia selecionada:

   - **URLs**: Você pode agrupar os resultados por **Ação**.
   - **Arquivos**: Você pode agrupar os resultados por **Ação**.
   - **Domínios de remetente para bypass BCL**: **O** grupo não está disponível nesta guia.
   - **Spoofing**: Você pode agrupar os resultados por **ação** ou tipo **Spoof**.

   Clique **em Pesquisar**, insira todo ou parte de um valor e pressione ENTER para encontrar um valor específico. Quando terminar, clique em Limpar o **ícone de pesquisa** Limpar pesquisa ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .

   Clique **em Filtrar** para filtrar os resultados. Os valores disponíveis no flyout **Filter** que aparece dependem da guia selecionada:

   - **URLs**
     - **Action**
     - **Nunca expirar**
     - **Data da última atualização**
     - **Data de expiração**

   - **Files**
     - **Action**
     - **Nunca expirar**
     - **Data da última atualização**
     - **Data de expiração**

   - **Domínios de remetente para bypass BCL**
     - **Nunca expirar**
     - **Data da última atualização**
     - **Data de expiração**

   - **Spoofing**
     - **Action**
     - **Tipo de spoof**

   Quando terminar, clique em **Aplicar**. Para limpar os filtros existentes,  clique em **Filtrar** e, no sobrevoo Filtro que aparece, clique em **Limpar filtros**.

## <a name="use-the-microsoft-365-defender-portal-to-modify-entries-in-the-tenant-allowblock-list"></a>Use o Microsoft 365 do Defender para modificar entradas na Lista de Locatários de Permitir/Bloquear

1. No portal Microsoft 365 Defender, acesse Políticas & **políticas de ameaça** Listas de \>  \> **locatários de locatários.**

2. Selecione a guia que contém o tipo de entrada que você deseja modificar:
   - **URLs**
   - **Files**
   - **Domínios de remetente para bypass BCL**
   - **Spoofing**

3. Selecione a entrada que você deseja modificar e clique em **Editar** ![ ícone ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) editar. Os valores que você pode modificar no sobrevoo que aparece dependem da guia selecionada na etapa anterior:

   - **URLs**
     - **Nunca expira** e/ou data de expiração.
     - **Observação opcional**

   - **Files**
     - **Nunca expira** e/ou data de expiração.
     - **Observação opcional**

   - **Domínios de remetente para bypass BCL**
     - **Nunca expira** e/ou data de expiração.

   - **Spoofing**
     - **Ação**: você pode alterar o valor para **Permitir** ou **Bloquear**.

4. Quando concluir, clique em **Salvar**.

## <a name="use-the-microsoft-365-defender-portal-to-remove-entries-from-the-tenant-allowblock-list"></a>Usar o portal Microsoft 365 Defender para remover entradas da lista De locatários de permitir/bloquear

1. No portal Microsoft 365 Defender, acesse **Listas** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**

2. Selecione a guia que contém o tipo de entrada que você deseja remover:
   - **URLs**
   - **Files**
   - **Domínios de remetente para bypass BCL**
   - **Spoofing**

3. Selecione a entrada que você deseja remover e clique em **Excluir** ![ ícone ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .

4. Na caixa de diálogo de aviso exibida, clique em **Excluir**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Use Exchange Online PowerShell ou EOP PowerShell autônomo para configurar a lista de locatários de permitir/bloquear

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a>Use o PowerShell para adicionar entradas de arquivo de bloqueio ou URL à Lista de Locatários De Permitir/Bloquear

Para adicionar entradas de arquivo de bloqueio ou URL na Lista de Locatários de Permitir/Bloquear, use a seguinte sintaxe:

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

Este exemplo adiciona uma entrada de arquivo de bloqueio para os arquivos especificados que nunca expiram.

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

Este exemplo adiciona uma entrada de URL de bloco para contoso.com e todos os subdomas (por exemplo, contoso.com, www.contoso.com e xyz.abc.contoso.com). Como não usamos os parâmetros ExpirationDate ou NoExpiration, a entrada expira após 30 dias.

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a>Use o PowerShell para adicionar entradas de remetentes com spoofed ou de autorização ou bloqueio à Lista de Locatários De permitir/Bloquear

Para adicionar entradas de remetentes com spoofed na Lista de Locatários De permitir/bloquear, use a seguinte sintaxe:

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a>Usar o PowerShell para exibir entradas de arquivo de bloqueio ou URL na Lista de Locatários Permitir/Bloquear

Para exibir entradas de arquivo de bloqueio ou URL na Lista de Locatários Permitir/Bloquear, use a seguinte sintaxe:

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

Este exemplo retorna informações para o valor de hash de arquivo especificado.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

Este exemplo retorna todas as URLs bloqueadas.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Use o PowerShell para exibir as entradas de remetentes com spoofed ou de permitir ou bloquear na Lista de Locatários De permitir/Bloquear

Para exibir entradas de remetentes com spoofed na Lista de Locatários Permitir/Bloquear, use a seguinte sintaxe:

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

Este exemplo retorna todas as entradas de remetentes com spoofed na Lista de Locatários de Permitir/Bloquear.

```powershell
Get-TenantAllowBlockListSpoofItems
```

Este exemplo retorna todas as entradas de remetentes com spoofed que são internas.

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

Este exemplo retorna todas as entradas de remetentes com spoofed bloqueados que são externas.

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a>Usar o PowerShell para modificar as entradas de arquivo de bloqueio e URL na Lista de Locatários Permitir/Bloquear

Para modificar entradas de arquivo de bloqueio e URL na Lista de Locatários de Permitir/Bloquear, use a seguinte sintaxe:

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

Este exemplo altera a data de expiração da entrada da URL de bloco especificada.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Use o PowerShell para modificar as entradas de remetentes com spoofed ou de permitir ou bloquear na Lista de Locatários de Permitir/Bloquear

Para modificar entradas de remetentes com spoofed ou de permitir ou bloquear na Lista de Locatários De permitir/Bloquear, use a seguinte sintaxe:

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

Este exemplo altera a entrada de remetentes com spoofed de permitir o bloqueio.

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a>Use o PowerShell para remover entradas de URL ou arquivo da Lista de Locatários Permitir/Bloquear

Para remover entradas de arquivo e URL da Lista de Locatários Permitir/Bloquear, use a seguinte sintaxe:

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

Este exemplo remove a entrada de URL de bloco especificada da Lista de Locatários de Bloqueio/Autorização.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a>Use o PowerShell para remover entradas de remetentes com spoofed ou de permitir ou bloquear da Lista de Locatários De permitir/Bloquear

Para remover as entradas de remetente de spoof ou de permitir ou bloquear da Lista de Locatários de Permitir/Bloquear, use a seguinte sintaxe:

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).

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

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Sintaxe de par de domínios para entradas de remetentes com spoofed na Lista de Locatários De permitir/bloquear

Um par de domínios para um remetente com spoofed na Lista de Locatários de Permitir/Bloquear usa a seguinte sintaxe: `<Spoofed user>, <Sending infrastructure>` .

- **Usuário com spoofed**: esse valor envolve o endereço de email do usuário que é exibido na caixa **De** em clientes de email. Esse endereço também é conhecido como `5322.From` endereço. Os valores válidos incluem:
  - Um endereço de email individual (por exemplo, chris@contoso.com).
  - Um domínio de email (por exemplo, contoso.com).
  - O caractere curinga (por exemplo, \* ).

- **Infraestrutura de** envio : esse valor indica a origem das mensagens do usuário espouado. Os valores válidos incluem:
  - O domínio encontrado em um registro DNS reverso (registro PTR) do endereço IP do servidor de email de origem (por exemplo, fabrikam.com).
  - Se o endereço IP de origem não tiver registro PTR, a infraestrutura de envio será identificada como \<source IP\> /24 (por exemplo, 192.168.100.100/24).

Aqui estão alguns exemplos de pares de domínio válidos para identificar os envios com spoofed:

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

O número máximo de entradas de remetentes com spoofed é 1000. 

Adicionar um par de domínios  só permite ou bloqueia a combinação do usuário e da *infraestrutura* de envio. Ele não permite emails do usuário com spoofed de qualquer origem, nem permite emails da fonte de infraestrutura de envio para qualquer usuário com spoofed. 

Por exemplo, você adiciona uma entrada de autorização para o seguinte par de domínio:

- **Domínio**: gmail.com
- **Infraestrutura**: tms.mx.com

Somente as mensagens desse domínio *e o* par de infraestrutura de envio podem ser falsas. Outros senders que tentam gmail.com não são permitidos. As mensagens de senders em outros domínios provenientes tms.mx.com são verificadas por inteligência falsa.
