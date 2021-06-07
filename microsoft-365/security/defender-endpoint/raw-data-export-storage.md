---
title: Transmitir eventos do Microsoft Defender para Ponto de Extremidade para sua Armazenamento de usuário
description: Saiba como configurar o Microsoft Defender para o Ponto de Extremidade para transmitir eventos de Busca Avançada para sua Armazenamento conta.
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
ms.openlocfilehash: c280baaf3af6f9fcac6059bc2797910eb6c226fd
ms.sourcegitcommit: f0118e61e490496cb23189cc5c73b23e2ba939be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52780172"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-storage-account"></a>Configurar o Microsoft Defender para o Ponto de Extremidade para transmitir eventos de Busca Avançada para sua Armazenamento conta

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a>Antes de você começar

1. Crie uma [Armazenamento em](/azure/storage/common/storage-account-overview) seu locatário.

2. Faça logoff no locatário do [Azure,](https://ms.portal.azure.com/)acesse Assinaturas > Sua assinatura > Provedores de Recursos **> Registrar no Microsoft.insights**.

## <a name="enable-raw-data-streaming"></a>Habilitar o streaming de dados brutos

1. Faça logon [no portal do Microsoft Defender para Ponto de Extremidade](https://securitycenter.windows.com) como um * Administrador **Global** _ ou _* Administrador _de Segurança_**.

2. Vá para [a página Configurações de exportação de dados](https://securitycenter.windows.com/interoperability/dataexport) Central de Segurança do Microsoft Defender.

3. Clique em **Adicionar configurações de exportação de dados.**

4. Escolha um nome para suas novas configurações.

5. Escolha **Encaminhar eventos para o Azure Armazenamento**.

6. Digite sua **Armazenamento ID do Recurso da Conta.** Para obter Armazenamento **ID** do Recurso de Conta do Armazenamento, vá para Armazenamento página da sua conta no portal do [Azure](https://ms.portal.azure.com/) > guia propriedades > copie o texto sob a **ID** do recurso da conta Armazenamento :

   ![Imagem da ID do recurso do hub de eventos1](images/storage-account-resource-id.png)

7. Escolha os eventos que deseja transmitir e clique em **Salvar**.

## <a name="the-schema-of-the-events-in-the-storage-account"></a>O esquema dos eventos na conta Armazenamento

- Um contêiner blob será criado para cada tipo de evento: 

  ![Imagem da ID do recurso do hub de eventos2](images/storage-account-event-schema.png)

- O esquema de cada linha em um blob é o seguinte JSON: 

  ```
  {
          "time": "<The time WDATP received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <WDATP Advanced Hunting event as Json> }
  }               
  ```

- Cada blob contém várias linhas.

- Cada linha contém o nome do evento, a hora em que o Defender for Endpoint recebeu o evento, o locatário que ele pertence (você só receberá eventos do seu locatário) e o evento no formato JSON em uma propriedade chamada "properties".

- Para obter mais informações sobre o esquema do Microsoft Defender para eventos do Ponto de Extremidade, consulte [Visão geral de Busca Avançada](advanced-hunting-overview.md).

- Em Busca Avançada, a tabela **DeviceInfo** tem uma coluna chamada **MachineGroup** que contém o grupo do dispositivo. Aqui todos os eventos também serão decorados com esta coluna. Confira [Grupos de Dispositivos](machine-groups.md) para obter mais informações.

## <a name="data-types-mapping"></a>Mapeamento de tipos de dados

Para obter os tipos de dados para nossas propriedades de eventos, faça o seguinte:

1. Entre [no](https://securitycenter.windows.com) Central de Segurança do Microsoft Defender e vá para a página De Busca [Avançada.](https://securitycenter.windows.com/hunting-package)

2. Execute a seguinte consulta para obter o mapeamento de tipos de dados para cada evento: 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Veja um exemplo para o evento Informações do Dispositivo: 

  ![Imagem da ID do recurso do hub de eventos3](images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da Busca Avançada](advanced-hunting-overview.md)
- [API de streaming do Microsoft Defender para Ponto de Extremidade](raw-data-export.md)
- [Transmitir eventos do Microsoft Defender para Ponto de Extremidade para sua conta de armazenamento do Azure](raw-data-export-storage.md)
- [Documentação Armazenamento conta do Azure](/azure/storage/common/storage-account-overview)