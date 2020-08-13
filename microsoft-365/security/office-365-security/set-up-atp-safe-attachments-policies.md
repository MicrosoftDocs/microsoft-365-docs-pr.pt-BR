---
title: Configurar políticas de anexos seguros de ATP do Office 365
f1.keywords:
- NOCSH
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
description: Saiba como definir políticas de anexos seguros para proteger sua organização contra arquivos mal-intencionados no email.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a8b69d114b1387a1ef76d962424149c1db93ce04
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656618"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a>Configurar políticas de anexos seguros de ATP do Office 365

> [!IMPORTANT]
> Este artigo destina-se aos clientes corporativos que têm a [Proteção Avançada contra Ameaças do Office 365](office-365-atp.md). Se você for um usuário doméstico que procura informações sobre anexos seguros no Outlook, consulte [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Pessoas costumam enviar, receber e compartilhar anexos, como documentos, apresentações, planilhas e muito mais. Nem sempre é fácil dizer se um anexo é seguro ou mal-intencionado apenas olhando uma mensagem de email. E a última coisa que você deseja é um anexo mal-intencionado para obter estragos para sua organização. Felizmente, a [proteção avançada contra ameaças do Office 365](office-365-atp.md) (ATP) pode ajudar. Você pode configurar as políticas de [anexos seguros de ATP](atp-safe-attachments.md) para ajudar a garantir que sua organização seja protegida contra ataques por anexos de email não seguros.

## <a name="what-to-do"></a>O que fazer

1. Revisar os pré-requisitos

2. Configurar uma política de anexos seguros de ATP

3. Saiba mais sobre as opções de política de anexos seguros de ATP

## <a name="step-1-review-the-prerequisites"></a>Etapa 1: revisar os pré-requisitos

- Certifique-se de que sua organização tenha a [proteção avançada contra ameaças do Office 365](office-365-atp.md).

- Verifique se você tem as permissões necessárias. Para definir (ou editar) políticas de ATP, você deve ter uma função de gerenciamento de organização do Exchange Online (o administrador global é atribuído a essa função por padrão) ou as funções de administrador de segurança e gerenciamento de higiene do Exchange Online. Para obter mais detalhes, consulte a seguinte tabela:

  ****

  |Role|Onde/como a atribuição|
  |---|---|
  |administrador global |Por padrão, a pessoa que se inscreve para comprar a Microsoft 365 é um administrador global. (Consulte [about Microsoft 365 admin Roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) para saber mais.)|
  |Administrador de Segurança |Centro de administração do Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
  |Gerenciamento de organização do Exchange Online, gerenciamento de higiene do Exchange Online |Centro de administração do Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>ou <br>  Cmdlets do PowerShell (consulte [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|
  |

  Para saber mais sobre funções e permissões, consulte [permissões no centro de &amp; conformidade de segurança](permissions-in-the-security-and-compliance-center.md).

- [Saiba mais sobre as opções de política de anexos seguros de ATP](#step-3-learn-about-atp-safe-attachments-policy-options) (neste artigo). Algumas opções, como as opções monitorar ou substituir, podem resultar em um atraso menor de email enquanto os anexos são verificados. Para evitar atrasos de mensagens, considere o uso da [entrega dinâmica e da visualização](dynamic-delivery-and-previewing.md).

- Aguarde até 30 minutos para que a política nova ou atualizada se espalhe para todos os datacenters da Microsoft 365.

## <a name="step-2-set-up-or-edit-an-atp-safe-attachments-policy"></a>Etapa 2: configurar (ou editar) uma política de anexos seguros de ATP

1. Acesse [https://protection.office.com](https://protection.office.com) e entre com sua conta corporativa ou de estudante.

2. No centro de &amp; conformidade de segurança, no painel de navegação esquerdo, em **Gerenciamento de ameaças**, escolha **Policy** \> **anexos seguros**da política.

3. Se você vir **ativar a ATP para SharePoint, onedrive e Microsoft Teams**, recomendamos que você selecione essa opção. Isso habilitará a [proteção avançada contra ameaças do Office 365 para o SharePoint, o onedrive e o Microsoft Teams](atp-for-spo-odb-and-teams.md) para seu ambiente do Microsoft 365.

4. Escolha **novo** (o botão novo é semelhante a um sinal de adição ( **+** )) para começar a criar sua política.

5. Especifique o nome, a descrição e as configurações da política.<br/><br/>**Exemplo:** Para configurar uma política chamada "sem atrasos" que entrega mensagens de todos os usuários imediatamente e anexar novamente os anexos após serem verificados, você pode especificar as seguintes configurações:

   - Na caixa **nome** , digite nenhum atraso.

   - Na caixa **Descrição** , digite uma descrição como, entrega mensagens imediatamente e reanexa os anexos após a verificação.

   - Na seção resposta, escolha a opção de **entrega dinâmica** . ([Saiba mais sobre entrega dinâmica e visualização com anexos seguros de ATP](dynamic-delivery-and-previewing.md).)

   - Na seção **redirecionar anexo** , selecione a opção para habilitar o redirecionamento e digite o endereço de email do administrador global, administrador de segurança ou analista de segurança que irá investigar anexos mal-intencionados.

   - Na seção **aplica-se** a, escolha **o domínio do destinatário**e selecione o seu domínio. Escolha **Adicionar**e, em seguida, escolha **OK**.

6. Escolha **Salvar**.

Considere configurar várias políticas de anexos seguros de ATP para sua organização. Essas políticas serão aplicadas na ordem em que estão listadas na página de **anexos seguros de ATP** . Após uma política ter sido definida ou editada, permita pelo menos 30 minutos para que as políticas entrem em vigor nos datacenters da Microsoft.

## <a name="step-3-learn-about-atp-safe-attachments-policy-options"></a>Etapa 3: Saiba mais sobre as opções de política de anexos seguros de ATP

À medida que você configura as políticas de anexos seguros de ATP, você escolhe entre várias opções, incluindo monitor, bloqueio, substituição, entrega dinâmica e assim por diante. Caso você esteja se perguntando o que essas opções fazem, a tabela a seguir resume cada e seu efeito.

****

|Opção|Efeito|Use quando quiser:|
|---|---|---|
|**Desabilitado**|Não examina anexos de malware  <br/> Não atrasa a entrega de mensagens|Desligar a verificação para destinatários selecionados.  <br/> Evitar atrasos desnecessários no roteamento de email interno.  <br/> **Essa opção não é recomendada para a maioria dos usuários. Você só deve usar essa opção para desativar a verificação de anexos seguros de ATP para destinatários que recebem emails de remetentes confiáveis.**|
|**Monitor**|Entrega mensagens com anexos e rastreia o que acontece com o malware detectado|Veja onde o malware detectado entra em sua organização|
|**Bloquear**|Impede que mensagens com anexos de malware detectados continuem  <br/> Envia mensagens com malware detectado para [colocar em quarentena no Office 365](manage-quarantined-messages-and-files.md) , onde um administrador de segurança ou analista pode revisar e liberar (ou excluir) essas mensagens  <br/> Bloqueia automaticamente mensagens e anexos futuros|Proteger sua organização de ataques repetidos usando os mesmos anexos de malware|
|**Replace**|Remove anexos detectados de malware  <br/> Notifica os destinatários de que os anexos foram removidos  <br/> Envia mensagens com malware detectado para [colocar em quarentena no Office 365](manage-quarantined-messages-and-files.md) , onde um administrador de segurança ou analista pode revisar e liberar (ou excluir) essas mensagens|Aumentar a visibilidade dos destinatários que os anexos foram removidos devido a um malware detectado|
|**Entrega dinâmica**|Entrega mensagens imediatamente  <br/> Substitui anexos por um arquivo de espaço reservado até que a verificação seja concluída e, em seguida, anexa novamente os anexos se nenhum malware for detectado  <br/> Inclui recursos de visualização de anexos para a maioria dos arquivos PDFs e do Office durante a verificação  <br/> Envia mensagens com malware detectado para colocar em quarentena onde um administrador de segurança ou analista pode revisar e liberar (ou excluir) essas mensagens  <br/> [Saiba mais sobre a entrega dinâmica e a visualização com anexos seguros de ATP](dynamic-delivery-and-previewing.md) <br/> |Evitar atrasos de mensagem ao proteger destinatários de arquivos mal-intencionados  <br/> Habilitar destinatários para visualizar anexos no modo de segurança enquanto a verificação está ocorrendo|
|**Habilitar redirecionamento**|Aplica-se quando a opção monitorar, bloquear ou substituir é escolhida  <br/> Envia anexos a um endereço de email especificado, onde os administradores de segurança ou os analistas podem investigar|Permitir que os administradores de segurança e analistas pesquisem anexos suspeitos|
|**Aplicar a seleção acima se a verificação de malware por anexos expirar ou ocorrer erro**|Aplica a ação configurada para anexos não seguros aos anexos que não podem ser verificados (devido ao tempo limite ou erro)|
|

## <a name="next-steps"></a>Próximas etapas

Quando suas políticas de anexos seguros de ATP estiverem vigentes, você poderá ver como a ATP está trabalhando para sua organização exibindo relatórios. Confira os seguintes recursos para saber mais:

- [Exibir relatórios para a proteção avançada contra ameaças do Office 365](view-reports-for-atp.md)

- [Usar o Explorer no centro de conformidade & segurança](threat-explorer.md)

Fique à frente dos novos recursos que chegam à ATP. Visite o [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) e saiba mais sobre os [novos recursos que estão sendo adicionados à ATP](office-365-atp.md#new-features-in-office-365-atp).
