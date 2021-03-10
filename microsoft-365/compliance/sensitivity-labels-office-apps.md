---
title: Gerenciar rótulos de confidencialidade em aplicativos do Office
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
description: Informações para os administradores de IT gerenciarem rótulos de sensibilidade em aplicativos do Office para área de trabalho, celular e Web.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1aa710939a805453a73db38eb93e4ceb90bc25d7
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597161"
---
# <a name="manage-sensitivity-labels-in-office-apps"></a>Gerenciar rótulos de confidencialidade em aplicativos do Office

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

Quando você [](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) publica rótulos de sensibilidade do Centro de conformidade do Microsoft 365 ou centro de rotulagem equivalente, eles começam a aparecer em aplicativos do Office para que os usuários classifiquem e protejam os dados à medida que são criados ou editados.

Use as informações deste artigo para ajudá-lo a gerenciar rótulos de sensibilidade com êxito em aplicativos do Office. Por exemplo, identifique as versões mínimas de aplicativos que você precisa para dar suporte à rotulagem integrado e entenda as interações com o cliente de rotulagem unificada da Proteção de Informações do Azure e a compatibilidade com outros aplicativos e serviços.

## <a name="labeling-client-for-desktop-apps"></a>Cliente de rotulagem para aplicativos da área de trabalho

Para usar rótulos de sensibilidade integrados aos aplicativos da área de trabalho do Office para Windows e Mac, você deve usar uma edição de assinatura do Office. Esse cliente de rotulagem não dá suporte a edições autônomas do Office, como Office 2016 ou Office 2019.

Para usar rótulos de sensibilidade com essas edições autônomas do Office em computadores Windows, instale o cliente de rotulagem unificada da Proteção de Informações do [Azure.](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>Suporte para recursos de rótulo de sensibilidade em aplicativos

Para cada recurso, as tabelas a seguir listam a versão mínima do Office que você precisa para dar suporte a rótulos de sensibilidade usando rótulos integrados. Ou, se a funcionalidade de rótulo estiver em visualização pública ou em revisão para uma versão futura. Use o [roteiro do Microsoft 365](https://aka.ms/MIPC/Roadmap) para obter detalhes sobre versões futuras.

As novas versões dos aplicativos do Office são disponibilizadas em horários diferentes para canais de atualização diferentes. Para obter mais informações, incluindo como configurar seu canal de atualização para que você possa testar um novo recurso de rotulagem no qual você está interessado, consulte [Overview of update channels for Microsoft 365 Apps](https://docs.microsoft.com/DeployOffice/overview-update-channels). Os novos recursos que estão na visualização privada não estão incluídos na tabela, mas você pode ser capaz de participar dessas visualizações nomeando sua organização para o programa de visualização privada da Proteção de Informações da [Microsoft.](https://aka.ms/mip-preview)

> [!NOTE]
> Os nomes dos canais de atualização para aplicativos do Office foram alterados recentemente. Por exemplo, o Canal Mensal agora é o Canal Atual e o Office Insider agora é o Canal Beta. Para obter mais informações, consulte [Changes to update channels for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/update-channels-changes).

Office para iOS e Office para Android: os rótulos de sensibilidade são integrados ao [aplicativo do Office.](https://www.microsoft.com/en-us/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/)

Recursos adicionais estão disponíveis quando você instala o cliente de rotulagem unificada da Proteção de Informações do Azure, que é executado somente em computadores Windows. Para obter esses detalhes, [consulte Comparar os clientes de rotulagem para computadores Windows](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers).

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Recursos de rótulo de sensibilidade no Word, Excel e PowerPoint

Os números listados são a versão mínima do aplicativo do Office necessária para cada recurso.

|Recursos                                                                                                        |Windows |Mac |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[Aplicar, alterar ou remover rótulo manualmente](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16,21+     | 2.21+ | 16.0.11231+ | [Sim - aceitação](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Aplicar um rótulo padrão](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16,21+     | 2.21+ | 16.0.11231+ | [Sim - aceitação](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|[Exigir uma justificativa para alterar um rótulo](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16,21+     | 2.21+ | 16.0.11231+ | [Sim - aceitação](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Fornecer link de ajuda para uma página de ajuda personalizada](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16,21+     | 2.21+ | 16.0.11231+ | [Sim - aceitação](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Marcar o conteúdo](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16,21+     | 2.21+ | 16.0.11231+ | [Sim - aceitação](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Marcações dinâmicas com variáveis](#dynamic-markings-with-variables)                                              | 2010+           | 16,42+     | 2,42+ | 16.0.13328+ | Em revisão |
|[Atribuir permissões agora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16,21+     | 2.21+ | 16.0.11231+ | [Sim - aceitação](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Permitir que usuários atribuam permissões](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |2004+ | 16,35+   | Em revisão   | Em revisão         | Em revisão                                                        |
|[Auditar atividades de usuário relacionadas a rótulos](data-classification-activity-explorer.md)                      | 2011+ | 16,43+ | Lançamento: 2,46+ | Lançamento: 16.0.13628+ | Sim <sup>\*</sup>                                                        |
|[Exigir que os usuários apliquem um rótulo a seus emails e documentos](#require-users-to-apply-a-label-to-their-email-and-documents)   | Lançamento: 2101+             | Lançamento: 16,45+         | Implantando na visualização: [Canal Beta](https://office.com/insider) | Lançamento: 16.0.13628+ | Em revisão                                            
|[Aplicar um rótulo de confidencialidade automaticamente ao conteúdo](apply-sensitivity-label-automatically.md)                    | 2009+                                  | Lançamento: 16,44+ | Em revisão | Em revisão | [Sim - aceitação](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Suporte a coautor e o AutoSave](sensitivity-labels-coauthoring.md) para documentos rotulados e criptografados | Visualização: [Canal Atual (Visualização)](https://office.com/insider) | Visualização: [Canal Beta](https://office.com/insider) | Em revisão | Em revisão | [Sim - aceitação](sensitivity-labels-sharepoint-onedrive-files.md) |
|

**Nota de rodapé:**

<sup>\*</sup> Atualmente, não inclui texto de justificativa para remover um rótulo ou diminuir o nível de classificação

### <a name="sensitivity-label-capabilities-in-outlook"></a>Recursos de rótulo de sensibilidade no Outlook

Os números listados são a versão mínima do aplicativo do Office necessária para cada recurso.

|Recursos                                                                                                        |Outlook para Windows |Outlook para Mac |Outlook no iOS |Outlook no Android |Outlook na Web |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[Aplicar, alterar ou remover rótulo manualmente](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16,21+                 | 4.7.1+         | 4.0.39+           | Sim               |
|[Aplicar um rótulo padrão](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16,21+                 | 4.7.1+         | 4.0.39+           | Sim               |
|[Exigir uma justificativa para alterar um rótulo](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16,21+                 | 4.7.1+         | 4.0.39+           | Sim               |
|[Fornecer link de ajuda para uma página de ajuda personalizada](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16,21+                 | 4.7.1+         | 4.0.39+           | Sim               |
|[Marcar o conteúdo](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+                     | 16,21+                 | 4.7.1+         | 4.0.39+           | Sim               |
|[Marcações dinâmicas com variáveis](#dynamic-markings-with-variables)                                              | Em revisão                     | Em revisão                 | Em revisão         | Em revisão           | Em revisão               |
|[Atribuir permissões agora](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16,21+                 | 4.7.1+         | 4.0.39+           | Sim               |
|[Permitir que usuários atribuam permissões](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16,21+                 | 4.7.1+         | 4.0.39+           | Sim               |
|[Exigir que os usuários apliquem um rótulo a seus emails e documentos](#require-users-to-apply-a-label-to-their-email-and-documents)   | Lançamento: 2101+                        | 16,43+ <sup>\*</sup>                    | Em revisão            | Em revisão                | Sim                |
|[Auditar atividades de usuário relacionadas a rótulos](data-classification-activity-explorer.md) | 2011+ | Em revisão | Em revisão           | Em revisão               | Em revisão |
|[Aplicar um rótulo de confidencialidade automaticamente ao conteúdo](apply-sensitivity-label-automatically.md)                    | 2009+                      | 16,44+ <sup>\*</sup>                    | Em revisão           | Em revisão               | Sim |
|

**Nota de rodapé:**

<sup>\*</sup> Requer o [novo Outlook para Mac](https://support.microsoft.com/office/the-new-outlook-for-mac-6283be54-e74d-434e-babb-b70cefc77439)


## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Cliente de rotulagem integrado do Office e outras soluções de rotulagem

O cliente de rotulagem interna do Office baixa rótulos de sensibilidade e configurações de política de rótulo de sensibilidade dos seguintes centros de administração:

- Centro de conformidade do Microsoft 365
- Centro de segurança do Microsoft 365
- Centro de Segurança e Conformidade do Office 365

Para usar o cliente de rotulagem interna do [](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) Office, você deve ter uma ou mais políticas de rótulo publicadas para usuários de um dos centros de administração listados e uma versão com suporte [do Office](#support-for-sensitivity-label-capabilities-in-apps).

Se ambas as condições são atendidas, mas você precisa desativar o cliente de rotulagem interna do Office, use a seguinte configuração de Política de Grupo:

1. Navegue **até Configuração do Usuário/Modelos Administrativos/Microsoft Office 2016/Configurações de Segurança.**

2. Definir **Usar o recurso de Sensibilidade no Office para aplicar e exibir** rótulos de sensibilidade **a 0**. 
 
Implante essa configuração usando a Política de Grupo ou usando o serviço de [política de nuvem do Office.](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service) A configuração entra em vigor quando os aplicativos do Office são reiniciados.

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Cliente de rotulagem integrado do Office e o cliente de Proteção de Informações do Azure

Se os usuários têm um dos clientes de Proteção de Informações do Azure[instalados](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) ( cliente de rotulagem unificada ou cliente clássico [),](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)por padrão, o cliente de rotulagem interna é desligado em seus aplicativos do Office. 

Para usar a rotulagem interna em vez do cliente de Proteção de Informações do Azure para aplicativos do Office, use as instruções da seção anterior, mas de acordo com a configuração de Política de Grupo Use o recurso Sensibilidade no **Office** para aplicar e exibir rótulos de sensibilidade **como 1**. 

Como alternativa, desabilite ou remova o Office Add-in, **Proteção de Informações do Azure.** Esse método é adequado para um único computador e testes ad hoc. Para obter instruções, [consulte Exibir, gerenciar e instalar os complementos em programas do Office.](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d) 

Quando você desabilita ou remove esse Complemento do Office, o cliente de Proteção de Informações do Azure permanece instalado para que você possa continuar rotular arquivos fora de seus aplicativos do Office. Por exemplo, usando o Explorador de Arquivos ou o PowerShell.

Para obter informações sobre quais recursos são suportados pelos clientes da Proteção de Informações do Azure e o cliente de rotulagem integrado do Office, consulte Choose your [Windows labeling solution](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-your-windows-labeling-solution) from the Azure Information Protection documentation.

## <a name="office-file-types-supported"></a>Tipos de arquivo do Office com suporte

Os aplicativos do Office que possuem rótulos integrados para arquivos do Word, Excel e PowerPoint suportam o formato Open XML (como .docx e .xlsx), mas não o formato Microsoft Office 97-2003 (como .doc e .xls), Open Document Format (como .odt e .ods) ou outros formatos. Quando um tipo de arquivo não tem suporte para rótulos integrados, o botão **Confidencialidade** não está disponível no aplicativo do Office.

O cliente de rotulagem unificada da Proteção de Informações do Azure dá suporte ao formato Open XML e ao formato Microsoft Office 97-2003. Para obter mais informações, consulte Tipos de arquivo suportados pelo cliente de rotulagem unificada da Proteção de Informações do [Azure](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-file-types) a partir do guia de administração desse cliente.

Para outras soluções de rotulagem, verifique a documentação dos tipos de arquivo suportados.

## <a name="protection-templates-and-sensitivity-labels"></a>Modelos de proteção e rótulos de sensibilidade

Modelos de proteção definidos pelo administrador , como aqueles que você define para a Criptografia de Mensagens do Office 365, não são visíveis nos [aplicativos](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)do Office quando você está usando rotulagem in-loco. Essa experiência simplificada reflete que não é necessário selecionar um modelo de proteção, pois as mesmas configurações são incluídas com rótulos de sensibilidade que têm criptografia habilitada.

Se você precisar converter modelos de proteção existentes em rótulos, use o portal do Azure e as seguintes instruções: Para converter modelos [em rótulos](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels).

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>Opções de Gerenciamento de Direitos de Informação (IRM) e rótulos de sensibilidade

Os rótulos de sensibilidade que você configura para aplicar criptografia removem a complexidade dos usuários para especificar suas próprias configurações de criptografia. Em muitos aplicativos do Office, essas configurações de criptografia individuais ainda podem ser configuradas manualmente pelos usuários usando opções de Gerenciamento de Direitos de Informação (IRM). Por exemplo, para aplicativos windows:

- Para um documento: **Informações de arquivo** proteger o documento  >    >    >  **restringem o acesso**
- para um email: na guia **Opções** > **Encrypt** 
  
Quando os usuários rotulam inicialmente um documento ou email, eles sempre podem substituir as configurações do rótulo por suas próprias configurações de criptografia. Por exemplo:

- Um usuário aplica o rótulo **Confidencial \ Todos** os Funcionários a um documento e esse rótulo é configurado para aplicar configurações de criptografia para todos os usuários na organização. Esse usuário configura manualmente as configurações do IRM para restringir o acesso a um usuário fora da sua organização. O resultado final é um documento chamado **Confidencial \** Todos os Funcionários e criptografado, mas os usuários em sua organização não podem abri-lo conforme o esperado.

- Um usuário aplica o rótulo Confidencial \ Somente **Destinatários** a um email e esse email é configurado para aplicar a configuração de criptografia **de Não Encaminhar**. Esse usuário configura manualmente as configurações do IRM para que o email não seja restrito. O resultado final é que o email pode ser encaminhado por destinatários, apesar de ter o rótulo **Confidencial \ Somente Destinatários.**

- Um usuário aplica o **rótulo Geral** a um documento, e esse rótulo não está configurado para aplicar criptografia. Esse usuário configura manualmente as configurações do IRM para restringir o acesso ao documento. O resultado final é um documento rotulado de **Geral,** mas que também aplica criptografia para que alguns usuários não possam abri-la conforme o esperado.

Se o documento ou o email já estiver rotulado, um usuário poderá fazer qualquer uma dessas ações se o conteúdo ainda não estiver criptografado ou se ele tiver o direito de uso [Exportar](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) ou Controle Total. 

Para obter uma experiência de rótulo mais consistente com relatórios significativos, forneça rótulos e orientações apropriados para que os usuários apliquem apenas rótulos para proteger documentos. Por exemplo:

- Para casos de exceção em que os usuários devem atribuir suas próprias permissões, forneça rótulos que permitem que os usuários [atribuam suas próprias permissões.](encryption-sensitivity-labels.md#let-users-assign-permissions) 

- Em vez de usuários removerem a criptografia manualmente após selecionar um rótulo que aplique criptografia, forneçam uma alternativa de sub-rótulo quando os usuários precisam de um rótulo com a mesma classificação, mas sem criptografia. Como:
    - **Confidencial \ Todos os Funcionários**
    - **Confidencial \ Qualquer Pessoa (sem criptografia)**

> [!NOTE]
> Se os usuários removerem a criptografia manualmente de um documento rotulado armazenado no SharePoint ou no OneDrive e você tiver habilitado rótulos de sensibilidade para arquivos do Office no SharePoint e [no OneDrive,](sensitivity-labels-sharepoint-onedrive-files.md)a criptografia de rótulo será restaurada automaticamente na próxima vez que o documento for acessado ou baixado. 


## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>Aplicar rótulos de sensibilidade a arquivos, emails e anexos

Os usuários podem aplicar apenas um rótulo por vez para cada documento ou email.

Quando você rotula uma mensagem de email que tenha anexos, os anexos herdarão o rótulo somente se o rótulo que você aplicar à mensagem de email aplicar criptografia e o anexo for um documento do Office ainda não estiver criptografado. Como o rótulo herdado aplica criptografia, o anexo é criptografado recentemente.

Um anexo não herda os rótulos da mensagem de email quando o rótulo aplicado à mensagem de email não aplica criptografia ou o anexo já está criptografado.

Exemplos de herança de rótulo, onde o rótulo **Confidencial** aplica criptografia e o rótulo **Geral** não aplica criptografia:

- Um usuário cria uma nova mensagem de email e aplica o **rótulo Confidencial** a essa mensagem. Em seguida, eles adicionam um documento do Word que não é rotulado ou criptografado. Como resultado da herança, o documento é recentemente rotulado **confidencial** e agora tem criptografia aplicada a partir desse rótulo.

- Um usuário cria uma nova mensagem de email e aplica o **rótulo Confidencial** a essa mensagem. Em seguida, eles adicionam um documento do Word rotulado **de Geral** e esse arquivo não é criptografado. Como resultado da herança, o documento é rotulado como **Confidencial** e agora tem a criptografia aplicada a partir desse rótulo.

## <a name="sensitivity-label-compatibility"></a>Compatibilidade de rótulo de sensibilidade

Com aplicativos iluminados por **RMS**: se você abrir um documento ou email rotulado e criptografado em um aplicativo iluminado por [RMS](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) que não suporta rótulos de sensibilidade, o aplicativo ainda impõe o gerenciamento de criptografia e direitos.

Com o cliente de Proteção de Informações do **Azure:** você pode exibir e alterar rótulos de sensibilidade aplicados a documentos e emails com o cliente de rotulagem integrado do Office usando o cliente de Proteção de Informações do Azure e o contrário.

**Com outras versões do Office**: qualquer usuário autorizado pode abrir documentos e emails rotulados em outras versões do Office. No entanto, você só pode exibir ou alterar o rótulo em versões suportadas do Office ou usando o cliente de Proteção de Informações do Azure. As versões do aplicativo do Office com suporte estão listadas na [seção anterior](#support-for-sensitivity-label-capabilities-in-apps).

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>Suporte para arquivos do SharePoint e do OneDrive protegidos por rótulos de sensibilidade

Para usar o cliente de rotulagem interna do Office com o Office na Web para documentos no SharePoint ou no OneDrive, certifique-se de ter habilitado rótulos de sensibilidade para arquivos do Office no SharePoint e [no OneDrive.](sensitivity-labels-sharepoint-onedrive-files.md)

## <a name="support-for-external-users-and-labeled-content"></a>Suporte para usuários externos e conteúdo rotulado

Quando você rotula um documento ou email, o rótulo é armazenado como metadados que incluem seu locatário e um GUID de rótulo. Quando um documento ou email rotulado é aberto por um aplicativo do Office que oferece suporte a rótulos de sensibilidade, os metadados são lidos e somente se o usuário pertence ao mesmo locatário, o rótulo é exibido em seu aplicativo. Por exemplo, para rótulos integrados para Word, PowerPoint e Excel, o nome do rótulo é exibido na barra de status. 

Isso significa que, se você compartilhar documentos com outra organização que usa nomes de rótulo diferentes, cada organização poderá aplicar e ver seu próprio rótulo aplicado ao documento. No entanto, os seguintes elementos de um rótulo aplicado são visíveis para usuários fora da sua organização:

- Marcações de conteúdo. Quando um rótulo aplica um header, rodapé ou marca d'água, eles são adicionados diretamente ao conteúdo e permanecem visíveis até que alguém o modifica ou exclui.

- O nome e a descrição do modelo de proteção subjacente de um rótulo que aplicou criptografia. Essas informações são exibidas em uma barra de mensagens na parte superior do documento, para fornecer informações sobre quem está autorizado a abrir o documento e seus direitos de uso para esse documento.

### <a name="sharing-encrypted-documents-with-external-users"></a>Compartilhamento de documentos criptografados com usuários externos

Além de restringir o acesso aos usuários em sua própria organização, você pode estender o acesso a qualquer outro usuário que tenha uma conta no Azure Active Directory. No entanto, se sua organização usar políticas de Acesso Condicional, consulte a [próxima seção](#conditional-access-policies) para considerações adicionais.

Todos os aplicativos do Office e outros aplicativos com [iluminação RMS](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) podem abrir documentos criptografados depois que o usuário tiver autenticado com êxito. 

Se os usuários externos não têm uma conta no Azure Active Directory, eles podem se autenticar usando contas de convidado em seu locatário. Essas contas de convidado também podem ser usadas para acessar documentos compartilhados no SharePoint ou no OneDrive quando você habilitar rótulos de sensibilidade para arquivos do Office no [SharePoint e no OneDrive](sensitivity-labels-sharepoint-onedrive-files.md):

- Uma opção é criar essas contas de convidado por conta própria. Você pode especificar qualquer endereço de email que esses usuários já usam. Por exemplo, seu endereço do Gmail.
    
    A vantagem dessa opção é que você pode restringir o acesso e os direitos a usuários específicos especificando seu endereço de email nas configurações de criptografia. A desvantagem é a sobrecarga de administração para a criação e coordenação da conta com a configuração do rótulo.

- Outra opção é usar a integração do SharePoint e do OneDrive com o [Azure AD B2B (Visualização)](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) para que as contas de convidado sejam criadas automaticamente quando seus usuários compartilharem links.
    
    A vantagem dessa opção é a sobrecarga administrativa mínima porque as contas são criadas automaticamente e a configuração de rótulo mais simples. Para esse cenário, você deve selecionar a opção de criptografia Adicionar qualquer usuário [autenticado](encryption-sensitivity-labels.md#requirements-and-limitations-for-add-any-authenticated-users) porque você não conhecerá os endereços de email antecipadamente. A desvantagem é que essa configuração não permite restringir o acesso e os direitos de uso a usuários específicos.

Os usuários externos também podem usar uma conta da Microsoft para abrir documentos criptografados quando usam o Windows e o Microsoft 365 Apps ( anteriormente aplicativos do[Office 365](https://docs.microsoft.com/deployoffice/name-change)) ou a edição autônoma do Office 2019. Mais recentemente com suporte para outras plataformas, as contas da Microsoft também têm suporte para abrir documentos criptografados no macOS (Microsoft 365 Apps, versão 16.42+), Android (versão 16.0.13029+) e iOS (versão 2.42+). Por exemplo, um usuário em sua organização compartilha um documento criptografado com um usuário fora da sua organização e as configurações de criptografia especificam um endereço de email do Gmail para o usuário externo. Esse usuário externo pode criar sua própria conta da Microsoft que usa seu endereço de email do Gmail. Em seguida, depois de entrar com essa conta, eles podem abrir o documento e editá-lo, de acordo com as restrições de uso especificadas para elas. Para ver um exemplo passo a passo desse cenário, consulte [Abrindo e editando o documento protegido.](https://docs.microsoft.com/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document)

> [!NOTE]
> O endereço de email da conta microsoft deve corresponder ao endereço de email especificado para restringir o acesso às configurações de criptografia.

Quando um usuário com uma conta da Microsoft abre um documento criptografado dessa forma, ele cria automaticamente uma conta de convidado para o locatário se uma conta de convidado com o mesmo nome ainda não existir. Quando a conta de convidado existe, ela pode ser usada para abrir documentos no SharePoint e no OneDrive usando o Office na Web, além de abrir documentos criptografados da área de trabalho e aplicativos do Office móveis com suporte.

No entanto, a conta de convidado automática não é criada imediatamente nesse cenário, devido à latência de replicação. Se você especificar endereços de email pessoais como parte das configurações de criptografia de rótulo, recomendamos que você crie contas de convidado correspondentes no Azure Active Directory. Em seguida, deixe esses usuários saberem que eles devem usar essa conta para abrir um documento criptografado da sua organização.

> [!TIP]
> Como você não pode ter certeza de que os usuários externos usarão um aplicativo cliente do Office com suporte, o compartilhamento de links do SharePoint e do OneDrive após a criação de contas de convidado (para usuários específicos) ou quando você usa a integração do SharePoint e do OneDrive com o [Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) (para qualquer usuário autenticado) é um método mais confiável para dar suporte à colaboração segura com usuários externos.

### <a name="conditional-access-policies"></a>Políticas de Acesso Condicional

Se sua organização implementou políticas de Acesso Condicional do [Azure Active Directory,](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)verifique a configuração dessas políticas. Se as políticas incluirem a Proteção de Informações do **Microsoft Azure** e a política se estender a usuários externos, esses usuários externos devem ter uma conta de convidado em seu locatário, mesmo que tenham uma conta do Azure AD em seu próprio locatário.

Sem essa conta de convidado, eles não podem abrir o documento criptografado e ver uma mensagem de erro. O texto da mensagem pode informá-los de que sua conta precisa ser adicionada como um usuário externo no locatário, com a instrução incorreta para este cenário de Sair e entrar novamente com uma conta de usuário do **Azure Active Directory** diferente.

Se você não puder criar e configurar contas de convidado em seu locatário para usuários externos que precisam abrir documentos criptografados por seus rótulos, remova a Proteção de Informações do Azure das políticas de Acesso Condicional ou exclua usuários externos das políticas.

Para obter mais informações sobre o Acesso Condicional e a Proteção de Informações do Azure, o serviço de criptografia usado por rótulos de sensibilidade, consulte a pergunta frequente, vejo que a Proteção de Informações do [Azure](https://docs.microsoft.com/azure/information-protection/faqs#i-see-azure-information-protection-is-listed-as-an-available-cloud-app-for-conditional-accesshow-does-this-work) está listada como um aplicativo de nuvem disponível para acesso condicional, como isso funciona?

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>Quando os aplicativos do Office aplicam a marcação de conteúdo e a criptografia

Os aplicativos do Office aplicam a marcação de conteúdo e a criptografia com um rótulo de sensibilidade de forma diferente, dependendo do aplicativo que você usa.

| App | Marcação de conteúdo | Criptografia |
| --- | --- | --- |
| Word, Excel, PowerPoint em todas as plataformas | Imediatamente | Imediatamente |
| Outlook para PC e Mac | Depois que o Exchange Online envia o email | Imediatamente |
| Outlook na Web, iOS e Android | Depois que o Exchange Online envia o email | Depois que o Exchange Online envia o email |
|

Soluções que aplicam rótulos de confidencialidade a arquivos fora dos aplicativos do Office fazem isso aplicando metadados de rotulagem ao arquivo. Nesse cenário, a marcação de conteúdo da configuração do rótulo não é inserida no arquivo, mas a criptografia é aplicada. 

Quando esses arquivos são abertos em um aplicativo da área de trabalho do Office, as marcações de conteúdo são aplicadas automaticamente pelo cliente de rotulagem unificada da Proteção de Informações do Azure. As marcações de conteúdo não são aplicadas automaticamente quando você usa rotulagem interna para aplicativos desktop, mobile ou Web.

Cenários que incluem a aplicação de um rótulo de sensibilidade fora dos aplicativos do Office incluem:

- O scanner, o Explorador de Arquivos e o PowerShell do cliente de rotulagem unificada da Proteção de Informações do Azure 

- Políticas de rotulagem automática para SharePoint e OneDrive

- Dados rotulados e criptografados exportados do Power BI

- Segurança no aplicativo na nuvem da Microsoft

Para esses cenários, usando seus aplicativos do Office, um usuário com rotulagem interna pode aplicar as marcações de conteúdo do rótulo removendo ou substituindo temporariamente o rótulo atual e, em seguida, aplicando o rótulo original.

### <a name="dynamic-markings-with-variables"></a>Marcações dinâmicas com variáveis

> [!IMPORTANT]
> Atualmente, nem todos os aplicativos em todas as plataformas suportam marcações dinâmicas de conteúdo que você pode especificar para seus headers, rodapés e marcas d'água. Para aplicativos que não suportam esse recurso, eles aplicam as marcações como o texto original especificado na configuração do rótulo, em vez de resolver as variáveis.
> 
> O cliente de rotulagem unificada da Proteção de Informações do Azure oferece suporte a marcações dinâmicas. Para rotular integrado ao Office, consulte as tabelas na seção [recursos](#support-for-sensitivity-label-capabilities-in-apps) nesta página.

Ao configurar um rótulo de sensibilidade para marcações de conteúdo, você pode usar as seguintes variáveis na cadeia de caracteres de texto para o seu header, rodapé ou marca d'água:

| Variável | Descrição | Exemplo quando o rótulo foi aplicado |
| -------- | ----------- | ------- |
| `${Item.Label}` | Nome de exibição de rótulo do rótulo aplicado| **Geral**|
| `${Item.Name}` | Nome do arquivo ou assunto de email do conteúdo que está sendo rotulado | **Sales.docx** |
| `${Item.Location}` | Caminho e nome do arquivo do documento que está sendo rotulado ou o assunto de email para um email que está sendo rotulado | **\\\Sales\2020\Q3\Report.docx**|
| `${User.Name}` | Nome de exibição do usuário que está aplicando o rótulo| **Richard Simone** |
| `${User.PrincipalName}` | Nome principal do usuário do Azure AD (UPN) do usuário que está aplicando o rótulo | **rsimone \@ contoso.com** |
| `${Event.DateTime}` | Data e hora em que o conteúdo é rotulado, no fuso horário local do usuário que aplica o rótulo | **10/08/2020 13:30** |

> [!NOTE]
> A sintaxe dessas variáveis é sensível a minúsculas.

#### <a name="setting-different-visual-markings-for-word-excel-powerpoint-and-outlook"></a>Definindo marcações visuais diferentes para Word, Excel, PowerPoint e Outlook

Como uma variável adicional, você pode configurar marcações visuais por tipo de aplicativo do Office usando uma instrução de variável "If.App" na cadeia de caracteres de texto e identificar o tipo de aplicativo usando os valores **Word**, **Excel**, **PowerPoint** ou **Outlook**. Você também pode abreviar esses valores, o que é necessário se quiser especificar mais de um na mesma instrução If.App.

> [!NOTE]
> Para obter a conclusão, as instruções para o Outlook estão incluídas, embora no momento sejam suportadas apenas pelo cliente de rotulagem unificada da Proteção de Informações do Azure.

Use a seguinte sintaxe:

```
${If.App.<application type>}<your visual markings text> ${If.End}
```

Assim como acontece com outras marcações visuais dinâmicas, a sintaxe é sensível a minúsculas.

Exemplos:

- **Definir texto de header somente para documentos do Word:**

    `${If.App.Word}This Word document is sensitive ${If.End}`

    Somente nos headers de documento do Word, o rótulo aplica o texto do header "Este documento do Word é sensível". Nenhum texto de header é aplicado a outros aplicativos do Office.

- **De definir texto do rodapé para Word, Excel e Outlook e texto de rodapé diferente para o PowerPoint:**

    `${If.App.WXO}This content is confidential. ${If.End}${If.App.PowerPoint}This presentation is confidential. ${If.End}`

    No Word, no Excel e no Outlook, o rótulo aplica o texto do rodapé "Esse conteúdo é confidencial". No PowerPoint, o rótulo aplica o texto do rodapé "Esta apresentação é confidencial".

- **De definir texto de marca d'água específico para Word e PowerPoint e, em seguida, texto de marca d'água para Word, Excel e PowerPoint:**

    `${If.App.WP}This content is ${If.End}Confidential`

    No Word e no PowerPoint, o rótulo aplica o texto de marca d'água "Este conteúdo é Confidencial". No Excel, o rótulo aplica o texto de marca d'água "Confidencial". No Outlook, o rótulo não aplica texto de marca d'água porque marcas d'água como marcações visuais não são suportadas para o Outlook.

## <a name="require-users-to-apply-a-label-to-their-email-and-documents"></a>Exigir que os usuários apliquem um rótulo a seus emails e documentos

> [!IMPORTANT]
> Também conhecido como rotulagem obrigatória, nem todos os aplicativos em todas as plataformas atualmente suportam a configuração de política de Exigir que os usuários apliquem um rótulo aos **seus emails e documentos.**
> 
> O cliente de rotulagem unificada da Proteção de Informações do [Azure](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app) dá suporte [](#support-for-sensitivity-label-capabilities-in-apps) à rotulagem obrigatória e à rotulagem em aplicativos do Office, consulte as tabelas na seção recursos nesta página.

Quando essa configuração de política é selecionada, os usuários atribuídos à política devem selecionar e aplicar um rótulo de sensibilidade nos seguintes cenários:

- Para o cliente de rotulagem unificada da Proteção de Informações do Azure:
    - Para documentos (Word, Excel, PowerPoint): quando um documento não rotulado é salvo ou os usuários fecham o documento.
    - Para emails (Outlook): no momento em que os usuários enviam uma mensagem não rotulada.

- Para rotular os aplicativos do Office integrados:
    - Para documentos ((Word, Excel, PowerPoint): quando um documento não rotulado é aberto ou salvo.
    - Para emails (Outlook): no momento em que os usuários enviam uma mensagem de email não rotulada.

Informações adicionais para rotulagem embutida:

- Quando os usuários são solicitados a adicionar um rótulo de sensibilidade porque eles abrem um documento sem rótulo, eles podem adicionar um rótulo ou optar por abrir o documento no modo somente leitura.

- Quando a rotulagem obrigatória está em vigor, os usuários não podem remover rótulos de sensibilidade dos documentos, mas podem alterar um rótulo existente.

Para obter orientações sobre quando usar essa configuração, consulte as informações sobre configurações [de política](sensitivity-labels.md#what-label-policies-can-do).

## <a name="end-user-documentation"></a>Documentação do usuário final

- [Aplicar rótulos de confidencialidade aos seus documentos e email no Office](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [Problemas conhecidos ao aplicar rótulos de confidencialidade aos arquivos do Office](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)
