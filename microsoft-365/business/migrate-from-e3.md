---
title: Migrar para Microsoft 365 Business do Office 365 E3
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
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
description: Saiba como mover sua empresa para Microsoft 365 Business Premium do Office 365 E3.
ms.openlocfilehash: f08b054473fdd63ec2372e81c776a1b64f89fe9d
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244827"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>Migrando do Office 365 E3 para Microsoft 365 Business Premium

Microsoft 365 Business Premium tem tudo o que você precisa para sua pequena empresa, combinando os melhores aplicativos de produtividade baseados em nuvem com gerenciamento e segurança de dispositivos simples. Se você tiver uma assinatura Office 365 E3, mas não tiver mais de 300 funcionários, considere alternar para o Microsoft 365 Business Premium para recursos de segurança adicionais.

A migração é fácil: primeiro você alterna licenças e todas as informações de dados e usuários em sua assinatura atual são mantidas. Após a migração, você precisará configurar os recursos que são adicionados Microsoft 365 Business Premium.

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>Diferenças entre Office 365 E3 e Microsoft 365 Business Premium

Esta tabela mostra as diferenças entre Microsoft 365 Business Premium e Office 365 E3.

| Recurso    | Suporte em Microsoft 365 Business Premium    | Suporte no Office 365 E3 | 
|:-------|:-----|:-----|
| **No local**        | | | 
| Office apps<sup>1</sup>    | Microsoft 365 Apps para Pequenos e Médios negócios    | Microsoft 365 Apps para empresas | 
| **Aplicativos de produtividade na nuvem**        | | | 
| Exchange Online e Outlook    | Limite de armazenamento de 50 GB por caixa de correio e limites ilimitados Arquivamento do Exchange Online    | Limite de armazenamento de 100 GB por caixa de correio e limites ilimitados Arquivamento do Exchange Online | 
| Teams    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Office 365 E3](../media/check-mark.png) | 
| OneDrive for Business    | Limite de armazenamento de 1 TB por usuário    | Ilimitado | 
| Yammer, SharePoint Online, Planner, Stream    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Office 365 E3](../media/check-mark.png) | 
| StaffHub    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Office 365 E3](../media/check-mark.png) | 
| MileIQ    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| **Proteção contra Ameaças**        | | | 
| Microsoft Defender para Office 365 Plano 1 | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | Não incluído, mas pode ser adicionado em | 
| **O gerenciamento de identidades**        | | | 
| Redefinição de senha de autoatenduro para contas Azure Active Directory (Azure AD), autenticação multifacional do Azure AD (MFA), Acesso Condicional, write-back de senha para identidades locais|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    |  | 
| **Gerenciamento de aplicativo e dispositivo**        | | |
| Microsoft Intune, Windows AutoPilot|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| Ativação de computador compartilhado|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Office 365 E3](../media/check-mark.png)| 
| Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    || 
| **Proteção de informações**        | | |
|Prevenção contra Perda de Dados do Office 365|    ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)|![Incluído no Office 365 E3](../media/check-mark.png)|
|Plano 1 de Proteção de Informações do Azure, BitLocker imposição|![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)||
|Plano 1 de Proteção de Informações do Azure, rótulos de sensibilidade|![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)||
|**Licença de Acesso para Cliente (direitos CAL)**|||
|Enterprise Pacote CAL (Exchange, SharePoint, Skype)||![Incluído no Office 365 E3](../media/check-mark.png)|

<sup>1</sup> A Microsoft 365 Business Premium versão Office aplicativos do Office não inclui ativação de volume por meio da Política de Grupo, telemetria de aplicativos, controles de atualização, comparação e consulta de planilhas ou business Intelligence.

## <a name="migration"></a>Migração

Para migrar sua assinatura, consulte [Alterar planos manualmente](../commerce/subscriptions/change-plans-manually.md) para obter instruções se você deseja mover apenas algumas pessoas para Microsoft 365 Business Premium. Você também pode [atualizar todos automaticamente](../commerce/subscriptions/upgrade-to-different-plan.md)ou trabalhar com um parceiro para mover sua assinatura e licenças do E3 para uma Microsoft 365 Business Premium assinatura.
As seções a seguir descrevem as alterações que você precisa fazer, se alguma, e o que você pode fazer após a migração.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Office 365 Dados e configuração de assinatura do E3
Você não precisa fazer alterações na sua assinatura ou dados atuais antes de migrar, o que inclui:

- Configuração de assinatura, como registros DNS e nomes de domínio.
- Contas de usuário e grupo e configurações de autenticação, como autenticação multifacional ou políticas de acesso condicional.
- Configurações de serviço de produtividade e seus dados, como Teams, caixas de correio Exchange Online, sites do SharePoint Online, pastas OneDrive for Business e OneNote blocos de anotações.
- Office aplicativos serão dimensionados automaticamente. Office 365 licenciamento moderno verificará a atribuição de licença do usuário a cada 72 horas e converterá Office aplicativos para a versão que corresponde à assinatura do usuário.

### <a name="windows-10"></a>Windows 10

Se o Windows já não estiver na atualização Windows Pro do Criador, atualize-os para Windows Pro [Creators Update](upgrade-to-windows-pro-creators-update.md).

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>Configurar políticas para proteger os dispositivos e arquivos do usuário

> [!NOTE]
> Se você configurar Office 365 e dispositivos MDM, esses dispositivos serão listados na página **Dispositivos** no Microsoft 365 de administração. Todas as políticas configuradas aparecerão na lista de políticas clássicas no [portal do Intune.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)

Depois de ter atribuído licenças Microsoft 365 Business Premium, você pode começar a proteger os dispositivos e arquivos dos usuários.

Se você atualizou todos na sua organização para Microsoft 365 Business Premium, você verá o assistente de [](set-up.md) instalação na Home page e poderá seguir o guia Configurar Microsoft 365 Business Premium nas etapas do assistente de instalação para proteger arquivos e dispositivos móveis.

Você também pode concluir estas etapas na página Dispositivos:
  
1. No centro de administração, na nav esquerda, vá para **Políticas de** \> **Dispositivos**.
    
2. Na página **Políticas de** dispositivo, escolha **Adicionar**.
    
3. No painel **Adicionar política,** dê um nome à política e escolha um **tipo de Política** no drop-down. 
    
     Você pode configurar políticas de aplicativos para proteger arquivos em dispositivos Android e iPhone, bem como Windows 10, e pode configurar políticas de configuração de dispositivos para dispositivos Windows 10 da empresa. Confira os seguintes links para obter detalhes:
    
  - [Definir configurações de proteção de aplicativo para dispositivos Android ou iOS](app-protection-settings-for-android-and-ios.md)
    
  - [Definir configurações de proteção de aplicativo para dispositivos Windows 10](protection-settings-for-windows-10-devices.md)
    
  - [Definir configurações de proteção de dispositivo para Windows 10 PCs](protection-settings-for-windows-10-pcs.md)
  
4. Depois de configurar políticas, você e seus funcionários podem configurar dispositivos:
    
  - Consulte [Configurar dispositivos Windows para usuários Microsoft 365 Business Premium para](set-up-windows-devices.md) etapas para Windows dispositivos. 
    
  - Consulte [Configurar dispositivos móveis para usuários Microsoft 365 Business Premium para](set-up-mobile-devices.md) etapas para telefones Android e iPhones. 
  
### <a name="mailbox-size"></a>Tamanho da caixa de correio

Microsoft 365 Business Premium tem um limite de armazenamento de 50 GB, pois usa Exchange Online Plano 1. Ao migrar para o Microsoft 365 Business Premium, se algum de seus usuários exceder 50 GB de armazenamento de caixa de correio, é recomendável atribuir a esse usuário um plano 2 do Exchange Online e remover o plano 1 do Exchange Online, pois não é viável atribuir ambos.


### <a name="threat-protection"></a>Proteção contra ameaças

Depois de migrar para Microsoft 365 Business Premium, você terá o Defender para Office 365. Consulte [Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) para ver uma visão geral. Para configurar, consulte [configurar Cofre Links,](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)configurar Cofre [Anexos](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)e configurar [Anti-phishing](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)no Defender para Office 365 .

### <a name="sensitivity-labels"></a>Rótulos de confidencialidade

Para começar a usar rótulos de sensibilidade, consulte [Visão geral dos](../compliance/sensitivity-labels.md) rótulos de sensibilidade e crie e gerencie o vídeo de [rótulos de sensibilidade.](../business-video/create-sensitivity-labels.md)
