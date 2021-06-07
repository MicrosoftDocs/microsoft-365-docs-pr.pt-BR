---
title: Transmitir Microsoft 365 eventos do Defender para sua conta Armazenamento usuário
description: Saiba como configurar o Microsoft 365 Defender para transmitir eventos de Busca Avançada para sua Armazenamento conta.
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
ms.openlocfilehash: 9ec8c286828fd6b551bf76c8340b58c9a1407bba
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778204"
---
# <a name="configure--microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a>Configure Microsoft 365 Defender para transmitir eventos de Busca Avançada para sua Armazenamento de usuário

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="before-you-begin"></a>Antes de começar:

1. Crie uma [Armazenamento em](/azure/storage/common/storage-account-overview) seu locatário.

2. Faça logoff no locatário do [Azure,](https://ms.portal.azure.com/)acesse Assinaturas > Sua assinatura > Provedores de Recursos **> Registrar no Microsoft.Insights**.

## <a name="enable-raw-data-streaming"></a>Habilitar o streaming de dados brutos:

1. Faça logon [no Microsoft 365 de](https://security.microsoft.com) segurança do Defender como um * Administrador **Global** _ ou _* Administrador _de Segurança_**.

2. Vá para [a página Configurações de exportação de dados](https://security.microsoft.com/settings/mtp_settings/raw_data_export) Central de Segurança do Microsoft Defender.

3. Clique em **Adicionar configurações de exportação de dados.**

4. Escolha um nome para suas novas configurações.

5. Escolha **Encaminhar eventos para o Azure Armazenamento**.

6. Digite sua **Armazenamento ID do Recurso da Conta.** Para obter Armazenamento **ID** do Recurso de Conta, vá até Armazenamento página da sua conta do [Azure na](https://ms.portal.azure.com/) guia propriedades do portal do Azure > > copie o texto em Armazenamento **ID** do Recurso de Conta :

   ![Imagem da ID do recurso do hub de eventos1](images/storage-account-resource-id.png)

7. Escolha os eventos que deseja transmitir e clique em **Salvar**.

## <a name="the-schema-of-the-events-in-the-storage-account"></a>O esquema dos eventos na conta Armazenamento:

- Um contêiner blob será criado para cada tipo de evento: 

  ![Imagem da ID do recurso do hub de eventos2](images/storage-account-event-schema.png)

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

- Para obter mais informações sobre o esquema de eventos Microsoft 365 Defender, consulte [Advanced Hunting overview](../defender/advanced-hunting-overview.md).


## <a name="data-types-mapping"></a>Mapeamento de tipos de dados:

Para obter os tipos de dados para nossas propriedades de eventos, faça o seguinte:

1. Entre no centro [Microsoft 365 segurança e](https://security.microsoft.com) vá para a página De Busca [Avançada.](https://security.microsoft.com/hunting-package)

2. Execute a seguinte consulta para obter o mapeamento de tipos de dados para cada evento: 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Veja um exemplo para o evento Informações do Dispositivo: 

  ![Imagem da ID do recurso do hub de eventos3](images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da Busca Avançada](../defender/advanced-hunting-overview.md)
- [Microsoft 365 Defender Streaming API](raw-data-export.md)
- [Transmitir Microsoft 365 eventos do Defender para sua conta de armazenamento do Azure](raw-data-export-storage.md)
- [Documentação Armazenamento conta do Azure](/azure/storage/common/storage-account-overview)
