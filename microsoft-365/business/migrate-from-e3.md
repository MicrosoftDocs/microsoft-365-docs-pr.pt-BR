---
title: Migrar para o Microsoft 365 Business do Office 365 E3
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Saiba como mover sua empresa para o Microsoft 365 Business Premium do Office 365 E3.
ms.openlocfilehash: 3f9fd70b2d31b32027981e638de249d92e98ea08
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164524"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>Migrando do Office 365 E3 para o Microsoft 365 Business Premium

O Microsoft 365 Business Premium tem tudo o que você precisa para sua pequena empresa, combinando os melhores aplicativos de produtividade baseados em nuvem com gerenciamento de dispositivos simples e segurança. Se você tem atualmente uma assinatura do Office 365 E3, mas não tem mais de 300 funcionários, considere alternar para o Microsoft 365 Business Premium para recursos de segurança adicionais.

A migração é fácil: primeiro você alterna licenças e todas as informações de dados e usuários em sua assinatura atual são mantidas. Após a migração, você precisará configurar os recursos adicionados ao Microsoft 365 Business Premium.

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>Diferenças entre o Office 365 E3 e o Microsoft 365 Business Premium

Esta tabela mostra as diferenças entre o Microsoft 365 Business Premium e o Office 365 E3.

| Recurso    | Suporte no Microsoft 365 Business Premium    | Suporte no Office 365 E3 | 
|:-------|:-----|:-----|
| **No local**        | | | 
| Aplicativos do Office<sup>1</sup>    | Microsoft 365 Apps para Pequenos e Médios negócios    | Microsoft 365 Apps para Grandes Empresas | 
| **Aplicativos de produtividade na nuvem**        | | | 
| Exchange Online e Outlook    | Limite de armazenamento de 50 GB por caixa de correio e limites ilimitados Arquivamento do Exchange Online    | Limite de armazenamento de 100 GB por caixa de correio e limites ilimitados Arquivamento do Exchange Online | 
| Teams    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Office 365 E3](../media/check-mark.png) | 
| OneDrive for Business    | Limite de armazenamento de 1 TB por usuário    | Ilimitado | 
| Yammer, SharePoint Online, Planner, Stream    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Office 365 E3](../media/check-mark.png) | 
| StaffHub    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Office 365 E3](../media/check-mark.png) | 
| Outlook Customer Manager    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| **Proteção contra Ameaças**        | | | 
| Microsoft Defender para Office 365 Plano 1 | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | Não incluído, mas pode ser adicionado em | 
| **O gerenciamento de identidades**        | | | 
| Redefinição de senha de autoatendamento para contas híbridas do Azure Active Directory (Azure AD), autenticação multifacional do Azure AD (MFA), Acesso Condicional, write-back de senha para identidades locais|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    |  | 
| **Gerenciamento de aplicativo e dispositivo**        | | |
| Microsoft Intune, Windows AutoPilot|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| Ativação de computador compartilhado|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Office 365 E3](../media/check-mark.png)| 
| Direitos de atualização para o Windows 10 Pro a partir de licenças do Win 7/8.1 Pro|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    || 
| **Proteção de informações**        | | |
|Prevenção contra Perda de Dados do Office 365|    ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)|![Incluído no Office 365 E3](../media/check-mark.png)|
|Plano 1 de Proteção de Informações do Azure, imposição do Bitlocker|![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)||
|Plano 1 de Proteção de Informações do Azure, rótulos de sensibilidade|![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)||
|**Licença de Acesso para Cliente (direitos CAL)**|||
|Enterprise CAL Suite (Exchange, SharePoint, Skype)||![Incluído no Office 365 E3](../media/check-mark.png)|

<sup>1</sup> A versão do Microsoft 365 Business Premium dos aplicativos do Office não inclui ativação de volume por meio da Política de Grupo, telemetria de aplicativos, controles de atualização, comparação e consulta de planilhas ou business Intelligence.

## <a name="migration"></a>Migração

Para migrar sua assinatura, consulte [Alterar planos manualmente](../commerce/subscriptions/change-plans-manually.md) para obter instruções se você deseja mover apenas algumas pessoas para o Microsoft 365 Business Premium. Você também pode [atualizar todos](../commerce/subscriptions/upgrade-to-different-plan.md)automaticamente ou trabalhar com um parceiro para mover sua assinatura e licenças do E3 para uma assinatura do Microsoft 365 Business Premium.
As seções a seguir descrevem as alterações que você precisa fazer, se alguma, e o que você pode fazer após a migração.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Dados e configuração de assinatura do Office 365 E3
Você não precisa fazer alterações na sua assinatura ou dados atuais antes de migrar, o que inclui:

- Configuração de assinatura, como registros DNS e nomes de domínio.
- Contas de usuário e grupo e configurações de autenticação, como autenticação multifacional ou políticas de acesso condicional.
- Configurações de serviço de produtividade e seus dados, como Teams, caixas de correio do Exchange Online, sites do SharePoint Online, pastas do OneDrive for Business e blocos de anotações do OneNote.
- Os aplicativos do Office serão dimensionados automaticamente. O licenciamento moderno do Office 365 verificará a atribuição de licença do usuário a cada 72 horas e converterá os aplicativos do Office na versão que corresponde à assinatura do usuário.

### <a name="windows-10"></a>Windows 10

Se o Windows ainda não estiver na atualização do Windows Pro Creator, [atualize-os para Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>Configurar políticas para proteger os dispositivos e arquivos do usuário

> [!NOTE]
> Se você configurar políticas e dispositivos do Office 365 MDM, esses dispositivos serão listados na página Dispositivos no Centro de administração do Microsoft 365.  Todas as políticas configuradas aparecerão na lista de políticas clássicas no [portal do Intune.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)

Depois de ter atribuído licenças ao Microsoft 365 Business Premium, você pode começar a proteger os dispositivos e arquivos dos usuários.

Se você atualizou todos na sua organização para o Microsoft 365 Business Premium, você verá o assistente de instalação na Home page e poderá seguir a configuração do [Microsoft 365 Business Premium](set-up.md) nas etapas do assistente de configuração para proteger arquivos e dispositivos móveis.

Você também pode concluir estas etapas na página Dispositivos:
  
1. No centro de administração, na nav esquerda, vá para **Políticas de** \> **Dispositivos**.
    
2. Na página **Políticas de** dispositivo, escolha **Adicionar**.
    
3. No painel **Adicionar política,** dê um nome à política e escolha um **tipo de Política** no drop-down. 
    
     Você pode configurar políticas de aplicativos para proteger arquivos em dispositivos Android e iPhone, bem como o Windows 10, e pode configurar políticas de configuração de dispositivo para dispositivos Windows 10 pertencentes à empresa. Confira os seguintes links para obter detalhes:
    
  - [Definir configurações de proteção de aplicativo para dispositivos Android ou iOS](app-protection-settings-for-android-and-ios.md)
    
  - [Definir configurações de proteção de aplicativo para dispositivos Windows 10](protection-settings-for-windows-10-devices.md)
    
  - [Definir configurações de proteção de dispositivo para computadores com Windows 10](protection-settings-for-windows-10-pcs.md)
  
4. Depois de configurar políticas, você e seus funcionários podem configurar dispositivos:
    
  - Consulte [Configurar dispositivos Windows para usuários do Microsoft 365 Business Premium](set-up-windows-devices.md) para etapas para dispositivos Windows. 
    
  - Consulte [Configurar dispositivos móveis para usuários do Microsoft 365 Business Premium](set-up-mobile-devices.md) para etapas para telefones Android e iPhones. 
  
### <a name="mailbox-size"></a>Tamanho da caixa de correio

O Microsoft 365 Business Premium tem um limite de armazenamento de 50 GB, pois usa o Plano 1 do Exchange Online. Ao migrar para o Microsoft 365 Business Premium, se algum de seus usuários exceder 50 GB de armazenamento de caixa de correio, é recomendável atribuir a esse usuário um Plano 2 do Exchange Online e remover o Plano 1 do Exchange Online, pois não é viável atribuir ambos.


### <a name="threat-protection"></a>Proteção contra ameaças

Depois de migrar para o Microsoft 365 Business Premium, você terá o Defender para Office 365. Consulte [o Microsoft Defender para Office 365](../security/defender-365-security/defender-for-office-365.md) para ver uma visão geral. Para configurar, consulte [set up Safe Links](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), set up Safe [Attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up Anti-phishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).

### <a name="sensitivity-labels"></a>Rótulos de confidencialidade

Para começar a usar rótulos de sensibilidade, consulte [Visão geral dos](../compliance/sensitivity-labels.md) rótulos de sensibilidade e crie e gerencie o vídeo de [rótulos de sensibilidade.](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)
