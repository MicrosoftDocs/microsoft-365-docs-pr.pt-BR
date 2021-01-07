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
description: Saiba mais sobre como os usuários trabalham com rótulos de confidencialidade nos aplicativos do Office para área de trabalho, celular e Web e quais aplicativos dão suporte a rótulos de confidencialidade.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ebf4626a6106a9bebc62c8bca1be825c645d60fd
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777074"
---
# <a name="use-sensitivity-labels-in-office-apps"></a>Usar rótulos de confidencialidade em aplicativos do Office

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

Quando você [publicou](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) rótulos de sensibilidade do centro de conformidade da Microsoft 365 ou do centro de rotulação equivalente, eles começarão a aparecer em aplicativos do Office para que os usuários classifiquem e protejam os dados à medida que são criados ou editados.

Use as informações deste artigo para ajudá-lo a gerenciar com êxito os rótulos de confidencialidade nos aplicativos do Office. Por exemplo, identifique as versões mínimas dos aplicativos necessários para dar suporte ao rotulamento interno e entenda as interações com o cliente de rotulação unificado de proteção de informações do Azure e a compatibilidade com outros aplicativos e serviços.

## <a name="labeling-client-for-desktop-apps"></a>Rotulando cliente para aplicativos de área de trabalho

Para usar rótulos de confidencialidade incorporados aos aplicativos de área de trabalho do Office para Windows e Mac, você deve usar uma edição de assinatura do Office. Este cliente de rótulo não dá suporte a edições autônomas do Office, como o Office 2016 ou o Office 2019.

Para usar rótulos de confidencialidade com essas edições autônomas do Office em computadores com Windows, instale o [cliente de rotulação unificada de proteção de informações do Azure](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2).

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>Suporte para recursos de rótulo de confidencialidade em aplicativos

Para cada capacidade, as tabelas a seguir listam a versão mínima do Office que você precisa para suportar rótulos de sensibilidade usando rotulação interna. Ou, se o recurso de rótulo estiver em visualização pública ou em revisão para uma versão futura. Use o [mapa do Microsoft 365](https://aka.ms/MIPC/Roadmap) para obter detalhes sobre versões futuras.

Novas versões de aplicativos do Office são disponibilizadas em momentos diferentes para diferentes canais de atualização. Para obter mais informações, incluindo como configurar seu canal de atualização para que você possa testar um novo recurso de rotulação em que está interessado, consulte [Overview of Update Channels for Microsoft 365 apps](https://docs.microsoft.com/DeployOffice/overview-update-channels). Os novos recursos que estão na visualização privada não estão incluídos na tabela, mas você pode participar dessas visualizações, especificando sua organização para o [programa de visualização privada da proteção de informações da Microsoft](https://aka.ms/mip-preview).

> [!NOTE]
> Os nomes dos canais de atualização dos aplicativos do Office foram alterados recentemente. Por exemplo, o canal mensal agora é o canal atual, e o Office Insider agora é um canal beta. Para obter mais informações, consulte [Changes to update Channels for Microsoft 365 apps](https://docs.microsoft.com/deployoffice/update-channels-changes).

Office para iOS e Office para Android: os rótulos de confidencialidade são incorporados no [aplicativo do Office](https://www.microsoft.com/en-us/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/).

Recursos adicionais estão disponíveis quando você instala o cliente de rotulação unificado de proteção de informações do Azure, que é executado somente em computadores Windows. Para obter esses detalhes, consulte [Compare the Labeling clients for Windows Computers](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers).

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Recursos de rótulo de confidencialidade no Word, Excel e PowerPoint

Os números listados são a versão mínima do aplicativo do Office necessária para cada recurso.

|Recursos                                                                                                        |Windows |Mac |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[Aplicar, alterar ou remover manualmente o rótulo](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Sim-aceitar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Aplicar um rótulo padrão](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Sim-aceitar](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|[Exigir uma justificativa para alterar um rótulo](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Sim-aceitar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Fornecer ajuda para um link para uma página de ajuda personalizada](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Sim-aceitar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Marcar o conteúdo](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Sim-aceitar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Marcações dinâmicas com variáveis](#dynamic-markings-with-variables)                                              | 2010 +           | 16.42 +     | 2.42 + | 16.0.13328 + | Em revisão |
|[Atribuir permissões agora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Sim-aceitar](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Permitir que usuários atribuam permissões](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |2004 + | 16.35 +   | Em revisão   | Em revisão         | Em revisão                                                        |
|[Exibir o uso de rótulo com o rótulo Analytics](label-analytics.md) e enviar dados para administradores                      | Visualização: [canal atual (visualização)](https://office.com/insider)            | Visualização: [canal atual (visualização)](https://office.com/insider)        | Em revisão   | Em revisão         | Sim <sup>\*</sup>                                                        |
|[Exigir que os usuários apliquem um rótulo aos seus emails e documentos](sensitivity-labels.md#what-label-policies-can-do)   | Visualização: distribuição para o [canal atual (visualização)](https://office.com/insider)             | Visualização: distribuição para o [canal atual (visualização)](https://office.com/insider)         | Em revisão   | Visualização: [canal beta](https://office.com/insider)         | Em revisão                                            
|[Aplicar um rótulo de confidencialidade automaticamente ao conteúdo](apply-sensitivity-label-automatically.md)                    | 2009 +                                  | Visualização para Word e PowerPoint: distribuindo para o [canal atual (visualização)](https://office.com/insider) | Em revisão | Em revisão | [Sim-aceitar](sensitivity-labels-sharepoint-onedrive-files.md) |
|Suporte para [salvamento automático](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) e [coautoria](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) em documentos rotulados e criptografados | Em revisão | Em revisão | Em revisão | Em revisão | [Sim-aceitar](sensitivity-labels-sharepoint-onedrive-files.md) |
|

**Footnote**

<sup>\*</sup> No momento, não inclui texto de justificativa para remover um rótulo ou diminuir o nível de classificação

### <a name="sensitivity-label-capabilities-in-outlook"></a>Recursos de rótulo de confidencialidade no Outlook

Os números listados são a versão mínima do aplicativo do Office necessária para cada recurso.

|Recursos                                                                                                        |Outlook para Windows |Outlook para Mac |Outlook no iOS |Outlook no Android |Outlook na Web |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[Aplicar, alterar ou remover manualmente o rótulo](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sim               |
|[Aplicar um rótulo padrão](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sim               |
|[Exigir uma justificativa para alterar um rótulo](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sim               |
|[Fornecer ajuda para um link para uma página de ajuda personalizada](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sim               |
|[Marcar o conteúdo](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sim               |
|[Marcações dinâmicas com variáveis](#dynamic-markings-with-variables)                                              | Em revisão                     | Em revisão                 | Em revisão         | Em revisão           | Em revisão               |
|[Atribuir permissões agora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sim               |
|[Permitir que usuários atribuam permissões](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sim               |
|[Exigir que os usuários apliquem um rótulo aos seus emails e documentos](#require-users-to-apply-a-label-to-their-email-and-documents)   | Visualização: [canal atual (visualização)](https://office.com/insider))                        | 16.43 +                     | 4.57.0 +            | 4.2037.4 +                | Sim                |
|[Exibir o uso de rótulo com o rótulo Analytics](label-analytics.md) e enviar dados para administradores                      | Visualização: [canal atual (visualização)](https://office.com/insider)                       | Visualização: [canal atual (visualização)](https://office.com/insider)                    | Em revisão           | Em revisão               | Sim               |
|[Aplicar um rótulo de confidencialidade automaticamente ao conteúdo](apply-sensitivity-label-automatically.md)                    | 2009 +                      | Em revisão                    | Em revisão           | Em revisão               | Sim |
|


## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Cliente de rotulagem interno do Office e outras soluções de rótulo

O cliente de rotulagem de rótulo do Office faz o download de rótulos de confidencialidade e definições de política de rótulo de confidencialidade dos seguintes centros de administração:

- Centro de conformidade do Microsoft 365
- Centro de segurança do Microsoft 365
- Centro de Segurança e Conformidade do Office 365

Para usar o cliente de rotulagem interno do Office, você deve ter uma ou mais [políticas de rótulo publicadas](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) para os usuários de um dos centros de administração listados e uma [versão com suporte do Office](#support-for-sensitivity-label-capabilities-in-apps).

Se ambas as condições forem atendidas, mas você precisar desativar o cliente de rotulamento interno do Office, use a seguinte configuração de política de Grupo:

1. Navegue até **configuração do usuário/Modelos Administrativos/Microsoft Office 2016/configurações de segurança**.

2. Definir **use o recurso de sensibilidade do Office para aplicar e exibir rótulos de sensibilidade** a **0**. 
 
Implante essa configuração usando a política de grupo ou o serviço de [política de nuvem do Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service). A configuração entra em vigor quando os aplicativos do Office são reiniciados.

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Cliente de rotulamento interno do Office e o cliente de proteção de informações do Azure

Se os usuários tiverem um dos clientes de proteção de informações do Azure instalados ([Unificação de nome de cliente](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) ou [cliente clássico](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)), por padrão, o cliente de rotulação interno está desativado em seus aplicativos do Office. 

Para usar o rotulamento interno, em vez do cliente de proteção de informações do Azure para aplicativos do Office, use as instruções da seção anterior, mas defina a configuração da política de grupo **use o recurso de sensibilidade no Office para aplicar e exibir rótulos de sensibilidade** para **1**. 

Como alternativa, desabilite ou remova o suplemento do Office, **proteção de informações do Azure**. Este método é adequado para um único computador e testes ad-hoc. Para obter instruções, consulte [Exibir, gerenciar e instalar suplementos nos programas do Office](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d). 

Quando você desabilita ou remove este suplemento do Office, o cliente de proteção de informações do Azure permanece instalado para que você possa continuar a rotular arquivos fora de seus aplicativos do Office. Por exemplo, usando o explorador de arquivos ou o PowerShell.

Para obter informações sobre quais recursos são compatíveis com os clientes de proteção de informações do Azure e para o cliente de rotulagem interno do Office, consulte [escolher qual rotulação de cliente usar para computadores Windows](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) a partir da documentação de proteção de informações do Azure.

## <a name="office-file-types-supported"></a>Tipos de arquivo do Office suportados

Os aplicativos do Office que possuem rotulação interna para arquivos do Word, Excel e PowerPoint oferecem suporte para o formato Open XML (como. docx e. xlsx), mas não para o formato do Microsoft Office 97-2003 (como. doc e. xls). Quando um tipo de arquivo não tem suporte para rotulamento interno, o botão **sensibilidade** não está disponível no aplicativo do Office.

O cliente de rotulação unificada de proteção de informações do Azure suporta o formato Open XML e o formato do Microsoft Office 97-2003. Para obter mais informações, consulte [tipos de arquivo compatíveis com o cliente de rotulação unificado de proteção de informações do Azure](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-file-types) no guia de administração do cliente.

Para outras soluções de rotulação, verifique a documentação para tipos de arquivo com suporte.

## <a name="protection-templates-and-sensitivity-labels"></a>Modelos de proteção e rótulos de confidencialidade

[Modelos de proteção](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)definidos pelo administrador, como aqueles que você define para a criptografia de mensagem do Office 365, não são visíveis em aplicativos do Office quando você está usando rotulação interna. Essa experiência simplificada reflete que não é necessário selecionar um modelo de proteção, porque as mesmas configurações estão incluídas com rótulos de confidencialidade com criptografia habilitada.

Se você precisar converter modelos de proteção existentes para rótulos, use o portal do Azure e as seguintes instruções: [para converter modelos em rótulos](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels).

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>Opções de gerenciamento de direitos de informação (IRM) e rótulos de confidencialidade

Os rótulos de confidencialidade configurados para aplicar criptografia removem a complexidade dos usuários para especificar suas próprias configurações de criptografia. Em muitos aplicativos do Office, essas configurações de criptografia individuais ainda podem ser configuradas manualmente por usuários usando as opções de gerenciamento de direitos de informação (IRM). Por exemplo, para aplicativos do Windows:

- Para um documento: **arquivo** de proteção de informações de arquivo restringir o  >    >    >  **acesso**
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

Para usar o cliente de rotulagem interno do Office com o Office na Web para documentos no SharePoint ou no OneDrive, verifique se você [habilitou rótulos de confidencialidade para arquivos do Office no SharePoint e no onedrive](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="support-for-external-users-and-labeled-content"></a>Suporte para usuários externos e conteúdo rotulado

Quando você rotula um documento ou email, o rótulo é armazenado como metadados que incluem seu locatário e um GUID de rótulo. Quando um documento ou email rotulado é aberto por um aplicativo do Office que oferece suporte a rótulos de sensibilidade, esses metadados são lidos e somente se o usuário pertencer ao mesmo locatário, o rótulo será exibido em seus aplicativos. Por exemplo, para rotulamento interno para Word, PowerPoint e Excel, o nome do rótulo é exibido na barra de status. 

Isso significa que, se você compartilhar documentos com outra organização que usa nomes de rótulo diferentes, cada organização poderá aplicar e ver seu próprio rótulo aplicado ao documento. No entanto, os seguintes elementos de um rótulo aplicado são visíveis para os usuários de fora da sua organização:

- Marcações de conteúdo. Quando um rótulo aplica um cabeçalho, rodapé ou marca d' água, eles são adicionados diretamente ao conteúdo e permanecem visíveis até que alguém modifique ou exclua-os.

- O nome e a descrição do modelo de proteção subjacente de um rótulo que aplicou a criptografia. Essas informações são exibidas em uma barra de mensagens na parte superior do documento, para fornecer informações sobre quem está autorizado a abrir o documento e seus direitos de uso desse documento.

### <a name="sharing-encrypted-documents-with-external-users"></a>Compartilhamento de documentos criptografados com usuários externos

Além de restringir o acesso aos usuários em sua própria organização, você pode estender o acesso a qualquer outro usuário que tenha uma conta no Azure Active Directory. Todos os aplicativos do Office e outros [aplicativos habilitados para RMS](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) podem abrir documentos criptografados após o usuário ter autenticado com êxito.

Se os usuários externos não tiverem uma conta no Azure Active Directory, você poderá criar uma conta de convidado para eles em seu locatário. Para o endereço de email, você pode especificar qualquer endereço de email que já esteja usando. Por exemplo, seu endereço do gmail. Essa conta de convidado também pode ser usada para acessar um documento compartilhado no SharePoint ou no OneDrive quando você tiver [habilitado rótulos de sensibilidade para arquivos do Office no SharePoint e no onedrive](sensitivity-labels-sharepoint-onedrive-files.md).

Os usuários externos também podem usar uma conta da Microsoft para documentos criptografados quando usam o Microsoft 365 aplicativos ([anteriormente conhecido como aplicativos do Office 365](https://docs.microsoft.com/deployoffice/name-change)) no Windows e com suporte recém-instalado no MacOS (versão 16.42 +), Android (versão 16.0.13029 +) e IOS (versão 2.42 +). Por exemplo, alguém compartilha um documento criptografado com eles, e as configurações de criptografia especificam o endereço de email do gmail. Este usuário pode criar sua própria conta da Microsoft que usa o endereço de email do gmail. Depois, após entrar com essa conta, eles poderão abrir o documento e editá-lo, de acordo com as restrições de uso especificadas para esse usuário. Para obter um exemplo passo a passo desse cenário, consulte [abrindo e editando o documento protegido](https://docs.microsoft.com/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document).

> [!NOTE]
> O endereço de email da conta da Microsoft deve corresponder ao endereço de email especificado para restringir o acesso às configurações de criptografia.

Quando um usuário com uma conta da Microsoft abre um documento criptografado dessa forma, ele cria automaticamente uma conta de convidado para o locatário se já não existir uma conta de convidado com o mesmo nome. Quando a conta de convidado existe, ela pode ser usada para abrir documentos no SharePoint e no OneDrive usando um navegador (Office na Web), além de abrir documentos criptografados do aplicativo da área de trabalho do Windows. 

No entanto, a conta de convidado automática não é criada imediatamente devido à latência de replicação. Se você especificar endereços de email pessoais como parte de suas configurações de criptografia de rótulo, recomendamos que você crie contas de convidados correspondentes no Azure Active Directory. Em seguida, permita que esses usuários saibam que eles devem usar essa conta para abrir um documento criptografado da sua organização.

> [!TIP]
> Como não é possível ter certeza de que os usuários externos usarão um aplicativo cliente do Office com suporte, o compartilhamento de links do SharePoint e do OneDrive após a criação de contas de convidados é um método mais confiável de suporte à colaboração segura com usuários externos.

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>Quando os aplicativos do Office aplicam a marcação e a criptografia de conteúdo

Os aplicativos do Office aplicam a marcação e a criptografia de conteúdo com um rótulo de confidencialidade de forma diferente, dependendo do aplicativo usado.

| App | Marcação de conteúdo | Criptografia |
| --- | --- | --- |
| Word, Excel, PowerPoint em todas as plataformas | Imediatamente | Imediatamente |
| Outlook para PC e Mac | Após o Exchange Online enviar o email | Imediatamente |
| Outlook na Web, iOS e Android | Após o Exchange Online enviar o email | Após o Exchange Online enviar o email |
|

As soluções que aplicam rótulos de confidencialidade aos arquivos fora dos aplicativos do Office fazem isso aplicando os metadados de rótulo ao arquivo. Neste cenário, a marcação de conteúdo da configuração do rótulo não é inserida no arquivo, mas a criptografia é aplicada. 

Quando esses arquivos são abertos em um aplicativo da área de trabalho do Office, as marcações de conteúdo são automaticamente aplicadas pelo cliente de rotulação unificado de proteção de informações do Azure. As marcações de conteúdo não são aplicadas automaticamente quando você usa rotulamento interno para aplicativos de área de trabalho, móveis ou Web.

Os cenários que incluem a aplicação de um rótulo de confidencialidade fora dos aplicativos do Office incluem:

- O scanner, o explorador de arquivos e o PowerShell do cliente de rotulação unificado de proteção de informações do Azure 

- Diretivas de rotulação automática para o SharePoint e o OneDrive

- Dados de rótulo e criptografados exportados do Power BI

- Microsoft Cloud App Security

Para esses cenários, usando seus aplicativos do Office, um usuário com rotulação interna pode aplicar as marcações de conteúdo do rótulo, removendo ou substituindo temporariamente o rótulo atual e reaplicando o rótulo original.

### <a name="dynamic-markings-with-variables"></a>Marcações dinâmicas com variáveis

> [!IMPORTANT]
> No momento, nem todos os aplicativos em todas as plataformas dão suporte a marcações de conteúdo dinâmico que você pode especificar para seus cabeçalhos, rodapés e marcas d' água. Para aplicativos que não dão suporte a esse recurso, eles aplicam as marcações como o texto original especificado na configuração do rótulo, em vez de resolver as variáveis.
> 
> O cliente de rótulo unificado de proteção de informações do Azure oferece suporte a marcações dinâmicas. Para rotular interno para o Office, Confira as tabelas na seção [recursos](#support-for-sensitivity-label-capabilities-in-apps) da página.

Ao configurar um rótulo de confidencialidade para marcações de conteúdo, você pode usar as seguintes variáveis na cadeia de caracteres de texto do cabeçalho, rodapé ou marca d' água:

| Variável | Descrição | Exemplo quando o rótulo é aplicado |
| -------- | ----------- | ------- |
| `${Item.Label}` | Nome para exibição do rótulo aplicado| **Geral**|
| `${Item.Name}` | Nome do arquivo ou assunto de email do conteúdo que está sendo rotulado | **Sales.docx** |
| `${Item.Location}` | Caminho e nome de arquivo do documento que está sendo rotulado ou o assunto do email para um email que está sendo rotulado | **\\\Sales\2020\Q3\Report.docx**|
| `${User.Name}` | Nome para exibição do usuário que está aplicando o rótulo| **Richard Simone** |
| `${User.PrincipalName}` | Nome principal de usuário do Azure AD (UPN) do usuário que está aplicando o rótulo | **rsimone \@ contoso.com** |
| `${Event.DateTime}` | Data e hora em que o conteúdo é rotulado, no fuso horário local do usuário que está aplicando o rótulo | **8/10/2020 1:30 PM** |

> [!NOTE]
> A sintaxe dessas variáveis diferencia maiúsculas de minúsculas.

## <a name="require-users-to-apply-a-label-to-their-email-and-documents"></a>Exigir que os usuários apliquem um rótulo aos seus emails e documentos

> [!IMPORTANT]
> Também conhecido como rotulação obrigatória, nem todos os aplicativos em todas as plataformas oferecem suporte à configuração de política de **exigir que os usuários apliquem um rótulo aos seus emails e documentos**.
> 
> O [cliente de rotulação unificado de proteção de informações do Azure](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app) oferece suporte a rotulamento obrigatório e rótulo interno para aplicativos do Office, Confira as tabelas na seção [recursos](#support-for-sensitivity-label-capabilities-in-apps) nesta página.

Quando essa configuração de política é selecionada, os usuários atribuídos à política devem selecionar e aplicar um rótulo de confidencialidade sob os seguintes cenários:

- Para o cliente de rotulação unificado de proteção de informações do Azure:
    - Para documentos (Word, Excel, PowerPoint): quando um documento sem rótulo é salvo ou os usuários fecham o documento.
    - Para emails (Outlook): no momento, os usuários enviam uma mensagem sem rótulo.

- Para rotular interno para aplicativos do Office:
    - Para documentos ((Word, Excel, PowerPoint): quando um documento sem rótulo é aberto ou salvo.
    - Para emails (Outlook): no momento, os usuários enviam uma mensagem de email sem rótulo.

Informações adicionais para rotulamento interno:

- Quando os usuários são solicitados a adicionar um rótulo de confidencialidade porque eles abrem um documento sem rótulo, eles podem adicionar um rótulo ou optar por abrir o documento no modo somente leitura.

- Quando o rótulo obrigatório estiver em vigor, os usuários não poderão remover os rótulos de confidencialidade dos documentos, mas podem alterar um rótulo existente.

#### <a name="setting-different-visual-markings-for-word-excel-powerpoint-and-outlook"></a>Definição de marcações visuais diferentes para Word, Excel, PowerPoint e Outlook

Como variável adicional, você pode configurar marcações visuais por tipo de aplicativo do Office usando uma instrução de variável "If. app" na sequência de texto e identificar o tipo de aplicativo usando os valores **Word**, **Excel**, **PowerPoint** ou **Outlook**. Você também pode abreviar esses valores, o que será necessário se você quiser especificar mais de um na mesma instrução If. app.

> [!NOTE]
> Para fins de integridade, as instruções do Outlook são incluídas, embora atualmente com suporte apenas pelo cliente de rotulação unificado de proteção de informações do Azure.

Use a seguinte sintaxe:

```
${If.App.<application type>}<your visual markings text> ${If.End}
```

Da mesma forma que as outras marcações visuais dinâmicas, a sintaxe diferencia maiúsculas de minúsculas.

Exemplos:

- **Definir texto de cabeçalho somente para documentos do Word:**

    `${If.App.Word}This Word document is sensitive ${If.End}`

    Somente em cabeçalhos de documento do Word, o rótulo aplica o texto do cabeçalho "este documento do Word é confidencial". Nenhum texto de cabeçalho é aplicado a outros aplicativos do Office.

- **Definir texto de rodapé para Word, Excel e Outlook e texto de rodapé diferente para o PowerPoint:**

    `${If.App.WXO}This content is confidential. ${If.End}${If.App.PowerPoint}This presentation is confidential. ${If.End}`

    No Word, no Excel e no Outlook, o rótulo aplica o texto do rodapé "este conteúdo é confidencial". No PowerPoint, o rótulo aplica o texto do rodapé "esta apresentação é confidencial".

- **Definir texto de marca d' água específica para Word e PowerPoint e, em seguida, texto de marca d' água para Word, Excel e PowerPoint:**

    `${If.App.WP}This content is ${If.End}Confidential`

    No Word e PowerPoint, o rótulo aplica o texto de marca d' água "este conteúdo é confidencial". No Excel, o rótulo aplica o texto de marca d' água "confidencial". No Outlook, o rótulo não aplica qualquer texto de marca d' água porque as marcas d' água como marcas visuais não são suportadas pelo Outlook.


## <a name="end-user-documentation"></a>Documentação do usuário final

- [Aplicar rótulos de confidencialidade aos seus documentos e email no Office](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [Problemas conhecidos ao aplicar rótulos de confidencialidade aos arquivos do Office](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)
