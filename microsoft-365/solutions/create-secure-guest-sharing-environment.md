---
title: Criar um ambiente de compartilhamento de convidados seguro
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-security-compliance
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
recommendations: false
description: Saiba mais sobre as opções disponíveis para criar um ambiente seguro de compartilhamento para convidados no Microsoft 365, fornecendo acesso de convidado para uma colaboração aperfeiçoada.
ms.openlocfilehash: f59c10f58f1ab89234ff3dda4bf69b6b8d718f76
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539222"
---
# <a name="create-a-secure-guest-sharing-environment"></a>Criar um ambiente de compartilhamento de convidados seguro

Neste artigo, abordaremos várias opções para criar um ambiente de compartilhamento de convidados seguro no Microsoft 365. Estes são exemplos para dar uma ideia das opções disponíveis. Você pode usar esses procedimentos em diferentes combinações para atender às necessidades de segurança e conformidade da sua organização.

Este artigo inclui:

- Configurar a autenticação multifator para os convidados.
- Configurar os termos de uso para os convidados.
- Configurar revisões trimestrais de acesso dos convidados para verificar periodicamente se eles continuam precisando de permissões para equipes e sites.
- Restringir convidados a acesso somente Web para dispositivos não gerenciados.
- Configurar uma política de tempo limite de sessão para garantir que os convidados autentiquem diariamente.
- Criação de um tipo de informação confidencial para um projeto altamente confidencial.
- Atribuição automática de um rótulo de confidencialidade a documentos que contêm um tipo de informação confidencial.
- Removendo automaticamente o acesso de convidados de arquivos com um rótulo de confidencialidade.

Algumas das opções discutidas neste artigo exigem que os convidados tenham uma conta do Azure Active Directory. Para garantir que os convidados sejam incluídos no diretório ao compartilhar arquivos e pastas com eles, use a [integração do SharePoint e do OneDrive com a Visualização B2B do Azure AD](/sharepoint/sharepoint-azureb2b-integration-preview).

Observe que não vamos discutir a habilitação das configurações de compartilhamento de convidados neste artigo. Confira [Colaborar com pessoas de fora da sua organização](collaborate-with-people-outside-your-organization.md) para obter detalhes sobre como habilitar o compartilhamento de convidados para diferentes cenários.

## <a name="set-up-multi-factor-authentication-for-guests"></a>Configurar a autenticação multifator para convidados

A autenticação multifator reduz significativamente as chances de uma conta ser comprometida. Como os convidados podem usar contas de email pessoais que não aderem a nenhuma política de governança ou práticas recomendadas, é especialmente importante exigir autenticação multifator para convidados. Se o nome de usuário e a senha de um convidado forem roubados, exigir um segundo fator de autenticação reduz muito as chances de partes desconhecidas obterem acesso aos seus sites e arquivos.

Neste exemplo, configuraremos a autenticação multifator para convidados usando uma política de acesso condicional do Azure Active Directory.

Configurar a autenticação multifator para convidados

1. Vá para [Políticas de acesso condicional do Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).
2. No **Acesso Condicional | Na folha Políticas**, clique em **Nova política**.
3. No campo **Nome**, digite um nome.
4. Em **Atribuições**, clique em **Usuários e grupos**.
5. Na lâmina **Usuários e grupos**, selecione **Selecionar usuários e grupos**, marque a caixa de seleção **Todos os convidados e usuários externos**.
6. Em **Atribuições**, clique em **Aplicativos de nuvem ou ações**.
7. Na lâmina **Aplicativos de nuvem ou ações**, selecione **Todos os aplicativos de nuvem** na guia **Incluir**.
8. Em **Controles de acesso**, clique em **Conceder**.
9. Na folha **Conceder**, marque a caixa de seleção **Exigir autenticação multifator**, e, em seguida, clique em **Selecionar**.
10. Na folha **Novo**, em **Habilitar política**, clique em **Ativar** e, em seguida, clique em **Criar**.

Agora, o convidado será solicitado a se inscrever na autenticação multifator para que possam acessar conteúdo, sites ou equipes compartilhados.

### <a name="more-information"></a>Mais informações

[Planejando uma Implantação de Autenticação Multifator do Microsoft Azure Active Directory](/azure/active-directory/authentication/howto-mfa-getstarted)

## <a name="set-up-a-terms-of-use-for-guests"></a>Definir os termos de uso para os convidados

Em algumas situações, os convidados podem não ter assinado acordos de não divulgação ou outros acordos legais com sua organização. Você pode exigir que os convidados concordem com os termos de uso antes de acessar os arquivos que são compartilhados com eles. Os termos de uso podem ser exibidos na primeira vez que tentam acessar um site ou arquivo compartilhado.

Para criar os termos de uso, primeiro é necessário criar um documento no Word ou em outro programa de criação e, em seguida, salvá-lo como um arquivo .pdf. Em seguida, esse arquivo pode ser carregado para o Azure AD.

Para criar os termos de uso do Azure AD

1. Entre no Azure como Administrador Global, Administrador de Segurança ou Administrador de Acesso Condicional.
2. Navegue até [Termos de uso](https://aka.ms/catou).
3. Clique em **Novos termos**.

   ![Captura de tela das configurações dos novos termos de uso do Azure Active Directory](../media/azure-ad-guest-terms-of-use.png)

4. Digite um **Nome** e um **Nome de exibição**.
6. Em **Documento Termos de uso**, navegue até o arquivo PDF que você criou e selecione-o.
7. Selecione o idioma para o documento de termos de uso.
8. Definir **Exigir que os usuários expandam os Termos de uso**, como **Ativado**.
9. Em **Acesso Condicional**, na lista **Impor com o modelo de política de Acesso Condicional**, escolha **Criar política de acesso condicional mais tarde**.
10. Clique em **Criar**.

Depois de criar os termos de uso, a próxima etapa é criar uma política de acesso condicional que exibe os termos de uso aos convidados.

Para criar uma política de acesso condicional:

1. Vá para [Políticas de acesso condicional do Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).
2. No **Acesso Condicional | Na folha Políticas**, clique em **Nova política**.
3. Na caixa **Nome**, digite um nome.
4. Em **Atribuições**, clique em **Usuários e grupos**.
5. Na lâmina **Usuários e grupos**, selecione **Selecionar usuários e grupos**, marque a caixa de seleção **Todos os convidados e usuários externos**.
6. Em **tarefas**, clique em **Aplicativos de nuvem ou ações**.
7. Na guia **Incluir**, selecione **Selecionar aplicativos** e, em seguida, clique em **Selecionar**.
8. Na folha **Selecionar**, selecione **Microsoft Teams**, **Office 365 SharePoint Online** e **Outlook Groups** e, em seguida, clique em **Selecionar**.
9. Em **Controles de acesso**, clique em **Conceder**.
10. Na folha **Conceder**, selecione **Temos de uso de convidado** e, em seguida, clique em **Selecionar**.
11. Na folha **Novo**, em **Habilitar política**, clique em **Ativar** e, em seguida, clique em **Criar**.

Agora, na primeira vez que um convidado tentar acessar um conteúdo ou uma equipe ou site em sua organização, ele deverá aceitar os termos de uso.

> [!NOTE]
> Usar o acesso condicional exige uma licença do Azure AD Premium P1. Para mais informações, confira [O que é acesso condicional](/azure/active-directory/conditional-access/overview).

### <a name="more-information"></a>Mais informações

[Termos de uso do Azure Active Directory](/azure/active-directory/conditional-access/terms-of-use)

## <a name="set-up-guest-access-reviews"></a>Acesso de convidado com revisões de acesso

Com as revisões de acesso no Azure AD, você pode automatizar uma revisão periódica do acesso do usuário a várias equipes e grupos. Ao exigir uma análise de acesso para convidados especificamente, você pode ajudar a garantir que os convidados não retenham o acesso às informações confidenciais da sua organização por mais tempo do que o necessário.

Para configurar uma revisão de acesso de convidado

1. Na página [Governança de Identidade](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade), no menu à esquerda, clique em **Revisões de acesso**.
2. Clique em **Novas revisões de acesso**.
3. Escolha a opção **Teams + Grupos**.
4. Escolha a opção **Todos os grupos do Microsoft 365** com usuários convidados. Clique em **Selecionar grupo(s) a excluir** se quiser excluir algum grupo.
5. Escolha a opção **Somente usuários convidados** e clique em **Avançar: Comentários**.
6. Em **Selecionar revisores**, escolha **Proprietário(s) do grupo**.
7. Clique em **Selecionar revisores substitutos**, escolha quem deve ser os revisores substitutos e clique em **Selecionar**.
8. Em **Especificar recorrência de revisão**, escolha **Trimestralmente**.
9. Selecione uma data de início e duração.
10. Para **Fim**, escolha **Nunca** e clique em **Avançar: Configurações**.

    ![Captura de tela da guia de revisão de acesso do Azure Active Directory](../media/azure-ad-create-access-review.png)

11. Na guia **Configurações**, revise as configurações para conformidade com suas regras de negócios.

    ![Captura de tela da guia de configurações de revisão de acesso do Azure Active Directory](../media/azure-ad-create-access-review-settings.png)

12. Clique em **Avançar: Analisar + Criar**.
13. Digite um **Nome de análise** e análise as configurações.
14. Clique em **Criar**.

É importante observar que os convidados podem ter acesso a equipes ou grupos, ou a arquivos e pastas individuais. Quando o acesso a arquivos e pastas é fornecido, os convidados não podem ser adicionados a qualquer grupo específico. Se desejar fazer revisões de acesso em convidados que não pertencem a uma equipe ou grupo, você pode criar um grupo dinâmico no Azure Active Directory para conter todos os convidados e, em seguida, criar uma análise de acesso para esse grupo. Os proprietários do site também podem gerenciar a [expiração de convidado para o site](https://support.microsoft.com/office/25bee24f-42ad-4ee8-8402-4186eed74dea)

### <a name="more-information"></a>Mais informações

[Gerenciar o acesso de convidado com revisões de acesso do Azure AD](/azure/active-directory/governance/manage-guest-access-with-access-reviews)

[Criar uma revisão de acesso de grupos ou aplicativos nas revisões de acesso do Azure AD](/azure/active-directory/governance/create-access-review)

## <a name="set-up-web-only-access-for-guests"></a>Configurar o acesso apenas à Web para convidados

Você pode reduzir a superfície de ataque e facilitar a administração, exigindo que os convidados acessem suas equipes, sites e arquivos usando apenas um navegador da web.

Para grupos e equipes do Microsoft 365, isso é feito com uma política de acesso condicional do Azure Active Directory. Para o Microsoft Office SharePoint Online, isso é configurado no Centro de Administração do SharePoint Online. (Você também pode [usar rótulos de confidencialidade para restringir o acesso dos convidados apenas à web](../compliance/sensitivity-labels-teams-groups-sites.md).)

Para restringir os convidados ao acesso apenas pela web para Grupos e Teams:

1. Vá para [Políticas de acesso condicional do Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).
2. Na folha **Acesso Condicional – Políticas**, clique em **Nova Política**.
3. Na caixa **Nome**, digite um nome.
4. Em **Atribuições**, clique em **Usuários e grupos**.
5. Na lâmina **Usuários e grupos**, selecione **Selecionar usuários e grupos**, marque a caixa de seleção **Todos os convidados e usuários externos**.
6. Em **tarefas**, clique em **Aplicativos de nuvem ou ações**.
7. Na guia **Incluir**, selecione **Selecionar aplicativos** e, em seguida, clique em **Selecionar**.
8. Na folha **Selecionar**, selecione **Microsoft Teams** e **Outlook Groups** e clique em **Selecionar**.
9. Em **Tarefas**, clique em **Condições**.
10. Na folha **Condições**, clique em **Aplicativos cliente**.
11. Na folha **Aplicativos cliente**, clique em **Sim** para **Configurar** e selecione **Aplicativos móveis e clientes de desktop**, **Clientes Exchange ActiveSync** e configurações de **outros clientes**. Desmarque a caixa de seleção **Navegador**.

    ![Captura de tela das configurações de aplicativos cliente de acesso condicional do Azure Active Directory](../media/azure-ad-conditional-access-client-mobile.png)

12. Clique em **Concluído**.
13. Em **Controles de acesso**, clique em **Conceder**.
14. Na folha **Conceder**, selecione **Exigir que o dispositivo seja marcado como em conformidade** e **Exigir o Dispositivo adicionado ao Azure AD híbrido**.
15. Em **Para vários controles**, selecione **Exigir um dos controles selecionados** e, em seguida, clique em **Selecionar**.
16. Na folha **Novo**, em **Habilitar política**, clique em **Ativar** e, em seguida, clique em **Criar**.

Para restringir os convidados ao acesso online para o Microsoft Office SharePoint Online

1. No [Centro de Administração do SharePoint Online](https://admin.microsoft.com/sharepoint), expanda **Políticas** e clique em **Controle de acesso**.
2. Clique em **Dispositivos não gerenciados**.
3. Selecione a opção **Permitir acesso limitado apenas pela web** e clique em **Salvar**.

Observe que essa configuração no Centro de administração do SharePoint Online cria uma política de acesso condicional de suporte no Microsoft Azure Active Directory.

## <a name="configure-a-session-timeout-for-guests"></a>Configurar um tempo limite de sessão para convidados

Exigir que os convidados se autentiquem regularmente pode reduzir a possibilidade de usuários desconhecidos acessarem o conteúdo da sua organização se o dispositivo de um convidado não for mantido seguro. Você pode configurar uma política de acesso condicional de tempo limite de sessão para convidados no Azure Active Directory.

Para configurar uma política de tempo limite de sessão de convidado

1. Vá para [Políticas de acesso condicional do Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).
2. Na folha **Acesso condicional – Políticas**, clique em **Nova Política**.
3. Na caixa **Nome**, digite *Tempo limite de sessão de convidado*.
4. Em **Atribuições**, clique em **Usuários e grupos**.
5. Na lâmina **Usuários e grupos**, selecione **Selecionar usuários e grupos**, marque a caixa de seleção **Todos os convidados e usuários externos**.
6. Em **tarefas**, clique em **Aplicativos de nuvem ou ações**.
7. Na guia **Incluir**, selecione **Selecionar aplicativos** e, em seguida, clique em **Selecionar**.
8. Na folha **Selecionar**, selecione **Microsoft Teams**, **Office 365 SharePoint Online** e **Outlook Groups** e, em seguida, clique em **Selecionar**.
9. Em **Controles de acesso**, clique em **Sessão**.
10. Na folha **Sessão**, selecione **Frequência de entrada**.
11. Selecione **1** e **Dias** para o período de tempo e, em seguida, clique em **Selecionar**.
12. Na folha **Novo**, em **Habilitar política**, clique em **Ativar** e, em seguida, clique em **Criar**.

## <a name="create-a-sensitive-information-type-for-a-highly-sensitive-project"></a>Criar um tipo de informação confidencial para um projeto altamente confidencial.

Os tipos de informações confidenciais são cadeias de caracteres predefinidas que podem ser usadas em fluxos de trabalho de política para reforçar os requisitos de conformidade. O Centro de Conformidade da Microsoft 365 vem com mais de 100 tipos de informações confidenciais, incluindo números de carteira de motorista, números de cartão de crédito, números de contas bancárias, etc.

Você pode criar tipos de informações confidenciais personalizados para ajudar a gerenciar o conteúdo específico da sua organização. Neste exemplo, criaremos um tipo personalizado de informação confidencial para um projeto altamente confidencial. Podemos então usar esse tipo de informação confidencial para aplicar automaticamente um rótulo de confidencialidade.

Criar um tipo de informação confidencial

1. No [Centro de Conformidade do Microsoft 365r](https://compliance.microsoft.com), na navegação à esquerda, expanda **Classificação** e, em seguida, clique em **Tipos de informação de confidencialidade**.
2. Clique em **Criar**.
3. Para **Nome** e **Descrição**, digite **Projeto Saturno** e, em seguida, clique em **Avançar**.
4. Clique em **Adicionar um elemento**.
5. Em **Detectar conteúdo contendo lista**, selecione **Palavras-chave** e, em seguida, digite *Projeto Saturno* na caixa de palavra-chave.
6. Clique em **Avançar** e em **Concluir**.
7. Se você quiser testar o tipo de informação confidencial, clique em **Não**.

### <a name="more-information"></a>Mais informações

[Personalizar tipos de informação confidencial](/Office365/SecurityCompliance/custom-sensitive-info-types)

## <a name="create-an-auto-labeling-policy-to-assign-a-sensitivity-label-based-on-a-sensitive-information-type"></a>Criar uma política de rotulagem automática para atribuir um rótulo de confidencialidade com base em um tipo de informação confidencial

Se você estiver usando rótulos de confidencialidade em sua organização, você pode aplicar automaticamente um rótulo a arquivos que contêm tipos de informações confidenciais definidos. 

Para criar uma política de rotulagem automática

1. Abra o [Centro de administração de conformidade do Microsoft 365](https://compliance.microsoft.com).
2. No painel de navegação esquerdo, clique em **Proteção de informações**.
3. Na guia **Rotulagem automática**, clique em **Criar política de rotulagem automática**.
4. Na página **Escolha as informações às quais deseja que este rótulo seja aplicado**, escolha **Personalizado** e clique em **Avançar**.
5. Digite um nome e uma descrição para a política e clique em **Avançar**.
6. Na página **Escolha os locais onde deseja aplicar o rótulo**, ative os **sites do Microsoft Office SharePoint Online** e clique em **Escolher sites**.
7. Adicione os URLs dos sites onde deseja ativar a rotulagem automática e clique em **Concluído**.
8. Clique em **Avançar**.
9. Na página **Configurar regras comuns ou avançadas**, escolha **Regras comuns** e clique em **Avançar**.
10. Na página **Definir regras para conteúdo em todos os locais**, clique em **Nova regra**.
11. Na página **Nova regra**, dê um nome à regra, clique em **Adicionar condição** e, a seguir, clique em **Conteúdo contém tipos de informações confidenciais**.
12. Clique em **Adicionar**, clique em **Tipos de informações confidenciais**, escolha os tipos de informações confidenciais que deseja usar, clique em **Adicionar** e clique em **Salvar**.
13. Clique em **Avançar**.
14. Clique em **Escolher um rótulo**, selecione o rótulo que deseja usar e clique em **Adicionar**.
15. Clique em **Avançar**.
16. Deixe a política no modo de simulação e clique em **Avançar**.
17. Clique em **Criar política** e, a seguir, clique em **Concluído**.

Com a política em vigor, quando um usuário digita "Projeto Saturno" em um documento, a política de rotulagem automática aplicará automaticamente o rótulo especificado ao verificar o arquivo.

### <a name="more-information"></a>Mais informações

[Aplicar um rótulo de confidencialidade automaticamente ao conteúdo](../compliance/apply-sensitivity-label-automatically.md)

## <a name="create-a-dlp-policy-to-remove-guest-access-to-highly-sensitive-files"></a>Crie uma política DLP para remover o acesso de convidados a arquivos altamente confidenciais

Você pode usar a [prevenção contra perda de dados (DLP)](../compliance/dlp-learn-about-dlp.md) para evitar o compartilhamento indesejado de conteúdo confidencial por convidados. A prevenção contra perda de dados pode agir com base no rótulo de confidencialidade de um arquivo e remover o acesso de convidado.

Para criar uma regra DLP

1. No centro de administração de conformidade do Microsoft 365, vá até a [página de prevenção contra perda de dados](https://compliance.microsoft.com/datalossprevention).
2. Clique em **Criar política**.
3. Escolha **Personalizado** e clique em **Avançar**.
4. Digite um nome para a política e clique em **Avançar**.
5. Na página **Locais para aplicar a política**, desative todas as configurações, exceto **sites do Microsoft Office SharePoint Online** e **contas do OneDrive** e clique em **Avançar**.
6. Na página **Definir configurações de política**, clique em **Avançar**.
7. Na página **Personalizar regras DLP avançadas**, clique em **Criar regra** e digite um nome para a regra.
8. Em **Condições**, clique em **Adicionar condição** e escolha **Conteúdo contém**.
9. Clique em **Adicionar**, escolha **Rótulos de confidencialidade**, escolha os rótulos que deseja usar e clique em **Adicionar**.

   ![Captura de tela das opções de condições, tipos de informações confidenciais, rótulos de confidencialidade e rótulos de retenção.](../media/limit-accidental-exposure-dlp-conditions.png)

10. Em **Ações**, clique em **Adicionar uma ação** e escolha **Restringir o acesso ou criptografar o conteúdo em locais do Microsoft 365**.
11. Marque a caixa de seleção **Restringir o acesso ou criptografar o conteúdo em locais do Microsoft 365** e escolha a opção **Somente pessoas fora de sua organização**.

      ![Captura de tela das opções de ação da regra DLP](../media/dlp-remove-guest-access-sensitive-files.png)

12. Clique em **Salvar** e em **Avançar**.
13. Escolha suas opções de teste e clique em **Avançar**.
14. Clique em **Enviar** e, em seguida, clique em **Concluído**.

É importante observar que esta política não remove o acesso se o convidado for membro do site ou da equipe como um todo. Se você planeja ter documentos altamente confidenciais em um site ou uma equipe com membros convidados, considere o uso de [canais privados no Teams](https://support.microsoft.com/office/de3e20b0-7494-439c-b7e5-75899ebe6a0e)e apenas permita os membros de sua organização nos canais privados.

## <a name="additional-options"></a>Opções adicionais

Há algumas opções adicionais no Microsoft 365 e no Azure Active Directory que podem ajudar a proteger seu ambiente de compartilhamento de convidado.

- Você pode criar uma lista de domínios de compartilhamento permitidos ou negados para limitar com quem os usuários podem compartilhar. Confira [restringir o compartilhamento de conteúdo do SharePoint e do OneDrive por domínio](/sharepoint/restricted-domains-sharing) e [Permitir ou bloquear convites para usuários B2B de organizações específicas](/azure/active-directory/b2b/allow-deny-list) para obter mais informações.
- Você pode limitar os locatários do Azure Active Directory aos quais seus usuários podem se conectar. Confira [Usar restrições de locatário para gerenciar o acesso aos aplicativos de nuvem SaaS](/azure/active-directory/manage-apps/tenant-restrictions) para mais informações. 
- Você pode criar um ambiente gerenciado em que os parceiros podem ajudar a gerenciar contas de convidado. Confira [Criar uma extranet B2B com convidados gerenciados](/Office365/Enterprise/b2b-extranet) para obter mais informações.

## <a name="see-also"></a>Confira também

[Limitar a exposição acidental dos arquivos ao compartilhar com convidados](share-limit-accidental-exposure.md)

[Práticas recomendadas para compartilhar arquivos e pastas com usuários não autenticados](best-practices-anonymous-sharing.md)

[Crie uma extranet B2B com convidados gerenciados](b2b-extranet.md)