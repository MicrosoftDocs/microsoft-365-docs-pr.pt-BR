---
title: Configurar uma equipe com isolamento de segurança
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
description: Saiba como criar uma equipe com um rótulo de confidencialidade exclusivo para segurança.
ms.openlocfilehash: 4d305e952d48d42afffe91466121c67621aa9d85
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52113397"
---
# <a name="configure-a-team-with-security-isolation"></a>Configurar uma equipe com isolamento de segurança

Este artigo fornece recomendações e etapas para configurar uma equipe privada no Microsoft Teams e usar um rótulo de confidencialidade exclusivo para criptografar arquivos, para que somente os membros da equipe possam descriptografá-los.

Além do acesso privado, este artigo descreve como configurar o site do Microsoft Office SharePoint Online associado, que você pode acessar na seção **Arquivos** de um canal de equipe, para obter a segurança adicional necessária para armazenar dados altamente regulamentados.

Os elementos de configuração para uma equipe com isolamento de segurança são:

- Uma equipe privada
- Segurança adicional no site do Microsoft Office SharePoint Online associado à equipe que:
  - Impede que os membros do site compartilhem o site com outras pessoas.
  - Impede que aqueles que não são membros do site solicitem acesso a ele.
- Um rótulo de confidencialidade especificamente para essa equipe que:
    - Impede o acesso ao conteúdo do Microsoft Office SharePoint Online a partir de dispositivos não gerenciados
    - Permite ou nega o acesso de convidados à equipe, dependendo de seus requisitos
    - Criptografa documentos aos quais o rótulo é aplicado

> [!IMPORTANT]
> Certifique-se de ter ativado os [rótulos de confidencialidade para proteger o conteúdo em sites do Microsoft Teams, Office 365 e Microsoft Office SharePoint Online](../compliance/sensitivity-labels-teams-groups-sites.md) antes de prosseguir com as etapas deste artigo.

Assista a esse vídeo para obter uma visão geral do processo de implementação.
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mGHf]

<a name="poster"></a> Para obter um resumo de 1 página desse cenário, confira o [pôster do Microsoft Teams com isolamento de segurança](../downloads/team-security-isolation-poster.pdf).

[![Pôster do Microsoft Teams com isolamento de segurança](../media/secure-teams-security-isolation/team-security-isolation-poster.png)](../downloads/team-security-isolation-poster.pdf)

Também é possível descarregar este pôster nos formatos [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pdf) ou [PowerPoint](https://download.microsoft.com/download/8/0/5/8057fc16-c044-40b6-a652-7ed555ba2895/team-security-isolation-poster.pptx) e imprimi-lo em papel tamanho carta, legal, ou tabloide (11 x 17).

Tente esta configuração em seu próprio ambiente de laboratório de teste com [estas instruções](team-security-isolation-dev-test.md).

Veja como a Contoso Corporation usou uma equipe isolada para um projeto ultrassecreto [neste estudo de caso](contoso-team-for-top-secret-project.md).

## <a name="initial-protections"></a>Proteções iniciais

Para ajudar a proteger o acesso à equipe e ao site subjacente do Microsoft Office SharePoint Online, revise as seguintes práticas recomendadas:
- [Políticas de acesso de dispositivos e identidades](../security/office-365-security/identity-access-policies.md)
- [Políticas de acesso do SharePoint Online](../security/office-365-security/sharepoint-file-access-policies.md)
- [Implantar equipes com proteção de linha de base](configure-teams-baseline-protection.md)

## <a name="guest-sharing"></a>Compartilhamento de convidados

Dependendo da natureza do seu negócio, você pode ou não querer ativar o compartilhamento de convidados para esta equipe. Se você planeja colaborar com pessoas de fora da sua organização na equipe, ative o compartilhamento de convidados. 

Para obter detalhes sobre como compartilhar com convidados com segurança, confira os seguintes recursos:

- [Limitar a exposição acidental a arquivos ao compartilhar arquivos com pessoas de fora da sua organização](./share-limit-accidental-exposure.md)
- [Criar um ambiente de compartilhamento de convidados seguro](./create-secure-guest-sharing-environment.md)

Para permitir ou bloquear o compartilhamento de convidados, usamos uma combinação de um rótulo de confidencialidade para a equipe e controles de compartilhamento no nível do site para o site do Microsoft Office SharePoint Online associado, ambos discutidos mais adiante.

## <a name="create-a-private-team"></a>Criar uma equipe privada

Como estamos criando um rótulo de confidencialidade especificamente para essa equipe, o próximo passo é criar a equipe. Se você já possui uma equipe, pode usá-la.

Para criar uma equipe para informações confidenciais
1. No Teams, clique em **Equipes** no lado esquerdo do aplicativo e clique em **Criar equipe ou ingressar em uma** na parte inferior da lista de equipes.
2. Clique em **Criar equipe** (primeiro cartão, canto superior esquerdo).
3. Escolha **Criar uma equipe do zero**.
4. Na lista **Confidencialidade**, mantenha o padrão.
5. Em **Privacidade**, clique em **Privado**.
6. Digite um nome para a equipe relacionada ao seu projeto confidencial. Por exemplo, **Projeto Saturno**.
7. Clique em **Criar**.
8. Adicione usuários à equipe e clique em **Fechar**.

## <a name="private-channel-settings"></a>Configurações de canal privado

Recomendamos restringir a criação de canais privados aos proprietários da equipe.

Para restringir a criação de canais privados
1. Na equipe, clique em **Mais opções** e em **Gerenciar equipe**.
2. Na guia **Configurações**, expanda **Permissões de membro**.
3. Desmarque a caixa de seleção **Permitir que os membros criem canais privados**.

Você também pode usar [políticas de equipes](/MicrosoftTeams/teams-policies) para controlar quem pode criar canais privados.

## <a name="create-a-sensitivity-label"></a>Criar um rótulo de confidencialidade

Para configurar uma equipe para isolamento de segurança, usaremos um rótulo de confidencialidade criado especificamente para essa equipe. Esse rótulo é usado no nível da equipe para controlar o compartilhamento de convidados e bloquear o acesso a partir de dispositivos não gerenciados. Ele também pode ser usado para classificar e criptografar arquivos individuais na equipe, para que somente proprietários e membros da equipe possam abri-los.

Se você tiver um parceiro interno ou um grupo de partes interessadas capaz de visualizar documentos criptografados, mas não editá-los, poderá adicioná-los ao rótulo com permissões somente de visualização. Em seguida, você poderá adicionar essas pessoas ao site do Microsoft Office SharePoint Online da equipe com permissões de Leitura, e elas terão acesso somente leitura ao site em que os documentos são mantidos, mas não à equipe em si.


Para criar um rótulo de confidencialidade
1. Abra o [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com).
2. Em **Soluções**, clique em **Proteção de informações**.
3. Clique em **Criar um rótulo**.
4. Dê um nome para o rótulo. Sugerimos nomeá-lo após a equipe com quem você vai usá-lo.
5. Adicione um nome de exibição e uma descrição e clique em **Avançar**.
6. Na página **Definir o escopo para este rótulo**, selecione **Arquivos e emails** e **Grupos e sites** e clique em **Avançar**.
7. Na página **Escolher configurações de proteção para arquivos e emails**, selecione **Criptografar arquivos e emails** e clique em **Avançar**.
8. Na página **Criptografia**, escolha **Definir configurações de criptografia**.
9. Clique em **Adicionar usuários ou grupos**, selecione a equipe que você criou e clique em **Adicionar**
10. Clique em **Selecionar permissões**.
11. Escolha **Coautoria** na lista suspensa e clique em **Salvar**.
12. Se você deseja incluir usuários ou grupos com acesso somente leitura a arquivos com o rótulo:
    1. Clique em **Atribuir permissões**.
    1. Clique em **Adicionar usuários ou grupos**, selecione os usuários ou grupos que você deseja adicionar e clique em **Adicionar**.
    1. Clique em **Selecionar permissões**.
    1. Escolha **Visualizador** na lista suspensa e clique em **Salvar**.
13.  Clique em **Salvar** e, em seguida, clique em **Avançar**.
14. Na página *Rotulagem automática para arquivos e emails**, clique em **Avançar**.
15. Na página **Definir configurações de proteção para grupos e sites**, selecione **Configurações de privacidade e acesso de usuário externo** e **Configurações de acesso ao dispositivo e compartilhamento externo** e clique em **Avançar**.
16. Na página **Definir privacidade e configurações de acesso de usuário externo**, em **Privacidade**, selecione a opção **Privado**.
17. Se desejar permitir o acesso de convidado, em **Acesso de usuário externo**, selecione **Permitir que proprietários do Grupo Microsoft 365 adicionem pessoas de fora de sua organização ao grupo como convidados**.
18. Clique em **Avançar**.
19. Na página **Definir compartilhamento externo e configurações de acesso ao dispositivo**, selecione **Controlar compartilhamento externo de sites rotulados do Microsoft Office SharePoint Online**.
20. Em **O conteúdo pode ser compartilhado com**, escolha **Convidados novos e existentes** se estiver permitindo o acesso de convidado ou **Somente as pessoas em sua organização** se não.
21. Em **Acesso de dispositivos não gerenciados**, escolha **Bloquear acesso**.
22. Clique em **Avançar**.
23. Na página **Rotulagem automática para colunas do banco de dados**, clique em **Avançar**.
24. Clique em **Criar rótulo** e, a seguir, clique em **Concluído**.

Depois de criar o rótulo, você precisará publicá-lo para os usuários que o usarão. Nesse caso, disponibilizaremos o rótulo apenas para as pessoas da equipe.

Para publicar um rótulo de confidencialidade
1. No Centro de conformidade do Microsoft 365, na página **Proteção de informações**, escolha a guia **Políticas de rótulo**.
2. Clique em **Publicar rótulos**.
3. Na página **Escolher rótulos de confidencialidade para publicar**, clique em **Escolher rótulos de confidencialidade para publicar**.
4. Selecione o rótulo que você criou e clique em **Adicionar**.
5. Clique em **Avançar**.
6. Na página Publicar para usuários e grupos, clique em **Escolher usuários e grupos**.
7. Clique em **Adicionar** e selecione a equipe que você criou.
8. Clique em **Adicionar** e, em seguida, clique em **Concluído**.
9. Clique em **Avançar**.
10. Na página Configurações de política, marque a caixa de seleção **Os usuários devem fornecer uma justificativa para remover um rótulo ou um rótulo de classificação inferior** e clique em **Avançar**.
11. Digite um nome para a política e clique em **Avançar**.
12. Clique em **Enviar** e clique em **Concluído**.

## <a name="apply-the-label-to-the-team"></a>Aplicar o rótulo à equipe

Depois que o rótulo for publicado, você deverá aplicá-lo à equipe para que o compartilhamento de convidados e as configurações dos dispositivos gerenciados entrem em vigor. Isso é feito no Centro de Administração do SharePoint Online. Observe que pode demorar um pouco para que o rótulo fique disponível após a publicação.

Para aplicar o rótulo de confidencialidade
1. Abra o [Centro de Administração do SharePoint Online](https://admin.microsoft.com/sharepoint).
2. Em **Sites**, clique em **Sites ativos**.
3. Clique no site associado à equipe.
4. Na guia **Políticas**, em **Confidencialidade**, clique em **Editar**.
5. Selecione o rótulo que você criou e clique em **Salvar**.

## <a name="sharepoint-settings"></a>Configurações do Microsoft Office SharePoint Online

Há três etapas a serem seguidas no Microsoft Office SharePoint Online:

- Atualize as configurações de compartilhamento de convidados do site no Centro de Administração do SharePoint Online para corresponder às que você escolheu quando criou o rótulo, e atualize o link de compartilhamento padrão para *Pessoas com acesso existente*.
- Atualize as configurações de compartilhamento do site no próprio site para impedir que os membros compartilhem arquivos, pastas ou o site e desative as solicitações de acesso.
- Se você adicionou pessoas ou grupos ao rótulo com permissões de Visualizador, poderá adicioná-los ao site do Microsoft Office SharePoint Online com permissões de Leitura.

### <a name="sharepoint-guest-settings"></a>Configurações de convidado do Microsoft Office SharePoint Online

A configuração de compartilhamento de convidados que você escolheu quando criou o rótulo (que afeta somente a associação à equipe) deve corresponder às configurações de compartilhamento de convidados do site do Microsoft Office SharePoint Online associado, da seguinte maneira:

|Configuração do rótulo|Configuração do site do Microsoft Office SharePoint Online|
|:------------|:----------------------|
|**Permitir que proprietários de grupos do Office 365 adicionem pessoas de fora da organização aos grupos** selecionado|**Convidados novos e existentes** (padrão para novas equipes)|
|**Permitir que os proprietários de grupos do Office 365 adicionem pessoas de fora da organização aos grupos** não selecionado|**Somente pessoas da sua organização**|

Também atualizaremos o tipo de link de compartilhamento padrão para reduzir o risco de compartilhamento acidental de arquivos e pastas para um público maior que o pretendido.

Para atualizar as configurações do site
1. Abra o [Centro de Administração do SharePoint Online](https://admin.microsoft.com/sharepoint).
2. Em **Sites**, clique em **Sites ativos**.
3. Clique no site associado à equipe.
4. Na guia **Políticas**, em **Compartilhamento externo**, clique em **Editar**.
5. Se você permitiu o compartilhamento de convidados ao criar o rótulo confidencial, certifique-se de que **Convidados novos e existentes** esteja selecionados. Se você não permitiu o compartilhamento quando criou o rótulo, escolha **Somente pessoas da sua organização**.
6. Em Tipo de link de compartilhamento padrão, limpe a caixa de seleção **O mesmo que a configuração de nível de organização** e selecione **Pessoas com acesso existente**.
7. Clique em **Salvar**.

#### <a name="private-channels"></a>Canais privados

Se você adicionar canais privados à equipe, cada canal privado criará um novo site do Microsoft Office SharePoint Online com as configurações de compartilhamento padrão. Como esses sites não estão visíveis no Centro de Administração do SharePoint Online, você deve usar o cmdlet [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) do Windows PowerShell com os seguintes parâmetros para atualizar as configurações de compartilhamento de convidados:

- `-SharingCapability Disabled` para desativar o compartilhamento de convidados (ativado por padrão)
- `-DefaultSharingLinkType Internal` para alterar o link de compartilhamento padrão para *Pessoas específicas*

Caso não pretenda usar canais privados com a sua equipe, é recomendável desativar a capacidade dos membros da equipe de criá-los em **Permissões de membro** em [Configurações da equipe](https://support.microsoft.com/office/ce053b04-1b8e-4796-baa8-90dc427b3acc).

### <a name="site-sharing-settings"></a>Configurações de compartilhamento de site

Para ajudar a garantir que o site do Microsoft Office SharePoint Online não seja compartilhado com pessoas que não são membros da equipe, limitamos esse compartilhamento aos proprietários. Também limitamos o compartilhamento de arquivos e pastas aos proprietários da equipe. Isso ajuda a garantir que os proprietários estejam cientes sempre que um arquivo for compartilhado com alguém de fora da equipe.

Para configurar o compartilhamento de site somente para proprietários
1. No Teams, navegue até a guia **Geral** da equipe que deseja atualizar.
2. Na barra de ferramentas da equipe, clique em **Arquivos**.
3. Clique nas reticências e em **Abrir no SharePoint**.
4. Na barra de ferramentas do site do SharePoint subjacente, clique no ícone de configurações e, em seguida, clique em **Permissões do site**.
5. No painel Permissões do site, em **Configurações de Compartilhamento**, clique em **Alterar configurações de compartilhamento**.
6. Em **Permissões de compartilhamento**, selecione **Somente proprietários do site podem compartilhar arquivos, pastas e o site** e clique em **Salvar**.

### <a name="custom-site-permissions"></a>Permissões de site personalizadas

Se você adicionou pessoas com permissões de Visualizador ao rótulo de confidencialidade, poderá adicioná-las ao site do Microsoft Office SharePoint Online com acesso de Leitura, para que possam acessar os arquivos facilmente.

Para adicionar usuários ao site
1. No site, clique no ícone de configurações e, em seguida, clique em **Permissões do site**.
2. Clique em **Convidar pessoas** e, em seguida, clique em **Compartilhar apenas site**.
3. Digite os nomes dos usuários e grupos que você deseja convidar.
4. Para cada pessoa ou grupo que você adicionar, altere as permissões de **Edição** para **Leitura**.
5. Escolha se deseja enviar um email para elas com um link para o site.
6. Clique em **Adicionar**.

## <a name="additional-protections"></a>Proteções adicionais

O Microsoft 365 oferece métodos adicionais para proteger seu conteúdo. Considere se as seguintes opções ajudariam a melhorar a segurança da sua organização.

- Fazer com que seus usuários convidados concordem com os [termos de uso](/azure/active-directory/conditional-access/terms-of-use).
- Configurar uma [política de tempo limite de sessão](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) para convidados.
- Criar [tipos de informações confidenciais](../compliance/sensitive-information-type-learn-about.md) e usar a [proteção contra perda de dados](../compliance/dlp-learn-about-dlp.md) para definir políticas de acesso a informações confidenciais.
- Usar as revisões de acesso do [Azure Active Directory](/azure/active-directory/governance/access-reviews-overview) para revisar periodicamente o acesso à equipe e a associação.

## <a name="drive-user-adoption-for-team-members"></a>Impulsionar a adoção do usuário para membros da equipe

Com a equipe instalada, é hora de impulsionar a adoção dessa equipe e sua segurança adicional aos membros da equipe.

### <a name="train-your-users"></a>Treinar seus usuários

Os membros da equipe podem acessar a equipe e todos os seus recursos, incluindo chats, reuniões e outros aplicativos. Ao trabalhar com arquivos da seção **Arquivos** de um canal, os membros da equipe devem atribuir o rótulo de confidencialidade aos arquivos criados por eles.

Quando o rótulo é aplicado ao arquivo, ele é criptografado. Os membros da equipe podem abri-lo e colaborar em tempo real. Se o arquivo sair do site e for encaminhado a um usuário mal-intencionado, ele precisará fornecer credenciais de uma conta de usuário que seja membro da equipe para abrir o arquivo e exibir seu conteúdo. 

Treine os membros da sua equipe:

- Sobre a importância de usar a nova equipe para chats, reuniões, arquivos e outros recursos do site do Microsoft Office SharePoint Online, e as consequências de um vazamento de dados altamente regulamentado, como ramificações legais, multas regulatórias, ransomware ou perda de vantagem competitiva.
- Como acessar a equipe.
- Como criar novos arquivos no site e carregar novos arquivos armazenados localmente.
- Como rotular arquivos com o rótulo de confidencialidade correto para a equipe.
- Como o rótulo protege os arquivos, mesmo quando vazam do site.

Este treinamento deve incluir exercícios práticos para que os membros da sua equipe possam experimentar esses recursos e seus resultados.

### <a name="conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a>Realize revisões periódicas de uso e envie comentários aos membros da equipe

Nas semanas após o treinamento:

- Aborde rapidamente os comentários dos membros da equipe e ajuste as políticas e configurações.
- Analise o uso da equipe e compare-o com as expectativas de uso.
- Certifique-se de que os arquivos altamente regulamentados tenham sido devidamente rotulados com o rótulo de confidencialidade. (Você pode ver quais arquivos têm um rótulo atribuído, exibindo uma pasta no Microsoft Office SharePoint Online e adicionando a coluna **Confidencialidade** pela opção **Mostrar/ocultar colunas** em **Adicionar coluna**.

Repita o treinamento dos usuários conforme necessário.

## <a name="see-also"></a>Confira também

[Azure AD Privileged Identity Management](/azure/active-directory/privileged-identity-management/pim-configure)