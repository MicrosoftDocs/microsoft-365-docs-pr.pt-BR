---
title: Fase 5 - gerenciamento de dispositivos móveis
description: Microsoft 365 Enterprise inclui o gerenciamento de dispositivos móveis usando o Microsoft Intune. Examine os requisitos e pré-requisitos, configurar Intune usando seu recurso do Active Directory do Azure, registrar iOS, macOS, Android e Windows dispositivos, implantar apps, crie um perfil de configurar, usar uma política de conformidade e habilitar o acesso condicional para dispositivos móveis gerenciamento de dispositivo com Microsoft 365 Enterprise.
keywords: 365 da Microsoft, Microsoft 365 Enterprise, Microsoft 365 documentação, gerenciamento de dispositivos móveis, Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/18/2018
ms.topic: conceptual
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
ms.custom: microsoft-intune
ms.openlocfilehash: 8d048ec6628cb8f7cb9c5e0d4c7960481bc69de1
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865336"
---
# <a name="phase-5-mobile-device-management-for-microsoft-365-enterprise"></a>Fase 5: Gerenciamento de dispositivos móveis para Microsoft 365 Enterprise

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon.png)

*Esse recurso é aplicado às versões E3 e E5 do Microsoft 365 Enterprise*

Microsoft 365 Enterprise inclui recursos para ajudar a gerenciar seus aplicativos, dentro da sua organização e dispositivos. Usando o Microsoft Intune, você pode gerenciar o iOS, Android, macOS e dispositivos do Windows para proteger o acesso aos recursos da sua organização, incluindo seus dados. Intune se integra com o Azure Active Directory (AD Azure) e habilita os seguintes cenários de negócios para Microsoft 365:

- Armazenar e compartilhar arquivos dentro e fora de sua organização para trabalhar de forma transparente entre os limites organizacionais
- Trabalhar com segurança de qualquer lugar, a qualquer momento e em qualquer dispositivo para alcançar mais, mantendo um estilo de trabalho flexível
- Fornecer tranquilidade com controles e visibilidade para conformidade verificada no setor com padrões globais em conformidade
- Proteger informações e reduzir o risco de perda de dados
- Detectar e proteger contra ameaças externas
- Monitorar, relatar e analisar atividade para reagir imediatamente para fornecer segurança da organização
- Proteger os usuários e suas contas

Para saber mais, confira [Transformação digital usando o Microsoft 365](http://transform.microsoft.com). 

Nesta fase, você registrar seus dispositivos em Intune e cria e aplicar políticas para ajudar a manter seus dados seguros. Toda a biblioteca de documentação Intune é [disponíveis online](https://docs.microsoft.com/intune). Também é uma boa prática para analisar o [planejamento da implantação Intune, design e implementação de guia](https://docs.microsoft.com/intune/planning-guide) antes de começar.

## <a name="step-1-plan-for-your-scenario"></a>Etapa 1: Planejar seu cenário

Um dos principais motivos para gerenciar os dispositivos móveis é seguro e proteger recursos da sua organização. [Formas comuns de usar o Microsoft Intune](https://docs.microsoft.com/intune/common-scenarios) lista alguns exemplos reais, incluindo a proteção de dados e email do Office 365.

Intune oferece opções para gerenciar o acesso à sua organização usando [Mobile Device Management (MDM) ou o gerenciamento de aplicativo de celular (MAM)](https://docs.microsoft.com/intune/byod-technology-decisions). MDM é quando seus dispositivos no Intune usuários "Registrar". Depois de registrado, eles são gerenciados de dispositivos e podem receber qualquer diretivas, regras e configurações usadas por sua organização. Por exemplo, você pode instalar o informações específicas aplicativos, criar uma política de senha, instale uma conexão VPN e muito mais.

Usuários com seus próprios dispositivos pessoais não talvez queira registrar seus dispositivos ou ser gerenciados por Intune e suas políticas. Mas, você ainda precisará proteger recursos e dados de sua organização. Neste cenário, você pode proteger seus aplicativos usando MAM. Por exemplo, você pode usar uma política MAM que exige que um usuário inserir um PIN ao acessar o SharePoint no dispositivo.

Você determinará como você irá gerenciar dispositivos pessoais ou pertence à organização. Convém tratar os dispositivos de forma diferente, dependendo de seu uso. Por exemplo, você talvez prefira diferentes planos para usuários no departamento de recursos humanos (RH) ou os usuários de vendas. [Identifique cenários de caso de uso de gerenciamento de dispositivo móvel](https://docs.microsoft.com/intune/planning-guide-scenarios) ajudam você a começar e inclui algumas orientações sobre esses cenários diferentes.

## <a name="step-2-get-your-prerequisites"></a>Etapa 2: Obter seus pré-requisitos

Em seguida, obtenha seus pré-requisitos conforme suas necessidades e seus cenários criados na etapa anterior. [Implementar o plano de](https://docs.microsoft.com/intune/planning-guide-onboarding) lista todos os requisitos. Aqui estão os itens significativos, que você precisa para Intune com Microsoft 365:

- **Assinatura Intune**: incluída 365 da Microsoft e oferece acesso a Microsoft Intune no [portal do Azure](https://portal.azure.com)
- **Assinatura do Office 365**: incluída 365 da Microsoft e é usado para aplicativos do Office, incluindo email
- **Premium do Azure Active Directory (AD)**: incluída 365 da Microsoft e é usado para criar grupos de segurança ou usuários. Esses grupos recebem Intune políticas que você criar, como forçar um comprimento de senha para desbloquear um dispositivo. Os grupos que você criar no [fase 2: identidade](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure) pode ser usado.

Pode haver alguns requisitos adicionais, dependendo das necessidades da sua organização. Por exemplo, se você irá gerenciar dispositivos iOS, será necessário um certificado de Push do Apple MDM. Se você estiver usando o Exchange local, e em seguida, você precisará o conector do Exchange local. Esses requisitos adicionais são descritos quando você chegar a essas etapas.

## <a name="step-3-set-up-intune"></a>Etapa 3: Configurar Intune

Intune utiliza muitos recursos no Azure AD, incluindo seu domínio, seus usuários e os grupos. Você também pode criar novos usuários e grupos de novos para atender às suas necessidades de empresa. Por exemplo, você pode criar um grupo chamado **dispositivos iOS**ou **RH todos os usuários**.  Beneficie-se de [Grupos dinâmicos](https://docs.microsoft.com/intune/groups-add) que permite que você crie o usuário ou grupos de dispositivos com base em torno de regras simples ou avançadas.

Esta etapa se concentra em Configurar Intune e preparação para você gerenciar seus dispositivos.

1. **[Confirmar que seus dispositivos são suportados](https://docs.microsoft.com/intune/supported-devices-browsers)**. Confirmar sua iOS, macOS, dispositivos Android, Galaxy e Windows são suportados pelo Intune. Se sua organização incluir dispositivos que não são suportados, as diretivas não são aplicadas para esses dispositivos.

2. **[Personalizar seu nome de domínio](https://docs.microsoft.com/intune/custom-domain-name-configure)**. Por padrão, um domínio chamado algo como **your-domain.onmicrosoft.com** é criado automaticamente no Windows Azure AD. **onmicrosoft.com** pode ser personalizado para sua organização. Quando você personaliza, ele também proporciona aos usuários um domínio familiar ao conectar-se a Intune e o uso de recursos.

3. **[Entrar no Intune](https://docs.microsoft.com/intune/account-sign-up)**. Quando você entrar, você pode ser solicitado para inserir informações sobre sua organização. Intune está incluído no Microsoft 365 e pode ser aberto diretamente do [portal de administração do Office 365](https://portal.office.com/). Você também pode abrir Intune diretamente do [portal do Azure](https://portal.azure.com).

4. **[Escolha sua configuração de gerenciamento de dispositivo móvel](https://docs.microsoft.com/intune/mdm-authority-set)**. Na primeira vez que você use Intune, você deve habilitar o gerenciamento de dispositivos. Intune pode ser usado como um serviço de nuvem apenas, um híbrido com Intune e System Center Configuration Manager ou usando o gerenciamento de dispositivos móveis para o Office 365. Você pode escolher qual instalação funciona melhor para sua organização.

5. **[Adicionar usuários](https://docs.microsoft.com/intune/users-add)** e **[Adicionar grupos](https://docs.microsoft.com/intune/groups-add)**. 

   Manualmente, você pode adicionar usuários ou se conectar ao Windows Azure AD para usuários de sincronização com Intune. Você também pode fornecer as funções de administrador a usuários específicos. Os usuários são necessários, a menos que seus dispositivos estejam "userless" dispositivos, como os dispositivos de quiosque.

   Grupos do Azure AD são usados para simplificar a como gerenciar usuários no Intune e dispositivos. Usar grupos, você poderá fazer muitas tarefas diferentes. Por exemplo, sua organização deseja exigir um aplicativo específico em dispositivos Android. Você pode criar um grupo de dispositivos com Android e implantar uma diretiva com esse aplicativo para o grupo.

    Intune, você pode adicionar usuários ou grupos que você criar no [fase 2: identidade](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)

6. **[Atribuir licenças](https://docs.microsoft.com/intune/licenses-assign)**. Para usuários ou dispositivos que se inscrevam no Intune, eles precisam de uma licença no dispositivo. Cada usuário ou dispositivo userless requer uma licença de Intune para acessar o serviço Intune. Essas licenças estão incluídas no Microsoft 365 e devem ser atribuídas no Intune.

## <a name="step-4-enroll-devices"></a>Etapa 4: Registrar dispositivos

Para gerenciar os dispositivos, os dispositivos devem ser registrados em Intune. Como administrador, você vai configurar restrições de inscrição e políticas para seus usuários e dispositivos. Cada plataforma de dispositivo (iOS, Android, macOS e Windows) tem uma variedade de opções. Você pode fazer com que seus usuários registrar-se. Ou então, você pode automatizar o registro para que os usuários simplesmente entrar no dispositivo.

Inscrição é uma etapa importante ao usar Intune. [Dispositivos de registrar](https://docs.microsoft.com/intune/device-enrollment) lista as etapas para os dispositivos diferentes.

|||
|:-------|:-----|
|![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Test Lab Guide: iOS e o registro do dispositivo Android](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md) |
|||


## <a name="step-5-add-and-deploy-apps"></a>Etapa 5: Adicionar e implante aplicativos

Aplicativos em dispositivos móveis geralmente são que os usuários de maneira mais rápidos obtém acesso aos seus recursos corporativos. 

Existem desafios ao usar aplicativos, que hajam em diferentes dispositivos, incluindo dispositivos de pessoais e corporativos. E, para proteger os recursos da sua organização e seus dados enquanto também torna-se de que os usuários produtivos.

Intune pode gerenciar aplicativos, incluindo como adicionar aplicativos, atribuí-las aos usuários ou grupos diferentes e revise outros detalhes importantes. Por exemplo, você pode ver quais aplicativos falharem ao instalar, verifique a versão de um aplicativo e muito mais.

Quando os usuários obtenham um dispositivo móvel, uma das primeiras tarefas é acessem documentos e emails organizacional. Usando Intune, você pode [criar e implantar as configurações de email](https://docs.microsoft.com/intune/email-settings-configure) usando aplicativos de email que são pré-instalados nos dispositivos. 

[Adicionar aplicativos](https://docs.microsoft.com/intune/app-management) lista as etapas para adicionar, implantar, monitorar, configurar e proteger os aplicativos em dispositivos dentro de sua org.

|||
|:-------|:-----|
|![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia do laboratório de teste: Políticas de gerenciamento de aplicativo móvel](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md) |
|||

## <a name="step-6-turn-on-compliance-and-conditional-access"></a>Etapa 6: Ativar acesso condicional e conformidade

Nas etapas anteriores, você deve configurar seu ambiente e habilitado Intune. Agora, você está pronto para criar algumas políticas usando a conformidade e acesso condicional.

Conformidade e acesso condicional são importantes para gerenciamento de dispositivos. **[Políticas de conformidade](https://docs.microsoft.com/intune/device-compliance-get-started)** são criados para ajudar a proteger os recursos da sua organização. Quando você cria uma política de conformidade, você estiver definindo o padrão ou a "linha de base" de um dispositivo deve ter. Por exemplo, você pode escolher um nível de ameaça aceitável (ou inaceitável), bloquear dispositivos jailbroken, exigem um comprimento de senha e muito mais. Se esses dispositivos não atenderem às suas regras, que significa que eles não são compatíveis com, você pode bloquear o acesso aos seus recursos.

Isso "bloqueando" introduz **[acesso condicional](https://docs.microsoft.com/intune/conditional-access)**. Se um dispositivo é considerado não é compatível com, você pode bloquear o acesso a email, SharePoint e muito mais.

Intune no [portal do Azure](https://portal.azure.com) lhe permite criar essas políticas e aplicá-las para seus usuários e dispositivos. Como prática recomendada, comece pequeno e usar uma abordagem em estágios. Por exemplo, crie uma política de iOS que bloqueia jailbroken dispositivos. Aplica a política de (chamado "assign" no Intune) a um grupo piloto ou de teste. Após o teste inicial, adicione mais usuários ao grupo piloto. Usando uma abordagem em estágios, você pode obter feedback de uma ampla gama de tipos de usuário.

[Introdução ao políticas de conformidade do dispositivo](https://docs.microsoft.com/intune/device-compliance-get-started) e [o que é o acesso condicional?](https://docs.microsoft.com/intune/conditional-access) pode ajudá-lo a começar.

## <a name="step-7-apply-features-and-settings"></a>Etapa 7: Aplicar configurações e recursos

Esses recursos e configurações normalmente são consideradas como a parte "interessante" do Intune e são muito poderosas. Após ter aplicado com êxito a algumas políticas de conformidade usando o access condicional, você estará pronto para criar **perfis de dispositivo**.

Intune no [portal do Azure](https://portal.azure.com) lhe permite criar perfis diferentes com base em sua plataforma de dispositivo - iOS, macOS, Android e Windows. Por exemplo, você pode:

- Use a proteção de ponto de extremidade em dispositivos Windows 10 para habilitar opções de BitLocker diferentes, incluindo a criptografia.
- Use o recurso de aplicativos restritos em dispositivos iOS para criar uma lista de aplicativos aprovados que pode ser instalado. Ou, crie uma lista de aplicativos proibidas.
- Use as configurações de quiosque para escolher quais aplicativos podem ser usados em dispositivos com Android em execução no modo de quiosque.
- Aplica uma conexão Wi-Fi e suas configurações, incluindo o tipo de segurança, em dispositivos que executam macOS.
- E mais

[o que são perfis de dispositivo Microsoft Intune?](https://docs.microsoft.com/intune/device-profiles) é um ótimo lugar para ler sobre perfis, consulte como criar um perfil e muito mais.

Lembre-se, comece pequeno e usar uma abordagem em estágios. Atribua o perfil a um grupo piloto ou de teste. Em seguida, atribua o perfil a mais grupos piloto.

## <a name="step-8-get-to-know-the-other-features"></a>Etapa 8: Obter saber nos outros recursos

Intune é um serviço poderoso e inclui muitos recursos. Aqui estão algumas outras tarefas que você pode fazer usando Intune:

- Gerenciar o software e atualizações de [dispositivos](https://docs.microsoft.com/intune/windows-update-for-business-configure)do Windows & [PCs](https://docs.microsoft.com/intune/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)e dispositivos [iOS](https://docs.microsoft.com/intune/software-updates-ios)
- Ativar a [Proteção de ameaça avançadas (ATP) do Windows Defender](https://docs.microsoft.com/intune/advanced-threat-protection) em seus dispositivos Windows 10 e use a conformidade e acesso condicional para proteger o acesso aos recursos corporativos, such as SharePoint or Exchange Online
- Usar [procura](https://docs.microsoft.com/intune/lookout-mobile-threat-defense-connector), [Symantec](https://docs.microsoft.com/intune/skycure-mobile-threat-defense-connector)e outros parceiros de ameaça defesa móvel
- Adicionar uma [autoridade de certificação (CA) do parceiro](https://docs.microsoft.com/intune/certificate-authority-add-scep-overview) para emitir e renovação de certificados
- [Fornecer orientação para seus usuários finais](https://docs.microsoft.com/intune/end-user-educate) sobre o aplicativo de Portal da empresa, introdução de aplicativos e muito mais
- Monitorar [aplicativos](https://docs.microsoft.com/intune/apps-monitor), monitorar a [conformidade de dispositivo](https://docs.microsoft.com/intune/compliance-policy-monitor), monitor [perfis de configuração](https://docs.microsoft.com/intune/compliance-policy-monitor)e telemetria mais usando os logs de auditoria. Você também pode se conectar ao [Intune Data Warehouse](https://docs.microsoft.com/intune/reports-nav-create-intune-reports) e usar Power BI para as necessidades de relatório ainda mais.


## <a name="identity-and-device-access-recommendations"></a>Recomendações de acesso de dispositivo e identidade

A Microsoft fornece um conjunto de recomendações para [acesso de dispositivo e identity](microsoft-365-policies-configurations.md) garantir uma força de trabalho segura e produtiva. Acesso de dispositivo, use as recomendações e configurações nos artigos a seguir, juntamente com as etapas nesta fase:

- [Pré-requisitos](identity-access-prerequisites.md)
- [Identidade comum e políticas de acesso ao dispositivo](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Como a Microsoft desenvolve o Microsoft 365 Enterprise

Saiba como os especialistas de TI da Microsoft planejados para e implantado gerenciamento EMS e dispositivo com estes recursos:

- [Gerenciar a produtividade móvel moderna com o Enterprise Mobility + Security](https://www.microsoft.com/itshowcase/Article/Content/972/Managing-modern-mobile-productivity-with-Enterprise-Mobility--Security)
- [Conectar-se para trabalhar no dispositivo Windows 10 com o Microsoft Intune](https://www.microsoft.com/itshowcase/Article/Content/783/Connecting-to-work-on-your-Windows-10-device-with-Microsoft-Intune)
- [Habilitar a produtividade móvel para dispositivos iOS, OS X e Android da Microsoft](https://www.microsoft.com/itshowcase/Article/Content/773/Enabling-mobile-productivity-for-iOS-OS-X-and-Android-devices-at-Microsoft)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Como a Contoso desenvolveu o Microsoft 365 Enterprise

Consulte como a Contoso Corporation, uma empresa multinacional fictícia, mas representativa, [implantado sua infraestrutura de gerenciamento de dispositivo móvel](contoso-mdm.md) com o Microsoft 365 serviços em nuvem.

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Próxima etapa

[Critérios de saída de infraestrutura de gerenciamento de dispositivo móvel](mobility-infrastructure-exit-criteria.md)

