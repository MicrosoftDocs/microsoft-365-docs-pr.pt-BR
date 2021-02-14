---
title: Configure a criptografia no Office 365 Enterprise
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/2/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: Com o Office 365, alguns recursos de criptografia são ligado por padrão; outros recursos podem ser configurados para atender a determinados requisitos legais ou de conformidade.
ms.openlocfilehash: 268bd7b57884549b7ab4abb45a7b69485498f1cb
ms.sourcegitcommit: 89636f35b0194986f156302fc1bb96af25d4805b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44799986"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Configure a criptografia no Office 365 Enterprise

A criptografia pode proteger seu conteúdo de ser lido por usuários não autorizados. Como [a criptografia no Office 365](encryption.md) pode ser feita usando várias tecnologias e métodos, não há um único local onde você ativar ou configurar a criptografia. Este artigo fornece informações sobre várias maneiras de configurar a criptografia como parte de sua estratégia de proteção de informações.
  
> [!TIP]
> Se você estiver procurando detalhes mais técnicos sobre criptografia, confira Detalhes de referência técnica sobre criptografia [no Office 365.](technical-reference-details-about-encryption.md)
  
Com o Office 365, vários recursos de criptografia estão disponíveis por padrão. Recursos de criptografia adicionais podem ser configurados para atender a determinados requisitos legais ou de conformidade. A tabela a seguir descreve vários métodos de criptografia para diferentes cenários.
  
|**Cenário**|**Métodos de criptografia**|
|:-----|:-----|
|Os arquivos são salvos em computadores Windows  <br/> |A criptografia no nível do computador pode ser feita usando o BitLocker em dispositivos Windows. Como administrador corporativo ou profissional de TI, você pode configurar isso usando o Microsoft Deployment Toolkit (MDT). Consulte [Configurar o MDT para BitLocker.](https://go.microsoft.com/fwlink/?linkid=849282)  <br/> |
|Os arquivos são salvos em dispositivos móveis  <br/> |Alguns tipos de dispositivos móveis criptografam arquivos salvos nesses dispositivos por padrão. Com recursos de gerenciamento de dispositivos móveis integrados para [o Office 365,](https://support.microsoft.com/en-us/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0)você pode definir políticas que determinam se os dispositivos móveis podem acessar dados no Office 365. Por exemplo, você pode definir uma política que permita que apenas dispositivos que criptografam conteúdo acessem dados do Office 365. Consulte [Criar e implantar políticas de segurança de dispositivo.](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6)  <br/> Para ter controle adicional sobre como os dispositivos móveis interagem com o Office 365, você pode considerar a adição [do Microsoft Intune.](https://docs.microsoft.com/mem/intune/fundamentals/setup-steps)  <br/> |
|Você precisa de controle sobre as chaves de criptografia usadas para criptografar seus dados nos data centers da Microsoft  <br/> | Como administrador do Office 365, você pode controlar as chaves de criptografia da sua organização e configurar o Office 365 para usá-las para criptografar seus dados em repouso nos data centers da Microsoft.  <br/> [Criptografia de serviço com Chave de Cliente no Office 365](customer-key-overview.md) <br/> |
|As pessoas estão se comunicando por email (Exchange Online)  <br/> | Como administrador do Exchange Online, você tem várias opções para configurar a criptografia de email. Entre eles:  <br/>  Usar a criptografia de mensagem [do Office 365 (OME)](set-up-new-message-encryption-capabilities.md) com o Azure Rights Management (Azure RMS) para permitir que as pessoas enviem mensagens criptografadas dentro ou fora da sua organização  <br/>  Usar [S/MIME para assinatura de mensagens e criptografia para](https://aka.ms/c6dozg) criptografar e assinar digitalmente mensagens de email  <br/>  Usar o TLS [para configurar conectores para fluxo de email seguro com outra organização](https://aka.ms/hs809p) <br/>  Confira [a criptografia de email no Office 365.](https://aka.ms/hic3f7)  <br/> |
|Os arquivos são acessados de sites de equipe ou bibliotecas de documentos (OneDrive for Business ou SharePoint Online)  <br/> |Quando as pessoas estão trabalhando com arquivos salvos no OneDrive for Business ou no SharePoint Online, as conexões TLS são usadas. Isso é integrado ao Office 365 automaticamente. Confira [a Criptografia de Dados no OneDrive for Business e no SharePoint Online.](https://go.microsoft.com/fwlink/?linkid=526379)  <br/> |
|Os arquivos são compartilhados em reuniões online e conversas de IM (Skype for Business Online)  <br/> |Quando as pessoas estão trabalhando com arquivos usando o Skype for Business Online, o TLS é usado para a conexão. Isso é integrado ao Office 365 automaticamente. Consulte [Segurança e Arquivamento (Skype for Business Online).](https://aka.ms/nuq4ws)  <br/> |
|Os arquivos são compartilhados em reuniões online e conversas de IM (Microsoft Teams)  <br/> |Quando as pessoas estão trabalhando com arquivos usando o Microsoft Teams, o TLS é usado para a conexão. Isso é integrado ao Office 365 automaticamente. No momento, o Microsoft Teams não dá suporte à renderização em linha de emails criptografados. Para impedir que emails criptografados chegar ao Microsoft Teams como criptografados, confira Perguntas frequentes [sobre Criptografia de Mensagens.](https://docs.microsoft.com/microsoft-365/compliance/ome-faq?view=o365-worldwide#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail)  <br/> 

## <a name="additional-information"></a>Informações adicionais

Para saber mais sobre soluções de proteção de arquivos que incluem opções de criptografia, consulte Soluções de proteção [de arquivos no Office 365.](https://www.microsoft.com/download/details.aspx?id=55523)
 
