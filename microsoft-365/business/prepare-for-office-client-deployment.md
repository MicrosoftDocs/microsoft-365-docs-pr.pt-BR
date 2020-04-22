---
title: Preparar a implantação do cliente do Office pela Microsoft 365 para empresas
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Saiba como instalar automaticamente os aplicativos do Office de 32 bits em computadores com Windows 10 e mantê-los atualizados.
ms.openlocfilehash: b5f01bc9bb10765929f3c6bdd5908e8b48a51a11
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633090"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a>Preparar a implantação do cliente do Office pela Microsoft 365 para empresas

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Preparar-se para instala automaticamente os aplicativos do Office em computadores de clientes

Você pode usar o Microsoft 365 for Business para instalar automaticamente os aplicativos do Office de 32 bits em computadores com Windows 10 e mantê-los atualizados com as atualizações.
  
A instalação automática funciona melhor se o computador do usuário final estiver no Windows 10 Business e:
  
- Não tiver aplicativos de área de trabalho do Office existentes (por exemplo, Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access e OneDrive).
    
    ou
    
- Tiver instalada uma versão Clique para Executar do Office.
    
Para determinar se você tem a versão Clique para Executar do Office, em qualquer aplicativo do Office, vá para **Arquivo** \> **Conta** ( **Conta do Office**). Se você vir **atualizações do Office** , conforme mostrado na figura a seguir, a instalação foi feita usando clique para executar. 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Quem se beneficia de ter esse recurso**
  
O usuário final cujo PC:
  
- **Tem** uma licença de usuário do Windows 10 Business, uma licença ativa do Microsoft 365 for Business, uma atualização do Windows 10 Creators e ingressou no Azure Active Directory. 
    
- **Não tem** aplicativos do Office de 64 bits (exemplo: Word, Excel, PowerPoint). Se os aplicativos do Office de 64 bits forem necessários, este recurso não é um bom ajuste porque não há suporte para o disparo de uma versão de 64 bits de 2016 clique para executar do Office no console de administração do Microsoft 365 for Business. 
    
- **Não tem** aplicativos autônomos do 2016 Windows Installer (MSI) (por exemplo, Visio ou Project). O Microsoft 365 for Business atualiza o Office para a versão clique para executar do Office 2016 e que não funciona com o Office 2016 MSI standalone apps. 
    
A tabela a seguir mostra a ação que os usuários finais/administradores podem precisar executar, dependendo do seu estado inicial, para ter uma versão bem-sucedida de clique para executar de 32 bits do deployment do Office no console de administração do Microsoft 365 para empresas.
  
|**Status inicial de instalação do Office**|**Ação a ser tomada antes da instalação do Office 365 para empresas**|**Estado final**|
|:-----|:-----|:-----|
|Nenhum pacote do Office instalado  <br/> |Nenhum  <br/> |O Office 2016 32-bit é instalado usando clique para executar  <br/> |
|Versão Clique para Executar de 32 bits do Office (2016 ou anterior) existente e nenhum aplicativo autônomo  <br/> |Nenhum  <br/> |Atualizar para a versão Clique para Executar de 32 bits mais recente do Office 2016, conforme necessário **\*** <br/> |
|Versão de clique para executar de 32 bits do Office e aplicativos do Office autônomos clique para executar 32 bits ou 64 bits (por exemplo, Visio, Project)  <br/> |Nenhum  <br/> |Aplicativos autônomos não são afetados. O pacote é atualizado para a versão Clique para Executar de 32 bits do Office 2016  <br/> |
|Versão Clique para Executar de 32 bits do Office e qualquer aplicativo autônomo do Office MSI de 32 bits ou 64 bits (exceto 2016)  <br/> |Nenhum  <br/> |Aplicativos autônomos não são afetados. O pacote é atualizado para a versão Clique para Executar de 32 bits do Office 2016  <br/> ||||
|Qualquer versão Clique para Executar de 64 bits do Office  <br/> |Desinstale os aplicativos do Office de 64 bits, se estiver tudo certo para substituí-los por aplicativos do Office de 32 bits  <br/> |Se os aplicativos do Office de 64 bits forem removidos, a versão Clique para Executar de 32 bits do Office 2016 será instalada  <br/> |
|Uma instalação MSI existente do Office 2016 com ou sem aplicativos autônomos  <br/> |Desinstale o MSI Office 2016.  <br/> |A versão Clique para Executar de 32 bits do Office 2016 está instalada. Nenhuma alteração nos aplicativos autônomos  <br/> |
|Instalação MSI existente do Office 2013 (ou anterior) e/ou aplicativos autônomos do Office  <br/> |Nenhuma  <br/> |A versão Clique para Executar de 32 bits do Office 2016 com a instalação do MSI Office preexistente (e aplicativos autônomos) funcionam lado a lado  <br/> |
||||
   
 **(\*) Observação:** A atualização para a versão Clique para Executar de 32 bits do Office 2016 não é instalada devido a um bug conhecido. Uma correção está em andamento. 
  
