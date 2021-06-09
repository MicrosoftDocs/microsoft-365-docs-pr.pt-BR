---
title: Microsoft Defender for Endpoint Device Control Removível Armazenamento Access Control
description: Um passo a passo sobre o Microsoft Defender para Ponto de Extremidade
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
ms.openlocfilehash: fba74990d8e4465f957acda83e66e1dc43a317e8
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841181"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a>Microsoft Defender for Endpoint Device Control Removível Armazenamento Access Control

[!INCLUDE [Prerelease](../includes/prerelease.md)]

O Microsoft Defender for Endpoint Device Control Removível Armazenamento Controle de Acesso permite que você faça a seguinte tarefa:
- auditoria, permitindo ou impedindo o acesso de leitura, gravação ou execução ao armazenamento removível com ou sem exclusão

|Privilégio |Permissão  |
|---------|---------|
|Access    |  Leitura, Gravação, Execução       |
|Modo de ação    |    Auditar, Permitir, Impedir     |
|Suporte A CSP   |   Sim      |
|Suporte a GPO    |   Sim      |
|Suporte baseado no usuário     |   Sim      |
|Suporte baseado em máquina    |    Sim     |

## <a name="prepare-your-endpoints"></a>Preparar seus pontos de extremidade

Implantar controle de acesso Armazenamento removível em dispositivos Windows 10 que tenham o Cliente Anti-malware Versão **4.18.2103.3 ou posterior**.
1. **4.18.2104 ou** posterior : Adicionar SerialNumberId, VID_PID, suporte a GPO baseado em filepath

2. **4.18.2105** ou posterior : Adicione suporte a curinga para HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, a combinação de usuário específico em máquina específica, SSD removêvel (um SSD do SanDisk Extreme)/suporte A USB Attached SCSI (UAS)

:::image type="content" source="images/powershell.png" alt-text="A interface do PowerShell":::

## <a name="policy-properties"></a>Propriedades de política

Você pode usar as seguintes propriedades para criar um grupo de armazenamento removível:

**Nome da propriedade: ID do grupo**

1. Descrição: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), uma ID exclusiva, representa o grupo e será usado na política.

**Nome da propriedade: DescriptorIdList**

1. Descrição: listar as propriedades do dispositivo que você deseja usar para cobrir no grupo.
Listar as propriedades do dispositivo que você deseja usar para cobrir no grupo.
Para cada propriedade de dispositivo, consulte **a seção Propriedades do Dispositivo** acima para obter mais detalhes.

1. Opções:
    - ID principal
        - RemovableMediaDevices
        - CdRomDevices
    - DeviceId
    - HardwareId
    - InstancePathId: InstancePathId é uma cadeia de caracteres que identifica exclusivamente o dispositivo no sistema, por exemplo, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0. O número no final (por exemplo, **&0**) representa o slot disponível e pode mudar de dispositivo para dispositivo. Para melhores resultados, use um curinga no final. Por exemplo, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611*
    - FriendlyNameId
    - SerialNumberId
    - VID
    - PID
    - VID_PID
        - 0751_55E0: corresponder a esse par exato do VID/PID
        - _55E0: corresponder qualquer mídia com PID=55E0
        - 0751_: corresponder qualquer mídia com VID=0751
        
**Nome da propriedade: MatchType** 

1. Descrição: quando há várias propriedades de dispositivo sendo usadas no DescriptorIDList, MatchType define a relação.

1. Opções:
    - MatchAll: Quaisquer atributos sob o DescritorIdList serão **e** relação; por exemplo, se o administrador colocar DeviceID e InstancePathID, para cada USB conectado, o sistema verificará se a USB atende aos dois valores.

    - MatchAny: Os atributos no DescriptorIdList serão **Ou** relação; por exemplo, se o administrador colocar DeviceID e InstancePathID, para cada USB conectado, o sistema fará a imposição desde que a USB tenha um valor **DeviceID** idêntico ou **InstanceID.**

A seguir estão as propriedades da política de controle de acesso:

**Nome da propriedade: PolicyRuleId**

1. Descrição: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), uma ID exclusiva, representa a política e será usada no relatório e na solução de problemas.

**Nome da propriedade: IncludedIdList**

1. Descrição: os grupos ao que a política será aplicada. Se vários grupos são adicionados, a política será aplicada a qualquer mídia em todos esses grupos.

1. Opções: a ID/GUID do grupo deve ser usada nesta instância.

O exemplo a seguir mostra o uso de GroupID:

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

**Nome da propriedade: ExcludedIDList**

1. Descrição: os grupos aos que a política não será aplicada.
1. Opções: a ID/GUID do grupo deve ser usada nesta instância.

**Nome da propriedade: ID de entrada**

1. Descrição: Um PolicyRule pode ter várias entradas; cada entrada com um GUID exclusivo informa ao Controle de Dispositivo uma restrição.

**Nome da propriedade: Type**

1. Descrição: define a ação para os grupos de armazenamento removíveis em IncludedIDList.
    - Imposição: Permitir ou Negar
    - Auditoria: AuditAllowed ou AuditDenied 
1. Opções:
    - Permitir
    - Negar
    - AuditAllowed: define notificação e evento quando o acesso é permitido
    - AuditDenied: define a notificação e o evento quando o acesso é negado; tem que trabalhar em conjunto com **a entrada Negar.**

Quando houver tipos de conflito para a mesma mídia, o sistema aplicará o primeiro na política. Um exemplo de tipo de conflito é **Permitir** e **Negar.**

**Nome da propriedade: Opções**

1. Descrição: define se a notificação deve ser exibida ou não.

   :::image type="content" source="images/device-status.png" alt-text="A tela na qual o status do dispositivo pode ser visto":::

1. Opções: 0-4. Quando Type Allow ou Deny estiver selecionado:

   - 0: nothing
   - 4: **desabilite AuditAllowed** e **AuditDenied** para esta Entrada. Mesmo que **Block** aconteça e **AuditDenied** estiver configurada, o sistema não mostrará a notificação.

   Quando Type **AuditAllowed** ou **AuditDenied** estiver selecionado:

   - 0: nothing
   - 1: mostrar notificação
   - 2: enviar evento
   - 3: mostrar evento de notificação e envio

**Nome da propriedade: AccessMask**

1. Descrição: define o acesso.

1. Opções: 1 a 7:
    - 1: Leitura
    - 2: Gravar
    - 3: Leitura e gravação
    - 4: Execute
    - 5: Leitura e execução
    - 6: Gravar e executar
    - 7: Leitura e gravação e execução

## <a name="common-removable-storage-access-control-scenarios"></a>Cenários comuns de controle de acesso Armazenamento removível

Para ajudar a familiarizá-lo com o Microsoft Defender for Endpoint Removable Armazenamento Access Control, reunimos alguns cenários comuns para você seguir.

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a>Cenário 1: Impedir o acesso de Gravação e Execução a todos, mas permitir USBs aprovados específicos

1. Criar grupos
    1. Grupo 1: Qualquer armazenamento removível e CD/DVD. Um exemplo de armazenamento removível e CD/DVD é: Grupo **9b28fae8-72f7-4267-a1a5-685f747a7146** no exemplo [Any Removable Armazenamento and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.
    
    2. Grupo 2: USBs aprovados com base nas propriedades do dispositivo. Um exemplo para este caso de uso é: ID de instância – Grupo **65fa649a-a111-4912-9294-fb6337a25038** no exemplo [usbs aprovados Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) arquivo.

    > [!NOTE]
    > Você precisa substituir `&` `&amp;` no valor.

2. Criar uma política
    1. Política 1: Bloquear o Acesso de Gravação e Execução, mas permitir USBs aprovados. Um exemplo para este caso de uso é: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** no exemplo Cenário 1 Bloquear Gravação e Executar Acesso, mas permitir [USBs aprovados .xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) arquivo.
    
    2. Política 2: Auditar o acesso de Gravação e Execução a USBs permitidos. Um exemplo para este caso de uso é: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** no exemplo [Cenário 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a>Cenário 2: AuditAr o acesso de Gravação e Execução a todos, mas bloquear USBs não aprovados específicos

1. Criar grupos
    1. Grupo 1: Qualquer armazenamento removível e CD/DVD. Um exemplo para este caso de uso é: Grupo **9b28fae8-72f7-4267-a1a5-685f747a7146** no exemplo [Any Removable Armazenamento and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.
    
    2. Grupo 2: USBs não aprovados com base nas propriedades do dispositivo, por exemplo, ID do fornecedor/ID do produto, Nome Amigável – **Grupo 65fa649a-a111-4912-9294-fb6337a25038 no** exemplo de [usbs Group.xmlnão aprovados.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 

    > [!NOTE]
    > Você precisa substituir `&` `&amp;` no valor.

2. Criar uma política
    1. Política 1: Bloquear o acesso de Gravação e Execução a todos, mas bloquear USBs não aprovados específicos. Um exemplo desse caso de uso é: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** no exemplo Scenario 2 Audit Write and Execute access to all but block specific [unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.
    
    2. Política 2: Auditar o acesso de gravação e execução a outras pessoas. Um exemplo desse caso de uso é: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** no exemplo [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.

## <a name="deploying-and-managing-policy-via-group-policy"></a>Implantação e gerenciamento de política por meio da Política de Grupo

O recurso Controle de Acesso Armazenamento removível permite aplicar a política por meio da Política de Grupo a usuários ou dispositivos ou ambos.

### <a name="licensing"></a>Licenciamento

Antes de começar a Armazenamento Controle de Acesso [Removível,](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)você deve confirmar sua assinatura Microsoft 365 . Para acessar e usar o Controle de Acesso Armazenamento removível, você deve ter Microsoft 365 E3 ou Microsoft 365 E5.

### <a name="deploying-policy-via-group-policy"></a>Implantando política por meio da Política de Grupo

1. Combine todos os grupos `<Groups>` `</Groups>` em um arquivo xml. 

    A imagem a seguir ilustra o exemplo do Cenário 1: Impedir o acesso de Gravação e Execução a todos, mas permitir [USBs aprovados específicos.](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="A tela exibindo as configurações que permitem USBs aprovados específicos em dispositivos":::
    
2. Combine todas as regras `<PolicyRules>` `</PolicyRules>` em um arquivo xml. 

    Se você quiser restringir um usuário específico, use a propriedade SID na Entrada. Se não houver SID na Entrada de política, a Entrada será aplicada a todas as instâncias de logon do computador.
    
    A imagem a seguir ilustra o uso da propriedade SID e um exemplo do Cenário 1: Impedir o acesso de Gravação e Execução a todos, mas permitir USBs aprovados [específicos.](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="A tela exibindo um código que indica o uso do atributo de propriedade SID":::

3. Salve arquivos XML de regra e grupo na pasta de compartilhamento de rede e coloque o caminho da pasta de compartilhamento de rede na configuração da Política de Grupo: Configuração do Computador -> Modelos **Administrativos -> Windows Componentes -> Microsoft Defender Antivírus -> Controle de Dispositivo: "Definir** grupos de política de controle de dispositivo" e "Definir regras de política de controle de dispositivo" .

    - O computador de destino deve ser capaz de acessar o compartilhamento de rede para ter a política. No entanto, depois que a política é lida, a conexão de compartilhamento de rede não é mais necessária, mesmo após a reinicialização do computador.

    :::image type="content" source="images/device-control.png" alt-text="A tela controle de dispositivo":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a>Implantação e gerenciamento de política por meio do Intune OMA-URI

O recurso Controle de Acesso Armazenamento removível permite aplicar a política por meio do OMA-URI a usuários ou dispositivos ou ambos.

### <a name="licensing"></a>Licenciamento

Antes de começar a Armazenamento Controle de Acesso [Removível,](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)você deve confirmar sua assinatura Microsoft 365 . Para acessar e usar o Controle de Acesso Armazenamento removível, você deve ter Microsoft 365 E3 ou Microsoft 365 E5.

### <a name="permission"></a>Permissão

Para implantação de política no Intune, a conta deve ter permissões para criar, editar, atualizar ou excluir perfis de configuração de dispositivo. Você pode criar funções personalizadas ou usar qualquer uma das funções criadas com essas permissões.

- Função de Gerente de Política e Perfil
- Função personalizada com permissões Create/Edit/Update/Read/Delete/View Reports ativas para perfis de Configuração de Dispositivo
- Administrador global

### <a name="deploying-policy-via-oma-uri"></a>Implantando política por meio do OMA-URI

**Microsoft Endpoint Manager centro de administração ( https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**

1. Para cada Grupo, crie uma regra OMA-URI:
    - OMA-URI: 

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData

      Por exemplo, para **qualquer grupo de CD/DVD e** armazenamento removível no exemplo, o link deve ser:

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData

    - Tipo de dados: cadeia de caracteres (arquivo XML)
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="O arquivo xml do tipo de dados STRING":::

2. Para cada política, também crie um OMA-URI:

    - OMA-URI: 

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData

      Por exemplo, para a regra Bloquear Gravação e Executar Acesso, mas permitir **USBs** aprovados no exemplo, o link deve ser: 

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.

    - Tipo de dados: cadeia de caracteres (arquivo XML)

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="Exibição de arquivo XML para o tipo de dados STRING":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a>Implantando e gerenciando a política usando a interface do usuário do Intune

Esse recurso (no centro de administração do Microsoft Endpoint Manager ( > Dispositivos > Perfis de configuração > Criar perfil > Plataforma: Windows 10 e posterior do & Profile: Device Control) ainda não está https://endpoint.microsoft.com/) disponível. 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>Exibir dados do Controle de Dispositivo Removível Armazenamento Access Control no Microsoft Defender para Ponto de Extremidade

O Microsoft 365 de segurança mostra o armazenamento removível bloqueado pelo Controle de Dispositivo Removível Armazenamento Controle de Acesso. Para acessar a Microsoft 365, você deve ter a seguinte assinatura:

- Microsoft 365 relatório do E5

```kusto
//events triggered by RemovableStoragePolicyTriggered
DeviceEvents
| where ActionType == &quot;RemovableStoragePolicyTriggered&quot; 
| extend parsed=parse_json(AdditionalFields) 
| extend RemovableStorageAccess = tostring(parsed.RemovableStorageAccess)  
| extend RemovableStoragePolicyVerdict = tostring(parsed.RemovableStoragePolicyVerdict)  
| extend MediaBusType = tostring(parsed.BusType)  
| extend MediaClassGuid = tostring(parsed.ClassGuid)
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaDeviceId = tostring(parsed.DeviceId) 
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId) 
| extend MediaName = tostring(parsed.MediaName) 
| extend RemovableStoragePolicy = tostring(parsed.RemovableStoragePolicy)  
| extend MediaProductId = tostring(parsed.ProductId)  
| extend MediaVendorId = tostring(parsed.VendorId)  
| extend MediaSerialNumber = tostring(parsed.SerialNumber)  
| extend MediaVolume = tostring(parsed.Volume)  
| project Timestamp, DeviceId, DeviceName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber, MediaVolume 
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="A tela que representa o bloqueio do armazenamento removível":::
