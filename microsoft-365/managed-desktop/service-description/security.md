---
title: Segurança na Área de Trabalho Gerenciada da Microsoft
description: ''
keywords: Serviço Microsoft Managed Desktop, 365 da Microsoft, documentação
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 0ea0bbc6a8055ee8459fadd85a6fa4ddac14bdb7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865304"
---
# <a name="security-in-microsoft-managed-desktop"></a>Segurança na Área de Trabalho Gerenciada da Microsoft

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Usando várias tecnologias Microsoft, podemos garantir que os dispositivos de área de trabalho gerenciada do Microsoft estejam protegidos e que a equipe de operações de segurança do Microsoft Desktop gerenciados pode impedir, detectar e responder a ameaças avançadas. Serviços, aplicativos e produtos de segurança de terceiros não são permitidos. Microsoft será aplicada a uma linha de base de política padrão para garantir a dispositivos, identidade, rede e dados corporativos são seguras e protegidos.

Essas categorias de aplicação de segurança são documentadas nas seções a seguir:

- [Segurança de dados](#data-security) – como podemos garantir que os dados é armazenado e atende aos requisitos para o posicionamento de segurança do Azure
- [Segurança de dispositivo](#device-security) – como podemos garantir que os dispositivos Microsoft Desktop gerenciados são seguros
- [Segurança de identidade](#identity-security) – não estão comprometidas como podemos garantir que os usuários no local de trabalho moderno
- [Segurança de rede](#network-security) – como podemos garantir um acesso seguro a recursos corporativos
- [Segurança das informações](#information-security) – como podemos garantir que os dados corporativos é seguro
- [Acesso de conta privilegiada](#privileged-account-access) - como podemos restringir o acesso

## <a name="data-security"></a>Segurança de dados

Dados transmitidos do seu locatário são armazenados nos bancos de dados do SQL Azure no locatário Microsoft hospedados nos EUA. Os dados são armazenados e atende aos requisitos para o posicionamento de segurança do Azure. 

Para obter mais informações, consulte [segurança do Microsoft Azure](https://www.microsoft.com/TrustCenter/Security/azure-security).

Esta lista resume os tipos de dados transmitidos entre a Microsoft e seu locatário. 

- Da Microsoft para seu locatário
    - Nomes de grupo
    - Configuração de diretiva de segurança
    - Ordens de dispositivo
    - Contas de usuário (msadmin, mstest, Microsoft gerenciados Desktop_soc_ro, Microsoft gerenciados Desktop_wdgsoc)
    - Atribuição de licença de E5 aos 4 usuários acima
    - O Windows update políticas para toques de atualização
    - No futuro, ainda mais recursos serão desenvolvidos para permitir o lançamento de outros tipos de conteúdo de configuração, incluindo aplicativos, políticas e configurações.
- De seu locatário à Microsoft
    - Dados de atualização, o uso e a confiabilidade do dispositivo
    - Dados de implantação e a confiabilidade do aplicativo
    - Dados de implantação de diretiva de segurança e atualização
    - Usuários atribuídos aos dispositivos



## <a name="device-security"></a>Segurança de dispositivo

Para evitar que as violações de segurança, é importante garantir que todos os dispositivos de área de trabalho gerenciada do Microsoft saudável e protegido. É igualmente importante garantir que podemos detectar dispositivos não íntegros e reduzir o risco mais cedo possível.

A tabela a seguir lista os serviços fornecidos para garantir que os dispositivos Microsoft Desktop gerenciados são confiáveis, íntegro e protegido.

Serviço | Descrição
--- | ---
Antivírus | Podemos garantirá que:<br>-Windows Defender AV está instalado e configurado<br>-Definições de Windows Defender AV estão atualizadas
Criptografia de Volume completo |    Windows BitLocker é a solução de criptografia de dados para dispositivos Microsoft Desktop gerenciados.<br><br>Depois que uma organização for onboarded no serviço, dispositivos serão criptografados usando o Windows BitLocker com internas confiar Platform Module (TPM) para impedir o acesso não autorizado aos dados de locais quando o dispositivo está no modo de suspensão ou desativado. 
Monitoramento |    Windows Defender avançada proteção contra ameaças (Windows Defender ATP) é a solução para todos os dispositivos de área de trabalho do Microsoft gerenciados de monitoramento de ameaça de segurança. Windows Defender ATP permite que os clientes corporativos detectar, investigue e responder a ameaças avançadas na sua rede corporativa. Para obter mais informações, consulte [proteção de ameaça avançado do Windows Defender.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
Atualizações de software |  Microsoft garantirá que dispositivos Microsoft Desktop gerenciados sempre são protegidos com a atualização de segurança mais recente para o Windows e o Office, usando o Windows Update para negócios.
Recuperação |  Dados corporativos estão armazenados no OneDrive para negócios e possam ser facilmente restaurados para dispositivos Microsoft Desktop gerenciados. Para obter mais informações, consulte [OneDrive for Business.](https://support.office.com/article/Restore-a-previous-version-of-a-file-in-OneDrive-159cad6d-d76e-4981-88ef-de6e96c93893?ui=en-US&rs=en-US&ad=US) 



## <a name="identity-security"></a>Segurança de identidade

Gerenciamento de acesso e identidade protege os ativos corporativos e os dados críticos para os negócios. Azure Active Directory (AD Azure) fornece serviços de identidade na nuvem e habilitar autenticação baseada em nuvem que garante que apenas as pessoas confiáveis pode acessar recursos corporativos usando dispositivos Microsoft Desktop gerenciados.

Serviço | Descrição
--- | ---
Provedor de autenticação de nível empresarial |  Edições de AD Premium Azure usadas pela Microsoft oferecem um serviço de alta disponibilidade hospedado em datacenters distribuídas globalmente. O serviço trata bilhões de autenticações de cada dia de mais de 200 milhões de usuários ativos e oferece um SLA de 99,9%.
Autenticação biométrica |  Windows Olá permite aos usuários fazer logon usando sua face ou um PIN, tornando mais difícil de esquecer ou roubar a senhas. Isso pode exigir um trabalho adicional para configurar. Para obter mais informações, consulte [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)
Autenticação de vários fatores | Azure a autenticação multifator impede o acesso não autorizado aos locais e de aplicativos em nuvem, fornecendo um nível adicional de autenticação usando um telefone celular, bem como pessoal redefinição de senha. 
Permissão de usuário padrão |  Para proteger o sistema e torná-lo mais seguro, o usuário será atribuído as permissões de usuário padrão. Isso é atribuído como parte da experiência imediata de piloto automático do Windows.



## <a name="network-security"></a>Segurança da rede

Os clientes são responsáveis por segurança da rede. 

Serviço | Descrição
--- | ---
VPN | Os clientes possuem sua infra-estrutura de VPN, para garantir a recursos corporativos limitados podem ser expostos fora da intranet.<br><br>Requisito mínimo: área de trabalho do Microsoft Managed exige uma solução VPN Windows 10 compatível e com suporte. Se sua organização precisar de uma solução VPN, ele precisa suportar Windows 10 e ser empacotado e facilidade de implantação por meio de Intune. Para obter mais informações, entre em contato com seu fornecedor de software.<br><br>Recomendação:<br>-A Microsoft recomenda uma solução de VPN moderna que possam ser facilmente implantada por meio de Intune para os perfis de VPN push. Isso oferece uma maneira de sempre ativa, sem interrupções, confiável e segura para acessar a rede corporativa. Para obter mais informações, consulte configurações VPN Intune.<br>-Clientes VPN espessas ou clientes herdados de VPN, não são recomendados pela Microsoft durante a utilização do Microsoft Desktop gerenciados como ele pode afetar o ambiente do usuário final.<br>-A Microsoft recomenda que o tráfego de saída web vai diretamente para a Internet, sem precisar passar por meio da VPN para evitar problemas de desempenho.<br>-Idealmente, a Microsoft recomenda o uso do Windows Azure Active Directory App Proxy em vez de uma VPN.


## <a name="information-security"></a>Segurança das informações

Os clientes podem configurar esses serviços opcionais para ajudar a proteger os ativos de alto valor corporativos. 

Serviço | Descrição
--- | ---
Acesso condicional |    Permita o acesso aos recursos corporativos e serviços somente quando o dispositivo é compatível com.
Recuperação de dados  | Informações armazenadas em pastas de chave no dispositivo são feitas backup ao OneDrive para Bbusiness. Microsoft Desktop gerenciados não é responsável por dados que não estão sincronizados com o OneDrive for Business. 
Proteção de Informações do Windows |    Para empresas que exigem altos níveis de segurança das informações, recomendamos a [Proteção de informações do Windows](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) e [proteção de informações do Azure.](https://www.microsoft.com/cloud-platform/azure-information-protection). 


## <a name="privileged-account-access"></a>Acesso de conta privilegiada

Hoje, podemos restringir o acesso às credenciais do cliente MSAdmin e o aplicativo por meio desses mecanismos:

- **Operadores** – integral-imediato-funcionários da Microsoft localizados nos EUA que foi concluído com êxito uma verificação de segurança e de plano de fundo periódica.
- **Identidade do operador** – protegida de acordo com os padrões definidos pela Microsoft. Para obter mais informações, consulte [Managing identidades de usuário e proteger o acesso na Microsoft](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft). 
- **Registro em log** é executada dentro do ambiente do operador e dentro de locatário do cliente. Dados de log e informações pessoais são mantidas dentro dos respectivos ambientes e não atravessam ambientes. 

