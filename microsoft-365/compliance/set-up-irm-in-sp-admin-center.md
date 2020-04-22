---
title: Set up Information Rights Management (IRM) in SharePoint admin center
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 239ce6eb-4e81-42db-bf86-a01362fed65c
description: Saiba como usar o IRM do SharePoint Online por meio do Microsoft Azure Active Directory Rights Management Services (RMS) para proteger listas e bibliotecas de documentos do SharePoint.
ms.openlocfilehash: c981ceefde2cedb5f6c8731fd9a5ad9318174120
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634773"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a>Set up Information Rights Management (IRM) in SharePoint admin center

## <a name="introduction"></a>Introdução

No SharePoint Online, a proteção de IRM é aplicada aos arquivos na lista e nível de biblioteca. Antes que sua organização possa usar a proteção de IRM, você deve primeiro configurar o gerenciamento de direitos. O IRM depende do serviço de gerenciamento de direitos do Azure da proteção de informações do Azure para criptografar e atribuir restrições de uso. Alguns planos do Microsoft 365 incluem o Azure Rights Management, mas não todos. Para saber mais, leia [como os aplicativos e serviços do Office dão suporte ao Azure Rights Management](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support).
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a>Ativar o serviço IRM usando o centro de administração do SharePoint

Antes que sua organização possa proteger listas e bibliotecas do SharePoint, você deve primeiro ativar o serviço de gerenciamento de direitos para sua organização. Saiba como ver [ativando o Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/activate-service). Você deve usar uma conta corporativa ou de estudante que tenha privilégios de administrador global para habilitar o serviço de gerenciamento de direitos. Caso contrário, você não poderá usar os recursos do IRM com o SharePoint Online.
  
Após ativar o serviço de gerenciamento de direitos, entre no centro de administração do SharePoint para ativar o IRM.
  
1. Entre como administrador global ou administrador do SharePoint.
    
2. Selecione o ícone do inicializador de aplicativos ![Ícone do inicializador de aplicativos do Office 365](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) no canto superior esquerdo e escolha **Administração** para abrir o Centro de administração do Office 365. (Se você não vir o bloco administrador, você não tem permissões de administrador em sua organização.) 
    
3. No painel esquerdo, escolha **central** \> de administração **do SharePoint**.
    
4. No painel esquerdo, escolha **configurações**e, em seguida, escolha a **página Configurações clássicas**.
    
5. Na seção **Gerenciamento de direitos de informação (IRM)** , escolha **usar o serviço IRM especificado em sua configuração**e, em seguida, escolha **Atualizar configurações de IRM**. Depois de atualizar as configurações do IRM, as pessoas em sua organização podem começar a usar o IRM em suas listas e bibliotecas de documentos do SharePoint. No entanto, as opções para fazer isso pode levar até uma hora para que apareçam em configurações de biblioteca e configurações de lista.
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a>Habilitar o IRM para bibliotecas de documentos e listas do SharePoint
<a name="__toc220831191"> </a>

Após atualizar as configurações do IRM, os proprietários do site podem proteger o IRM de suas listas e bibliotecas de documentos do SharePoint. Para obter mais informações, consulte [aplicar o gerenciamento de direitos de informação a uma lista ou biblioteca](apply-irm-to-a-list-or-library.md).
  
Quando os proprietários de site habilitam o IRM para uma lista ou biblioteca, eles podem proteger qualquer tipo de arquivo com suporte nessa lista ou biblioteca. Quando o IRM está habilitado para uma biblioteca, o gerenciamento de direitos se aplica a todos os arquivos nessa biblioteca. Quando você habilita o IRM para uma lista, o gerenciamento de direitos aplica-se somente aos arquivos anexados a itens de lista, e não aos itens de lista reais.
  
Quando as pessoas baixam arquivos em uma lista ou biblioteca habilitada para IRM, os arquivos são criptografados para que apenas pessoas autorizadas possam exibi-los. Cada arquivo gerenciado por direitos também contém uma licença de publicação que impõe restrições às pessoas que exibem o arquivo. As restrições típicas incluem tornar um arquivo somente leitura, desabilitar a cópia de texto, impedir que as pessoas salvem uma cópia local e impedindo que as pessoas imprimam o arquivo. Os programas cliente que podem ler tipos de arquivo com suporte para IRM usam a licença de publicação dentro do arquivo gerenciado por direitos para impor essas restrições. É assim que um arquivo gerenciado por direitos mantém sua proteção mesmo depois de ser baixado. Para habilitar o IRM em uma lista ou biblioteca, confira [aplicar o gerenciamento de direitos de informação a uma lista ou biblioteca](apply-irm-to-a-list-or-library.md).
  
Você não pode criar ou editar documentos em uma biblioteca habilitada para IRM usando o Office em um navegador. Em vez disso, uma pessoa de cada vez pode baixar e editar arquivos criptografados por IRM. Use check-in e check-out para gerenciar a *coautoria* ou a criação de vários usuários. 
  
Ao baixar um arquivo PDF de uma biblioteca protegida por IRM, o Microsoft 365 cria um arquivo PDF protegido. A extensão do arquivo não será alterada, mas o arquivo estará protegido. Para exibir este arquivo, você precisará do Azure Information Protection Viewer, o cliente completo de proteção de informações do Azure ou outro aplicativo que ofereça suporte à exibição de arquivos PDF protegidos. 
  
O SharePoint Online oferece suporte à criptografia dos seguintes tipos de arquivo:
  
- PDF
    
- Os formatos de arquivo 97-2003 para os seguintes programas do Microsoft Office: Word, Excel e PowerPoint
    
- Formatos do Office Open XML para os seguintes programas do Microsoft Office: Word, Excel e PowerPoint
    
- O formato XML Paper Specification (XPS)
 
> [!NOTE]
> A proteção de IRM não pode ser aplicada a documentos protegidos (como arquivos PDF assinados digitalmente), pois o SharePoint precisa abrir o documento durante o carregamento. 

## <a name="next-steps"></a>Próximas etapas
<a name="__toc220831191"> </a>

Depois de habilitar o IRM para o SharePoint Online, você pode começar a aplicar o gerenciamento de direitos às listas e bibliotecas. Para obter informações, consulte [aplicar o gerenciamento de direitos de informação a uma lista ou biblioteca](apply-irm-to-a-list-or-library.md).
  
O novo cliente de sincronização do OneDrive para Windows agora oferece suporte à sincronização de bibliotecas de documentos do SharePoint protegidas por IRM e locais do OneDrive (desde que a configuração de IRM da biblioteca não esteja definida para expirar direitos de acesso de documento). Para obter mais informações ou para começar a implantar o novo cliente de sincronização, consulte [implantar o novo cliente de sincronização do onedrive para Windows](https://support.office.com/article/3f3a511c-30c6-404a-98bf-76f95c519668).
  
[Início da página](#introduction)  
