---
title: Configurações de acesso de dispositivo e identidade - Microsoft 365 Enterprise
description: Descreve as recomendações da Microsoft e conceitos principais para implantar o email seguro, documentos e as políticas de aplicativos e configurações.
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/11/2018
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: 74378da4206c3735cd949358c6cb34b314c82b97
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864700"
---
# <a name="identity-and-device-access-configurations"></a>Configurações de identidade e de acesso ao dispositivo

Esta série de artigos descreve como configurar o acesso seguro aos serviços de nuvem por meio de mobilidade corporativos + produtos de segurança por meio da implementação de um ambiente recomendada e a configuração, incluindo um conjunto indicado de políticas de acesso condicional e recursos relacionados. Você pode usar estas diretrizes para proteger o acesso a todos os serviços que são integrados com o Windows Azure Active Directory, incluindo os serviços do Office 365, a outros serviços SaaS e aplicativos de local publicado com Proxy de aplicativo do Windows Azure AD. 

Estas recomendações estejam alinhadas às Microsoft seguro pontuação, bem como [identidade pontuação no Azure AD](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/identity-secure-score) e aumentarão essas pontuações para sua organização. Estas recomendações também ajudarão a implementar estas [cinco etapas para protegerão a infraestrutura de identidade](https://docs.microsoft.com/en-us/azure/security/azure-ad-secure-steps). 

A Microsoft entende que algumas organizações têm requisitos de ambiente exclusivo ou complexidade. Se você for um dessas organizações, use estas recomendações como ponto de partida. No entanto, a maioria das organizações pode implementar estas recomendações conforme prescrito. 

## <a name="intended-audience"></a>Público-alvo

Estas recomendações destinam Enterprise arquitetos e profissionais de TI que estão familiarizados com o [Office 365](https://technet.microsoft.com/library/dn127064(v=office.14).aspx) e [Microsoft Enterprise mobilidade + segurança](http://microsoft.com/ems) que inclui, entre outros, Azure Active Directory (identidade), Microsoft Intune (gerenciamento de dispositivo) e proteção de informações do Windows Azure (proteção de dados).

### <a name="customer-environment"></a>Ambiente de cliente

As políticas recomendadas são aplicáveis para organizações de empresa que operam inteiramente dentro de nuvem da Microsoft e para o híbrido clientes com a infraestrutura implantavam no local e a nuvem da Microsoft.

Muitas das recomendações fornecidas contam com serviços avançados disponíveis apenas com mobilidade corporativos + licenças E5 de segurança (EMS). Recomendações apresentadas pressupõem recursos completos de licença do EMS E5.

Para as organizações que não possuem Enterprise mobilidade + segurança E5 licenças, a Microsoft recomenda que implementar recursos de proteção de linha de base do Azure AD incluídos com todos os planos de pelo menos. Mais informações podem ser encontradas no artigo, [o que é proteção de linha de base](/azure/active-directory/active-directory-conditional-access-baseline-protection) na biblioteca do Azure AD.

### <a name="caveats"></a>Advertências

Sua organização pode estar sujeitos a requisitos de conformidade normativa ou outros, incluindo recomendações específicas que podem exigir a aplicar políticas que divergem de essas configurações recomendadas. Essas configurações recomendam controles de uso que historicamente não estava disponíveis. Recomendamos esses controles, como podemos acredite que representam um equilíbrio entre a segurança e a produtividade.  

Podemos ter feito o melhor possível para levar em conta uma ampla variedade de requisitos de proteção organizacional, não estamos capazes de conta para todos os requisitos de possíveis ou para todos os aspectos exclusivos de sua organização.

## <a name="three-tiers-of-protection"></a>Três camadas de proteção

A maioria das organizações tem requisitos específicos sobre segurança e proteção de dados. Esses requisitos variam por segmento do setor e por funções de trabalho dentro das organizações. Por exemplo, seu departamento jurídico e os administradores do Office 365 podem exigir controles de proteção de informações e segurança adicionais em sua correspondência de email que não são necessários para outros usuários da unidade de negócios.

Cada setor também tem seu próprio conjunto de normas especializados. Em vez de fornecer uma lista de todas as opções de segurança possíveis ou uma recomendação por função de trabalho ou de segmento do setor, foram fornecidas recomendações para três diferentes níveis de segurança e proteção que pode ser aplicada com base na granulação das suas necessidades .

- **Proteção de linha de base** — é recomendável que você estabelece um padrão mínimo de proteção de dados, bem como os dispositivos que acessam os dados e identidades. Você pode seguir estas recomendações de linha de base para oferecer proteção padrão forte que atenda às necessidades de muitas organizações.
- **Proteção confidencial** — alguns clientes têm um subconjunto de dados que devem ser protegidos nos níveis mais altos ou exigem que todos os dados devem ser protegidos em um nível superior. Você pode aplicar a aumentar a proteção a todos ou dados específicos define em seu ambiente do Office 365. É recomendável proteger identidades e dispositivos que acessam dados confidenciais comparável níveis de segurança.  
- **Altamente regulamentado** — algumas organizações podem ter uma pequena quantidade de dados que são classificados altamente, segredo comercial ou regulamentados dados. A Microsoft fornece recursos para ajudar as organizações a atender a esses requisitos, incluindo proteção adicional para identidades e dispositivos.

![Cone de segurança - todos os clientes > alguns clientes > clientes específicos. Aplicativo amplo para o aplicativo específico](../images/M365-idquality-threetiers.png)

Esta orientação mostra como implementar a proteção para identidades e dispositivos para cada um desses níveis de proteção. Usar este guia como ponto de partida para sua organização e ajustar as diretivas para atender suas necessidades de organização específica.

É importante Use níveis consistentes de proteção através de seus dados, as identidades e dispositivos. Por exemplo, se você implementar esta orientação, certifique-se de proteger os dados nos níveis comparáveis. Esses modelos de arquitetura mostram quais recursos são comparáveis.

**Proteção de identidade e o dispositivo para o Office 365**<br/>
![Miniatura do pôster "Identity e dispositivo de proteção para o Office 365"](../images/O365_Identity_device_protection_thumb.png)<br/>
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Mais idiomas](https://www.microsoft.com/download/details.aspx?id=55032)

**Soluções para proteção de arquivos do Office 365**<br/>
![Miniatura do pôster "Soluções de proteção de arquivo no Office 365"](../images/24be68b5-d852-4fdb-94ad-94491a19edd8.png)<br/>
[PDF](http://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.pdf) | [Visio](http://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.vsdx)

## <a name="security-and-productivity-trade-offs"></a>Vantagens e desvantagens de produtividade e segurança

Implementação de qualquer estratégia de segurança exige compensações entre segurança e produtividade. É útil avaliar como cada decisão afeta o equilíbrio de segurança, a funcionalidade e facilidade de uso.

![Triplo de segurança balanceamento de segurança, a funcionalidade e facilidade de uso.](media/policies-configurations/security-triad.png)

As recomendações fornecidas baseiam-se nos princípios seguintes:

- Conheça o seu público seja flexível seus requisitos de segurança e funcionais.
- Aplicar a diretiva de segurança no momento e garantir que ele seja consistente.

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Serviços e conceitos do dispositivo e a identidade de proteção de acesso

Microsoft 365 Enterprise foi projetado para grandes organizações e integra o Office 365 Enterprise, Windows 10 Enterprise e mobilidade corporativos + segurança (EMS) para capacitar todos para ser criativo e trabalhar juntos, de forma segura.

Esta seção fornece uma visão geral dos serviços do Microsoft 365 e recursos que são importantes para acesso de dispositivo e identidade.

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Azure AD oferece recursos de gerenciamento de um pacote completo de identidade. Nossas recomendações para proteger o acesso de usam os seguintes recursos:

- **[Redefinir a senha de autoatendimento (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks.md)** — permitir que os usuários redefinam suas senhas sem intervenção de assistência técnica de forma segura, fornecendo a verificação dos vários métodos de autenticação que o administrador pode controlar.
- **[A autenticação multifator (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks.md)** — MFA requer que os usuários fornecem duas formas de verificação, como uma senha de usuário além de uma notificação a partir do aplicativo de Authenticator Microsoft ou uma chamada telefônica. MFA reduz significativamente o risco que uma identidade roubada pode ser usado para acessar o seu ambiente do Office 365.
- **[Acesso condicional](/azure/active-directory/conditional-access/overview.md)** — Azure AD avalia as condições do logon do usuário e usa políticas de acesso condicional que você cria para permitir o acesso. Por exemplo, neste guia mostraremos como criar uma política de acesso condicional para exigir conformidade do dispositivo para o acesso aos dados confidenciais. Isso reduz drasticamente o risco que um hacker com uma identidade roubado pode acessar seus dados confidenciais. Ele também protege dados confidenciais nos dispositivos porque os dispositivos aos requisitos específicos de saúde e segurança.
- **[Grupos do Azure AD](/azure/active-directory/fundamentals/active-directory-manage-groups.md)** — regras de acesso condicional, o gerenciamento de dispositivos com Intune, e pares permissões para sites em sua organização e arquivos dependem de atribuição para os usuários e/ou grupos do Azure AD. Recomendamos que você criar grupos de Azure AD que correspondem aos níveis de proteção que estiver implementando. Por exemplo, sua equipe de executivos é provavelmente destinos de valor mais altos para hackers. Portanto, faz sentido atribuir esses funcionários a um grupo do Windows Azure AD e atribuir esse grupo para políticas de acesso condicional e outras diretivas que impõe um nível mais alto de proteção para o access.
- **[O registro de dispositivos](/azure/active-directory/devices/overview.md)** — você registrar um dispositivo no Azure AD para fornecer uma identidade ao dispositivo. Essa identidade é usada para autenticar o dispositivo, quando um usuário entrar e aplicar regras de acesso condicional que exigem PCs compatíveis ou domínio. Para este guia, usamos o registro de dispositivos para registrar automaticamente computadores associados a um domínio do Windows. Registro de dispositivo é um pré-requisito para o gerenciamento de dispositivos com Intune. 
- **[Proteção de identidade do Windows Azure AD](/azure/active-directory/identity-protection/overview)** — proteção de identidade do Windows Azure AD permite detectar possíveis vulnerabilidades afetar identidades da sua organização e configurar a política de correção automatizada para baixo, médio e entrada de alto risco e risco do usuário. Esta orientação depende essa avaliação de risco para aplicar políticas de acesso condicional para a autenticação multifator. Este guia também inclui uma política de acesso condicional que requer que os usuários alterem sua senha, se forem detectadas atividades de alto risco para sua conta.

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune) é um serviço de gerenciamento de dispositivo móvel baseado em nuvem da Microsoft. Este guia recomenda o gerenciamento de dispositivos do Windows PCs com Intune e recomenda configurações de política de conformidade do dispositivo. Intune determina se os dispositivos são compatíveis com e envia esses dados para o Windows Azure AD para ser usado na aplicação de políticas de acesso condicional.

#### <a name="intune-app-protection"></a>Proteção de app Intune

Políticas de [proteção de app Intune](https://docs.microsoft.com/intune/app-protection-policy) podem ser usadas para proteger dados da sua empresa em aplicativos móveis com ou sem registro de dispositivos em gerenciamento. Intune ajuda a proteger as informações do Office 365, certificando-se de que seus funcionários ainda podem ser a perda de dados produtivos e impedindo. Implementando políticas no nível de aplicativo, você pode restringir o acesso aos recursos da empresa e manter os dados dentro do controle do seu departamento de TI.

Esta orientação mostra como criar políticas recomendadas para impor o uso de aplicativos aprovados e determinar como esses aplicativos podem ser usados com seus dados de negócios.

### <a name="office-365"></a>Office 365

Esta orientação mostra como implementar um conjunto de políticas para proteger o acesso ao Office 365, incluindo o Exchange Online, SharePoint Online e OneDrive for Business. Além de implementar essas diretivas, é recomendável que também aumentar o nível de proteção para o seu locatário do Office 365 usando estes recursos:

- [Configure seu locatário do Office 365 para aumentar a segurança](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355) — essas recomendações se aplicam à segurança de linha de base para seu locatário do Office 365.
- [Mapa de segurança do office 365: principais prioridades para os primeiros 30 dias, 90 dias e além](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) — essas recomendações incluem o registro em log, governança de dados, acesso de administrador e proteção contra ameaças.
- [Arquivos e sites seguro do SharePoint Online](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files) — este conjunto de artigos descreve como proteger os arquivos e os sites nos níveis apropriados para a proteção de linha de base, confidenciais e altamente confidenciais.

### <a name="windows-10-and-office-365-proplus"></a>Windows 10 e Office 365 ProPlus

10 do Windows e o Office 365 ProPlus são o ambiente de cliente recomendado para PCs. É recomendável 10 do Windows, como o Windows Azure é projetado para fornecer a experiência mais suave possível para o local e o Azure AD. Windows 10 também inclui recursos de segurança avançados que podem ser gerenciados por meio de Intune. O Office 365 ProPlus inclui as versões mais recentes dos aplicativos do Office. Essas usam autenticação moderna, que é mais segura e um requisito para acesso condicional. Esses aplicativos também incluem ferramentas aprimoradas de segurança e conformidade.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>Aplicando esses recursos em todos os três níveis de proteção

A tabela a seguir resume as nossas recomendações para o uso desses recursos em todos os três níveis de proteção.

|Mecanismo de proteção|Linha de base|Confidencial|Altamente controlada|
|:-------------------|:-------|:--------|:---------------|
|**Impor a MFA**|No risco de entrada médio ou acima|No risco de entrada baixo ou acima|Em todas as novas sessões|
|**Impor a alteração de senha**|Para usuários de alto risco|Para usuários de alto risco|Para usuários de alto risco|
|**Impor a proteção de aplicativos do Intune**|Sim|Sim|Sim|
|**Impor o registro do Intune (COD)**|Exige um compatível ou domínio ingressou PC, mas permitir BYOD telefones/tablets|Exigir um dispositivo em conformidade ou ingressado no domínio|Exigir um dispositivo em conformidade ou ingressado no domínio|

## <a name="device-ownership"></a>Propriedade do dispositivo

A tabela acima reflete a tendência para muitas organizações oferecer suporte a uma mistura de dispositivos de propriedade corporativo, bem como dispositivos pessoais ou traga-your-proprietário (BYOD) para habilitar a produtividade móvel entre a força de trabalho. Políticas de proteção de aplicativos Intune Certifique-se de que email é protegido contra exfiltrating sem os aplicativos móveis do Outlook e outros aplicativos móveis do Office, em dispositivos de propriedade corporativo e BYOD.  

Recomendamos que os dispositivos de propriedade corporativo ser gerenciados por Intune ou domínio para aplicar proteções adicionais e controle.  Sensibilidade de dados, dependendo da sua organização pode optar por não permitir BYOD população de usuários específicos ou aplicativos específicos.

## <a name="next-steps"></a>Próximas etapas

[Trabalho de pré-requisito para implementar políticas de acesso de dispositivo e identidade](identity-access-prerequisites.md)