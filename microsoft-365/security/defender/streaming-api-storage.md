---
title: Transmitir eventos do Microsoft 365 Defender para sua conta de armazenamento
description: Saiba como configurar o Microsoft 365 Defender para transmitir eventos de Busca Avançada para sua conta de Armazenamento.
keywords: exportação de dados brutos, API de streaming, API, Hubs de Eventos, armazenamento do Azure, conta de armazenamento, Busca Avançada, compartilhamento de dados brutos
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
ms.openlocfilehash: fa61e2fd0591d375a17bad6e166a76c1ca40862e
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028870"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a>Configurar o Microsoft 365 Defender para transmitir eventos de Busca Avançada para sua conta de Armazenamento

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


## <a name="before-you-begin"></a>Antes de começar:

1. Crie uma [conta de armazenamento](/azure/storage/common/storage-account-overview) em seu locatário.

2. Faça logoff no locatário do [Azure,](https://ms.portal.azure.com/)acesse Assinaturas > Sua assinatura > Provedores de Recursos **> Registrar no Microsoft.Insights**.

## <a name="enable-raw-data-streaming"></a>Habilitar o streaming de dados brutos:

1. Faça logon no Centro de segurança do [Microsoft 365 Defender](https://security.microsoft.com) como um ***Administrador Global** _ ou _* Administrador _de Segurança_**.

2. Vá para [a página Configurações de exportação de dados](https://security.microsoft.com/settings/mtp_settings/raw_data_export) no Centro de Segurança do Microsoft Defender.

3. Clique em **Adicionar configurações de exportação de dados.**

4. Escolha um nome para suas novas configurações.

5. Escolha **Encaminhar eventos para o Armazenamento do Azure.**

6. Digite sua **ID de Recurso de Conta de Armazenamento**. Para obter sua **ID** de Recurso de Conta de Armazenamento, vá para a página Conta de Armazenamento no portal do [Azure](https://ms.portal.azure.com/) > guia propriedades > copiar o texto em **ID** de Recurso da Conta de Armazenamento :

   ![Imagem da ID do recurso do hub de eventos1](../defender-endpoint/images/storage-account-resource-id.png)

7. Escolha os eventos que deseja transmitir e clique em **Salvar**.

## <a name="the-schema-of-the-events-in-the-storage-account"></a>O esquema dos eventos na conta de armazenamento:

- Um contêiner blob será criado para cada tipo de evento: 

  ![Imagem da ID do recurso do hub de eventos2](../defender-endpoint/images/storage-account-event-schema.png)

- O esquema de cada linha em um blob é o seguinte JSON: 

  ```
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }               
  ```

- Cada blob contém várias linhas.

- Cada linha contém o nome do evento, a hora em que o Defender for Endpoint recebeu o evento, o locatário que ele pertence (você só receberá eventos do seu locatário) e o evento no formato JSON em uma propriedade chamada "properties".

- Para obter mais informações sobre o esquema dos eventos do Microsoft 365 Defender, consulte [Advanced Hunting overview](../defender/advanced-hunting-overview.md).


## <a name="data-types-mapping"></a>Mapeamento de tipos de dados

Para obter os tipos de dados para nossas propriedades de eventos, faça o seguinte:

1. Faça logoff no Centro de segurança [do Microsoft 365](https://security.microsoft.com) e vá para [a página Busca Avançada.](https://security.microsoft.com/hunting-package)

2. Execute a seguinte consulta para obter o mapeamento de tipos de dados para cada evento: 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Veja um exemplo para o evento Informações do Dispositivo: 

  ![Imagem da ID do recurso do hub de eventos3](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da Busca Avançada](../defender/advanced-hunting-overview.md)
- [Microsoft 365 Defender Streaming API](streaming-api.md)
- [Transmitir eventos do Microsoft 365 Defender para sua conta de armazenamento do Azure](streaming-api-storage.md)
- [Documentação da Conta de Armazenamento do Azure](/azure/storage/common/storage-account-overview)
