---
title: Recursos de conformidade e segurança de negócios da Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Saiba mais sobre os recursos de segurança que acompanham o Microsoft 365 Business.
ms.openlocfilehash: 0e1823374ec1843b6caa3f080393ca013302bf72
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593416"
---
# <a name="microsoft-365-business-security-and-compliance-features"></a>Recursos de conformidade e segurança de negócios da Microsoft 365

O Microsoft 365 Business oferece recursos simplificados de segurança para ajudar a proteger seus dados em PCs, telefones e tablets.
    
## <a name="microsoft-365-business-admin-center-security-features"></a>Recursos de segurança do centro de administração de negócios da Microsoft 365

[![Rótulo para informar que o centro de administração está mudando e você pode encontrar mais detalhes em aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Você pode gerenciar muitos dos recursos de segurança de negócios do Microsoft 365 no centro de administração, que oferece uma maneira simplificada para ativar ou desativar esses recursos. No centro de administração, você pode fazer o seguinte:
  
- [Definir configurações de gerenciamento de aplicativo para dispositivos Android ou Ios](app-protection-settings-for-android-and-ios.md) . 
    
    Essas configurações incluem a exclusão de arquivos de um dispositivo inativo após um período definido, a criptografia de arquivos de trabalho, exigindo que os usuários definam um PIN e assim por diante.
    
- [Definir configurações de proteção de aplicativo para dispositivos Windows 10](protection-settings-for-windows-10-devices.md) . 
    
    Essas configurações podem ser aplicadas a dados da empresa em dispositivos pertencentes à empresa ou pessoais.
    
- [Definir configurações de proteção de dispositivos para dispositivos Windows 10](protection-settings-for-windows-10-pcs.md) . 
    
    Você pode habilitar a criptografia [BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405) para ajudar a proteger os dados caso um dispositivo seja perdido ou roubado, e permitir que o [Windows Exploit Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-exploit-protection) forneça proteção avançada contra o ransomware. 
    
- [Remover dados da empresa de dispositivos](remove-company-data.md)
    
    Você pode limpar dados da empresa remotamente se um dispositivo for perdido, roubado ou se um funcionário sair da sua empresa.
    
- [Redefina dispositivos Windows 10 para suas configurações de fábrica](reset-devices-to-factory-settings.md) . 
    
    Você pode redefinir qualquer dispositivo Windows 10 que tenha as configurações de proteção de dispositivo aplicadas a eles.
    
## <a name="additional-security-features"></a>Recursos de segurança adicionais 

Recursos avançados no Microsoft 365 Business estão disponíveis para ajudá-lo a proteger sua empresa contra ameaças e proteger as informações confidenciais.
  
- **[Proteção Avançada contra Ameaças do Office 365](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)**
    
    A proteção avançada contra ameaças (ATP) ajuda a proteger sua empresa contra ataques sofisticados de phishing e ransomware, projetados para comprometer informações de funcionários ou clientes. Os recursos incluem:
    
  - Análise de conexão sofisticada e análise com alimentação de AI para detectar e descartar mensagens perigosas.
    
  - Verificações automáticas de links em email para avaliar se eles fazem parte de um esquema de phishing. Isso impede você de acessar sites não seguros.

- **[Os recursos completos do Intune no portal do Azure](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    Acessar o centro de administração do Intune no portal do Azure permite que você configure recursos de segurança adicionais, como gerenciamento de dispositivos MacOS, iPhone e dispositivos Android, juntamente com o gerenciamento avançado de dispositivos do Windows, que não está disponível através da Microsoft 365 centro de administração de negócios.
- **Mesmo [acesso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) que o plano P1 do Azure AD**


    O acesso condicional pode ajudar a proteger sua organização contra o risco de entrada, as tentativas de acesso de uma rede ou localidade inesperada, o acesso tenta de tipos de dispositivos arriscados e assim por diante. As políticas de acesso condicional são aplicadas depois que a primeira autenticação é concluída e usa sinais do primeiro evento de autenticação para determinar se o acesso tentado deve ser aprovado, negado ou se for mais uma prova (como uma segunda forma de identificação) é necessário.

    Os recursos de acesso condicional incluídos são:

    - Acesso com base no nome de usuário, grupo e função
    - Acesso [baseado em um aplicativo](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access) 
    - [Acesso com base no local](https://docs.microsoft.com/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration);  Só permitir o acesso de intervalos de IP confiáveis ou países específicos 
    - Exigir MFA para acesso
    - Bloquear o acesso a aplicativos que usam [autenticação herdada](https://docs.microsoft.com/azure/active-directory/conditional-access/block-legacy-authentication)
    - Exigir que os aplicativos usem a [proteção de aplicativo do Intune](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)
    - Autenticação personalizada, como a MFA, com provedores terceirizados, por exemplo, DUO.
   
    Outros recursos
    - [Redefinição de senha de autoatendimento](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-customization) para o Azure ad híbrido
    
## <a name="compliance-features"></a>Recursos de conformidade

Sua assinatura do Microsoft 365 Business inclui recursos que ajudam você a manter padrões de conformidade e regulamentações.

- **[Visão geral das políticas de prevenção contra perda de dados](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)** (DLP). 
    
    Você pode configurar a DLP para detectar automaticamente informações confidenciais, como números de cartão de crédito, números de seguridade social e assim por diante, para evitar o compartilhamento inadvertido fora da empresa.
    
- **[Arquivamento do Exchange Online](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    A licença de arquivamento do Exchange Online permite que as mensagens sejam facilmente arquivadas com o backup contínuo de dados. Ele armazena todos os emails de um usuário, incluindo itens excluídos, caso eles sejam necessários posteriormente para descoberta ou restauração. Além disso, você pode usar diferentes políticas de retenção para preservar dados de email para litígios, eDiscovery ou para atender aos requisitos de conformidade.
    
- **[Rótulos de confidencialidade](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)**

   O Microsoft 365 Business inclui todos os recursos do [plano de proteção de informações do Azure 1](https://go.microsoft.com/fwlink/p/?linkid=871407). Com esse plano, você pode criar **Rótulos de confidencialidade** que permitem controlar o acesso a informações confidenciais em emails e documentos, com controles como "não encaminhar" e "não copiar". Você também pode classificar informações confidenciais como "confidencial" e especificar como as informações classificadas podem ser compartilhadas fora e dentro da empresa. A criptografia de nível empresarial é fácil de aplicar a emails e documentos para manter suas informações privadas. Você também pode instalar o suplemento cliente de proteção de informações do Azure para aplicativos do Office. Para obter mais informações, consulte [cliente de rotulação unificado de proteção de informações do Azure](https://docs.microsoft.com/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history). Para rótulos de confidencialidade, instale o **AzInfoProtection_UL. exe**.

Você pode gerenciar esses recursos no centro de &amp; conformidade de segurança e no centro de administração do Intune. Com o tempo, os controles simplificados serão adicionados ao centro de administração de negócios do Microsoft 365.
  
    
## <a name="faq"></a>Perguntas frequentes

 ### <a name="are-these-security-features-available-in-all-markets"></a>Esses recursos de segurança estão disponíveis em todos os mercados?
  
Sim, esses recursos estão disponíveis em todos os mercados onde o Microsoft 365 Business é vendido.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>Como localizar o centro de conformidade &amp; de segurança?
  
1. [Entre no Microsoft 365 Business](https://portal.microsoft.com/) usando suas credenciais de administrador. 
    
2. No painel de navegação à esquerda, localize **centros de administração** e expanda-o. 
    
    ![No painel de navegação esquerdo do centro de administração do Microsoft 365, escolha centros de administração.](media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. Escolha **conformidade &amp; de segurança** para acessar o &amp; centro de conformidade de segurança.
