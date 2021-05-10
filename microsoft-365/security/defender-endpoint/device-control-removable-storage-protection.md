---
title: Microsoft Defender for Endpoint Device Control Removable Armazenamento Protection
description: Entenda os "recursos que ajudam a impedir que o usuário ou a máquina ou ambos usem mídia de armazenamento removível não autorizada
keywords: mídia de armazenamento removível
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-smandalika
author: v-smandalika
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ec5cfa78852d65db808c4e853f90f5639df25d6f
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300105"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Microsoft Defender for Endpoint Device Control Removable Armazenamento Protection

[!INCLUDE [Prerelease](../includes/prerelease.md)]

O Microsoft Defender for Endpoint Device Control Removível Armazenamento Proteção impede que o usuário ou máquina ou ambos usem mídia de armazenamento removível não autorizada.

**Microsoft Defender for Endpoint Removable Armazenamento Protection**


|Política  |Funcionalidade |Descrição  |
|---------|---------|---------|
|Instalação do dispositivo    |  Impedir a instalação com ou sem exclusão - Permitir dispositivos específicos com base em várias propriedades; para obter mais informações, consulte a [seção Propriedades do](#device-properties) dispositivo abaixo.        |    Funciona no computador: Usuários diferentes fazendo logon no mesmo computador serão restritos pela mesma política. Para obter informações, [consulte Como controlar dispositivos USB e outras mídias removíveis usando o Microsoft Defender para Ponto de Extremidade](control-usb-devices-using-intune.md).     |
|Controle de acesso de armazenamento removível      | (1) Auditar o acesso de leitura ou gravação ou execução ao armazenamento removível com base em várias propriedades de dispositivo, com ou sem exceção. Para obter mais informações, consulte a [seção Propriedades do](#device-properties) dispositivo abaixo. (2) Impedir acesso de leitura ou gravação ou execução com ou sem exclusão - Permitir dispositivos específicos com base em várias propriedades de dispositivo; para obter mais informações sobre as propriedades do dispositivo, consulte a [seção Propriedades do](#device-properties) dispositivo abaixo.     |     Funciona em máquina ou usuário ou ambos: permitir somente pessoas específicas que executam o acesso de Leitura/Gravação/Execução a um armazenamento removível específico em um computador específico; para o recurso no Windows, consulte Controle de Acesso [de armazenamento removível;](device-control-removable-storage-access-control.md) para o recurso no Mac, consulte [Controle de dispositivo para macOS](mac-device-control-overview.md).     |
|Armazenamento removível de DLP do ponto de extremidade      |    Auditar ou avisar ou impedir que um usuário copie um item ou informações para mídia removível ou dispositivo USB.     |  Para obter mais informações, consulte [Microsoft Endpoint DLP](/compliance/endpoint-dlp-learn-about.md).       |
|BitLocker    |     Bloquear dados que devem ser gravados em unidades removíveis que não sejam BitLocker protegidos: Bloqueie o acesso a unidades removíveis, a menos que tenham sido criptografadas em um computador pertencente à sua organização.    |   Para obter mais informações, consulte BitLocker – [Unidade Removível Configurações](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings#bitlocker---removable-drive-settings.md).      |

## <a name="device-properties"></a>Propriedades do dispositivo

O Microsoft Defender for Endpoint Device Control Removable Armazenamento Protection permite restringir o acesso de armazenamento removível com base nas propriedades descritas na tabela abaixo:


|Nome da propriedade  |Políticas aplicáveis  |Aplica-se a sistemas operacionais  |Descrição  |
|---------|---------|---------|---------|
|Classe device    |     [Como controlar dispositivos USB e outras mídias removíveis usando o Microsoft Defender para Ponto de Extremidade](control-usb-devices-using-intune.md)     |   Windows      |  Para obter informações sobre formatos de ID de dispositivo, consulte [classe de configuração do dispositivo](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors). **Observação:** a instalação do dispositivo pode ser aplicada a qualquer dispositivo, não apenas ao armazenamento removível.       |
|ID principal   |     Controle de acesso de armazenamento removível    |   Windows      |      A ID primária inclui armazenamento removível e CD/DVD.   |
|ID do dispositivo     |  [Como controlar dispositivos USB e outras mídias removíveis usando o Microsoft Defender para Ponto de Extremidade;](control-usb-devices-using-intune.md) Controle de acesso de armazenamento removível       |      Windows   |    Para obter informações sobre formatos de ID de dispositivo, consulte [Standard USB Identifiers](/windows-hardware/drivers/install/standard-usb-identifiers), por exemplo, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07      |
|Hardware ID     |     [Como controlar dispositivos USB e outras mídias removíveis usando o Microsoft Defender para Ponto de Extremidade;](control-usb-devices-using-intune.md) Controle de acesso de armazenamento removível    |     Windows    |    Uma cadeia de caracteres identificou o dispositivo no sistema, por exemplo, USBSTOR\DiskGeneric_Flash_Disk______8.07; **Observação:** a ID de hardware não é exclusiva; dispositivos diferentes podem compartilhar o mesmo valor.|
|ID da Instância    | Instalação do dispositivo; Controle de acesso de armazenamento removível     |     Windows    |   Uma cadeia de caracteres identifica exclusivamente o dispositivo no sistema, por exemplo, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0      |
|Nome Amigável     |     Controle de acesso de armazenamento removível    |   Windows      |    Uma cadeia de caracteres anexada ao dispositivo, por exemplo, Dispositivo USB de Disco Flash Genérico     |
|ID do fornecedor/ID do produto     |  Controle de acesso de armazenamento removível       |   Windows Mac      |     ID do fornecedor é o código de fornecedor de quatro dígitos que o comitê USB atribui ao fornecedor. A ID do produto é o código de produto de quatro dígitos que o fornecedor atribui ao dispositivo; Suporte a caractere curinga.    |
|NumberId de série     |     Controle de acesso de armazenamento removível    |      Windows Mac   |     Por exemplo, <SerialNumberId>002324B534BCB431B000058A</SerialNumberId>    |

## <a name="related-topic"></a>Tópicos relacionados

- [Microsoft Defender for Endpoint Device Control Removível Armazenamento Access Control](device-control-removable-storage-access-control.md)
