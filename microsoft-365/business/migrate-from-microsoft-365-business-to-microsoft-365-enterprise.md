---
title: Migrar do Microsoft 365 Business para o Microsoft 365 E3
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Saiba como mover sua empresa da Microsoft 365 Business Premium para a Microsoft 365 E3.
ms.openlocfilehash: 6a795d96ccae7e054e7e52d4fd60a4e73b3c71dd
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401985"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>Migrar do Microsoft 365 Business Premium para o Microsoft 365 E3

O Microsoft 365 Business Premium tem tudo o que você precisa para sua pequena empresa, combinando os melhores aplicativos de produtividade baseada na nuvem com gerenciamento de dispositivos simples e segurança que permitem que seus funcionários façam o melhor trabalho. Em alguns casos, no entanto, talvez você precise migrar sua assinatura do Microsoft 365 Business Premium para a Microsoft 365 E3. 

Por exemplo, sua empresa cresceu e precisa de mais de 300 licenças (Parabéns, da forma).

Ou, seus negócios precisam de recursos corporativos, como o Microsoft 365 aplicativos para empresas, o Windows 10 Enterprise E3 ou as licenças de acesso para Cliente Enterprise (CALs).

A atualização é fácil: você pode iniciar a atualização [a partir do centro de administração](../commerce/subscriptions/upgrade-to-different-plan.md). Todos os dados e a configuração da sua assinatura atual são mantidos. Não há nada para se preparar para a migração e nada para fazer posteriormente, exceto aproveitar os novos recursos.

>[!Note]
>Você também pode usar uma assinatura do Microsoft 365 Business Premium para até 300 estações e obter uma assinatura do Microsoft 365 E3 por mais de 300 estações. No entanto, o Office 365 ATP não está incluído no Microsoft 365 E3. Para obter proteção contínua contra ameaças, você deve adicionar mais licenças do Office 365 ATP para que todos os usuários no escopo das suas políticas de ATP do Office 365 sejam licenciados.
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Diferenças entre o Microsoft 365 Business Premium e o Microsoft 365 Enterprise

Esta tabela mostra as diferenças entre o Microsoft 365 Business Premium e o Microsoft 365 E3.

| Recurso    | Suporte no Microsoft 365 Business Premium    | Suporte no Microsoft 365 E3 | 
|:-------|:-----|:-----|
| **No local**        | | | 
| Windows 10    | Windows 10 Business  |     Windows 10 Enterprise E3| 
| Aplicativos do Office *    | [Aplicativos do Microsoft 365 para empresas](#office-365-business)    | Microsoft 365 Apps para empresas | 
| **Aplicativos de produtividade em nuvem**        | | | 
| Exchange Online e Outlook    | limite de armazenamento de 50 GB por caixa de correio e arquivamento ilimitado do Exchange Online    | limite de armazenamento de 100 GB por caixa de correio e arquivamento ilimitado do Exchange Online | 
| Teams    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| OneDrive for Business    | limite de armazenamento de 1 TB por usuário    | Ilimitado | 
| Yammer, SharePoint Online, Planner, Stream    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| Gerenciador de clientes do Outlook, MileIQ    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| **Proteção contra ameaças**        | | | 
| Recursos de redução de superfície de ataque    | [Confira esta lista](#threat-protection) | Gerenciamento corporativo de isolamento baseado em hardware para o Microsoft Edge | 
| Office 365 plano de proteção avançada contra ameaças (ATP) 1 | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | Não está incluído, mas pode ser adicionado em | 
| **O gerenciamento de identidades**        | | | 
| Redefinição de senha de autoatendimento para contas híbridas do Azure Active Directory (Azure AD), autenticação multifator do Azure (MFA), acesso condicional, write-back de senha para identidades locais|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| Descoberta do Cloud app, integridade do Azure AD Connect    |     | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| Logon único (SSO) de aplicativos do Azure AD Office 365:10 aplicativos por usuário (Galeria de aplicativos SaaS como Salesforce) * | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| Azure AD Premium 1 SSO: sem limite (aplicativos locais por meio do proxy de aplicativo do Azure AD e aplicativos não-Galeria usando modelos de integração de aplicativos de autoatendimento)    |     | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| **Gerenciamento de dispositivos e aplicativos**        | | | 
| Microsoft Intune, piloto automático do Windows|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
|Acesso à área de trabalho virtual (VDA)    |  |     ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
|Área de trabalho virtual do Windows (WVD)    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png) |     ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
|Ativação de computador compartilhado (SCA)    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png) |     ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| Pacote de otimização de área de trabalho da Microsoft    | |     ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| **Proteção de informações**        | | | 
| Prevenção de perda de dados do Office 365, plano de proteção de informações do Azure 1    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| Proteção de informações da janela para o Endpoint DLP    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| **Licença de acesso para cliente (direitos de CAL)**    | | |     
| Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, gerenciamento de direitos do Windows)| |         ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| **Conformidade**        | | | 
| Arquivamento ilimitado de email    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| Pontuação de conformidade/gerente de conformidade    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| Descoberta eletrônica    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| Bloqueio in-loco e retenção de litígio    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| Marcas de retenção e políticas de retenção do MRM (gerenciamento de registros de mensagens)    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
||||

\*Os usuários aos quais foram atribuídos acesso aos aplicativos SaaS podem obter acesso SSO para até 10 aplicativos. Os administradores podem configurar o SSO e alterar o acesso de usuário para aplicativos SaaS diferentes, mas o acesso SSO só é permitido para 10 aplicativos por usuário por vez. Todos os aplicativos do Office 365 são contados como um único aplicativo.

## <a name="migration"></a>Migração

Para migrar, trabalhe com seu parceiro para transferir sua assinatura e licenças do Microsoft 365 Business Premium para uma assinatura do Microsoft 365 E3 adequada com suas licenças.

As seções a seguir descrevem as alterações que você precisa fazer, se houver, e o que você pode fazer após a migração.

### <a name="microsoft-365-subscription-configuration-and-data"></a>Dados e configuração de assinatura do Microsoft 365

Você não precisa fazer alterações na assinatura atual ou nos dados antes de migrar, o que inclui:

- Configuração de assinatura, como nomes de domínio DNS.
- Contas de usuário e de grupo e configurações de autenticação, como a autenticação multifator ou políticas de acesso condicional.
- Configurações de serviço de produtividade e seus dados, como equipes, caixas de correio do Exchange Online, sites do SharePoint Online, pastas do OneDrive for Business e blocos de anotações do OneNote.

Os usuários agora podem desfrutar de armazenamento ilimitado nas pastas caixas de correio do Exchange Online e do OneDrive for Business.

Você pode começar a usar a descoberta do Cloud app, o Azure AD Connect Health e o SSO para mais de 10 aplicativos.

>[!Note]
>Os usuários migrados para o Microsoft 365 E3 não podem mais usar o Gerenciador de clientes do Outlook e o MileIQ.
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a>Proteção contra Ameaças

O Windows 10 Business inclui estas proteções:

- Aplicação da integridade do processo de inicialização do sistema operacional
- Aplicação de integridade de componentes operacionais confidenciais
- Atenuações de vulnerabilidade avançada e de exploração de dia zero
- Proteção de rede baseada em reputação para o Microsoft Edge, o Internet Explorer e o Chrome
- Firewall baseado em host
- Atenuações de ransomware
- Isolamento baseado em hardware para o Microsoft Edge
- Controle de aplicativo equipado com o gráfico de segurança inteligente
- Controle de dispositivo (USB)
- Proteção de rede para ameaças baseadas na Web
- Regras de prevenção de invasão do host

O Windows 10 Enterprise E3 também inclui o gerenciamento corporativo de isolamento baseado em hardware para o Microsoft Edge.

>[!Note]
>Os usuários migrados para o Microsoft 365 E3 precisarão de uma licença do Office 365 ATP para proteção contínua contra ameaças. Certifique-se de adquirir licenças adicionais do Office 365 ATP para que todos os usuários no escopo de suas políticas de ATP do Office 365 sejam licenciados. 
>

### <a name="device-management-with-intune"></a>Gerenciamento de dispositivos com o Intune

Você não precisa fazer alterações na configuração atual do Intune antes de migrar, o que inclui dispositivos registrados e configurações de dispositivo e aplicativo.

### <a name="windows-10"></a>Windows 10

O Microsoft 365 Business Premium inclui o Windows 10 Business, que você pode instalar com o Windows AutoPilot. Quando você migra para o Microsoft 365 E3, cada licença de usuário inclui o Windows 10 Enterprise E3, que também pode ser instalado com o Windows AutoPilot.

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Aplicativos do Microsoft 365 para empresas

Seu Microsoft 365 aplicativos para cliente comercial instalado em seus dispositivos começará automaticamente a usar os recursos dos aplicativos da Microsoft 365 para empresas. Após a migração, agora você pode usar:

 - Ativação por volume através da diretiva de grupo
 - Telemetria de aplicativos
 - Atualizar controles
 - Comparar e consultar planilhas
 - Business intelligence

