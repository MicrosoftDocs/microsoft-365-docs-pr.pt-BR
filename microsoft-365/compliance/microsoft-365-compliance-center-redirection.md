---
title: Redirecionar usuários do centro Office 365 Segurança e Conformidade para o Centro de conformidade do Microsoft 365
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: Saiba mais sobre redirecionar automaticamente Office 365 usuários do Centro de Conformidade e Segurança para o Centro de conformidade do Microsoft 365..
ms.collection: M365-security-compliance
ms.openlocfilehash: 62fc302f9f065ac7bb0475a6e72dc240a56a1fe1
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339401"
---
# <a name="redirect-users-from-the-office-365-security-and-compliance-center-to-the-microsoft-365-compliance-center"></a>Redirecionar usuários do centro Office 365 Segurança e Conformidade para o Centro de conformidade do Microsoft 365

Este artigo explica como funciona o redirecionamento automático para usuários que acessam soluções de conformidade do Centro de Conformidade e Segurança Office 365 (protection.office.com) para o Centro de conformidade do Microsoft 365 (compliance.microsoft.com).

## <a name="what-to-expect"></a>O que esperar

O redirecionamento automático é habilitado por padrão para todos os usuários que acessam as seguintes soluções relacionadas Office 365 Segurança e Conformidade (protection.office.com):

- Prevenção de perda de dados (DLP)
- Classificação
- Governança de informações
- Gerenciamento de registros
- Conformidade de comunicação (anteriormente 'Supervisão')

Os usuários são automaticamente roteados para as mesmas soluções de conformidade no Centro de conformidade do Microsoft 365 (compliance.microsoft.com).

> [!NOTE]
> Para outras soluções de conformidade incluídas no Centro de Conformidade e Segurança do Office 365, os usuários continuarão a gerenciar essas soluções no Centro de conformidade do Microsoft 365 ou no Centro de Conformidade e Segurança Office 365. O redirecionamento automático para essas soluções de conformidade estará disponível em breve.

Esse recurso e controles associados não habilitam o redirecionamento automático de recursos de Segurança para o Microsoft Defender para Office 365. Para habilitar o redirecionamento para recursos de segurança, consulte [Redirecionando](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) contas do Microsoft Defender para Office 365 para o centro de segurança Microsoft 365 para obter detalhes.

## <a name="can-i-go-back-to-using-the-former-portal"></a>Posso voltar a usar o portal anterior?

Se algo não estiver funcionando para você ou se houver algo que você não consiga concluir por meio do portal Centro de conformidade do Microsoft 365, você poderá desabilitar temporariamente o redirecionamento automático para todos os usuários.

> [!IMPORTANT]
> O Centro de conformidade do Microsoft 365 é o portal de gerenciamento de substituição para soluções de conformidade gerenciadas atualmente no centro Office 365 Segurança e Conformidade. Todas as Microsoft 365 de conformidade serão gerenciadas somente no Centro de conformidade do Microsoft 365. Desabilitar o redirecionamento para o Centro de conformidade do Microsoft 365 deve ser uma solução de curto prazo.

Para alternar de volta para o centro Office 365 Segurança e Conformidade (protection.microsoft.com) para todos os usuários, conclua as seguintes etapas:

1. Entre no Centro de conformidade do Microsoft 365 [como](https://compliance.microsoft.com) administrador global ou usando qualquer conta com permissões de administrador de conformidade no Azure Active directory.
2. Navegue **até Configurações**  >  **redirecionamento do Centro de Conformidade.**
3. Alterne a configuração de redirecionamento automático para **Off**.
4. Selecione **Desativar e** compartilhar comentários quando solicitado.

Depois de desabilitados, os usuários não serão mais roteados para compliance.microsoft.com e serão direcionados para o centro Office 365 Segurança e Conformidade (protection.microsoft.com). Essa configuração pode ser habilitada novamente a qualquer momento pelos administradores de Conformidade ou Global.

## <a name="related-information"></a>Informações relacionadas

- [Centro de conformidade do Microsoft 365 visão geral](/microsoft-365/compliance/microsoft-365-compliance-center)
