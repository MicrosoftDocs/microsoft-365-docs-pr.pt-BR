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
description: Com o Office 365, alguns recursos de criptografia são ativados por padrão; outros recursos podem ser configurados para atender a certos requisitos legais ou de conformidade.
ms.openlocfilehash: bce7487f1cb57c04e262f068ea7e192808e43e8a
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943472"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Configure a criptografia no Office 365 Enterprise

A criptografia pode proteger o conteúdo contra leitura por usuários não autorizados. Como a [criptografia no Office 365](encryption.md) pode ser feita usando várias tecnologias e métodos, não existe um único lugar onde você ativa ou configura a criptografia. Este artigo fornece informações sobre várias maneiras de configurar ou configurar a criptografia como parte da estratégia de proteção de informações.
  
> [!TIP]
> Se você estiver procurando mais detalhes técnicos sobre criptografia, consulte [Technical Reference Details about Encryption in Office 365](technical-reference-details-about-encryption.md).
  
Com o Office 365, vários recursos de criptografia estão disponíveis por padrão. Recursos adicionais de criptografia podem ser configurados para atender a certos requisitos legais ou de conformidade. A tabela a seguir descreve vários métodos de criptografia para diferentes cenários.
  
|**Cenário**|**Métodos de criptografia**|
|:-----|:-----|
|Os arquivos são salvos em computadores com Windows  <br/> |A criptografia no nível do computador pode ser feita usando o BitLocker em dispositivos Windows. Como administrador corporativo ou profissional de ti, você pode configurar isso usando o kit de ferramentas de implantação da Microsoft (MDT). Confira [Configurar o MDT for BitLocker](https://go.microsoft.com/fwlink/?linkid=849282).  <br/> |
|Os arquivos são salvos em dispositivos móveis  <br/> |Alguns tipos de dispositivos móveis criptografam arquivos que são salvos nesses dispositivos por padrão. Com os [recursos do gerenciamento de dispositivo móvel interno para o Office 365](https://support.office.com/article/a1da44e5-7475-4992-be91-9ccec25905b0), você pode definir políticas que determinam se os dispositivos móveis devem acessar dados no Office 365. Por exemplo, você pode definir uma política que permita que apenas dispositivos que criptografam o conteúdo acessem os dados do Office 365. Consulte [criar e implantar políticas de segurança de dispositivos](https://support.office.com/article/d310f556-8bfb-497b-9bd7-fe3c36ea2fd6).  <br/> Para obter mais controle sobre como os dispositivos móveis interagem com o Office 365, você pode considerar a adição [do Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/setup-steps).  <br/> |
|Você precisa de controle sobre as chaves de criptografia usadas para criptografar seus dados nos data centers da Microsoft  <br/> | Como administrador do Office 365, você pode controlar as chaves de criptografia da sua organização e, em seguida, configurar o Office 365 para usá-las para criptografar seus dados em repouso nos data centers da Microsoft.  <br/> [Criptografia de serviço com Chave de Cliente no Office 365](customer-key-overview.md) <br/> |
|Pessoas estão se comunicando por email (Exchange Online)  <br/> | Como administrador do Exchange Online, você tem várias opções para configurar a criptografia de email. Entre eles:  <br/>  Usando a [criptografia de mensagem do Office 365 (ome)](set-up-new-message-encryption-capabilities.md) com o Azure Rights Management (Azure RMS) para permitir que as pessoas enviem mensagens criptografadas dentro ou fora da sua organização  <br/>  Usando [S/MIME para assinatura e criptografia de mensagens](https://aka.ms/c6dozg) para criptografar e assinar digitalmente mensagens de email  <br/>  Usando o TLS para [configurar conectores para fluxo de email seguro com outra organização](https://aka.ms/hs809p) <br/>  Consulte [criptografia de email no Office 365](https://aka.ms/hic3f7).  <br/> |
|Os arquivos são acessados por sites de equipe ou bibliotecas de documentos (OneDrive for Business ou SharePoint Online)  <br/> |Quando as pessoas estão trabalhando com arquivos salvos no OneDrive for Business ou no SharePoint Online, as conexões TLS são usadas. Isso é feito automaticamente no Office 365. Consulte [criptografia de dados no onedrive for Business e no SharePoint Online](https://go.microsoft.com/fwlink/?linkid=526379).  <br/> |
|Os arquivos são compartilhados em reuniões online e conversas de IM (Skype for Business online)  <br/> |Quando as pessoas estão trabalhando com arquivos usando o Skype for Business Online, o TLS é usado para a conexão. Isso é feito automaticamente no Office 365. Consulte [segurança e arquivamento (Skype for Business online)](https://aka.ms/nuq4ws).  <br/> |

## <a name="additional-information"></a>Informações adicionais

Para saber mais sobre soluções de proteção de arquivo que incluem opções de criptografia, confira [soluções de proteção de arquivo no Office 365](https://www.microsoft.com/download/details.aspx?id=55523).
 
