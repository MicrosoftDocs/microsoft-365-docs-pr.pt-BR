---
title: Infraestrutura de base não empresarial do Microsoft 365 para empresas
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/08/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Percorra as fases simplificadas da infraestrutura de base do Microsoft 365 para empresas para organizações não empresariais.
ms.openlocfilehash: e1c747e5f4ab3e58adeaf91518512d8ece83d91b
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011894"
---
# <a name="microsoft-365-for-enterprise-foundation-infrastructure-for-non-enterprises"></a>Infraestrutura de base não empresarial do Microsoft 365 para empresas

Organizações não empresariais também podem implantar o Microsoft 365 para empresas e perceber o valor comercial de uma infraestrutura integrada e segura, que permite o trabalho em equipe e desbloqueia a criatividade. Uma organização não empresarial tipicamente possui:

- Uma pequena quantidade de infraestrutura de TI local, como servidores de email e de arquivos e um domínio dos Serviços de Domínio do Active Directory (AD DS), ou nada.
- Uma pequena equipe de TI, composta em sua maioria por generalistas de TI, em vez de especialistas em uma tecnologia ou carga de trabalho específica, como rede ou email.

Para organizações menores, não corporativas, a Microsoft oferece o [Microsoft 365 for business](https://www.microsoft.com/microsoft-365/business). No entanto, existem razões pelas quais você pode precisar do Microsoft 365 para empresas, como por exemplo:

- Sua organização precisa de mais ou precisará de mais de 300 licenças do Microsoft 365, que é o máximo para o Microsoft 365 for business.
- Sua organização precisa dos recursos avançados de produtividade, voz, segurança e análise que não estão disponíveis no Microsoft 365 for business.

Este artigo orienta você para a realização de uma implantação simplificada da infraestrutura de base do Microsoft 365 para empresas adequada para a sua organização não empresarial.

## <a name="first-set-up-your-subscription"></a>Primeiro, configure sua assinatura

Você deve configurar os domínios do Sistema de Nomes de Domínio (DNS) para sua assinatura. Se você já possui uma assinatura do Microsoft 365, isso já deve ter sido feito. Caso contrário, siga as instruções em [Adicionar um domínio ao Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain?view=o365-worldwide).

Em seguida, você precisará configurar segurança adicional para o Microsoft 365. Siga as instruções em [Configurar segurança aumentada](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

## <a name="phase-1-networking"></a>Fase 1: Rede

Organizações não empresariais geralmente têm conexões locais com a Internet em cada escritório e não usam servidores proxy, firewalls ou dispositivos de inspeção de pacotes. O provedor de serviços de Internet (ISP) que atende a cada escritório possui um servidor DNS regionalmente local, para que o tráfego seja direcionado para o local de rede do Microsoft 365 mais próximo de seus escritórios e de seus usuários locais. Para obter mais informações, confira [Configurar conexões de Internet locais para cada escritório](networking-dns-resolution-same-location.md).

Portanto, você precisa apenas verificar com seu ISP a conexão em cada um dos locais de seu escritório:

- Usa um servidor DNS regionalmente local.
- É adequada para as suas necessidades atuais e futuras à medida que seus usuários comecem a usar mais serviços de nuvem do Microsoft 365.

Se você usa servidores proxy, firewalls ou dispositivos de inspeção de pacotes, confira [Configurar o bypass de tráfego](networking-configure-proxies-firewalls.md) para obter informações sobre como otimizar o desempenho dos serviços do Microsoft 365.

### <a name="your-configuration-so-far"></a>Sua configuração até agora

Aqui está um resumo visual com o elemento da Fase 1 em destaque. **Sua organização** pode ter vários escritórios, cada um com uma conexão de Internet local com um ISP (provedor de serviços de Internet) que usa um servidor DNS regionalmente local. Por meio do ISP, os usuários em cada escritório podem acessar o local de rede da Microsoft 365 mais próximo e os recursos da sua assinatura do Microsoft 365.

![Sua organização depois da fase de rede](../media/deploy-foundation-infrastructure-non-enterprises/networking-config.png)

## <a name="phase-2-identity"></a>Fase 2: Identidade

Cada funcionário da sua organização deve poder entrar, o que exige uma conta de usuário no locatário do Azure Active Directory (Azure AD) da sua assinatura do Microsoft 365 para empresas. Grupos são usados ​​para conter contas de usuário e outros grupos para se comunicar ou obter acesso a recursos autorizados, como um site do SharePoint Online ou uma equipe. 

### <a name="administrator-accounts"></a>Contas de administrador

Proteja suas contas de usuário de administrador global exigindo senhas fortes e MFA (Autenticação Multifator). Para obter mais informações, confira [Proteger as contas de administrador global](identity-create-protect-global-admins.md#protect-global-administrator-accounts).

Se a sua organização exigir alta segurança e você tiver o Microsoft 365 E5, use o Azure AD Privileged Identity Management para habilitar o acesso just-in-time de administrador. Confira [Configurar administradores globais sob demanda](identity-create-protect-global-admins.md#identity-pim) para obter mais informações.

### <a name="recommendations-for-groups"></a>Recomendações para grupos

Se você tiver um domínio do AD DS no local, continue usando esses grupos no Microsoft 365 para empresas como grupos no Azure AD.

Se você não tem um domínio do AD DS no local, crie grupos de segurança no Azure AD usando esses níveis de segurança.

| Nível de segurança | Descrição | Exemplos |
|:-------|:-----|:-----|
| Linha de base | Este é um padrão mínimo para proteger dados e as identidades e dispositivos que acessam seus dados. <BR><BR> Normalmente, estes são os dados da sua organização gerenciados pela maioria dos seus usuários. | Grupos para trabalhadores de primeira linha, como de vendas, marketing, suporte, administração e manufatura. |
| Confidencial | Esta é uma proteção adicional para um subconjunto de dados que deve ser protegido além do nível da linha de base. Esses grupos contêm usuários que usam e criam dados confidenciais específicos de departamentos e projetos que não devem estar disponíveis para todos. | Equipes de produtos ou marketing que estão desenvolvendo produtos futuros |
| Altamente controlado | Este é o nível mais alto de proteção para uma quantidade normalmente pequena de dados altamente confidenciais, considerados propriedade intelectual ou segredo comercial, ou dados que devem obedecer a regulamentações de segurança. |  Equipes de pesquisa, jurídica e financeira ou equipes que armazenam ou usam dados de clientes ou parceiros. |
||||

### <a name="hybrid-identity"></a>Identidade híbrida

Se você tiver um domínio do AD DS local, precisará sincronizar o conjunto de contas de usuários, grupos e contatos do seu domínio com o locatário do Azure AD de sua assinatura do Microsoft 365 para empresas. Se você tiver um domínio do AD DS no local, configure o Azure AD Connect em um servidor com PHS (sincronização de hash de senha). Confira [Sincronizar identidades](identity-add-user-accounts.md#synchronize-identities-for-hybrid-identity) para obter mais informações.

### <a name="more-secure-user-access-with-conditional-access-policies"></a>Acesso de usuário mais seguro com políticas de Acesso Condicional

O Azure AD avalia as condições de logons de usuários e pode usar políticas de Acesso Condicional para conceder ou negar o acesso, bem como impor outras ações que devem ser tomadas para concluir o logon. Por exemplo, se o Azure AD determinar que o logon está acontecendo sob condições de médio ou alto risco, ele pode exigir que o usuário execute o MFA para concluir o logon.

Você aplica políticas de Acesso Condicional a contas ou grupos de usuários. Para facilitar uma atribuição mais fácil de políticas de Acesso Condicional, crie esses grupos de segurança do Azure AD em sua organização:

- LINHA DE BASE

  Contém os grupos ou contas de usuários para usuários com acesso a dados de linha de base.

- CONFIDENCIAL

  Contém os grupos ou contas de usuários para usuários com acesso a dados confidenciais.

- ALTAMENTE REGULAMENTADO

  Contém os grupos ou contas de usuários para usuários com acesso a dados altamente regulamentados.

- COND-ACCESS-EXCLUDE

  Um grupo vazio que você pode usar para excluir temporariamente um usuário de políticas de Acesso Condicional.

Esta é a lista de políticas de Acesso Condicional do Azure AD a ser habilitada ou criada.

| Política de Acesso Condicional do Azure AD | Grupos aos quais se aplica |
|:------|:-----|
| Política de linha de base: exigir MFA para administradores | Esta política se aplica a funções administrativas, portanto, nenhum grupo precisa ser especificado. Esta política precisa ser ativada. Todas as políticas subsequentes precisam ser criadas e ativadas. |
| Bloquear clientes que não oferecem suporte à autenticação moderna | Selecione “Todos os usuários” nas configurações de política. |
| Exigir MFA quando o risco de logon é médio ou alto (requer o Microsoft 365 E5) | LINHA DE BASE |
| Exigir MFA quando o risco de logon é baixo, médio ou alto (requer o Microsoft 365 E5) | CONFIDENCIAL |
| Sempre exigir MFA | ALTAMENTE REGULAMENTADO |
| Exigir aplicativos aprovados em dispositivos iOS e Android | LINHA DE BASE, CONFIDENCIAL, ALTAMENTE REGULAMENTADO |
| Exigir PCs compatíveis | LINHA DE BASE |
| Exigir PCs compatíveis e dispositivos iOS e Android | CONFIDENCIAL, ALTAMENTE REGULAMENTADO |
|||

Aqui está a política de risco do usuário do Azure AD Identity Protection (requer o Microsoft 365 E5) para criar e ativar.

| Política de risco do usuário do Azure AD Identity Protection | Grupos aos quais se aplica |
|:------|:-----|
| Usuários de alto risco devem alterar suas senhas | Selecione “Todos os usuários” nas configurações de política. |
|||

Confira [Políticas comuns de acesso a identidades e dispositivos](identity-access-policies.md) para obter instruções.

### <a name="groups-for-easier-management"></a>Grupos para um gerenciamento mais fácil

Aqui estão alguns recursos que podem tornar o gerenciamento de grupos e licenças mais fácil para você.

| Recurso | Usar |
|:------|:-----|
| Gerenciamento de grupo de autoatendimento | Permitir o gerenciamento de grupos do Azure AD por proprietários de grupos em vez da equipe de TI. Confira [Gerenciamento de grupo de autoatendimento](identity-use-group-management.md#allow-users-to-create-and-manage-their-own-groups) para obter mais informações. |
| Associação de grupos dinâmicos | Configurar adição ou remoção automática de contas de usuários de grupos do Azure AD com base nos atributos da conta do usuário, como Departamento ou País. Confira [Associação de grupos dinâmicos](identity-use-group-management.md#set-up-dynamic-group-membership) para obter mais informações. |
| Licenciamento com base em grupo | Use a associação a grupos para atribuir ou cancelar a atribuição de licenças a contas de usuários automaticamente. Confira [Licenciamento baseado em grupo](identity-use-group-management.md#set-up-automatic-licensing) para obter mais informações. |
|  |  |

Se você estiver usando licenciamento baseado em grupo, crie um grupo denominado LICENCIADO para conter nomes de contas de usuários que possuem atribuída uma licença do Microsoft 365 para empresas.

### <a name="monitor-user-access"></a>Monitorar o acesso a usuários

Se você tiver o Microsoft 365 E5, poderá usar o Azure AD Identity Protection para monitorar e analisar logons de usuário para detectar comprometimento de credenciais. Confira [Proteger contra comprometimento de credenciais](identity-secure-user-sign-ins.md#protect-against-credential-compromise) para obter mais informações.

### <a name="your-configuration-so-far"></a>Sua configuração até agora

Aqui está um resumo visual da fase Identidade para identidade híbrida, com elementos novos e existentes destacados.

![Sua organização após a fase Identidade para identidade híbrida](../media/deploy-foundation-infrastructure-non-enterprises/identity-config.png)
 
Os novos e destacados elementos de identidade híbrida incluem:
 
|||
|:------:|:-----|
| ![Um domínio local do AD DS com contas e grupos de usuários](../media/deploy-foundation-infrastructure-non-enterprises/identity-adds.png) | Um domínio local do AD DS com contas e grupos de usuários. |
| ![Um servidor baseado no Windows executando o Azure AD Connect](../media/deploy-foundation-infrastructure-non-enterprises/identity-aadconnect.png) | Um servidor baseado no Windows executando o Azure AD Connect. |
| ![O conjunto sincronizado de contas e grupos de usuários do AD DS no Azure AD](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-accounts.png) | O conjunto sincronizado de contas e grupos de usuários do AD DS no Azure AD. |
| ![Configurações do Azure AD para autenticação, proteção de contas globais e simplificação do gerenciamento de grupos e licenças](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | Configurações do Azure AD para autenticação, proteção de contas globais e simplificação do gerenciamento de grupos e licenças. |
| ![Políticas de Acesso Condicional do Azure AD](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | Políticas de Acesso Condicional do Azure AD. |
|||

Aqui está um resumo visual da fase Identidade para identidade somente na nuvem, com os novos elementos destacados.

![Sua organização após a fase Identidade para identidade somente na nuvem](../media/deploy-foundation-infrastructure-non-enterprises/identity-config-cloud-only.png)
 
Os novos elementos de identidade somente na nuvem destacados incluem:
 
|||
|:------:|:-----|
| ![As contas de usuários e grupos do Azure AD](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-accounts-cloud-only.png) | As contas de usuários e grupos do Azure AD. |
| ![Configurações do Azure AD para autenticação, proteção de contas globais e simplificação do gerenciamento de grupos e licenças](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | Configurações do Azure AD para autenticação, proteção de contas globais e simplificação do gerenciamento de grupos e licenças. |
| ![Políticas de Acesso Condicional do Azure AD](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | Políticas de Acesso Condicional do Azure AD. |
|||

## <a name="phase-3-windows-10-enterprise"></a>Fase 3: Windows 10 Enterprise

Para garantir que seus dispositivos Windows 10 Enterprise estejam integrados à infraestrutura de identidade e segurança do Microsoft 365 para empresas, aqui estão suas opções:

- Híbrido (você tem um domínio local do AD DS)

  Para cada dispositivo empresarial do Windows 10 já existente no seu domínio AD DS, ingresse-o no locatário do Azure AD. Confira [Como configurar dispositivos associados híbridos do Active Directory do Azure](https://go.microsoft.com/fwlink/p/?linkid=872870) para obter instruções.

  Para cada novo dispositivo do Windows 10 Enterprise, associe-o ao seu domínio do AD DS e, em seguida, associe-o ao locatário do Azure AD.

  Inscreva cada dispositivo do Windows 10 Enterprise para o gerenciamento de dispositivos móveis. Confira [Inscrever um dispositivo do Windows 10 no Intune usando uma Política de Grupo](https://go.microsoft.com/fwlink/p/?linkid=872871) para obter instruções.

- Somente na nuvem (você não possui um domínio do AD DS no local)

  Associe cada dispositivo do Windows 10 Enterprise ao locatário do Azure AD da sua assinatura.

  Confira [Adicione seu dispositivo de trabalho à rede da sua organização](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network) para obter mais informações.


Depois de instalados e associados, cada dispositivo do Windows 10 Enterprise instala automaticamente as atualizações do serviço em nuvem do Windows Update for Business. Em uma organização não empresarial, normalmente não há necessidade de configurar uma infraestrutura para distribuir e instalar atualizações do Windows 10.

### <a name="your-configuration-so-far"></a>Sua configuração até agora

Aqui está um resumo visual da fase do Windows 10 Enterprise com os novos elementos destacados.

![Sua organização após a fase Windows 10 Enterprise](../media/deploy-foundation-infrastructure-non-enterprises/win10-config.png)
 
Os novos e destacados elementos do Windows 10 Enterprise incluem:

|||
|:------:|:-----|
| ![Windows 10 Enterprise instalado em dispositivos Windows](../media/deploy-foundation-infrastructure-non-enterprises/win10-device.png) | Windows 10 Enterprise instalado em dispositivos Windows, com um laptop local como exemplo. |
| ![Centro de Serviços de Licenciamento por Volume](../media/deploy-foundation-infrastructure-non-enterprises/win10-cloud.png) | O Centro de Serviços de Licenciamento por Volume, que fornece imagens para novas instalações do Windows 10 Enterprise, e o serviço Windows Update for Business, que fornece as atualizações mais recentes. |
|||

## <a name="phase-4-microsoft-365-apps-for-enterprise"></a>Fase 4 - Microsoft 365 Apps para empresas

O Microsoft 365 para empresas inclui o Microsoft 365 Apps, a versão de assinatura do Microsoft Office. Como o Office 2016 ou o Office 2019, o Microsoft 365 Apps é instalado diretamente nos seus dispositivos clientes. Entretanto, o Microsoft 365 Apps para empresas recebe atualizações que incluem novos recursos regularmente. Consulte [Sobre o Microsoft 365 Apps para Grandes Empresas](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps) para obter mais informações.

Na sua organização não corporativa, instale manualmente o Microsoft 365 Apps para empresas nos dispositivos, o que pode incluir dispositivos Windows, iOS e Android. Isso pode ser feito como parte da preparação de um novo dispositivo para uso ou pode ser feito pelo usuário como parte de seu processo de integração.

Em ambos os casos, o administrador ou o usuário entra no portal do Office 365 em https://portal.office.com. Na guia **Página inicial do Microsoft Office**, clique em **Instalar o Office** e percorra o processo de instalação.

As atualizações dos recursos do Microsoft 365 Apps para empresas são baixadas mensalmente por cada computador em que ele está instalado. Normalmente, não é necessário que uma organização não corporativa configure uma infraestrutura para distribuir o Microsoft 365 Apps para atualizações corporativas. 

### <a name="your-configuration-so-far"></a>Sua configuração até agora

Aqui está um resumo visual da fase do Microsoft 365 Apps para empresas com os novos elementos destacados.

![Sua organização depois da fase do Microsoft 365 Apps para empresas](../media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-config.png)
 
Aqui está um resumo visual da fase do Microsoft 365 Apps para empresas, com os novos elementos destacados:
 
|||
|:------:|:-----|
| ![Microsoft 365 Apps para empresas instalado em dispositivos](../media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-device.png) | Microsoft 365 Apps para empresas instalado em dispositivos, com um notebook local como exemplo. |
| ![A Rede de Entrega de Conteúdo do Office (CDN) para aplicativos do Microsoft 365 para empresas](../media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-cdn.png) | A Rede de Entrega de Conteúdo do Office (CDN) do Microsoft 365 Apps para empresas, cujos dispositivos acessam as atualizações do Microsoft 365 Apps para empresas. |
|||

## <a name="phase-5-mobile-device-management"></a>Fase 5: Gerenciamento de dispositivos móveis

O Microsoft 365 para empresas inclui o Microsoft Intune para gerenciamento de dispositivos móveis. Com o Intune, você pode gerenciar dispositivos iOS, Android, macOS e Windows para proteger o acesso aos recursos da sua organização, incluindo seus dados. O Intune usa as contas de usuários, grupos e computadores do Azure AD.

O Intune fornece dois tipos de gerenciamento de dispositivos móveis:

- O gerenciamento de dispositivos móveis (MDM) é quando os dispositivos são inscritos no Intune. Uma vez inscritos, eles se tornam dispositivos gerenciados e podem receber as políticas, regras e configurações usadas por sua organização. Esses tipos de dispositivos são normalmente de propriedade da sua organização e emitidos para seus funcionários.

- Os usuários com seus próprios dispositivos pessoais podem não querer inscrever seus dispositivos ou serem gerenciados pelo Intune com suas políticas e configurações. No entanto, você ainda precisa proteger os recursos e dados de sua organização. Para este cenário, você pode proteger seus aplicativos usando o gerenciamento de aplicativos móveis (MAM).  

As políticas do Intune podem impor a conformidade do dispositivo e a proteção do aplicativo. Aqui está a lista de políticas do Intune para criar.

| Políticas do Intune | Grupos aos quais se aplica |
|:------|:-----|
| Política de conformidade de dispositivos para o Windows | LINHA DE BASE, CONFIDENCIAL, ALTAMENTE REGULAMENTADO |
| Política de conformidade de dispositivos para iOS | CONFIDENCIAL, ALTAMENTE REGULAMENTADO |
| Conformidade de dispositivos para macOS | CONFIDENCIAL, ALTAMENTE REGULAMENTADO |
| Política de conformidade de dispositivos para Android e Android Enterprise | CONFIDENCIAL, ALTAMENTE REGULAMENTADO |
| Política de proteção de aplicativos para iOS | LINHA DE BASE, CONFIDENCIAL, ALTAMENTE REGULAMENTADO |
| Política de proteção de aplicativos para macOS | LINHA DE BASE, CONFIDENCIAL, ALTAMENTE REGULAMENTADO |
| Política de proteção de aplicativos para Android e Android Enterprise | LINHA DE BASE, CONFIDENCIAL, ALTAMENTE REGULAMENTADO |
|||
    
Confira [Políticas comuns de acesso a identidades e dispositivos](identity-access-policies.md) para obter instruções.

### <a name="your-configuration-so-far"></a>Sua configuração até agora

Aqui está um resumo visual da fase de Gerenciamento de Dispositivos Móveis com os novos elementos destacados.

![Sua organização depois da fase de Gerenciamento de Dispositivo Móvel](../media/deploy-foundation-infrastructure-non-enterprises/mdm-config.png)
 
Os novos e destacados elementos de gerenciamento de dispositivos móveis incluem:

|||
|:------:|:-----|
| ![Dispositivos registrados no Intune](../media/deploy-foundation-infrastructure-non-enterprises/mdm-device.png) | Dispositivos registrados no Intune, mostrando um laptop local executando o Windows 10 Enterprise como exemplo. |
| ![Políticas do Intune para conformidade de dispositivos e proteção de aplicativos](../media/deploy-foundation-infrastructure-non-enterprises/mdm-policies.png) | Políticas do Intune para conformidade de dispositivos e proteção de aplicativos. |
|||

## <a name="phase-6-information-protection"></a>Fase 6: Proteção de informações

O Microsoft 365 para empresas tem um host de recursos de proteção de informações que permitem tratar classificações de dados de maneira diferente, aplicando níveis diferentes de governança, segurança e proteção. 

Por exemplo, as correspondências normais entre a maioria dos funcionários e os documentos com os quais eles trabalham precisam de um certo nível de linha de base de proteção. Registros financeiros, dados do cliente e sua propriedade intelectual precisam de um nível mais alto de proteção.

O primeiro passo para uma estratégia de proteção da informação é determinar os níveis de proteção. Muitas organizações usam esses níveis, que já estão sendo usados para políticas de Acesso Condicional:

- Linha de base

  Os exemplos incluem comunicações comerciais normais (email) e arquivos para funcionários administrativos, de vendas e de suporte.

- Confidencial

  Os exemplos incluem informações financeiras e jurídicas e dados de pesquisa e desenvolvimento para novos produtos ou serviços.

- Altamente controlada

  Exemplos incluem informações de identificação pessoal de clientes e parceiros e planos estratégicos ou propriedade intelectual da sua organização.

Com base nesses níveis de segurança de dados, o próximo passo é identificar e implementar:

- Tipos de informações confidenciais personalizadas

  O Microsoft 365 fornece uma ampla seleção de tipos de informações confidenciais, como serviços de saúde e números de cartão de crédito. Se você não encontrar o que precisa na lista fornecida, poderá criar o seu próprio.

- Rótulos de retenção

  Para cumprir as políticas da organização e os regulamentos regionais, talvez seja necessário especificar por quanto tempo os tipos específicos de documentos ou documentos com conteúdo específico devem ser mantidos. Você pode implementar isto para emails e documentos usando rótulos de retenção. Os rótulos de retenção também podem ser usados ​​em conjunto com as políticas de prevenção contra perda de dados (DLP) que podem restringir o compartilhamento de arquivos ou email fora da sua organização.

- Rótulos de confidencialidade

  Você pode rotular emails ou documentos com um rótulo de confidencialidade nomeado para que os níveis adicionais de segurança possam ser aplicados. Exemplos são marcas d'água, criptografia e permissões, que especificam quem tem permissão para acessar o email ou documento e o que eles podem fazer.

Confira os [tipos de classificação do Microsoft 365](infoprotect-configure-classification.md#microsoft-365-classification-types) para obter mais informações.

Se você usar rótulos de sensibilidade com permissões, talvez você precise criar grupos de segurança adicionais para definir quem tem permissão para fazer o quê com e-mails e documentos com o rótulo de sensibilidade aplicado. 

Por exemplo, você precisa criar um rótulo de confidencialidade PESQUISA para proteger os emails e documentos da sua equipe de pesquisa. Você determina que:

- Os pesquisadores devem ter a capacidade de alterar documentos marcados com o rótulo de sensibilidade da pesquisa.
- Os funcionários que não são de pesquisa só precisam ter a capacidade de exibir documentos marcados com o rótulo de sensibilidade da PESQUISA. 

Isso significa que você precisa criar e gerenciar dois grupos adicionais do Microsoft 365:

- PESQUISA-TODOS
- PESQUISA-VISUALIZAR

Esses grupos e suas permissões se tornam parte da configuração do rótulo de confidencialidade PESQUISA.

Para rótulos de confidencialidade configurados com permissões baseadas em grupo, você deve gerenciar a associação desses grupos.

### <a name="your-configuration-so-far"></a>Sua configuração até agora

Aqui está um resumo visual da fase de Proteção de Informações com os novos elementos destacados.

![Sua organização depois da fase de Proteção de Informações](../media/deploy-foundation-infrastructure-non-enterprises/info-protect-config.png)
 
Os novos e destacados elementos de proteção de informações incluem:
 
|||
|:------:|:-----|
| ![Rótulos de sensibilidade para os três níveis de segurança](../media/deploy-foundation-infrastructure-non-enterprises/info-protect-labels.png) | Rótulos de sensibilidade dos três níveis de segurança que os usuários podem aplicar a documentos e emails. |
|||

Rótulos de retenção e tipos de informações personalizadas não são exibidos.

## <a name="onboarding"></a>Integração

Com a infraestrutura do Microsoft 365 para empresas instalada, você pode integrar seus funcionários facilmente.

### <a name="a-new-windows-10-enterprise-device"></a>Um novo dispositivo do Windows 10 Enterprise

Antes de fornecer ao funcionário um novo dispositivo do Windows 10 Enterprise:

- Para identidade híbrida

  Associe o dispositivo ao seu AD DS, associe o dispositivo ao seu locatário do Azure AD e, em seguida, inscreva o dispositivo no Intune.

- Para identidade somente na nuvem

  Associe o dispositivo ao seu locatário do Azure AD.

### <a name="existing-employee-with-an-ad-ds-user-account"></a>Funcionário existente com uma conta de usuário do AD DS

Como parte da integração inicial da sua organização ao usar a identidade híbrida, adicione a conta de usuário do AD DS a estes grupos do Azure AD:

- LICENCIADO
- Os grupos de segurança apropriados do AD DS ou do Azure AD que são membros dos grupos LINHA DE BASE, CONFIDENCIAL e ALTAMENTE REGULADO do Azure AD.
- Grupos de rótulos de confidencialidade (conforme necessário)

O funcionário existente já deve ser adicionado aos grupos de grupo de trabalho e grupos departamentais e regionais do AD DS.

Você pode adicionar uma conta de usuário a vários grupos do Azure AD no centro de administração do Microsoft 365. Nas propriedades da conta do usuário, clique em **gerenciar grupos > Adicionar associações**.

Caso pretenda usar o PowerShell, confira [esta pasta de trabalho](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/deploy-foundation-infrastructure-non-enterprises/Group-License-Mgmt-PowerShell.xlsx)do Excel para baixá-la, que gera os comandos do PowerShell com base em uma conta de usuário especificada e os nomes dos grupos selecionados.

### <a name="new-employee-with-a-cloud-only-user-account"></a>Novo funcionário com conta de usuário somente na nuvem

Como parte da integração inicial da sua organização ao usar a identidade somente na nuvem, adicione a nova conta de usuário a estes grupos:

- LICENCIADO
- Os grupos de segurança apropriados do Azure AD que são membros dos grupos LINHA DE BASE, CONFIDENCIAL e ALTAMENTE REGULAMENTADO do Azure AD
- Grupo de trabalho, departamental, e grupos regionais
- Grupos de rótulos de confidencialidade (conforme necessário)

### <a name="initial-sign-in-to-microsoft-365"></a>Logon inicial no Microsoft 365

Na primeira vez que os funcionários entram no Microsoft 365, instrua-os a:

1. Fazerem logon em seus dispositivos com suas credenciais de conta de usuário.
2. Usando um navegador, entre no portal do Office 365, em https://portal.office.com.
3. Na guia **Página inicial do Office 365**, clique em **Instalar o Office** para instalar o Microsoft 365 Apps nos seus dispositivos.

## <a name="end-results"></a>Resultados finais

Aqui estão os resultados da configuração da infraestrutura de base do Microsoft 365 para empresas para sua organização não empresarial.

### <a name="infrastructure-results"></a>Resultados de infraestrutura

Após o desenvolvimento e a configuração da infraestrutura do Microsoft 365 para empresas, você deve ter:

- Uma conexão de Internet local para cada um de seus escritórios com largura de banda suficiente fornecida por um ISP (provedor de serviços de Internet) que usa um servidor DNS regionalmente local.
- Para identidade híbrida, o Azure AD Connect é executado em um servidor que sincroniza seu domínio do AD DS local com o seu locatário do Azure AD.
- Esses grupos:
  - LICENCIADO
  - ACESSO-COND-EXCLUIR
  - Os grupos de segurança apropriados do AD DS ou do Azure AD que também são membros dos grupos LINHA DE BASE, CONFIDENCIAL e ALTAMENTE REGULADO do Azure AD 
  - Grupo de trabalho, departamental, e grupos regionais
  - Rótulo de sensibilidade dos grupos do Microsoft 365 (conforme necessário)
- Políticas de Acesso Condicional de logon do Azure AD que usam os grupos LINHA DE BASE, CONFIDENCIAL, ALTAMENTE REGULADO, COND-ACCESS-EXCLUDE do Azure AD.
- Políticas de conformidade de aplicativos e dispositivos do Intune.
- Tipos de informações confidenciais personalizadas (conforme necessário).
- Rótulos de retenção (conforme necessário).
- Rótulos de confidencialidade (conforme necessário).

Este é um resumo visual da infraestrutura se sua organização usa identidade híbrida, a qual inclui seu domínio do AD DS, um servidor do Azure AD Connect e grupos e usuários do AD DS sincronizados.

![Resumo da infraestrutura se a sua organização usa identidade híbrida](../media/deploy-foundation-infrastructure-non-enterprises/final-hybrid-config.png)
 
Aqui está um resumo visual da infraestrutura se a sua organização usa a identidade somente na nuvem.
 
![Resumo visual da infraestrutura se a sua organização usa a identidade somente na nuvem.](../media/deploy-foundation-infrastructure-non-enterprises/final-cloud-only-config.png)

### <a name="employee-results"></a>Resultados dos funcionários

Após a integração, cada funcionário deve ter:

- Um caminho de rede local de alto desempenho conectando os dispositivos deles aos serviços de nuvem da Microsoft 365 na região deles.
- Uma conta de usuário com estas associações de grupo:
   - LICENCIADO
   - Os grupos de segurança apropriados do AD DS ou do Azure AD, que também são membros dos grupos LINHA DE BASE, CONFIDENCIAL e ALTAMENTE REGULADO do Azure AD para políticas de Acesso Condicional 
   - Grupo de trabalho e grupos departamentais e regionais apropriados
   - Rótulo de sensibilidade dos grupos do Microsoft 365 (conforme necessário)
- Um dispositivo do Windows 10 Enterprise que:
   - É associado ao locatário do Azure AD (somente nuvem) ou ao locatário do Azure AD e ao seu domínio do AD DS (híbrido).
   - Atualiza automaticamente com as melhorias e aprimoramentos de segurança mais recentes do produto Windows 10 Enterprise.
   - O Microsoft 365 Apps para empresas está instalado, o qual se atualiza automaticamente com os aprimoramentos mais recentes do produto Office e aprimoramentos de segurança.
   - Está inscrito no Intune e sujeito às políticas de conformidade de dispositivos e políticas de proteção de aplicativos do Intune.

## <a name="next-step"></a>Próxima etapa

Implante suas [cargas de trabalho e cenários](deploy-workloads.md) e aproveite os recursos e a configuração de base do Microsoft 365 para empresas.
