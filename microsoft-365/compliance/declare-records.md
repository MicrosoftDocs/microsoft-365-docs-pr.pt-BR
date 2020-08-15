---
title: Declarar registros usando rótulos de retenção
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 'Declarar registros usando rótulos de retenção. '
ms.openlocfilehash: c8024cf08be2259ffa8b6747bebf4943e11e4d60
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695228"
---
# <a name="declare-records-by-using-retention-labels"></a>Declarar registros usando rótulos de retenção

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

Você usa [rótulos de retenção](retention.md#retention-labels) para marcar conteúdos como registros. É possível publicar esses rótulos para que usuários e administradores possam aplicá-los manualmente ou automaticamente ao conteúdo que você deseja classificar como registro.

## <a name="configuring-retention-labels-to-declare-records"></a>Configurar rótulos de retenção para declarar registros

Ao criar um [rótulo de retenção](retention.md#retention-labels), escolha a opção de marcar o conteúdo como um registro.

>[!NOTE] 
> A opção de marcar o conteúdo como registro não está disponível quando você cria ou configura rótulos de retenção da **Governança de Informações** no Centro de conformidade do Microsoft 365. Em vez disso, você deve usar o **Gerenciamento de Registros**.

1. No [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com), vá para **Gerenciamento de Registros** \> **Plano de Arquivo**. Na página **Planejamento de arquivos**, clique em **Criar um rótulo**.

2. Na página **Configurações de rótulo** no assistente, escolha a opção para classificar o conteúdo como registro.
    
   ![Clique em Usar rótulo para classificar o conteúdo como uma caixa de seleção de Registro](../media/recordversioning6.png)

3. Aplique o rótulo de retenção aos documentos do SharePoint ou OneDrive e emails do Exchange, conforme necessário. Para obter instruções:
    
    - [Criar rótulos de retenção e aplicá-los em aplicativos](create-apply-retention-labels.md)
    
    - [Aplicar um rótulo de retenção automaticamente ao conteúdo](apply-retention-labels-automatically.md)

## <a name="applying-the-configured-retention-label-to-content"></a>Aplicando o rótulo de retenção configurado ao conteúdo

Quando os rótulos de retenção que marcam o conteúdo como registro são disponibilizados para os usuários aplicá-los nos aplicativos:

- Para o Exchange, qualquer usuário com acesso de gravação à caixa de correio pode aplicar esses rótulos. 
- Para o SharePoint e OneDrive, qualquer usuário no grupo Membros padrão (o nível de permissão de Contribuição) pode aplicar esses rótulos.

Exemplo de um documento marcado como registro usando um rótulo de retenção:

![Painel de detalhes do documento marcado como um registro](../media/recordversioning7.png)

## <a name="next-steps"></a>Próximas etapas

Se você precisar atualizar documentos que são registros, confira [Usar controle de versão de registro para atualizar registros armazenados no SharePoint ou no OneDrive](record-versioning.md).

Para saber mais sobre a disposição de registros, confira [Descarte de conteúdo](disposition.md).
