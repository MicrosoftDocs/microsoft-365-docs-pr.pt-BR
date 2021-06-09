---
title: Nomes do dispositivo
description: Como Área de Trabalho Gerenciada da Microsoft gerencia nomes de dispositivos
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
ms.openlocfilehash: adf4809e0d8dc29f170475435b19092abf2062fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893682"
---
# <a name="device-names"></a>Nomes do dispositivo

Área de Trabalho Gerenciada da Microsoft usa Windows Autopilot, Azure Active Directory e Microsoft Intune. Para que esses serviços funcionem em conjunto perfeitamente, os dispositivos precisam de nomes consistentes e padronizados. Área de Trabalho Gerenciada da Microsoft aplica um formato de nome padronizado (do formato *MMD-%RAND11*) quando os dispositivos são inscritos. Windows O Piloto Automático atribui esses nomes. Para obter mais informações sobre o Autopilot, consulte Experiência de primeira corrida [com o Autopilot e a Página de Status de Registro.](../get-started/esp-first-run.md)

## <a name="automated-name-changes"></a>Alterações automáticas de nome

Se um dispositivo for renomeado posteriormente, Área de Trabalho Gerenciada da Microsoft o renomeará automaticamente para um novo nome no formato padronizado. Esse processo ocorre a cada quatro horas. A alteração de nome ocorre na próxima vez que o usuário reiniciar o dispositivo.

> [!IMPORTANT]
> Se seu ambiente depender de nomes de dispositivo específicos (por exemplo, para dar suporte a uma configuração de rede específica), você deve investigar opções para remover essa dependência antes de se registrar no Área de Trabalho Gerenciada da Microsoft. Se você deve manter a dependência de nome, você pode enviar uma solicitação por meio do [portal](../working-with-managed-desktop/admin-support.md) de administração para desabilitar a função de renomeação e usar o formato de nome desejado.