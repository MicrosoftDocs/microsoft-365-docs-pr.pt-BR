---
title: Microsoft Defender for Endpoint Device Control Printer Protection
description: O Microsoft Defender for Endpoint Device Control Printer Protection impede que as pessoas imprimirem por meio de impressoras não corporativas ou impressora USB não aprovada.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: v-lsaldanha
author: lovina-saldanha
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: 431497ded684543c33d91c49a0da47e92297321f
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809198"
---
# <a name="device-control-printer-protection"></a>Proteção da Impressora de Controle de Dispositivos 

O Microsoft Defender for Endpoint Device Control Printer Protection impede que as pessoas imprimirem por meio de impressoras não corporativas ou impressora USB não aprovada.

## <a name="licensing"></a>Licenciamento 

Antes de começar a proteção de impressora, você deve [confirmar sua assinatura Microsoft 365 .](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) Para acessar e usar a Proteção contra Impressoras, você deve ter o seguinte:

- Microsoft 365 E3 para implantação de funcionalidade/política 
- Microsoft 365 E5 para relatórios 

## <a name="permission"></a>Permissão 

Para a implantação de política no Intune, para implantar a política por meio do OMA-URI, a conta deve ter permissões para criar, editar, atualizar ou excluir perfis de configuração do dispositivo. Você pode criar funções personalizadas ou usar qualquer uma das funções criadas com essas permissões:  

- Função gerenciador de política e perfil. 
- Ou função personalizada com permissões Create/Edit/Update/Read/Delete/View Reports ativas para perfis de Configuração de Dispositivo  
- Ou administrador global

Para ver relatórios de configuração de dispositivo, a conta deve ter permissões de relatórios de exibição. Você pode criar funções personalizadas ou usar as funções integrados com essas permissões:  

- Administrador de segurança global
- Administrador de segurança
- Leitor de segurança 

## <a name="prepare-your-endpoints"></a>Preparar seus pontos de extremidade

Certifique-se de que os Windows 10 dispositivos que você planeja implantar a Proteção de Impressora para atender a esses requisitos.

1. Participe do Programa Insider.

1. As seguintes atualizações do Windows foram instaladas. 

    - Para Windows 1809: instalar o [Windows KB5003217](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46) 
    - Para Windows 1909: instalar Windows Atualizar [KB5003212](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)
    - Para Windows 2004 ou posterior 
    
1. Se você estiver planejando implantar a política por meio da Política de Grupo, o dispositivo deve ser MDATP ingressado; se você estiver planejando implantar a política por meio do MEM, o dispositivo deve ser ingressado no Intune.

## <a name="deploy-device-control-printer-protection-policy"></a>Implantar política de Proteção de Impressora de Controle de Dispositivo

Você pode implantar a política por meio da Política de Grupo ou do Intune.

| Título | Descrição | Suporte A CSP | Suporte a GPO | Suporte baseado no usuário | Suporte baseado em máquina |
|:--|:--|:--|:--|:--|:--|
|**Habilitar restrições de impressão de controle de dispositivo**|Impedir a impressão de pessoas por meio de impressora não corporativa|Sim|Sim|Sim|Sim|
|**Lista de dispositivos de impressão conectados a USB aprovados**\*|Permitir impressora USB específica|Sim|Sim|Sim|Sim|
|||||||

\*Essa política deve ser usada juntamente com **Habilitar Restrições de** Impressão de Controle de Dispositivo
## <a name="deploy-policy-via-intune"></a>Implantar política por meio do Intune 

Para o Intune, atualmente a Proteção de Impressora de Controle de Dispositivo dá suporte apenas ao OMA-URI.

**Cenário 1: Impedir que as pessoas imprimirem por meio de qualquer impressora não corporativa** 

 - Aplicar política sobre máquina: 

    - ./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl 

- Aplicar política sobre o usuário: 

    - ./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser 

A cadeia de caracteres de suporte CSP com `` <enabled/>`` : 

:::image type="content" source="../../media/customeditrow.png" alt-text="linha de edição personalizada":::

**Cenário 2: Permitir impressoras USB aprovadas específicas**

- Aplicar política sobre máquina: 

    - ./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices 

- Aplicar política sobre o usuário: 

    - ./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser  

A cadeia de caracteres de suporte do CSP com impressoras USB aprovadas por meio da propriedade 'ApprovedUsbPrintDevices', `` <enabled/><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872"/>`` exemplo: 

:::image type="content" source="../../media/editrow.png" alt-text="editar linha":::

## <a name="deploy-policy-via-group-policy"></a>Implantar política por meio da Política de Grupo 

Se o dispositivo não estiver ingressado no Intune, você também poderá implantar a política por meio da Política de Grupo. 

**Cenário 1: Impedir que as pessoas imprimirem por meio de qualquer impressora não corporativa** 

- Aplicar política sobre máquina: 

    - Configuração do Computador > Modelos Administrativos > Impressora: Habilitar restrições de impressão de controle de dispositivo 

- Aplicar política sobre o usuário: 

    - Configuração do Usuário > Modelos Administrativos > Painel de Controle > Impressoras: Habilitar restrições de impressão de controle de dispositivo 

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="habilitar restrições de impressão de dispositivo":::
 

**Cenário 2: Permitir impressoras USB aprovadas específicas**

- Aplicar política sobre máquina: 

    - Configuração do Computador > Modelos Administrativos > Impressora: Lista de dispositivos de impressão conectados a USB aprovados 

- Aplicar política sobre o usuário:  

    - Configuração do Usuário > Modelos Administrativos > Painel de Controle > Impressoras: Lista de dispositivos de impressão conectados a USB aprovados 
 
 :::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="lista de dispositivos de impressão usb conectados aprovados":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a>Exibir dados de Proteção de Impressora de Controle de Dispositivo no Portal do Microsoft Defender para Ponto de Extremidade 

O [Microsoft 365 de segurança mostra](https://security.microsoft.com) a impressão bloqueada pela política de Proteção de Impressora de Controle de Dispositivo acima.
 
```sql
DeviceEvents 

|where ActionType == 'PrintJobBlocked' 

| extend parsed=parse_json(AdditionalFields) 

| extend PrintedFile=tostring(parsed.JobOrDocumentName) 

| extend PrintPortName=tostring(parsed.PortName) 

| extend PrinterName=tostring(parsed.PrinterName) 

| extend Policy=tostring(parsed.RestrictionReason)  

| project Timestamp, DeviceId, DeviceName, ActionType, InitiatingProcessAccountName,Policy, PrintedFile, PrinterName, PrintPortName, AdditionalFields 

| order by Timestamp desc 
```

 :::image type="content" source="../../media/device-control-advanced-hunting.png" alt-text="busca avançada":::
