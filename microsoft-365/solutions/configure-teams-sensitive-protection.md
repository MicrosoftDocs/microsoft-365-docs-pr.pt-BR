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
description: Aprenda a implantar equipes com proteção para dados altamente confidenciais.
ms.openlocfilehash: 16c4ceedcafee02ca5d168cc70fc61bb8d01fc72
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750782"
---
# <a name="configure-teams-with-protection-for-sensitive-data"></a>Configurar equipes com proteção para dados altamente confidenciais

Neste artigo, examinamos a criação de uma equipe com um nível de proteção altamente confidencial. Certifique-se de ter concluído as etapas em [Implantar equipes com proteção de linha de base](configure-teams-baseline-protection.md) antes de seguir as etapas deste artigo. A camada altamente confidencial oferece as seguintes proteções adicionais sobre a camada de linha de base:

- Um rótulo de confidencialidade para a equipe que permite ativar ou desativar o compartilhamento de convidados e limita o acesso ao conteúdo do Microsoft Office SharePoint Online a somente Web para dispositivos não gerenciados. Este rótulo também pode ser usado para classificar e criptografar arquivos.
- Um tipo de link de compartilhamento padrão mais restritivo
- Somente os proprietários da equipe podem criar canais privados.

## <a name="guest-sharing"></a>Compartilhamento de convidados

Dependendo da natureza da sua empresa, você pode ou não querer ativar o compartilhamento de convidados para equipes que contenham dados altamente confidenciais. Se você planeja colaborar com pessoas de fora da sua organização na equipe, recomendamos ativar o compartilhamento de convidados. O Microsoft 365 inclui vários recursos de segurança e conformidade para ajudar você a compartilhar conteúdo confidencial com segurança. Geralmente, esta é uma opção mais segura do que enviar conteúdo por email diretamente para pessoas de fora da sua organização.

Para obter detalhes sobre como compartilhar com convidados com segurança, confira os seguintes recursos:

- [Limite a exposição acidental a arquivos ao compartilhar arquivos com pessoas de fora da sua organização](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)
- [Criar um ambiente seguro de compartilhamento de convidados](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

Para permitir ou bloquear o compartilhamento de convidados, usamos uma combinação de um rótulo de confidencialidade para a equipe e controles de compartilhamento no nível do site para o Microsoft Office SharePoint Online associado, ambos discutidos mais adiante.

## <a name="sensitivity-labels"></a>Rótulos de confidencialidade

Para o nível de proteção altamente confidencial, usaremos um rótulo de confidencialidade para classificar a equipe. Este rótulo também pode ser usado para classificar e criptografar arquivos individuais nesta ou em outras equipes ou em outros locais de arquivos, como o Microsoft Office SharePoint Online ou o OneDrive. 

Como primeira etapa, você deve habilitar os rótulos de confidencialidade para o Teams. Confira [Usar rótulos de confidencialidade para proteger o conteúdo no Microsoft Teams, grupos do Office 365 e sites do Microsoft Office SharePoint Online](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) para obter detalhes.

Se você já possui rótulos de confidencialidade implantados em sua organização, considere como este rótulo se ajusta à sua estratégia geral de rotulação. Você pode alterar o nome ou as configurações, se necessário, para atender às necessidades da sua organização.

Depois de ativar os rótulos de confidencialidade para o Teams, a próxima etapa é criar o rótulo.

Para criar um rótulo de confidencialidade
1. Abra o [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com).
2. Em **Soluções**, clique em **Proteção de informações**.
3. Clique em **Criar um rótulo**.
4. Dê um nome ao rótulo. Sugerimos **Confidencial**, mas você pode escolher um nome diferente se esse já estiver em uso.
5. Adicione um nome de exibição e uma descrição e clique em **Avançar**.
6. Na página **Definir o escopo para este rótulo**, selecione **Arquivos e emails** e **Grupos e sites** e clique em **Avançar**.
7. Na página **Escolher configurações de proteção para arquivos e emails**, clique em **Avançar**.
8. Na página *Rotulagem automática para arquivos e emails**, clique em **Avançar**.
9. Na página **Definir configurações de proteção para grupos e sites**, selecione **Configurações de privacidade e acesso de usuário externo** e **Configurações de acesso ao dispositivo e compartilhamento externo** e clique em **Avançar**.
10. Na página **Definir privacidade e configurações de acesso de usuário externo**, em **Privacidade**, selecione a opção **Privado**.
11. Se desejar permitir o acesso de convidado, em **Acesso de usuário externo**, selecione **Permitir que proprietários do Grupo Microsoft 365 adicionem pessoas de fora de sua organização ao grupo como convidados**.
12. Clique em **Avançar**.
13. Na página **Definir compartilhamento externo e configurações de acesso ao dispositivo**, selecione **Controlar compartilhamento externo de sites rotulados do Microsoft Office SharePoint Online**.
14. Em **O conteúdo pode ser compartilhado com**, escolha **Convidados novos e existentes** se estiver permitindo o acesso de convidado ou **Somente as pessoas em sua organização** se não.
15. Em **Acesso de dispositivos não gerenciados**, escolha **Permitir acesso limitado apenas à web**.
16. Clique em **Avançar**.
17. Na página **Rotulagem automática para colunas do banco de dados**, clique em **Avançar**.
18. Clique em **Criar rótulo** e, a seguir, clique em **Concluído**.

Depois de criar o rótulo, você precisará publicá-lo para os usuários que o usarão. Para proteção confidencial, disponibilizaremos o rótulo para todos os usuários. Publique o rótulo no Centro de conformidade do Microsoft 365, na guia **Políticas de rótulo** da página **Proteção de informações**. Se você possuir uma política que se aplique a todos os usuários, adicione este rótulo a essa política. Se você precisar criar uma nova política, confira [Publicar rótulos de confidencialidade por meio da criação de uma política de rótulos](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).

## <a name="create-a-team"></a>Criar uma equipe

A configuração adicional do cenário altamente confidencial é feita no site do Microsoft Office SharePoint Online associado à equipe; portanto, a próxima etapa é criar uma equipe.

Para criar uma equipe para informações altamente confidenciais
1. Nas equipes, clique em **Equipes** no lado esquerdo do aplicativo e clique em **Ingressar ou criar uma equipe** na parte inferior da lista de equipes.
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

Você também pode usar [políticas de equipes](https://docs.microsoft.com/MicrosoftTeams/teams-policies) para controlar quem pode criar canais privados.

## <a name="sharepoint-settings"></a>Configurações do SharePoint

Sempre que você cria uma nova equipe com o rótulo altamente confidencial, há duas etapas a serem executadas no Microsoft Office SharePoint Online:

- Atualize as configurações de compartilhamento de convidados do site no Centro de Administração do SharePoint Online para corresponder ao que você escolheu quando criou o rótulo, e atualize o link de compartilhamento padrão para *Pessoas Específicas*.
- Atualize as configurações de compartilhamento do site no próprio site para impedir que os membros compartilhem o site.

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
5. Se você permitiu o compartilhamento de convidados ao criar o rótulo confidencial, certifique-se de que **Convidados novos e existentes** esteja selecionados. Se você não permitiu o compartilhamento quando criou o rótulo, escolha **Somente pessoas da sua organização**.
6. Em tipo de link de compartilhamento padrão, desmarque a caixa de seleção **igual ao nível da organização** e selecione **pessoas específicas (somente as pessoas que o usuário especificar)**.
7. Clique em **Salvar**.

Se você deseja criar um script como parte do processo de criação da equipe, use [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) com os seguintes parâmetros:

- `-SharingCapability Disabled` para desativar o compartilhamento de convidados (ativado por padrão)
- `-DefaultSharingLinkType Internal` para alterar o link de compartilhamento padrão para *Pessoas específicas*

#### <a name="private-channels"></a>Canais privados

Se você adicionar canais privados à equipe, cada canal privado criará um novo site do Microsoft Office SharePoint Online com as configurações de compartilhamento padrão. Estes sites não estão visíveis no Centro de Administração do SharePoint Online; portanto, você deve usar o cmdlet Set-SPOSite do Windows PowerShell para atualizar as configurações de compartilhamento de convidados.

### <a name="site-sharing-settings"></a>Configurações de compartilhamento de site

Para ajudar a garantir que o site do Microsoft Office SharePoint Online não seja compartilhado com pessoas que não sejam membros da equipe, limitamos esse compartilhamento aos proprietários.

Para configurar o compartilhamento de site somente para proprietários
1. No Teams, navegue até a guia **Geral** da equipe que deseja atualizar.
2. Na barra de ferramentas da equipe, clique em **Arquivos**.
3. Clique nas reticências e em **Abrir no SharePoint**.
4. Na barra de ferramentas do site do SharePoint subjacente, clique no ícone de configurações e, em seguida, clique em **Permissões do site**.
5. No painel Permissões de site, em **Configurações de Compartilhamento**, clique em **Alterar configurações de compartilhamento**.
6. Em **Compartilhar permissões**, escolha **Proprietários de membros do site e pessoas com permissões de edição podem compartilhar arquivos e pastas, mas apenas os proprietários do site podem compartilhar o site** e em seguida clique em **Salvar**.


## <a name="see-also"></a>Confira também

[Criar e configurar rótulos de confidencialidade e suas políticas](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels)


