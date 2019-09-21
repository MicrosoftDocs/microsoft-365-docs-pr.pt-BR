---
title: Solução de problemas e informações de suporte
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5d9f75f5-bb7f-458c-ad30-5c8eae0b0e4e
ms.collection:
- M365-security-compliance
description: Este tópico descreve as etapas de solução de problemas para os usuários finais e administradores e fornece informações sobre como contatar o suporte técnico para obter assistência.
ms.openlocfilehash: 2a8019ed58bfb88183d20a8292bd5a30d9b43f13
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073792"
---
# <a name="troubleshooting-and-support-information"></a>Solução de problemas e informações de suporte

Este tópico descreve as etapas de solução de problemas para os usuários finais e administradores e fornece informações sobre como contatar o suporte técnico para obter assistência.
  
## <a name="troubleshooting-for-users"></a>Solução de problemas para os usuários

Ocasionalmente, você pode enfrentar problemas com o Microsoft Office Outlook depois de adicionar o Suplemento de Relatório de Lixo Eletrônico. Veja a seguir os problemas que você pode encontrar, juntamente com dicas para resolvê-los. 
  
- Nada acontece quando você clica em **Relatar Lixo Eletrônico**
    
- O Outlook para de responder depois que você selecionar uma mensagem de email
    
- O lixo eletrônico relatado não pode ser entregue devido a uma resposta "não entregue"
    
### <a name="troubleshooting-tip"></a>Dica de solução de problemas

1. Feche e reinicie o Microsoft Office Outlook.
    
2. Verifique se você é capaz de criar e enviar uma mensagem de teste. Para fazer isso, você pode enviar uma mensagem de teste para outra conta de email pela qual é responsável e, em seguida, verificar se a mensagem é recebida.
    
Se o problema persistir, entre em contato com o administrador de TI.
  
> [!TIP]
> Também é possível enviar mensagens de spam diretamente para a Microsoft, usando o endereço de email [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com); para enviar mensagens que são falsos positivos, use o endereço de email [not_junk@office365.microsoft.com](mailto: not_junk@office365.microsoft.com). Para obter mais informações, consulte [enviar mensagens de spam, não spam e golpes de phishing para a Microsoft para análise](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). 
  
## <a name="troubleshooting-for-administrators"></a>Solução de problemas para os administradores

Como administrador, você pode perceber problemas com usuários que utilizam o Suplemento de Relatório de Lixo Eletrônico do Microsoft Office Outlook. A seguir. apresentamos algumas dicas para solucionar problemas que você possa vir a encontrar. 
  
 **Problema:** Aparece uma mensagem de erro continuamente pedindo para os usuários entrarem em contato com o administrador do sistema. 
  
### <a name="troubleshooting-tip"></a>Dica de solução de problemas

1. Defina o seguinte valor de chave do Registro como "Verbose":
    
  - **Outlook de 32 bits instalado em um sistema operacional de 32 bits:**
    
    HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel
    
  - **Outlook de 32 bits instalado em um sistema operacional de 64 bits:**
    
    HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Junk Email Reporting\Addins\LoggingLevel
    
  - **Outlook de 64 bits (sempre instalado em um sistema operacional de 64 bits):**
    
    HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel
    
2. Reinicie o Microsoft Office Outlook e peça aos usuários para relatar quando virem a mensagem de erro.
    
3. Colete as informações de log encontradas no seguinte local: 
    
    %LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt
    
4. Entre em contato com o suporte técnico do Exchange Online Protection e forneça as informações de log. 
    
 **Problema:** Os usuários optam por não receber uma confirmação quando eles enviam um email como lixo eletrônico e agora eles querem a opção de volta. 
  
### <a name="troubleshooting-tip"></a>Dica de solução de problemas

1. Defina o seguinte valor de chave do Registro como "True": HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences\ConfirmReportJunk
    
2. Reinicie o Microsoft Office Outlook.
    
## <a name="support-information"></a>Informações de suporte

Se você precisar de ajuda com a instalação, configuração ou desinstalação do suplemento, entre em contato com o suporte técnico usando o link nova solicitação de serviço na página suporte no centro de administração do Microsoft 365. Para opções adicionais, incluindo o envio de uma solicitação de serviço por meio de opções de telefone e de autoatendimento, consulte [ajuda e suporte para EOP](help-and-support-for-eop.md).
  
## <a name="for-more-information"></a>Para saber mais

[Habilitar o suplemento de Mensagem de Relatório](https://support.office.com/article/4250c4bc-6102-420b-9e0a-a95064837676)
  
[Relatar mensagens de Lixo Eletrônico à Microsoft](report-junk-email-messages-to-microsoft.md)
  

