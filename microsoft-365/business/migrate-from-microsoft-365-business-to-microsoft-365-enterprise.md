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
description: Saiba como mover sua empresa de Microsoft 365 Business Premium para Microsoft 365 E3.
ms.openlocfilehash: 6502d79dbb283db37b00e4fccf89b15ab4291ce5
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227610"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>Migrar do Microsoft 365 Business Premium para o Microsoft 365 E3

Microsoft 365 Business Premium tem tudo o que você precisa para sua pequena empresa, combinando os melhores aplicativos de produtividade baseados em nuvem com gerenciamento de dispositivos simples e segurança que permitem que seus funcionários trabalhem melhor. Em alguns casos, no entanto, talvez seja necessário migrar sua assinatura Microsoft 365 Business Premium para Microsoft 365 E3.

Por exemplo, sua empresa cresceu e precisa de mais de 300 licenças (parabéns, por sinal).

Ou, sua empresa precisa de recursos corporativos, como Microsoft 365 Apps para Grandes Empresas, Windows 10 Enterprise E3 ou Enterprise De Acesso para Cliente (CALs).

A atualização é fácil: você pode iniciar a atualização [no Centro de administração](../commerce/subscriptions/upgrade-to-different-plan.md). Todos os seus dados e configuração em sua assinatura atual são mantidos. Não há nada para você fazer para se preparar para a migração e nada para fazer depois, exceto tirar proveito dos novos recursos.

> [!NOTE]
> Você também pode usar uma assinatura Microsoft 365 Business Premium para até 300 assentos e obter uma assinatura Microsoft 365 E3 para mais de 300 assentos. No entanto, o Microsoft Defender para Office 365 não está incluído no Microsoft 365 E3. Para proteção contra ameaças contínuas, você deve adicionar licenças adicionais do Defender para Office 365 para que todos os usuários no escopo do seu Defender para Office 365 polícias sejam licenciados.

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Diferenças entre Microsoft 365 Business Premium e Microsoft 365 Enterprise

Esta tabela mostra as diferenças entre Microsoft 365 Business Premium e Microsoft 365 E3.

| Recurso    | Suporte em Microsoft 365 Business Premium    | Suporte no Microsoft 365 E3 |
|:-------|:-----|:-----|
| **No local**        | | |
| Windows 10    | Windows 10 Business  |     Windows 10 Enterprise E3|
| Office aplicativos*    | [Microsoft 365 Apps para Pequenos e Médios Negócios](#office-365-business)    | Microsoft 365 Apps para Grandes Empresas |
| **Aplicativos de produtividade na nuvem**        | | |
| Exchange Online e Outlook    | Limite de armazenamento de 50 GB por caixa de correio e Exchange Online arquivamento ilimitado    | Limite de armazenamento de 100 GB por caixa de correio e arquivamento Exchange Online ilimitado |
| Teams    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) |
| OneDrive for Business    | Limite de armazenamento de 1 TB por usuário    | Ilimitado |
| Yammer, SharePoint Online, Planner, Stream    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) |
| **Proteção contra Ameaças**        | | |
| Recursos de redução de superfície de ataque    | [Veja esta lista](#threat-protection) | Enterprise gerenciamento de isolamento baseado em hardware para Microsoft Edge |
| Microsoft Defender para Office 365 Plano 1 | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | Não incluído, mas pode ser adicionado em |
| **O gerenciamento de identidades**        | | |
| Redefinição de senha de autoatenduro para contas Azure Active Directory (Azure AD), autenticação multifacional do Azure AD (MFA), Acesso Condicional, write-back de senha para identidades locais|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) |
| Descoberta de aplicativos na nuvem, Azure AD Conexão saúde    |     | ![Incluído no Microsoft 365 E3](../media/check-mark.png) |
| Azure AD Office 365 aplicativo Sign-On s SSO (SSO): 10 aplicativos por usuário (aplicativos SaaS da Galeria, como Salesforce)* | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) |
| Azure AD Premium 1 SSO: sem limite (aplicativos locais por meio do Proxy de Aplicativos do Azure AD e aplicativos que não são de galeria usando Self-Service de Integração de Aplicativos)    |     | ![Incluído no Microsoft 365 E3](../media/check-mark.png) |
| **Gerenciamento de aplicativo e dispositivo**        | | |
| Microsoft Intune, Windows Piloto Automático|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) |
|VDA (Virtual Desktop Access)    |  |     ![Incluído no Microsoft 365 E3](../media/check-mark.png) |
|Windows Área de trabalho virtual (WVD)    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png) |     ![Incluído no Microsoft 365 E3](../media/check-mark.png) |
|Ativação de computador compartilhado (SCA)    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png) |     ![Incluído no Microsoft 365 E3](../media/check-mark.png) |
| Pacote de Otimização da Área de Trabalho da Microsoft    | |     ![Incluído no Microsoft 365 E3](../media/check-mark.png) |
| **Proteção de informações**        | | |
| Office 365 Prevenção contra perda de dados, Plano 1 de Proteção de Informações do Azure    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) |
| Proteção de Informações da Janela para DLP do ponto de extremidade    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) |
| **Licença de Acesso para Cliente (direitos CAL)**    | | |
| Enterprise Pacote CAL (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Gerenciamento de Direitos)| |         ![Incluído no Microsoft 365 E3](../media/check-mark.png) |
| **Conformidade**        | | |
| Arquivamento ilimitado de email    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) |
| Gerenciador de Conformidade    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) |
| Descoberta eletrônica    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) |
| Espera in-locar e manter litígio    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) |
| Marcas de retenção e políticas de retenção mrm (gerenciamento de registros de mensagens)    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) |
||||

\* Os usuários que tiveram acesso aos aplicativos SaaS podem obter acesso ao SSO para até 10 aplicativos. Os administradores podem configurar o SSO e alterar o acesso do usuário a diferentes aplicativos SaaS, mas o acesso ao SSO só é permitido para 10 aplicativos por usuário por vez. Todos Office 365 aplicativos são contados como um único aplicativo.

## <a name="migration"></a>Migração

Para migrar, trabalhe com seu parceiro para mover sua assinatura Microsoft 365 Business Premium e licenças para uma assinatura Microsoft 365 E3 com suas licenças.

As seções a seguir descrevem quais alterações você precisa fazer, se alguma, e o que você pode fazer após a migração.

### <a name="microsoft-365-subscription-configuration-and-data"></a>Microsoft 365 configuração e dados de assinatura

Você não precisa fazer alterações na sua assinatura ou dados atuais antes de migrar, o que inclui:

- Configuração de assinatura, como nomes de domínio DNS.
- Contas de usuário e grupo e configurações de autenticação, como autenticação multifacional ou políticas de acesso condicional.
- Configurações de serviço de produtividade e seus dados, como Teams, caixas de correio Exchange Online, sites do SharePoint Online, pastas OneDrive for Business e OneNote blocos de anotações.

Seus usuários agora podem desfrutar de armazenamento ilimitado nas caixas de correio Exchange Online e OneDrive for Business pastas.

Você pode começar a usar o Cloud App Discovery, o Azure AD Conexão Health e o SSO para mais de 10 aplicativos.

<a name="threat-protection"></a>
### <a name="threat-protection"></a>Proteção contra ameaças

Windows 10 Business inclui essas proteções:

- Imposição de integridade do processo de inicialização do sistema operacional
- Imposição de integridade de componentes operacionais confidenciais
- Vulnerabilidade avançada e mitigações de exploração de dia zero
- Proteção de rede baseada em reputação para Microsoft Edge, Internet Explorer e Chrome
- Firewall baseado em host
- Mitigações de ransomware
- Isolamento baseado em hardware para Microsoft Edge
- Controle de aplicativos alimentado pela segurança inteligente Graph
- Controle de dispositivo (USB)
- Proteção de rede para ameaças baseadas na Web
- Regras de prevenção contra intrusões de host

Windows 10 Enterprise O E3 também inclui o gerenciamento empresarial do isolamento baseado em hardware para Microsoft Edge.

> [!NOTE]
> Os usuários migrados para Microsoft 365 E3 exigirão uma licença do Microsoft Defender para Office 365 proteção contra ameaças contínuas. Certifique-se de comprar licenças adicionais do Defender Office 365 para que todos os usuários no escopo do defender para Office 365 polícias sejam licenciados.

### <a name="device-management-with-intune"></a>Gerenciamento de dispositivos com o Intune

Você não precisa fazer alterações na configuração atual do Intune antes de migrar, o que inclui dispositivos inscritos e configurações de dispositivo e aplicativo.

### <a name="windows-10"></a>Windows 10

Microsoft 365 Business Premium inclui Windows 10 Business, que você pode instalar com Windows AutoPilot. Quando você migra para Microsoft 365 E3, cada licença de usuário inclui Windows 10 Enterprise E3, que você também pode instalar com o Windows Autopilot.

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Aplicativos do Microsoft 365 para empresas

Seu Microsoft 365 Apps para Pequenos e Médios negócios cliente instalado em seus dispositivos começará automaticamente a usar os recursos de Microsoft 365 Apps para Grandes Empresas. Após a migração, agora você pode usar:

- Suporte à Política de Grupo
- Comparação e consulta de planilha
- Business intelligence
