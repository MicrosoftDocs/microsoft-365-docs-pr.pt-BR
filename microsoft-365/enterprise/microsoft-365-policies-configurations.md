---
title: Configurações de acesso de dispositivo e identidade-Microsoft 365 Enterprise
description: Descreve as recomendações da Microsoft e os conceitos principais para implantar políticas e configurações de email, documentos e aplicativos seguros.
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/11/2018
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 8d7adda0ded3a118676a67d0446a5744233468f3
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633259"
---
# <a name="identity-and-device-access-configurations"></a>Identidade e configurações de acesso ao dispositivo

Esta série de artigos descreve como configurar o acesso seguro aos serviços em nuvem por meio de produtos de EMS (Enterprise Mobility + Security) implementando um ambiente e uma configuração recomendados, incluindo um conjunto prescrito de políticas de acesso condicional e recursos relacionados. O EMS é um componente principal do Microsoft 365. Você pode usar estas diretrizes para proteger o acesso a todos os serviços integrados ao Azure Active Directory, incluindo os serviços do Office 365, outros serviços SaaS e aplicativos locais publicados com o proxy de aplicativo do Azure AD. 

Essas recomendações são alinhadas com a pontuação segura da Microsoft, bem como a [Pontuação de identidade no Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-secure-score), e aumentam essas pontuações para sua organização. Essas recomendações também ajudarão você a implementar essas [cinco etapas para proteger sua infraestrutura de identidade](https://docs.microsoft.com/azure/security/azure-ad-secure-steps). 

A Microsoft entende que algumas organizações têm requisitos ou complexidades de ambiente exclusivos. Se você for uma dessas organizações, use estas recomendações como ponto de partida. No entanto, a maioria das organizações pode implementar essas recomendações conforme prescrito. 

## <a name="intended-audience"></a>Público-alvo

Essas recomendações são direcionadas para arquitetos corporativos e profissionais de ti que estão familiarizados com o [Office 365](https://technet.microsoft.com/library/dn127064(v=office.14).aspx) e [o Microsoft Enterprise Mobility + Security](https://microsoft.com/ems), que inclui, entre outros, o Azure Active Directory (identidade), o Microsoft Intune (gerenciamento de dispositivos) e a proteção de informações do Azure (proteção de dados).

### <a name="customer-environment"></a>Ambiente do cliente

As políticas recomendadas são aplicáveis a organizações corporativas operando totalmente dentro da nuvem da Microsoft e para clientes com infraestrutura híbrida (implantadas no local e na nuvem da Microsoft).

Muitas das recomendações fornecidas dependem de serviços disponíveis somente com licenças do Enterprise Mobility + Security (EMS) e5. As recomendações apresentadas pressupõem recursos de licença Full EMS e5.

Para as organizações que não têm licenças do Enterprise Mobility + Security e5, a Microsoft recomenda que você, pelo menos, implemente os recursos de proteção de linha de base do Azure AD incluídos em todos os planos. É possível encontrar mais informações no artigo, [o que é proteção de linha de base](/azure/active-directory/active-directory-conditional-access-baseline-protection), na biblioteca do Azure AD.

### <a name="caveats"></a>ADVERTÊNCIAS

Sua organização pode estar sujeita à regulamentação ou outros requisitos de conformidade, incluindo recomendações específicas que podem exigir que você aplique políticas que divergem dessas configurações recomendadas. Essas configurações recomendam controles de uso que historicamente não estavam disponíveis. Recomendamos esses controles porque acreditamos que eles representam um equilíbrio entre produtividade e segurança.  

Fizemos nossa melhor consideração para uma ampla variedade de requisitos de proteção organizacional, mas não é possível considerar todos os requisitos possíveis ou todos os aspectos exclusivos da sua organização.

## <a name="three-tiers-of-protection"></a>Três camadas de proteção

A maioria das organizações tem requisitos específicos sobre segurança e proteção de dados. Esses requisitos variam por segmento do setor e por funções de trabalho dentro das organizações. Por exemplo, seu departamento jurídico e os administradores do Office 365 podem exigir controles de proteção de informações e segurança adicionais em sua correspondência de email que não são necessários para outros usuários da unidade de negócios. 

Cada setor também tem seu próprio conjunto de normas especializadas. Em vez de fornecer uma lista de todas as opções de segurança possíveis ou uma recomendação por segmento do setor ou função de trabalho, as recomendações foram fornecidas para três camadas diferentes de segurança e proteção que podem ser aplicadas com base na granularidade das suas necessidades .

- **Proteção de linha de base**: Recomendamos que você estabeleça um padrão mínimo para proteger os dados, bem como as identidades e dispositivos que acessam seus dados. Você pode seguir estas recomendações de linha de base para fornecer uma proteção padrão forte que atenda às necessidades de muitas organizações.
- **Proteção confidencial**: alguns clientes têm um subconjunto de dados que devem ser protegidos em níveis mais altos ou podem exigir que todos os dados sejam protegidos em um nível mais alto. Você pode aplicar mais proteção a todos ou conjuntos de dados específicos em seu ambiente do Office 365. É recomendável proteger identidades e dispositivos que acessam dados confidenciais com níveis compatíveis de segurança.  
- **Altamente regulamentado**: algumas organizações podem ter uma pequena quantidade de dados altamente classificados, segredos de comércio consititutes ou dados regulamentados. A Microsoft fornece recursos para ajudar as organizações a atender a esses requisitos, incluindo proteção adicional para identidades e dispositivos.

![Cone de segurança-todos os clientes > alguns clientes > clientes específicos. Aplicativo amplo para aplicativos específicos](../media/M365-idquality-threetiers.png)

Esta orientação mostra como implementar a proteção de identidades e dispositivos para cada uma dessas camadas de proteção. Use estas orientações como ponto de partida para sua organização e ajuste as políticas para atender aos requisitos específicos da sua organização.

É importante usar níveis consistentes de proteção nos dados, identidades e dispositivos. Por exemplo, se você implementar este guia, certifique-se de proteger seus dados em níveis comparáveis. Esses modelos de arquitetura mostram quais recursos são comparáveis.

**Proteção de identidade e dispositivo para o Office 365**<br/>
![Miniatura do pôster "proteção de identidade e dispositivo para o Office 365"](../media/O365_Identity_device_protection_thumb.png)<br/>
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Mais idiomas](https://www.microsoft.com/download/details.aspx?id=55032)

**Soluções para proteção de arquivos do Office 365**<br/>
![Miniatura do pôster "soluções de proteção de arquivo no Office 365"](../media/24be68b5-d852-4fdb-94ad-94491a19edd8.png)<br/>
[PDF](https://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.pdf) | [Visio](https://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.vsdx)

## <a name="security-and-productivity-trade-offs"></a>Vantagens e desvantagens de produtividade e segurança

Implementar qualquer estratégia de segurança exige variações entre segurança e produtividade. É útil avaliar como cada decisão afeta o equilíbrio de segurança, funcionalidade e facilidade de uso.

![Segurança Tríade balanceamento de segurança, funcionalidade e facilidade de uso.](../media/policies-configurations/security-triad.png)

As recomendações fornecidas são baseadas nos seguintes princípios:

- Conheça seu público e seja flexível para seus requisitos de segurança e funcionais.
- Aplique uma política de segurança no momento e assegure-se de que ela seja significativa.

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Serviços e conceitos de proteção de acesso de dispositivo e identidade

O Microsoft 365 Enterprise foi projetado para grandes organizações e integra o Office 365 Enterprise, o Windows 10 Enterprise e o Enterprise Mobility + Security (EMS), para permitir que todos sejam criativos e trabalhem em conjunto com segurança.

Esta seção fornece uma visão geral dos serviços e recursos do Microsoft 365 que são importantes para o acesso a identidades e dispositivos.

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

O Azure AD fornece um pacote completo de recursos de gerenciamento de identidades. Para proteger o acesso, recomendamos o uso dos seguintes recursos:

- **[Redefinição de senha de autoatendimento (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)**: permitir que os usuários redefinam suas senhas com segurança e sem a intervenção da assistência técnica, fornecendo a verificação de vários métodos de autenticação que o administrador pode controlar.

- **[Autenticação multifator (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)**: a MFA exige que os usuários forneçam duas formas de verificação, como a senha de um usuário, além de uma notificação do aplicativo Microsoft Authenticator ou de uma chamada telefônica. A MFA reduz muito o risco de que uma identidade roubada possa ser usada para acessar seu ambiente do Office 365.

- **[Acesso condicional](/azure/active-directory/conditional-access/overview)**: o Azure ad avalia as condições do logon do usuário e usa políticas de acesso condicional que você cria para permitir o acesso. Por exemplo, neste guia, mostraremos como criar uma política de acesso condicional para exigir a conformidade do dispositivo para acessar dados confidenciais. Isso reduz muito o risco de que um hacker com uma identidade roubada possa acessar seus dados confidenciais. Ele também protege dados confidenciais nos dispositivos, porque os dispositivos atendem aos requisitos específicos de integridade e segurança.

- **[Grupos do Azure ad](/azure/active-directory/fundamentals/active-directory-manage-groups)**: regras de acesso condicional, gerenciamento de dispositivos com o Intune e até mesmo permissões para arquivos e sites em sua organização, dependem da atribuição para os grupos de usuários e/ou do Azure AD. Recomendamos que você crie grupos do Azure AD que correspondam aos níveis de proteção que você está implementando. Por exemplo, sua equipe executiva é provavelmente metas de valor mais alto para hackers. Portanto, faz sentido atribuir esses funcionários a um grupo do Azure AD e atribuir esse grupo a políticas de acesso condicional e outras políticas que impõem um nível mais alto de proteção para o Access.

- **[Registro de dispositivo](/azure/active-directory/devices/overview)**: você registra um dispositivo no Azure ad para fornecer uma identidade ao dispositivo. Essa identidade é usada para autenticar o dispositivo quando um usuário entra e para aplicar as regras de acesso condicional que exigem computadores associados ou em conformidade com o domínio. Para este guia, usamos o registro de dispositivo para registrar automaticamente os computadores Windows associados ao domínio. O registro de dispositivo é um pré-requisito para gerenciar dispositivos com o Intune. 

- **[Proteção de identidade do Azure ad](/azure/active-directory/identity-protection/overview)**: o Azure ad Identity Protection permite que você detecte possíveis vulnerabilidades que afetam as identidades da sua organização e configure a política de correção automatizada para riscos de entrada baixa, média e alta e o risco do usuário. Este guia depende dessa avaliação de risco para aplicar políticas de acesso condicional para a autenticação multifator. Este guia também inclui uma política de acesso condicional que exige que os usuários alterem a senha se for detectada atividade de alto risco para a conta.

### <a name="microsoft-intune"></a>Microsoft Intune

O [Intune](https://docs.microsoft.com/intune/introduction-intune) é o serviço de gerenciamento de dispositivo móvel baseado em nuvem da Microsoft. Este guia recomenda o gerenciamento de dispositivos dos computadores Windows com o Intune e recomenda as configurações de política de conformidade de dispositivos. O Intune determina se os dispositivos são compatíveis e envia esses dados para o Azure AD usar ao aplicar políticas de acesso condicional.

#### <a name="intune-app-protection"></a>Proteção de aplicativos do Intune

As políticas de [proteção de aplicativos do Intune](https://docs.microsoft.com/intune/app-protection-policy) podem ser usadas para proteger os dados da sua organização em aplicativos móveis, com ou sem registrar dispositivos no gerenciamento. O Intune ajuda a proteger as informações do Office 365, assegurando que seus funcionários ainda possam ser produtivos e evitando a perda de dados. Ao implementar políticas de nível de aplicativo, você pode restringir o acesso aos recursos da empresa e manter os dados dentro do controle do departamento de ti.

Esta orientação mostra como criar políticas recomendadas para impor o uso de aplicativos aprovados e para determinar como esses aplicativos podem ser usados com seus dados corporativos.

### <a name="office-365"></a>Office 365

Esta orientação mostra como implementar um conjunto de políticas para proteger o acesso ao Office 365, incluindo o Exchange Online, o SharePoint Online e o OneDrive for Business. Além de implementar essas políticas, recomendamos que você também aumente o nível de proteção para o seu locatário do Office 365 usando estes recursos:

- [Configure seu locatário do Office 365 para maior segurança](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355): estas recomendações se aplicam à segurança de linha de base para seu locatário do Office 365.
- [Mapa de segurança do Office 365: principais prioridades para os primeiros 30 dias, 90 dias e mais](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352): estas recomendações incluem registro em log, governança de dados, acesso de administrador e proteção contra ameaças.


### <a name="windows-10-and-office-365-proplus"></a>Windows 10 e Office 365 ProPlus

O Windows 10 e o Office 365 ProPlus são o ambiente de cliente recomendado para computadores. Recomendamos o Windows 10, já que o Azure foi projetado para fornecer a experiência mais suave possível tanto para o local quanto para o AD do Azure. O Windows 10 também inclui recursos avançados de segurança que podem ser gerenciados por meio do Intune. O Office 365 ProPlus inclui as versões mais recentes dos aplicativos do Office. Eles usam autenticação moderna, que é mais segura e um requisito para acesso condicional. Esses aplicativos também incluem ferramentas aprimoradas de segurança e conformidade.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>Aplicação desses recursos nas três camadas de proteção

A tabela a seguir resume nossas recomendações para usar esses recursos nas três camadas de proteção.

|Mecanismo de proteção|Linha de base|Confidencial|Altamente controlada|
|:-------------------|:-------|:--------|:---------------|
|**Impor a MFA**|No risco de entrada médio ou acima|No risco de entrada baixo ou acima|Em todas as novas sessões|
|**Impor alteração de senha**|Para usuários de alto risco|Para usuários de alto risco|Para usuários de alto risco|
|**Impor a proteção de aplicativos do Intune**|Sim|Sim|Sim|
|**Impor registro do Intune (COD)**|Exigir um computador de conformidade ou ingressado no domínio, mas permitir telefones/tablets BYOD|Exigir um dispositivo em conformidade ou ingressado no domínio|Exigir um dispositivo em conformidade ou ingressado no domínio|

## <a name="device-ownership"></a>Propriedade do dispositivo

A tabela acima reflete a tendência de muitas organizações de oferecer suporte a uma combinação de dispositivos de propriedade corporativa, bem como dispositivos pessoais ou de BYODs ((em inglês) para habilitar a produtividade móvel em toda a força de mesa. As políticas de proteção de aplicativos do Intune garantem que o email seja protegido de exfiltrating fora do aplicativo móvel do Outlook e outros aplicativos do Office Mobile, tanto em dispositivos de propriedade corporativa quanto em BYODs.  

Recomendamos que os dispositivos de propriedade corporativa sejam gerenciados pelo Intune ou que ingressou no domínio para aplicar proteções e controle adicionais. Dependendo da confidencialidade de dados, sua organização pode optar por não permitir o BYODs para populações de usuários específicos ou aplicativos específicos.

## <a name="next-steps"></a>Próximas etapas

[Trabalho de pré-requisito para implementar as políticas de acesso de dispositivo e identidade](identity-access-prerequisites.md)
