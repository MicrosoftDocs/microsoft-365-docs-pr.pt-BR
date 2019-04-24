---
title: Visão geral dos serviços do Microsoft 365 Enterprise | Microsoft docs
description: Este conteúdo fornece uma visão geral das recomendações de uso do Microsoft 365 Enterprise e Enterprise.
author: jeffgilb
manager: femila
ms.prod: microsoft-365-business
ms.topic: article
ms.date: 08/23/2017
ms.author: jeffgilb
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 7772421a32abd863f4301a4bc3d8264d8fe44242
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290156"
---
# <a name="microsoft-365-enterprise-services-and-concepts"></a>Conceitos e serviços do Microsoft 365 Enterprise

O Microsoft 365 Enterprise foi desenvolvido para organizações de grande porte e integra-se ao Office 365 Enterprise, ao Windows 10 Enterprise e ao Enterprise Mobility + Security (EMS) a fim de permitir que todos sejam criativos e trabalhem juntos, de forma segura. O Microsoft 365 Enterprise inclui uma edição corporativa do Windows 10 e aplicativos do Office por meio do Office 365 ProPlus.

O Windows 10 e o Office 365 ProPlus fornecem novas versões de recursos para as empresas em março e setembro, por meio do Canal Semestral. Uma versão de recurso do Canal Semestral tem suporte durante 18 meses. O Microsoft Intune e o System Center Configuration Manager fornecem recursos para implantar e atualizar o Windows 10 e o Office 365 ProPlus.

Estas são as versões mais recentes do Windows 10, Office 365 ProPlus, Microsoft Intune e System Center Configuration Manager:

|     |**Canal Semestral (direcionado)**|**Canal Semestral**|
|:-----|:-----|:-----|
|**Windows 10**|Windows 10 Fall Creators Update (em breve)|Versão 1703|
|**Office 365 ProPlus**|Versão 1803|Versão 1708|
|**Intune**|N/D|Versão 1708|
|**System Center Configuration Manager**|Versão do Technical Preview 1708|Versão 1706<sup>*</sup>|

<sup>*</sup> A atualização 1706 do branch atual do System Center Configuration Manager está disponível como uma atualização no console para sites instalados anteriormente que executam a versão 1606, 1610 ou 1702.

> [!NOTE]
> Os serviços do Microsoft Azure também são atualizados regularmente, mas não são conhecidos por um número de versão. Para ver as atualizações mais recentes, e as próximas, para os serviços do Azure, consulte o [roteiro da plataforma de nuvem](https://www.microsoft.com/cloud-platform/roadmap).

Para saber mais sobre os recursos disponíveis nessas versões, consulte os seguintes artigos:
- [Novidades no Windows 10](https://docs.microsoft.com/windows/whats-new/)
- [Informações de versão do Windows 10](https://technet.microsoft.com/windows/release-info)
- [Histórico de atualizações do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history)
- [Versões de canal de atualização de cliente do Office 365](https://technet.microsoft.com/office/mt465751)
- [Novidades do Microsoft Intune](https://docs.microsoft.com/intune/whats-new)
- [Novidades no System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-incremental-versions)
- [Funcionalidades no Technical Preview 1708 do System Center Configuration Manager](https://docs.microsoft.com/sccm/core/get-started/capabilities-in-technical-preview-1708)

## <a name="services-overview"></a>Visão geral dos serviços

Esta seção oferece uma visão geral dos serviços do EMS e do Office 365 incluídos no Microsoft 365 Enterprise e também apresenta os conceitos básicos necessários para entender como usá-lo para suas necessidades organizacionais. Esses serviços oferecem funcionalidades que permitem que os administradores de empresa da nuvem da Microsoft não só protejam as identidades e os dispositivos dos funcionários da empresa, como também controlem o acesso aos próprios dados da empresa; tanto em trânsito quanto em repouso.

|Serviço|Descrição|
|-------|-----------|
|[Microsoft Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)|O Azure AD oferece um pacote completo de funcionalidades de gerenciamento de identidade, incluindo autenticação multifator, registro de dispositivos, gerenciamento de senha de autoatendimento, gerenciamento de grupo de autoatendimento, controle de acesso baseado em função, monitoramento de uso do aplicativo, alerta e monitoramento avançados de segurança e de auditoria.|
|[Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)|Esse serviço permite que você detecte possíveis vulnerabilidades que afetam as identidades da sua organização e configure respostas automatizadas por meio de políticas de acesso condicional para risco do usuário e risco de conexão baixo, médio e alto.|
|[Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)|Esse serviço permite que as organizações minimizem o número de pessoas que têm acesso persistente a operações privilegiadas. Para isso, o Azure AD Privileged Identity Management apresenta o conceito de um administrador qualificado. Os administradores qualificados devem ser usuários que precisam de acesso privilegiado de vez em quando, mas não todos os dias. A função ficará inativa até o usuário precisar de acesso. Depois de concluir um processo de ativação, ele se tornará um administrador ativo durante um período de tempo predeterminado.|
|[Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)| A Proteção de Informações do Azure é uma solução baseada em nuvem, fornecida como parte da oferta do EMS E5, que ajuda uma organização a classificar, rotular e proteger seus documentos e emails. Isso pode ser feito automaticamente por administradores que definem regras e condições, manualmente pelos usuários, ou uma combinação na qual os usuários recebem as recomendações. Você utiliza rótulos da Proteção de Informações do Azure para aplicar classificação a documentos e emails. Quando você faz isso, a classificação fica identificável sempre, independentemente de onde os dados são armazenados ou com quem eles são compartilhados.<br><br>As configurações da política de Proteção de Informações do Azure são protegidas pelo [Azure Rights Management](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms). De forma semelhante à maneira como os rótulos são aplicados, a proteção aplicada usando o Rights Management permanece com os documentos e emails, independentemente do local — dentro ou fora de sua organização, redes, servidores de arquivos e aplicativos.|
|[Microsoft Intune](https://docs.microsoft.com/intune/understand-explore/introduction-to-microsoft-intune)|O Intune é um serviço de EMM (gerenciamento de mobilidade empresarial) baseado em nuvem que ajuda a habilitar sua força de trabalho a ser produtiva enquanto mantém dados corporativos protegidos. O Intune integra-se completamente ao Azure AD para oferecer controle de acesso e de identidade e é usado para gerenciamento de dispositivos e de aplicativos. As funcionalidades do [Gerenciamento de dispositivo do Intune](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) são usadas para configurar e proteger os dispositivos do seu usuário, incluindo computadores Windows.<br><br>As funcionalidades do gerenciamento de dispositivo do Intune dão suporte ao registro [BYOD (Traga seu próprio dispositivo)](https://docs.microsoft.com/enterprise-mobility-security/solutions/enable-byod), que permite que os usuários registrem seus celulares, tablets ou computadores, e ao registro [COD (Dispositivo de propriedade corporativa)](https://docs.microsoft.com/enterprise-mobility-security/solutions/issue-corp-devices) que habilita cenários de gerenciamento como registro automático, dispositivos compartilhados ou configurações de requisito de registro pré-autorizado. Para ter mais segurança, ainda é possível exigir que a MFA registre um dispositivo. Depois de registrado no gerenciamento, o Intune poderá configurar os recursos e as configurações do dispositivo para habilitar o acesso seguro aos recursos da empresa.|

## <a name="important-concepts-to-understand"></a>Conceitos importantes a serem compreendidos
Os principais conceitos e recursos de EMS com os quais você deve estar familiarizado estão descritos na tabela abaixo.

|Conceito principal|Descrição|
|------------|-----------|
|[MFA (autenticação multiFator do Azure)](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud)|Como a solução de verificação de duas etapas da Microsoft, o Azure MFA ajuda a proteger o acesso a dados e aplicativos enquanto atende à demanda do usuário para um processo de entrada simples. Ele oferece autenticação forte por meio de um intervalo de métodos de verificação, incluindo chamadas telefônicas, mensagens de texto ou verificações de aplicativos móveis.|
|[Acesso condicional do Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)|Esse recurso do Azure AD permite que você aplique controles no acesso aos aplicativos de nuvem no seu ambiente com base em condições específicas. Com controles, você pode vincular outros requisitos para o acesso ou pode bloqueá-lo. A implementação do acesso condicional é baseada em políticas.|
|[Prevenção de perda de dados do Exchange Online (DLP)](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)|Políticas de prevenção contra perda de dados (DLP) do Exchange Online, disponíveis como um recurso Premium das assinaturas do Exchange Online Plan 2 e do Office 365, permitem que as organizações identifiquem, monitorem e protejam automaticamente as informações confidenciais no Office 365.<br><br>Com as políticas de DLP do Exchange Online, você pode identificar informações confidenciais em vários locais, como o Exchange Online, o SharePoint Online e o OneDrive for Business. Por exemplo, essas políticas ajudam a identificar documentos contendo informações confidenciais ou a impedir o compartilhamento acidental de informações confidenciais com pessoas de fora da organização.|
|[Regras de fluxo/transporte de email do Exchange](https://support.office.com/article/Define-mail-flow-rules-to-encrypt-or-decrypt-email-messages-9B7DAF19-D5F2-415B-BC43-A0F5F4A585E8)|Regras de fluxo de emails do Exchange, também conhecidas como regras de transporte, procure condições específicas em mensagens que passam pela sua organização e as agem. As regras de fluxo de emails são semelhantes às regras de caixa de entrada que estão disponíveis em muitos clientes de email. A principal diferença entre regras de fluxo de emails e regras que você configurou em um aplicativo cliente como o Outlook é que as regras de fluxo de emails atuam em mensagens enquanto estão em trânsito, em oposição à mensagem ser entregue. As regras de fluxo de emails também contêm um conjunto mais avançado de condições, exceções e ações, que oferece a flexibilidade para implementar muitos tipos de políticas de mensagens.|
|[Gerenciamento de dispositivo móvel do Intune](https://docs.microsoft.com/intune/understand-explore/introduction-to-microsoft-intune)|O Intune oferece o gerenciamento de dispositivo móvel (MDM) usando os protocolos ou APIs disponíveis nos sistemas operacionais móveis. Ele inclui tarefas como registrar dispositivos no gerenciamento para que ele tenha um inventário de dispositivos que estão acessando serviços corporativos, configurando dispositivos para garantir que eles atendam aos padrões de segurança e integridade da empresa, fornecendo certificados e perfis Wi-Fi/VPN a acessar serviços corporativos, relatar e medir a conformidade de dispositivos para padrões corporativos e remover dados corporativos de dispositivos gerenciados.|
|[Políticas de proteção de aplicativos do Intune](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)|As políticas de proteção de aplicativos do Intune podem ser usadas para proteger os dados da sua empresa em aplicativos móveis com ou sem registrar dispositivos no gerenciamento. Na verdade, os dispositivos móveis dos seus usuários podem até mesmo ser gerenciados por outra solução não Microsoft MDM enquanto o [Intune ajuda a proteger as informações do Office 365](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-company-data-without-managing-devices). Ao garantir que seus funcionários ainda possam ser produtivos, você também pode evitar a perda de dados intencionais e não intencionais. Ao implementar políticas de nível de aplicativo, você pode restringir o acesso aos recursos da empresa e manter os dados dentro do controle do departamento de ti.|
|[Tempo de vida do token do Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes)|Você pode especificar o tempo de vida de um token emitido pelo Azure Active Directory (Azure AD). Você pode definir vidas úteis de token para todos os aplicativos em sua organização, para um aplicativo multilocatário (várias organizações) ou para uma entidade de serviço específica em sua organização.|
|Agentes de identidade da Microsoft|A Microsoft fornece aplicativos para cada plataforma móvel que permitem a ponte de credenciais entre aplicativos de diferentes fornecedores e permite recursos avançados avançados que exigem um único local seguro de onde validar as credenciais. Chamamos esses agentes. No iOS e no Android, esses agentes são fornecidos por meio do Microsoft Authenticator e dos aplicativos do portal da empresa do Intune. No Windows 10, essa funcionalidade é fornecida por um seletor de contas interno no sistema operacional, conhecido tecnicamente como o agente de autenticação da Web.|

## <a name="security-best-practices-and-recommendations"></a>Recomendações e melhores práticas de segurança
Embora não haja uma única melhor recomendação para todos os ambientes de clientes, o artigo [Políticas de segurança e configurações recomendadas](microsoft-365-policies-configurations.md) apresenta conceitos importantes de melhores práticas para serem compreendidos. Este artigo também descreve as recomendações gerais da Microsoft sobre como aplicar a política e a configuração na nuvem da Microsoft para garantir que os seus colaboradores estejam protegidos e também sejam produtivos.

### <a name="baseline-recommended-security-policies-and-configurations"></a>Configurações e políticas de segurança recomendadas de linha de base
[Recomendações de política de acesso de dispositivo e identidade geral](identity-access-policies.md) descreve as políticas comuns recomendadas para ajudá-lo a proteger o Microsoft 365 Enterprise. Também são abordadas as configurações padrão do cliente da plataforma que recomendamos para oferecer a melhor experiência SSO para seus usuários, bem como os pré-requisitos técnicos para acesso condicional.

### <a name="exchange-online-access-policies"></a>Políticas de acesso do Exchange Online
[Recomendações de política para ajudar a proteger o email](secure-email-recommended-policies.md) fornece recomendações da Microsoft para ajudá-lo a proteger emails organizacionais e clientes de email com suporte para autenticação moderna e acesso condicional. Essas recomendações são um complemento à [identidade comum e às recomendações da política de acesso](identity-access-policies.md).

### <a name="sharepoint-online-access-policies"></a>Políticas de acesso do SharePoint Online
As recomendações são fornecidas para [proteger o acesso a arquivos do SharePoint Online](sharepoint-file-access-policies.md) além das recomendações de política de [acesso e identidade comuns](identity-access-policies.md) e [recomendações de política para ajudar a proteger emails](secure-email-recommended-policies.md). Este artigo descreve as novas políticas que devem ser criadas e como as políticas existentes devem ser corrigidas para proteger o email do Exchange Online e o acesso a arquivos do SharePoint Online.

## <a name="deploy-windows-10-and-office-365-proplus"></a>Implantar o Windows 10 e o Office 365 ProPlus
Saiba como implantar o Windows 10 e o Office 365 ProPlus e integrar ao Microsoft Azure Active Directory (Azure AD) ou no Active Directory Domain Services (AD DS). Implante o Windows 10, o Office 365 ProPlus e seus outros aplicativos de linha de negócios em novos dispositivos, ou atualize os dispositivos existentes para Windows 10 usando o Intune, o System Center Configuration Manager e a Política de Grupo para gerenciar dispositivos.

Para saber mais, confira os seguintes artigos:
- [Considerações sobre a implantação do Windows 10](https://docs.microsoft.com/windows/deployment/planning/windows-10-deployment-considerations)
- [Guia de implantação do Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/deployment-guide-for-office-365-proplus)
- [Guia de práticas recomendadas para implantação do Office 365 ProPlus na empresa](https://docs.microsoft.com/DeployOffice/best-practices/best-practices)
- [Implantar aplicativos do Office 365 ProPlus em dispositivos Windows 10 usando o Intune](https://docs.microsoft.com/intune/apps-add-office365)

Para obter assistência de implantação com o Microsoft 365 [entre em contato com o FastTrack](https://fasttrack.microsoft.com/microsoft365).

## <a name="manage-updates-to-windows-10-and-office-365-proplus"></a>Gerenciar atualizações para Windows 10 e Office 365 ProPlus
Os links a seguir mostram como obter o máximo de controle sobre a qualidade e as atualizações de recurso para Windows 10 e Office 365 ProPlus. Aprenda a controlar com eficiência o uso de largura de banda e a manter o Windows e o Office atualizados com os recursos e atualizações de segurança mais recentes.

Para obter mais informações, consulte os artigos a seguir.
- [Visão geral do Windows como serviço](https://docs.microsoft.com/windows/deployment/update/waas-overview)
- [Visão geral dos canais de atualização do Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)
- [Gerenciar atualizações de software com o Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure)
- [Implantar as atualizações do Windows 10 usando o System Center Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)<sup>*</sup>
- [Gerenciar o Office 365 ProPlus com o Configuration Manager](https://docs.microsoft.com/sccm/sum/deploy-use/manage-office-365-proplus-updates)

<sup>*</sup> A Microsoft incentiva as organizações que estão usando o Configuration Manager para gerenciamento de atualizações do Windows a continuar fazendo isso para computadores cliente com Windows 10.

## <a name="next-steps"></a>Próximas etapas
[Página do produto do Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise)<br/>
[Roteiro da plataforma de nuvem](https://www.microsoft.com/cloud-platform/roadmap)
