---
title: Listar a API de incidentes no Microsoft 365 Defender
description: Saiba como listar a API de incidentes no Microsoft 365 Defender
keywords: lista, incidentes, incidentes, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 4488a552475121adc4a439106bc0bf0d97cb509a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052844"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a>Listar a API de incidentes no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial. A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.


## <a name="api-description"></a>Descrição da API

A API de incidentes de lista permite classificar por meio de incidentes para criar uma resposta de segurança cibernética informada. Ele expõe uma coleção de incidentes que foram sinalizados em sua rede, dentro do intervalo de tempo especificado na política de retenção do ambiente. Os incidentes mais recentes são exibidos na parte superior da lista. Cada incidente contém uma matriz de alertas relacionados e suas entidades relacionadas.

A API dá suporte aos seguintes **operadores OData:**

- `$filter`nas `lastUpdateTime` propriedades , `createdTime` , `status` e `assignedTo`
- `$top`, com um valor máximo **de 100**
- `$skip`

## <a name="limitations"></a>Limitações

1. O tamanho máximo da página **é de 100 incidentes.**
2. A taxa máxima de solicitações **é de 50 chamadas por minuto** e **1500 chamadas por hora.**

## <a name="permissions"></a>Permissões

Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Access Microsoft 365 Defender APIs](api-access.md)

Tipo de permissão | Permissão | Nome de exibição de permissão
-|-|-
Aplicativo | Incident.Read.All | Ler todos os incidentes
Aplicativo | Incident.ReadWrite.All | Ler e gravar todos os incidentes
Delegada (conta corporativa ou de estudante) | Incident.Read | Ler incidentes
Delegada (conta corporativa ou de estudante) | Incident.ReadWrite | Incidentes de leitura e gravação

> [!Note]
> Ao obter um token usando credenciais de usuário:
>
> - O usuário precisa ter permissão de exibição para incidentes no portal.
> - A resposta incluirá apenas incidentes aos que o usuário está exposto.

## <a name="http-request"></a>Solicitação HTTP

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Nome | Tipo | Descrição
-|-|-
Autorização | Cadeia de caracteres | Portador {token}. **Required**


## <a name="request-body"></a>Corpo da solicitação

Nenhum.

## <a name="response"></a>Resposta

Se tiver êxito, este método `200 OK` retornará e uma lista [de incidentes](api-incident.md) no corpo da resposta.

## <a name="schema-mapping"></a>Mapeamento de esquema

### <a name="incident-metadata"></a>Metadados de incidente

Nome do campo | Descrição | Valor de exemplo
-|-|-
incidentId | Identificador exclusivo para representar o incidente | 924565
redirectIncidentId | Somente populado no caso de um incidente estar sendo agrupado com outro incidente, como parte da lógica de processamento de incidentes. | 924569
incidentName | Valor de cadeia de caracteres disponível para cada incidente. | Atividade ransomware
createdTime | Hora em que o incidente foi criado pela primeira vez. | 2020-09-06T14:46:57.0733333Z
lastUpdateTime | Hora em que o incidente foi atualizado pela última vez no back-end.<br /><br /> Esse campo pode ser usado quando você estiver definindo o parâmetro request para o intervalo de tempo em que os incidentes são recuperados. | 2020-09-06T14:46:57.29Z
assignedTo | Proprietário do incidente ou *nulo* se nenhum proprietário for atribuído. | secop2@contoso.com
classificação | A especificação do incidente. Os valores da propriedade são: *Unknown*, *FalsePositive*, *TruePositive* | Desconhecido
determinação | Especifica a determinação do incidente. Os valores da propriedade são: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel,* *SecurityTesting,* *UnwantedSoftware*, *Other* | NotAvailable
status | Categorizar incidentes (como *Ativo* ou *Resolvido).* Ele pode ajudá-lo a organizar e gerenciar sua resposta a incidentes. | Ativo
severity | Indica o possível impacto nos ativos. Quanto maior a gravidade, maior será o impacto. Normalmente, itens de severidade mais altos exigem a atenção mais imediata.<br /><br />Um dos seguintes valores: *Informational*, *Low*, *Medium e *High*. | Médio
tags | Matriz de marcas personalizadas associadas a um incidente, por exemplo, para sinalizar um grupo de incidentes com uma característica comum. | \[\]
alerts | Matriz contendo todos os alertas relacionados ao incidente, além de outras informações, como gravidade, entidades envolvidas no alerta e a origem dos alertas. | \[\] (consulte detalhes sobre campos de alerta abaixo)

### <a name="alerts-metadata"></a>Metadados de alertas

Nome do campo | Descrição | Valor de exemplo
-|-|-
alertId | Identificador exclusivo para representar o alerta | caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC
incidentId | Identificador exclusivo para representar o incidente ao que esse alerta está associado | 924565
serviceSource | Serviço de origem do alerta, como o Microsoft Defender para Ponto de Extremidade, o Microsoft Cloud App Security, o Microsoft Defender para Identidade ou o Microsoft Defender para Office 365. | MicrosoftCloudAppSecurity
creationTime | Hora em que o alerta foi criado pela primeira vez. | 2020-09-06T14:46:55.7182276Z
lastUpdatedTime | Hora em que o alerta foi atualizado pela última vez no back-end. | 2020-09-06T14:46:57.2433333Z
resolvedTime | Hora em que o alerta foi resolvido. | 2020-09-10T05:22:59Z
firstActivity | Hora em que o alerta relatou pela primeira vez que a atividade foi atualizada no back-end.| 2020-09-04T05:22:59Z
title | Breve identificação do valor da cadeia de caracteres disponível para cada alerta. | Atividade ransomware
descrição | Valor de cadeia de caracteres que descreve cada alerta. | O usuário Test User2 (testUser2@contoso.com) manipulou 99 arquivos com várias extensões terminando com a extensão *incomum herunterladen*. Esse é um número incomum de manipulações de arquivos e indica um possível ataque de ransomware.
category | Exibição visual e numérica da distância em que o ataque progrediu ao longo da cadeia de morte. Alinhado ao [MITRE ATT&CK™ framework](https://attack.mitre.org/). | Impacto
status | Categorizar alertas (como *Novo,* *Ativo* ou *Resolvido).* Ele pode ajudá-lo a organizar e gerenciar sua resposta a alertas. | Novo
severity | Indica o possível impacto nos ativos. Quanto maior a gravidade, maior será o impacto. Normalmente, itens de severidade mais altos exigem a atenção mais imediata.<br>Um dos seguintes valores: *Informational*, *Low*, *Medium e *High*. | Médio
investigationId | A ID de investigação automatizada disparada por esse alerta. | 1234
investigationState | Informações sobre o status atual da investigação. Um dos seguintes valores: *Unknown* *,* Terminated , *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Enued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*. | UnsupportedAlertType
classificação | A especificação do incidente. Os valores da propriedade são: *Unknown*, *FalsePositive*, *TruePositive* ou *null* | Desconhecido
determinação | Especifica a determinação do incidente. Os valores da propriedade são: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel,* *SecurityTesting,* *UnwantedSoftware*, *Other* ou  *null* | Apt
assignedTo | Proprietário do incidente ou *nulo* se nenhum proprietário for atribuído. | secop2@contoso.com
actorName | O grupo de atividades, se for o caso, o associado a esse alerta. | BORON
threatFamilyName | Família de ameaças associada a esse alerta. | null
mitreTechniques | As técnicas de ataque, conforme alinhadas com o [MITRE ATT](https://attack.mitre.org/)&CK ™ estrutura. | \[\]
devices | Todos os dispositivos onde os alertas relacionados ao incidente foram enviados. | \[\] (consulte detalhes sobre os campos de entidade abaixo)

### <a name="device-format"></a>Formato de dispositivo

Nome do campo | Descrição | Valor de exemplo
-|-|-
DeviceId | A ID do dispositivo conforme designado no Microsoft Defender ATP. | 24c222b0b0b60fe148eeece49ac83910cc6a7ef491
aadDeviceId |  A ID do dispositivo conforme designado no [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis). Disponível apenas para dispositivos ingressados no domínio. | null
deviceDnsName | O nome de domínio totalmente qualificado para o dispositivo. | user5cx.middleeast.corp.contoso.com
osPlatform | A plataforma do sistema operacional que o dispositivo está executando.| WindowsServer2016
osBuild | A versão de com build do sistema operacional em execução do dispositivo. | 14393
rbacGroupName | O grupo de controle [de acesso](/azure/role-based-access-control/overview) baseado em função (RBAC) associado ao dispositivo. | WDATP-Ring0
firstSeen | Hora em que o dispositivo foi visto pela primeira vez. | 2020-02-06T14:16:01.9330135Z
healthStatus | O estado de saúde do dispositivo. | Ativo
riskScore | A pontuação de risco do dispositivo. | Alto
entidades | Todas as entidades identificadas para fazer parte ou relacionadas a um determinado alerta. | \[\] (consulte detalhes sobre os campos de entidade abaixo)

### <a name="entity-format"></a>Formato de entidade

Nome do campo | Descrição | Valor de exemplo
-|-|-
entityType | Entidades identificadas para fazer parte ou relacionadas a um determinado alerta.<br>Os valores das propriedades são: *User*, *Ip*, *Url*, File , *Process*, *MailBox*, *MailMessage,* *MailCluster*, *Registry*  | User
sha1 | Disponível se entityType for *File*.<br>O hash de arquivo para alertas associados a um arquivo ou processo. | 5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd
sha256 | Disponível se entityType for *File*.<br>O hash de arquivo para alertas associados a um arquivo ou processo. | 28cb017dfc99073a1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043
fileName | Disponível se entityType for *File*.<br>O nome do arquivo para alertas associados a um arquivo ou processo | Detector.UnitTests.dll
filePath | Disponível se entityType for *File*.<br>O caminho do arquivo para alertas associados a um arquivo ou processo | C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out
processId | Disponível se entityType for *Process*. | 24348
processCommandLine | Disponível se entityType for *Process*. | "Seu arquivo está pronto para baixar \_1911150169.exe"
processCreationTime | Disponível se entityType for *Process*. | 2020-07-18T03:25:38.5269993Z
parentProcessId | Disponível se entityType for *Process*. | 16840
parentProcessCreationTime | Disponível se entityType for *Process*. | 2020-07-18T02:12:32.8616797Z
ipAddress | Disponível se entityType for *Ip*. <br>Endereço IP para alertas associados a eventos de rede, como *Comunicação a um destino de rede mal-intencionado.* | 62.216.203.204
url | Disponível se entityType for *Url*. <br>URL para alertas associados a eventos de rede, como Comunicação *a um destino de rede mal-intencionado.* | down.esales360.cn
accountName | Disponível se entityType for *User*. | testUser2
domainName | Disponível se entityType for *User*. | europe.corp.contoso
userSid | Disponível se entityType for *User*. | S-1-5-21-1721254763-462695806-1538882281-4156657
aadUserId | Disponível se entityType for *User*. | fc8f7484-f813-4db2-afab-bc1507913fb6
userPrincipalName | Disponível se entityType for *User* / *MailBox* / *MailMessage*. | testUser2@contoso.com
mailboxDisplayName | Disponível se entityType for *MailBox*. | test User2
mailboxAddress | Disponível se entityType for *User* / *MailBox* / *MailMessage*. | testUser2@contoso.com
clusterBy | Disponível se entityType for  *MailCluster*. | Assunto; P2SenderDomain; ContentType
sender | Disponível se entityType for *User* / *MailBox* / *MailMessage*. | user.abc@mail.contoso.co.in
destinatário | Disponível se entityType for *MailMessage*. | testUser2@contoso.com
assunto | Disponível se entityType for *MailMessage*. | \[Atenção \] EXTERNA
deliveryAction | Disponível se entityType for *MailMessage*. | Entregue
securityGroupId | Disponível se entityType for  *SecurityGroup*. | 301c47c8-e15f-4059-ab09-e2ba9ffd372b
securityGroupName | Disponível se entityType for  *SecurityGroup*. | Operadores de Configuração de Rede
registryHive | Disponível se entityType for  *Registry*. | MÁQUINA LOCAL HKEY \_ \_ |
registryKey | Disponível se entityType for  *Registry*. | SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon
registryValueType | Disponível se entityType for  *Registry*. | Cadeia de caracteres
registryValue | Disponível se entityType for  *Registry*. | 31-00-00-00
deviceId | A ID, se for o caso, do dispositivo relacionado à entidade. | 986e5df8b73dacd43c8917d17e523e76b13c75cd

## <a name="example"></a>Exemplo

**Solicitação**

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

**Response**

```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Windows Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-articles"></a>Artigos relacionados

- [Acessar as APIs do Microsoft 365 Defender](api-access.md)
- [Saiba mais sobre limites de API e licenciamento](api-terms.md)
- [Compreender códigos de erro](api-error-codes.md)
- [Visão geral dos incidentes](incidents-overview.md)
- [APIs de Incidente](api-incident.md)
- [Atualizar API de incidentes](api-update-incidents.md)