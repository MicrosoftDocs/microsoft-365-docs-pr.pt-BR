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
ms.openlocfilehash: 019a422bb879389f42a32cf30f9a8094f776078a
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126192"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>Migrar do Microsoft 365 Business Premium para o Microsoft 365 E3

O Microsoft 365 Business Premium tem tudo o que você precisa para sua pequena empresa, combinando os melhores aplicativos de produtividade baseados em nuvem com gerenciamento de dispositivos simples e segurança que permitem que seus funcionários trabalhem melhor. Em alguns casos, no entanto, talvez seja necessário migrar sua assinatura do Microsoft 365 Business Premium para o Microsoft 365 E3. 

Por exemplo, sua empresa cresceu e precisa de mais de 300 licenças (parabéns, a propósito).

Ou, sua empresa precisa de recursos corporativos, como o Microsoft 365 Apps para empresas, Windows 10 Enterprise E3 ou Licenças de Acesso para Cliente Empresarial (CALs).

A atualização é fácil: você pode iniciar a atualização [no Centro de administração.](../commerce/subscriptions/upgrade-to-different-plan.md) Todos os seus dados e configurações em sua assinatura atual são mantidos. Não há nada a fazer para se preparar para a migração e nada a fazer depois, exceto tirar proveito dos novos recursos.

>[!Note]
>Você também pode usar uma assinatura do Microsoft 365 Business Premium para até 300 assentos e obter uma assinatura do Microsoft 365 E3 para mais de 300 assentos. No entanto, o Microsoft Defender para Office 365 não está incluído no Microsoft 365 E3. Para proteção continuada contra ameaças, você deve adicionar licenças adicionais do Defender para o Office 365 para que todos os usuários no escopo do seu Defender para as polícias do Office 365 sejam licenciados.
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Diferenças entre o Microsoft 365 Business Premium e o Microsoft 365 Enterprise

Esta tabela mostra as diferenças entre o Microsoft 365 Business Premium e o Microsoft 365 E3.

| Recurso    | Suporte no Microsoft 365 Business Premium    | Suporte no Microsoft 365 E3 | 
|:-------|:-----|:-----|
| **No local**        | | | 
| Windows 10    | Windows 10 Business  |     Windows 10 Enterprise E3| 
| Aplicativos do Office*    | [Microsoft 365 Apps para Pequenos e Médios negócios](#office-365-business)    | Microsoft 365 Apps para empresas | 
| **Aplicativos de produtividade na nuvem**        | | | 
| Exchange Online e Outlook    | Limite de armazenamento de 50 GB por caixa de correio e arquivamento ilimitado do Exchange Online    | Limite de armazenamento de 100 GB por caixa de correio e arquivamento ilimitado do Exchange Online | 
| Teams    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| OneDrive for Business    | Limite de armazenamento de 1 TB por usuário    | Ilimitado | 
| Yammer, SharePoint Online, Planner, Stream    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| MileIQ    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| **Proteção contra Ameaças**        | | | 
| Recursos de redução de superfície de ataque    | [Veja esta lista](#threat-protection) | Gerenciamento empresarial de isolamento baseado em hardware para o Microsoft Edge | 
| Defender para Office 365 Plano 1 | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | Não incluído, mas pode ser adicionado | 
| **O gerenciamento de identidades**        | | | 
| Redefinição de senha de autoatendente para contas híbridas do Azure Active Directory (Azure AD), autenticação multifacional (MFA) do Azure AD, Acesso Condicional, write-back de senha para identidades locais|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| Descoberta de aplicativos na nuvem, Azure AD Connect Health    |     | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| Aplicativos do Office 365 do Azure AD Sign-On (SSO): 10 aplicativos por usuário (aplicativos SaaS de galeria, como Salesforce)* | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| SSO do Azure AD Premium 1: sem limite (aplicativos locais por meio do Proxy de Aplicativo do Azure AD e aplicativos que não são de galeria usando Self-Service integração de aplicativos)    |     | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| **Gerenciamento de aplicativo e dispositivo**        | | | 
| Microsoft Intune, Windows Autopilot|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
|Acesso à Área de Trabalho Virtual (VDA)    |  |     ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
|Área de Trabalho Virtual do Windows (WVD)    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png) |     ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
|Ativação de Computador Compartilhado (SCA)    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png) |     ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| Pacote de Otimização da Área de Trabalho da Microsoft    | |     ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| **Proteção de informações**        | | | 
| Prevenção contra Perda de Dados do Office 365, Plano 1 de Proteção de Informações do Azure    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| Proteção de Informações do Window para o ponto de extremidade DLP    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| **Licença de Acesso para Cliente (direitos CAL)**    | | |     
| Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)| |         ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| **Conformidade**        | | | 
| Arquivamento ilimitado de email    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| Gerente de Conformidade    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| Descoberta eletrônica    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| In-place hold and litigation hold    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| Marcas de retenção MRM (Gerenciamento de Registros de Mensagens) e políticas de retenção    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
||||

\* Os usuários que têm acesso aos aplicativos SaaS podem obter acesso SSO a até 10 aplicativos. Os administradores podem configurar o SSO e alterar o acesso do usuário a diferentes aplicativos SaaS, mas o acesso ao SSO só é permitido para 10 aplicativos por usuário por vez. Todos os aplicativos do Office 365 são contados como um único aplicativo.

## <a name="migration"></a>Migração

Para migrar, trabalhe com seu parceiro para migrar sua assinatura e licenças do Microsoft 365 Business Premium para uma assinatura adequada do Microsoft 365 E3 com suas licenças.

As seções a seguir descrevem quais alterações você precisa fazer, se alguma, e o que você pode fazer após a migração.

### <a name="microsoft-365-subscription-configuration-and-data"></a>Dados e configuração de assinatura do Microsoft 365

Você não precisa fazer alterações em sua assinatura atual ou dados antes de migrar, o que inclui:

- Configuração de assinatura, como nomes de domínio DNS.
- Configurações de autenticação e contas de usuários e grupos, como autenticação multifacional ou políticas de acesso condicional.
- Configurações do serviço de produtividade e seus dados, como equipes, caixas de correio do Exchange Online, sites do SharePoint Online, pastas do OneDrive for Business e blocos de anotações do OneNote.

Os usuários agora podem aproveitar o armazenamento ilimitado nas caixas de correio do Exchange Online e nas pastas do OneDrive for Business.

Você pode começar a usar a Descoberta de Aplicativo na Nuvem, o Azure AD Connect Health e o SSO para mais de 10 aplicativos.

>[!Note]
>Os usuários migrados para o Microsoft 365 E3 não podem mais usar MileIQ.
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a>Proteção contra Ameaças

O Windows 10 Business inclui estas proteções:

- Imposição de integridade do processo de inicialização do sistema operacional
- Imposição de integridade de componentes operacionais confidenciais
- Vulnerabilidade avançada e mitigações de exploração de dia zero
- Proteção de rede baseada em reputação para Microsoft Edge, Internet Explorer e Chrome
- Firewall baseado em host
- Mitigações de ransomware
- Isolamento baseado em hardware para o Microsoft Edge
- Controle de aplicativo da plataforma do Gráfico de Segurança Inteligente
- Controle de dispositivo (USB)
- Proteção de rede para ameaças baseadas na Web
- Regras de prevenção contra invasões de host

O Windows 10 Enterprise E3 também inclui o gerenciamento corporativo de isolamento baseado em hardware para o Microsoft Edge.

>[!Note]
>Os usuários migrados para o Microsoft 365 E3 exigirão uma licença do Microsoft Defender para Office 365 para proteção continuada contra ameaças. Certifique-se de comprar licenças adicionais do Defender para o Office 365 para que todos os usuários no escopo do seu Defender para as polícias do Office 365 sejam licenciados. 
>

### <a name="device-management-with-intune"></a>Gerenciamento de dispositivos com o Intune

Você não precisa fazer alterações em sua configuração atual do Intune antes de migrar, o que inclui dispositivos inscritos e configurações de dispositivos e aplicativos.

### <a name="windows-10"></a>Windows 10

O Microsoft 365 Business Premium inclui o Windows 10 Business, que você pode instalar com o Windows AutoPilot. Quando você migra para o Microsoft 365 E3, cada licença de usuário inclui o Windows 10 Enterprise E3, que você também pode instalar com o Windows Autopilot.

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Microsoft 365 Apps para Pequenos e Médios negócios

Seu cliente do Microsoft 365 Apps para Empresas instalado em seus dispositivos começará automaticamente a usar os recursos do Microsoft 365 Apps para empresas. Após a migração, você pode usar:

 - Suporte à Política de Grupo
 - Comparação e pesquisa de planilhas
 - Business intelligence

