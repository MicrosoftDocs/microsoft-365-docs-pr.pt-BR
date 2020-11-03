---
title: Listar a API de incidentes no Microsoft 365 defender
description: Saiba como listar a API de incidentes no Microsoft 365 defender
keywords: lista, incidente, incidentes, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 9da6fdf04fd22767f3984229b7862f02b8293067
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844991"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a>Listar a API de incidentes no Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**

- Microsoft 365 defender

> [!IMPORTANT]
> Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.


## <a name="api-description"></a>Descrição da API

A API de incidentes permite que você classifique por meio de incidentes para priorizar e criar uma resposta cybersecurity informada. Ele expõe uma coleção de incidentes que foram sinalizados de dispositivos, contas de email e usuários em sua rede, dentro do intervalo de tempo especificado em sua política de retenção de ambiente. Os incidentes mais recentes são exibidos na parte superior da lista. Cada incidente contém uma matriz de alertas relacionados e suas entidades relacionadas.

<br>A API oferece suporte aos seguintes operadores **OData** :
<br>```$filter``` nas ```lastUpdateTime``` Propriedades: ```createdTime``` , ```status``` e ```assignedTo``` .
<br>```$top``` com o valor máximo de **100**
<br>```$skip```

## <a name="limitations"></a>Limitações

1. O tamanho máximo da página é de **100 incidentes**.
2. A taxa máxima de solicitações é de **50 chamadas por minuto** e **1500 de chamadas por hora**.

## <a name="permissions"></a>Permissões

Uma das seguintes permissões é necessária para chamar esta API. Para saber mais, incluindo como escolher permissões, consulte [Access Microsoft 365 defender APIs](api-access.md)

Tipo de permissão |   Permissão  |   Nome para exibição da permissão
:---|:---|:---
Aplicativo |   Incident. Read. All | ' Ler todos os incidentes '
Aplicativo |   Incident. ReadWrite. All | ' Ler e gravar todos os incidentes '
Delegada (conta corporativa ou de estudante) | Incidente. Read | "Ler incidentes"
Delegada (conta corporativa ou de estudante) | Incident. ReadWrite | ' Ler e gravar incidentes '

> [!Note]
> Ao obter um token usando as credenciais do usuário:
> - O usuário precisa ter permissão de exibição para incidentes no Portal.
> - A resposta só incluirá incidentes aos quais o usuário está exposto.

## <a name="http-request"></a>Solicitação HTTP

```
GET /api/incidents
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Nome | Tipo | Descrição
:---|:---|:---
Autorização | String | Portador {token}. **Obrigatório**.


## <a name="request-body"></a>Corpo da solicitação
Nenhum.

## <a name="response"></a>Resposta
Se tiver êxito, este método retornará 200 OK e uma lista de [incidentes](api-incident.md) no corpo da resposta.

## <a name="schema-mapping"></a>Mapeamento de esquema

| Nome do campo                                | Descrição                                                                                                                                                                                                                                                                                                                                                                                | Valor de exemplo                                                                                                                                                                                                                                     |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Metadados de incidentes**                         |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| incidentalid                                | Identificador exclusivo para representar o incidente.                                                                                                                                                                                                                                                                                                                                                | 924565                                                                                                                                                                                                                                            |
| redirectIncidentId                        | Apenas preenchido no caso de um incidente ser agrupado com outro incidente, como parte da lógica de processamento de incidentes.                                                                                                                                                                                                                                                           | 924569                                                                                                                                                                                                                                            |
| incidentalname                              | Valor de cadeia de caracteres disponível para cada incidente.                                                                                                                                                                                                                                                                                                                                                  | Atividade de ransomware                                                                                                                                                                                                                               |
| createdtime                               | Hora em que o incidente foi criado pela primeira vez.                                                                                                                                                                                                                                                                                                                                                      | 2020-09-06T14:46:57.0733333 Z                                                                                                                                                                                                                      |
| lastUpdateTime                            | Hora em que o incidente foi atualizado pela última vez no back-end.<br> Este campo pode ser usado ao definir o parâmetro de solicitação para o intervalo de tempo em que os incidentes são recuperados.                                                                                                                                                                                                                      | 2020-09-06T14:46:57.29 Z                                                                                                                                                                                                                           |
| assignedTo                                | Proprietário do incidente ou *nulo* se nenhum proprietário for atribuído.                                                                                                                                                                                                                                                                                                                         | secop2@contoso.com                                                                                                                                                                                                |
| classificação                            | A especificação do incidente. Os valores da propriedade são: *desconhecido* , *FalsePositive* , *TruePositive*                                                                                                                                                                                                                                                                           | Desconhecido                                                                                                                                                                                                                                           |
| determinação                             | Especifica a determinação do incidente. Os valores de propriedade são: *não disponível* , *apt* , *malware* , *SecurityPersonnel* , *SecurityTesting* , *UnwantedSoftware* , *outros*                                                                                                                                                                                                                | Não disponível                                                                                                                                                                                                                                      |
| status                                    | Categorizar incidentes (como *ativos* ou *resolvidos* ). Isso ajuda a organizar e gerenciar sua resposta a incidentes.                                                                                                                                                                                                                                                                  | Ativo                                                                                                                                                                                                                                            |
| severity                                  | Indica o possível impacto nos ativos. Quanto maior a gravidade, maior o impacto. Normalmente, os itens de maior severidade exigem a atenção mais imediata.<br>Um dos seguintes valores: *informativo* , *baixo* , * médio e *alto*.                                                                                                                                | Médio                                                                                                                                                                                                                                            |
| categorias                                      | Matriz de marcas personalizadas associadas a um incidente, por exemplo, para sinalizar um grupo de incidentes com uma característica comum.                                                                                                                                                                                                                                                                  | \[\]                                                                                                                                                                                                                                              |
| alerts                                    | Matriz de todos os alertas relacionados ao incidente e outras informações, como gravidade, entidades que estavam envolvidas no alerta, a fonte dos alertas.                                                                                                                                                                                                                     | \[\] (veja detalhes nos campos de alerta abaixo)                                                                                                                                                                                                          |
| **Metadados de alertas**                           |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| Alertid                                   | Identificador exclusivo para representar o alerta                                                                                                                                                                                                                                                                                                                                                   | caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC                                                                                                                                                                                                            |
| incidentalid                                | Identificador exclusivo para representar o incidente ao qual este alerta está associado                                                                                                                                                                                                                                                                                                                  | 924565                                                                                                                                                                                                                                            |
| Unificação de serviço                             | Serviço do qual o alerta se origina, como o Microsoft defender para ponto de extremidade, o Microsoft Cloud app Security, o Microsoft defender para identidade ou o Microsoft defender para Office 365.                                                                                                                                                                                                                                                                     | MicrosoftCloudAppSecurity                                                                                                                                                                                                                         |
| creationTime                              | Hora em que o alerta foi criado pela primeira vez.                                                                                                                                                                                                                                                                                                                                                         | 2020-09-06T14:46:55.7182276 Z                                                                                                                                                                                                                      |
| lastUpdatedtime                           | Hora em que o alerta foi atualizado pela última vez no back-end.                                                                                                                                                                                                                                                                                                                                           | 2020-09-06T14:46:57.2433333 Z                                                                                                                                                                                                                      |
| reresolvitime                              | Hora em que o alerta foi resolvido.                                                                                                                                                                                                                                                                                                                                                              | 2020-09-10T05:22:59Z                                                                                                                                                                                                                              |
| firstActivity                             | Hora em que o alerta primeiro informou que a atividade foi atualizada no back-end.                                                                                                                                                                                                                                                                                                                             | 2020-09-04T05:22:59Z                                                                                                                                                                                                                              |
| title                                     | Valor de cadeia de caracteres de identificação rápida disponível para cada alerta.                                                                                                                                                                                                                                                                                                                                                     | Atividade de ransomware                                                                                                                                                                                                                               |
| description                               | Valor da cadeia de caracteres descrevendo cada alerta.                                                                                                                                                                                                                                                                                                                                                        | O testUser2@contoso.com de teste de usuário (Usuário2) manipulou 99 arquivos com várias extensões terminando com a extensão *Herunterladen* incomuns. Esse é um número incomum de manipulação de arquivos e indica um possível ataque de ransomware. |
| category                                  | Visual e o modo de exibição numérico de quanto o ataque evoluiu ao longo da cadeia de Kill. Alinhado com o [Mitre ATT&CK™ Framework](https://attack.mitre.org/).                                                                                                                                                                                                                           | Impacto                                                                                                                                                                                                                                            |
| status                                    | Categorizar alertas (como *novos* , *ativos* ou *resolvidos* ). Isso ajuda a organizar e gerenciar sua resposta a alertas.                                                                                                                                                                                                                                                                   | Novo                                                                                                                                                                                                                                               |
| severity                                  | Indica o possível impacto nos ativos. Quanto maior a gravidade, maior o impacto. Normalmente, os itens de maior severidade exigem a atenção mais imediata.<br>Um dos seguintes valores: *informativo* , *baixo* , * médio e *alto*.                                                                                                                                   | Médio                                                                                                                                                                                                                                            |
| investigaid                           | A ID de investigação automatizada disparada por esse alerta.                                                                                                                                                                                                                                                                                                                                | 1234                                                                                                                                                                                                                                              |
| investigable                        | Informações sobre o status atual da investigação. Uma das seguintes opções: *desconhecido* , *terminado* , *SuccessfullyRemediated* , *benigno* , *Failed* , *PartiallyRemediated* , *running* , *PendingApproval* , *PendingResource* , *PartiallyInvestigated* , *TerminatedByUser* , *TerminatedBySystem* , *queued* , *InnerFailure* , *PreexistingAlert* , *UnsupportedOs, UnsupportedAlertType* , *SuppressedAlert*. *UnsupportedAlertType* | UnsupportedAlertType                                                                                                                                                                                                                              |
| classificação                            | A especificação do incidente. Os valores da propriedade são: *desconhecido* , *FalsePositive* , *TruePositive* ou *nulo*                                                                                                                                                                                                                                                                   | Desconhecido                                                                                                                                                                                                                                           |
| determinação                             | Especifica a determinação do incidente. Os valores de propriedade são: *não disponível* , *apt* , *malware* , *SecurityPersonnel* , *SecurityTesting* , *UnwantedSoftware* , *outros* ou  *nulos*                                                                                                                                                                                                     | Chance                                                                                                                                                                                                                                               |
| assignedTo                                | Proprietário do incidente ou *nulo* se nenhum proprietário for atribuído.                                                                                                                                                                                                                                                                                                                            | secop2@contoso.com                                                                                                                                                                                                 |
| actorname                                 | O grupo de atividades, se houver, associado a esse alerta.                                                                                                                                                                                                                                                                                                                                        | BORON                                                                                                                                                                                                                                             |
| threatFamilyName                          | Família de ameaças associada a esse alerta.                                                                                                                                                                                                                                                                                                                                                   | null                                                                                                                                                                                                                                              |
| mitreTechniques                           | As técnicas de ataque, conforme alinhado com o [Mitre ATT&CK](https://attack.mitre.org/)™ Framework.                                                                                                                                                                                                                                                                                                                              | \[\]                                                                                                                                                                                                                                              |
| dispositivos                                   | Todos os dispositivos em que os alertas relacionados ao incidente foram enviados.                                                                                                                                                                                                                                                                                                     | \[\] (veja detalhes nos campos de entidade abaixo)                                                                                                                                                                                                         |
| **Formato do dispositivo**                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| DeviceId                                  | A ID do dispositivo conforme designada no Microsoft defender para ponto de extremidade.                                                                                                                                                                                                                                                                                                                                                       | 24c222b0b60fe148eeece49ac83910cc6a7ef491                                                                                                                                                                                                          |
| aadDeviceId                               |  A ID do dispositivo, conforme designado no [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD). Disponível apenas para dispositivos que ingressaram no domínio.                                                                                                                                                                                                                                                                                                                              | null                                                                                                                                                                                                                                              |
| deviceDnsName                             | O nome de domínio totalmente qualificado para o dispositivo.                                                                                                                                                                                                                                                                                                                                                                        | user5cx.middleeast.corp.contoso.com                                                                                                                                                                                                    |
| osPlatform                                | A plataforma do sistema operacional que o dispositivo está executando.                                                                                                                                                                                                                                                                                                                                                                     | WindowsServer2016                                                                                                                                                                                                                                 |
| osBuild                                   | A versão de compilação do sistema operacional que o dispositivo está executando.                                                                                                                                                                                                                                                                                                                                                                | 14393                                                                                                                                                                                                                                             |
| rbacGroupName                             | O grupo RBAC ( [controle de acesso baseado em função](https://docs.microsoft.com/azure/role-based-access-control/overview) ) associado ao dispositivo.                                                                                                                                                                                                                                                                                                                             | WDATP-Ring0                                                                                                                                                                                                                                       |
| firstSeen                                 | Hora em que o dispositivo foi visto pela primeira vez.                                                                                                                                                                                                                                                                                                                                                           | 2020-02-06T14:16:01.9330135 Z                                                                                                                                                                                                                      |
| healthStatus                              | O estado de integridade do dispositivo.                                                                                                                                                                                                                                                                                                                                                                        | Ativo                                                                                                                                                                                                                                            |
| riskScore                                 | A pontuação de risco para o dispositivo.                                                                                                                                                                                                                                                                                                                                                                       | Alto                                                                                                                                                                                                                                              |
| contabilidade                                  | Todas as entidades que foram identificadas como parte de, ou relacionadas a, um determinado alerta.                                                                                                                                                                                                                                                                                | \[\] (veja detalhes nos campos de entidade abaixo)                                                                                                                                                                                                         |
| **Formato de entidade**                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| entityType                                | Entidades que foram identificadas como parte de um determinado alerta ou relacionadas a ela.<br>Os valores de propriedades são: *usuário* , *IP* , *URL* , *arquivo* , *processo* , *caixa de correio* , *MailMessage* , *MailCluster* , *registro*                                                                                                                                                                                                     | Usuário                                                                                                                                                                                                                                              |
| SHA1                                      | Disponível se entityType for *arquivo*.<br>O hash do arquivo para alertas associados a um arquivo ou processo.                                                                                                                                                                                                                                                                                    | 5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd                                                                                                                                                                                                          |
| SHA256                                    | Disponível se entityType for *arquivo*.<br>O hash do arquivo para alertas associados a um arquivo ou processo.                                                                                                                                                                                                                                                                                    | 28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043                                                                                                                                                                                  |
| fileName                                  | Disponível se entityType for *arquivo*.<br>O nome de arquivo para alertas associados a um arquivo ou processo                                                                                                                                                                                                                                                                                    | Detector.UnitTests.dll                                                                                                                                                                                                                            |
| filePath                                  | Disponível se entityType for *arquivo*.<br>O caminho do arquivo para alertas associados a um arquivo ou processo                                                                                                                                                                                                                                                                                    | C: \\ \\ \\ \\ \_ serviço de implantação temporária de trabalho do agente \\ \\ \_ \\ \\ \_ 2020-09-06 12 \_ 14 \_ 54 \\ \\                                                                                                                                                                    |
| Identificação                                 | Disponível se entityType for *processo*.                                                                                                                                                                                                                                                                                                                                                     | 24348                                                                                                                                                                                                                                             |
| processCommandLine                        | Disponível se entityType for *processo*.                                                                                                                                                                                                                                                                                                                                                     | " \\ " Seu arquivo está pronto para baixar \_1911150169.exe\\ ""                                                                                                                                                                                           |
| processCreationTime                       | Disponível se entityType for *processo*.                                                                                                                                                                                                                                                                                                                                                     | 2020-07-18T03:25:38.5269993 Z                                                                                                                                                                                                                      |
| parentProcessId                           | Disponível se entityType for *processo*.                                                                                                                                                                                                                                                                                                                                                   | 16840                                                                                                                                                                                                                                             |
| parentProcessCreationTime                 | Disponível se entityType for *processo*.                                                                                                                                                                                                                                                                                                                                                     | 2020-07-18T02:12:32.8616797 Z                                                                                                                                                                                                                      |
| ipAddress                                 | Disponível se entityType for *IP*. <br>Endereço IP para alertas associados a eventos de rede, como *comunicação com um destino de rede mal-intencionado*.                                                                                                                                                                                                                                   | 62.216.203.204                                                                                                                                                                                                                                    |
| url                                       | Disponível se entityType for *URL*. <br>URL para alertas associados a eventos de rede, como *comunicação com um destino de rede mal-intencionado*.                                                                                                                                                                                                                                  | down.esales360.cn                                                                                                                                                                                                                                 |
| accountName                               | Disponível se entityType for *User*.                                                                                                                                                                                                                                                                                                                                                         | testUser2                                                                                                                                                                                                                                         |
| domainName                                | Disponível se entityType for *User*.                                                                                                                                                                                                                                                                                                                                                        | Europa. Corp. contoso                                                                                                                                                                                                                              |
| Userid                                   | Disponível se entityType for *User*.                                                                                                                                                                                                                                                                                                                                                        | S-1-5-21-1721254763-462695806-1538882281-4156657                                                                                                                                                                                                  |
| aadUserId                                 | Disponível se entityType for *User*.                                                                                                                                                                                                                                                                                                                                                        | fc8f7484-f813-4db2-afab-bc1507913fb6                                                                                                                                                                                                              |
| userPrincipalName                         | Disponível se EntityType é o MailMessage da caixa de correio do *usuário* / *MailBox* / *MailMessage*.                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                      |
| mailboxDisplayName                        | Disponível se entityType for *Mailbox*.                                                                                                                                                                                                                                                                                                                                                     | testar Usuário2                                                                                                                                                                                                                                        |
| mailboxAddress                            | Disponível se EntityType é o MailMessage da caixa de correio do *usuário* / *MailBox* / *MailMessage*.                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                      |
| clusterBy                                 | Disponível se entityType for  *MailCluster*.                                                                                                                                                                                                                                                                                                                                                 | Sob P2SenderDomain; ContentType                                                                                                                                                                                                                |
| sender                                    | Disponível se EntityType é o MailMessage da caixa de correio do *usuário* / *MailBox* / *MailMessage*.                                                                                                                                                                                                                                                                                                                                  | user.abc@mail.contoso.co.in                                                                                                                                                                 |
| destinatário                                 | Disponível se entityType for *MailMessage*.                                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                       |
| assunto                                   | Disponível se entityType for *MailMessage*.                                                                                                                                                                                                                                                                                                                                                 | \[\]Atenção externa                                                                                                                                                                                                                            |
| deliveryaction                            | Disponível se entityType for *MailMessage*.                                                                                                                                                                                                                                                                                                                                                 | Gerados                                                                                                                                                                                                                                         |
| securityGroupId                           | Disponível se entityType for  *segurança*.                                                                                                                                                                                                                                                                                                                                               | 301c47c8-e15f-4059-ab09-e2ba9ffd372b                                                                                                                                                                                                              |
| securityGroupName                         | Disponível se entityType for  *segurança*.                                                                                                                                                                                                                                                                                                                                               | Operadores de configuração de rede                                                                                                                                                                                                                   |
| registryHive                              | Disponível se entityType for  *registro*.                                                                                                                                                                                                                                                                                                                                                    | \_máquina local \_ HKEY                                                                                                                                                                                                                              |
| Chaves                               | Disponível se entityType for  *registro*.                                                                                                                                                                                                                                                                                                                                                     | SOFTWARE \\ \\ Microsoft \\ \\ Windows NT \\ \\ CurrentVersion \\ \\ Winlogon                                                                                                                                                                                 |
| registryValueType                         | Disponível se entityType for  *registro*.                                                                                                                                                                                                                                                                                                                                                    | String                                                                                                                                                                                                                                            |
| REGISTRYVALUE                             | Disponível se entityType for  *registro*.                                                                                                                                                                                                                                                                                                                                                    | 31-00-00-00                                                                                                                                                                                                                                       |
| deviceId                                  | A ID, se houver, do dispositivo relacionado à entidade.                                                                                                                                                                                                                                                                                                                                           | 986e5df8b73dacd43c8917d17e523e76b13c75cd                                                                                                                                                                                                          |



## <a name="example"></a>Exemplo

**Solicitação**

```
GET https://api.security.microsoft.com/api/incidents
```

**Resposta**
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

## <a name="related-topic"></a>Tópico relacionado
- [APIs de Incidente](api-incident.md)
- [Atualizar incidente](api-update-incidents.md)
