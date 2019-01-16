---
title: Segurança na Área de Trabalho Gerenciada da Microsoft
description: ''
keywords: Serviço Microsoft Managed Desktop, 365 da Microsoft, documentação
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 928d01e7386bedc500e984b9c2a3240c6229bb43
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865304"
---
# <a name="security-in-microsoft-managed-desktop"></a>Segurança na Área de Trabalho Gerenciada da Microsoft

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft Desktop gerenciados aplica um conjunto padrão de políticas e utiliza muitas tecnologias Microsoft para ajudar a dispositivos de área de trabalho do Microsoft gerenciados seguros, dados da empresa armazenado e mais. As áreas listadas abaixo são detalhadas ainda mais:  

- [Segurança de dados](#data-security) - tipos de dados coletados pelo Microsoft Desktop gerenciados e onde ele está armazenado com segurança
- [Segurança de dispositivo](#device-security) – segurança e proteção em dispositivos Microsoft Desktop gerenciados
- [Gerenciamento de acesso e identidade](#identity-and-access-management) – Gerenciando uso seguro de dispositivos por meio de serviços de identidade do Active Directory do Azure
- [Segurança da rede](#network-security) – informações de VPN e o Microsoft Desktop gerenciados recomendada solução e configurações
- [Segurança das informações](#information-security) – serviços opcionais de disponíveis para aumentar a proteção de informações confidenciais 

## <a name="data-security"></a>Segurança de dados

Dados coletados de Inquilinos do cliente (que permite que os serviços de TI de área de trabalho gerenciada da Microsoft e operações) são armazenados nos bancos de dados do SQL Azure no locatário Microsoft hospedados nos Estados Unidos.

Para obter mais informações, consulte [segurança do Microsoft Azure](https://docs.microsoft.com/azure/security/azure-database-security-overview).

Os tipos de dados transmitidos do seu locatário são mostrados abaixo:

- Dados de atualização, o uso e a confiabilidade do dispositivo
- Dados de implantação e a confiabilidade do aplicativo
- Dados de implantação de diretiva de segurança e atualização
- Usuários atribuídos aos dispositivos



## <a name="device-security"></a>Segurança de dispositivo

Microsoft Desktop gerenciados garante que todos os dispositivos gerenciados são protegidos e protegidos e detecta ameaças mais cedo possível usando os seguintes serviços:

Serviço | Descrição
--- | ---
Antivírus | Windows Defender AV está instalado e configurado<br>Definições do Windows Defender AV estão atualizadas
Criptografia de Volume completo |    Windows BitLocker é a solução de criptografia de volume para dispositivos Microsoft Desktop gerenciados.<br><br>Depois que uma organização for onboarded no serviço, dispositivos serão criptografados usando o Windows BitLocker com internas confiar Platform Module (TPM) para impedir o acesso não autorizado aos dados de locais quando o dispositivo está no modo de suspensão ou desativado. 
Monitoramento |    Windows Defender avançada proteção contra ameaças (Windows Defender ATP) é usada para o monitoramento de ameaças de segurança em todos os dispositivos de área de trabalho gerenciada do Microsoft. Windows Defender ATP permite aos clientes enterprise detectar, investigar e responder a ameaças avançadas na sua rede corporativa. Para obter mais informações, consulte [proteção de ameaça avançado do Windows Defender.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
Atualizações de software |  Dispositivos de área de trabalho gerenciada do Microsoft sempre são protegidos com as últimas atualizações de segurança.
Configuração de dispositivo seguro |   Microsoft Desktop gerenciados implementa o Microsoft Security Baseline. Para obter mais informações, consulte [linhas de base do Windows security.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>Gerenciamento de identidades e acesso

Gerenciamento de acesso e identidade protege os ativos corporativos e os dados críticos para os negócios. Microsoft Desktop gerenciados configura os dispositivos para garantir o uso seguro com o Azure Active Directory (AD Azure) gerenciados identidades. É responsabilidade do cliente para manter informações precisas no seu locatário do Azure AD. 

Serviço | Descrição
--- | ---
Autenticação biométrica |  Windows Olá permite aos usuários fazer logon usando sua face ou um PIN, tornando mais difícil de esquecer ou roubar a senhas. Para obter mais informações, consulte [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)
Multi-factor Authentication | Azure a autenticação multifator mais fortemente controla o acesso às funções confidenciais do serviço Microsoft Desktop gerenciados, fornecendo um nível adicional de autenticação usando um telefone celular, como a redefinição de senha bem como pessoal. 
Permissão de usuário padrão |  Para proteger o sistema e torná-lo mais seguro, o usuário será atribuído as permissões de usuário padrão. Isso é atribuído como parte da experiência imediata de piloto automático do Windows.



## <a name="network-security"></a>Segurança da rede

Os clientes são responsáveis por segurança da rede. 

Serviço | Descrição
--- | ---
VPN | Os clientes possuem sua infra-estrutura de VPN, para garantir a recursos corporativos limitados podem ser expostos fora da intranet.<br><br>Requisito mínimo: área de trabalho do Microsoft Managed exige uma solução VPN Windows 10 compatível e com suporte. Se sua organização precisar de uma solução VPN, ele precisa suportar Windows 10 e ser empacotado e facilidade de implantação por meio de Intune. Para obter mais informações, entre em contato com seu fornecedor de software.<br><br>Recomendação:<br>-A Microsoft recomenda uma solução VPN moderna que possam ser facilmente implantada por meio de Intune para os perfis de VPN push. Isso oferece uma maneira de sempre ativa, sem interrupções, confiável e segura para acessar a rede corporativa. Para obter mais informações, consulte [[VPN configurações Intune]](https://docs.microsoft.com/intune/vpn-settings-configure).<br>-Clientes VPN espessas ou clientes herdados de VPN, não são recomendados pela Microsoft durante a utilização do Microsoft Desktop gerenciados como ele pode afetar o ambiente do usuário final.<br>-A Microsoft recomenda que o tráfego de saída web vai diretamente para a Internet, sem precisar passar por meio da VPN para evitar problemas de desempenho.<br>-Idealmente, a Microsoft recomenda o uso do Windows Azure Active Directory App Proxy em vez de uma VPN.


## <a name="information-security"></a>Segurança das informações

Os clientes podem configurar esses serviços opcionais para ajudar a proteger os ativos de alto valor corporativos. 

Serviço | Descrição
--- | ---
Recuperação de dados  | Informações armazenadas em pastas de chave no dispositivo são feitas backup ao OneDrive for Business. Microsoft Desktop gerenciados não é responsável por dados que não estão sincronizados com o OneDrive for Business. 
Proteção de Informações do Windows |    Para empresas que exigem altos níveis de segurança das informações, recomendamos a [Proteção de informações do Windows](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) e [proteção de informações do Azure.](https://www.microsoft.com/cloud-platform/azure-information-protection). 

