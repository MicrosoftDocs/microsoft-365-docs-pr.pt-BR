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
ms.openlocfilehash: 841c5197addff704016e344ba7ae44355c872f72
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47817094"
---
# <a name="declare-records-by-using-retention-labels"></a>Declarar registros usando rótulos de retenção

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

Para declarar documentos e emails como um registro, use [rótulos de retenção](retention.md#retention-labels) que identificam itens como registros. É possível publicar esses rótulos para que usuários e administradores possam aplicá-los manualmente ou automaticamente ao conteúdo que você deseja classificar como registro.

## <a name="configuring-retention-labels-to-declare-records"></a>Configurar rótulos de retenção para declarar registros

Quando você criar ou configurar um rótulo de retenção, selecione a opção para marcar os itens como registros.

>[!NOTE] 
> A opção de marcar o conteúdo como registro não está disponível quando você cria ou configura rótulos de retenção da **Governança de Informações** no Centro de conformidade do Microsoft 365. Em vez disso, você deve usar o **Gerenciamento de Registros**.

Para criar um novo rótulo de retenção que marque o conteúdo como um registro:

1. No [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com), vá para **Gerenciamento de Registros** \> **Plano de Arquivo**. Na página **Planejamento de arquivos**, clique em **Criar um rótulo**.

2. Na página **Definir configurações de retenção** no assistente, escolha a opção para marcar itens como registros:
    
   ![Selecione a configuração de retenção para marcar os itens como um registro](../media/recordversioning6.png)

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

Para obter uma lista dos cenários com suporte para o gerenciamento de registros, confira [Cenários comuns para o gerenciamento de registros](get-started-with-records-management.md#common-scenarios-for-records-management).
