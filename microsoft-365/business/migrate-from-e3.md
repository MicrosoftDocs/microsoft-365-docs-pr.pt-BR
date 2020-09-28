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
ms.openlocfilehash: f3f3894a2a5cb69f9f91825d89db4f4b857fac5c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295281"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>Migrando do Office 365 E3 para a Microsoft 365 Business Premium 

O Microsoft 365 Business Premium tem tudo o que você precisa para sua pequena empresa, combinando os melhores aplicativos de produtividade baseada na nuvem com gerenciamento e segurança simples de dispositivos. Se você tiver uma assinatura do Office 365 E3, mas não tiver mais de 300 funcionários, considere mudar para o Microsoft 365 Business Premium para recursos de segurança adicionais.

A migração é fácil: primeiro você muda de licenças e todos os seus dados e informações de usuário em sua assinatura atual são mantidos. Após a migração, você precisará configurar os recursos que são adicionados no Microsoft 365 Business Premium.

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>Diferenças entre o Office 365 E3 e o Microsoft 365 Business Premium

Esta tabela mostra as diferenças entre o Microsoft 365 Business Premium e o Office 365 E3.

| Recurso    | Suporte no Microsoft 365 Business Premium    | Suporte no Office 365 E3 | 
|:-------|:-----|:-----|
| **No local**        | | | 
| Aplicativos do Office<sup>1</sup>    | Aplicativos do Microsoft 365 para empresas    | Microsoft 365 Apps para empresas | 
| **Aplicativos de produtividade em nuvem**        | | | 
| Exchange Online e Outlook    | limite de armazenamento de 50 GB por caixa de correio e arquivamento ilimitado do Exchange Online    | limite de armazenamento de 100 GB por caixa de correio e arquivamento ilimitado do Exchange Online | 
| Teams    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído com o Office 365 E3](../media/check-mark.png) | 
| OneDrive for Business    | limite de armazenamento de 1 TB por usuário    | Ilimitado | 
| Yammer, SharePoint Online, Planner, Stream    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído com o Office 365 E3](../media/check-mark.png) | 
| StaffHub    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído com o Office 365 E3](../media/check-mark.png) | 
| Gerenciador de clientes do Outlook, MileIQ    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| **Proteção contra Ameaças**        | | | 
| Office 365 plano de proteção avançada contra ameaças (ATP) 1 | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | Não está incluído, mas pode ser adicionado em | 
| **O gerenciamento de identidades**        | | | 
| Redefinição de senha de autoatendimento para contas híbridas do Azure Active Directory (Azure AD), autenticação multifator do Azure (MFA), acesso condicional, write-back de senha para identidades locais|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    |  | 
| **Gerenciamento de dispositivos e aplicativos**        | | |
| Microsoft Intune, piloto automático do Windows|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| Ativação de computador compartilhado|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído com o Office 365 E3](../media/check-mark.png)| 
| Atualizar direitos para o Windows 10 pro de licenças do Win 7/8.1 pro|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    || 
| **Proteção de informações**        | | |
|Prevenção contra Perda de Dados do Office 365|    ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)|![Incluído com o Office 365 E3](../media/check-mark.png)|
|Plano de proteção de informações do Azure 1, imposição do BitLocker|![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)||
|Plano de proteção de informações do Azure 1, rótulos de confidencialidade|![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)||
|**Licença de acesso para cliente (direitos de CAL)**|||
|Enterprise CAL Suite (Exchange, SharePoint, Skype)||![Incluído com o Office 365 E3](../media/check-mark.png)|

<sup>1</sup> a versão do Microsoft 365 Business Premium dos aplicativos do Office não inclui ativação por volume através da política de grupo, telemetria de aplicativos, controles de atualização, comparação de planilhas e consultas de Business Intelligence.

## <a name="migration"></a>Migração

Para migrar sua assinatura, confira [alterar planos manualmente](../commerce/subscriptions/change-plans-manually.md) para obter instruções se você deseja mover apenas algumas pessoas para o Microsoft 365 Business Premium. Você também pode [Atualizar todas as pessoas automaticamente](../commerce/subscriptions/upgrade-to-different-plan.md)ou trabalhar com um parceiro para migrar sua assinatura e licenças E3 para uma assinatura do Microsoft 365 Business Premium.
As seções a seguir descrevem as alterações que você precisa fazer, se houver, e o que você pode fazer após a migração.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Dados e configuração de assinatura do Office 365 E3
Você não precisa fazer alterações em sua assinatura atual ou seus dados antes de migrar, o que inclui:

- Configuração de assinatura, como registros DNS e nomes de domínio.
- Contas de usuário e de grupo e configurações de autenticação, como a autenticação multifator ou políticas de acesso condicional.
- Configurações de serviço de produtividade e seus dados, como equipes, caixas de correio do Exchange Online, sites do SharePoint Online, pastas do OneDrive for Business e blocos de anotações do OneNote.
- Os aplicativos do Office serão dimensionados automaticamente. O licenciamento moderno do Office 365 verificará a atribuição da licença do usuário a cada 72 horas e converterá os aplicativos do Office para a versão que corresponde à assinatura do usuário.

### <a name="windows-10"></a>Windows 10

Se o Windows ainda não estiver na atualização do Windows pro Creator, [atualize-o para a atualização do Windows pro Creators](upgrade-to-windows-pro-creators-update.md).

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>Configurar políticas para proteger os arquivos e os dispositivos do usuário

> [!NOTE]
> Se você configurar as políticas e dispositivos do Office 365 MDM, esses dispositivos serão listados na página **dispositivos** no centro de administração do Microsoft 365. Qualquer política configurada será mostrada na lista de políticas clássicas no [portal do Intune](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).

Depois de atribuir licenças ao Microsoft 365 Business Premium, você pode começar a proteger os dispositivos e arquivos dos usuários.

Se você atualizou todas as pessoas em sua organização para o Microsoft 365 Business Premium, verá o assistente de instalação na Home Page e poderá seguir as etapas [Configurar o Microsoft 365 Business Premium nas](set-up.md) etapas do assistente de instalação para proteger arquivos e dispositivos móveis.

Você também pode concluir estas etapas na página dispositivos:
  
1. No centro de administração, na navegação à esquerda, vá para **Devices** \> **políticas**de dispositivos.
    
2. Na página **políticas de dispositivo** , escolha **Adicionar**.
    
3. No painel **Adicionar política** , dê um nome à política e, em seguida, escolha um **tipo de política** na lista suspensa. 
    
     Você pode configurar políticas de aplicativo para proteger arquivos em dispositivos Android e iPhone, bem como Windows 10, e pode configurar políticas de configuração de dispositivo para dispositivos do Windows 10 de propriedade da empresa. Confira os seguintes links para obter detalhes:
    
  - [Definir configurações de proteção de aplicativo para dispositivos Android ou iOS](app-protection-settings-for-android-and-ios.md)
    
  - [Definir configurações de proteção de aplicativo para dispositivos Windows 10](protection-settings-for-windows-10-devices.md)
    
  - [Definir configurações de proteção de dispositivos para computadores com Windows 10](protection-settings-for-windows-10-pcs.md)
  
4. Depois de configurar as políticas, você e seus funcionários poderão configurar dispositivos:
    
  - Consulte [configurar dispositivos Windows para usuários do Microsoft 365 Business Premium](set-up-windows-devices.md) para obter etapas para dispositivos Windows. 
    
  - Confira [configurar dispositivos móveis para usuários do Microsoft 365 Business Premium](set-up-mobile-devices.md) para obter etapas para telefones Android e iPhones. 
  
### <a name="mailbox-size"></a>Tamanho da caixa de correio

O Microsoft 365 Business Premium tem um limite de armazenamento de 50 GB, pois usa o Exchange Online plano 1. Durante a migração para o Microsoft 365 Business Premium, se qualquer um dos seus usuários exceder 50 GB de armazenamento de caixa de correio, é recomendável que você atribua a este usuário um plano 2 do Exchange Online e remova o plano 1 do Exchange Online, já que não é possível atribuir ambos.


### <a name="threat-protection"></a>Proteção contra Ameaças

Após a migração para o Microsoft 365 Business Premium, você tem o Office 365 ATP. Confira [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) para obter uma visão geral. Para configurar, consulte [Configurar links de segurança ATP](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [Configurar anexos de segurança ATP](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)e configurar o [anti-phishing da ATP](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).

### <a name="sensitivity-labels"></a>Rótulos de confidencialidade

Para começar a usar rótulos de sensibilidade, confira [visão geral dos rótulos de confidencialidade](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) e [criar e gerenciar o vídeo de rótulos de Sensibilidade](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) .
