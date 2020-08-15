---
title: Como corrigir problemas de sincronização de diretórios do Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MBS150
ms.assetid: 79c43023-5a47-45ae-8068-d8a26eee6bc2
description: Descreve causas comuns de problemas com a sincronização de diretórios no Office 365 e fornece alguns métodos para ajudar a solucionar problemas.
ms.openlocfilehash: 80b4a88e91230a8736f209ecd65c58b2882c25d6
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687455"
---
# <a name="fixing-problems-with-directory-synchronization-for-microsoft-365"></a>Como corrigir problemas de sincronização de diretórios do Microsoft 365

Com a sincronização de diretórios, você pode continuar a gerenciar os usuários e grupos locais, e sincronizar acréscimos, eliminações e alterações com a nuvem. Mas a configuração é um pouco complicada e algumas vezes pode ser difícil identificar a origem dos problemas. Temos recursos para ajudá-lo a identificar os possíveis problemas e corrigi-los.
  
## <a name="how-do-i-know-if-something-is-wrong"></a>Como saber se algo está errado?

O primeiro sinal de que algo está errado é quando o bloco de Status do DirSync no Centro de Administração do Microsoft 365 indica que há um problema.
  
Você também receberá um email (no endereço de email alternativo e no seu email de administrador) do Microsoft 365 que indica que seu locatário encontrou erros de sincronização de diretório. Para obter mais detalhes, confira o artigo [Como identificar erros de sincronização de diretório no Microsoft 365](identify-directory-synchronization-errors.md).
  
## <a name="how-do-i-get-azure-active-directory-connect-tool"></a>Como faço para obter a ferramenta Azure Active Directory Connect?

No [Centro de Administração do Microsoft 365](https://admin.microsoft.com), vá para **Usuários** \> **Usuários ativos**. Clique em **Mais** no menu (três pontos) e selecione **Sincronização do diretório**. 
  
Siga as [instruções do assistente](set-up-directory-synchronization.md) para baixar o Azure AD Connect. 
  
Se ainda estiver usando a Sincronização (DirSync) do Azure Active Directory (Azure AD), confira o artigo [Como solucionar problemas de instalação da Ferramenta de Sincronização do Azure Active Directory e mensagens de erro do Assistente de Configuração no Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=396717) para saber mais sobre os requisitos do sistema para instalar o DirSync, as permissões necessárias e como solucionar erros comuns. 
  
Para atualizar o Azure AD Sync para o Azure AD Connect, confira as [instruções de atualização](https://go.microsoft.com/fwlink/p/?LinkId=733240).
  
## <a name="resolving-common-causes-of-problems-with-directory-synchronization-in-microsoft-365"></a>Como resolver as causas mais comuns de problemas de sincronização de diretórios no Microsoft 365

### <a name="synchronized-objects-arent-appearing-or-updating-online-or-im-getting-synchronization-error-reports-from-the-service"></a>Os objetos sincronizados não estão aparecendo nem sendo atualizados online, ou estou recebendo relatórios de erros de sincronização enviados pelo Serviço.

- [Sincronização de identidades e resiliência do atributo duplicada](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)

### <a name="i-have-an-alert-in-the-admin-center-or-am-receiving-automated-emails-that-there-hasnt-been-a-recent-synchronization-event"></a>Recebi um alerta no centro de administração ou estou recebendo emails automáticos informando que não ocorreram eventos de sincronização recentes
- [Solucionar problemas de conectividade com o Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/tshoot-connect-connectivity)
- [Contas e permissões do Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=820598)
- [Sincronização do Azure AD Connect: como gerenciar a conta de serviço do Azure AD](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-azureadaccount)
- [A sincronização do diretório com o Azure Active Directory para ou você é alertado de que a sincronização não aconteceu há mais de um dia](https://support.microsoft.com/help/2882421/directory-synchronization-to-azure-active-directory-stops-or-you-re-warned-that-sync-hasn-t-registered-in-more-than-a-day)

### <a name="password-hashes-arent-synchronizing-or-im-seeing-an-alert-in-the-admin-center-that-there-hasnt-been-a-recent-password-hash-synchronization"></a>As senhas criptografadas não estão sendo sincronizadas ou estou vendo um alerta no centro de administração informando que não ocorreu nenhuma sincronização recente da criptografia de senhas
- [Como implementar a sincronização da criptografia de senha com a sincronização do Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)

### <a name="im-seeing-an-alert-that-object-quota-exceeded"></a>Estou vendo um alerta informando que a cota de Objetos foi excedida
- Temos uma cota de objetos integrada para ajudar a proteger o serviço. Se você tiver um número excessivo de objetos em seu diretório e precisar sincronizar com o Microsoft 365, precisará [Entrar em contato com o suporte de produtos empresariais](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) para aumentar sua cota.

### <a name="i-need-to-know-which-attributes-are-synchronized"></a>Preciso saber quais atributos são sincronizados
- Você pode encontrar uma lista de todos os atributos que são sincronizados entre o local e a nuvem [aqui](https://go.microsoft.com/fwlink/p/?LinkId=396719).

### <a name="i-cant-manage-or-remove-objects-that-were-synchronized-to-the-cloud"></a>Não consigo gerenciar nem remover os objetos que foram sincronizados para a nuvem
- Você está pronto para gerenciar objetos somente na nuvem? Ou existe um objeto que foi excluído localmente, mas está preso na nuvem? Confira [Como solucionar erros durante a sincronização](https://go.microsoft.com/fwlink/p/?linkid=842044) e este [artigo sobre suporte](https://go.microsoft.com/fwlink/p/?LinkId=396720) para obter orientação sobre como resolver esses problemas.

### <a name="i-got-an-error-message-that-my-company-has-exceeded-the-number-of-objects-that-can-be-synchronized"></a>Recebi uma mensagem de erro informando que minha empresa excedeu o número de objetos que podem ser sincronizados
- Leia mais sobre o problema [aqui](https://go.microsoft.com/fwlink/p/?LinkId=396721).
   
## <a name="other-resources"></a>Outros recursos

- [Script para corrigir UPNs duplicados](https://go.microsoft.com/fwlink/p/?LinkId=396725)
    
- [Como preparar um domínio não roteável (por exemplo, domínio .local) para a sincronização de diretórios](prepare-a-non-routable-domain-for-directory-synchronization.md)
    
- [Script para contar o total de objetos sincronizados](https://go.microsoft.com/fwlink/p/?LinkId=396726)
    
- [Solucionar problemas do AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=396727)
    
- [Usar o PowerShell para corrigir os atributos DisplayName vazios para grupos habilitados para email](https://go.microsoft.com/fwlink/p/?LinkId=396728)
    
- [Usar o PowerShell para corrigir UPN duplicado](https://go.microsoft.com/fwlink/p/?LinkId=396730)
    
- [Usar o PowerShell para corrigir endereços de email duplicados](https://go.microsoft.com/fwlink/p/?LinkId=396731)
    
