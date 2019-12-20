---
title: Configurar políticas de anexos seguros de ATP do Office 365
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Definir políticas de anexos seguros para proteger sua organização contra arquivos mal-intencionados no email.
ms.openlocfilehash: 0bafa8e21d3788871f9daf38aeeabd00abb97bec
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806714"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a>Configurar políticas de anexos seguros de ATP do Office 365

> [!IMPORTANT]
> Este artigo destina-se aos clientes corporativos que têm a [Proteção Avançada contra Ameaças do Office 365](office-365-atp.md). Se você for um usuário doméstico que procura informações sobre anexos seguros no Outlook, consulte [Advanced Outlook.com Security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).

Pessoas costumam enviar, receber e compartilhar anexos, como documentos, apresentações, planilhas e muito mais. Nem sempre é fácil dizer se um anexo é seguro ou mal-intencionado apenas olhando uma mensagem de email. E a última coisa que você deseja é um anexo mal-intencionado para obter estragos para sua organização. Felizmente, a [proteção avançada contra ameaças do Office 365](office-365-atp.md) (ATP) pode ajudar. Você pode configurar as políticas de [anexos seguros de ATP](atp-safe-attachments.md) para ajudar a garantir que sua organização seja protegida contra ataques por anexos de email não seguros.

## <a name="what-to-do"></a>O que fazer

1. Revisar os pré-requisitos

2. Configurar uma política de anexos seguros de ATP

3. Saiba mais sobre as opções de política de anexos seguros de ATP

## <a name="step-1-review-the-prerequisites"></a>Etapa 1: revisar os pré-requisitos

- Certifique-se de que sua organização tenha a [proteção avançada contra ameaças do Office 365](office-365-atp.md).

- Verifique se você tem as permissões necessárias. Para definir (ou editar) políticas ATP, você deve ter uma função apropriada atribuída. Alguns exemplos são descritos na tabela a seguir:

  |Role|Onde/como a atribuição|
  |---------|---------|
  |Administrador Global do Office 365 |Por padrão, a pessoa que se inscreve para comprar o Office 365 é um administrador global. (Confira [sobre as funções de administrador do Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) para saber mais.)|
  |Administrador de Segurança |Centro de administração do Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory ()|
  |Gerenciamento de Organização do Exchange Online |Centro de administração do[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange () <br>ou <br>  Cmdlets do PowerShell (consulte [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))|

  Para saber mais sobre funções e permissões, confira [permissões no centro de conformidade &amp; de segurança do Office 365](permissions-in-the-security-and-compliance-center.md).

- [Saiba mais sobre as opções de política de anexos seguros de ATP](#step-3-learn-about-atp-safe-attachments-policy-options) (neste artigo). Algumas opções, como as opções monitorar ou substituir, podem resultar em um atraso menor de email enquanto os anexos são verificados. Para evitar atrasos de mensagens, considere o uso da [entrega dinâmica e da visualização](dynamic-delivery-and-previewing.md).

- Aguarde até 30 minutos para que a política nova ou atualizada se espalhe para todos os datacenters do Office 365.

## <a name="step-2-set-up-or-edit-an-atp-safe-attachments-policy"></a>Etapa 2: configurar (ou editar) uma política de anexos seguros de ATP

1. Acesse [https://protection.office.com](https://protection.office.com) e entre com sua conta corporativa ou de estudante.

2. No centro de conformidade com &amp; segurança do Office 365, no painel de navegação esquerdo, em **Gerenciamento de ameaças**, escolha **anexos seguros**de **política** \> .

3. Se você vir **ativar a ATP para SharePoint, onedrive e Microsoft Teams**, recomendamos que você selecione essa opção. Isso habilitará a [proteção avançada contra ameaças do Office 365 para o SharePoint, o onedrive e o Microsoft Teams](atp-for-spo-odb-and-teams.md) para seu ambiente do Office 365.

4. Escolha **novo** (o botão novo é semelhante a um sinal de **+** adição ()) para começar a criar sua política.

5. Especifique o nome, a descrição e as configurações da política.<br/><br/>**Exemplo:** Para configurar uma política chamada "sem atrasos" que entrega mensagens de todos os usuários imediatamente e anexar novamente os anexos após serem verificados, você pode especificar as seguintes configurações:

   - Na caixa **nome** , digite nenhum atraso.

   - Na caixa **Descrição** , digite uma descrição como, entrega mensagens imediatamente e reanexa os anexos após a verificação.

   - Na seção resposta, escolha a opção de **entrega dinâmica** . ([Saiba mais sobre entrega dinâmica e visualização com anexos seguros de ATP](dynamic-delivery-and-previewing.md).)

   - Na seção **redirecionar anexo** , selecione a opção para habilitar o redirecionamento e digite o endereço de email do seu administrador global do Office 365, administrador de segurança ou analista de segurança que irá investigar anexos mal-intencionados.

   - Na seção **aplica-se** a, escolha **o domínio do destinatário**e selecione o seu domínio. Escolha **Adicionar**e, em seguida, escolha **OK**.

6. Selecione **Salvar**.

Considere configurar várias políticas de anexos seguros de ATP para sua organização. Essas políticas serão aplicadas na ordem em que estão listadas na página de **anexos seguros de ATP** . Após uma política ter sido definida ou editada, permita pelo menos 30 minutos para que as políticas entrem em vigor nos datacenters da Microsoft.

## <a name="step-3-learn-about-atp-safe-attachments-policy-options"></a>Etapa 3: Saiba mais sobre as opções de política de anexos seguros de ATP

À medida que você configura as políticas de anexos seguros de ATP, você escolhe entre várias opções, incluindo monitor, bloqueio, substituição, entrega dinâmica e assim por diante. Caso você esteja se perguntando o que essas opções fazem, a tabela a seguir resume cada e seu efeito.

|**Opção**|**Effect**|**Use quando quiser:**|
|:-----|:-----|:-----|
|**Desabilitado**|Não examina anexos de malware  <br/> Não atrasa a entrega de mensagens|Desative a verificação para remetentes, scanners, faxes ou hosts inteligentes internos que só enviarão anexos conhecidos e bons  <br/> Evitar atrasos desnecessários no roteamento de email interno  <br/> **Essa opção não é recomendada para a maioria dos usuários. Ele permite que você ative a verificação de anexos seguros de ATP para um pequeno grupo de remetentes internos.**|
|**Monitorar**|Entrega mensagens com anexos e rastreia o que acontece com o malware detectado|Veja onde o malware detectado entra em sua organização|
|**Bloquear**|Impede que mensagens com anexos de malware detectados continuem  <br/> Envia mensagens com malware detectado para [colocar em quarentena no Office 365](manage-quarantined-messages-and-files.md) , onde um administrador de segurança ou analista pode revisar e liberar (ou excluir) essas mensagens  <br/> Bloqueia automaticamente mensagens e anexos futuros|Proteger sua organização de ataques repetidos usando os mesmos anexos de malware|
|**Replace**|Remove anexos detectados de malware  <br/> Notifica os destinatários de que os anexos foram removidos  <br/> Envia mensagens com malware detectado para [colocar em quarentena no Office 365](manage-quarantined-messages-and-files.md) , onde um administrador de segurança ou analista pode revisar e liberar (ou excluir) essas mensagens|Aumentar a visibilidade dos destinatários que os anexos foram removidos devido a um malware detectado|
|**Entrega dinâmica**|Entrega mensagens imediatamente  <br/> Substitui anexos por um arquivo de espaço reservado até que a verificação seja concluída e, em seguida, anexa novamente os anexos se nenhum malware for detectado  <br/> Inclui recursos de visualização de anexos para a maioria dos arquivos PDFs e do Office durante a verificação  <br/> Envia mensagens com malware detectado para colocar em quarentena onde um administrador de segurança ou analista pode revisar e liberar (ou excluir) essas mensagens  <br/> [Saiba mais sobre a entrega dinâmica e a visualização com anexos seguros de ATP](dynamic-delivery-and-previewing.md) <br/> |Evitar atrasos de mensagem ao proteger destinatários de arquivos mal-intencionados  <br/> Habilitar destinatários para visualizar anexos no modo de segurança enquanto a verificação está ocorrendo|
|**Habilitar redirecionamento**|Aplica-se quando a opção monitorar, bloquear ou substituir é escolhida  <br/> Envia anexos a um endereço de email especificado, onde os administradores de segurança ou os analistas podem investigar|Permitir que os administradores de segurança e analistas pesquisem anexos suspeitos|

## <a name="next-steps"></a>Próximas etapas

Quando suas políticas de anexos seguros de ATP estiverem vigentes, você poderá ver como a ATP está trabalhando para sua organização exibindo relatórios. Confira os seguintes recursos para saber mais:

- [Exibir relatórios para a proteção avançada contra ameaças do Office 365](view-reports-for-atp.md)

- [Usar o Explorer no centro de conformidade & segurança](threat-explorer.md)

Fique à frente dos novos recursos que chegam à ATP. Visite o [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) e saiba mais sobre os [novos recursos que estão sendo adicionados à ATP](office-365-atp.md#new-features-in-office-365-atp).
