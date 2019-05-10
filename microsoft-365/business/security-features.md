---
title: Recursos de segurança do Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Saiba mais sobre os recursos de segurança que acompanham o Microsoft 365 Business.
ms.openlocfilehash: adf1cf183022f3d2c19364b9f60868e285f78637
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660501"
---
# <a name="microsoft-365-business-security-features"></a>Recursos de segurança do Microsoft 365 Business

O Microsoft 365 Business oferece recursos simplificados de segurança para ajudar a proteger seus dados em PCs, telefones e tablets.
    
## <a name="microsoft-365-business-admin-center-security-features"></a>Recursos de segurança do centro de administração de negócios da Microsoft 365

![Faixa que aponta para https://aka.ms/aboutM365preview.](media/m365admincenterchanging.png)

Você pode gerenciar muitos dos recursos de segurança de negócios do Microsoft 365 no centro de administração, que oferece uma maneira simplificada para ativar ou desativar esses recursos. No centro de administração, você pode fazer o seguinte:
  
![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
- [Definir configurações de gerenciamento de aplicativo para dispositivos Android ou Ios](app-protection-settings-for-android-and-ios.md) . 
    
    Essas configurações incluem a exclusão de arquivos de um dispositivo inativo após um período definido, a criptografia de arquivos de trabalho, exigindo que os usuários definam um PIN, etc.
    
- [Definir configurações de proteção de aplicativo para dispositivos Windows 10](protection-settings-for-windows-10-devices.md) . 
    
    Essas configurações podem ser aplicadas a dados da empresa em dispositivos pertencentes à empresa ou de propriedade pessoal.
    
- [Definir configurações de proteção de dispositivos para dispositivos Windows 10](protection-settings-for-windows-10-pcs.md) . 
    
    Você pode habilitar a criptografia [BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405) para ajudar a proteger os dados caso um dispositivo seja perdido ou roubado, e permitir que o [Windows Exploit Guard](https://go.microsoft.com/fwlink/p/?linkid=871404) forneça proteção avançada contra o ransomware. 
    
- [Remover dados da empresa de dispositivos](remove-company-data.md)
    
    Você pode limpar dados da empresa remotamente se um dispositivo for perdido, roubado ou se um funcionário sair da sua empresa.
    
- [Redefina dispositivos Windows 10 para suas configurações de fábrica](reset-devices-to-factory-settings.md) . 
    
    Você pode redefinir qualquer dispositivo Windows 10 que tenha as configurações de proteção de dispositivo aplicadas a eles.
    
## <a name="additional-security-features"></a>Recursos de segurança adicionais 

Recursos avançados no Microsoft 365 Business estão disponíveis para ajudá-lo a proteger sua empresa contra ameaças e proteger as informações confidenciais.
  
- **[Proteção Avançada contra Ameaças do Office 365](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)**
    
    A proteção avançada contra ameaças (ATP) ajuda a proteger sua empresa contra ataques sofisticados de phishing e ransomware, projetados para comprometer informações de funcionários ou clientes. Os recursos incluem:
    
  - Análise de conexão sofisticada e análise com alimentação de AI para detectar e descartar mensagens perigosas.
    
  - Verificações automáticas de links da Web em email para avaliar se eles fazem parte de um esquema de phishing. Isso impede você de acessar sites não seguros.
    
- **[Visão geral das políticas de prevenção contra perda de dados](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)** (DLP). 
    
    Você pode configurar o DLP para detectar automaticamente informações confidenciais, como números de cartão de crédito, números de seguridade social, etc. para impedir o compartilhamento inadvertido fora da empresa.
    
- **[Arquivamento do Exchange Online](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    A licença de arquivamento do Exchange Online permite que as mensagens sejam facilmente arquivadas com o backup contínuo de dados. Ele armazena todos os emails de um usuário, incluindo itens excluídos, caso eles sejam necessários posteriormente para descoberta ou restauração. Além disso, você pode usar diferentes políticas de retenção para preservar dados de email para litígios, eDiscovery ou para atender aos requisitos de conformidade.
    
- **[Proteção de Informações do Azure](https://go.microsoft.com/fwlink/p/?linkid=871406)**
    
    A proteção de informações ajuda você a controlar o acesso a informações confidenciais em emails e documentos com controles como "não encaminhar" e "não copiar". Você também pode classificar informações confidenciais como "confidencial" e especificar como as informações classificadas podem ser compartilhadas fora e dentro da empresa. A criptografia de nível empresarial é fácil de aplicar a emails e documentos para manter suas informações privadas. O Microsoft 365 Business inclui todos os recursos do [plano de proteção de informações do Azure 1](https://go.microsoft.com/fwlink/p/?linkid=871407). Você também pode instalar o suplemento cliente de proteção de informações do Azure para aplicativos do Office. Para obter mais detalhes, consulte [Azure Information Protection Client admininstrator Guide](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide).
    
- **[Os recursos completos do Intune no portal do Azure](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    Acessar o centro de administração do Intune no portal do Azure permite que você configure recursos de segurança adicionais, como o gerenciamento de dispositivos MacOS, iPhone e dispositivos Android, juntamente com o gerenciamento avançado de dispositivos do Windows, que não estão disponíveis no Microsoft 365 centro de administração de negócios.
    
As seções a seguir descrevem como você pode gerenciar esses recursos no centro &amp; de conformidade de segurança e no centro de administração do Intune. Com o tempo, os controles simplificados serão adicionados ao centro de administração de negócios do Microsoft 365.
  
    
## <a name="faq"></a>Perguntas frequentes

 ### <a name="are-these-security-features-available-in-all-markets"></a>Esses recursos de segurança estão disponíveis em todos os mercados?
  
Sim, esses recursos estão disponíveis em todos os mercados onde o Microsoft 365 Business é vendido.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>Como localizar o centro de conformidade &amp; de segurança?
  
1. [Entre no Microsoft 365 Business](https://portal.microsoft.com/) usando suas credenciais de administrador. 
    
2. No painel de navegação à esquerda, localize **centros de administração** e expanda-o. 
    
    ![No painel de navegação esquerdo do centro de administração do Microsoft 365, escolha centros de administração.](media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. Escolha **conformidade &amp; de segurança** para acessar o &amp; centro de conformidade de segurança.