---
title: Analisador de configuração para políticas de segurança
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a usar o analisador de configuração para encontrar e corrigir as políticas de segurança que estão abaixo das políticas de segurança predefinidas de proteção padrão e proteção estrita.
ms.openlocfilehash: af7cf269151c7e947a0a2f653ce8638d46ccd905
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658656"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a>Analisador de configuração para políticas de proteção no EOP e Microsoft defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Os recursos descritos neste artigo estão em visualização, não estão disponíveis em todas as organizações e estão sujeitos a alterações. Para obter informações sobre o cronograma de lançamento, confira o [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).

O analisador de configuração no centro de conformidade & segurança fornece um local central para encontrar e corrigir as políticas de segurança nas quais as configurações estão abaixo das configurações de perfil de proteção padrão e proteção estrita em [políticas de segurança predefinidas](preset-security-policies.md).

Os seguintes tipos de políticas são analisados pelo analisador de configuração:

- **Políticas de proteção do Exchange Online (EOP)**: isso inclui as organizações do Microsoft 365 com caixas de correio do Exchange Online e organizações autônomas do EOP sem caixas de correio do Exchange Online:

  - [Políticas antispam](configure-your-spam-filter-policies.md).
  - [Diretivas Antimalware](configure-anti-malware-policies.md).
  - [EOP regras anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).

- **Políticas do Microsoft defender para Office 365**: isso inclui organizações com as assinaturas do complemento Microsoft 365 E5 ou defender para Office 365:

  - Políticas anti-phishing no Microsoft defender para Office 365, que incluem:

    - As mesmas [configurações de spoof](set-up-anti-phishing-policies.md#spoof-settings) que estão disponíveis nas políticas anti-phishing do EOP.
    - [Configurações de representação](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Limites avançados de phishing](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Políticas de links seguros](set-up-atp-safe-links-policies.md).

  - [Políticas de anexos seguros](set-up-atp-safe-attachments-policies.md).

Os valores de configuração de política **padrão** e **estrito** usados como linhas de base são descritos em [configurações recomendadas para a segurança do EOP e do Microsoft defender para Office 365](recommended-settings-for-eop-and-office365-atp.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a página do **analisador de configuração** , use <https://protection.office.com/configurationAnalyzer> .

- Para se conectar ao Windows PowerShell do Exchange Online, confira [Conectar ao Windows PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos deste artigo:
  - Para usar o analisador de configuração **e** fazer atualizações em políticas de segurança, você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de **administrador de segurança** .
  - Para acesso somente leitura ao analisador de configuração, você precisa ser membro dos grupos de função **leitor global** ou **leitor de segurança** .

  Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

  **Observações**:

  - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a>Usar o analisador de configuração no centro de conformidade & segurança

No centro de conformidade & segurança, vá para  \>  \> **analisador de configuração** de política de gerenciamento de ameaças.

![Widget analisador de configuração na página política de gerenciamento de ameaças \>](../../media/configuration-analyzer-widget.png)

O analisador de configuração tem duas guias principais:

- **Configurações e recomendações**: escolha padrão ou estrito e Compare essas configurações com as políticas de segurança existentes. Nos resultados, você pode ajustar os valores de suas configurações para colocá-los no mesmo nível que o padrão ou estrito.

- **Histórico e análise de descompasso de configuração**: este modo de exibição permite que você rastreie alterações de política ao longo do tempo.

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a>Guia configuração e recomendações no analisador de configuração

Por padrão, a guia é aberta na comparação com o perfil de proteção padrão. Você pode mudar para a comparação do perfil de proteção estrito clicando em **Exibir recomendações estritas**. Para retornar, selecione **Exibir recomendações padrão**.

![Exibição de configurações e recomendações no analisador de configuração](../../media/configuration-analyzer-settings-and-recommendations-view.png)

Por padrão, a coluna **grupo de políticas/nome da configuração** contém uma exibição recolhida dos diferentes tipos de políticas de segurança e o número de configurações que precisam de melhorias (se houver). Os tipos de políticas são:

- **Antispam**
- **Anti-phishing**
- **Anti-malware**
- **Anexos seguros de ATP** (se sua assinatura incluir o Microsoft defender para Office 365)
- **Links seguros de ATP** (se sua assinatura incluir o Microsoft defender para Office 365)

No modo de exibição padrão, tudo é recolhido. Ao lado de cada política, há um resumo dos resultados da comparação de suas políticas (que você pode modificar) e as configurações nas políticas correspondentes para os perfis de proteção padrão ou estrito (que você não pode modificar). Você verá as seguintes informações para o perfil de proteção para o qual você está comparando:

- **Verde**: todas as configurações de todas as políticas existentes são pelo menos tão seguras quanto o perfil de proteção.
- **Âmbar**: um pequeno número de configurações nas políticas existentes não é tão seguro quanto o perfil de proteção.
- **Vermelho**: um número significativo de configurações nas políticas existentes não é tão seguro quanto o perfil de proteção. Isso pode ser algumas configurações em muitas políticas ou muitas configurações em uma política.

Para comparações favoráveis, você verá o texto: **todas as configurações seguem** \<**Standard** or **Strict**\> **recomendações**. Caso contrário, você verá o número de configurações recomendadas a serem alteradas.

Se você expandir o **nome de configuração e grupo de políticas**, todas as políticas e as configurações associadas em cada política específica que exigem atenção são reveladas. Ou você pode expandir um tipo específico de política (por exemplo, **antispam**) para ver apenas essas configurações nesses tipos de políticas que exigem sua atenção.

Se a comparação não tiver recomendações de melhoria (verde), a expansão da política não revela nada. Se houver qualquer número de recomendações de aperfeiçoamento (âmbar ou vermelho), as configurações que exigem atenção são reveladas e as informações correspondentes são reveladas nas seguintes colunas:

- O nome da configuração que requer sua atenção. Por exemplo, na captura de tela anterior, é o **limite de email em massa** em uma política antispam.

- **Política**: o nome da política afetada que contém a configuração.

- **Aplicado a**: o número de usuários aos quais as políticas afetadas são aplicadas.

- **Configuração atual**: o valor atual da configuração.

- **Última modificação**: a data em que a política foi modificada pela última vez.

- **Recomendações**: o valor da configuração no perfil de proteção padrão ou estrita. Para alterar o valor da configuração na política para corresponder ao valor recomendado no perfil de proteção, clique em **adotar**. Se a alteração for bem-sucedida, você verá a mensagem: as **recomendações foram adotadas com êxito**. Clique em **Atualizar** para ver o número reduzido de recomendações e a remoção da linha de configuração/política específica dos resultados.

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>Análise de descompasso de configuração e guia histórico no analisador de configuração

Esta guia permite que você rastreie as alterações feitas em suas políticas de segurança personalizadas. Por padrão, as seguintes informações são exibidas:

- **Última modificação**
- **Modificado por**
- **Nome da configuração**
- **Política**
- **Tipo**

Para filtrar os resultados, clique em **Filtro**. No submenu **filtros** que aparece, você pode selecionar um dos seguintes filtros:

- **Hora de início** e **hora de término** (Data)
- **Proteção padrão** ou **proteção estrita**

Para exportar os resultados para um arquivo. csv, clique em **Exportar**.

![Análise de descompasso de configuração e exibição de histórico no analisador de configuração](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
