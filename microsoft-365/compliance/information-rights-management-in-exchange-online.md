---
title: Criptografia de email do Exchange Online com AD RMS
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2c956776-0016-4be6-b4cd-133a237f4a9e
description: Você pode configurar o IRM do Exchange Online para usar o AD RMS (Active Directory Rights Management Service) local, se necessário, para atender aos requisitos da sua organização. Isso não é comum. Se você não tiver um requisito para usar o AD RMS, use a criptografia de mensagem do Office.
ms.openlocfilehash: 1c3bdf02f31f57f1328f0244d539d0dc88e7ba89
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38684815"
---
# <a name="exchange-online-mail-encryption-with-ad-rms"></a>Criptografia de email do Exchange Online com AD RMS

Para evitar o vazamento de informações, o Exchange Online inclui a funcionalidade IRM (Gerenciamento de Direitos de Informação) que oferece proteção online e offline de mensagens e anexos de email. Você pode configurar o IRM do Exchange Online para usar o AD RMS (Active Directory Rights Management Service) local, se necessário, para atender aos requisitos da sua organização. Isso não é comum. Se você não tiver um requisito para usar o AD RMS, use a [criptografia de mensagem do Office 365](ome.md) . 

A proteção do IRM pode ser aplicada por usuários no Microsoft Outlook ou no Outlook na Web e pode ser aplicada por administradores usando regras de proteção de transporte ou regras de proteção do Outlook. O IRM ajuda você e seus usuários a controlar quem pode acessar, encaminhar, imprimir ou copiar dados confidenciais em um email.
  
## <a name="changes-to-how-irm-works-with-office-365-message-encryption-ome-and-azure-active-directory"></a>Alterações no modo como o IRM funciona com o Office 365 Message Encryption (OME) e Azure Active Directory

A partir de setembro de 2017, ao configurar os novos recursos de criptografia de mensagens do Office 365 para sua organização, você também configura o IRM para uso com o Azure Rights Management (Azure RMS). Você não mais configurou o IRM com o Azure RMS separadamente. Em vez disso, o OME e o gerenciamento de direitos funcionam perfeitamente juntos. Para obter mais detalhes sobre os novos recursos, confira [perguntas frequentes sobre criptografia de mensagem do Office 365](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e). Se você estiver pronto para começar a usar os novos recursos do OME em sua organização, confira [configurar os novos recursos de criptografia de mensagens do Office 365 criados na parte superior da proteção de informações do Azure](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e).
  
## <a name="how-irm-works-with-exchange-online-and-active-directory-rights-management-services"></a>Como o IRM funciona com o Exchange Online e o Active Directory Rights Management Services

O IRM do Exchange Online usa o Active Directory Rights Management Services (AD RMS) local, uma tecnologia de proteção de informações no Windows Server 2008 e posterior. A proteção do IRM é aplicada ao email por meio da aplicação de um modelo de política de direitos do AD RMS a uma mensagem de email. Os direitos são anexados à própria mensagem para que a proteção ocorra online e offline e dentro e fora do firewall da sua organização.
  
Os usuários podem aplicar um modelo a uma mensagem de email para controlar as permissões que os destinatários têm em uma mensagem. Ações como encaminhar, extrair informações de uma mensagem, salvar uma mensagem ou imprimir uma mensagem podem ser controladas com a aplicação de uma política de direitos do AD RMS à mensagem.
  
Você pode configurar o IRM para usar um servidor AD RMS executando o Windows Server 2008 ou posterior. Você pode usar esse servidor AD RMS para gerenciar os modelos de política de direitos de AD RMS para sua organização baseada em nuvem. O Outlook também usa o servidor AD RMS para permitir que os usuários apliquem a proteção do IRM às mensagens que enviam. Para obter detalhes, consulte [Configurar o IRM para usar um servidor AD RMS local](configure-irm-to-use-an-on-premises-ad-rms-server.md). 
  
Depois de habilitada, a proteção do IRM pode ser aplicada às mensagens da seguinte maneira:
  
- **Os usuários podem aplicar um modelo manualmente usando o Outlook e o Outlook na Web.** Os usuários podem aplicar uma modelo de política de direitos do AD RMS a uma mensagem de email selecionando o modelo na lista **Definir permissões**. Quando os usuários enviam uma mensagem protegida por IRM, qualquer arquivo anexado que usa um formato compatível também recebe a mesma proteção do IRM para a mensagem. A proteção do IRM é aplicada aos arquivos associados ao Word, Excel e PowerPoint, bem como aos arquivos .xps e anexos de mensagens de email. 
    
- **Os administradores podem usar regras de proteção de transporte para aplicar a proteção de IRM automaticamente ao Outlook e ao Outlook na Web.** Você pode criar regras de proteção de transporte para mensagens protegidas por IRM. Configure a ação da regra de proteção de transporte para aplicar um modelo de política de direitos do AD RMS às mensagens que cumprem a condição da regra. Depois que você habilita o IRM, os modelos de política de direitos do AD RMS de sua organização ficam disponíveis para uso com a ação de regra de proteção de transporte denominada **Aplicar proteção de direitos à mensagem com**.
    
- **Os administradores podem criar regras de proteção do Outlook.** As regras de proteção do Outlook aplicam automaticamente a proteção de IRM a mensagens no Outlook 2010 (não no Outlook na Web) com base em condições de mensagem que incluem o departamento do remetente ao qual a mensagem é enviada e se os destinatários estão dentro ou fora do seu departamento. Para obter detalhes, consulte [Create an Outlook Protection Rule](https://technet.microsoft.com/library/da64750d-faaf-44de-ad8c-888eba7fbdbf.aspx).
    

