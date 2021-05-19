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
ms.openlocfilehash: c9b97c2157ba8090628af23b2ab54cf38f04d8c6
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538382"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Microsoft Defender for Endpoint Device Control Removable Armazenamento Protection

[!INCLUDE [Prerelease](../includes/prerelease.md)]

O Microsoft Defender for Endpoint Device Control Removível Armazenamento Proteção impede que o usuário ou máquina ou ambos usem mídia de armazenamento removível não autorizada.

## <a name="protection-policies"></a>Políticas de proteção

### <a name="device-installation"></a>Instalação do dispositivo

**Recursos** - Impedir a instalação com ou sem exclusão com base em várias propriedades de dispositivo.

**Descrição**
- Aplicado no nível do computador: a mesma política se aplica a qualquer usuário conectado.
- Oferece suporte a MEM e GPO.
- Suporte para '[Propriedades do dispositivo](#device-properties)' conforme listado.
- Para obter mais informações sobre Windows, consulte Como controlar dispositivos USB e outras [mídias removíveis usando o Microsoft Defender para Ponto de Extremidade](control-usb-devices-using-intune.md).

**Plataforma com suporte** - Windows 10

**Descrição**
- Aplicado no nível do computador: a mesma política se aplica a qualquer usuário conectado
- Para obter informações específicas do macOS, consulte [Controle de dispositivo para macOS](mac-device-control-overview.md).
 
**Plataforma com suporte** - macOS Catalina 10.15.4+ (com extensões do sistema habilitadas)

### <a name="removable-storage-access-control"></a>Controle de acesso de armazenamento removível

**Capabilities**
- *Auditoria* Acesso de leitura ou gravação ou execução ao armazenamento removível com base em várias propriedades de dispositivo, com ou sem exclusão.
- *Impedir* Acesso de leitura ou gravação ou execução com ou sem exclusão - Permitir dispositivo específico com base em várias propriedades de dispositivo.

**Descrição**
- Aplicado em máquina ou usuário ou ambos – permite apenas que pessoas específicas que executam o acesso de Leitura/Gravação/Execução a armazenamento removível específico em máquina específica.
- Suporte a MEM OMA-URI e GPO.
- Suporte para '[Propriedades do dispositivo](#device-properties)' conforme listado.
- Para ver o recurso Windows, consulte [Controle de acesso de armazenamento removível.](device-control-removable-storage-access-control.md)

**Plataforma com suporte** - Windows 10

**Descrição**
- Aplicado no nível do computador: a mesma política se aplica a qualquer usuário conectado.
- Para obter informações específicas do macOS, consulte [Controle de dispositivo para macOS](mac-device-control-overview.md).
 
**Plataforma com suporte** - macOS Catalina 10.15.4+ (com extensões do sistema habilitadas)

### <a name="windows-portable-device-access-control"></a>Windows Controle de Acesso a Dispositivo Portátil

**Recursos** - Negar acesso de leitura ou gravação a qualquer Windows [portátil](/windows-hardware/drivers/portable/), por exemplo: Tablet, iPhone.

**Descrição**
- Aplicado em máquina ou usuário ou ambos.
- Suporte a MEM OMA-URI e GPO.

**Plataforma com suporte** - Windows 10

### <a name="endpoint-dlp-removable-storage"></a>Armazenamento removível de DLP do ponto de extremidade

**Recursos** - Auditar ou Avisar ou Impedir que um usuário copie um item ou informações para mídia removível ou dispositivo USB.

**Descrição** - Para obter mais informações sobre Windows, consulte [Learn about Microsoft 365 Endpoint data loss prevention](../../compliance/endpoint-dlp-learn-about.md).

**Plataforma com suporte** - Windows 10

### <a name="bitlocker"></a>BitLocker 

**Capabilities**
- Bloquear dados a serem gravados em unidades removíveis que não BitLocker protegidas.
- Bloquear o acesso a unidades removíveis, a menos que tenham sido criptografadas em um computador pertencente à sua organização
 
**Descrição** - Para obter mais informações sobre Windows, [consulte BitLocker – Unidade Removível Configurações](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).

**Plataforma com suporte** - Windows 10

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

