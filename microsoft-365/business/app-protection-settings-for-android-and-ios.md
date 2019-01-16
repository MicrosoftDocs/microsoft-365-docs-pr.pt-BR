---
title: Defina configurações de proteção de aplicativo para dispositivos Android ou iOS
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Saiba como criar, editar ou excluir uma política de gerenciamento de aplicativo e proteger os arquivos de trabalho em dispositivos Android ou iOS.
ms.openlocfilehash: ed03227496120369b94bf2396974eebfd7798678
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865249"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>Defina configurações de proteção de aplicativo para dispositivos Android ou iOS

## <a name="create-an-app-management-policy"></a>Criar uma política de gerenciamento de aplicativos

1. Acesse o [Microsoft 365 Business](https://portal.office.com) com credenciais de administrador global. 
    
2. No centro de administração, no cartão **Políticas de dispositivos**, escolha **Adicionar política**.
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. No painel **Adicionar política**, insira um nome exclusivo para essa política. 
    
4. Em **Tipo de política**, escolha **Gerenciamento de Aplicativos para Android** ou **Gerenciamento de Aplicativos para iOS**, dependendo de qual conjunto de políticas que você deseja criar. 
    
5. Expanda **Proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** e **Gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** \> defina as configurações como desejar. A opção **Gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** é **Desativada** por padrão, mas recomenda-se que ela seja **Ativada** e que os valores padrão sejam aceitos. Confira [Configurações disponíveis](app-protection-settings-for-android-and-ios.md#bkmk_availablesettings) para saber mais. 
    
    Você sempre poderá usar o link **Redefinir as configurações padrão** para voltar para a configuração padrão. 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. Em seguida, decida **Quem receberá estas configurações?** Se não quiser usar o grupo de segurança padrão **Todos os Usuários**, escolha **Alterar**, escolha o grupo de segurança que deverá receber essas configurações \> **Selecionar**.
    
7. Por fim, escolha **Concluído** para salvar a política e atribui-la a dispositivos. 
    
## <a name="edit-an-app-management-policy"></a>Editar uma política de gerenciamento de aplicativos

1. No cartão de **políticas** , escolha **Editar política**.
    
2. No painel **Editar política**, escolha a política que você deseja alterar 
    
3. Escolha **Editar** ao lado de cada configuração para alterar os valores na política. Quando você altera um valor, ele é salvo automaticamente na política 
    
4. Quando terminar, feche o painel **Editar política**. 
    
## <a name="delete-an-app-management-policy"></a>Excluir uma política de gerenciamento de aplicativos

1. No cartão **Políticas**, escolha **Excluir política**.
    
2. No painel **Excluir política**, escolha as políticas que você deseja excluir \> **Selecionar** e, em seguida, clique em **Confirmar** para excluir a política ou políticas escolhidas. 
    
## <a name="available-settings"></a>Configurações disponíveis

As tabelas a seguir fornecem informações detalhadas sobre as configurações disponíveis para proteger os arquivos de trabalho em dispositivos e as configurações que controlam como os usuários acessam arquivos do Office em seus dispositivos móveis.
  
 Confira [Como os recursos de proteção no Microsoft 365 Business são mapeados para as configurações do Intune](map-protection-features-to-intune-settings.md) para obter mais informações. 
  
### <a name="settings-that-protect-work-files"></a>Configurações que protegem os arquivos de trabalho

As configurações a seguir estão disponíveis para proteger os arquivos de trabalho se o dispositivo do usuário for perdido ou roubado:
  
|||
|:-----|:-----|
|Configuração  <br/> |Descrição  <br/> |
|Excluir arquivos de trabalho de um dispositivo inativo após determinada quantidade de dias  <br/> |Se um dispositivo não for usado pela quantidade de dias que você especificar aqui, quaisquer arquivos de trabalho armazenados nele serão excluídos automaticamente.  <br/> |
|Forçar os usuários a salvar todos os arquivos de trabalho no OneDrive for Business  <br/> |Se essa configuração estiver **Ativada**, o único local disponível para salvar arquivos de trabalho será o OneDrive for Business.  <br/> |
|Criptografar arquivos de trabalho  <br/> |Mantenha essa configuração **Ativada** para que os arquivos de trabalho sejam protegidos por criptografia. Mesmo que o dispositivo seja perdido ou roubado, ninguém poderá ler os dados da empresa.  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>Configurações que controlam como os usuários acessam arquivos do Office em dispositivos móveis

As configurações a seguir estão disponíveis para gerenciar como os usuários acessam arquivos de trabalho do Office:
  
|||
|:-----|:-----|
|Configuração  <br/> |Descrição  <br/> |
|Exigir um PIN ou uma impressão digital para acessar aplicativos do Office  <br/> |Se essa configuração estiver **Ativada**, os usuários precisarão fornecer outra forma de autenticação, além de seu nome de usuário e senha, para poderem usar os aplicativos do Office em seus dispositivos móveis.  <br/> |
|Redefinir o PIN quando houver muitas falhas de logon  <br/> |Para impedir que um usuário não autorizado adivinhe um PIN, o PIN será redefinido após determinado número de tentativas incorretas.  <br/> |
|Exigir que os usuários entrem novamente depois que os aplicativos do Office ficarem ociosos  <br/> |Esta configuração determina quanto tempo o usuário pode ficar ocioso antes de ser solicitado a entrar novamente.  <br/> |
|Negar o acesso aos arquivos de trabalho em dispositivos com jailbreak ou com acesso raiz  <br/> |Os usuários inteligentes podem ter dispositivos com jailbreak ou com acesso raiz. Isso significa que o usuário pode modificar o sistema operacional, deixando o dispositivo mais sujeito a malware. Esses dispositivos são bloqueados quando essa configuração está **Ativada**.  <br/> |
|Permitir que os usuários copiem o conteúdo dos aplicativos do Office para os aplicativos pessoais  <br/> |Podemos permitir isso por padrão, mas se a configuração está **habilitada**, o usuário pode copiar informações em um arquivo de trabalho para um arquivo pessoal. Se a configuração estiver **desativada**, o usuário será capaz de copiar informações de uma conta do trabalho em um app pessoal ou a conta pessoal.<br/> |
   

  

