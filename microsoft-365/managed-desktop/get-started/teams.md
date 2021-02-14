---
title: Microsoft Teams
description: Como o Teams é instalado em dispositivos e atualizado posteriormente
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação, aplicativos, aplicativos de linha de negócios, aplicativos LOB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: ea2ef7637a8d360e3b598aec4852425d977ae4ec
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950899"
---
# <a name="microsoft-teams"></a>Microsoft Teams

[O Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) é [um aplicativo de mensagens](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) para sua organização que também fornece um espaço de trabalho para colaboração e comunicação em tempo real, reuniões e compartilhamento de arquivos e aplicativos.

## <a name="initial-deployment"></a>Implantação inicial

A maioria dos fornecedores de hardware ainda não inclui o Teams como parte de suas imagens, portanto, a Área de Trabalho Gerenciada da Microsoft implanta o Teams em seus dispositivos usando o Microsoft Intune. Todos os dispositivos gerenciados têm o pacote [.msi](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) do Teams instalado, garantindo que todos os usuários que entrarem em um dispositivo tenham o Microsoft Teams pronto para uso. Quando o pacote terminar de instalar pela primeira vez, o Teams será iniciado automaticamente e adicionará um atalho à área de trabalho.

### <a name="microsoft-intune-changes"></a>Alterações do Microsoft Intune

A Área de Trabalho Gerenciada da Microsoft adiciona dois aplicativos à sua organização do Azure AD para o Microsoft Teams. Eles são implantados em clientes de 64 bits ou 32 bits, conforme apropriado para o dispositivo:  

- Modern Workplace – Instalador em Todo o Computador do Teams x64  
- Modern Workplace – Instalador em Todo o Computador do Teams x32

## <a name="updates"></a>Atualizações

O Teams segue um caminho de atualização separado do Microsoft 365 Apps para empresas e o cliente da área de trabalho se atualiza automaticamente. O Teams verifica se há atualizações a cada algumas horas, baixa-as e aguarda o computador ficar ocioso antes de instalar a atualização silenciosamente.  

O grupo de produtos do Teams não permite que os administradores controlem as atualizações, portanto, a Área de Trabalho Gerenciada da Microsoft usa o [canal de atualização automática padrão.](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)

### <a name="manually-updating-teams"></a>Atualizando manualmente o Teams

Os usuários individuais também podem baixar atualizações selecionando **Verificar** se há atualizações no menu suspenso Perfil,   no canto superior direito do  ****   aplicativo. Se uma atualização estiver disponível, ela será baixada e instalada silenciosamente quando o computador estiver ocioso.

## <a name="delivery-optimization-of-updates"></a>Otimização de entrega de atualizações

A otimização de entrega para as atualizações do Teams está 2010 100 por padrão e não requer nenhuma ação de administradores ou usuários. 