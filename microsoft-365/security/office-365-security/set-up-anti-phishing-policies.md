---
title: Configurar as políticas anti-phishing do Office 365 ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 08/29/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
description: Proteção contra phishing, com proteção abrangente como parte do Office 365 proteção avançada contra ameaças e proteção básica no Office 365 proteção do Exchange Online, pode ajudar a proteger sua organização contra ataques de phishing baseados em representação mal-intencionada. e outros ataques de phishing.
ms.openlocfilehash: 2f57a81451c1bf77399e741752ec2d8ea0577dfe
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598348"
---
# <a name="set-up-office-365-atp-anti-phishing-and-anti-phishing-policies"></a> Configurar políticas antiphishing e antiphishing da ATP do Office 365

A [proteção antiphishing da ATP](atp-anti-phishing.md), parte da [proteção avançada contra ameaças do Office 365](office-365-atp.md), pode ajudar a proteger sua organização contra ataques de phishing baseados em representação mal-intencionada e outros ataques de phishing. Se você for um administrador de segurança ou global do Office 365 Enterprise, poderá configurar as políticas de anti-phishing do ATP.

Os ataques de phishing vêm em uma variedade de formulários de ataques baseados em mercadoria ao spear phishing ou Whaling. Com a complexidade crescente, é difícil até mesmo um olho treinado para identificar alguns desses ataques sofisticados. Felizmente, a proteção avançada contra ameaças do Office 365 pode ajudar. Você pode configurar uma política anti-phishing do ATP para ajudar a garantir que sua organização esteja protegida contra esses ataques.

> [!NOTE]
> A ATP anti-phishing só está disponível na proteção avançada contra ameaças (ATP). A ATP é incluída em assinaturas, como [microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise e5, Office 365 Education a5, etc. Se sua organização tiver uma assinatura do Office 365 que não inclua o Office 365 ATP, você poderá comprar ATP como um complemento. Confira mais informações em [planos e preços avançados de proteção contra ameaças do office 365](https://products.office.com/exchange/advance-threat-protection) e a [Descrição do serviço de proteção avançada contra ameaças do Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Certifique-se de que sua organização esteja usando a versão mais recente do Office 365 ProPlus no Windows para aproveitar totalmente a proteção antiphishing da ATP.

Uma política anti-phishing também está disponível para o Office 365 proteção do Exchange Online, com um conjunto limitado de proteção contra falsificação destinado a proteger contra ataques baseados em autenticação e de base.

O que fazer:

1. Examine os pré-requisitos.

2. Saiba mais sobre as opções de política anti-phishing e de anti-phishing da ATP.

3. Configurar uma política de anti-phishing ou uma política anti-phishing do ATP.

> [!IMPORTANT]
> Para saber como várias tecnologias são aplicadas, consulte [que política se aplica quando vários métodos de proteção e verificações de detecção são executados em seu email](how-policies-and-protections-are-combined.md).

## <a name="review-the-prerequisites"></a>Revisar os pré-requisitos

- Para definir (ou editar) políticas ATP, você deve ter uma função apropriada atribuída. Alguns exemplos são descritos na tabela a seguir:

  |Role|Onde/como a atribuição|
  |---------|---------|
  |Administrador Global do Office 365|Por padrão, a pessoa que se inscreve para comprar o Office 365 é um administrador global. (Confira [sobre as funções de administrador do Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) para saber mais.)|
  |Administrador de Segurança|Centro de administração do Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory ()|
  |Gerenciamento de Organização do Exchange Online|Centro de administração do[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange () <br>ou <br>  Cmdlets do PowerShell (consulte [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))|

  Para saber mais sobre funções e permissões, confira [permissões no centro de conformidade &amp; de segurança do Office 365](permissions-in-the-security-and-compliance-center.md).

- Provavelmente, você configurará várias políticas anti-phishing para sua organização. O Office 365 impõe essas políticas na ordem em que estão listadas na **página** anti-phishing e nas páginas **anti-phishing do ATP** no centro de conformidade de segurança &amp; . Após revisar suas [Opções de política](#learn-about-atp-anti-phishing-policy-options), Reserve algum tempo para determinar quantas políticas você precisará e a prioridade de cada uma.

- Planeje gastar cerca de 5-15 minutos para configurar sua primeira política anti-phishing.

- Aguarde até 30 minutos para que a política nova ou atualizada se espalhe para todos os datacenters do Office 365.

## <a name="set-up-an-anti-phishing-or-atp-anti-phishing-policy"></a>Configurar uma política anti-phishing de anti-phishing ou de anti-phishing

Cada organização no Office 365 tem uma política anti-phishing padrão que se aplica a todos os usuários. Você pode criar várias políticas anti-phishing personalizadas que podem ser delimitadas a usuários, grupos ou domínios específicos em sua organização. As políticas personalizadas criadas prevalecem sobre a política padrão. Você adiciona, edita e exclui políticas anti-phishing no centro de conformidade de segurança &amp; do Office 365.

1. Acesse [https://protection.office.com](https://protection.office.com) e entre com sua conta corporativa ou de estudante.

2. No centro de conformidade com &amp; segurança do Office 365, no painel de navegação esquerdo, em **Gerenciamento de ameaças**, escolha **política**.

3. Na página **política** , escolha anti- **phishing** ou **antivírus ATP**.

4. Na página **anti-phishing ou anti** **-phishing da ATP** , siga um destes procedimentos:

   - Para adicionar uma nova política, selecione **+ criar**.

   - Para editar uma política existente, selecione o nome da política na lista exibida na página **anti-phishing** . (Como alternativa, você pode ou escolher **política padrão** acima da lista.) Na página exibida, escolha **Editar política**.

5. Especifique o nome, a descrição e as configurações da política. Consulte [saiba mais sobre as opções de política de anti-phishing do ATP](#learn-about-atp-anti-phishing-policy-options) para obter mais detalhes.

6. Depois de revisar as configurações, escolha **criar esta política** (ou **salvar**).

## <a name="learn-about-atp-anti-phishing-policy-options"></a>Saiba mais sobre as opções de política anti-phishing do ATP

À medida que você configura ou edita as políticas de anti-phishing da ATP, é possível escolher entre várias opções que oferecem a proteção mais sofisticada e abrangente, conforme descrito na tabela a seguir:

|**Essa configuração**|**Faça isto**|**Use quando quiser:**|
|:-----|:-----|:-----|
|**Adicionar usuários para proteger**|Define quais endereços de email serão protegidos pela política. Você pode adicionar até 60 endereços internos e externos que você deseja proteger da representação.|Quando você quiser garantir que o email de fora da organização não seja uma representação de um dos usuários na lista de usuários que você está protegendo. Exemplos de usuários que você pode querer proteger são executivos de alto nível, proprietários de negócios, membros da placa externa e assim por diante.  <br/> Essa lista de usuários protegidos é diferente da lista de pessoas à qual a política se aplica ou, em vez disso, para a qual a política é imposta. Você define a lista aplica-se a na seção **aplicado a** das opções de política.  <br/> Por exemplo, se você adicionar `Mary Smith <marys@contoso.com>` como um usuário para proteger e, em seguida, aplicar a política ao grupo "todos os usuários". Isso garantiria que um email que parecia representar "Mary Smith" seja enviado para um usuário no grupo "todos os usuários" seria acionado pela política.|
|**Adicionar domínios para proteger**|Permite que você escolha quais domínios você deseja proteger da representação. Você pode especificar que a política inclui todos os seus domínios personalizados, uma lista de domínios separada por vírgulas ou uma combinação dos dois. Se você escolher **incluir automaticamente domínios que possuo**e, posteriormente, adicionar um domínio à sua organização do Office 365, esta política anti-phishing estará no local para o novo domínio.|Sempre que você quiser garantir que o email de fora da organização não seja uma representação de um dos domínios definidos em sua lista de domínios verificados ou de um domínio de parceiro.|
|**Escolher ações**|Escolha a ação a ser tomada quando o Office 365 detectar uma tentativa de representação em relação aos usuários e domínios adicionados à política. Você pode escolher diferentes ações para usuários e domínios na mesma política anti-phishing. Essas ações aplicam-se a qualquer email de entrada que tenha sido identificado pelo Office 365 como a representação de uma conta de usuário ou domínio que esteja sob a proteção dessa política anti-phishing.  <br/> **Mensagem de quarentena** O email será enviado para a quarentena do Office 365. Quando você escolhe essa opção, o email não é enviado ao destinatário original.  <br/> **Redirecionar mensagem para outro endereço de email** O email será enviado para o endereço de email que você especificar. Você pode especificar vários endereços de email. Quando você escolhe essa opção, o email não é enviado ao destinatário original.  <br/> **Mover mensagem para a pasta de lixo eletrônico dos destinatários** O email será enviado para a pasta lixo eletrônico dos destinatários. Quando você escolhe essa opção, o email ainda é enviado ao destinatário original, mas não é colocado na caixa de entrada do destinatário.  <br/> **Entregar a mensagem e adicionar outros endereços à linha Cco** O email será entregue ao destinatário original. Além disso, os usuários que você identificar serão adicionados à linha Cco da mensagem antes de serem entregues. Quando você escolhe essa opção, o email ainda é enviado para a caixa de entrada do destinatário original.  <br/> **Não aplicar nenhuma ação** O email será entregue na caixa de entrada do destinatário original. Nenhuma outra ação será executada na mensagem de email.  <br/> **Ativar dicas de proteção contra phishing** Habilita dicas de segurança anti-phishing no email.|Quando você quiser realizar uma ação em mensagens que o Office 365 determinou ser uma representação de um usuário ou domínio, conforme definido na política.|
|**Habilitar inteligência de caixa de correio**|Habilita ou desabilita a inteligência de caixa de correio para esta política. Você só pode habilitar a inteligência de caixa de correio para contas baseadas em nuvem, ou seja, contas cuja caixa de correio está hospedada inteiramente no Office 365.| Este recurso usa o Machine Learning para determinar os padrões de email de um usuário com seus contatos. Com essas informações, o AI pode diferenciar melhor os emails autênticos e de phishing.|
|**Habilitar proteção de representação baseada em inteligência de caixa de correio**|Habilita ou desabilita a inteligência de caixa de correio para proteção de representação para essa política. O importante aqui é o controle da representação de uma determinada caixa de correio.|Quando você quiser aprimorar os resultados de representação de usuários com base no mapa de remetentes individuais de cada usuário. Essa inteligência permite que o Office 365 Personalize a detecção de representação do usuário e trate melhor os falsos positivos. Quando a representação do usuário é detectada, com base na inteligência de caixa de correio, você pode definir a ação a ser tomada na mensagem.|
|**Adicionar domínios e remetentes confiáveis**|Define endereços de email e domínios que não serão considerados representação por essa política. As mensagens dos endereços e domínios de email do remetente que você adiciona como remetentes confiáveis e domínios nunca serão classificadas como um ataque baseado em representação. Como resultado, as ações e configurações nesta política não serão aplicadas a mensagens desses remetentes e domínios.  <br/><br/>O limite máximo para essas listas é de aproximadamente 1000 entradas.|Quando os usuários interagem com domínios ou usuários que disparam a representação, mas são considerados seguros. Por exemplo, se um parceiro tiver o mesmo nome de exibição ou nome de domínio semelhante ao definido como um usuário na lista.|
|**Aplicado a**|Define os destinatários cujas mensagens de email de entrada serão sujeitas às regras da política. Você pode criar condições e exceções para os destinatários associados à política.  <br/> Por exemplo, você pode criar uma política global para sua organização aplicando a regra a todos os destinatários em seu domínio.  <br/> Você também pode criar regras de exceção, como uma regra que não verifica mensagens de email para um grupo específico de destinatários.|Cada política deve ser associada a um conjunto de usuários, por exemplo, usuários em um grupo ou domínio específico.|
|**Limites avançados de phishing**|Define o nível de configurações para como as mensagens de phishing são tratadas.  <br/> **Padrão** Um email suspeito de ser phishing é tratado da forma padrão.  <br/> **Agressivo** É suspeito que o sistema fique em caso de phishing com um alto grau de confiança e que seja tratado pelo sistema da mesma maneira.  <br/> **Mais agressivo** É suspeito que o sistema seja de phishing com uma média, alta ou muito alto grau de confiança é manipulado pelo sistema da mesma maneira.  <br/> **Mais agressivo** É suspeito que o sistema seja de phishing com baixa, média, alta ou muito alto grau de confiança é tratado pelo sistema da mesma maneira.|Quando você deseja ser mais agressivo no tratamento de mensagens potencialmente de phishing no Office 365. Por exemplo, as mensagens com uma grande probabilidade de ser phishing terão as ações mais agressivas tomadas neles enquanto as mensagens com baixa probabilidade têm ações menos agressivas tomadas. Essa configuração também afeta outras partes do sistema de filtragem que combinam sinais juntos. Isso não significa necessariamente que ações diferentes são implementadas.  Essencialmente, você define a probabilidade de o email ser Phish, para determinar a (mesma) ação designada. A possibilidade de mover mensagens boas aumenta conforme o nível das configurações aumenta.|

## <a name="learn-about-anti-phishing-policy-options"></a>Saiba mais sobre as opções de política anti-phishing

Ao configurar ou editar seu anti-phishing, você pode escolher entre várias opções, conforme descrito na tabela a seguir:

|**Essa configuração**|**Faça isto**|**Use quando quiser:**|
|:-----|:-----|:-----|
|**Aplicado a**|Define os destinatários cujas mensagens de email de entrada serão sujeitas às regras da política. Você pode criar condições e exceções para os destinatários associados à política.  <br/> Por exemplo, você pode criar uma política global para sua organização aplicando a regra a todos os destinatários em seu domínio.  <br/> Você também pode criar regras de exceção, como uma regra que não verifica mensagens de email para um grupo específico de destinatários.|Cada política deve ser associada a um conjunto de usuários, por exemplo, usuários em um grupo ou domínio específico.|
|**Escolher ações**|Escolha a ação a ser tomada quando o Office 365 detectar uma tentativa de falsificação de organização externa ou interna contra seus usuários. Essas ações se aplicam a qualquer email de entrada que tenha sido identificado pelo Office 365 como uma tentativa de falsificação para usuários que estão sob a proteção desta política anti-phishing.  <br/> **Mensagem de quarentena** O email será enviado para a quarentena do Office 365. Quando você escolhe essa opção, o email não é enviado ao destinatário original.  <br/> **Mover mensagem para a pasta de lixo eletrônico dos destinatários** O email será enviado para a pasta lixo eletrônico dos destinatários. Quando você escolhe essa opção, o email ainda é enviado ao destinatário original, mas não é colocado na caixa de entrada do destinatário.  <br/> **Não aplicar nenhuma ação** O email será entregue na caixa de entrada do destinatário original. Nenhuma outra ação será executada na mensagem de email.|Quando você quiser realizar uma ação em mensagens que o Office 365 determinou ser uma tentativa de falsificação de domínios internos ou externos, conforme definido na política.|

Depois que a sua organização configurou políticas anti-phishing ou políticas de anti-phishing da ATP, você pode ver como o serviço está funcionando [exibindo relatórios para proteção avançada contra ameaças](view-reports-for-atp.md).

## <a name="example-anti-phishing-policy-to-protect-a-user-and-a-domain"></a>Exemplo: política anti-phishing para proteger um usuário e um domínio

Este exemplo configura uma política chamada "Domain and CEO" que fornece proteção de usuário e de domínio da representação e aplica a política a todos os emails recebidos por usuários no domínio `contoso.com`. O administrador de segurança determinou que a política deve atender a esses requisitos de negócios:

- A política precisa fornecer proteção para a conta de email do CEO e o domínio inteiro.

- As mensagens que são consideradas como tentativas de representação em relação à conta de usuário do CEO precisam ser redirecionadas para o endereço de email do administrador de segurança.

- As mensagens determinadas em tentativas de representação no domínio são menos urgentes e devem ser colocadas em quarentena para análise posterior.

O administrador de segurança na Contoso pode usar valores como o seguinte para criar uma política anti-phishing que atenda a essas necessidades.

|||
|:-----|:-----|
|**Configuração ou opção**|**Exemplo**|
|Nome|Domínio e CEO|
|Descrição|Certifique-se de que o CEO e nosso domínio não estão sendo representados.|
|Adicionar usuários para proteger|O endereço de email do CEO no mínimo.|
|Adicionar domínios para proteger|O domínio organizacional que inclui o escritório do CEO.|
|Escolher ações|Se o email for enviado por um usuário representado: escolha **redirecionar mensagem para outro endereço de email** e, em seguida, digite o endereço de email do `securityadmin@contoso.com`administrador de segurança, por exemplo,.  <br/> Se o email for enviado por um domínio representado: escolher **mensagem de quarentena**.|
|Inteligência de caixa de correio|Por padrão, a inteligência de caixa de correio é selecionada quando você cria uma nova política anti-phishing. Deixe esta configuração **em** para obter os melhores resultados.|
|Adicionar domínios e remetentes confiáveis|Para este exemplo, não defina substituições.|
|Aplicado a|Selecione **o domínio do destinatário**. Em **qualquer um dos seguintes**, selecione **escolher**. Selecione **+ Adicionar**. Marque a caixa de seleção ao lado do nome do domínio, por exemplo `contoso.com`, na lista e selecione **Adicionar**. Selecione **Concluído**.|

## <a name="delete-an-anti-phishing-or-atp-anti-phishing-policy"></a>Excluir uma política anti-phishing de anti-phishing ou ATP

Você pode excluir políticas personalizadas criadas usando o centro de conformidade de &amp; segurança. Não é possível excluir a política padrão para sua organização. Recomendamos usar o centro &amp; de conformidade de segurança para rever ou editar qualquer uma das suas políticas de ATP.

1. Acesse [https://protection.office.com](https://protection.office.com) e entre com sua conta corporativa ou de estudante.

2. Na navegação à esquerda, em **Gerenciamento de ameaças**, escolha **política**.

3. Na página **política** , escolha anti- **phishing** ou **antivírus ATP**.

4. Na página **anti-phishing ou anti** **-phishing da ATP** , selecione o nome da política na lista.

5. Na página exibida, escolha **excluir política**. Aguarde até 30 minutos para que as alterações se espalhem para todos os datacenters do Office 365.

## <a name="next-steps"></a>Próximas etapas

Quando suas políticas anti-phishing estiverem em vigor, você poderá ver como os recursos de proteção contra ameaças estão funcionando para sua organização, exibindo relatórios. Confira os seguintes recursos para saber mais:

- [Exibir relatórios do Office 365 ATP](view-reports-for-atp.md) ou [exibir relatórios de segurança de email](view-email-security-reports.md)

- [Usar o explorador de ameaças (ou detecções em tempo real)](threat-explorer.md)

Fique à frente dos novos recursos que chegam à ATP. Visite o [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) e saiba mais sobre os [novos recursos que estão sendo adicionados à ATP](office-365-atp.md#new-features-in-office-365-atp).
