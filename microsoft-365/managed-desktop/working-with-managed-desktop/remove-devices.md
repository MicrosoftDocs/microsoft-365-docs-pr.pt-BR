---
title: Remover dispositivos
description: Remover dispositivos do Área de Trabalho Gerenciada da Microsoft gerenciamento
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: fa1cb7307fddd815a2a9249c5a98739d21bd2418
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893663"
---
# <a name="remove-devices"></a>Remover dispositivos

Você pode remover dispositivos Área de Trabalho Gerenciada da Microsoft gerenciamento usando o portal de administração. Essa ação é permanente, mas você pode registrá-los com Área de Trabalho Gerenciada da Microsoft novamente seguindo as etapas [de registro](../get-started/register-devices-self.md).

Quando você remove um dispositivo, todos os seguintes ocorrem:

- Removemos o dispositivo do Autopilot.
- Removemos o dispositivo de todos os grupos de dispositivos "Modern Workplace".
- Removemos o dispositivo da folha **Dispositivos** no portal de administração.

Ao remover um dispositivo, você tem a opção de também removê-lo do Azure Active Directory (Azure AD) e Microsoft Intune.
 
> [!CAUTION]
> Remover os objetos relacionados a um dispositivo do Azure AD e Microsoft Intune é permanente. Se você remover os objetos, não poderá exibir ou gerenciar os dispositivos dos portais do Intune e do Azure. Os dispositivos não poderão acessar os recursos corporativos da empresa. Os dados da empresa podem ser excluídos deles se os dispositivos tentarem entrar depois de serem excluídos.

1. Em [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), selecione **Dispositivos** no painel de navegação esquerdo.
2. Procure a seção **Área de Trabalho Gerenciada da Microsoft** do menu e selecione **Dispositivos**.
3. No espaço Área de Trabalho Gerenciada da Microsoft dispositivos, selecione os dispositivos que você deseja excluir.
4. Selecione **Ações do dispositivo** e selecione Excluir **Dispositivo** que abre um sub-entrada para remover os dispositivos.
5. No sub-entrada, revise os dispositivos selecionados e selecione **Remover dispositivos**. Se você quiser também remover os objetos do Azure AD e do Intune ao mesmo tempo, marque a caixa de seleção. A remoção do dispositivo pode levar alguns minutos para ser concluída.

> [!NOTE]
> Não é possível remover dispositivos que estão em um **estado de** registro pendente.