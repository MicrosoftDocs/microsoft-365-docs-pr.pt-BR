---
title: Configurar o IRM (Gerenciamento de Direitos de Informação) no centro de administração do SharePoint
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 33e5a72ea1d0733656379bc4efdca7dd14f78cb1
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819191"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a>Configurar o IRM (Gerenciamento de Direitos de Informação) no centro de administração do SharePoint

No SharePoint Online, a proteção de IRM é aplicada a arquivos nos níveis de biblioteca e lista. Para que a sua organização possa usar a proteção de IRM, primeiro configure o Gerenciamento de Direitos. O IRM conta com o serviço da Azure Rights Management da Proteção de Informações do Azure para criptografar e atribuir restrições de uso. Alguns planos do Microsoft 365 incluem o Azure Rights Management, mas nem todos. Para saber mais, leia [Como os aplicativos e serviços do Office são suportados pelo Azure Rights Management.](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support)
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a>Ativar o serviço IRM usando o Centro de administração do SharePoint

Antes que sua organização possa proteger listas e bibliotecas do SharePoint com IRM, primeiro você deve ativar o serviço gerenciamento de direitos para sua organização. Para saber como ver [a ativação do Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/activate-service). Você deve usar uma conta comercial ou de estudante que tenha privilégios de administrador global para habilitar o serviço Gerenciamento de Direitos. Caso contrário, você não poderá usar os recursos do IRM com o SharePoint Online.
  
Depois de ativar o serviço de Gerenciamento de Direitos, entre no centro de administração do SharePoint para ativar o IRM.
  
1. Entre como um administrador global ou administrador do SharePoint.
    
2. Selecione o ícone do inicializador de aplicativos ![Ícone do inicializador de aplicativos do Office 365](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) no canto superior esquerdo e escolha **Administração** para abrir o Centro de administração do Office 365. (Se você não vir o painel Administrador, você não tem permissões de administrador em sua organização.) 
    
3. No painel esquerdo, escolha Centros **de administração do** \> **SharePoint.**
    
4. No painel esquerdo, escolha as **configurações** e escolha a **página de configurações clássicas.**
    
5. Na seção Gerenciamento de Direitos de **Informação (IRM),** escolha Usar o serviço **IRM** especificado em sua configuração e, em seguida, escolha Atualizar Configurações **do IRM.** Depois de atualizar as configurações do IRM, as pessoas em sua organização podem começar a usar o IRM em suas listas e bibliotecas de documentos do SharePoint. No entanto, as opções para fazer isso podem levar até uma hora para aparecer em Configurações de Biblioteca e Configurações de Lista.
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a>Listas e bibliotecas de documentos do SharePoint habilitadas para IRM
<a name="__toc220831191"> </a>

Depois de atualizar as configurações do IRM, os proprietários de site podem proteger suas listas e bibliotecas de documentos do SharePoint com o IRM. Para obter mais informações, [consulte Aplicar o Gerenciamento de Direitos de Informação a uma lista ou biblioteca.](apply-irm-to-a-list-or-library.md)
  
Quando os proprietários de site habilitam o IRM para uma lista ou biblioteca, eles podem proteger todos os tipos de arquivo com suporte nessa lista ou biblioteca. Quando o IRM está habilitado para uma biblioteca, o gerenciamento de direitos se aplica a todos os arquivos nessa biblioteca. Quando você habilita o IRM para uma lista, o gerenciamento de direitos se aplica somente aos arquivos anexados a itens de lista, não aos itens de lista reais.
  
Quando as pessoas baixam arquivos em uma lista ou biblioteca habilitada para IRM, os arquivos são criptografados para que somente pessoas autorizadas possam exibi-los. Cada arquivo com direitos gerenciados também contém uma licença de emissão que impõe restrições às pessoas que visualizam o arquivo. As restrições típicas incluem tornar um arquivo somente leitura, desabilitar a cópia de texto, impedir que as pessoas salvam uma cópia local e impedir que as pessoas imprimi-lo. Programas cliente que podem ler tipos de arquivo com suporte para IRM usam a licença de emissão no arquivo com direitos gerenciados para impor essas restrições. É assim que um arquivo com direitos gerenciados mantém sua proteção mesmo depois de ser baixado. Para habilitar o IRM em uma lista ou biblioteca, consulte Aplicar Gerenciamento de Direitos de [Informação a uma lista ou biblioteca.](apply-irm-to-a-list-or-library.md)
  
Você não pode criar ou editar documentos em uma biblioteca habilitada para IRM usando o Office em um navegador. Em vez disso, uma pessoa de cada vez pode baixar e editar arquivos criptografados por IRM. Use check-in e check-out para gerenciar  *a coautor*  ou a autoria em vários usuários. 
  
Quando você baixa um arquivo PDF de uma biblioteca protegida por IRM, o Microsoft 365 cria um arquivo PDF protegido. A extensão do arquivo não mudará, mas o arquivo está protegido. Para exibir esse arquivo, você precisará do visualizador da Proteção de Informações do Azure, do cliente completo da Proteção de Informações do Azure ou de outro aplicativo que suporte a exibição de arquivos PDF protegidos. 
  
O SharePoint Online oferece suporte à criptografia dos seguintes tipos de arquivo:
  
- PDF
    
- Os formatos de arquivo 97-2003 para os seguintes programas do Microsoft Office: Word, Excel e PowerPoint
    
- Os formatos do Office Open XML para os seguintes programas do Microsoft Office: Word, Excel e PowerPoint
    
- O formato XML Paper Specification (XPS)
 
> [!NOTE]
> A proteção por IRM não pode ser aplicada a documentos protegidos (como arquivos PDF assinados digitalmente), pois o SharePoint precisa abrir o documento ao carregar. 

## <a name="next-steps"></a>Próximas etapas
<a name="__toc220831191"> </a>

Depois de habilitar o IRM para o SharePoint Online, você poderá começar a aplicar o gerenciamento de direitos a listas e bibliotecas. Para obter informações, [consulte Aplicar o Gerenciamento de Direitos de Informação a uma lista ou biblioteca.](apply-irm-to-a-list-or-library.md)
  
O novo cliente de sincronização do OneDrive para Windows agora dá suporte à sincronização de bibliotecas de documentos do SharePoint protegidas por IRM e locais do OneDrive (desde que a configuração do IRM para a biblioteca não seja definida para expirar direitos de acesso a documentos). Para saber mais ou começar a implantar o novo cliente de sincronização, confira Implantar o novo cliente de sincronização do [OneDrive para Windows.](https://docs.microsoft.com/onedrive/deploy-on-windows)
  
[Início da página](set-up-irm-in-sp-admin-center.md)
