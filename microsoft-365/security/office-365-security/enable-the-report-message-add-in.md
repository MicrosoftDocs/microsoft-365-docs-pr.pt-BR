---
title: Habilitar o suplemento de Mensagem de Relatório
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Saiba como habilitar o suplemento de mensagem de relatório para o Outlook e o Outlook na Web, para usuários individuais ou para toda a organização.
ms.openlocfilehash: 2e9d6ae87d0f6da7721c5c86d904a836d4610a5e
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196604"
---
# <a name="enable-the-report-message-add-in"></a>Habilitar o suplemento de Mensagem de Relatório

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Se você for um administrador em uma organização do Microsoft 365 com caixas de correio do Exchange Online, recomendamos que você use o portal de envios no centro de conformidade de & de segurança. Para obter mais informações, consulte [usar o envio do administrador para enviar spam, phishing, URLs e arquivos suspeitos à Microsoft](admin-submission.md).

O suplemento de mensagem de relatório para o Outlook e o Outlook na Web (anteriormente conhecido como Outlook Web App) permite que as pessoas relatem facilmente falsos positivos (emails satisfatórios marcados como defeituosos) ou falsos negativos (emails inválidos permitidos) para a Microsoft e seus afiliados para análise. A Microsoft usa esses envios para melhorar a eficácia das tecnologias de proteção de email.

Por exemplo, suponha que as pessoas estejam relatando muitas mensagens como phishing. Essas informações são superfícies no [painel de segurança](security-dashboard.md) e em outros relatórios. A equipe de segurança da sua organização pode usar essas informações como indicação de que as políticas anti-phishing podem precisar ser atualizadas. Ou, se as pessoas estiverem relatando muitas mensagens que foram sinalizadas como lixo eletrônico como não sendo lixo eletrônico usando o suplemento de mensagem de relatório, a equipe de segurança da sua organização poderá precisar ajustar [políticas antispam](configure-your-spam-filter-policies.md).

Além disso, se sua organização estiver usando o [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) ou o [plano 2](office-365-ti.md), o suplemento de mensagem de relatório fornecerá a equipe de segurança da sua organização com informações úteis que podem ser usadas para analisar e atualizar as políticas de segurança.

Os administradores podem habilitar o suplemento de mensagem de relatório para a organização, e os usuários individuais podem instalá-lo para si mesmos.

Se você for um usuário individual, é possível [habilitar o relatório de suplemento de mensagens para você](#get-the-report-message-add-in-for-yourself).

Se você for um administrador global ou um administrador do Exchange Online e o Exchange estiver configurado para usar a autenticação OAuth, você poderá [habilitar o suplemento de mensagem de relatório para sua organização](#get-and-enable-the-report-message-add-in-for-your-organization). O suplemento de mensagem de relatório agora está disponível por meio da [implantação centralizada](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- O suplemento de mensagem de relatório funciona com a maioria das assinaturas do Microsoft 365 e os seguintes produtos:

  - Outlook na Web
  - Outlook 2013 SP1 ou posterior
  - Outlook 2016 para Mac
  - Outlook incluído no Microsoft 365 Apps for Enterprise

- O suplemento de mensagem de relatório não está disponível para caixas de correio em organizações locais do Exchange.

- Você pode configurar mensagens relatadas para serem copiadas ou redirecionadas para uma caixa de correio que você especificar. Para obter mais informações, consulte [especificar uma caixa de correio para envios de emails de spam e mensagens de phishing no Exchange Online](user-submission.md).

- O navegador da Web existente deverá funcionar com o suplemento de mensagem de relatório. Mas, se você notar que o suplemento não está disponível ou não está funcionando conforme o esperado, tente um navegador diferente.

- Para instalações organizacionais, a organização precisa ser configurada para usar a autenticação OAuth. Confira mais informações em [determinar se a implantação centralizada de suplementos funciona para sua organização](../../admin/manage/centralized-deployment-of-add-ins.md).

- Os administradores precisam ser membros do grupo de funções administradores globais. Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

## <a name="get-the-report-message-add-in-for-yourself"></a>Obter o suplemento de mensagem de relatório para você mesmo

1. Vá para o Microsoft AppSource em <https://appsource.microsoft.com/marketplace/apps> e procure o suplemento de mensagem de relatório. Para ir diretamente para o suplemento de mensagem de relatório, acesse <https://appsource.microsoft.com/product/office/wa104381180> .

2. Clique em **obter agora**.

   ![Mensagem de relatório-obter agora](../../media/ReportMessageGETITNOW.png)

3. Na caixa de diálogo exibida, revise os termos de uso e política de privacidade e clique em **continuar**.

4. Entre usando sua conta corporativa ou de estudante (para uso comercial) ou sua conta da Microsoft (para uso pessoal).

Depois que o suplemento estiver instalado e habilitado, você verá os seguintes ícones:

- No Outlook, o ícone tem a seguinte aparência:

  ![Ícone de suplemento de mensagem de relatório para Outlook](../../media/OutlookReportMessageIcon.png)

- No Outlook na Web, o ícone tem a seguinte aparência:

  ![Ícone de suplemento da mensagem de relatório da Web do Outlook](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Para saber como usar o suplemento, confira [usar o suplemento de mensagem de relatório](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>Obter e habilitar o suplemento de mensagem de relatório para sua organização

> [!NOTE]
> Pode levar até 12 horas para que o suplemento apareça em sua organização.

1. No centro de administração do Microsoft 365, vá para a página **serviços & suplementos** <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> e clique em **implantar suplemento**.

   ![Página serviços e suplementos no centro de administração do Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. No submenu **implantar um novo suplemento** que aparece, revise as informações e clique em **Avançar**.

3. Na próxima página, clique em **escolher na loja**.

   ![Implantar uma nova página de suplemento](../../media/NewAddInScreen2.png)

4. Na página **selecionar suplemento** que aparece, clique na caixa de **pesquisa** , insira uma mensagem de **relatório**e clique em ícone de pesquisa de **pesquisa** ![ ](../../media/search-icon.png) . Na lista de resultados, encontre **mensagem de relatório** e clique em **Adicionar**.

   ![Selecionar resultados de pesquisa de suplemento](../../media/NewAddInScreen3.png)

5. Na caixa de diálogo exibida, revise as informações de licenciamento e privacidade e clique em **continuar**.

6. Na página **Configurar Suplemento** exibida, defina as seguintes configurações:

   - **Usuários atribuídos**: selecione um dos seguintes valores:

     - **Todos** (padrão)
     - **Usuários/grupos específicos**
     - **Só eu**

   - **Método de implantação**: selecione um dos seguintes valores:

     - **Fixo (padrão)**: o suplemento é implantado automaticamente para os usuários especificados, e eles não podem removê-lo.
     - **Disponível**: os usuários podem instalar o suplemento em **casa** \> **Get de suplementos** do \> **administrador**.
     - **Opcional**: o suplemento é implantado automaticamente para os usuários especificados, mas eles podem optar por removê-lo.

   ![Configurar página de suplemento](../../media/configure-add-in.png)

   Quando tiver concluído, clique em **implantar**.

7. Na página **implantar mensagem de relatório** que aparece, você verá um relatório de progresso seguido de uma confirmação de que o suplemento foi implantado. Depois de ler as informações, clique em **Avançar**.

   ![Página implantar mensagem de relatório](../../media/deploy-report-message-page.png)

8. Na página **anunciar suplemento** que aparece, revise as informações e, em seguida, clique em **fechar**.

   ![Anunciar página de suplemento](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a>Saiba como usar o suplemento de mensagem de relatório

Pessoas que têm o suplemento atribuído a eles verão os seguintes ícones:

- No Outlook, o ícone tem a seguinte aparência:

  ![Ícone de suplemento de mensagem de relatório para Outlook](../../media/OutlookReportMessageIcon.png)

- No Outlook na Web, o ícone tem a seguinte aparência:

  ![Ícone de suplemento da mensagem de relatório da Web do Outlook](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Ao notificar os usuários sobre o suplemento de mensagens de relatório, inclua um link para [usar o suplemento de mensagem de relatório](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>Revise ou edite as configurações do suplemento de mensagem de relatório

1. No centro de administração do Microsoft 365, acesse a página de **suplementos de & de serviços** em <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> .

   ![Página serviços e suplementos no novo centro de administração do Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Localize e selecione o suplemento de **mensagem de relatório** .

3. No submenu **Editar mensagem de relatório** que aparece, revise e edite as configurações conforme apropriado para sua organização. Quando concluir, clique em **Salvar**.

   ![Configurações para o suplemento de mensagem de relatório](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a>Exibir e examinar mensagens relatadas

Para revisar as mensagens que os usuários reportam à Microsoft, você tem estas opções:

- Use o portal de envios do administrador. Para obter mais informações, consulte [View User envios to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).

- Criar uma regra de fluxo de emails (também conhecida como regra de transporte) para enviar cópias de mensagens relatadas. Para obter instruções, consulte [usar regras de fluxo de emails para ver o que seus usuários estão relatando à Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).
