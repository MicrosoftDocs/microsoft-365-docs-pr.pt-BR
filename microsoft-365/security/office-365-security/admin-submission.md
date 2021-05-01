---
title: Envios de administrador
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
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
description: Os administradores podem aprender a usar o portal Envios no Centro de Conformidade de Segurança & para enviar emails suspeitos, emails suspeitos de phishing, spam e outras mensagens potencialmente prejudiciais, URLs e arquivos para a Microsoft para verificação.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d0b91808aa9008f467f66b8200f2c05a120fbcd9
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107225"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Usar o Envio do Administrador para enviar spam, phishing, URLs e arquivos à Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)


Em Microsoft 365 organizações com caixas de correio no Exchange Online, os administradores podem usar o portal Envios no Centro de Conformidade & Segurança para enviar mensagens de email, URLs e anexos à Microsoft para verificação.

Ao enviar uma mensagem de email, você receberá:

1. **Verificação de autenticação de** email : Detalhes sobre se a autenticação de email passou ou falhou quando ela foi entregue.
2. **Visitas de política**: informações sobre quaisquer políticas que possam ter permitido ou bloqueado o email de entrada em seu locatário, substituindo nossos vereditos de filtro de serviço.
3. **Reputação/detonação** de carga : Exame de quaisquer URLs e anexos na mensagem.
4. **Análise de notas**: Revisão feita por alunos de nível humano para confirmar se as mensagens são mal-intencionadas ou não.

> [!IMPORTANT]
> A análise de reputação/detonação e classificação de carga não é feita em todos os locatários. As informações são impedidas de sair da organização quando os dados não devem sair do limite do locatário para fins de conformidade.

Para outras maneiras de enviar mensagens de email, URLs e anexos à Microsoft, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a página **Envio,** use <https://protection.office.com/reportsubmission> .

- Para enviar mensagens e arquivos para a Microsoft, você precisa ser membro de um dos seguintes grupos de função:

  - **Gerenciamento da** organização **ou leitor de segurança** no Centro de Conformidade & [Segurança.](permissions-in-the-security-and-compliance-center.md)

  - **Gerenciamento de organização** em [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).

    Observe que a associação neste grupo de funções é necessária para Exibir [envios](#view-user-submissions-to-the-custom-mailbox) de usuário para a caixa de correio personalizada conforme descrito posteriormente neste artigo.

- Para obter mais informações sobre como os usuários podem enviar mensagens e arquivos para a Microsoft, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="report-suspicious-content-to-microsoft"></a>Relatar conteúdo suspeito à Microsoft

1. Na Central de Conformidade & segurança,  vá para Envios de gerenciamento de ameaças , verifique se você está na guia \>  **Envios de** administrador e clique em **Novo envio**.

2. Use Novo sub-sub-sub-texto de envio que aparece para enviar a mensagem, a URL ou o anexo, conforme descrito nas seções a seguir. 

### <a name="submit-a-questionable-email-to-microsoft"></a>Enviar um email questionável à Microsoft

1. Na seção **Tipo de** objeto, selecione **Email**. Na seção **Formato de envio,** use uma das seguintes opções:

   - **ID** da mensagem de rede : este é um valor GUID que está disponível no header **X-MS-Exchange-Organization-Network-Message-Id** na mensagem ou no header **X-MS-Office365-Filtering-Correlation-Id** em mensagens em quarentena.

   - **Arquivo**: clique **em Escolher arquivo**. Na caixa de diálogo que é aberta, encontre e selecione o arquivo .eml ou .msg e clique em **Abrir**.

   > [!NOTE]
   > A capacidade de enviar mensagens com até 30 dias foi temporariamente suspensa para o Defender Office 365 clientes. Os administradores só poderão voltar 7 dias.

2. Na seção **Destinatários,** especifique um ou mais destinatários com os quais você gostaria de executar uma verificação de política. A verificação de política determinará se o email foi ignorado devido a políticas de usuário ou organização.

3. Na seção **Motivo do envio,** selecione uma das seguintes opções:

   - **Não deve ter sido bloqueado**

   - **Deve ter sido bloqueado**: Selecione **Spam,** **Phishing** ou **Malware**. Se você não tiver certeza, use seu melhor julgamento.

4. Quando terminar, clique no **botão Enviar.**

   ![Novo exemplo de envio de URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Enviar uma URL suspeita para a Microsoft

1. Na seção **Tipo de** objeto, selecione **URL**. Na caixa exibida, insira a URL completa (por exemplo, `https://www.fabrikam.com/marketing.html` ).

2. Na seção **Motivo do envio,** selecione uma das seguintes opções:

   - **Não deve ter sido bloqueado**

   - **Deve ter sido bloqueado**: Selecione **Phishing** ou **Malware.**

3. Quando terminar, clique no **botão Enviar.**

   ![Novo exemplo de envio de email](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>Enviar um arquivo suspeito à Microsoft

1. Na seção **Tipo de** objeto, selecione **Anexo**.

2. Clique **em Escolher Arquivo**. Na caixa de diálogo que é aberta, encontre e selecione o arquivo e clique em **Abrir**.

3. Na seção **Motivo do envio,** selecione uma das seguintes opções:

   - **Não deve ter sido bloqueado**

   - **Deve ter sido bloqueado**: **Malware** é a única opção e é selecionado automaticamente..

4. Quando terminar, clique no **botão Enviar.**

   ![Novo exemplo de envio de anexo](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a>Exibir itens enviados para análise

No Centro de Conformidade & segurança,  vá para \> **Envios** de gerenciamento de ameaças , verifique se você está na guia **Enviado para** análise

Na parte superior da página, você pode inserir uma data de início, uma data de término e (por padrão) você pode filtrar pela **ID** do Envio (um valor GUID atribuído a cada envio) inserindo um valor na caixa e clicando em Atualizar botão ![ ](../../media/scc-quarantine-refresh.png) . Update

Para alterar os critérios de filtro, clique no botão **ID do** Envio e escolha um dos seguintes valores:

- **Sender**
- **Assunto/URL/Nome do arquivo**
- **Enviado por**
- **Tipo de envio**
- **Status**

![Novas opções de Filtro para envios de administrador](../../media/admin-submission-email-filter-options.png)

Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **Dados de gráfico** ou **Tabela**. Na caixa de diálogo exibida, salve o arquivo .csv arquivo.

Abaixo do gráfico, há três guias: **Email** (padrão), **URL** e **Anexo.**

### <a name="view-admin-email-submissions"></a>Exibir envios de email do administrador

Clique na **guia Email.**

Você pode clicar no **botão Opções de** coluna perto da parte inferior da página para adicionar ou remover colunas do exibição:

- **Date**
- **ID do envio:** um valor GUID atribuído a cada envio.
- **Enviado por**<sup>\*</sup>
- **Assunto**<sup>\*</sup>
- **Sender**
- **IP do remetente**<sup>\*</sup>
- **Tipo de envio**
- **Motivo da entrega**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Se você clicar nesse valor, informações detalhadas serão exibidas em um sobremenu.

#### <a name="admin-submission-rescan-details"></a>Detalhes da verificação de envio de administrador

As mensagens enviadas em envios de administrador são rescanned e os resultados mostrados no submenu de detalhes:

- Se houve falha na autenticação do email do remetente no momento da entrega.
- Informações sobre quaisquer acessos à política que possam ter afetado ou substituído o veredicto de uma mensagem.
- Resultados de detonação atuais para ver se os URLs ou arquivos contidos na mensagem eram maliciosos ou não.
- Comentários dos alunos.

Se uma substituição for encontrada, a nova varredura deve ser concluída em alguns minutos. Se não houve um problema na autenticação ou na entrega de email não foi afetado por uma substituição, os comentários dos alunos podem levar até um dia.

### <a name="view-admin-url-submissions"></a>Exibir envios de URL do administrador

Clique na **guia URL.**

Você pode clicar no **botão Opções de** coluna perto da parte inferior da página para adicionar ou remover colunas do exibição:

- **Date**
- **ID do envio**
- **Enviado por**<sup>\*</sup>
- **URL**<sup>\*</sup>
- **Tipo de envio**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Se você clicar nesse valor, informações detalhadas serão exibidas em um sobremenu.

### <a name="view-admin-attachment-submissions"></a>Exibir envios de anexos de administrador

Clique na **guia Anexos.**

Você pode clicar no **botão Opções de** coluna perto da parte inferior da página para adicionar ou remover colunas do exibição:

- **Date**
- **ID do envio**
- **Enviado por**<sup>\*</sup>
- **Nome do arquivo**<sup>\*</sup>
- **Tipo de envio**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Se você clicar nesse valor, informações detalhadas serão exibidas em um sobremenu.

## <a name="view-user-submissions-to-microsoft"></a>Exibir envios de usuários para a Microsoft

Se você tiver implantado o [add-in](enable-the-report-message-add-in.md)De Mensagem de Relatório, o complemento Relatar [Phishing](enable-the-report-phish-add-in.md)ou as pessoas usarem o relatório integrado no Outlook na [Web,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)você poderá ver o que os usuários estão relatando na guia **Envios do** usuário.

1. No Centro de Conformidade & segurança, vá para **Envios de gerenciamento** \> **de ameaças.**

2. Selecione a **guia Envios de usuário** e clique em Novo **envio**.

Você pode clicar no **botão Opções de** coluna perto da parte inferior da página para adicionar ou remover colunas do exibição:

- **Enviado em**
- **Enviado por**<sup>\*</sup>
- **Assunto**<sup>\*</sup>
- **Sender**
- **IP do remetente**<sup>\*</sup>
- **Tipo de envio**

<sup>\*</sup> Se você clicar nesse valor, informações detalhadas serão exibidas em um sobremenu.

Na parte superior da página, você pode inserir uma data de início, uma data de término e (por padrão) você pode filtrar por **Remetente** inserindo um valor na caixa e clicando em ![ Atualizar botão ](../../media/scc-quarantine-refresh.png) . Update

Para alterar os critérios de filtro, clique no botão **Remetente** e escolha um dos seguintes valores:

- **Domínio do remetente**
- **Assunto**
- **Enviado por**
- **Tipo de envio**
- **IP do remetente**

![Novas opções de Filtro para envios de usuários](../../media/user-submissions-filter-options.png)

Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **Dados de gráfico** ou **Tabela**. Na caixa de diálogo exibida, salve o arquivo .csv arquivo.

## <a name="view-user-submissions-to-the-custom-mailbox"></a>Exibir envios de usuário para a caixa de correio personalizada

**Se** você configurou [uma caixa](user-submission.md) de correio personalizada para receber mensagens relatadas pelo usuário, você pode exibir e também enviar mensagens que foram entregues à caixa de correio de relatório.

1. No Centro de Conformidade & segurança, vá para **Envios de gerenciamento** \> **de ameaças.**

2. Selecione a **guia Caixa de correio** Personalizada.

Você pode clicar no **botão Opções de** coluna perto da parte inferior da página para adicionar ou remover colunas do exibição:

- **Enviado em**
- **Enviado por**<sup>\*</sup>
- **Assunto**<sup>\*</sup>
- **Sender**
- **IP do remetente**<sup>\*</sup>
- **Tipo de envio**

Na parte superior da página, você pode inserir uma data de  início, uma data de término e filtrar enviando inserindo um valor na caixa e clicando em ![ Atualizar botão ](../../media/scc-quarantine-refresh.png) . Update

Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **Dados de gráfico** ou **Tabela**. Na caixa de diálogo exibida, salve o arquivo .csv arquivo.

> [!NOTE]
> Se as organizações estão configuradas para enviar somente para a caixa de correio personalizada, as mensagens relatadas não serão enviadas para análise novamente e os resultados no portal de mensagens relatadas pelo usuário sempre estarão vazios.

## <a name="undo-user-submissions"></a>Desfazer envios de usuário

Depois que um usuário envia um email suspeito para a caixa de correio personalizada, o usuário e o administrador não têm uma opção para desfazer o envio. Se o usuário quiser recuperar o email, ele estará disponível para recuperação nas pastas Itens Excluídos ou Lixo Eletrônico.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>Enviar mensagens para a Microsoft da caixa de correio personalizada

Se você configurou a caixa de correio personalizada para interceptar mensagens relatadas pelo usuário sem enviar as mensagens para a Microsoft, você poderá encontrar e enviar mensagens específicas para a Microsoft para análise. Isso move efetivamente um envio de usuário para um envio de administrador.

Na guia **Mensagens relatadas pelo** usuário, selecione uma mensagem na lista, clique no botão **Ação** e faça uma das seguintes seleções:

- **Relatório limpo**
- **Relatar phishing**
- **Relatar malware**
- **Relatar spam**

![Novas opções no botão Ação](../../media/user-submission-custom-mailbox-action-button.png)
