---
title: Microsoft 365 Business Premium segurança e conformidade
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-security-compliance
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Saiba mais sobre os recursos de segurança que vêm com Microsoft 365 Business Premium ajudar a proteger seus dados em computadores, telefones e tablets.
ms.openlocfilehash: 974204e100d3228f78406aca4acce67a889b08c3
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52113457"
---
# <a name="microsoft-365-business-premium-security-and-compliance-features"></a>Microsoft 365 Business Premium segurança e conformidade

Microsoft 365 Business Premium oferece recursos de segurança simplificados para ajudar a proteger seus dados em computadores, telefones e tablets.
    
## <a name="microsoft-365-admin-center-security-features"></a>Microsoft 365 de segurança do centro de administração

Você pode gerenciar muitos dos recursos Microsoft 365 Business Premium segurança no centro de administração, o que oferece uma maneira simplificada de ativar ou desativar esses recursos. No centro de administração, você pode fazer o seguinte:
  
- [Definir configurações de gerenciamento de aplicativos para dispositivos Android ou iOS.](app-protection-settings-for-android-and-ios.md) 
    
    Essas configurações incluem a exclusão de arquivos de um dispositivo inativo após um período definido, a criptografia de arquivos de trabalho, a exigência de que os usuários deem um PIN e assim por diante.
    
- [Definir configurações de proteção de aplicativo para Windows 10 dispositivos](protection-settings-for-windows-10-devices.md) . 
    
    Essas configurações podem ser aplicadas aos dados da empresa em dispositivos de propriedade da empresa ou pessoais.
    
- [Definir configurações de proteção de dispositivo para Windows 10 dispositivos](protection-settings-for-windows-10-pcs.md) . 
    
    Você pode habilitar [BitLocker](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions) criptografia para ajudar a proteger dados no caso de um dispositivo ser perdido ou roubado e permitir que Windows [Exploit Guard](/windows/security/threat-protection/microsoft-defender-atp/enable-exploit-protection) forneça proteção avançada contra ransomware. 
    
- [Remover dados da empresa de dispositivos](remove-company-data.md)
    
    Você pode apagar remotamente os dados da empresa se um dispositivo for perdido, roubado ou um funcionário sair da empresa.
    
- [Redefinir Windows 10 dispositivos para suas configurações de fábrica.](reset-devices-to-factory-settings.md) 
    
    Você pode redefinir qualquer Windows 10 que tenham configurações de proteção de dispositivo aplicadas a eles.
    
## <a name="additional-security-features"></a>Recursos de segurança adicionais 

Recursos avançados do Microsoft 365 Business Premium estão disponíveis para ajudá-lo a proteger sua empresa contra ameaças cibernéticas e proteger informações confidenciais.
  
- **[Microsoft Defender para Office 365](../security/office-365-security/defender-for-office-365.md)**
    
    O Microsoft Defender for Office 365 ajuda a proteger seus negócios contra ataques sofisticados de phishing e ransomware projetados para comprometer informações de funcionários ou clientes. Os recursos incluem:
    
  - Análise sofisticada de anexos e análise com AI para detectar e descartar mensagens perigosas.
    
  - Verificações automáticas de links no email para avaliar se eles fazem parte de um esquema de phishing. Isso impede que você acesse sites não seguros.

- **[Os recursos completos do Intune no portal do Azure](/mem/intune/fundamentals/what-is-intune)**
    
    Acessar o centro de administração do Intune no portal do Azure permite configurar recursos de segurança adicionais, como o gerenciamento de dispositivos MacOS, dispositivos iPhone e Dispositivos Android, juntamente com o gerenciamento avançado de dispositivos para Windows, que não estão disponíveis por meio do centro de administração do Microsoft 365.
- **Mesmo [Acesso Condicional do](/azure/active-directory/conditional-access/overview) Azure AD Premium plano P1**


    O Acesso Condicional pode ajudar a proteger sua organização contra riscos de entrada, tentativas de acesso de uma rede ou localidade inesperada, tentativas de acesso de tipos de dispositivos arriscados e assim por diante. As políticas de Acesso Condicional são impostas após a conclusão da primeira autenticação e ela usa sinais do primeiro evento de autenticação para determinar se a tentativa de acesso deve ser aprovada, negada ou se mais provas (como uma segunda forma de identificação) são necessárias.

    Os recursos de acesso condicional incluídos são:

    - Acesso com base no nome de usuário, grupo e função
    - Acesso [com base em um aplicativo](/azure/active-directory/conditional-access/app-based-conditional-access) 
    - [Acesso com base no local;](/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration)  permitir apenas o acesso de intervalos IP confiáveis ou países específicos 
    - Exigir MFA para acesso
    - Bloquear o acesso a aplicativos que usam [autenticação herdda](/azure/active-directory/conditional-access/block-legacy-authentication)
    - Exigir que os aplicativos usem a [proteção de aplicativos do Intune](/azure/active-directory/conditional-access/app-protection-based-conditional-access)
    - Autenticação personalizada, como MFA com provedores de terceiros, por exemplo, DUO.
   
    Outros recursos
    - [Redefinição de senha de autoatendamento](/azure/active-directory/authentication/concept-sspr-customization) para o Azure AD híbrido
    
## <a name="compliance-features"></a>Recursos de conformidade

Sua Microsoft 365 Business Premium inclui recursos que ajudam você a manter a conformidade e os padrões regulatórios.

- **[Saiba mais sobre prevenção contra perda de dados](../compliance/dlp-learn-about-dlp.md))** (DLP). 
    
    Você pode configurar a DLP para detectar automaticamente informações confidenciais, como números de cartão de crédito, números de previdência social e assim por diante, para impedir o compartilhamento inadvertido fora da empresa.
    
- **[Arquivamento do Exchange Online](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Arquivamento do Exchange Online permite que as mensagens sejam facilmente arquivadas com backup contínuo de dados. Ele armazena todos os emails de um usuário, incluindo itens excluídos, caso eles são necessários posteriormente para descoberta ou restauração. Além disso, você pode usar políticas de retenção diferentes para preservar dados de email para retenção de litígio, Descoberta Eletrônico ou para atender aos requisitos de conformidade.
    
- **[Rótulos de confidencialidade](../compliance/sensitivity-labels.md)**

   Microsoft 365 Business Premium inclui todos os recursos do Plano de Proteção de Informações do [Azure 1](https://go.microsoft.com/fwlink/p/?linkid=871407). Com esse plano,  você pode criar rótulos de Sensibilidade que permitem controlar o acesso a informações confidenciais em emails e documentos, com controles como "Não encaminhar" e "Não copiar". Você também pode classificar informações confidenciais como "Confidenciais" e especificar como informações confidenciais podem ser compartilhadas fora e dentro da empresa. Enterprise criptografia de grau é fácil de aplicar a emails e documentos para manter suas informações privadas. Você também pode instalar o complemento do cliente de Proteção de Informações do Azure para Office aplicativos. Para saber mais, consulte o [cliente de rótulos unificado da Proteção de Informações do Microsoft Azure](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history). Para rótulos de sensibilidade, instale o **AzInfoProtection_UL.exe**.

Você pode gerenciar esses recursos no Centro de &amp; Conformidade e Segurança do Centro de administração do Intune. Com o tempo, os controles simplificados serão adicionados ao Microsoft 365 de administração.
  
    
## <a name="faq"></a>Perguntas frequentes

 ### <a name="are-these-security-features-available-in-all-markets"></a>Esses recursos de segurança estão disponíveis em todos os mercados?
  
Sim, esses recursos estão disponíveis em todos os mercados onde Microsoft 365 Business Premium é vendido.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>Como encontro o Centro de &amp; Conformidade e Segurança?
  
1. [Entre no Microsoft 365 Business Premium](https://portal.microsoft.com/) usando suas credenciais de administrador. 
    
2. Na nav esquerda, localize **centros de administração e** expanda-o. 
    
    ![Na nav esquerda no centro de administração Microsoft 365, escolha Centros de administração.](../media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. Escolha **Conformidade &amp; de Segurança** para ir para o Centro de Conformidade e &amp; Segurança.
