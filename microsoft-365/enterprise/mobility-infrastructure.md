---
title: Fase 5-gerenciamento de dispositivos móveis
description: O Microsoft 365 Enterprise inclui gerenciamento de dispositivos móveis usando o Microsoft Intune. Revise os requisitos e pré-requisitos, configure o Intune usando seu recurso do Azure Active Directory, registre os dispositivos iOS, macOS, Android e Windows, implante aplicativos, crie um perfil de configuração, use uma política de conformidade e habilite o acesso condicional para dispositivos móveis gerenciamento de dispositivos com o Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, documentação do Microsoft 365, gerenciamento de dispositivos móveis, Intune
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 72ddad03486bf2c7dcba682453fa3bcfbdd1162b
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031146"
---
# <a name="phase-5-mobile-device-management-for-microsoft-365-enterprise"></a>Fase 5: gerenciamento de dispositivos móveis para o Microsoft 365 Enterprise

![Fase 5: gerenciamento de dispositivo móvel](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon.png)

*Este recurso se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

O Microsoft 365 Enterprise inclui recursos para ajudar a gerenciar dispositivos e seus aplicativos em sua organização. Usando o Microsoft Intune, você pode gerenciar os dispositivos iOS, Android, macOS e Windows para proteger o acesso aos recursos da sua organização, incluindo seus dados. 

Nesta fase, você registra seus dispositivos no Intune e cria e aplica políticas para ajudar a manter seus dados seguros e protegidos. A biblioteca inteira da documentação do Intune está [disponível online](https://docs.microsoft.com/intune). Também recomendamos que você analise o [Guia de planejamento, design e implementação da implantação do Intune](https://docs.microsoft.com/intune/planning-guide) antes de começar.

## <a name="step-1-plan-for-your-scenario"></a>Etapa 1: planejar seu cenário

Uma das principais razões para gerenciar dispositivos móveis é proteger e proteger os recursos da sua organização. [Maneiras comuns de usar o Microsoft Intune](https://docs.microsoft.com/intune/common-scenarios) lista alguns exemplos do mundo real, incluindo a proteção de email e dados do Office 365.

O Intune oferece opções para gerenciar o acesso à sua organização usando o gerenciamento de dispositivo móvel (MDM) ou o gerenciamento de aplicativo móvel (MAM). O MDM é quando os usuários "registram" seus dispositivos no Intune. Após o registro, eles são dispositivos gerenciados e podem receber quaisquer políticas, regras e configurações usadas por sua organização. Por exemplo, você pode instalar aplicativos específicos, criar uma diretiva de senha, instalar uma conexão VPN e muito mais.

Os usuários com seus próprios dispositivos pessoais podem não querer registrar seus dispositivos ou ser gerenciados pelo Intune e suas políticas. Mas você ainda precisa proteger os recursos e os dados da sua organização. Neste cenário, você pode proteger seus aplicativos usando MAM. Por exemplo, você pode usar uma política MAM que exige que um usuário insira um PIN ao acessar o SharePoint no dispositivo.

Você também determinará como vai gerenciar dispositivos pessoais ou pertencentes à organização. Você pode querer tratar os dispositivos de forma diferente, dependendo do uso. Por exemplo, você pode querer diferentes planos para usuários em recursos humanos (RH) ou usuários em vendas. [Identificar cenários de uso do gerenciamento de dispositivos móveis](https://docs.microsoft.com/intune/planning-guide-scenarios) pode começar e incluir algumas orientações sobre esses diferentes cenários.

## <a name="step-2-get-your-prerequisites"></a>Etapa 2: obter seus pré-requisitos

Em seguida, obtenha seus pré-requisitos com base em seus requisitos e seus cenários criados na etapa anterior. [Implementar seu plano](https://docs.microsoft.com/intune/planning-guide-onboarding) lista todos os requisitos. Estes são os itens significativos de que você precisa para o Intune com o Microsoft 365:

- **Assinatura do Intune**: incluída no Microsoft 365 e fornece acesso ao Microsoft Intune no [portal do Azure](https://portal.azure.com)
- **Assinatura do office 365**: incluída no Microsoft 365 e é usada para aplicativos do Office, incluindo email
- **Azure Active Directory (Azure AD) Premium**: incluído no Microsoft 365 e é usado para criar grupos de usuários ou de segurança. Esses grupos recebem as políticas do Intune que você cria, como forçar um comprimento de senha para desbloquear um dispositivo. Os grupos criados na [fase 2: identidade](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure) podem ser usados.

Podem existir alguns requisitos adicionais, dependendo das necessidades da sua organização. Por exemplo, se você estiver gerenciando dispositivos iOS, precisará de um certificado de push MDM da Apple. Se você estiver usando o Exchange local, precisará do Exchange Connector local. Esses requisitos adicionais são descritos quando você obtém essas etapas.

## <a name="step-3-set-up-intune"></a>Etapa 3: configurar o Intune

O Intune usa vários recursos no Azure AD, incluindo seu domínio, seus usuários e seus grupos. Você também pode criar novos usuários e novos grupos para atender às necessidades da sua empresa. Por exemplo, você pode criar um grupo chamado **dispositivos IOS**ou **todos os usuários de RH**.  Aproveite os [grupos dinâmicos](https://docs.microsoft.com/intune/groups-add) que permitem criar grupos de usuários ou de dispositivos com base em regras simples ou avançadas.

Esta etapa enfoca a configuração do Intune e sua preparação para você gerenciar seus dispositivos.

1. **[Confirme se há suporte para seus dispositivos](https://docs.microsoft.com/intune/supported-devices-browsers)**. Confirme se os dispositivos iOS, macOS, Android, Galaxy e Windows têm suporte no Intune. Se sua organização incluir dispositivos que não são suportados, as diretivas não serão aplicadas a esses dispositivos.

2. **[Personalize seu nome de domínio](https://docs.microsoft.com/intune/custom-domain-name-configure)**. Por padrão, um domínio chamado algo como **your-domain.onmicrosoft.com** é criado automaticamente no Azure AD. o **onmicrosoft.com** pode ser personalizado para sua organização. Ao personalizar o, ele também fornece aos usuários um domínio familiar quando se conecta ao Intune e usando recursos.

3. **[Entre no Intune](https://docs.microsoft.com/intune/account-sign-up)**. Ao entrar, você pode ser solicitado a inserir informações sobre sua organização. O Intune está incluído no Microsoft 365 e pode ser aberto diretamente a partir do [centro de administração do microsoft 365](https://admin.microsoft.com). Você também pode abrir o Intune diretamente do [portal do Azure](https://portal.azure.com).

4. **[Escolha sua configuração de gerenciamento de dispositivo móvel](https://docs.microsoft.com/intune/mdm-authority-set)**. Na primeira vez que usar o Intune, você deve habilitar o gerenciamento de dispositivos. O Intune pode ser usado como um serviço somente de nuvem, um híbrido com o Intune e o System Center Configuration Manager ou usando o gerenciamento de dispositivo móvel para o Office 365. Você pode escolher qual configuração funciona melhor para sua organização.

5. **[Adicione usuários](https://docs.microsoft.com/intune/users-add)** e **[adicione grupos](https://docs.microsoft.com/intune/groups-add)**. 

   Você pode adicionar usuários manualmente ou usar a identidade híbrida e o Azure AD Connect para sincronizar suas contas de usuário local com o Intune. Você também pode fornecer funções de administrador a usuários específicos. Os usuários são necessários, a menos que seus dispositivos sejam dispositivos "de não-usuário", como dispositivos quiosque.

   Os grupos do Azure AD são usados para simplificar o modo como você gerencia dispositivos e usuários no Intune. Usando grupos, você pode fazer muitas tarefas diferentes. Por exemplo, sua organização deseja exigir um aplicativo específico em dispositivos Android. Você pode criar um grupo de dispositivos Android e implantar uma política com este aplicativo no grupo.

    No Intune, você pode adicionar usuários ou grupos criados na [fase 2: identidade](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)

6. **[Atribuir licenças](https://docs.microsoft.com/intune/licenses-assign)**. Para que os usuários ou dispositivos se inscrevam no Intune, eles precisam de uma licença do Microsoft 365 com o serviço do Intune habilitado para acessar o serviço do Intune. Você atribui licenças do Microsoft 365, que têm o serviço do Microsoft Intune habilitado por padrão, no centro de administração do Microsoft 365 ou no PowerShell.

## <a name="step-4-enroll-devices"></a>Etapa 4: registrar dispositivos

Para gerenciar dispositivos, os dispositivos devem ser registrados no Intune. Como administrador, você configurará restrições de registro e políticas para seus usuários e dispositivos. Cada plataforma de dispositivo (iOS, Android, macOS e Windows) tem uma variedade de opções. Os usuários podem se inscrever. Ou, você pode automatizar o registro para que os usuários simplesmente entrem no dispositivo.

O registro é uma etapa principal ao usar o Intune. [Inscrever dispositivos](https://docs.microsoft.com/intune/device-enrollment) lista as etapas para os diferentes dispositivos.

|||
|:-------|:-----|
|![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia do laboratório de teste: registro de dispositivo Android e iOS](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md) |
|||


## <a name="step-5-add-and-deploy-apps"></a>Etapa 5: Adicionar e implantar aplicativos

Os aplicativos em dispositivos móveis costumam ser a maneira mais rápida de acessar seus recursos corporativos. 

Há desafios ao usar aplicativos, pois há dispositivos diferentes, incluindo dispositivos pessoais e dispositivos corporativos. Além disso, você deseja proteger os recursos e os dados da sua organização ao mesmo tempo que garante que os usuários sejam produtivos.

O Intune pode gerenciar aplicativos, incluindo adicionar aplicativos, atribuí-los a usuários ou grupos diferentes e revisar outros detalhes importantes. Por exemplo, você pode ver quais aplicativos falham ao instalar, verificar a versão de um aplicativo e muito mais.

Quando os usuários recebem um dispositivo móvel, uma das primeiras tarefas é acessar os documentos e emails organizacionais. Usando o Intune, você pode [criar e implantar configurações de email](https://docs.microsoft.com/intune/email-settings-configure) usando aplicativos de email pré-instalados nos dispositivos. 

O artigo [adicionar aplicativos](https://docs.microsoft.com/intune/apps/apps-add) lista as etapas para adicionar, implantar, monitorar, configurar e proteger aplicativos em dispositivos de sua organização.

|||
|:-------|:-----|
|![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia do laboratório de teste: políticas de conformidade do dispositivo](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md) |
|||

## <a name="step-6-turn-on-compliance-and-conditional-access"></a>Etapa 6: ativar a conformidade e o acesso condicional

Nas etapas anteriores, configure seu ambiente e habilitou o Intune. Agora, você está pronto para criar algumas políticas usando conformidade e acesso condicional.

A conformidade e o acesso condicional são importantes para o gerenciamento de dispositivos. [As políticas de conformidade](https://docs.microsoft.com/intune/device-compliance-get-started) são criadas para ajudar a proteger os recursos da sua organização. Ao criar uma política de conformidade, você está definindo o padrão ou a "linha de base" do que um dispositivo deve ter. Por exemplo, você pode escolher um nível de ameaça aceitável (ou inaceitável), bloquear dispositivos desbloqueados, exigir um comprimento de senha e muito mais. Se esses dispositivos não atenderem às suas regras, o que significa que não estão em conformidade, você poderá bloquear o acesso aos recursos.

Esse "bloqueio" apresenta [acesso condicional](https://docs.microsoft.com/intune/conditional-access). Se um dispositivo for considerado não compatível, você poderá bloquear o acesso a emails, SharePoint e muito mais.

O Intune no [portal do Azure](https://portal.azure.com) permite que você crie essas políticas e as aplique aos seus usuários e dispositivos. Como prática recomendada, comece pequeno e use uma abordagem em estágios. Por exemplo, crie uma política de iOS que bloqueia dispositivos desbloqueados. Aplica-se (chamado "Assign" no Intune) a política a um piloto ou grupo de teste. Após o teste inicial, adicione mais usuários ao grupo piloto. Usando uma abordagem em estágios, você pode obter comentários de uma ampla variedade de tipos de usuário.

Confira introdução [às políticas de conformidade do dispositivo](https://docs.microsoft.com/intune/device-compliance-get-started) e [saiba mais sobre o acesso condicional e o Intune?](https://docs.microsoft.com/intune/conditional-access) para ajudá-lo a começar.

## <a name="step-7-apply-features-and-settings"></a>Etapa 7: aplicar recursos e configurações

Esses recursos e configurações costumam ser considerados a parte "legal" do Intune e são muito eficientes. Após aplicar com êxito algumas políticas de conformidade usando o acesso condicional, você estará pronto para criar perfis de **dispositivo**.

O Intune no [portal do Azure](https://portal.azure.com) permite que você crie perfis diferentes com base em sua plataforma de dispositivo-IOS, MacOS, Android e Windows. Por exemplo, você pode:

- Use o Endpoint Protection em dispositivos Windows 10 para habilitar diferentes opções de BitLocker, incluindo criptografia.
- Use o recurso aplicativos restritos em dispositivos iOS para criar uma lista de aplicativos aprovados que podem ser instalados. Ou crie uma lista de aplicativos proibidos.
- Use as configurações de quiosque para escolher quais aplicativos podem ser usados em dispositivos Android executados no modo quiosque.
- Aplicar uma conexão Wi-Fi e suas configurações, incluindo o tipo de segurança, em dispositivos que executam o macOS.

[Aplicar recursos e configurações em seus dispositivos usando perfis de dispositivo](https://docs.microsoft.com/intune/device-profiles) é um ótimo local para ler sobre perfis, ver como criar um perfil e muito mais.

Lembre-se, comece pequeno e use uma abordagem em estágios. Atribua o perfil a um grupo piloto ou de teste. Em seguida, atribua o perfil a mais grupos pilotos.

## <a name="step-8-get-to-know-the-other-features"></a>Etapa 8: Conheça os outros recursos

O Intune é um serviço poderoso e inclui vários recursos. Veja algumas outras tarefas que você pode executar usando o Intune:

- Gerenciar software e atualizações em [dispositivos](https://docs.microsoft.com/intune/windows-update-for-business-configure) & Windows[PCs](https://docs.microsoft.com/intune/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)e dispositivos [Ios](https://docs.microsoft.com/intune/software-updates-ios)
- Ative a [proteção avançada contra ameaças do Microsoft defender (ATP)](https://docs.microsoft.com/intune/advanced-threat-protection) em seus dispositivos Windows 10 e use a conformidade e o acesso condicional para proteger o acesso a recursos corporativos, como o SharePoint ou o Exchange Online
- Use [atento](https://docs.microsoft.com/intune/lookout-mobile-threat-defense-connector), [Symantec](https://docs.microsoft.com/intune/skycure-mobile-threat-defense-connector)e outros parceiros de ameaças de defesa de dispositivos móveis
- Adicionar uma [autoridade de certificação (CA) de parceiro](https://docs.microsoft.com/intune/certificate-authority-add-scep-overview) para emitir e renovar certificados
- [Forneça orientações aos usuários finais](https://docs.microsoft.com/intune/end-user-educate) no aplicativo portal da empresa, obtendo aplicativos e muito mais
- Monitorar [aplicativos](https://docs.microsoft.com/intune/apps-monitor) e [perfis de configuração e conformidade de dispositivos](https://docs.microsoft.com/intune/compliance-policy-monitor)e mais telemetria usando os logs de auditoria. Você também pode se conectar ao [armazém de dados do Intune](https://docs.microsoft.com/intune/reports-nav-create-intune-reports) e usar o Power bi para obter ainda mais necessidades de relatórios.


## <a name="identity-and-device-access-recommendations"></a>Recomendações de acesso de dispositivo e identidade

A Microsoft fornece um conjunto de recomendações para [acesso de dispositivo e identidade](microsoft-365-policies-configurations.md) para garantir uma força de trabalho segura e produtiva. Para acesso ao dispositivo, use as recomendações e configurações nos artigos a seguir, juntamente com as etapas desta fase:

- [Pré-requisitos](identity-access-prerequisites.md)
- [Identidade comum e políticas de acesso ao dispositivo](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Como a Microsoft desenvolve o Microsoft 365 Enterprise

Saiba como os especialistas de ti da Microsoft [gerenciam dispositivos com o EMS](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR8).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Como a Contoso desenvolveu o Microsoft 365 Enterprise

Veja como a Contoso Corporation, uma empresa multinacional fictícia, mas representativa, [implantou sua infraestrutura de gerenciamento de dispositivo móvel com os](contoso-mdm.md) serviços de nuvem da Microsoft 365.

![A Contoso Corporation](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Próxima etapa

[Critérios de saída da infraestrutura de gerenciamento de dispositivo móvel](mobility-infrastructure-exit-criteria.md)

