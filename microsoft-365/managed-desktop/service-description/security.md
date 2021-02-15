---
title: Tecnologias de segurança na Área de Trabalho Gerenciada da Microsoft
description: Tecnologias usadas para segurança de dispositivos, gerenciamento de identidades e acesso, segurança de rede e segurança de informações
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 5076ddca6053adc7cebb9599c8d82a42c7ab5a63
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840908"
---
# <a name="security-technologies-in-microsoft-managed-desktop"></a>Tecnologias de segurança na Área de Trabalho Gerenciada da Microsoft

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

A Área de Trabalho Gerenciada da Microsoft usa várias tecnologias da Microsoft para ajudar a proteger dados e dispositivos gerenciados. Além disso, o Centro de Operações de Segurança da Área de Trabalho Gerenciada da Microsoft usa vários [processos](security-operations.md) em conjunto com essas tecnologias.

Especificamente: 

- [Segurança do dispositivo](#device-security) – segurança e proteção em dispositivos da Área de Trabalho Gerenciada da Microsoft
- [Gerenciamento de identidades e acesso](#identity-and-access-management) – gerenciando o uso seguro de dispositivos por meio dos serviços de identidade do Azure Active Directory
- [Segurança de rede](#network-security) – informações de VPN e solução e configurações recomendadas da Área de Trabalho Gerenciada da Microsoft
- [Segurança da informação](#information-security) – serviços opcionais disponíveis para proteger ainda mais as informações confidenciais 

Para obter informações sobre as práticas de armazenamento, uso e segurança de dados usadas pela Área de Trabalho Gerenciada da Microsoft, consulte nosso whitepaper em [https://aka.ms/mmd-data](https://aka.ms/mmd-data) .


## <a name="device-security"></a>Segurança do dispositivo

A Área de Trabalho Gerenciada da Microsoft garante que todos os dispositivos gerenciados sejam protegidos e detecte ameaças o mais cedo possível usando os seguintes serviços:

Serviço | Descrição
--- | ---
Antivírus | O Microsoft Defender AV está instalado e configurado<br>As definições do Microsoft Defender AV estão atualizadas
Criptografia de Volume Completo |    O Windows BitLocker é a solução de criptografia de volume para dispositivos da Área de Trabalho Gerenciada da Microsoft.<br><br>Depois que uma organização for integrada ao serviço, os dispositivos serão criptografados usando o Windows BitLocker com o TPM (Trust Platform Module) interno para impedir o acesso não autorizado a dados locais quando o dispositivo estiver no modo de espera ou desligado. 
Monitoramento |    O Microsoft Defender para Ponto de Extremidade é usado para monitoramento de ameaças de segurança em todos os dispositivos da Área de Trabalho Gerenciada da Microsoft. O Defender para Ponto de Extremidade permite que os clientes corporativos detectem, investiguem e respondam a ameaças avançadas em sua rede corporativa. Para obter mais informações, [consulte Microsoft Defender for Endpoint.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
Atualizações do sistema operacional |  Os dispositivos da Área de Trabalho Gerenciada da Microsoft estão sempre protegidos com as atualizações de segurança mais recentes.
Configuração de Dispositivo Seguro |   A Área de Trabalho Gerenciada da Microsoft implementa a Linha de Base de Segurança da Microsoft. Para obter mais informações, consulte linhas [de base de segurança do Windows.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>Gerenciamento de identidades e acesso

O gerenciamento de identidade e acesso protege ativos corporativos e dados essenciais para os negócios. A Área de Trabalho Gerenciada da Microsoft configura dispositivos para garantir o uso seguro com identidades gerenciadas do Azure Active Directory (Azure AD). É responsabilidade do cliente manter informações precisas em seu locatário do Azure AD. 

Serviço | Descrição
--- | ---
Autenticação biométrica |  O Windows Hello permite que os usuários se inscrevam usando seu rosto ou um PIN, tornando as senhas mais difíceis de esquecer ou roubar. Os clientes são responsáveis por implementar os pré-requisitos necessários para seu Active Directory local para uso desse serviço em uma configuração híbrida. Para obter mais informações, consulte [o Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 
Permissão de usuário padrão |  Para proteger o sistema e torná-lo mais seguro, o usuário receberá permissões de usuário padrão. Essa permissão é atribuída como parte da experiência de configuração do Windows Autopilot.



## <a name="network-security"></a>Segurança de rede

Os clientes são responsáveis pela segurança da rede. 

Serviço | Descrição
--- | ---
VPN | Os clientes têm sua infraestrutura VPN, para garantir que recursos corporativos limitados possam ser expostos fora da intranet.<br><br>Requisito mínimo: a Área de Trabalho Gerenciada da Microsoft requer uma solução VPN compatível e compatível com o Windows 10. Se sua organização precisar de uma solução VPN, ela precisará dar suporte ao Windows 10 e ser empacotada e implantável por meio do Intune. Entre em contato com seu editor de software para obter mais informações.<br><br>Recomendação:<br>- A Microsoft recomenda uma solução VPN moderna que pode ser facilmente implantada por meio do Intune para por push de perfis VPN. Essa abordagem fornece uma maneira sempre contínua, contínua, confiável e segura de acessar a rede corporativa. Para saber mais, confira [[Configurações de VPN no Intune]](https://docs.microsoft.com/intune/vpn-settings-configure).<br>– Clientes VPN grossas, ou clientes VPN mais antigos, não são recomendados pela Microsoft ao usar a Área de Trabalho Gerenciada da Microsoft, pois isso pode afetar o ambiente do usuário.<br>- A Microsoft recomenda que o tráfego da Web de saída vá diretamente para a Internet sem passar pela VPN para evitar problemas de desempenho.<br>- Idealmente, a Microsoft recomenda o uso do Proxy de Aplicativo do Azure Active Directory em vez de uma VPN.


## <a name="information-security"></a>Segurança das informações

Você pode configurar esses serviços opcionais para ajudar a proteger ativos corporativos de alto valor. 

Serviço | Descrição
--- | ---
Recuperação de dados  | As informações armazenadas em pastas-chave no dispositivo são armazenadas no OneDrive for Business. A Área de Trabalho Gerenciada da Microsoft não é responsável por dados que não estão sincronizados com o OneDrive for Business. 
Proteção de Informações do Windows |    Para empresas que exigem altos níveis de segurança da informação, recomendamos a Proteção de Informações do [Windows](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) e a Proteção de [Informações do Azure.](https://www.microsoft.com/cloud-platform/azure-information-protection) 

