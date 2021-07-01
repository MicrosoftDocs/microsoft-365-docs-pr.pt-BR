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
description: Com Office 365, alguns recursos de criptografia são aados por padrão; outros recursos podem ser configurados para atender a determinados requisitos legais ou de conformidade.
ms.openlocfilehash: a9a3170fdb99a4acfec8cf4d3b03ab9b584197bd
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228466"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Configure a criptografia no Office 365 Enterprise

A criptografia pode proteger seu conteúdo de ser lido por usuários não autorizados. Como [a criptografia no Office 365](encryption.md) pode ser feita usando várias tecnologias e métodos, não há um único local onde você ativar ou configurar a criptografia. Este artigo fornece informações sobre várias maneiras de configurar ou configurar a criptografia como parte de sua estratégia de proteção de informações.

> [!TIP]
> Se você estiver procurando detalhes mais técnicos sobre criptografia, consulte [Technical reference details about encryption in Office 365](technical-reference-details-about-encryption.md).

Com Office 365, vários recursos de criptografia estão disponíveis por padrão. Recursos adicionais de criptografia podem ser configurados para atender a determinados requisitos legais ou de conformidade. A tabela a seguir descreve vários métodos de criptografia para cenários diferentes.

<br>

****

|Cenário|Métodos de criptografia|
|---|---|
|Os arquivos são salvos em Windows computadores|A criptografia no nível do computador pode ser feita usando o BitLocker em Windows dispositivos. Como administrador corporativo ou Pro de TI, você pode configurar isso usando o Microsoft Deployment Toolkit (MDT). Consulte [Configurar o MDT para BitLocker](/windows/deployment/deploy-windows-mdt/set-up-mdt-for-bitlocker).|
|Os arquivos são salvos em dispositivos móveis|Alguns tipos de dispositivos móveis criptografam arquivos que são salvos nesses dispositivos por padrão. Com [recursos de Gerenciamento de Dispositivo Móvel do Office 365](https://support.microsoft.com/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0)internas, você pode definir políticas que determinam se os dispositivos móveis podem acessar dados em Office 365. Por exemplo, você pode definir uma política que permite que apenas dispositivos que criptografam conteúdo acessem Office 365 dados. Consulte [Criar e implantar políticas de segurança de dispositivo.](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6) <p> Para obter controle adicional sobre como os dispositivos móveis interagem com Office 365, você pode considerar adicionar [Microsoft Intune](/mem/intune/fundamentals/setup-steps).|
|Você precisa controlar as chaves de criptografia usadas para criptografar seus dados nos data centers da Microsoft|Como administrador Office 365, você pode controlar as chaves de criptografia da sua organização e, em seguida, configurá-las Office 365 usá-las para criptografar seus dados em repouso nos data centers da Microsoft. <p> [Criptografia de serviço com Chave de Cliente no Office 365](customer-key-overview.md)|
|As pessoas estão se comunicando por email (Exchange Online)|Como administrador Exchange Online, você tem várias opções para configurar a criptografia de email. Entre eles: <ul><li>Usar Office 365 criptografia de mensagem [(OME)](set-up-new-message-encryption-capabilities.md) com o Azure Rights Management (Azure RMS) para permitir que as pessoas enviem mensagens criptografadas dentro ou fora de sua organização</li><li>Usando [S/MIME](/exchange/security-and-compliance/smime-exo/smime-exo) para criptografar e assinar digitalmente mensagens de email</li><li>Usando o TLS para [configurar conectores para fluxo de email seguro com outra organização](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)</li></ul> <p> Consulte [Criptografia de email em Office 365](./email-encryption.md).|
|Os arquivos são acessados de sites de equipe ou bibliotecas de documentos (OneDrive for Business ou SharePoint Online)|Quando as pessoas estão trabalhando com arquivos salvos no OneDrive for Business ou SharePoint Online, as conexões TLS são usadas. Isso é integrado Office 365 automaticamente. Consulte [Criptografia de Dados no OneDrive for Business e SharePoint Online](./data-encryption-in-odb-and-spo.md).|
|Os arquivos são compartilhados em reuniões online e conversas de IM (Skype for Business Online)|Quando as pessoas estão trabalhando com arquivos usando Skype for Business Online, o TLS é usado para a conexão. Isso é integrado Office 365 automaticamente. Consulte [Segurança e Arquivamento (Skype for Business Online)](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features).|
|Os arquivos são compartilhados em reuniões online e conversas de IM (Microsoft Teams)|Quando as pessoas estão trabalhando com arquivos usando Microsoft Teams, o TLS é usado para a conexão. Isso é integrado Office 365 automaticamente. Microsoft Teams atualmente não dá suporte à renderização em linha de emails criptografados. Para impedir que o email criptografado entre Microsoft Teams como criptografado, consulte Perguntas frequentes sobre criptografia [de mensagens.](./ome-faq.yml#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail-)|
|

## <a name="additional-information"></a>Informações adicionais

Para saber mais sobre soluções de proteção de arquivos que incluem opções de criptografia, consulte [File Protection Solutions in Office 365](https://www.microsoft.com/download/details.aspx?id=55523).
