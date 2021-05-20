---
title: Lista de incidentes de API no Microsoft 365 Defender
description: Saiba como listar API incidentes no Microsoft 365 Defender
keywords: lista, incidente, incidentes, api
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
ms.openlocfilehash: 6f0c92371e7e9b7a3348f90df788ee8c3a46374b
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572148"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a>Lista de incidentes de API no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial. A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.


## <a name="api-description"></a>Descrição da API

A lista de incidentes API permite que você classifique através de incidentes para criar uma resposta de segurança cibernética informada. Ele expõe uma coleção de incidentes que foram sinalizados em sua rede, dentro do intervalo de tempo especificado na política de retenção do ambiente. Os incidentes mais recentes são exibidos no topo da lista. Cada incidente contém uma série de alertas relacionados, e suas entidades relacionadas.

A API suporta os seguintes operadores **OData:**

- `$filter` sobre `lastUpdateTime` `createdTime` , `status` , , e `assignedTo` propriedades
- `$top`, com um valor máximo de **100**
- `$skip`

## <a name="limitations"></a>Limitações

1. O tamanho máximo da página é **de 100 incidentes.**
2. A taxa máxima de solicitações é de **50 chamadas por minuto** e **1500 chamadas por hora.**

## <a name="permissions"></a>Permissões

Uma das seguintes permissões é necessária para chamar esta API. Para saber mais, incluindo como escolher permissões, consulte [APIs do Access Microsoft 365 Defender](api-access.md)

Tipo de permissão | Permissão | Nome de exibição de permissão
-|-|-
Aplicativo | Incidente.Read.Todos | Leia todos os incidentes
Aplicativo | Incidente.ReadWrite.Todos | Leia e escreva todos os incidentes
Delegado (conta corporativa ou de estudante) | Incidente.Leia | Leia incidentes
Delegado (conta corporativa ou de estudante) | Incidente.ReadWrite | Leia e escreva incidentes

> [!Note]
> Ao obter um token usando credenciais de usuário:
>
> - O usuário precisa ter permissão de visualização para incidentes no portal.
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

Se for bem sucedido, este método retorna `200 OK` , e uma lista de [incidentes](api-incident.md) no corpo de resposta.

## <a name="schema-mapping"></a>Mapeamento de esquemas

### <a name="incident-metadata"></a>Metadados incidentes

Nome do campo | Descrição | Valor de exemplo
-|-|-
incidenteId | Identificador único para representar o incidente | 924565
redirecionarIncidentId | Só povoado no caso de um incidente estiver sendo agrupado com outro incidente, como parte da lógica de processamento de incidentes. | 924569
incidentName | Valor de sequência disponível para cada incidente. | Atividade de ransomware
criadoTime | Tempo em que o incidente foi criado pela primeira vez. | 2020-09-06T14:46:57.0733333Z
lastUpdateTime | Tempo quando o incidente foi atualizado pela última vez no backend.<br /><br /> Este campo pode ser usado quando você está definindo o parâmetro de solicitação para o intervalo de tempo que os incidentes são recuperados. | 2020-09-06T14:46:57.29Z
assignedTo | Dono do incidente, ou *nulo* se nenhum proprietário for designado. | secop2@contoso.com
classificação | A especificação para o incidente. Os valores da propriedade são: *Desconhecido,* *FalsePositive*, *TruePositive* | Desconhecido
determinação | Especifica a determinação do incidente. Os valores da propriedade são: *NotAvailable*, *Apt*, *Malware,* *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Outros* | Não disponível
status | Categorizar incidentes (como *Ativo*, ou *Resolvido*). Ele pode ajudá-lo a organizar e gerenciar sua resposta a incidentes. | Ativa
severity | Indica o possível impacto sobre os ativos. Quanto maior a gravidade, maior o impacto. Normalmente, itens de maior gravidade requerem a atenção mais imediata.<br /><br />Um dos seguintes valores: *Informativo,* *Baixo*, *Médio e *Alto*. | Médio
tags | Matriz de etiquetas personalizadas associadas a um incidente, por exemplo, para sinalizar um grupo de incidentes com uma característica comum. | \[\]
comentários | Conjunto de comentários criados por secops ao gerenciar o incidente, por exemplo, informações adicionais sobre a seleção de classificação. | \[\]
alerts | Matriz contendo todos os alertas relacionados ao incidente, além de outras informações, como gravidade, entidades envolvidas no alerta e a origem dos alertas. | \[\] (veja detalhes sobre os campos de alerta abaixo)

### <a name="alerts-metadata"></a>Alertas de metadados

Nome do campo | Descrição | Valor de exemplo
-|-|-
alertId | Identificador único para representar o alerta | caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC
incidenteId | Identificador único para representar o incidente este alerta está associado a | 924565
serviceSource | Serviço do que o alerta se origina, como Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity ou Microsoft Defender for Office 365. | MicrosoftCloudAppSecurity
criaçãoTime | Tempo em que o alerta foi criado pela primeira vez. | 2020-09-06T14:46:55.7182276Z
lastUpdatedTime | Tempo em que o alerta foi atualizado pela última vez no backend. | 2020-09-06T14:46:57.2433333Z
tempo resolvido | Tempo em que o alerta foi resolvido. | 2020-09-10T05:22:59Z
firstActivity | Tempo em que o alerta informou pela primeira vez que a atividade foi atualizada no backend.| 2020-09-04T05:22:59Z
title | Breve identifique o valor da sequência disponível para cada alerta. | Atividade de ransomware
descrição | Valor de sequência descrevendo cada alerta. | O usuário Test User2 (testUser2@contoso.com) manipulou 99 arquivos com várias extensões terminando com a extensão incomum *herunterladen*. Este é um número incomum de manipulações de arquivos e é um indicativo de um potencial ataque de ransomware.
category | Visão visual e numérica de quão longe o ataque progrediu ao longo da cadeia de morte. Alinhado ao [quadro mitre ATT&CK™](https://attack.mitre.org/). | Impacto
status | Classificar alertas (como *Novo,* *Ativo* ou *Resolvido*). Ele pode ajudá-lo a organizar e gerenciar sua resposta aos alertas. | Novo
severity | Indica o possível impacto sobre os ativos. Quanto maior a gravidade, maior o impacto. Normalmente, itens de maior gravidade requerem a atenção mais imediata.<br>Um dos seguintes valores: *Informativo,* *Baixo*, *Médio e *Alto*. | Médio
investigaçãoId | A ID de investigação automatizada desencadeada por este alerta. | 1234
investigaçãoEstia | Informações sobre o estado atual da investigação. Um dos seguintes valores: *Desconhecido*, *Encerrado*, *Com sucesso, Remediado*, *Benigno*, *Falho*, *Parcialmente Remediado*, *Execução*, *Pendentes,* *PendentesResource*, *Parcialmente Investigado*, *EncerradoByUser*, *EncerradoBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnupportedAlertType*, *SuppressedAlert*.  | Sem suporteAlertType
classificação | A especificação para o incidente. Os valores da propriedade são: *Desconhecido,* *FalsoPositivo,* *TruePositive* ou *nulo* | Desconhecido
determinação | Especifica a determinação do incidente. Os valores da propriedade são: *NotAvailable*, *Apt*, *Malware,* *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Outros* ou  *nulos* | apto
assignedTo | Dono do incidente, ou *nulo* se nenhum proprietário for designado. | secop2@contoso.com
nome do ator | O grupo de atividades, se houver, está associado a este alerta. | boro
ameaçaFamilyName | Família de ameaças associada a este alerta. | null
mitreTechniques | As técnicas de ataque, alinhadas com a estrutura [de ™ MITRE ATT&CK.](https://attack.mitre.org/) | \[\]
Dispositivos | Todos os dispositivos para onde foram enviados alertas relacionados ao incidente. | \[\] (veja detalhes sobre os campos da entidade abaixo)

### <a name="device-format"></a>Formato do dispositivo

Nome do campo | Descrição | Valor de exemplo
-|-|-
DeviceId | O ID do dispositivo como designado no Microsoft Defender para Endpoint. | 24c222b0b60fe148eeece49ac83910cc6a7ef491
aadDeviceId |  O ID do dispositivo como designado em [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis). Disponível apenas para dispositivos de domínio. | null
dispositivoDnsName | O nome de domínio totalmente qualificado para o dispositivo. | user5cx.middleeast.corp.contoso.com
osPlatform | A plataforma operacional que o dispositivo está executando.| WindowsServer2016
osBuild | A versão de compilação para o SISTEMA OPERACIONAL o dispositivo está em execução. | 14393
rbacGroupName | O grupo [de controle de acesso baseado em papel](/azure/role-based-access-control/overview) (RBAC) associado ao dispositivo. | WDATP-Ring0
firstSeen | Tempo em que o dispositivo foi visto pela primeira vez. | 020-02-06T14:16:01.9330135Z
healthStatus | O estado de saúde do dispositivo. | Ativa
riskScore | A pontuação de risco para o dispositivo. | Alto
Entidades | Todas as entidades identificadas fazem parte ou relacionadas a um determinado alerta. | \[\] (veja detalhes sobre os campos da entidade abaixo)

### <a name="entity-format"></a>Formato da entidade

Nome do campo | Descrição | Valor de exemplo
-|-|-
entidadeType | Entidades identificadas como parte ou relacionadas a um determinado alerta.<br>Os valores das propriedades são: *Usuário*, *Ip,* *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registro* | Usuário
sha1 | Disponível se a entidadeType for *File*.<br>O hash do arquivo para alertas associados a um arquivo ou processo. | 5de83918691aa96ee2ca6d74f0a38fb8d1bd6dd
sha256 | Disponível se a entidadeType for *File*.<br>O hash do arquivo para alertas associados a um arquivo ou processo. | 28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043
fileName | Disponível se a entidadeType for *File*.<br>O nome do arquivo para alertas associados a um arquivo ou processo | Detector.UnitTests.dll
filePath | Disponível se a entidadeType for *File*.<br>O caminho do arquivo para alertas associados a um arquivo ou processo | C: \\ \agent_work_temp\Implantar\SYSTEM\2020-09-06 12_14_54\Out
processId | Disponível se a entidadeType for *Process*. | 24348
processCommandLine | Disponível se a entidadeType for *Process*. | "Seu arquivo está pronto para baixar \_1911150169.exe"
processCreationTime | Disponível se a entidadeType for *Process*. | 2020-07-18T03:25:38.5269993Z
parentProcessId | Disponível se a entidadeType for *Process*. | 16840
parentProcessCreationTime | Disponível se a entidadeType for *Process*. | 2020-07-18T02:12:32.8616797Z
ipAddress | Disponível se a entidadeType for *Ip*. <br>Endereço IP para alertas associados a eventos de rede, como *comunicação a um destino de rede malicioso*. | 62.216.203.204
url | Disponível se a entidadeType é *Url*. <br>URL para alertas associados a eventos de rede, como, *Comunicação para um destino de rede malicioso*. | down.esales360.cn
accountName | Disponível se a entidadeType for *Usuário*. | testUser2
domainName | Disponível se a entidadeType for *Usuário*. | europa.corp.contoso
userSid | Disponível se a entidadeType for *Usuário*. | S-1-5-21-1721254763-462695806-1538882281-4156657
aadUserId | Disponível se a entidadeType for *Usuário*. | fc8f7484-f813-4db2-afab-bc1507913fb6
userPrincipalName | Disponível se a entidadeType for *User* / *MailBox* / *MailMessage*. | testUser2@contoso.com
caixa de correioDisplayName | Disponível se a entidadeType for *MailBox*. | teste Usuário2
mailboxAddress | Disponível se a entidadeType for *User* / *MailBox* / *MailMessage*. | testUser2@contoso.com
clusterBy | Disponível se a entidadeType for  *MailCluster*. | Assunto; P2SenderDomain; Tipo de conteúdo
remetente | Disponível se a entidadeType for *User* / *MailBox* / *MailMessage*. | user.abc@mail.contoso.co.in
destinatário | Disponível se a entidadeType for *MailMessage*. | testUser2@contoso.com
Assunto | Disponível se a entidadeType for *MailMessage*. | \[Atenção EXTERNA \]
deliveryAction | Disponível se a entidadeType for *MailMessage*. | Entregue
securityGroupId | Disponível se a entidadeType for  *SecurityGroup*. | 301c47c8-e15f-4059-ab09-e2ba9ffd372b
securityGroupName | Disponível se a entidadeType for  *SecurityGroup*. | Operadores de configuração de rede
registryHive | Disponível se a entidadeType for  *Registry*. | MÁQUINA LOCAL HKEY \_ \_ |
registroKey | Disponível se a entidadeType for  *Registry*. | SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon
registryValueType | Disponível se a entidadeType for  *Registry*. | Cadeia de caracteres
registroVasse | Disponível se a entidadeType for  *Registry*. | 31-00-00-00
deviceId | O ID, se houver, do dispositivo relacionado à entidade. | 986e5df8b73dacd43c8917d17e523e76b13c75cd

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
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
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
            "comments": [],
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
            "comments": [],
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

- [Acesse as APIs do Microsoft 365 Defender](api-access.md)
- [Conheça os limites e licenciamento da API](api-terms.md)
- [Entenda códigos de erro](api-error-codes.md)
- [Visão geral dos incidentes](incidents-overview.md)
- [APIs de Incidente](api-incident.md)
- [Atualizar a API incidente](api-update-incidents.md)
