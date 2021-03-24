---
title: Definir configurações globais para configurações de Links Seguros no Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a exibir e configurar configurações globais (a lista "Bloquear as URLs a seguir" e a proteção para aplicativos do Office 365) para Links Seguros no Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 390177a24648cf860a78ab831d5dfe334b2c9590
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053690"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Configurar configurações globais para Links Seguros no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Este artigo se destina a clientes empresariais que possuem o [Microsoft Defender para Office 365](defender-for-office-365.md). Se você for um usuário de residência procurando informações sobre Safelinks no Outlook, consulte [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Links Seguros é um recurso do [Microsoft Defender para Office 365](defender-for-office-365.md) que fornece verificação de URL de mensagens de email de entrada no fluxo de emails e hora de verificação de clique em URLs e links em mensagens de email e em outros locais. Para obter mais informações, consulte [Links seguros no Microsoft Defender para Office 365](safe-links.md).

Você configura a maioria das configurações de Links Seguros em políticas de Links Seguros. Para obter instruções, consulte [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).

No entanto, Os Links Seguros também usam configurações globais que se aplicam a todos os usuários incluídos em quaisquer políticas de Links Seguros ativos. Estas áreas de configurações globais:

- A **lista Bloquear as URLs a** seguir. Para obter mais informações, consulte ["Bloquear a lista de URLs a seguir" para Links Seguros](safe-links.md#block-the-following-urls-list-for-safe-links)
- Proteção de Links Seguros para aplicativos do Office 365. Para obter mais informações, consulte [Configurações de Links Seguros para aplicativos do Office 365.](safe-links.md#safe-links-settings-for-office-365-apps)

Você pode configurar as configurações globais de Links Seguros no Centro de Conformidade de Segurança & ou no PowerShell (PowerShell do Exchange Online para organizações qualificadas do Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online, mas com assinaturas de complemento do Microsoft Defender para Office 365).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Os recursos fornecidos pelas configurações globais para Links Seguros só são aplicados aos usuários incluídos em políticas ativas de Links Seguros. Não há política interna ou padrão de Links Seguros, portanto, você precisa criar pelo menos uma política de Links Seguros para que essas configurações globais sejam ativas. Para obter instruções, consulte [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a página **Links Seguros,** use <https://protection.office.com/safelinksv2> .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa de permissões em **Exchange Online** antes de poder realizar os procedimentos neste artigo:
  - Para definir as configurações globais para Links Seguros, você precisa ser membro dos grupos de função Gerenciamento da Organização **ou** Administrador **de** Segurança.
  - Para acesso somente leitura às configurações globais para Links Seguros, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.

  Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Observações**:

  - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).
  - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

- Para nossos valores recomendados para as configurações globais para Links Seguros, consulte [Configurações de Links Seguros.](recommended-settings-for-eop-and-office365.md#safe-links-settings)

- Permitir até 30 minutos para que uma política nova ou atualizada seja aplicada.

- [Novos recursos estão sendo adicionados continuamente ao Microsoft Defender para Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365). À medida que novos recursos são adicionados, talvez seja necessário fazer ajustes nas políticas existentes de Links Seguros.

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>Configure a lista "Bloquear as URLs a seguir" no Centro de Conformidade & Segurança

A **lista Bloquear as URLs** a seguir identifica os links que sempre devem ser bloqueados pela verificação de Links Seguros em aplicativos com suporte. Para obter mais informações, consulte ["Bloquear a lista de URLs a seguir" para Links Seguros.](safe-links.md#block-the-following-urls-list-for-safe-links)

1. No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças Atp Links Seguros e clique \>  \> em **Configurações Globais**.

2. Na política **Links Seguros para sua organização** que aparece, vá para a caixa Bloquear as **URLs a** seguir.

3. Configure uma ou mais entradas conforme descrito em Sintaxe de entrada para a lista ["Bloquear as URLs a seguir".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

   Quando concluir, clique em **Salvar**.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>Configurar a lista "Bloquear as URLs a seguir" no PowerShell

Para obter detalhes sobre a sintaxe de entrada, consulte Sintaxe de entrada para a lista ["Bloquear as URLs a seguir".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

Você pode usar o cmdlet **Get-AtpPolicyForO365** para exibir entradas existentes na _propriedade BlockURLs._

- Para adicionar valores que substituirão quaisquer entradas existentes, use a seguinte sintaxe no PowerShell do Exchange Online ou no PowerShell de Proteção do Exchange Online:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  Este exemplo adiciona as seguintes entradas à lista:

  - Bloqueie o domínio, subdomas e caminhos para fabrikam.com.
  - Bloquear a pesquisa de subdomínio, mas não o domínio pai ou outros subdomínios em tailspintoys.com

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- Para adicionar ou remover valores sem afetar outras entradas existentes, use a seguinte sintaxe:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  Este exemplo adiciona uma nova entrada para adatum.com e remove a entrada para fabrikam.com.

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a>Configurar a proteção de Links Seguros para aplicativos do Office 365 no Centro de Conformidade & Segurança

A proteção de Links Seguros para aplicativos do Office 365 se aplica a documentos em aplicativos da área de trabalho, dispositivos móveis e web do Office com suporte. Para obter mais informações, consulte [Configurações de Links Seguros para aplicativos do Office 365.](safe-links.md#safe-links-settings-for-office-365-apps)

1. No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças Atp Links Seguros e clique \>  \> em **Configurações Globais**.

2. Na política **Links Seguros para sua** organização que aparece, configure as seguintes configurações na seção Configurações que se aplicam ao conteúdo, exceto **email:**

   - **Aplicativos do Office 365**: Verifique se a alternância está à direita para habilitar Links Seguros para aplicativos do Office 365 com ![ suporte: Alternar ](../../media/scc-toggle-on.png) em .

   - **Não rastreia quando** os usuários clicam em Links Seguros : Mova a alternância para a esquerda para controlar os cliques do usuário relacionados a URLs bloqueadas em aplicativos do Office 365 com suporte: ![ Alternar ](../../media/scc-toggle-off.png) para fora .

   - **Não permitir que** os usuários cliquem em Links Seguros para a URL original : Verifique se a alternância está à direita para impedir que os usuários cliquem na URL bloqueada original em aplicativos do Office 365 com suporte: ![ Alternar em ](../../media/scc-toggle-on.png) .

   Quando concluir, clique em **Salvar**.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>Configurar a proteção de links seguros para aplicativos do Office 365 no PowerShell

Se você preferir usar o PowerShell para configurar a proteção de Links Seguros para aplicativos do Office 365, use a seguinte sintaxe no PowerShell do Exchange Online ou no PowerShell de Proteção do Exchange Online:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

Este exemplo configura as seguintes configurações para a proteção de Links Seguros em aplicativos do Office 365:

- Links seguros para aplicativos do Office 365 está ativado (não estamos usando o parâmetro _EnableSafeLinksForO365Clients_ e o valor padrão é $true).
- Os cliques do usuário relacionados a URLs bloqueadas em aplicativos do Office 365 suportados são rastreados.
- Os usuários não têm permissão para clicar na URL bloqueada original em aplicativos do Office 365 com suporte (não estamos usando o parâmetro _AllowClickThrough_ e o valor padrão é $false).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você configurou com êxito as configurações globais para Links Seguros (a lista Bloquear as **URLs** a seguir e as configurações de proteção de aplicativos do Office 365), faça qualquer uma das seguintes etapas:

- No Centro de Conformidade & segurança,  vá até Política de Gerenciamento de Ameaças Links Seguros atp , clique em Configurações globais e verifique as configurações no \>  \> fly out que aparece.

- No PowerShell do Exchange Online ou no PowerShell da Proteção do Exchange Online, execute o seguinte comando e verifique as configurações:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).