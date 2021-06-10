---
title: Tecnologias de segurança no Área de Trabalho Gerenciada da Microsoft
description: Tecnologias usadas para segurança de dispositivos, gerenciamento de identidade e acesso, segurança de rede e segurança de informações
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b1111f0867ff9a49ba670cdd8b48d10d158fd3ed
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917765"
---
# <a name="security-technologies-in-microsoft-managed-desktop"></a>Tecnologias de segurança no Área de Trabalho Gerenciada da Microsoft

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Área de Trabalho Gerenciada da Microsoft usa várias tecnologias da Microsoft para ajudar a proteger dispositivos e dados gerenciados. Além disso, o Área de Trabalho Gerenciada da Microsoft de Operações de Segurança usa vários [processos](security-operations.md) em conjunto com essas tecnologias.

Especificamente: 

- [Segurança do](#device-security) dispositivo – segurança e proteção em Área de Trabalho Gerenciada da Microsoft dispositivos
- [Gerenciamento de identidade e acesso](#identity-and-access-management) – gerenciando o uso seguro de dispositivos por meio Azure Active Directory de identidade
- [Segurança de rede](#network-security) – informações de VPN e Área de Trabalho Gerenciada da Microsoft soluções e configurações recomendadas
- [Segurança de informações](#information-security) – serviços opcionais disponíveis para proteger ainda mais informações confidenciais 

Para obter informações sobre as práticas de armazenamento, uso e segurança de dados usadas pelo Área de Trabalho Gerenciada da Microsoft, consulte nosso whitepaper em [https://aka.ms/mmd-data](https://aka.ms/mmd-data) .


## <a name="device-security"></a>Segurança do dispositivo

Área de Trabalho Gerenciada da Microsoft garante que todos os dispositivos gerenciados sejam protegidos e protegidos e detecte ameaças o mais cedo possível usando os seguintes serviços:

Serviço | Descrição
--- | ---
Antivírus | O Microsoft Defender AV está instalado e configurado<br>As definições do Microsoft Defender AV estão atualizadas
Criptografia de Volume Total |    Windows BitLocker é a solução de criptografia de volume para Área de Trabalho Gerenciada da Microsoft dispositivos.<br><br>Depois que uma organização estiver integrado ao serviço, os dispositivos serão criptografados usando o Windows BitLocker com TPM (Módulo de Plataforma de Confiança) interno para impedir o acesso não autorizado a dados locais quando o dispositivo estiver no modo de sono ou desligado. 
Monitoramento |    O Microsoft Defender para Ponto de Extremidade é usado para monitoramento de ameaças de segurança em todos os Área de Trabalho Gerenciada da Microsoft dispositivos. O Defender for Endpoint permite que os clientes corporativos detectem, investiguem e respondam a ameaças avançadas em sua rede corporativa. Para obter mais informações, consulte [Microsoft Defender for Endpoint.](/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
Atualizações do sistema operacional |  Área de Trabalho Gerenciada da Microsoft dispositivos estão sempre protegidos com as atualizações de segurança mais recentes.
Configuração segura do dispositivo |   Área de Trabalho Gerenciada da Microsoft implementa a Linha de Base de Segurança da Microsoft. Para obter mais informações, [consulte Windows de segurança.](/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>Gerenciamento de identidades e acesso

O gerenciamento de identidade e acesso protege ativos corporativos e dados críticos para os negócios. Área de Trabalho Gerenciada da Microsoft configura dispositivos para garantir o uso seguro com Azure Active Directory identidades gerenciadas (Azure AD). É responsabilidade do cliente manter informações precisas em seu locatário do Azure AD. 

Serviço | Descrição
--- | ---
Autenticação Biométrica |  Windows O Hello permite que os usuários se inscrevam usando o rosto ou um PIN, tornando as senhas mais difíceis de esquecer ou roubar. Os clientes são responsáveis por implementar os pré-requisitos necessários para seu Active Directory local para uso desse serviço em uma configuração híbrida. Para obter mais informações, consulte [Windows Hello.](/windows-hardware/design/device-experiences/windows-hello) 
Permissão de usuário padrão |  Para proteger o sistema e torná-lo mais seguro, o usuário receberá Permissões padrão de usuário. Essa permissão é atribuída como parte do Windows autopiloto fora do box.



## <a name="network-security"></a>Segurança de rede

Os clientes são responsáveis pela segurança da rede. 

Serviço | Descrição
--- | ---
VPN | Os clientes têm sua infraestrutura VPN para garantir que recursos corporativos limitados possam ser expostos fora da intranet.<br><br>Requisito mínimo: Área de Trabalho Gerenciada da Microsoft requer uma Windows 10 vpn compatível e compatível. Se sua organização precisar de uma solução VPN, ela precisa dar suporte Windows 10 e ser empacotada e implantável por meio do Intune. Entre em contato com seu editor de software para obter mais informações.<br><br>Recomendação:<br>– A Microsoft recomenda uma solução VPN moderna que pode ser facilmente implantada por meio do Intune para pressionar perfis VPN. Essa abordagem fornece uma maneira contínua, perfeita, confiável e segura de acessar a rede corporativa. Para obter mais informações, [consulte [Configurações de VPN no Intune]](/intune/vpn-settings-configure).<br>– Clientes VPN de espessura, ou clientes VPN mais antigos, não são recomendados pela Microsoft ao usar Área de Trabalho Gerenciada da Microsoft, pois podem afetar o ambiente do usuário.<br>– A Microsoft recomenda que o tráfego da Web de saída vá diretamente para a Internet sem passar pela VPN para evitar problemas de desempenho.<br>- Idealmente, a Microsoft recomenda o uso de um proxy de aplicativo Azure Active Directory em vez de uma VPN.


## <a name="information-security"></a>Segurança de informações

Você pode configurar esses serviços opcionais para ajudar a proteger ativos corporativos de alto valor. 

Serviço | Descrição
--- | ---
Recuperação de dados  | As informações armazenadas em pastas de chave no dispositivo são armazenadas em OneDrive for Business. Área de Trabalho Gerenciada da Microsoft não é responsável por dados que não são sincronizados com OneDrive for Business. 
Proteção de Informações do Windows |    Para empresas que exigem altos níveis de segurança de informações, recomendamos Windows [Proteção](/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) de Informações e Proteção de Informações [do Azure.](https://www.microsoft.com/cloud-platform/azure-information-protection).