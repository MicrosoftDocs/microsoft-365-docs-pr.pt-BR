---
title: Preparar para distribuição de cliente do Office com o Microsoft 365 Business
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
description: Saiba como instalar automaticamente os aplicativos do Office de 32 bits em computadores com o Windows 10 e mantê-los atualizados.
ms.openlocfilehash: 5b28c1e62d813c52b41ce8e7619c865cdf7690e2
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575809"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a>Preparar para distribuição de cliente do Office com o Microsoft 365 Business

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Preparar-se para instala automaticamente os aplicativos do Office em computadores de clientes

Você pode usar o Microsoft 365 Business para instalar os aplicativos do Office de 32 bits em computadores com o Windows 10 e mantê-los atualizados automaticamente.
  
Isso funciona melhor se o computador do usuário final tiver o Windows 10 Business e:
  
- Não tiver aplicativos de área de trabalho do Office existentes (por exemplo, Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access e OneDrive).
    
    ou
    
- Tiver instalada uma versão Clique para Executar do Office.
    
Para determinar se você tem a versão Clique para Executar do Office, em qualquer aplicativo do Office, vá para **Arquivo** \> **Conta** ( **Conta do Office**). Se você vir Atualizações do Office, como é mostrado na figura a seguir, a instalação foi realizada usando o Clique para Executar. 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Quem se beneficia com esse recurso**
  
O usuário final cujo PC:
  
- **Tem** uma licença de usuário do Windows 10 Business, uma licença ativa do Microsoft 365 Business, a Atualização do Windows 10 para Criadores e ingressou no Azure Active Directory. 
    
- **Não tem** aplicativos do Office de 64 bits (exemplo: Word, Excel, Powerpoint). Se os aplicativos do Office de 64 bits forem necessários, esse recurso não é o ideal, pois não há suporte para acionar uma versão Clique para Executar de 64 bits do Office 2016 pelo console de administração do Microsoft 365 Business. 
    
- **Não tem** aplicativos autônomos do 2016 Windows Installer (MSI) (por exemplo, Visio ou Project). O Microsoft 365 Business atualiza o Office para a versão Clique para Executar do Office 2016 e ela não funciona com aplicativos autônomos do Office 2016 MSI. 
    
A tabela a seguir detalha as ações que os usuários finais/administradores podem precisar tomar, dependendo do seu estado inicial, para ter uma versão Clique para Executar de 32 bits do Office pelo console de administração do Microsoft 365 Business.
  
|**Status inicial de instalação do Office**|**Ação a ser executada antes de instalar o Office pelo Microsoft 365 Business**|**Estado final**|
|:-----|:-----|:-----|
|Nenhum pacote do Office instalado  <br/> |Nenhum  <br/> |O Office 2016 de 32 bits foi instalado usando Clique para Executar  <br/> |
|Versão Clique para Executar de 32 bits do Office (2016 ou anterior) existente e nenhum aplicativo autônomo  <br/> |Nenhum  <br/> |Atualizar para a versão Clique para Executar de 32 bits mais recente do Office 2016, conforme necessário **\*** <br/> |
|Versão Clique para Executar de 32 bits do Office e aplicativos autônomos Clique para Executar de 32 ou 64 bits do Office (por exemplo, Visio, Project)  <br/> |Nenhum  <br/> |Aplicativos autônomos não são afetados. O pacote é atualizado para a versão Clique para Executar de 32 bits do Office 2016  <br/> |
|Versão Clique para Executar de 32 bits do Office e qualquer aplicativo autônomo do Office MSI de 32 bits ou 64 bits (exceto 2016)  <br/> |Nenhum  <br/> |Aplicativos autônomos não são afetados. O pacote é atualizado para a versão Clique para Executar de 32 bits do Office 2016  <br/> ||||
|Qualquer versão Clique para Executar de 64 bits do Office  <br/> |Desinstalar os aplicativos do Office de 64 bits, se for possível substituí-los pelos aplicativos do Office de 32 bits  <br/> |Se os aplicativos do Office de 64 bits forem removidos, a versão Clique para Executar de 32 bits do Office 2016 será instalada  <br/> |
|Uma instalação MSI existente do Office 2016 com ou sem aplicativos autônomos  <br/> |Desinstale o MSI Office 2016.  <br/> |A versão Clique para Executar de 32 bits do Office 2016 está instalada. Nenhuma alteração nos aplicativos autônomos  <br/> |
|Instalação MSI existente do Office 2013 (ou anterior) e/ou aplicativos autônomos do Office  <br/> |Nenhuma  <br/> |A versão Clique para Executar de 32 bits do Office 2016 com a instalação do MSI Office preexistente (e aplicativos autônomos) funcionam lado a lado  <br/> |
||||
   
 **(\*) Observação:** A atualização para a versão Clique para Executar de 32 bits do Office 2016 não é instalada devido a um bug conhecido. A correção está em andamento. 
  


