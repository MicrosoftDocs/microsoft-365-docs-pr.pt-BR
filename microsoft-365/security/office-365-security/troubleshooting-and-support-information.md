---
title: Solução de problemas e informações de suporte
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
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
ms.openlocfilehash: c87744608930603f70e6be1132a0b405e9646b57
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441188"
---
# <a name="troubleshooting-and-support-information"></a>Solução de problemas e informações de suporte

Este tópico descreve as etapas de solução de problemas para os usuários finais e administradores e fornece informações sobre como contatar o suporte técnico para obter assistência.

## <a name="troubleshooting-for-users"></a>Solução de problemas para os usuários

Ocasionalmente, você pode enfrentar problemas com o Microsoft Outlook após adicionar o suplemento de relatório de lixo eletrônico. Veja a seguir os problemas que você pode encontrar, juntamente com dicas para resolvê-los.

- Nada acontece quando você clica em **Relatar Lixo Eletrônico**

- O Outlook para de responder depois que você selecionar uma mensagem de email

- O lixo eletrônico relatado não pode ser entregue devido a uma resposta "não entregue"

Para corrigir esse problema, siga estas etapas:

1. Feche e reinicie o Outlook.

2. Verifique se você é capaz de criar e enviar uma mensagem de teste. Para fazer isso, você pode enviar uma mensagem de teste para outra conta de email pela qual é responsável e, em seguida, verificar se a mensagem é recebida.

Se o problema persistir, entre em contato com seu administrador.

> [!TIP]
> Também é possível enviar mensagens de spam diretamente para a Microsoft, usando o endereço de email [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com); para enviar mensagens que são falsos positivos, use o endereço de email [not_junk@office365.microsoft.com](mailto: not_junk@office365.microsoft.com). Para obter mais informações, consulte [enviar mensagens de spam, não spam e golpes de phishing para a Microsoft para análise](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).

## <a name="troubleshooting-for-administrators"></a>Solução de problemas para os administradores

Como administrador, você pode ter problemas com usuários usando o suplemento relatório de lixo eletrônico para o Outlook. Veja a seguir algumas dicas para resolver problemas que você pode encontrar.

### <a name="problem-an-error-message-asking-users-to-contact-their-system-administrator-continually-appears"></a>Problema: uma mensagem de erro solicitando que os usuários entrem em contato com o administrador do sistema é exibida continuamente

1. Defina o seguinte valor de chave do Registro como "Verbose":

   - **o Outlook de 32 bits instalado em um sistema operacional de 32 bits**:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

   - **o Outlook de 32 bits instalado em um sistema operacional de 64 bits**:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

   - **64 bit Outlook (sempre instalado em um sistema operacional de 64 bits)**:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

2. Reinicie o Outlook e peça aos usuários para reportá-los quando eles verão a mensagem de erro.

3. Colete as informações de log encontradas no seguinte local:

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. Entre em contato com o suporte técnico do Exchange Online Protection e forneça as informações de log.

### <a name="problem-users-choose-not-to-receive-a-confirmation-when-they-submit-an-email-as-junk-and-now-they-want-the-option-back"></a>Problema: os usuários optam por não receber uma confirmação quando eles enviam um email como lixo eletrônico e agora eles querem a opção de volta

1. Defina o seguinte valor de chave do registro como "true `HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences\ConfirmReportJunk`":.

2. Reinicie o Outlook.

## <a name="support-information"></a>Informações de suporte

Se você precisar de ajuda com a instalação, configuração ou desinstalação do suplemento, entre em contato com o suporte técnico usando o link nova solicitação de serviço na página suporte no centro de administração do Microsoft 365. Para opções adicionais, incluindo o envio de uma solicitação de serviço por meio de opções de telefone e de autoatendimento, consulte [ajuda e suporte para EOP](help-and-support-for-eop.md).

## <a name="for-more-information"></a>Para saber mais

[Habilitar o suplemento de Mensagem de Relatório](https://support.office.com/article/4250c4bc-6102-420b-9e0a-a95064837676)

[Relatar mensagens de lixo eletrônico à Microsoft](report-junk-email-messages-to-microsoft.md)
