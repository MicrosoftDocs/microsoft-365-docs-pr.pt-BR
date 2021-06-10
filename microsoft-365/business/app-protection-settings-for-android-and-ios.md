---
title: Defina configurações de proteção de aplicativo para dispositivos Android ou iOS
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Saiba como criar, editar ou excluir uma política de gerenciamento de aplicativos e proteger arquivos de trabalho em dispositivos Android ou iOS.
ms.openlocfilehash: 2e157737990c7aca6e87a676e90f62f0d40ad372
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580285"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>Defina configurações de proteção de aplicativo para dispositivos Android ou iOS

Este artigo se aplica a Microsoft 365 Business Premium.

## <a name="create-an-app-management-policy"></a>Criar uma política de gerenciamento de aplicativos

1. Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
    
2. Na nav esquerda, escolha **Políticas** de \>  \> **Dispositivos Adicionar**.
  
3. No painel **Adicionar política**, insira um nome exclusivo para essa política. 
    
4. Em **Tipo de Política**, escolha Gerenciamento de **Aplicativos para Android** ou Gerenciamento de Aplicativos para **iOS,** dependendo do conjunto de políticas que você deseja criar. 
    
5. Expanda **Proteger arquivos de trabalho quando dispositivos são perdidos ou roubados** e Gerenciar como os usuários **acessam Office arquivos em dispositivos móveis**. Configure as configurações como você gostaria. **Gerenciar como os usuários acessam Office**  arquivos em dispositivos móveis está  Desligado por padrão, mas recomendamos que você a a ligue e aceite os valores padrão. Para obter mais informações, consulte [Configurações disponíveis](#available-settings). 
    
    Você sempre poderá usar o link **Redefinir as configurações padrão** para voltar para a configuração padrão. 
    
    ![Screenshot of Create a policy with Application management for Android selected](../media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. Em seguida, decida **Quem receberá estas configurações?** Se você não quiser usar o grupo de segurança padrão **Todos** os Usuários, escolha **Alterar**, escolha os grupos de segurança que obterão essas configurações \> **Selecione**.
    
7. Por fim, escolha **Concluído** para salvar a política e atribui-la a dispositivos. 
    
## <a name="edit-an-app-management-policy"></a>Editar uma política de gerenciamento de aplicativos

1. No cartão **Políticas,** escolha **Editar política**.
    
2. No painel **Editar política**, escolha a política que você deseja alterar 
    
3. Escolha **Editar** ao lado de cada configuração para alterar os valores na política. Quando você altera um valor, ele é salvo automaticamente na política.
    
4. Quando terminar, feche o painel **Editar política.** 
    
## <a name="delete-an-app-management-policy"></a>Excluir uma política de gerenciamento de aplicativos

1. Na página **Políticas,** escolha uma política e **exclua**.
    
2. No painel **Excluir política,** escolha **Confirmar** para excluir a política ou as políticas escolhidas. 
    
## <a name="available-settings"></a>Configurações disponíveis

As tabelas a seguir dão informações detalhadas sobre as configurações disponíveis para proteger arquivos de trabalho em dispositivos e as configurações que controlam como os usuários acessam Office arquivos de seus dispositivos móveis.
  
 Para obter mais informações, consulte [How do protection features in Microsoft 365 Business Premium map to Intune settings](map-protection-features-to-intune-settings.md). 
  
### <a name="settings-that-protect-work-files"></a>Configurações que protegem os arquivos de trabalho

As configurações a seguir estão disponíveis para proteger os arquivos de trabalho se o dispositivo do usuário for perdido ou roubado:
  
|||
|:-----|:-----|
|Configuração  <br/> |Descrição  <br/> |
|Excluir arquivos de trabalho de um dispositivo inativo após determinada quantidade de dias  <br/> |Se um dispositivo não for usado para o número de dias especificado aqui, todos os arquivos de trabalho armazenados no dispositivo serão excluídos automaticamente.  <br/> |
|Forçar os usuários a salvar todos os arquivos de trabalho no OneDrive for Business  <br/> |Se essa configuração for **On**, o único local de salvação disponível para arquivos de trabalho será OneDrive for Business.  <br/> |
|Criptografar arquivos de trabalho  <br/> |Mantenha essa configuração **Ativada** para que os arquivos de trabalho sejam protegidos por criptografia. Mesmo que o dispositivo seja perdido ou roubado, ninguém poderá ler os dados da empresa.  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>Configurações que controlam como os usuários acessam arquivos do Office em dispositivos móveis

As configurações a seguir estão disponíveis para gerenciar como os usuários acessam arquivos de trabalho do Office:
  
|||
|:-----|:-----|
|Configuração  <br/> |Descrição  <br/> |
|Exigir um PIN ou uma impressão digital para acessar aplicativos do Office  <br/> |Se essa configuração for **On,** os usuários devem fornecer outra forma de autenticação, além de seu nome de usuário e senha, para que eles possam usar Office aplicativos em seus dispositivos móveis.<br/> |
|Redefinir o PIN quando houver muitas falhas de logon  <br/> |Para impedir que um usuário não autorizado adivinhe um PIN, o PIN será redefinido após determinado número de tentativas incorretas.  <br/> |
|Exigir que os usuários entrem novamente depois que os aplicativos do Office ficarem ociosos  <br/> |Essa configuração determina por quanto tempo um usuário pode ficar ocioso antes de ser solicitado a entrar novamente.  <br/> |
|Negar o acesso aos arquivos de trabalho em dispositivos com jailbreak ou com acesso raiz  <br/> |Os usuários inteligentes podem ter dispositivos com jailbreak ou com acesso raiz. Isso significa que o usuário pode modificar o sistema operacional, deixando o dispositivo mais sujeito a malware. Os dispositivos são bloqueados quando essa configuração está **Ativada**.  <br/> |
|Não permita que os usuários copiem conteúdo de aplicativos Office aplicativos pessoais  <br/> |Permitimos isso por padrão, mas se a configuração estiver **Ativada**, o usuário poderá copiar informações de uma pasta de trabalho para um arquivo pessoal. Quando a configuração está **Desativada**, o usuário não pode copiar informações de uma conta corporativa para um aplicativo pessoal ou uma conta pessoal.  <br/> |
