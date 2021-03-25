---
title: Habilitar o suplemento de Mensagem de Relatório
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Saiba como habilitar o complemento Mensagem de Relatório para Outlook e Outlook na Web, para usuários individuais ou toda a sua organização.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4e85af902eaaa41eb82acf8d4b4baedc538e7888
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51202946"
---
# <a name="enable-the-report-message-add-in"></a>Habilitar o suplemento de Mensagem de Relatório

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Se você for um administrador em uma organização do Microsoft 365 com caixas de correio do Exchange Online, recomendamos usar o portal Envios no Centro de Conformidade & Segurança. Para obter mais informações, [consulte Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).

Os complementos De Relatório de Mensagens e Phishing para Outlook e Outlook na Web (anteriormente conhecido como Outlook Web App) permitem que as pessoas reportem facilmente falsos positivos (bons emails marcados como ruins) ou falsos negativos (email ruim permitido) para a Microsoft e suas afiliadas para análise.

A Microsoft usa esses envios para melhorar a eficácia das tecnologias de proteção de email. Por exemplo, se as pessoas estão relatando muitas mensagens que foram sinalizadas como lixo eletrônico como Não Lixo Eletrônico usando o complemento Mensagem de Relatório, a equipe de segurança da sua organização pode precisar ajustar as políticas [anti-spam.](configure-your-spam-filter-policies.md)

Você pode instalar o add-in Report Message ou Report Phishing. Se quiser que seus usuários reportem apenas mensagens de phishing, implante o complemento Relatar Phishing em sua organização. Para obter mais informações, [consulte Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).

O complemento Mensagem de Relatório oferece a opção de relatar mensagens de spam e phishing. Os administradores podem habilitar o complemento Mensagem de Relatório para a organização, e usuários individuais podem instalá-lo por conta própria.

Se você for um usuário individual, poderá habilitar o [complemento Mensagem de Relatório para si mesmo.](#get-the-report-message-add-in-for-yourself)

Se você for um administrador global ou um administrador do Exchange Online e o Exchange estiver configurado para usar a autenticação OAuth, você poderá habilitar o complemento Mensagem [de Relatório para sua organização.](#get-and-enable-the-report-message-add-in-for-your-organization) A mensagem de Add-In agora está disponível por meio da [Implantação Centralizada.](../../admin/manage/centralized-deployment-of-add-ins.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- O complemento Mensagem de Relatório funciona com a maioria das assinaturas do Microsoft 365 e os seguintes produtos:

  - Outlook na Web
  - Outlook 2013 SP1 ou posterior
  - Outlook 2016 para Mac
  - Outlook incluído nos aplicativos do Microsoft 365 para Empresas
  - Aplicativo do Outlook para iOS e Android

- O complemento Mensagem de Relatório não está disponível para caixas de correio compartilhadas ou caixas de correio em organizações locais do Exchange.

- Você pode configurar mensagens relatadas a serem copiadas ou redirecionadas para uma caixa de correio especificada. Para obter mais informações, consulte [Políticas de envios de usuário](user-submission.md).

- O navegador da Web existente deve funcionar com o complemento Mensagem de Relatório. Mas, se você observar que o complemento não está disponível ou não está funcionando conforme o esperado, tente um navegador diferente.

- Para as instalações organizacionais, a organização precisa ser configurada para usar a autenticação OAuth. Para obter mais informações, [consulte Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).

- Os administradores precisam ser membros do grupo de função Administradores Globais. Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

## <a name="get-the-report-message-add-in-for-yourself"></a>Obter o complemento Mensagem de Relatório para você mesmo

1. Vá para o Microsoft AppSource em <https://appsource.microsoft.com/marketplace/apps> e pesquise o complemento Mensagem de Relatório. Para ir diretamente para o add-in Mensagem de Relatório, vá para <https://appsource.microsoft.com/product/office/wa104381180> .

2. Clique **em OBTER AGORA**.

   ![Mensagem de relatório - Obter agora](../../media/ReportMessageGETITNOW.png)

3. Na caixa de diálogo exibida, revise os termos de uso e política de privacidade e clique em **Continuar**.

4. Entre usando sua conta comercial ou de estudante (para uso comercial) ou sua conta da Microsoft (para uso pessoal).

Depois que o add-in for instalado e habilitado, você verá os seguintes ícones:

- No Outlook, o ícone tem esta aparência:

  ![Ícone de add-in de mensagem de relatório para o Outlook](../../media/OutlookReportMessageIcon.png)

- No Outlook na Web, o ícone tem esta aparência:

  ![Ícone do add-in de mensagem de relatório do Outlook na Web](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Para saber como usar o add-in, consulte [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>Obter e habilitar o complemento Mensagem de Relatório para sua organização

> [!NOTE]
> Pode levar até 12 horas para que o complemento apareça em sua organização.

1. No Centro de administração do Microsoft 365, vá para a página Ir para a página Configurações de **Complementos** em , Se você não vir a Página de Adicionar, vá para o \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> link Configurações Integradas aplicativos Complementos  na parte superior da página Aplicativos  \>  \> **integrados.** 

2. Selecione **Implantar o Add-in** na parte superior da página e selecione **Próximo**.

   ![Página serviços e complementos no centro de administração do Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. No **sub-sub-projeto** que aparece, revise as informações e clique em **Próximo**.

4. Na próxima página, clique **em Escolher na Loja**.

   ![Implantar uma nova página de complemento](../../media/NewAddInScreen2.png)

5. Na página **Selecionar o add-in** que  aparece, clique na caixa Pesquisar, insira **Mensagem** de Relatório e clique em **Pesquisar** ![ ícone de ](../../media/search-icon.png) Pesquisa. Na lista de resultados, encontre **Mensagem de Relatório** e clique em **Adicionar**.

   ![Selecionar resultados de pesquisa de complemento](../../media/NewAddInScreen3.png)

6. Na caixa de diálogo exibida, revise as informações de licenciamento e privacidade e clique em **Continuar**.

7. Na página **Configurar o complemento** que aparece, configure as seguintes configurações:

   - **Usuários atribuídos**: Selecione um dos seguintes valores:

     - **Todos** (padrão)
     - **Usuários/grupos específicos**
     - **Só eu**

   - **Método de implantação**: selecione um dos seguintes valores:

     - **Fixo (Padrão)**: o complemento é implantado automaticamente para os usuários especificados e eles não podem removê-lo.
     - **Disponível**: os usuários podem instalar o add-in em **Home** \> **Get add-ins** \> **Admin-managed**.
     - **Opcional**: o complemento é implantado automaticamente para os usuários especificados, mas eles podem optar por removê-lo.

   ![Configurar página de add-in](../../media/configure-add-in.png)

   Quando terminar, clique em **Implantar**.

8. Na página **Implantar Mensagem** de Relatório exibida, você verá um relatório de progresso seguido de uma confirmação de que o complemento foi implantado. Depois de ler as informações, clique em **Próximo**.

   ![Página Implantar Mensagem de Relatório](../../media/deploy-report-message-page.png)

9. Na página **Anunciar o** complemento que aparece, revise as informações e clique em **Fechar**.

   ![Anunciar página de complementos](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a>Saiba como usar o complemento Mensagem de Relatório

As pessoas que têm o complemento atribuído a eles verão os seguintes ícones:

- No Outlook, o ícone tem esta aparência:

  ![Ícone de adicionar mensagem de relatório para o Outlook](../../media/OutlookReportMessageIcon.png)

- No Outlook na Web, o ícone tem esta aparência:

  ![Ícone de Complemento de Mensagem de Relatório da Web do Outlook](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Quando você notificar os usuários sobre o complemento Mensagem de Relatório, inclua um link para Usar o [complemento Mensagem de Relatório](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>Revisar ou editar configurações do complemento Mensagem de Relatório

1. No Centro de administração do Microsoft 365, vá para a página Ir para a página Configurações de **Complementos** em , Se você não vir a Página de Adicionar, vá para o \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> link Configurações Integradas aplicativos Complementos  na parte superior da página Aplicativos  \>  \> **integrados.** 

   ![Página Serviços e Add-Ins no novo Centro de Administração do Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Encontre e selecione o complemento **Mensagem** de Relatório.

3. No flyout **Editar Relatório Mensagem** que aparece, revise e edite as configurações conforme apropriado para sua organização. Quando concluir, clique em **Salvar**.

   ![Configurações do complemento Mensagem de Relatório](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a>Exibir e revisar mensagens relatadas

Para revisar as mensagens relatadas pelos usuários à Microsoft, você tem estas opções:

- Use o portal Envios de Administrador. Para obter mais informações, consulte [Exibir envios de usuários para a Microsoft](admin-submission.md#view-user-submissions-to-microsoft).

- Crie uma regra de fluxo de emails (também conhecida como regra de transporte) para enviar cópias de mensagens relatadas. Para obter instruções, [consulte Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).
