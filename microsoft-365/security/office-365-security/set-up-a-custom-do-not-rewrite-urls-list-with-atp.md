---
title: Configurar uma lista personalizada de URLs do não Rewrite usando os links seguros de ATP do Office 365
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 08/29/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection:
- M365-security-compliance
description: Ao configurar as políticas de links seguros de ATP, você pode incluir uma lista de URLs que não reconfigura para permitir que algumas pessoas em sua organização visitem sites que você inclui na sua lista.
ms.openlocfilehash: ca1927871b834459a05c1c36e5b15d3d47aa242b
ms.sourcegitcommit: ba223b4fd069fc6fd09c2a2e34c770a18bc7b2a2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39866573"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a>Configurar uma lista personalizada de URLs do não Rewrite usando os links seguros de ATP do Office 365

> [!IMPORTANT]
> Este artigo destina-se aos clientes corporativos que têm a [Proteção Avançada contra Ameaças do Office 365](office-365-atp.md). Se você for um usuário doméstico que procura informações sobre links seguros no Outlook, consulte [Advanced Outlook.com Security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

Com a [proteção avançada contra ameaças do Office 365](office-365-atp.md) (ATP), sua organização pode ter um [URL bloqueado personalizado](set-up-a-custom-blocked-urls-list-wtih-atp.md), de modo que, quando as pessoas clicam em endereços da Web (URLs) em mensagens de email ou determinados documentos do Office, eles são impedidos de ir para essas URLs. Sua organização também pode ter listas personalizadas de "não reescrever" para grupos específicos em sua organização. Uma lista "não reconfigurar" permite que algumas pessoas visitem URLs que, de outra forma, são bloqueadas por [links de ATP seguros no Office 365](atp-safe-links.md). 
  
Este artigo descreve como especificar uma lista de URLs que são excluídas da verificação de links seguros de ATP e alguns pontos importantes a ter em mente.

## <a name="set-up-a-do-not-rewrite-list"></a>Configurar uma lista de "não reconfigurar"

A proteção de links seguros de ATP usa várias listas, incluindo a lista de URLs bloqueadas da organização e as listas "não reescrever" para exceções. Se você tiver as permissões necessárias, poderá configurar as listas personalizadas de "não reescrever". Você faz isso quando adiciona ou edita políticas de links seguros que se aplicam a destinatários específicos em sua organização. 

Para editar (ou definir) políticas ATP, você deve ter uma função apropriada atribuída. A tabela a seguir inclui alguns exemplos. Para saber mais, confira [permissões no centro de conformidade & segurança do Office 365](permissions-in-the-security-and-compliance-center.md).

|Role  |Onde/como a atribuição  |
|---------|---------|
|Administrador Global do Office 365 |Por padrão, a pessoa que se inscreve para comprar o Office 365 é um administrador global. (Confira [sobre as funções de administrador do Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) para saber mais.)         |
|Administrador de Segurança |Centro de administração do Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory ()|
|Gerenciamento de Organização do Exchange Online |Centro de administração do[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange () <br>ou <br>  Cmdlets do PowerShell (consulte [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) |

> [!TIP]
> Para saber mais sobre funções e permissões, confira [permissões no centro de conformidade &amp; de segurança do Office 365](permissions-in-the-security-and-compliance-center.md).

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a>Para exibir ou editar uma lista de URLs de "não reescrever" personalizada
  
1. Acesse [https://protection.office.com](https://protection.office.com) e entre com sua conta corporativa ou de estudante. 
    
2. Na navegação à esquerda, em **links seguros**da **política** \> de **Gerenciamento** \> de ameaças.
    
3. Na seção **políticas que se aplicam a destinatários específicos** , escolha **novo** (o botão novo é semelhante a um sinal **+** de adição ()) para criar uma nova política. (Como alternativa, você pode editar uma política existente.)<br/>![Escolha novo para adicionar uma política de links seguros para destinatários de email específicos](../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
4. Especifique um nome e uma descrição para a política.
    
5. Na seção não **reescrever as seguintes URLs** , selecione a caixa **Insira uma URL válida** e, em seguida, digite uma URL e, em seguida, escolha o sinal de adição (+). 
    
6. Na seção **aplica-se** a, escolha **o destinatário é um membro de**e, em seguida, escolha o (s) grupo (s) que você deseja incluir na política. Escolha **Adicionar**e, em seguida, escolha **OK**.
    
7. Quando terminar de adicionar URLs, no canto inferior direito da tela, escolha **salvar**.
    
> [!NOTE]
> Certifique-se de revisar a lista personalizada de URLs bloqueadas da sua organização. Confira [Configurar uma lista de URLs bloqueadas personalizada usando os links seguros de ATP](set-up-a-custom-blocked-urls-list-wtih-atp.md). 
  
## <a name="important-points-to-keep-in-mind"></a>Pontos importantes a ter em mente

- Qualquer URL especificada na lista "não reescrever" será excluída da verificação de links seguros de ATP para os destinatários que você especificar.
 
- Se você já tiver uma lista de URLs na lista de "não reescrever", verifique se a lista e adicione caracteres curinga conforme apropriado. Por exemplo, se a sua lista existente tem uma entrada `https://contoso.com/a` como e você deseja incluir subcaminhos como `https://contoso.com/a/b` em sua política, adicione um curinga à sua entrada para que ele se `https://contoso.com/a/*`pareça.
    
- Não inclua uma barra (/) nas URLs que você especificar na lista "não reconfigurar". Por exemplo, em vez de `contoso.com/` inserir na lista "não reescrever", insira `contoso.com`.

- Ao especificar uma lista "não reconfigurar" para uma política de links seguros de ATP, você pode incluir até três asteriscos curinga (\*). Curingas (\*) são usados para incluir explicitamente prefixos ou subdomínios, `https://` como `https://`ou. Uma entrada, como não `contoso.com` é a mesma `*.contoso.com/*` da lista "não reconfigurar". Você deve ter `*.contoso.com/*` se quiser permitir que as pessoas visitem um domínio e seus subdomínios e caminhos.
    
A tabela a seguir lista exemplos do que você pode inserir e o efeito que essas entradas têm.
    
|**Entrada de exemplo**|**O que ele faz**|
|:-----|:-----|
|`contoso.com`|Permite que os destinatários visitem um `https://contoso.com` site como, mas não subdomínios ou caminhos.|
|`*.contoso.com/*`  <br/> |Permite que os destinatários visitem um domínio, subdomínios e caminhos, como `https://www.contoso.com`, `https://www.contoso.com` `https://maps.contoso.com`, ou`https://www.contoso.com/a`  <br/> |
|`https://contoso.com/a`  <br/> |Permite que destinatários específicos visitem um site `https://contoso.com/a`como, mas não subcaminhos como`https://contoso.com/a/b`  <br/> |
|`https://contoso.com/a/*`  <br/> |Permite que destinatários específicos visitem um site `https://contoso.com/a` como e subcaminhos como`https://contoso.com/a/b`  <br/> |
   
 
