---
title: Configurações de identidade e acesso a dispositivos - Microsoft 365 para empresas
description: Descreve as recomendações e os conceitos principais da Microsoft para a implantação de configurações e políticas de email, documentos e aplicativos seguros.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-overview
ms.technology: mdo
ms.openlocfilehash: 948f4515b37f27695e1e66730134aa19114ca1cf
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538994"
---
# <a name="identity-and-device-access-configurations"></a>Identidade e configurações de acesso ao dispositivo

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)

O perímetro de segurança moderno da sua organização agora se estende além de sua rede para incluir usuários acessando aplicativos baseados em nuvem de qualquer local com uma variedade de dispositivos. Sua infraestrutura de segurança precisa determinar se uma determinada solicitação de acesso deve ser concedida e em quais condições.

Essa determinação deve se basear na conta de usuário da entrada, no dispositivo que está sendo usado, no aplicativo que o usuário está usando para acesso, no local do qual a solicitação de acesso é feita e em uma avaliação do risco da solicitação. Esse recurso ajuda a garantir que apenas usuários e dispositivos aprovados possam acessar os recursos críticos.

Esta série de artigos descreve um conjunto de configurações de pré-requisitos de identidade e acesso a dispositivos e um conjunto de acesso condicional do Azure Active Directory (Azure AD), Microsoft Intune e outras políticas para proteger o acesso ao Microsoft 365 para aplicativos e serviços de nuvem empresariais, outros serviços SaaS e aplicativos locais publicados com o Proxy de Aplicativo do Azure AD.

As configurações e políticas de acesso a dispositivos e identidades são recomendadas em três camadas: proteção de linha de base, proteção confidencial e proteção para ambientes com dados altamente regulamentados ou classificados. Essas camadas e suas configurações correspondentes fornecem níveis consistentes de proteção em seus dados, identidades e dispositivos.

Esses recursos e suas recomendações:

- São suportados em Microsoft 365 E3 e Microsoft 365 E5.
- Estão alinhados com a [Pontuação](../defender/microsoft-secure-score.md) Segura da Microsoft, bem como a pontuação de identidade no [Azure AD,](/azure/active-directory/fundamentals/identity-secure-score)e aumentarão essas pontuações para sua organização.
- Ajudará você a implementar essas [cinco etapas para proteger sua infraestrutura de identidade.](/azure/security/azure-ad-secure-steps)

Se sua organização tiver requisitos ou complexidades de ambiente exclusivos, use essas recomendações como ponto de partida. No entanto, a maioria das organizações pode implementar essas recomendações conforme prescrito.

Assista a este vídeo para uma visão geral rápida das configurações de identidade e acesso a dispositivos Microsoft 365 para empresas.

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxEDQ]

> [!NOTE]
> A Microsoft também vende Enterprise Mobility + Security (EMS) para Office 365 assinaturas. Os recursos EMS E3 e EMS E5 são equivalentes aos de Microsoft 365 E3 e Microsoft 365 E5. Consulte [Planos emS](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing) para obter os detalhes.

## <a name="intended-audience"></a>Público-alvo pretendido

Essas recomendações destinam-se a arquiteto Microsoft 365 s corporativos e profissionais de TI que estão familiarizados com os serviços de segurança e produtividade na nuvem, que inclui o Azure AD (identidade), o Microsoft Intune (gerenciamento de dispositivos) e a Proteção de Informações da Microsoft (proteção de dados).

### <a name="customer-environment"></a>Ambiente do cliente

As políticas recomendadas são aplicáveis a organizações corporativas que operam inteiramente dentro da nuvem da Microsoft e para clientes com infraestrutura de identidade híbrida, que é uma floresta local dos Serviços de Domínio do Active Directory (AD DS) sincronizada com um locatário do Azure AD.

Muitas das recomendações fornecidas dependem de serviços disponíveis apenas com o Microsoft 365 E5, Microsoft 365 E3 com as licenças de complemento de Segurança do E5, EMS E5 ou Azure AD Premium P2.

Para essas organizações que não têm essas licenças, a Microsoft recomenda que você implemente pelo menos os padrões de segurança , que estão [incluídos](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)em todos os Microsoft 365 planos.

### <a name="caveats"></a>Advertências

Sua organização pode estar sujeita a requisitos regulatórios ou outros requisitos de conformidade, incluindo recomendações específicas que podem exigir que você aplique políticas que divergem dessas configurações recomendadas. Essas configurações recomendam controles de uso que historicamente não estavam disponíveis. Recomendamos esses controles porque acreditamos que eles representam um equilíbrio entre a segurança e a produtividade.

Fizemos o possível para levar em conta uma ampla variedade de requisitos de proteção organizacional, mas não somos capazes de responder por todos os requisitos possíveis ou por todos os aspectos exclusivos da sua organização.

## <a name="three-tiers-of-protection"></a>Três camadas de proteção

A maioria das organizações tem requisitos específicos sobre segurança e proteção de dados. Esses requisitos variam por segmento do setor e por funções de trabalho dentro das organizações. Por exemplo, seu departamento jurídico e administradores podem exigir controles adicionais de segurança e proteção de informações em torno de suas correspondências de email que não são necessárias para outras unidades de negócios.

Cada setor também tem seu próprio conjunto de normas especializadas. Em vez de fornecer uma lista de todas as opções de segurança possíveis ou uma recomendação por segmento do setor ou função de trabalho, recomendações foram fornecidas para três camadas diferentes de segurança e proteção que podem ser aplicadas com base na granularidade de suas necessidades.

- **Proteção de linha** de base : recomendamos que você estabeleça um padrão mínimo para proteger dados, bem como as identidades e dispositivos que acessam seus dados. Você pode seguir essas recomendações de linha de base para fornecer uma proteção padrão forte que atenda às necessidades de muitas organizações.
- **Proteção sensível**: alguns clientes têm um subconjunto de dados que devem ser protegidos em níveis mais altos ou podem exigir que todos os dados sejam protegidos em um nível superior. Você pode aplicar maior proteção a todos ou conjuntos de dados específicos em seu Microsoft 365 ambiente. É recomendável proteger identidades e dispositivos que acessam dados confidenciais com níveis compatíveis de segurança.
- **Altamente regulamentado:** algumas organizações podem ter uma pequena quantidade de dados altamente classificados, constituir segredos comerciais ou são dados regulamentados. A Microsoft fornece recursos para ajudar as organizações a atender a esses requisitos, incluindo proteção adicional para identidades e dispositivos.

![Cone de segurança - Todos os clientes > alguns clientes > clientes específicos. Aplicativo amplo para aplicativo específico](../../media/microsoft-365-policies-configurations/M365-idquality-threetiers.png)

Esta orientação mostra como implementar a proteção para identidades e dispositivos para cada uma dessas camadas de proteção. Use essa orientação como ponto de partida para sua organização e ajuste as políticas para atender aos requisitos específicos da sua organização.

É importante usar níveis consistentes de proteção para dados, identidades e dispositivos. Por exemplo, se você implementar essas diretrizes, certifique-se de proteger seus dados em níveis comparáveis.

A **proteção de identidade e dispositivo para Microsoft 365** de arquitetura mostra quais recursos são comparáveis.

[![Imagem em miniatura para identidade e proteção de dispositivo para Microsoft 365 cartaz](../../media/microsoft-365-policies-configurations/O365_Identity_device_protection_thumb.png)](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) <br> [Exibir como um PDF](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Baixar como um PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Baixar como um Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.vsdx)  

Além disso, consulte a solução [Implantar proteção de informações para regulamentos](../../solutions/information-protection-deploy.md) de privacidade de dados para proteger informações armazenadas em Microsoft 365.

## <a name="security-and-productivity-trade-offs"></a>Vantagens e desvantagens de produtividade e segurança

Implementar qualquer estratégia de segurança requer trocas entre segurança e produtividade. É útil avaliar como cada decisão afeta o equilíbrio de segurança, funcionalidade e facilidade de uso.

![Segurança e segurança de balanceamento de segurança, funcionalidade e facilidade de uso.](../../media/microsoft-365-policies-configurations/security-triad.png)

As recomendações fornecidas se baseiam nos seguintes princípios:

- Conheça seus usuários e seja flexível para seus requisitos de segurança e funcional.
- Aplique uma política de segurança a tempo e certifique-se de que ela seja significativa.

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Serviços e conceitos para proteção de identidade e acesso a dispositivos

Microsoft 365 para empresas foi projetado para grandes organizações para capacitar todos a serem criativos e trabalharem juntos com segurança.

Esta seção fornece uma visão geral dos serviços Microsoft 365 e recursos importantes para o acesso à identidade e ao dispositivo.

### <a name="azure-ad"></a>Azure Active Directory

O Azure AD fornece um pacote completo de recursos de gerenciamento de identidade. Recomendamos usar esses recursos para proteger o acesso.

|Capcidade ou recurso|Descrição|Licenças|
|---|---|---|
|[MFA (Autenticação Multifator)](/azure/active-directory/authentication/concept-mfa-howitworks)|O MFA exige que os usuários forneçam duas formas de verificação, como uma senha de usuário, além de uma notificação do aplicativo Microsoft Authenticator ou de uma chamada telefônica. A MFA reduz consideravelmente o risco de que credenciais roubadas possam ser usadas para acessar seu ambiente. Microsoft 365 usa o serviço de Autenticação Multifatória do Azure AD para entrar com base em MFA.|Microsoft 365 E3 ou E5|
|[Acesso condicional](/azure/active-directory/conditional-access/overview)|O Azure AD avalia as condições da entrada do usuário e usa políticas de Acesso Condicional para determinar o acesso permitido. Por exemplo, nesta orientação, mostramos como criar uma política de Acesso Condicional para exigir a conformidade do dispositivo para acesso a dados confidenciais. Isso reduz consideravelmente o risco de que um hacker com seu próprio dispositivo e credenciais roubadas possa acessar seus dados confidenciais. Ele também protege dados confidenciais nos dispositivos, pois os dispositivos devem atender aos requisitos específicos de segurança e saúde.|Microsoft 365 E3 ou E5|
|[Grupos do Azure AD](/azure/active-directory/fundamentals/active-directory-manage-groups)|Políticas de Acesso Condicional, gerenciamento de dispositivos com o Intune e até mesmo permissões para arquivos e sites em sua organização dependem da atribuição para contas de usuário ou grupos do Azure AD. Recomendamos que você crie grupos do Azure AD que correspondam aos níveis de proteção que você está implementando. Por exemplo, sua equipe executiva provavelmente são alvos de valores mais altos para hackers. Portanto, faz sentido adicionar as contas de usuário desses funcionários a um grupo do Azure AD e atribuir esse grupo a políticas de Acesso Condicional e outras políticas que impõem um nível mais alto de proteção para acesso.|Microsoft 365 E3 ou E5|
|[Registro de dispositivo](/azure/active-directory/devices/overview)|Você registra um dispositivo no Azure AD para criar uma identidade para o dispositivo. Essa identidade é usada para autenticar o dispositivo quando um usuário entra e para aplicar políticas de Acesso Condicional que exigem PCs ingressados no domínio ou compatíveis. Para essa orientação, usamos o registro de dispositivo para registrar automaticamente computadores ingressados Windows domínio. O registro de dispositivo é um pré-requisito para gerenciar dispositivos com o Intune.|Microsoft 365 E3 ou E5|
|[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview)|Permite detectar possíveis vulnerabilidades que afetam as identidades da sua organização e configurar a política de correção automatizada para baixo, médio e alto risco de login e risco de usuário. Essa orientação baseia-se nessa avaliação de risco para aplicar políticas de Acesso Condicional para autenticação multifacional. Essa orientação também inclui uma política de Acesso Condicional que exige que os usuários alterem sua senha se atividades de alto risco são detectadas para suas contas.|Microsoft 365 E5, Microsoft 365 E3 com o complemento E5 Security, EMS E5 ou licenças do Azure AD Premium P2|
|[Redefinição de senha de autoatendados (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)|Permita que os usuários redefinam suas senhas com segurança e sem intervenção do help-desk, fornecendo a verificação de vários métodos de autenticação que o administrador pode controlar.|Microsoft 365 E3 ou E5|
|[Proteção de senha do Azure AD](/azure/active-directory/authentication/concept-password-ban-bad)|Detecte e bloqueie senhas fracas conhecidas e suas variantes e termos fracos adicionais específicos para sua organização. Listas de senhas globais proibidas padrão são aplicadas automaticamente a todos os usuários em um locatário do Microsoft Azure AD. Você pode definir entradas adicionais em uma lista de senhas proibidas personalizadas. Quando os usuários alteram ou redefinem suas senhas, essas listas de senhas proibidas são verificadas para garantir o uso de senhas fortes.|Microsoft 365 E3 ou E5|
|

Aqui estão os componentes de acesso de identidade e dispositivo, incluindo objetos, configurações e subservidores do Intune e do Azure AD.

![Componentes de acesso de identidade e dispositivo](../../media/microsoft-365-policies-configurations/identity-device-access-components.png)

### <a name="microsoft-intune"></a>Microsoft Intune

[O Intune](/intune/introduction-intune) é o serviço de gerenciamento de dispositivo móvel baseado na nuvem da Microsoft. Essa orientação recomenda o gerenciamento de dispositivos de Windows PCs com o Intune e recomenda configurações de política de conformidade de dispositivo. O Intune determina se os dispositivos são compatíveis e envia esses dados para o Azure AD para usar ao aplicar políticas de Acesso Condicional.

#### <a name="intune-app-protection"></a>Proteção de aplicativo do Intune

As políticas de proteção de aplicativos do [Intune](/intune/app-protection-policy) podem ser usadas para proteger os dados da sua organização em aplicativos móveis, com ou sem registrar dispositivos no gerenciamento. O Intune ajuda a proteger informações, garantir que seus funcionários ainda possam ser produtivos e evitar a perda de dados. Ao implementar políticas no nível do aplicativo, você pode restringir o acesso aos recursos da empresa e manter os dados no controle do departamento de TI.

Essas diretrizes mostram como criar políticas recomendadas para impor o uso de aplicativos aprovados e determinar como esses aplicativos podem ser usados com seus dados comerciais.

### <a name="microsoft-365"></a>Microsoft 365

Essas diretrizes mostram como implementar um conjunto de políticas para proteger o acesso a serviços de nuvem Microsoft 365, incluindo Microsoft Teams, Exchange Online, SharePoint Online e OneDrive for Business. Além de implementar essas políticas, recomendamos que você também eleva o nível de proteção para seu locatário usando esses recursos:

- [Configurar locatário para aumentar a segurança](tenant-wide-setup-for-increased-security.md)

  Recomendações que se aplicam à segurança da linha de base para seu locatário.

- [Roteiro de segurança: principais prioridades para os primeiros 30 dias, 90 dias e além](security-roadmap.md)

  Recomendações que incluem log, governança de dados, acesso de administrador e proteção contra ameaças.

### <a name="windows-10-and-microsoft-365-apps-for-enterprise"></a>Aplicativos do Windows 10 e do Microsoft 365 para empresas

Windows 10 com Microsoft 365 Apps para Grandes Empresas é o ambiente cliente recomendado para PCs. Recomendamos Windows 10 porque o Azure foi projetado para oferecer a experiência mais suave possível tanto para o local quanto para o Azure AD. Windows 10 também inclui recursos avançados de segurança que podem ser gerenciados por meio do Intune. Microsoft 365 Apps para Grandes Empresas inclui as versões mais recentes de Office aplicativos. Eles usam autenticação moderna, que é mais segura e um requisito para o Acesso Condicional. Esses aplicativos também incluem ferramentas de segurança e conformidade aprimoradas.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>Aplicar esses recursos nas três camadas de proteção

A tabela a seguir resume nossas recomendações para usar esses recursos nas três camadas de proteção.

|Mecanismo de proteção|Linha de base|Confidencial|Altamente controlado|
|---|---|---|---|
|**Impor a MFA**|No risco de entrada médio ou acima|No risco de entrada baixo ou acima|Em todas as novas sessões|
|**Impor alteração de senha**|Para usuários de alto risco|Para usuários de alto risco|Para usuários de alto risco|
|**Impor a proteção de aplicativos do Intune**|Sim|Sim|Sim|
|**Impor o registro do Intune para dispositivos de propriedade da organização**|Exigir um computador compatível ou ingressado em domínio, mas permitir telefones e tablets de dispositivos BYOD (dispositivos de uso próprio)|Exigir um dispositivo compatível ou ingressado em domínio|Exigir um dispositivo compatível ou ingressado em domínio|
|

## <a name="device-ownership"></a>Propriedade do dispositivo

A tabela acima reflete a tendência de muitas organizações suportarem uma combinação de dispositivos de propriedade da organização, bem como byods pessoais ou pessoais para habilitar a produtividade móvel em toda a força de trabalho. As políticas de proteção de aplicativos do Intune garantem que o email seja protegido contra exfiltração do aplicativo móvel Outlook e outros aplicativos móveis Office, em dispositivos de propriedade da organização e BYODs.

Recomendamos que os dispositivos de propriedade da organização sejam gerenciados pelo Intune ou ingressados no domínio para aplicar proteções e controle adicionais. Dependendo da sensibilidade dos dados, sua organização pode optar por não permitir BYODs para populações de usuários específicas ou aplicativos específicos.

## <a name="deployment-and-your-apps"></a>Implantação e seus aplicativos

Antes de configurar e lançar a configuração de identidade e acesso a dispositivos para seus aplicativos integrados ao Azure AD, você deve:

- Decida quais aplicativos usados em sua organização você deseja proteger.
- Analise essa lista de aplicativos para determinar os conjuntos de políticas que fornecem níveis apropriados de proteção.

  Você não deve criar conjuntos separados de políticas para cada aplicativo porque o gerenciamento delas pode se tornar complicado. A Microsoft recomenda agrupar seus aplicativos que tenham os mesmos requisitos de proteção para os mesmos usuários.

  Por exemplo, você pode ter um conjunto de políticas que incluam todos os aplicativos Microsoft 365 para todos os seus usuários para proteção de linha de base e um segundo conjunto de políticas para todos os aplicativos confidenciais, como os usados por recursos humanos ou departamentos financeiros, e aplicá-los a esses grupos.

Depois de determinar o conjunto de políticas para os aplicativos que você deseja proteger, role as políticas para seus usuários incrementalmente, abordando problemas ao longo do caminho.

Por exemplo, configure as políticas que serão usadas para todos os seus aplicativos Microsoft 365 para apenas Exchange Online com as alterações adicionais para Exchange. Role essas políticas para seus usuários e trabalhe em todos os problemas. Em seguida, adicione Teams com suas alterações adicionais e role isso para seus usuários. Em seguida, adicione SharePoint com suas alterações adicionais. Continue adicionando o restante de seus aplicativos até que você possa configurar essas políticas de linha de base com confiança para incluir todos os Microsoft 365 aplicativos.

Da mesma forma, para seus aplicativos confidenciais, crie o conjunto de políticas e adicione um aplicativo por vez e trabalhe por todos os problemas até que todos eles sejam incluídos no conjunto de políticas de aplicativos confidenciais.

A Microsoft recomenda que você não crie conjuntos de políticas que se apliquem a todos os aplicativos porque isso pode resultar em algumas configurações não intencional. Por exemplo, as políticas que bloqueiam todos os aplicativos podem bloquear os administradores do portal do Azure e as exclusões não podem ser configuradas para pontos de extremidade importantes, como o Microsoft Graph.

## <a name="steps-to-configure-identity-and-device-access"></a>Etapas para configurar o acesso de identidade e dispositivo

![Etapas para configurar a identidade e o acesso ao dispositivo.](../../media/microsoft-365-policies-configurations/identity-device-access-steps.png)

1. Configure os recursos de identidade de pré-requisito e suas configurações.
2. Configure a identidade comum e acesse políticas de Acesso Condicional.
3. Configurar políticas de Acesso Condicional para usuários convidados e externos.
4. Configure políticas de Acesso Condicional Microsoft 365 aplicativos de nuvem─ como Microsoft Teams, Exchange Online e SharePoint─ e Microsoft Cloud App Security.

Depois de configurar o acesso a identidades e dispositivos, consulte o guia de implantação de recursos do [Azure AD](/azure/active-directory/fundamentals/active-directory-deployment-checklist-p2) para obter uma lista de verificação em fases de recursos adicionais a considerar e a Governança de Identidade do [Azure AD](/azure/active-directory/governance/) para proteger, monitorar e auditar o acesso.

## <a name="next-step"></a>Próxima etapa

[Trabalho de pré-requisito para implementar políticas de acesso a dispositivos e identidades](identity-access-prerequisites.md)