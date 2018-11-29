---
title: Visão geral dos serviços do Microsoft 365 Enterprise | Microsoft Docs
description: Este conteúdo oferece uma visão geral do Microsoft 365 Enterprise e recomendações para uso empresarial.
author: jeffgilb
manager: femila
ms.prod: microsoft-365-business
ms.topic: article
ms.date: 08/23/2017
ms.author: jeffgilb
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 7772421a32abd863f4301a4bc3d8264d8fe44242
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865240"
---
# <a name="microsoft-365-enterprise-services-and-concepts"></a>Serviços e conceitos do Microsoft 365 Enterprise

O Microsoft 365 Enterprise foi desenvolvido para organizações de grande porte e integra-se ao Office 365 Enterprise, ao Windows 10 Enterprise e ao Enterprise Mobility + Security (EMS) a fim de permitir que todos sejam criativos e trabalhem juntos, de forma segura. O Microsoft 365 Enterprise inclui uma edição corporativa do Windows 10 e aplicativos do Office por meio do Office 365 ProPlus.

O Windows 10 e o Office 365 ProPlus fornecem novas versões de recursos para as empresas em março e setembro, por meio do Canal Semestral. Uma versão de recurso do Canal Semestral tem suporte durante 18 meses. O Microsoft Intune e o System Center Configuration Manager fornecem recursos para implantar e atualizar o Windows 10 e o Office 365 ProPlus.

Estas são as versões mais recentes do Windows 10, Office 365 ProPlus, Microsoft Intune e System Center Configuration Manager:

|     |**Canal Semestral (Direcionado)**|**Canal Semestral**|
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

## <a name="important-concepts-to-understand"></a>Conceitos importantes a serem entendidos
Os conceitos básicos e as funcionalidades do EMS com as quais você deve estar familiarizado são descritos na tabela abaixo.

|Conceito básico|Descrição|
|------------|-----------|
|[MFA (Autenticação Multifator) do Azure](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud)|Como a solução de verificação em duas etapas da Microsoft, o MFA do Azure ajuda a proteger o acesso aos dados e aos aplicativos e atende à demanda do usuário por um processo de conexão simples. Ele oferece uma autenticação forte por meio de uma variedade de métodos de verificação, incluindo verificação por chamada telefônica, por mensagem de texto ou por aplicativo móvel.|
|[Acesso condicional do Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)|Essa capacidade do Azure AD permite que você aplique controles no acesso a aplicativos de nuvem em seu ambiente com base em condições específicas. Com os controles, é possível vincular requisitos adicionais ao acesso ou bloqueá-lo. A implementação do acesso condicional é baseada em políticas.|
|[DLP (Prevenção contra perda de dados) do Exchange Online](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)|As políticas de DLP (Prevenção contra perda de dados) do Exchange Online, disponível como recurso premium de assinaturas do Exchange Online (Plano 2) e do Office 365, permitem que as organizações identifiquem, monitorem e protejam automaticamente informações confidenciais no Office 365.<br><br>Com as políticas DLP do Exchange Online, é possível identificar informações confidenciais em vários locais, como no Exchange Online, no SharePoint Online e no OneDrive para Empresas. Por exemplo, essas políticas ajudarão a identificar documentos que contêm informações confidenciais ou impedir o compartilhamento acidental de informações confidenciais com pessoas fora da sua organização.|
|[Regras de transporte/de fluxo de emails do Exchange](https://support.office.com/article/Define-mail-flow-rules-to-encrypt-or-decrypt-email-messages-9B7DAF19-D5F2-415B-BC43-A0F5F4A585E8)|As regras de fluxo de emails do Exchange, também conhecidas como regras de transporte, procuram condições específicas em mensagens passadas em toda a sua organização e agem sobre elas. As regras de fluxo de emails são como as regras da caixa de entrada que estão disponíveis em muitos clientes de email. A principal diferença entre as regras de fluxo de emails e as que você configuraria em um aplicativo cliente, como o Outlook, é que as regras de fluxo de emails agem sobre mensagens enquanto elas estão em trânsito, e não após a mensagem ser entregue. As regras de fluxo de emails também contêm um conjunto mais avançado de condições, exceções e ações, que oferece a flexibilidade para implementar muitos tipos de políticas de mensagem.|
|[Gerenciamento de dispositivo móvel do Intune](https://docs.microsoft.com/intune/understand-explore/introduction-to-microsoft-intune)|O Intune oferece o MDM (gerenciamento de dispositivo móvel) por meio de protocolos ou APIs disponíveis nos sistemas operacionais móveis. Ele inclui tarefas como registrar dispositivos no gerenciamento para que a TI tenha um inventário de dispositivos que estão acessando os serviços corporativos, configurar os dispositivos para garantir que eles atendam aos padrões de integridade e de segurança da empresa, fornecer certificados e perfis Wi-Fi/VPN para acessar serviços corporativos, informar e medir a conformidade do dispositivo quanto a padrões corporativos e remover dados corporativos de dispositivos gerenciados.|
|[Políticas de proteção de aplicativo do Intune](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)|As políticas de proteção de aplicativo do Intune podem ser usadas para proteger os dados da sua empresa em aplicativos móveis com ou sem o registro de dispositivos no gerenciamento. Na verdade, os dispositivos móveis dos seus usuários ainda podem ser gerenciados por outra solução de MDM que não seja da Microsoft, embora o [Intune ajude a proteger as informações do Office 365](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-company-data-without-managing-devices). Enquanto você se certifica de que seus funcionários ainda possam ser produtivos, também é possível evitar a perda de dados, intencional ou acidental. Implementando as políticas de nível de aplicativo, é possível restringir o acesso aos recursos da empresa e manter os dados dentro do controle do seu departamento de TI.|
|[Tempo de vida do token do Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes)|É possível especificar o tempo de vida de um token emitido pelo Azure AD (Azure Active Directory). É possível definir tempos de vida do token para todos os aplicativos em sua organização, para um aplicativo multilocatário (organização múltipla) ou para uma entidade de serviço específica em sua organização.|
|Agentes de identidade da Microsoft|A Microsoft fornece aplicativos para toda plataforma móvel que permitem a passagem de credenciais entre aplicativos de diferentes fornecedores e permitem recursos aprimorados especiais que exigem um local seguro único do qual validar as credenciais. Nós os chamamos de agentes. No iOS e no Android, esses agentes são fornecidos por meio dos aplicativos Microsoft Authenticator e Portal da Empresa do Intune. No Windows 10, essa funcionalidade é fornecida por um seletor de contas incorporado ao sistema operacional, conhecido tecnicamente como Agente de Autenticação da Web.|

## <a name="security-best-practices-and-recommendations"></a>Recomendações e melhores práticas de segurança
Embora não haja uma única melhor recomendação para todos os ambientes de clientes, o artigo [Políticas de segurança e configurações recomendadas](microsoft-365-policies-configurations.md) apresenta conceitos importantes de melhores práticas para serem compreendidos. Este artigo também descreve as recomendações gerais da Microsoft sobre como aplicar a política e a configuração na nuvem da Microsoft para garantir que os seus colaboradores estejam protegidos e também sejam produtivos.

### <a name="baseline-recommended-security-policies-and-configurations"></a>Configurações e políticas de segurança recomendadas de linha de base
A [identidade geral e as recomendações da política de acesso do dispositivo](identity-access-policies.md) descrevem as políticas normalmente recomendadas para ajudar você a proteger o Microsoft 365 Enterprise. Também são abordadas as configurações padrão do cliente da plataforma que recomendamos para oferecer a melhor experiência SSO para seus usuários, bem como os pré-requisitos técnicos para acesso condicional.

### <a name="exchange-online-access-policies"></a>Políticas de acesso do Exchange Online
As [recomendações de política para ajudar a proteger emails](secure-email-recommended-policies.md) fornecem recomendações da Microsoft para ajudar você a proteger o email organizacional e os clientes de email que dão suporte à Autenticação Moderna e ao Acesso Condicional. Essas recomendações são um complemento à [identidade comum e às recomendações da política de acesso](identity-access-policies.md).

### <a name="sharepoint-online-access-policies"></a>Políticas de acesso do SharePoint Online
As recomendações são fornecidas para [proteger o acesso aos arquivos do SharePoint Online](sharepoint-file-access-policies.md), além da [identidade comum e das recomendações da política de acesso](identity-access-policies.md) e das [recomendações de política para ajudar a proteger emails](secure-email-recommended-policies.md). Este artigo descreve as novas políticas que devem ser criadas e como as políticas existentes devem ser corrigidas para proteger o email do Exchange Online e o acesso aos arquivos do SharePoint Online.

## <a name="deploy-windows-10-and-office-365-proplus"></a>Implantar o Windows 10 e o Office 365 ProPlus
Saiba como implantar o Windows 10 e o Office 365 ProPlus e integrar ao Microsoft Azure Active Directory (Azure AD) ou no Active Directory Domain Services (AD DS). Implante o Windows 10, o Office 365 ProPlus e seus outros aplicativos de linha de negócios em novos dispositivos, ou atualize os dispositivos existentes para Windows 10 usando o Intune, o System Center Configuration Manager e a Política de Grupo para gerenciar dispositivos.

Para obter mais informações, consulte os artigos a seguir.
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
