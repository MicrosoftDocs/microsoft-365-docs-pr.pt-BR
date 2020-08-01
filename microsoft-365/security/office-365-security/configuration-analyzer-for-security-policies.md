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
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a usar o analisador de configuração para localizar e corrigir políticas de segurança que contêm configurações que estão abaixo das políticas de segurança predefinidas proteção padrão e proteção estrita.
ms.openlocfilehash: 259d498646ecf893a57a608a37e3b771083716cc
ms.sourcegitcommit: fab425ea4580d1924fb421e6db233d135f5b7d19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533951"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a>Analisador de configuração para políticas de proteção no EOP e no Office 365 ATP

> [!NOTE]
> Os recursos descritos neste tópico estão em visualização, não estão disponíveis em todas as organizações e estão sujeitos a alterações.

O analisador de configuração no centro de conformidade & segurança fornece um local central para encontrar e corrigir qualquer uma das políticas de segurança que contêm configurações que estão abaixo das configurações de perfil de proteção padrão e proteção estrita em [políticas de segurança predefinidas](preset-security-policies.md).

Os seguintes tipos de políticas são analisados pelo analisador de configuração:

- **Políticas de proteção do Exchange Online (EOP)**: isso inclui as organizações do Microsoft 365 com caixas de correio do Exchange Online e organizações autônomas do EOP sem caixas de correio do Exchange Online:
  
  - [Políticas antispam](configure-your-spam-filter-policies.md).
  - [Diretivas Antimalware](configure-anti-malware-policies.md).
  - [EOP regras anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).

- **Políticas de proteção avançada contra ameaças (ATP) do office 365**: inclui organizações com as assinaturas do Microsoft 365 E5 ou do Office 365 ATP Add-on:

  - Políticas anti-phishing da ATP, que incluem:

    - As mesmas [configurações de spoof](set-up-anti-phishing-policies.md#spoof-settings) que estão disponíveis nas políticas anti-phishing do EOP.
    - [Configurações de representação](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [Limites avançados de phishing](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - [Políticas de links seguros](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).

  - [Políticas de anexos seguros](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).

Os valores de configuração de política **padrão** e **estrito** usados como linhas de base são descritos em [configurações recomendadas para a segurança do EOP e do Office 365 ATP](recommended-settings-for-eop-and-office365-atp.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a página do **analisador de configuração** , use <https://protection.office.com/configurationAnalyzer> .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Você precisa ter permissões atribuídas antes de poder executar os procedimentos neste tópico:

  - Para usar o analisador de configuração **e** fazer atualizações em políticas de segurança, você precisa ser membro de um dos grupos de função a seguir:

    - **Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).
    - **Gerenciamento de organizações** ou **Gerenciamento de higiene** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Para acesso somente leitura ao analisador de configuração, você precisa ser membro de um dos seguintes grupos de função:

    - **Leitor de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).
    - **Gerenciamento da organização Somente visualização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a>Usar o analisador de configuração no centro de conformidade & segurança

No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **analisador de configuração**de política de gerenciamento de ameaças.

![Widget analisador de configuração na página política de gerenciamento de ameaças \>](../../media/configuration-analyzer-widget.png)

O analisador de configuração tem duas guias principais:

- **Configurações e recomendações**: escolha padrão ou estrito e Compare essas configurações com as políticas de segurança existentes. Nos resultados, você pode ajustar os valores de suas configurações para colocá-los no mesmo nível que o padrão ou estrito.

- **Histórico e análise de descompasso de configuração**: este modo de exibição permite controlar as alterações feitas em suas políticas com base nos resultados do analisador de configuração ao longo do tempo.

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a>Guia configuração e recomendações no analisador de configuração

Por padrão, a guia é aberta na comparação com o perfil de proteção padrão. Você pode mudar para a comparação do perfil de proteção estrito clicando em **Exibir recomendações estritas**. Para retornar, selecione **Exibir recomendações padrão**.

![Exibição de configurações e recomendações no analisador de configuração](../../media/configuration-analyzer-settings-and-recommendations-view.png)

Por padrão, a coluna **grupo de políticas/nome da configuração** contém uma exibição recolhida dos diferentes tipos de políticas de segurança e o número de configurações nessas políticas que precisam de melhorias (se houver). Os tipos de políticas são:

- **Antispam**
- **Anti-phishing**
- **Antimalware**
- **Anexos seguros de ATP** (se sua assinatura incluir ATP)
- **Links seguros de ATP** (se sua assinatura incluir ATP)

No modo de exibição padrão, tudo é recolhido. Ao lado de cada política, um resumo dos resultados da comparação de suas políticas (que você pode modificar) e as configurações nas políticas correspondentes para os perfis de proteção padrão ou estrito (que você não pode modificar) são exibidos. Você verá as seguintes informações:

- **Verde**: todas as configurações de todas as políticas existentes são pelo menos tão seguras quanto o perfil de proteção para o qual você está comparando.
- **Âmbar**: um pequeno número de configurações nas políticas existentes não é tão seguro quanto o perfil de proteção para o qual você está comparando.
- **Vermelho**: um número significativo de configurações nas políticas existentes não é tão seguro quanto o perfil de proteção para o qual você está comparando. Isso pode ser algumas configurações em muitas políticas ou muitas configurações em uma política.

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

Esta guia permite que você rastreie as alterações feitas em suas políticas de segurança personalizadas com base nas informações do analisador de segurança. Por padrão, as seguintes informações são exibidas:

- **Última modificação**
- **Modificado por**
- **Nome da configuração**
- **Política**
- **Type**

Para filtrar os resultados, clique em **Filtro**. No submenu **filtros** que aparece, você pode selecionar um dos seguintes filtros:

- **Hora de início** e **hora de término** (Data)
- **Proteção padrão** ou **proteção estrita**

Para exportar os resultados para um arquivo. csv, clique em **Exportar**.

![Análise de descompasso de configuração e exibição de histórico no analisador de configuração](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
