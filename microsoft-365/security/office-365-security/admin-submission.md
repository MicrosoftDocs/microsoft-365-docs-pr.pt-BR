---
title: Envios de administrador
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o portal de envios no centro de conformidade de & de segurança para enviar emails suspeitos, emails de phishing, spam e outras mensagens, URLs e arquivos potencialmente nocivos para a Microsoft para verificação.
ms.openlocfilehash: 18941c1400917291f8924331fd19827e476db914
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726854"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Usar o Envio do Administrador para enviar spam, phishing, URLs e arquivos à Microsoft

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online, os administradores podem usar o portal de envios no centro de conformidade de & de segurança para enviar mensagens de email, URLs e anexos para a Microsoft para verificação.

Ao enviar um email, você receberá informações sobre qualquer política que possa ter permitido o email de entrada em seu locatário, bem como o exame de qualquer URL e anexo no email. As políticas que podem ter permitido um email incluem a lista de remetentes confiáveis de um usuário individual, bem como políticas de nível de locatário, como regras de fluxo de emails do Exchange (também conhecidas como regras de transporte).

Para obter outras maneiras de enviar mensagens de email, URLs e anexos para a Microsoft, consulte [relatar mensagens e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a página de **envio** , use <https://protection.office.com/reportsubmission> .

- Você precisa receber permissões antes de executar os procedimentos deste tópico:

  - Para enviar mensagens e arquivos para a Microsoft, você precisa ser membro de um dos grupos de função a seguir:

    - **Gerenciamento da organização** ou **administrador de segurança** no centro de conformidade de & de [segurança](permissions-in-the-security-and-compliance-center.md).
    - Gerenciamento da **organização** ou **Gerenciamento de higiene** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Para acesso somente leitura ao portal de envios, você precisa ser membro de um dos grupos de função a seguir:

    - **Leitor de segurança** no [centro de conformidade & segurança](permissions-in-the-security-and-compliance-center.md).
    - **Gerenciamento de organização somente para exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Para obter mais informações sobre como os usuários podem enviar mensagens e arquivos para a Microsoft, consulte [relatar mensagens e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="report-suspicious-content-to-microsoft"></a>Relatar conteúdo suspeito para a Microsoft

1. No centro de conformidade & segurança, vá para análise de **Gerenciamento de ameaça** \> **Review** \> **mensagens de envio de administração**.

2. Na página **Submissions** envios que aparece, clique no botão **novo envio** .

3. Use um novo submenu de **envio** que parece enviar a mensagem, a URL ou o anexo, conforme descrito nas seções a seguir.

### <a name="submit-a-questionable-email-to-microsoft"></a>Enviar um email questionável à Microsoft

1. Na seção **tipo de objeto** , selecione **email**. Na seção **formato de envio** , use uma das seguintes opções:

   - **ID da mensagem de rede**: Este é um valor de GUID que está disponível no cabeçalho **X-MS-Exchange-Organization-Network-Message-ID** na mensagem.

   - **Arquivo**: clique em **escolher arquivo**. Na caixa de diálogo que é aberta, localize e selecione o arquivo. eml ou. msg e clique em **abrir**.

2. Na seção **destinatários** , especifique um ou mais destinatários em relação à qual você gostaria de executar uma verificação de política. A verificação de política determinará se o email ignorará a verificação por causa de políticas de usuário ou organização.

3. Na seção **motivo da envio** , selecione uma das seguintes opções:

   - **Não deve ter sido bloqueado**

   - **Deveriam ter sido bloqueados**: selecione **spam**, **phishing**ou **malware**. Se você não tiver certeza, use a melhor avaliação.

4. Se o filtro tiver sido ignorado devido às políticas após o envio, você verá informações sobre essa política.

   Se o filtro não tiver sido ignorado devido a uma ou mais políticas, a verificação será concluída em vários minutos. Você verá informações adicionais sobre o envio clicando no link status. Isso inclui os resultados da verificação de política e a veredicto de nova verificação. Observação isso não executa o email por meio da pilha de filtragem completa do Office 365 ATP novamente, mas executa uma verificação parcial com base em determinados atributos do email, da URL ou do arquivo.

5. Quando tiver concluído, clique no botão **Enviar** .

![Exemplo de envio de URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Enviar uma URL suspeita para a Microsoft

1. Na seção **tipo de objeto** , selecione **URL**. Na caixa exibida, digite a URL completa (por exemplo, <https://www.fabrikam.com/marketing.html> ).

2. Na seção **motivo da envio** , selecione uma das seguintes opções:

   - **Não deve ter sido bloqueado**

   - **Deveria ter sido bloqueado**: selecione **phishing** ou **malware**.

3. Quando tiver concluído, clique no botão **Enviar** .

![Exemplo de envio de email](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>Enviar um arquivo suspeito para a Microsoft

1. Na seção **tipo de objeto** , selecione **anexo**.

2. Clique em **escolher arquivo**. Na caixa de diálogo que é aberta, localize e selecione o arquivo e clique em **abrir**.

3. Na seção **motivo da envio** , selecione uma das seguintes opções:

   - **Não deve ter sido bloqueado**

   - **Deveria ter sido bloqueado**: o **malware** é a única opção e é selecionado automaticamente..

4. Quando tiver concluído, clique no botão **Enviar** .

![Exemplo de envio de anexos](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a>Exibir envios de administradores

1. No centro de conformidade & segurança, vá para análise de **Gerenciamento de ameaça** \> **Review** \> **mensagens de envio de administração**.

2. Na página **envios** que aparece, verifique se a guia **envios de administrador** está selecionada.

Próximo à parte superior da página, você pode inserir uma data de início, uma data de término e (por padrão), você pode filtrar por **ID de envio** , inserindo um valor na caixa e clicando em ![ Atualizar botão ](../../media/scc-quarantine-refresh.png) . Update

Para alterar os critérios de filtro, clique no botão **ID de envio** e escolha um dos seguintes valores:

- **Sender**
- **Assunto/URL/nome do arquivo**
- **Enviado por**
- **Tipo de envio**
- **Status**

![Opções de filtro para envios de administradores](../../media/admin-submission-email-filter-options.png)

Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **dados do gráfico** ou **tabela**. Na caixa de diálogo exibida, salve o arquivo. csv.

Abaixo do gráfico, há três guias: **email** (padrão), **URL**e **anexo**.

### <a name="view-admin-email-submissions"></a>Exibir envios de email de administração

Clique na guia **email** .

Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:

- **Date**
- **ID de envio**
- **Enviado por**<sup>\*</sup>
- **Assunto**<sup>\*</sup>
- **Sender**
- **IP do remetente**<sup>\*</sup>
- **Tipo de envio**
- **Motivo da entrega**
- **Estado**<sup>\*</sup>
- **Tipo de controle**
- **Fonte de controle**

  <sup>\*</sup>Se você clicar nesse valor, as informações detalhadas serão exibidas em um submenu.

### <a name="view-admin-url-submissions"></a>Exibir envios de URL de administração

Clique na guia **URL** .

Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:

- **Date**
- **ID de envio**
- **Enviado por**<sup>\*</sup>
- **URL**<sup>\*</sup>
- **Tipo de envio**
- **Estado**<sup>\*</sup>

  <sup>\*</sup>Se você clicar nesse valor, as informações detalhadas serão exibidas em um submenu.

### <a name="view-admin-attachment-submissions"></a>Exibir envios de anexo de administrador

Clique na guia **anexos** .

Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:

- **Date**
- **ID de envio**
- **Enviado por**<sup>\*</sup>
- **Nome do arquivo**<sup>\*</sup>
- **Tipo de envio**
- **Estado**<sup>\*</sup>

  <sup>\*</sup>Se você clicar nesse valor, as informações detalhadas serão exibidas em um submenu.

## <a name="view-user-submissions-to-microsoft"></a>Exibir envios de usuários para a Microsoft

Se você tiver implantado o [suplemento de mensagem de relatório](enable-the-report-message-add-in.md)ou se as pessoas usarem [relatórios internos no Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), você poderá ver quais usuários estão relatando na guia **envios** de usuários.

1. No centro de conformidade & segurança, vá para análise de **Gerenciamento de ameaça** \> **Review** \> **mensagens de envio de administração**.

2. Na página **envios** que aparece, clique na guia **envios do usuário** .

Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:

- **Enviado em**
- **Enviado por**<sup>\*</sup>
- **Assunto**<sup>\*</sup>
- **Sender**
- **IP do remetente**<sup>\*</sup>
- **Tipo de envio**

<sup>\*</sup>Se você clicar nesse valor, as informações detalhadas serão exibidas em um submenu.

Próximo à parte superior da página, você pode inserir uma data de início, uma data de término e (por padrão), você pode filtrar por **remetente** inserindo um valor na caixa e clicando em ![ Atualizar botão ](../../media/scc-quarantine-refresh.png) . Update

Para alterar os critérios de filtro, clique no botão **remetente** e escolha um dos seguintes valores:

- **Domínio do remetente**
- **Assunto**
- **Enviado por**
- **Tipo de envio**
- **IP do remetente**

![Opções de filtro para envios de usuários](../../media/user-submissions-filter-options.png)

Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **dados do gráfico** ou **tabela**. Na caixa de diálogo exibida, salve o arquivo. csv.

## <a name="view-user-submissions-to-the-custom-mailbox"></a>Exibir envios de usuários para a caixa de correio personalizada

Se você [configurou uma caixa de correio personalizada](user-submission.md) para receber mensagens relatadas pelo usuário, você pode exibir e também enviar mensagens que foram entregues à caixa de correio de relatório.

1. No centro de conformidade & segurança, vá para análise de **Gerenciamento de ameaça** \> **Review** \> **mensagens de envio de administração**.

2. Na página **envios** que aparece, clique na guia **caixa de correio personalizada** .

Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:

- **Enviado em**
- **Enviado por**<sup>\*</sup>
- **Assunto**<sup>\*</sup>
- **Sender**
- **IP do remetente**<sup>\*</sup>
- **Tipo de envio**

Próximo à parte superior da página, você pode inserir uma data de início, uma data de término e filtrar por **enviado** , inserindo um valor na caixa e clicando em ![ Atualizar botão ](../../media/scc-quarantine-refresh.png) . Update

Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **dados do gráfico** ou **tabela**. Na caixa de diálogo exibida, salve o arquivo. csv.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>Enviar mensagens para a Microsoft a partir da caixa de correio personalizada

Se você tiver configurado a caixa de correio personalizada para interceptar mensagens relatadas pelo usuário sem enviar as mensagens à Microsoft, poderá encontrar e enviar mensagens específicas para a Microsoft para análise. Isso move efetivamente um envio de usuário para um envio de administrador.

Na guia **caixa de correio personalizada** , selecione uma mensagem na lista, clique no botão de **ação** e faça uma das seguintes seleções:

- **Limpeza de relatório**
- **Relatar phishing**
- **Relatar malware**
- **Relatar spam**

![Opções no botão de ação](../../media/user-submission-custom-mailbox-action-button.png)
