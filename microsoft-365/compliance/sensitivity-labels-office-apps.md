---
title: Usar rótulos de confidencialidade em aplicativos do Office
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Saiba mais sobre como os usuários trabalham com rótulos de confidencialidade nos aplicativos do Office para a área de trabalho, aplicativos do Office para dispositivos móveis e aplicativos do Office para a Web. Descubra quais aplicativos dão suporte a rótulos de confidencialidade.
ms.openlocfilehash: 8015df13735097292be7c2866cdb9f5c061b2c68
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943594"
---
# <a name="use-sensitivity-labels-in-office-apps"></a>Usar rótulos de confidencialidade em aplicativos do Office

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

Quando você [publicou](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) rótulos de sensibilidade do centro de conformidade da Microsoft 365 ou do centro de rotulação equivalente, eles começarão a aparecer em aplicativos do Office para que os usuários classifiquem e protejam os dados à medida que são criados ou editados.

Use as informações deste artigo para ajudá-lo a gerenciar com êxito os rótulos de confidencialidade nos aplicativos do Office. Por exemplo, identifique as versões mínimas dos aplicativos necessários para dar suporte ao rotulamento interno e entenda as interações com o cliente de rotulação unificado de proteção de informações do Azure e a compatibilidade com outros aplicativos e serviços.

## <a name="labeling-client-for-desktop-apps"></a>Rotulando cliente para aplicativos de área de trabalho

Para usar rótulos de confidencialidade incorporados aos aplicativos de área de trabalho do Office para Windows e Mac, você deve usar uma edição de assinatura do Office. Este cliente de rótulo não dá suporte a edições autônomas do Office, como o Office 2016 ou o Office 2019.

Para usar rótulos de confidencialidade com essas edições autônomas do Office em computadores com Windows, instale o [cliente de rotulação unificada de proteção de informações do Azure](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2).

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>Suporte para recursos de rótulo de confidencialidade em aplicativos

Para cada capacidade, as tabelas a seguir listam a versão mínima necessária para esse aplicativo suportar rótulos de sensibilidade usando rotulação interna. Ou, se o recurso de rótulo estiver em visualização pública ou em revisão para uma versão futura.

Novas versões dos aplicativos são disponibilizadas em momentos diferentes para diferentes canais de atualização. Para obter mais informações, incluindo como configurar seu canal de atualização para que você possa testar um novo recurso de rotulação em que está interessado, consulte [Overview of Update Channels for Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus). Os novos recursos que estão na visualização privada não estão incluídos na tabela, mas você pode participar dessas visualizações, especificando sua organização para o [programa de visualização privada da proteção de informações da Microsoft](https://aka.ms/mip-preview).

Recursos adicionais estão disponíveis quando você instala o cliente de rotulação unificado de proteção de informações do Azure, que é executado somente em computadores Windows. Para obter esses detalhes, consulte [Compare the Labeling clients for Windows Computers](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers).

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Recursos de rótulo de confidencialidade no Word, Excel e PowerPoint

Para iOS e Android: onde eles têm uma versão mínima listada, o recurso de rótulo de confidencialidade também é compatível com o [aplicativo do Office](https://www.microsoft.com/en-us/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/).

|Funcionalidade                                                                                                        |Windows Desktop |Área de trabalho Mac |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[Aplicar, alterar ou remover manualmente o rótulo](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Visualização](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Aplicar um rótulo padrão](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | Em revisão                                                        |
|[Exigir uma justificativa para alterar um rótulo](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Visualização](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Fornecer ajuda para um link para uma página de ajuda personalizada](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Visualização](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Marcar o conteúdo](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Visualização](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Atribuir permissões agora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Visualização](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Permitir que usuários atribuam permissões](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | Distribuindo para o [canal mensal](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus#monthly-channel-for-microsoft-365-apps) (2003 +) | Distribuindo para o [canal mensal](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus#monthly-channel-for-microsoft-365-apps) (16.35 +)   | Em revisão   | Em revisão         | Em revisão                                                        |
|[Exibir o uso de rótulo com o rótulo Analytics](label-analytics.md) e enviar dados para administradores                      | Em revisão            | Em revisão        | Em revisão   | Em revisão         | Em revisão                                                        |
|[Exigir que os usuários apliquem um rótulo aos seus emails e documentos](sensitivity-labels.md#what-label-policies-can-do)   | Em revisão            | Em revisão        | Em revisão   | Em revisão         | Em revisão                                                        |
|[Aplicar um rótulo de confidencialidade automaticamente ao conteúdo](apply-sensitivity-label-automatically.md)                    | Visualização: no [Office Insider](https://office.com/insider)                                  | Em revisão | Em revisão | Em revisão | [Visualização](sensitivity-labels-sharepoint-onedrive-files.md) |
|Suporte para [salvamento automático](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) e [coautoria](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) em documentos rotulados e protegidos | Em revisão | Em revisão | Em revisão | Em revisão | [Visualização](sensitivity-labels-sharepoint-onedrive-files.md) |
|

### <a name="sensitivity-label-capabilities-in-outlook"></a>Recursos de rótulo de confidencialidade no Outlook

|Funcionalidade                                                                                                        |Outlook na área de trabalho do Windows |Área de trabalho do Outlook no Mac  |Outlook no iOS |Outlook no Android |Outlook na Web |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[Aplicar, alterar ou remover manualmente o rótulo](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sim               |
|[Aplicar um rótulo padrão](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sim               |
|[Exigir uma justificativa para alterar um rótulo](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sim               |
|[Fornecer ajuda para um link para uma página de ajuda personalizada](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sim               |
|[Marcar o conteúdo](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sim               |
|[Atribuir permissões agora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sim               |
|[Permitir que usuários atribuam permissões](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sim               |
|[Exibir o uso de rótulo com o rótulo Analytics](label-analytics.md) e enviar dados para administradores                      | Em revisão                       | Em revisão                    | Em revisão           | Em revisão               | Em revisão               |
|[Exigir que os usuários apliquem um rótulo aos seus emails e documentos](sensitivity-labels.md#what-label-policies-can-do)   | Em revisão                       | Em revisão                    | Em revisão           | Em revisão               | Em revisão               |
|[Aplicar um rótulo de confidencialidade automaticamente ao conteúdo](apply-sensitivity-label-automatically.md)                    | Visualização: distribuição para o [Office Insider](https://office.com/insider)                       | Em revisão                    | Em revisão           | Em revisão               | Sim |
|

## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Cliente de rotulagem interno do Office e outras soluções de rótulo

O cliente de rotulagem de rótulo do Office faz o download de rótulos de confidencialidade e definições de política de rótulo de confidencialidade dos seguintes centros de administração:

- Centro de conformidade do Microsoft 365
- Centro de segurança do Microsoft 365
- Centro de Segurança e Conformidade do Office 365

Para usar o cliente de rotulagem interno do Office, você deve ter uma ou mais [políticas de rótulo publicadas](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) para os usuários de um dos centros de administração listados e uma [versão com suporte do Office](#support-for-sensitivity-label-capabilities-in-apps).

Se ambas as condições forem atendidas, mas você precisar desativar o cliente de rotulamento interno do Office, use a seguinte configuração de política de Grupo:

1. Navegue até **configuração do usuário/Modelos Administrativos/Microsoft Office 2016/configurações de segurança**

2. Definir **use o recurso de sensibilidade do Office para aplicar e exibir rótulos de sensibilidade** a **0**. 
 
Implante essa configuração usando a política de grupo ou o serviço de [política de nuvem do Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service). A configuração entra em vigor quando os aplicativos do Office são reiniciados.

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Cliente de rotulamento interno do Office e o cliente de proteção de informações do Azure

Se os usuários tiverem um dos clientes de proteção de informações do Azure instalados ([Unificação de nome de cliente](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) ou [cliente clássico](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)), por padrão, o cliente de rotulação interno está desativado em seus aplicativos do Office. 

Para usar o rotulamento interno, em vez do cliente de proteção de informações do Azure para aplicativos do Office, use as instruções da seção anterior, mas defina a configuração da política de grupo **use o recurso de sensibilidade no Office para aplicar e exibir rótulos de sensibilidade** para **1**. 

Como alternativa, desabilite ou remova o suplemento do Office, **proteção de informações do Azure**. Este método é adequado para um único computador e testes ad-hoc. Para obter instruções, consulte [Exibir, gerenciar e instalar suplementos nos programas do Office](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d). 

Quando você desabilita ou remove este suplemento do Office, o cliente de proteção de informações do Azure permanece instalado para que você possa continuar a rotular arquivos fora de seus aplicativos do Office. Por exemplo, usando o explorador de arquivos ou o PowerShell.

Para obter informações sobre quais recursos são compatíveis com os clientes de proteção de informações do Azure e para o cliente de rotulagem interno do Office, consulte [escolher qual rotulação de cliente usar para computadores Windows](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) a partir da documentação de proteção de informações do Azure.

## <a name="protection-templates-and-sensitivity-labels"></a>Modelos de proteção e rótulos de confidencialidade

[Modelos de proteção](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)definidos pelo administrador, como aqueles que você define para a criptografia de mensagem do Office 365, não são visíveis em aplicativos do Office quando você está usando rotulação interna. Essa experiência simplificada reflete que não é necessário selecionar um modelo de proteção, porque as mesmas configurações estão incluídas com rótulos de confidencialidade com criptografia habilitada.

Se você precisar converter modelos de proteção existentes para rótulos, use o portal do Azure e as seguintes instruções: [para converter modelos em rótulos](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels).

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>Opções de gerenciamento de direitos de informação (IRM) e rótulos de confidencialidade

Os rótulos de confidencialidade configurados para aplicar criptografia removem a complexidade dos usuários para especificar suas próprias configurações de criptografia. Em muitos aplicativos do Office, essas configurações de criptografia individuais ainda podem ser configuradas manualmente por usuários usando as opções de gerenciamento de direitos de informação (IRM). Por exemplo, para aplicativos do Windows:

- Para um documento: **arquivo** > de**proteção** > de**informações** > de arquivo**restringir o acesso**
- para um email: na guia **opções** > **criptografar** 
  
Quando o usuário rotula inicialmente um documento ou um email, eles podem sempre substituir suas definições de configuração de rótulo por suas próprias configurações de criptografia. Por exemplo:

- Um usuário aplica o rótulo **confidencial \ todos os funcionários** a um documento e esse rótulo é configurado para aplicar as configurações de criptografia para todos os usuários da organização. Esse usuário define manualmente as configurações de IRM para restringir o acesso a um usuário fora da sua organização. O resultado final é um documento rotulado como **confidencial \ todos os funcionários** e criptografados, mas os usuários de sua organização não podem abri-lo conforme o esperado.

- Um usuário aplica somente o rótulo **confidencial \ destinatários** a um email, e este email é configurado para aplicar a configuração de criptografia de **não encaminhar**. Esse usuário configura manualmente as configurações de IRM para que o email seja irrestrito. O resultado final é o email pode ser encaminhado por destinatários, apesar de ter o rótulo **confidencial \ somente destinatários** .

- Um usuário aplica o rótulo **geral** a um documento, e esse rótulo não é configurado para aplicar criptografia. Esse usuário configura manualmente as configurações de IRM para restringir o acesso ao documento. O resultado final é um documento rotulado como **geral** , mas também aplica criptografia para que alguns usuários não possam abri-lo conforme o esperado.

Se o documento ou o email já estiver rotulado, um usuário poderá realizar qualquer uma dessas ações se o conteúdo ainda não estiver criptografado ou se ele tiver o [uso direito](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) de exportação ou controle total. 

Para obter uma experiência de rótulo mais consistente com relatórios significativos, forneça rótulos e orientações apropriados para que os usuários apliquem apenas rótulos para proteger documentos. Por exemplo:

- Para casos de exceção em que os usuários devem atribuir suas próprias permissões, forneça rótulos que [permitem que os usuários atribuam suas próprias permissões](encryption-sensitivity-labels.md#let-users-assign-permissions). 

- Em vez de usuários removendo manualmente a criptografia depois de selecionar um rótulo que aplica criptografia, forneça uma alternativa de subrótulo quando os usuários precisarem de um rótulo com a mesma classificação, mas sem criptografia. Como:
    - **Confidencial \ todos os funcionários**
    - **Confidencial \ qualquer pessoa (sem criptografia)**

> [!NOTE]
> Se os usuários removerem manualmente a criptografia de um documento rotulado armazenado no SharePoint ou no OneDrive e você tiver [habilitado rótulos de confidencialidade para arquivos do Office no SharePoint e no onedrive](sensitivity-labels-sharepoint-onedrive-files.md), a criptografia de rótulo será restaurada automaticamente na próxima vez que o documento for acessado ou baixado. 

## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>Aplicar rótulos de confidencialidade a arquivos, emails e anexos

Os usuários podem aplicar apenas um rótulo por vez para cada documento ou email.

Quando você rotula uma mensagem de email que tem anexos, os anexos não herdam o rótulo com uma exceção:

- O anexo é um documento do Office com um rótulo que não aplica criptografia e o rótulo que você aplica à mensagem de email aplica criptografia. Nesse caso, o documento do Office enviado por email herda o rótulo do email com suas configurações de criptografia.

Caso contrário: 

- Se os anexos tiverem um rótulo, eles manterão o rótulo aplicado originalmente.
- Se os anexos forem criptografados sem um rótulo, a criptografia permanecerá mas não serão rotuladas.
- Se os anexos não tiverem um rótulo, eles permanecerão sem rótulo.

## <a name="sensitivity-label-compatibility"></a>Compatibilidade de rótulo de confidencialidade

**Com aplicativos habilitados para RMS**: se você abrir um documento ou email rotulado e criptografado em um [aplicativo habilitado para RMS](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) que não ofereça suporte a rótulos de sensibilidade, o aplicativo ainda forçará a criptografia e o gerenciamento de direitos.

**Com o cliente de proteção de informações do Azure**: você pode exibir e alterar os rótulos de sensibilidade que você aplica aos documentos e emails com o cliente de rotulagem interno do Office usando o cliente de proteção de informações do Azure e o contrário.

**Com outras versões do Office**: qualquer usuário autorizado pode abrir documentos e emails rotulados em outras versões do Office. No entanto, você só pode exibir ou alterar o rótulo nas versões compatíveis do Office ou usando o cliente de proteção de informações do Azure. As versões do aplicativo do Office com suporte estão listadas na [seção anterior](#support-for-sensitivity-label-capabilities-in-apps).

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>Suporte para arquivos do SharePoint e do OneDrive protegidos por rótulos de confidencialidade

Para usar o cliente de rotulagem interno do Office com o Office na Web para documentos no OneDrive for Business ou no SharePoint Online, certifique-se de que você tenha optado pela visualização para [habilitar os rótulos de confidencialidade dos arquivos do Office no SharePoint e no onedrive](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="when-office-365-applies-content-marking-and-encryption"></a>Quando o Office 365 aplica a marcação e a criptografia de conteúdo

O Office 365 aplica a marcação e a criptografia de conteúdo com um rótulo de confidencialidade de forma diferente, dependendo do aplicativo usado.

| App | Marcação de conteúdo | Criptografia |
| --- | --- | --- |
| Word, Excel, PowerPoint em todas as plataformas | Imediatamente | Imediatamente |
| Outlook para PC e Mac | Após o Exchange Online enviar o email | Imediatamente |
| Outlook na Web, iOS e Android | Após o Exchange Online enviar o email | Após o Exchange Online enviar o email |
|

## <a name="end-user-documentation"></a>Documentação do usuário final

- [Aplicar rótulos de confidencialidade aos seus documentos e email no Office](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [Problemas conhecidos ao aplicar rótulos de confidencialidade aos arquivos do Office](https://support.office.com/article/known-issues-when-you-apply-sensitivity-labels-to-your-office-files-b169d687-2bbd-4e21-a440-7da1b2743edc)