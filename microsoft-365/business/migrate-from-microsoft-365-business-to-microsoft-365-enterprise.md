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
description: Saiba como mover sua empresa do Microsoft 365 Business Premium para o Microsoft 365 E3.
ms.openlocfilehash: 10630671f3deb7eff0ad0f601d301b90743ee35f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164504"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>Migrar do Microsoft 365 Business Premium para o Microsoft 365 E3

O Microsoft 365 Business Premium tem tudo o que você precisa para sua pequena empresa, combinando os melhores aplicativos de produtividade baseados em nuvem com gerenciamento de dispositivos simples e segurança que permitem que seus funcionários trabalhem melhor. Em alguns casos, no entanto, talvez seja necessário migrar sua assinatura do Microsoft 365 Business Premium para o Microsoft 365 E3. 

Por exemplo, sua empresa cresceu e precisa de mais de 300 licenças (parabéns, por sinal).

Ou sua empresa precisa de recursos corporativos, como Aplicativos do Microsoft 365 para empresas, Windows 10 Enterprise E3 ou Licenças de Acesso para Cliente Empresarial (CALs).

A atualização é fácil: você pode iniciar a atualização [no Centro de administração](../commerce/subscriptions/upgrade-to-different-plan.md). Todos os seus dados e configuração em sua assinatura atual são mantidos. Não há nada para você fazer para se preparar para a migração e nada para fazer depois, exceto tirar proveito dos novos recursos.

>[!Note]
>Você também pode usar uma assinatura do Microsoft 365 Business Premium para até 300 assentos e obter uma assinatura do Microsoft 365 E3 para mais de 300 assentos. No entanto, o Microsoft Defender para Office 365 não está incluído no Microsoft 365 E3. Para proteção contra ameaças contínuas, você deve adicionar licenças adicionais do Defender para o Office 365 para que todos os usuários no escopo de suas polícias do Defender para Office 365 sejam licenciados.
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Diferenças entre o Microsoft 365 Business Premium e o Microsoft 365 Enterprise

Esta tabela mostra as diferenças entre o Microsoft 365 Business Premium e o Microsoft 365 E3.

| Recurso    | Suporte no Microsoft 365 Business Premium    | Suporte no Microsoft 365 E3 | 
|:-------|:-----|:-----|
| **No local**        | | | 
| Windows 10    | Windows 10 Business  |     Windows 10 Enterprise E3| 
| Aplicativos do Office*    | [Microsoft 365 Apps para Pequenos e Médios Negócios](#office-365-business)    | Microsoft 365 Apps para Grandes Empresas | 
| **Aplicativos de produtividade na nuvem**        | | | 
| Exchange Online e Outlook    | Limite de armazenamento de 50 GB por caixa de correio e arquivamento ilimitado do Exchange Online    | Limite de armazenamento de 100 GB por caixa de correio e arquivamento ilimitado do Exchange Online | 
| Teams    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| OneDrive for Business    | Limite de armazenamento de 1 TB por usuário    | Ilimitado | 
| Yammer, SharePoint Online, Planner, Stream    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| **Proteção contra Ameaças**        | | | 
| Recursos de redução de superfície de ataque    | [Veja esta lista](#threat-protection) | Gerenciamento empresarial do isolamento baseado em hardware para o Microsoft Edge | 
| Microsoft Defender para Office 365 Plano 1 | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | Não incluído, mas pode ser adicionado em | 
| **O gerenciamento de identidades**        | | | 
| Redefinição de senha de autoatendamento para contas híbridas do Azure Active Directory (Azure AD), autenticação multifacional do Azure AD (MFA), Acesso Condicional, write-back de senha para identidades locais|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| Descoberta de aplicativos na nuvem, a saúde do Azure AD Connect    |     | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| Aplicativos do Azure AD Office 365 Single Sign-On (SSO): 10 aplicativos por usuário (aplicativos SaaS da Galeria, como Salesforce)* | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| SSO do Azure AD Premium 1: sem limite (aplicativos locais por meio do Proxy de Aplicativo do Azure AD e aplicativos que não são de galeria usando Self-Service de Integração de Aplicativos)    |     | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| **Gerenciamento de aplicativo e dispositivo**        | | | 
| Microsoft Intune, Windows Autopilot|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
|VDA (Virtual Desktop Access)    |  |     ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
|Área de trabalho virtual do Windows (WVD)    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png) |     ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
|Ativação de computador compartilhado (SCA)    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png) |     ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| Pacote de Otimização da Área de Trabalho da Microsoft    | |     ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| **Proteção de informações**        | | | 
| Prevenção contra perda de dados do Office 365, Plano 1 de Proteção de Informações do Azure    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| Proteção de Informações da Janela para DLP do ponto de extremidade    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| **Licença de Acesso para Cliente (direitos CAL)**    | | |     
| Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)| |         ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| **Conformidade**        | | | 
| Arquivamento ilimitado de email    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| Gerenciador de Conformidade    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| Descoberta eletrônica    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| Espera in-locar e manter litígio    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| Marcas de retenção e políticas de retenção mrm (gerenciamento de registros de mensagens)    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
||||

\* Os usuários que tiveram acesso aos aplicativos SaaS podem obter acesso ao SSO para até 10 aplicativos. Os administradores podem configurar o SSO e alterar o acesso do usuário a diferentes aplicativos SaaS, mas o acesso ao SSO só é permitido para 10 aplicativos por usuário por vez. Todos os aplicativos do Office 365 são contados como um único aplicativo.

## <a name="migration"></a>Migração

Para migrar, trabalhe com seu parceiro para mover sua assinatura e licenças do Microsoft 365 Business Premium para uma assinatura adequada do Microsoft 365 E3 com suas licenças.

As seções a seguir descrevem quais alterações você precisa fazer, se alguma, e o que você pode fazer após a migração.

### <a name="microsoft-365-subscription-configuration-and-data"></a>Dados e configuração de assinatura do Microsoft 365

Você não precisa fazer alterações na sua assinatura ou dados atuais antes de migrar, o que inclui:

- Configuração de assinatura, como nomes de domínio DNS.
- Contas de usuário e grupo e configurações de autenticação, como autenticação multifacional ou políticas de acesso condicional.
- Configurações de serviço de produtividade e seus dados, como Teams, caixas de correio do Exchange Online, sites do SharePoint Online, pastas do OneDrive for Business e blocos de anotações do OneNote.

Seus usuários agora podem desfrutar de armazenamento ilimitado nas caixas de correio do Exchange Online e pastas do OneDrive for Business.

Você pode começar a usar a Descoberta de Aplicativos na Nuvem, a Saúde do Azure AD Connect e o SSO para mais de 10 aplicativos.

<a name="threat-protection"></a>
### <a name="threat-protection"></a>Proteção contra ameaças

O Windows 10 Business inclui essas proteções:

- Imposição de integridade do processo de inicialização do sistema operacional
- Imposição de integridade de componentes operacionais confidenciais
- Vulnerabilidade avançada e mitigações de exploração de dia zero
- Proteção de rede baseada em reputação para Microsoft Edge, Internet Explorer e Chrome
- Firewall baseado em host
- Mitigações de ransomware
- Isolamento baseado em hardware para o Microsoft Edge
- Controle de aplicativos alimentado pelo Intelligent Security Graph
- Controle de dispositivo (USB)
- Proteção de rede para ameaças baseadas na Web
- Regras de prevenção contra intrusões de host

O Windows 10 Enterprise E3 também inclui o gerenciamento empresarial do isolamento baseado em hardware para o Microsoft Edge.

>[!Note]
>Os usuários migrados para o Microsoft 365 E3 exigirão uma licença do Microsoft Defender para Office 365 para proteção contínua contra ameaças. Certifique-se de comprar licenças adicionais do Defender para o Office 365 para que todos os usuários no escopo de suas polícias do Defender para Office 365 sejam licenciados. 
>

### <a name="device-management-with-intune"></a>Gerenciamento de dispositivos com o Intune

Você não precisa fazer alterações na configuração atual do Intune antes de migrar, o que inclui dispositivos inscritos e configurações de dispositivo e aplicativo.

### <a name="windows-10"></a>Windows 10

O Microsoft 365 Business Premium inclui o Windows 10 Business, que você pode instalar com o Windows AutoPilot. Quando você migra para o Microsoft 365 E3, cada licença de usuário inclui o Windows 10 Enterprise E3, que você também pode instalar com o Windows Autopilot.

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Microsoft 365 Apps para Pequenos e Médios negócios

Seu cliente do Microsoft 365 Apps for Business instalado em seus dispositivos começará a usar automaticamente os recursos do Microsoft 365 Apps para empresas. Após a migração, agora você pode usar:

 - Suporte à Política de Grupo
 - Comparação e consulta de planilha
 - Business intelligence

