---
title: Configurar equipes com proteção para dados altamente confidenciais
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
recommendations: false
description: Aprenda a implantar equipes com proteção para dados altamente confidenciais.
ms.openlocfilehash: d83c10df50d02f47a6d70ee80b2ddbf89fff37d0
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538190"
---
# <a name="configure-teams-with-protection-for-highly-sensitive-data"></a>Configurar equipes com proteção para dados altamente confidenciais

Neste artigo, examinamos a criação de uma equipe com um nível de proteção altamente confidencial. Certifique-se de ter concluído as etapas em [Implantar equipes com proteção de linha de base](configure-teams-baseline-protection.md) antes de seguir as etapas deste artigo.

Para esta camada de proteção, criamos um rótulo de confidencialidade que pode ser usado em toda a organização para equipes e arquivos altamente confidenciais. Somente membros de sua organização e convidados que você tenha especificado poderão descriptografar arquivos que usem este rótulo. Se você precisar isolar ainda mais as permissões para que somente os membros de uma equipe específica possam descriptografar arquivos, confira [Implantar uma equipe com isolamento de segurança](secure-teams-security-isolation.md).

A camada altamente confidencial oferece as seguintes proteções adicionais sobre a camada de linha de base:

- Um rótulo de confidencialidade para a equipe que permite ativar ou desativar o compartilhamento de convidados e bloquear o acesso ao conteúdo do Microsoft Office SharePoint Online para dispositivos não gerenciados. Este rótulo também pode ser usado para classificar e criptografar arquivos.
- Um tipo de link de compartilhamento padrão mais restritivo
- Somente os proprietários da equipe podem criar canais privados.
- As solicitações de acesso para o site do Microsoft Office SharePoint Online associado estão desativadas.

## <a name="guest-sharing"></a>Compartilhamento de convidados

Dependendo da natureza da sua empresa, você pode ou não querer ativar o compartilhamento de convidados para equipes que contenham dados altamente confidenciais. Se você planeja colaborar com pessoas de fora da sua organização na equipe, recomendamos ativar o compartilhamento de convidados. O Microsoft 365 inclui vários recursos de segurança e conformidade para ajudar você a compartilhar conteúdo confidencial com segurança. Geralmente, esta é uma opção mais segura do que enviar conteúdo por email diretamente para pessoas de fora da sua organização.

Para obter detalhes sobre como compartilhar com convidados com segurança, confira os seguintes recursos:

- [Limitar a exposição acidental a arquivos ao compartilhar arquivos com pessoas de fora da sua organização](./share-limit-accidental-exposure.md)
- [Criar um ambiente de compartilhamento de convidados seguro](./create-secure-guest-sharing-environment.md)

Para permitir ou bloquear o compartilhamento de convidados, usamos uma combinação de um rótulo de confidencialidade para a equipe e controles de compartilhamento no nível do site para o Microsoft Office SharePoint Online associado, ambos discutidos mais adiante.

## <a name="sensitivity-labels"></a>Rótulos de confidencialidade

Para o nível de proteção altamente confidencial, usaremos um rótulo de confidencialidade para classificar a equipe. Este rótulo também pode ser usado para classificar e criptografar arquivos individuais nesta ou em outras equipes ou em outros locais de arquivos, como o Microsoft Office SharePoint Online ou o OneDrive. 

Como primeira etapa, você deve habilitar os rótulos de confidencialidade para o Teams. Confira [Usar rótulos de confidencialidade para proteger o conteúdo no Microsoft Teams, grupos do Office 365 e sites do Microsoft Office SharePoint Online](../compliance/sensitivity-labels-teams-groups-sites.md) para obter detalhes.

Se você já possui rótulos de confidencialidade implantados em sua organização, considere como este rótulo se ajusta à sua estratégia geral de rotulação. Você pode alterar o nome ou as configurações, se necessário, para atender às necessidades da sua organização.

Depois de ativar os rótulos de confidencialidade para o Teams, a próxima etapa é criar o rótulo.

Para criar um rótulo de confidencialidade
1. Abra o [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com).
2. Em **Soluções**, clique em **Proteção de informações**.
3. Clique em **Criar um rótulo**.
4. Dê um nome ao rótulo. Sugerimos **Altamente confidencial**, mas você pode escolher um nome diferente se este nome já estiver em uso.
5. Adicione um nome de exibição e uma descrição e clique em **Avançar**.
6. Na página **Definir o escopo para este rótulo**, selecione **Arquivos e emails** e **Grupos e sites** e clique em **Avançar**.
7. Na página **Escolher configurações de proteção para arquivos e emails**, selecione **Criptografar arquivos e emails** e clique em **Avançar**.
8. Na página **Criptografia**, escolha **Definir configurações de criptografia**.
9. Em **Atribuir permissões a usuários e grupos específicos**, clique em **Atribuir permissões**.
10. Clique em **Adicionar todos os usuários e grupos em sua organização**.
11. Se houver usuários convidados que devam ter permissões para descriptografar arquivos, clique em **Adicionar usuários ou grupos** e adicione-os.
12.  Clique em **Salvar** e, em seguida, clique em **Avançar**.
13. Na página *Rotulagem automática para arquivos e emails**, clique em **Avançar**.
14. Na página **Definir configurações de proteção para grupos e sites**, selecione **Configurações de privacidade e acesso de usuário externo** e **Configurações de acesso ao dispositivo e compartilhamento externo** e clique em **Avançar**.
15. Na página **Definir privacidade e configurações de acesso de usuário externo**, em **Privacidade**, selecione a opção **Privado**.
16. Se desejar permitir o acesso de convidado, em **Acesso de usuário externo**, selecione **Permitir que proprietários do Grupo Microsoft 365 adicionem pessoas de fora de sua organização ao grupo como convidados**.
17. Clique em **Avançar**.
18. Na página **Definir compartilhamento externo e configurações de acesso ao dispositivo**, selecione **Controlar compartilhamento externo de sites rotulados do Microsoft Office SharePoint Online**.
19. Em **O conteúdo pode ser compartilhado com**, escolha **Convidados novos e existentes** se estiver permitindo o acesso de convidado ou **Somente as pessoas em sua organização** se não.
20. Em **Acesso de dispositivos não gerenciados**, escolha **Bloquear acesso**. (Se você está permitindo convidados e eles não têm dispositivos gerenciados, você pode querer escolher **Permitir acesso limitado apenas pela web**.)
21. Clique em **Avançar**.
22. Na página **Rotulagem automática para colunas do banco de dados**, clique em **Avançar**.
23. Clique em **Criar rótulo** e, a seguir, clique em **Concluído**.

Depois de criar o rótulo, você precisará publicá-lo para os usuários que o usarão. Para proteção confidencial, disponibilizaremos o rótulo para todos os usuários. Publique o rótulo no Centro de conformidade do Microsoft 365, na guia **Políticas de rótulo** da página **Proteção de informações**. Se você possuir uma política que se aplique a todos os usuários, adicione este rótulo a essa política. Se você precisar criar uma nova política, confira [Publicar rótulos de confidencialidade por meio da criação de uma política de rótulos](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).

## <a name="create-a-team"></a>Criar uma equipe

A configuração adicional do cenário altamente confidencial é feita no site do Microsoft Office SharePoint Online associado à equipe; portanto, a próxima etapa é criar uma equipe.

Para criar uma equipe para informações altamente confidenciais
1. No Teams, clique em **Equipes** no lado esquerdo do aplicativo e clique em **Criar equipe ou ingressar em uma** na parte inferior da lista de equipes.
2. Clique em **Criar equipe** (primeiro cartão, canto superior esquerdo).
3. Escolha **Criar uma equipe do zero**.
4. Na lista **Confidencialidade**, escolha o rótulo **Altamente confidencial** que você acabou de criar.
5. Em **Privacidade**, clique em **Privado**.
6. Digite um nome para a equipe e clique em **Criar**.
7. Adicione usuários à equipe e clique em **Fechar**.

## <a name="private-channel-settings"></a>Configurações de canal privado

Nesta camada, restringimos a criação de canais privados os proprietários da equipe.

Para restringir a criação de canais privados
1. Na equipe, clique em **Mais opções** e em **Gerenciar equipe**.
2. Na guia **Configurações**, expanda **Permissões de membro**.
3. Desmarque a caixa de seleção **Permitir que os membros criem canais privados**.

Você também pode usar [políticas de equipes](/MicrosoftTeams/teams-policies) para controlar quem pode criar canais privados.

## <a name="sharepoint-settings"></a>Configurações do Microsoft Office SharePoint Online

Sempre que você cria uma nova equipe com o rótulo altamente confidencial, há duas etapas a serem executadas no Microsoft Office SharePoint Online:

- Atualize as configurações de compartilhamento de convidados do site no Centro de Administração do SharePoint Online para corresponder ao que você escolheu quando criou o rótulo, e atualize o link de compartilhamento padrão para *Pessoas com acesso existente*.
- Atualize as configurações de compartilhamento do site no próprio site para impedir que os membros compartilhem arquivos, pastas ou o site, e desative as solicitações de acesso.

### <a name="site-guest-sharing-settings"></a>Configurações de compartilhamento de convidados do site

A configuração de compartilhamento de convidados que você escolheu quando criou o rótulo (que afeta somente a associação à equipe) deve corresponder às configurações de compartilhamento de convidados do site do Microsoft Office SharePoint Online associado, da seguinte maneira:

|Configuração do rótulo|Configuração do site do Microsoft Office SharePoint Online|
|:------------|:----------------------|
|**Permitir que proprietários de grupos do Office 365 adicionem pessoas de fora da organização aos grupos** selecionado|**Convidados novos e existentes** (padrão para novas equipes)|
|**Permitir que os proprietários de grupos do Office 365 adicionem pessoas de fora da organização aos grupos** não selecionado|**Somente pessoas em sua organização**|

Para atualizar as configurações do site
1. Abra o [Centro de Administração do SharePoint Online](https://admin.microsoft.com/sharepoint).
2. Em **Sites**, clique em **Sites ativos**.
3. Clique no site associado à equipe.
4. Na guia **Políticas**, em **Compartilhamento externo**, clique em **Editar**.
5. Se você permitiu o compartilhamento de convidados ao criar o rótulo Altamente confidencial, certifique-se de que **Convidados novos e existentes** esteja selecionado. Se você não permitiu o compartilhamento quando criou o rótulo, escolha **Somente pessoas da sua organização**.
6. Em Tipo de link de compartilhamento padrão, limpe a caixa de seleção **O mesmo que a configuração de nível de organização** e selecione **Pessoas com acesso existente**.
7. Clique em **Salvar**.

Se você deseja criar um script como parte do processo de criação da equipe, use [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) com os seguintes parâmetros:

- `-SharingCapability Disabled` para desativar o compartilhamento de convidados (ativado por padrão)
- `-DefaultSharingLinkType Internal` para alterar o link de compartilhamento padrão para *Pessoas específicas*

#### <a name="private-channels"></a>Canais privados

Se você adicionar canais privados à equipe, cada canal privado criará um novo site do Microsoft Office SharePoint Online com as configurações de compartilhamento padrão. Estes sites não estão visíveis no Centro de Administração do SharePoint Online; portanto, você deve usar o cmdlet Set-SPOSite do Windows PowerShell para atualizar as configurações de compartilhamento de convidados.

### <a name="site-sharing-settings"></a>Configurações de compartilhamento de site

Para ajudar a garantir que o site do Microsoft Office SharePoint Online não seja compartilhado com pessoas que não são membros da equipe, limitamos esse compartilhamento aos proprietários. Também limitamos o compartilhamento de arquivos e pastas aos proprietários da equipe. Isso ajuda a garantir que os proprietários estejam cientes sempre que um arquivo for compartilhado com alguém de fora da equipe.

Para configurar o compartilhamento de site somente para proprietários
1. No Teams, navegue até a guia **Geral** da equipe que deseja atualizar.
2. Na barra de ferramentas da equipe, clique em **Arquivos**.
3. Clique nas reticências e em **Abrir no SharePoint**.
4. Na barra de ferramentas do site do SharePoint subjacente, clique no ícone de configurações e, em seguida, clique em **Permissões do site**.
5. No painel **Permissões do site**, em **Compartilhamento do site**, clique em **Alterar como os membros podem compartilhar**.
6. Em **Permissões de compartilhamento**, escolha **Somente proprietários do site podem compartilhar arquivos, pastas e o site**.
7. Defina **Permitir solicitações de acesso** como **Desativado** e clique em **Salvar**.

## <a name="see-also"></a>Confira também

[Criar e configurar rótulos de confidencialidade e suas políticas](../compliance/create-sensitivity-labels.md)