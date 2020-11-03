---
title: Definir configurações globais para configurações de links seguros no defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a exibir e definir as configurações globais (a lista e proteção dos seguintes URLs para aplicativos do Office 365) para links seguros no Microsoft defender para Office 365.
ms.openlocfilehash: 655fba35bf3675bfd571c8e4923a00fbeba85304
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842423"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Definir configurações globais para links seguros no Microsoft defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Este artigo destina-se a clientes comerciais que têm [o Microsoft defender para Office 365](office-365-atp.md). Se você for um usuário doméstico que procura informações sobre o Safelinks no Outlook, consulte [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Links seguros é um recurso do [Microsoft defender para Office 365](office-365-atp.md) que oferece verificação de URL de mensagens de email de entrada no fluxo de emails e a hora de clicar em verificação de URLs e links em mensagens de email e em outros locais. Para obter mais informações, consulte [links seguros no Microsoft defender para Office 365](atp-safe-links.md).

Você define as configurações de links mais seguros em políticas de links seguros. Para obter instruções, consulte [set up Safe links Policies in Microsoft defender for Office 365](set-up-atp-safe-links-policies.md).

No entanto, os links seguros também usam configurações globais que se aplicam a todos os usuários que estão incluídos em qualquer política ativa de links seguros. Área de configurações globais:

- O **bloqueia a lista de URLs a seguir** . Para obter mais informações, consulte [a lista "bloquear as seguintes URLs" para links seguros](atp-safe-links.md#block-the-following-urls-list-for-safe-links)
- Proteção de links seguros para aplicativos do Office 365. Para obter mais informações, consulte [configurações de links seguros para aplicativos do Office 365](atp-safe-links.md#safe-links-settings-for-office-365-apps).

Você pode definir as configurações de links seguros globais no centro de conformidade e segurança & ou no PowerShell (Exchange Online PowerShell para organizações qualificadas da Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online, mas com o Microsoft defender para Office 365 assinaturas complementares).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Os recursos fornecidos por configurações globais para links seguros só são aplicados aos usuários incluídos em políticas de links seguros ativos. Não há nenhuma política interna ou de links seguros padrão, portanto, você precisa criar pelo menos uma política de links seguros para que essas configurações globais estejam ativas. Para obter instruções, consulte [set up Safe links Policies in Microsoft defender for Office 365](set-up-atp-safe-links-policies.md).

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a página de **links seguros** , use <https://protection.office.com/safelinksv2> .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Para exibir e definir as configurações globais de links seguros, você precisa ser membro de um dos grupos de função a seguir:

  - **Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).
  - **Gerenciamento de organização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Para obter os valores recomendados para as configurações globais de links seguros, consulte [configurações de links seguros](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).

- Aguarde até 30 minutos para que uma política nova ou atualizada seja aplicada.

- [Novos recursos estão sempre sendo adicionados ao Microsoft defender para Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365). À medida que novos recursos são adicionados, talvez seja necessário fazer ajustes em suas políticas de links seguros existentes.

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>Configurar a lista "bloquear as seguintes URLs" no centro de conformidade de & de segurança

A lista de **URLs a seguir** identifica os links que devem ser sempre bloqueados pela verificação de links seguros em aplicativos compatíveis. Para obter mais informações, consulte [a lista "bloquear as seguintes URLs" para obter links seguros](atp-safe-links.md#block-the-following-urls-list-for-safe-links).

1. No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** \> **Policy** \> e **links seguros de ATP** e clique em **configurações globais**.

2. Na **política de links seguros de sua organização** que aparece, vá para a caixa **bloquear as seguintes URLs** .

3. Configure uma ou mais entradas, conforme descrito na [sintaxe de entrada da lista "bloquear as seguintes URLs"](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).

   Quando concluir, clique em **Salvar**.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>Configurar a lista "bloquear as seguintes URLs" no PowerShell

Para obter detalhes sobre a sintaxe de entrada, consulte a [sintaxe de entrada para a lista "bloquear as seguintes URLs"](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).

Você pode usar o cmdlet **Get-AtpPolicyForO365** para exibir as entradas existentes na propriedade _BlockURLs_ .

- Para adicionar valores que substituirão quaisquer entradas existentes, use a seguinte sintaxe no PowerShell do Exchange Online ou do Exchange Online Protection:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  Este exemplo adiciona as seguintes entradas à lista:

  - Bloquear o domínio, subdomínios e caminhos para o fabrikam.com.
  - Bloquear a pesquisa de subdomínio, mas não o domínio pai ou outros subdomínios no tailspintoys.com

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- Para adicionar ou remover valores sem afetar outras entradas existentes, use a seguinte sintaxe:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  Este exemplo adiciona uma nova entrada para adatum.com e remove a entrada de fabrikam.com.

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a>Configurar a proteção de links seguros para aplicativos do Office 365 no centro de conformidade & segurança

Proteção de links seguros para aplicativos do Office 365 aplica-se a documentos em aplicativos da Web, móveis e da área de trabalho do Office compatíveis. Para obter mais informações, consulte [configurações de links seguros para aplicativos do Office 365](atp-safe-links.md#safe-links-settings-for-office-365-apps).

1. No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** \> **Policy** \> e **links seguros de ATP** e clique em **configurações globais**.

2. Na **política de links seguros de sua organização** que aparece, defina as seguintes configurações na seção **configurações que se aplicam ao conteúdo exceto o email** :

   - **Aplicativos do office 365** : Verifique se a opção Alternar está à direita para habilitar links seguros para aplicativos do Office 365 suportados: ![ Ativar/desativar ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .

   - **Não rastrear quando os usuários clicarem em links seguros** : mover a opção para a esquerda para rastrear os cliques do usuário relacionados a URLs bloqueadas em aplicativos do Office 365 com suporte: ![ desativar ](../../media/scc-toggle-off.png) .

   - **Não permita que os usuários cliquem através de links seguros para a URL original** : Verifique se o botão de alternância está à direita para impedir que os usuários cliquem no URL bloqueado original em aplicativos do Office 365 com suporte: ![ Ativar/desativar ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .

   Quando concluir, clique em **Salvar**.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>Configurar a proteção de links seguros para aplicativos do Office 365 no PowerShell

Se você preferir usar o PowerShell para configurar a proteção de links seguros para aplicativos do Office 365, use a seguinte sintaxe no PowerShell do Exchange Online ou do Exchange Online Protection PowerShell:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

Este exemplo define as seguintes configurações para proteção de links seguros em aplicativos do Office 365:

- Os links seguros para aplicativos do Office 365 estão ativados (não estamos usando o parâmetro _EnableSafeLinksForO365Clients_ , e o valor padrão é $true).
- Os cliques do usuário relacionados a URLs bloqueadas em aplicativos do Office 365 com suporte são rastreados.
- Os usuários não têm permissão para clicar na URL bloqueada original em aplicativos compatíveis com o Office 365 (não estamos usando o parâmetro _AllowClickThrough_ , e o valor padrão é $false).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você configurou com êxito as configurações globais para links seguros (a lista de **seguintes URLs** e as configurações de proteção de aplicativos do Office 365), execute qualquer uma das seguintes etapas:

- No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** \> **Policy** \> , **links seguros de ATP** , clique em **configurações globais** e verifique as configurações na saída que aparece.

- No PowerShell do Exchange Online ou do Exchange Online Protection, execute o seguinte comando e verifique as configurações:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).
