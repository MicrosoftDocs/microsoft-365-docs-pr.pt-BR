---
title: Configurar uma lista personalizada de URLs do não Rewrite usando links seguros de ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Saiba como configurar URLs bloqueadas personalizadas para usuários e não reescrever lista de URLs para um grupo de usuários nas políticas de links seguros de ATP do Office 365.
ms.openlocfilehash: 9ec9c92e038aee33c716405916df009e3f4c60c5
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825228"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-atp-safe-links"></a>Configurar uma lista personalizada de URLs do não Rewrite usando links seguros de ATP

> [!IMPORTANT]
> Este artigo destina-se aos clientes corporativos que têm a [Proteção Avançada contra Ameaças do Office 365](office-365-atp.md). Se você for um usuário doméstico que procura informações sobre links seguros no Outlook, consulte [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Com a [proteção avançada contra ameaças do Office 365](office-365-atp.md) (ATP), sua organização pode ter um [URL bloqueado personalizado](set-up-a-custom-blocked-urls-list-atp.md), de modo que, quando as pessoas clicam em endereços da Web (URLs) em mensagens de email ou determinados documentos do Office, eles são impedidos de ir para essas URLs. Sua organização também pode ter listas personalizadas de "não reescrever" para grupos específicos em sua organização. Uma lista "não reconfigurar" permite que algumas pessoas visitem URLs que, de outra forma, são bloqueadas por [links de ATP seguros no Office 365](atp-safe-links.md).

Este artigo descreve como especificar uma lista de URLs que são excluídas da verificação de links seguros de ATP e alguns pontos importantes a ter em mente.

> [!NOTE]
> Se sua organização usa políticas de links seguros, a lista "não reescrever" é o único método com suporte para testes phishing de terceiros.

## <a name="set-up-a-do-not-rewrite-list"></a>Configurar uma lista de "não reconfigurar"

A proteção de links seguros de ATP usa várias listas, incluindo a lista de URLs bloqueadas da organização e as listas "não reescrever" para exceções. Se você tiver as permissões necessárias, poderá configurar as listas personalizadas de "não reescrever". Você faz isso quando adiciona ou edita políticas de links seguros que se aplicam a destinatários específicos em sua organização.

Para editar (ou definir) políticas ATP, você deve ter uma função apropriada atribuída. A tabela a seguir inclui alguns exemplos. Para saber mais, confira [permissões no centro de conformidade de & de segurança](permissions-in-the-security-and-compliance-center.md).

|Role|Onde/como a atribuição|
|---|---|
|administrador global|Por padrão, a pessoa que se inscreve para comprar a Microsoft 365 é um administrador global. (Consulte [about Microsoft 365 admin Roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) para saber mais.)|
|Administrador de Segurança|Centro de administração do Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
|Gerenciamento de Organização do Exchange Online|Centro de administração do Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>ou <br>  Cmdlets do PowerShell (consulte [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|
|

> [!TIP]
> Para saber mais sobre funções e permissões, consulte [permissões no centro de conformidade de & de segurança](permissions-in-the-security-and-compliance-center.md).

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a>Para exibir ou editar uma lista de URLs de "não reescrever" personalizada

1. Acesse [https://protection.office.com](https://protection.office.com) e entre com sua conta corporativa ou de estudante.

2. Na navegação à esquerda, em **Threat management** \> **Policy** \> **links seguros**da política de gerenciamento de ameaças.

3. Na seção **políticas que se aplicam a destinatários específicos** , escolha **novo** (o botão novo é semelhante a um sinal de adição ( **+** )) para criar uma nova política. (Como alternativa, você pode editar uma política existente.)<br/>![Escolha novo para adicionar uma política de links seguros para destinatários de email específicos](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)

4. Especifique um nome e uma descrição para a política.

5. Ativar **URLs** será reescrito e verificado em relação a uma lista de links mal-intencionados conhecidos quando o usuário clicar no link.

6. Na seção não **reescrever as seguintes URLs** , selecione a caixa **Insira uma URL válida** , insira uma URL e, em seguida, escolha o sinal de adição (+).

7. Na seção **aplica-se** a, escolha **o destinatário é um membro de**e, em seguida, escolha o (s) grupo (s) que você deseja incluir na política. Escolha **Adicionar**e, em seguida, escolha **OK**.

8. Quando terminar de adicionar URLs, no canto inferior direito da tela, escolha **salvar**.

> [!NOTE]
> Certifique-se de revisar a lista personalizada de URLs bloqueadas da sua organização. Confira [Configurar uma lista de URLs bloqueadas personalizada usando os links seguros de ATP](set-up-a-custom-blocked-urls-list-atp.md).

## <a name="important-points-to-keep-in-mind"></a>Pontos importantes a ter em mente

- Qualquer URL especificada na lista "não reescrever" será excluída da verificação de links seguros de ATP para os destinatários que você especificar.

- Considere adicionar URLs internas comumente usadas à lista "não reescrever" para melhorar a experiência do usuário. Por exemplo, se você tiver serviços locais, como o Skype for Business ou o SharePoint, poderá adicionar suas URLs à lista para excluí-los da verificação.

- Se você já tiver uma lista de URLs na lista de "não reescrever", verifique se a lista e adicione caracteres curinga conforme apropriado. Por exemplo, se a sua lista existente tem uma entrada como `https://contoso.com/a` e você deseja incluir subcaminhos como `https://contoso.com/a/b` em sua política, adicione um curinga à sua entrada para que ele se pareça `https://contoso.com/a/*` .

- Ao especificar uma lista "não reconfigurar" para uma política de links seguros de ATP, você pode incluir até três curingas ( \* ). Os curingas incluem explicitamente prefixos ou subdomínios. Por exemplo, a entrada `contoso.com` não é igual a `*.contoso.com/*` , pois `*.contoso.com/*` permite que as pessoas visitem subdomínios e caminhos no domínio especificado.

A tabela a seguir lista exemplos do que você pode inserir e o efeito que essas entradas têm.

****

|Entrada de exemplo|O que ele faz|
|---|---|
|`contoso.com`|Permite que os destinatários visitem um site como `https://contoso.com` , mas não subdomínios ou caminhos.|
|`*.contoso.com/*`|Permite que os destinatários visitem um domínio, subdomínios e caminhos, como `https://www.contoso.com` , `https://www.contoso.com` , `https://maps.contoso.com` ou `https://www.contoso.com/a` . <br/><br/> Essa entrada é inerentemente melhor do que `*contoso.com*` porque não inclui sites potencialmente fraudulentos, como `https://www.falsecontoso.com` ou `https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|Permite que destinatários específicos visitem um site como `https://contoso.com/a` , mas não subcaminhos como `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|Permite que destinatários específicos visitem um site como `https://contoso.com/a` e subcaminhos como `https://contoso.com/a/b`|
|
