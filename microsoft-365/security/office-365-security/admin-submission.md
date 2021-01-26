---
title: Envios de administrador
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o portal de Envios no Centro de Conformidade e Segurança & para enviar emails suspeitos, emails suspeitos de phishing, spam e outras mensagens potencialmente prejudiciais, URLs e arquivos à Microsoft para verificação.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 879a13e7c059495e653b79c424b227fe9f35a498
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976598"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Usar o Envio do Administrador para enviar spam, phishing, URLs e arquivos à Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Nas organizações do Microsoft 365 com caixas de correio no Exchange Online, os administradores podem usar o portal de Envios no Centro de Conformidade & e Segurança para enviar mensagens de email, URLs e anexos à Microsoft para verificação.

Ao enviar uma mensagem de email, você receberá:

1. **Verificação de autenticação de** email: Detalhes sobre se a autenticação de email passou ou falhou quando foi entregue.
2. **Visitas à** política: informações sobre quaisquer políticas que possam ter permitido ou bloqueado o email de entrada em seu locatário, substituindo nossos vereditos de filtro de serviço.
3. **Reputação/detonação da** carga: exame de quaisquer URLs e anexos na mensagem.
4. **Análise de nota:** revisão feita por notas humanas para confirmar se as mensagens são mal-intencionadas ou não.

> [!IMPORTANT]
> A reputação/a detonação da carga e a análise de classificação não são feitas em todos os locatários. As informações são impedidas de sair da organização quando os dados não deveriam sair do limite do locatário para fins de conformidade.

Para outras maneiras de enviar mensagens de email, URLs e anexos à Microsoft, consulte Mensagens e arquivos [de relatório para a Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Você abrir o Centro de conformidade e segurança em <https://protection.office.com/>. Para ir diretamente para a página **de** Envio, use <https://protection.office.com/reportsubmission> .

- Para enviar mensagens e arquivos à Microsoft, você precisa ser membro de um dos seguintes grupos de função:

  - **Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).

  - **Gerenciamento de organização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

    Observe que a associação nesse grupo de função é necessária para exibir [envios](#view-user-submissions-to-the-custom-mailbox) de usuário para a caixa de correio personalizada, conforme descrito posteriormente neste artigo.

- Para obter mais informações sobre como os usuários podem enviar mensagens e arquivos à Microsoft, consulte [Mensagens e arquivos de relatório para a Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="report-suspicious-content-to-microsoft"></a>Relatar conteúdo suspeito à Microsoft

1. No Centro de Conformidade & segurança,  vá para Envios de gerenciamento de ameaças, verifique se você está na guia Envios de Administrador e clique em \>  **Novo envio.** 

2. Use **o sub80** de envio novo que aparece para enviar a mensagem, a URL ou o anexo, conforme descrito nas seções a seguir.

### <a name="submit-a-questionable-email-to-microsoft"></a>Enviar um email questionável para a Microsoft

1. Na seção **Tipo de objeto,** selecione **Email**. Na seção **Formato de** envio, use uma das seguintes opções:

   - **ID** da mensagem de rede: este é um valor guid que está disponível no header **X-MS-Exchange-Organization-Network-Message-Id** na mensagem ou no header **X-MS-Office365-Filtering-Correlation-Id** em mensagens em quarentena.

   - **Arquivo:** clique **em Escolher arquivo.** Na caixa de diálogo que abre, encontre e selecione o arquivo .eml ou .msg e clique em **Abrir.**

   > [!NOTE]
   > Os administradores com o Defender para Office 365 Plano 1 ou Plano 2 podem enviar mensagens com até 30 dias. Outros administradores só poderão voltar 7 dias.

2. Na seção **Destinatários,** especifique um ou mais destinatários para os quais você gostaria de executar uma verificação de política. A verificação de política determinará se o email burlou a verificação devido a políticas de usuário ou organização.

3. Na seção **Motivo do envio,** selecione uma das seguintes opções:

   - **Não deveria ter sido bloqueado**

   - **Deve ter sido bloqueado:** Selecionar **Spam,** **Phishing** ou **Malware.** Se você não tiver certeza, use seu melhor bom senso.

4. Quando terminar, clique no **botão** Enviar.

   ![Exemplo de envio de URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Enviar uma URL suspeita para a Microsoft

1. Na seção **Tipo de objeto,** selecione **URL**. Na caixa exibida, insira a URL completa (por exemplo, `https://www.fabrikam.com/marketing.html` ).

2. Na seção **Motivo do envio,** selecione uma das seguintes opções:

   - **Não deveria ter sido bloqueado**

   - **Deve ter sido bloqueado:** Selecionar **Phishing** ou **Malware.**

3. Quando terminar, clique no **botão** Enviar.

   ![Exemplo de envio de email](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>Enviar um arquivo suspeito para a Microsoft

1. Na seção **Tipo de objeto,** selecione **Anexo**.

2. Clique **em Escolher Arquivo.** Na caixa de diálogo que é aberta, encontre e selecione o arquivo e clique em **Abrir.**

3. Na seção **Motivo do envio,** selecione uma das seguintes opções:

   - **Não deveria ter sido bloqueado**

   - **Deve ter sido bloqueado:** **o malware** é a única opção e é selecionado automaticamente.

4. Quando terminar, clique no **botão** Enviar.

   ![Exemplo de envio de anexo](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a>Exibir envios de administrador

No Centro de Conformidade & segurança,  vá para Envios de gerenciamento de ameaças, verifique se você está na guia Envios de Administrador e clique em \>  **Novo envio.** 

Na parte superior da página, você pode inserir uma data de início, uma data de término e (por padrão) filtrar pela **ID** de Envio (um valor GUID atribuído a cada envio) inserindo um valor na caixa e clicando no botão ![ ](../../media/scc-quarantine-refresh.png) Atualizar. Update

Para alterar os critérios de filtro, clique no **botão ID de** Envio e escolha um dos seguintes valores:

- **Sender**
- **Assunto/URL/Nome do arquivo**
- **Enviado por**
- **Tipo de envio**
- **Status**

![Opções de filtro para envios de administrador](../../media/admin-submission-email-filter-options.png)

Para exportar os resultados, clique **em Exportar** próximo à parte superior da página e selecione **Chart data** ou **Table**. Na caixa de diálogo exibida, salve o arquivo .csv.

Abaixo do gráfico, há três guias: **Email** (padrão), **URL** e **Anexo.**

### <a name="view-admin-email-submissions"></a>Exibir envios de email de administrador

Clique na **guia Email.**

Você pode clicar **no botão Opções de** coluna na parte inferior da página para adicionar ou remover colunas da exibição:

- **Date**
- **ID de** envio: um valor GUID atribuído a cada envio.
- **Enviado por**<sup>\*</sup>
- **Assunto**<sup>\*</sup>
- **Sender**
- **IP do remetente**<sup>\*</sup>
- **Tipo de envio**
- **Motivo da entrega**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Se você clicar nesse valor, as informações detalhadas serão exibidas em um flyout.

#### <a name="admin-submission-rescan-details"></a>Detalhes de verificação de envio de administrador

As mensagens enviadas nos envios de administrador são novamente exibidas e os resultados são mostrados no submenu de detalhes:

- Se houve uma falha na autenticação de email do remetente no momento da entrega.
- Informações sobre quaisquer acertos de política que poderiam ter afetado ou substituído o veredito de uma mensagem.
- Resultados de detonação atuais para ver se as URLs ou arquivos contidos na mensagem são mal-intencionados ou não.
- Comentários dos alunos.

Se uma substituição foi encontrada, a verificação novamente deve ser concluída em vários minutos. Se não houve um problema na autenticação ou na entrega de email não tiver sido afetado por uma substituição, o feedback dos alunos pode levar até um dia.

### <a name="view-admin-url-submissions"></a>Exibir envios de URL de administrador

Clique na **guia URL.**

Você pode clicar **no botão Opções de** coluna na parte inferior da página para adicionar ou remover colunas da exibição:

- **Date**
- **ID de envio**
- **Enviado por**<sup>\*</sup>
- **URL**<sup>\*</sup>
- **Tipo de envio**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Se você clicar nesse valor, as informações detalhadas serão exibidas em um flyout.

### <a name="view-admin-attachment-submissions"></a>Exibir envios de anexo de administrador

Clique na **guia Anexos.**

Você pode clicar **no botão Opções de** coluna na parte inferior da página para adicionar ou remover colunas da exibição:

- **Date**
- **ID de envio**
- **Enviado por**<sup>\*</sup>
- **Nome do arquivo**<sup>\*</sup>
- **Tipo de envio**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Se você clicar nesse valor, as informações detalhadas serão exibidas em um flyout.

## <a name="view-user-submissions-to-microsoft"></a>Exibir envios de usuário para a Microsoft

Se você implantou o complemento Mensagem de [Relatório,](enable-the-report-message-add-in.md)o relatório [de phishing](enable-the-report-phish-add-in.md)ou as pessoas usam os relatórios integrados no [Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), você pode ver o que os usuários estão relatando na guia **Envios** de usuário.

1. No Centro de Conformidade & segurança, vá para Envios **de gerenciamento** \> **de ameaças.**

2. Selecione a **guia Envios de** usuário e clique em **Novo envio.**

Você pode clicar **no botão Opções de** coluna na parte inferior da página para adicionar ou remover colunas da exibição:

- **Enviado em**
- **Enviado por**<sup>\*</sup>
- **Assunto**<sup>\*</sup>
- **Sender**
- **IP do remetente**<sup>\*</sup>
- **Tipo de envio**

<sup>\*</sup> Se você clicar nesse valor, as informações detalhadas serão exibidas em um flyout.

Na parte superior da página, você pode inserir uma data de início, uma  data de término e (por padrão) filtrar por Remetente inserindo um valor na caixa e clicando no botão ![ ](../../media/scc-quarantine-refresh.png) Atualizar. Update

Para alterar os critérios de filtro, clique **no botão** Remetente e escolha um dos seguintes valores:

- **Domínio do remetente**
- **Assunto**
- **Enviado por**
- **Tipo de envio**
- **IP do remetente**

![Opções de filtro para envios de usuário](../../media/user-submissions-filter-options.png)

Para exportar os resultados, clique **em Exportar** próximo à parte superior da página e selecione **Chart data** ou **Table**. Na caixa de diálogo exibida, salve o arquivo .csv.

## <a name="view-user-submissions-to-the-custom-mailbox"></a>Exibir envios de usuário para a caixa de correio personalizada

**Se** você configurou [uma caixa de](user-submission.md) correio personalizada para receber mensagens relatadas pelo usuário, você pode exibir e também enviar mensagens que foram entregues à caixa de correio de relatório.

1. No Centro de Conformidade & segurança, vá para Envios **de gerenciamento** \> **de ameaças.**

2. Selecione a **guia Caixa de Correio** Personalizada.

Você pode clicar **no botão Opções de** coluna na parte inferior da página para adicionar ou remover colunas da exibição:

- **Enviado em**
- **Enviado por**<sup>\*</sup>
- **Assunto**<sup>\*</sup>
- **Sender**
- **IP do remetente**<sup>\*</sup>
- **Tipo de envio**

Na parte superior da página, você pode inserir uma data de início, uma data de término e pode filtrar por **Submitted** inserindo um valor na caixa e clicando no botão ![ ](../../media/scc-quarantine-refresh.png) Atualizar. Update

Para exportar os resultados, clique **em Exportar** próximo à parte superior da página e selecione **Chart data** ou **Table**. Na caixa de diálogo exibida, salve o arquivo .csv.

## <a name="undo-user-submissions"></a>Desfazer envios de usuário

Depois que um usuário envia um email suspeito para a caixa de correio personalizada, o usuário e o administrador não têm a opção de desfazer o envio. Se o usuário quiser recuperar o email, ele estará disponível para recuperação nas pastas Itens Excluídos ou Lixo Eletrônico.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>Enviar mensagens para a Microsoft da caixa de correio personalizada

Se você configurou a caixa de correio personalizada para interceptar mensagens relatadas pelo usuário sem enviar as mensagens para a Microsoft, poderá encontrar e enviar mensagens específicas à Microsoft para análise. Isso efetivamente move um envio de usuário para um envio de administrador.

Na guia **Caixa de Correio** Personalizada, selecione  uma mensagem na lista, clique no botão Ação e faça uma das seguintes seleções:

- **Relatório limpo**
- **Relatar phishing**
- **Relatar malware**
- **Relatar spam**

![Opções no botão Ação](../../media/user-submission-custom-mailbox-action-button.png)
