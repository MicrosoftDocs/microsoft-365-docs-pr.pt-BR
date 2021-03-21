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
ms.openlocfilehash: 68db84118ac8ccd7c734152aa28816db819198f7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919397"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a>Configurar o IRM (Gerenciamento de Direitos de Informação) no centro de administração do SharePoint

No SharePoint Online, a proteção de IRM é aplicada a arquivos nos níveis de biblioteca e lista. Para que a sua organização possa usar a proteção de IRM, primeiro configure o Gerenciamento de Direitos. O IRM conta com o serviço da Azure Rights Management da Proteção de Informações do Azure para criptografar e atribuir restrições de uso. Alguns planos do Microsoft 365 incluem o Gerenciamento de Direitos do Azure, mas não todos. Para saber mais, leia [Como aplicativos e serviços do Office suportam o Gerenciamento de Direitos do Azure.](/azure/information-protection/understand-explore/office-apps-services-support)
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a>Ativar o serviço de IRM usando o Centro de administração do SharePoint

Antes que sua organização possa proteger listas e bibliotecas do SharePoint protegidas por IRM, primeiro você deve ativar o serviço de Gerenciamento de Direitos para sua organização. Para saber como ver [Ativando o Gerenciamento de Direitos do Azure](/information-protection/deploy-use/activate-service). Você deve usar uma conta de estudante ou de trabalho que tenha privilégios globais de administrador para habilitar o serviço de Gerenciamento de Direitos. Caso contrário, você não poderá usar recursos de IRM com o SharePoint Online.
  
Depois de ativar o serviço de Gerenciamento de Direitos, entre no Centro de administração do SharePoint para ativar o IRM.
  
1. Entre como administrador global ou administrador do SharePoint.
    
2. Selecione o ícone do inicializador de aplicativos ![Ícone do inicializador de aplicativos do Office 365](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) no canto superior esquerdo e escolha **Administração** para abrir o Centro de administração do Office 365. (Se você não vir o painel Administrador, não terá permissões de administrador em sua organização.) 
    
3. No painel esquerdo, escolha **Centros de administração** do \> **SharePoint**.
    
4. No painel esquerdo, escolha **configurações** e escolha **a página de configurações clássicas.**
    
5. Na seção Gerenciamento de Direitos de Informação **(IRM),** escolha Usar o serviço **irm** especificado em sua configuração e, em seguida, escolha **Atualizar Configurações do IRM**. Depois de atualizar as configurações do IRM, as pessoas em sua organização podem começar a usar o IRM em suas listas do SharePoint e bibliotecas de documentos. No entanto, as opções para fazer isso podem levar até uma hora para aparecer em Configurações de Biblioteca e Configurações de Lista.
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a>Listas e bibliotecas de documentos do SharePoint habilitados para IRM
<a name="__toc220831191"> </a>

Depois de atualizar as configurações do IRM, os proprietários de sites podem proteger suas listas do SharePoint e bibliotecas de documentos. Para obter mais informações, [consulte Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).
  
Quando os proprietários de sites habilitam o IRM para uma lista ou biblioteca, eles podem proteger quaisquer tipos de arquivo com suporte nessa lista ou biblioteca. Quando o IRM está habilitado para uma biblioteca, o gerenciamento de direitos se aplica a todos os arquivos nessa biblioteca. Quando você habilita o IRM para uma lista, o gerenciamento de direitos se aplica somente a arquivos anexados a itens de lista, não aos itens de lista reais.
  
Quando as pessoas baixam arquivos em uma lista ou biblioteca habilitada para IRM, os arquivos são criptografados para que somente as pessoas autorizadas possam exibi-los. Cada arquivo gerenciado por direitos também contém uma licença de emissão que impõe restrições às pessoas que visualizam o arquivo. As restrições típicas incluem fazer um arquivo somente leitura, desabilitar a cópia do texto, impedir que as pessoas salvam uma cópia local e impedir que as pessoas imprimim o arquivo. Os programas cliente que podem ler tipos de arquivo com suporte para IRM usam a licença de emissão dentro do arquivo gerenciado por direitos para impor essas restrições. É assim que um arquivo gerenciado por direitos mantém sua proteção mesmo depois de ser baixado. Para habilitar o IRM em uma lista ou biblioteca, consulte [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).
  
Não é possível criar ou editar documentos em uma biblioteca habilitada para IRM usando o Office em um navegador. Em vez disso, uma pessoa por vez pode baixar e editar arquivos criptografados por IRM. Use o check-in e o check-out para gerenciar  *a coautor*  ou a autoria em vários usuários. 
  
Quando você baixa um arquivo PDF de uma biblioteca protegida por IRM, o Microsoft 365 cria um arquivo PDF protegido. A extensão do arquivo não mudará, mas o arquivo está protegido. Para exibir esse arquivo, você precisará do visualizador da Proteção de Informações do Azure, do cliente completo da Proteção de Informações do Azure ou de outro aplicativo que suporte a exibição de arquivos PDF protegidos. 
  
O SharePoint Online dá suporte à criptografia dos seguintes tipos de arquivo:
  
- PDF
    
- Os formatos de arquivo 97-2003 para os seguintes programas Microsoft Office: Word, Excel e PowerPoint
    
- Os formatos do Office Open XML para os seguintes programas Microsoft Office: Word, Excel e PowerPoint
    
- O formato XPS (Especificação de Papel XML)
 
> [!NOTE]
> A proteção de IRM não pode ser aplicada a documentos protegidos (como arquivos PDF assinados digitalmente), pois o SharePoint precisa abrir o documento ao carregar. 

## <a name="next-steps"></a>Próximas etapas
<a name="__toc220831191"> </a>

Depois de habilitar o IRM para o SharePoint Online, você pode começar a aplicar o gerenciamento de direitos a listas e bibliotecas. Para obter informações, [consulte Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).
  
O novo cliente de sincronização do OneDrive para Windows agora dá suporte à sincronização de bibliotecas de documentos do SharePoint protegidas por IRM e locais do OneDrive (desde que a configuração do IRM para a biblioteca não seja definida para expirar direitos de acesso a documentos). Para obter mais informações ou para começar a implantar o novo cliente de sincronização, consulte [Deploy the new OneDrive sync client for Windows](/onedrive/deploy-on-windows).
  
[Início da página](set-up-irm-in-sp-admin-center.md)