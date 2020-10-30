---
title: Limitar a exposição acidental
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom: ''
localization_priority: Priority
f1.keywords: NOCSH
description: Saiba como limitar a exposição acidental de informações ao compartilhar arquivos com pessoas de fora da sua organização.
ms.openlocfilehash: 6250103e36900da76a4529a73b78f14862ab86ef
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769001"
---
# <a name="limit-accidental-exposure-to-files-when-sharing-with-people-outside-your-organization"></a>Limitar a exposição acidental de arquivos ao compartilhar com pessoas de fora da sua organização

Ao compartilhar arquivos e pastas com pessoas de fora da sua organização, há uma variedade de opções para reduzir as chances de compartilhar acidentalmente informações confidenciais. Você pode escolher a opção apresentada neste artigo que atenda melhor às necessidades da sua organização.

## <a name="use-best-practices-for-anyone-links"></a>Usar as práticas recomendadas para links para Qualquer pessoa

Se as pessoas em sua organização precisarem fazer compartilhamentos não autenticados, mas você está preocupado que pessoas não autenticadas façam modificações no conteúdo, leia [Práticas recomendadas para compartilhamento não autenticado](best-practices-anonymous-sharing.md) para obter diretrizes sobre como trabalhar com o compartilhamento não autenticado em sua organização.

## <a name="turn-off-anyone-links"></a>Desativar links para Qualquer pessoa

Recomenda-se deixar os links para *Qualquer pessoa* habilitados para o conteúdo apropriado porque essa é a maneira mais fácil de compartilhar, além de poder ajudar a reduzir o risco de usuários que buscam soluções diferentes e fora do controle do departamento de TI. Os links para *Qualquer pessoa* podem ser encaminhados a outras pessoas, mas o acesso aos arquivos só estará disponível para os usuários que tiverem o link.

Caso você queira que as pessoas de fora da sua organização sempre façam a autenticação ao acessar o conteúdo no SharePoint, Grupos ou no Teams, você pode desativar o compartilhamento a *Qualquer pessoa* . Isso impedirá usuários de compartilharem conteúdo não autenticado.

Mesmo desabilitando os links para *Qualquer pessoa* , os usuários continuarão podendo fazer compartilhamentos facilmente com convidados usando links para *Pessoas específicas* . Nesse caso, todas as pessoas de fora da sua organização precisarão se autenticar para poder acessar o conteúdo compartilhado.

Dependendo das suas necessidades, você pode desabilitar links para *Qualquer pessoa* para sites específicos ou para toda a organização.

Para desativar os links para *Qualquer pessoa* da sua organização
1. No centro de administração do SharePoint, na navegação à esquerda, clique em **Compartilhamento** .
2. Defina as configurações de compartilhamento externo do SharePoint para **Convidados novos e existentes** .

   ![Captura de tela das configurações de compartilhamento externo do site do SharePoint no nível da organização](../media/sharepoint-organization-external-sharing-controls-new-users.png)

3. Clique em **Salvar** .

Para desativar os links para *Qualquer pessoa* de um site
1. No centro de administração do SharePoint, na navegação à esquerda, expanda a opção **Sites** e clique em **Sites ativos** .
2. Clique no site que você deseja configurar.
3. Na faixa de opções, clique em **Compartilhamento** .
4. Verifique se o compartilhamento está definido como **Convidados novos e existentes** .

   ![Captura de tela das configurações de compartilhamento externo do site do SharePoint](../media/sharepoint-site-external-sharing-settings.png)

5. Caso tenha feito alterações, clique em **Salvar** .

## <a name="domain-filtering"></a>Filtragem de domínios

Você pode usar as listas permitir ou negar domínio para determinar os domínios que seus usuários podem compartilhar com pessoas de fora da sua organização.

Com uma lista de permissões, você pode especificar uma lista de domínios que os usuários de sua organização podem compartilhar com pessoas de fora da sua organização. O compartilhamento com outros domínios está bloqueado. Se sua organização só colabora com as pessoas presentes em uma lista de domínios específicos, você pode usar esse recurso para impedir o compartilhamento com outros domínios.

Com uma lista de negações, você pode especificar uma lista de domínios que os usuários da organização não podem compartilhar com pessoas de fora da sua organização. O compartilhamento com os domínios listados está bloqueado. Isso poderá ser útil se você tiver concorrentes, por exemplo, que deseja impedir de acessar o conteúdo da sua organização.

As listas de permissão e negação afetam apenas o compartilhamento com convidados. Os usuários continuarão podendo fazer compartilhamentos com pessoas de domínios proibidos usando links para *Qualquer pessoa* caso você ainda não os tenha desabilitado. Para obter os melhores resultados com listas de permissão e negação de domínio, cogite desabilitar os links para *Qualquer pessoa* conforme descrito acima.

Para configurar uma lista de permissão ou negação de domínio
1. No centro de administração do SharePoint, na navegação à esquerda, clique em **Compartilhamento** .
2. Em **Configurações avançadas para compartilhamento externo** , marque a caixa de seleção **Limitar compartilhamento externo por domínio** .
3. Clique em **Adicionar domínios** .
4. Selecione se deseja bloquear domínios, digite os domínios e clique em **OK.**

   ![Captura de tela das configurações de limite de compartilhamento externo por domínio do SharePoint](../media/sharepoint-sharing-block-domain.png)

5. Clique em **Salvar** .

Caso deseje limitar o compartilhamento por domínio em um nível superior ao SharePoint e ao OneDrive, você pode [permitir ou bloquear convites para usuários B2B de organizações específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list) no Azure Active Directory. (Você deve configurar a [integração do SharePoint e do OneDrive com a versão prévia do B2B do Azure AD](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) para que essas configurações se apliquem ao SharePoint e ao OneDrive).

## <a name="limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups"></a>Limitar o compartilhamento de arquivos, pastas e sites com pessoas de fora da sua organização com grupos de segurança especificados

Você pode restringir o compartilhamento de arquivos, pastas e sites com pessoas de fora da sua organização com os membros de um grupo de segurança específico. Isso será útil caso você queira habilitar o compartilhamento externo, mas com um fluxo de trabalho de aprovação ou processo de solicitação. Como alternativa, você pode exigir que os usuários concluam um curso de treinamento antes que eles sejam adicionados ao grupo de segurança e possam compartilhar externamente.

Limitar o compartilhamento externo com membros de um grupo de segurança
1. No [centro de administração do SharePoint](https://admin.microsoft.com/sharepoint), na navegação à esquerda, em **Políticas** clique em **Compartilhamento** .
2. Em **Compartilhamento externo** , expanda **Mais configurações de compartilhamento externo** .

3. Selecione **Permitir que somente os usuários em grupos de segurança específicos compartilhem externamente** e, em seguida, selecione **Gerenciar grupos de segurança** .

    ![Captura de tela do Painel gerenciar grupos de segurança](https://docs.microsoft.com/sharepoint/sharepointonline/media/manage-security-groups.png)

4. Na caixa **Adicionar um grupo de segurança** , digite um nome para o grupo de segurança. A caixa de grupo de segurança é exibida.

5. Ao lado do nome do grupo de segurança, na lista suspensa **Pode compartilhar com** , escolha:

    - **Somente convidados autenticados** (padrão)
    - **Qualquer pessoa**

6. Selecione **Salvar** .

Observe que isso afeta arquivos, pastas e sites, mas não os grupos do Microsoft 365 ou Teams. Quando os membros convidarem pessoas para um grupo privado do Microsoft 365 ou uma equipe privada no Microsoft Teams, o convite é enviado ao proprietário do grupo ou equipe para aprovação.

## <a name="see-also"></a>Confira também

[Criar um ambiente seguro de compartilhamento de convidados](create-secure-guest-sharing-environment.md)

[Práticas recomendadas para compartilhar arquivos e pastas com usuários anônimos](best-practices-anonymous-sharing.md)