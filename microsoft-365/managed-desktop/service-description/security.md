---
title: Segurança na área de trabalho gerenciada da Microsoft
description: ''
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 6d3be89b52d71543687a02a1fd3fbae8bc1543f8
ms.sourcegitcommit: 4460975970ae13e917d4d336e92dbd76ae26493b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243932"
---
# <a name="security-in-microsoft-managed-desktop"></a>Segurança na área de trabalho gerenciada da Microsoft

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

O Microsoft Managed desktop usa várias tecnologias da Microsoft para ajudar a proteger os dispositivos e dados gerenciados. Especificamente: 

- [Segurança de dados](#data-security) -tipos de dados coletados pela área de trabalho gerenciada da Microsoft e onde eles são armazenados com segurança
- [Segurança do dispositivo](#device-security) – segurança e proteção nos dispositivos de área de trabalho gerenciada da Microsoft
- [Gerenciamento de identidade e acesso](#identity-and-access-management) – Gerenciando o uso seguro de dispositivos por meio do Azure Active Directory Identity Services
- [Segurança de rede](#network-security) – informações de VPN e configurações e soluções recomendadas do Microsoft Managed desktop
- [Segurança de informações](#information-security) – serviços opcionais disponíveis para proteger ainda mais as informações confidenciais 

## <a name="data-security"></a>Segurança de dados

Os dados coletados de locatários do cliente (que permite que os serviços e operações de ti da área de trabalho gerenciada da Microsoft) são armazenados em bancos de dados do Azure SQL no Microsoft locatário hospedado nos Estados Unidos da América.

Para obter mais informações, consulte [segurança do Microsoft Azure](https://docs.microsoft.com/azure/security/azure-database-security-overview).

Listadas abaixo estão os tipos de dados transmitidos do locatário:

- Dados de atualização de dispositivo, uso e confiabilidade
- Dados de implantação e confiabilidade de aplicativos
- Atualização e dados de implantação de política de segurança
- Usuários atribuídos a dispositivos
- Logs de segurança de seu locatário relacionado às contas usadas pela área de trabalho gerenciada pela Microsoft para gerenciar o serviço



## <a name="device-security"></a>Segurança do dispositivo

O Microsoft Managed desktop garante que todos os dispositivos gerenciados estão protegidos e protegidos e detecta ameaças o mais cedo possível, usando os seguintes serviços:

Serviço | Descrição
--- | ---
Antivírus | O Microsoft defender AV está instalado e configurado<br>As definições de AV do Microsoft defender estão atualizadas
Criptografia de volume completo |    O Windows BitLocker é a solução de criptografia de volume para dispositivos de área de trabalho gerenciada da Microsoft.<br><br>Depois que uma organização é integrada ao serviço, os dispositivos serão criptografados usando o Windows BitLocker com o módulo de plataforma de confiança (TPM) interno para impedir o acesso não autorizado a dados locais quando o dispositivo estiver no modo de suspensão ou desativado. 
Monitoramento |    A proteção avançada contra ameaças do Microsoft defender (Microsoft defender ATP) é usada para monitoramento de ameaças de segurança em todos os dispositivos de área de trabalho gerenciado da Microsoft. O Microsoft defender ATP permite que os clientes corporativos detectem, investiguem e respondam a ameaças avançadas em sua rede corporativa. Para obter mais informações, consulte [proteção avançada contra ameaças do Microsoft defender.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
Atualizações do sistema operacional |  Os dispositivos de área de trabalho gerenciada da Microsoft sempre são protegidos com as últimas atualizações de segurança.
Configuração de dispositivo seguro |   O Microsoft Managed desktop implementa a linha de base de segurança da Microsoft. Para obter mais informações, consulte [linhas de base de segurança do Windows.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>Gerenciamento de identidades e acesso

O gerenciamento de identidades e acesso protege os ativos corporativos e os dados críticos para os negócios. O Microsoft Managed desktop configura dispositivos para garantir o uso seguro com identidades gerenciadas do Azure Active Directory (Azure AD). É responsabilidade do cliente manter informações precisas no locatário do Azure AD. 

Serviço | Descrição
--- | ---
Autenticação biométrica |  O Windows Hello permite que os usuários façam logon usando sua face ou um PIN, tornando as senhas mais difíceis de esquecer ou roubar. Os clientes são responsáveis por implementar os pré-requisitos necessários para o Active Directory local para o uso desse serviço em uma configuração híbrida. Para obter mais informações, consulte [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 
Permissão de usuário padrão |  Para proteger o sistema e torná-lo mais seguro, as permissões de usuário padrão serão atribuídas ao usuário. Isso é atribuído como parte da experiência inicial da caixa do Windows AutoPilot.



## <a name="network-security"></a>Segurança da rede

Os clientes são responsáveis pela segurança da rede. 

Serviço | Descrição
--- | ---
VPN | Os clientes possuem sua infraestrutura de VPN, para garantir que os recursos corporativos limitados possam ser expostos fora da intranet.<br><br>Requisitos mínimos: o Microsoft Managed desktop requer uma solução VPN compatível com o Windows 10 e com suporte. Se sua organização precisar de uma solução VPN, precisará oferecer suporte ao Windows 10 e ser empacotado e implantado por meio do Intune. Entre em contato com o fornecedor do software para obter mais informações.<br><br>Recomendação<br>– A Microsoft recomenda uma solução de VPN moderna que possa ser implantada facilmente por meio do Intune para enviar perfis VPN. Isso oferece uma maneira contínua, fácil, confiável e segura de acessar a rede corporativa. Para obter mais informações, consulte [[configurações de VPN no Intune]](https://docs.microsoft.com/intune/vpn-settings-configure).<br>-Clientes VPN espesso ou clientes VPN herdados não são recomendados pela Microsoft enquanto usam a área de trabalho gerenciada da Microsoft, pois isso pode afetar o ambiente do usuário final.<br>-A Microsoft recomenda que o tráfego da Web de saída vá diretamente para a Internet sem passar pela VPN para evitar qualquer problema de desempenho.<br>– Idealmente, a Microsoft recomenda o uso do proxy de aplicativo do Azure Active Directory em vez de uma VPN.


## <a name="information-security"></a>Segurança de informações

Os clientes podem configurar esses serviços opcionais para ajudar a proteger ativos corporativos de valor alto. 

Serviço | Descrição
--- | ---
Recuperação de dados  | É feito o backup das informações armazenadas nas principais pastas do dispositivo no OneDrive for Business. O Microsoft Managed desktop não é responsável por dados que não estão sincronizados com o OneDrive for Business. 
Proteção de Informações do Windows |    Para empresas que exigem altos níveis de segurança de informações, recomendamos [proteção de informações do Windows](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) e proteção de [informações do Azure.](https://www.microsoft.com/cloud-platform/azure-information-protection). 

