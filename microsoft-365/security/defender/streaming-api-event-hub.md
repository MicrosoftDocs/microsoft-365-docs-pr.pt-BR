---
title: Transmitir Microsoft 365 Defender eventos para o Hub de Eventos do Azure
description: Saiba como configurar o Microsoft 365 Defender para transmitir eventos de Busca Avançada para o Hub de Eventos.
keywords: exportação de dados brutos, API de streaming, API, Hub de Eventos do Azure, armazenamento do Azure, conta de armazenamento, Busca Avançada, compartilhamento de dados brutos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2e43b75e49d01a05fdacae0adf63ea3337631dfd
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289230"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hub"></a>Configurar Microsoft 365 Defender para transmitir eventos de Busca Avançada para o Hub de Eventos do Azure

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a>Antes de começar

1. Crie um [hub de eventos](/azure/event-hubs/) em seu locatário.

2. Faça logoff no locatário do [Azure,](https://ms.portal.azure.com/)acesse Assinaturas > Sua assinatura > Provedores de Recursos > Registrar no **Microsoft.Insights**.

3. Crie um Namespace do Hub de Eventos, vá até **Event Hub > Adicionar** e selecione a camada de preços, as unidades de transferência e a Inflação Automática apropriada para a carga esperada. Para obter mais informações, consulte [Pricing - Event Hub | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).  

### <a name="add-contributor-permissions"></a>Adicionar permissões de colaborador

Depois que o namespace hub de eventos for criado, você precisará:

1. Defina o usuário que fará logo Microsoft 365 Defender colaborador.

2. Se você estiver se conectando a um aplicativo, adicione a Entidade de Serviço de Registro de Aplicativo como Leitor, Receptor de Dados do Hub de Eventos do Azure (isso também pode ser feito no nível de Grupo de Recursos ou Assinatura). 

    Vá para Namespace de hubs de eventos > Controle de acesso **(IAM)** > Adicionar e verificar em **Atribuições de função**.

## <a name="enable-raw-data-streaming"></a>Habilitar o streaming de dados brutos

1. Faça logon no [Microsoft 365 Defender de](https://security.microsoft.com) segurança como um ***Administrador Global** _ ou _* Administrador _de Segurança_**.

2. Vá para a [página Configurações da API de Streaming.](https://security.microsoft.com/settings/mtp_settings/raw_data_export)

3. Clique em **Adicionar**.

4. Escolha um nome para suas novas configurações.

5. Escolha **Encaminhar eventos para o Hub de Eventos do Azure.**

6. Você pode selecionar se deseja exportar os dados do evento para um único Hub de Eventos ou exportar cada tabela de eventos para um hub de eventos diferente no namespace do Hub de Eventos. 

7. Para exportar os dados de evento para um único Hub de Eventos, insira o nome do **Hub** de Eventos e sua ID de recurso **do Hub de Eventos.**

   Para obter sua **ID** de recurso do Hub de Eventos, vá para sua página de namespace do Hub de Eventos do Azure na guia Propriedades do [Azure](https://ms.portal.azure.com/)> copiar o texto em  >   **ID** de Recurso :

   ![Imagem da Id1 do recurso hub de eventos](../defender-endpoint/images/event-hub-resource-id.png)

8. Escolha os eventos que deseja transmitir e clique em **Salvar**.

## <a name="the-schema-of-the-events-in-azure-event-hub"></a>O esquema dos eventos no Hub de Eventos do Azure

```JSON
{
   "records": [
               {
                  "time": "<The time Microsoft 365 Defender received the event>"
                  "tenantId": "<The Id of the tenant that the event belongs to>"
                  "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                  "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
               }
               ...
            ]
}
```

- Cada mensagem do Hub de Eventos no Hub de Eventos do Azure contém uma lista de registros.

- Cada registro contém o nome do evento, a hora em que Microsoft 365 Defender recebeu o evento, o locatário que ele pertence (você só receberá eventos de seu locatário) e o evento no formato JSON em uma propriedade chamada "**properties**".

- Para obter mais informações sobre o esquema de eventos Microsoft 365 Defender, consulte [Visão geral de Busca Avançada.](advanced-hunting-overview.md)

- Em Busca Avançada, a tabela **DeviceInfo** tem uma coluna chamada **MachineGroup** que contém o grupo do dispositivo. Aqui todos os eventos também serão decorados com esta coluna. 

## <a name="data-types-mapping"></a>Mapeamento de tipos de dados

Para obter os tipos de dados para propriedades de evento, faça o seguinte:

1. Entre no centro [Microsoft 365 segurança e](https://security.microsoft.com) vá para a página De Busca [Avançada.](https://security.microsoft.com/hunting-package)

2. Execute a seguinte consulta para obter o mapeamento de tipos de dados para cada evento:

   ```kusto
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Veja um exemplo para o evento Informações do Dispositivo: 

  ![Imagem da Id do recurso hub de eventos2](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral da Busca Avançada](advanced-hunting-overview.md)
- [Microsoft 365 Defender API de streaming](streaming-api.md)
- [Transmitir Microsoft 365 Defender eventos para sua conta de armazenamento do Azure](streaming-api-storage.md)
- [Documentação do Hub de Eventos do Azure](/azure/event-hubs/)
- [Solucionar problemas de conectividade - Hub de Eventos do Azure](/azure/event-hubs/troubleshooting-guide)
