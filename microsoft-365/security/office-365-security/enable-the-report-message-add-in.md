---
title: Habilitar o suplemento de Mensagem de Relatório
f1.keywords:
- NOCSH
ms.author: siosulli
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
description: Saiba como habilitar o complemento Mensagem de Relatório para o Outlook e o Outlook na Web, para usuários individuais ou toda a organização.
ms.openlocfilehash: 13721317c33cf207f27cd8b98fb6d32864651847
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2021
ms.locfileid: "49864990"
---
# <a name="enable-the-report-message-add-in"></a>Habilitar o suplemento de Mensagem de Relatório

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Se você for um administrador em uma organização do Microsoft 365 com caixas de correio do Exchange Online, recomendamos usar o portal Envios no Centro de Conformidade e Segurança & Segurança. Para obter mais informações, consulte Usar o Envio de Administrador [para enviar spam, phishing, URLs e arquivos suspeitos para a Microsoft.](admin-submission.md)

Os complementos De Relatório de Mensagens e Phishing do Outlook e do Outlook na Web (anteriormente conhecido como Outlook Web App) permitem que as pessoas reportem facilmente falsos positivos (emails bons marcados como ruins) ou falsos negativos (emails ruins permitidos) para a Microsoft e suas afiliadas para análise.

A Microsoft usa esses envios para melhorar a eficácia das tecnologias de proteção de email. Por exemplo, se as pessoas estão relatando muitas mensagens que foram sinalizadas como lixo eletrônico como Não é Lixo Eletrônico usando o complemento Mensagem de Relatório, a equipe de segurança da sua organização pode precisar ajustar as políticas [anti-spam.](configure-your-spam-filter-policies.md)

Você pode instalar o complemento Mensagem de Relatório ou Phishing de Relatório. Se você quiser que seus usuários reportem apenas mensagens de phishing, implante o complemento De relatório de phishing em sua organização. Para obter mais informações, [consulte Habilitar o complemento Phishing de Relatório.](enable-the-report-phish-add-in.md)

O complemento Mensagem de Relatório oferece a opção de relatar mensagens de spam e phishing. Os administradores podem habilitar o complemento Mensagem de Relatório para a organização, e usuários individuais podem instalá-lo por conta própria.

Se você for um usuário individual, poderá habilitar o complemento [Mensagem de Relatório para si mesmo.](#get-the-report-message-add-in-for-yourself)

Se você for um administrador global ou um administrador do Exchange Online e o Exchange estiver configurado para usar a autenticação OAuth, você poderá habilitar o complemento Mensagem de Relatório para [sua organização.](#get-and-enable-the-report-message-add-in-for-your-organization) A mensagem de Add-In relatório agora está disponível por meio [da Implantação Centralizada.](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- O complemento Mensagem de Relatório funciona com a maioria das assinaturas do Microsoft 365 e os seguintes produtos:

  - Outlook na Web
  - Outlook 2013 SP1 ou posterior
  - Outlook 2016 para Mac
  - Outlook incluído nos aplicativos do Microsoft 365 para Empresas

- O complemento Mensagem de Relatório não está disponível para caixas de correio em organizações locais do Exchange.

- Você pode configurar mensagens relatadas para serem copiadas ou redirecionadas para uma caixa de correio que você especificar. Para obter mais informações, consulte [Políticas de envios de usuário.](user-submission.md)

- Seu navegador da Web existente deve funcionar com o complemento Mensagem de Relatório. Porém, se você perceber que o complemento não está disponível ou não está funcionando conforme o esperado, tente outro navegador.

- Para as instalações organizacionais, a organização precisa ser configurada para usar a autenticação OAuth. Para obter mais informações, [consulte Determinar se a Implantação Centralizada de complementos funciona para sua organização.](../../admin/manage/centralized-deployment-of-add-ins.md)

- Os administradores precisam ser membros do grupo de funções Administradores globais. Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

## <a name="get-the-report-message-add-in-for-yourself"></a>Obter o complemento Mensagem de Relatório para você mesmo

1. Vá para o Microsoft AppSource em e procure o complemento <https://appsource.microsoft.com/marketplace/apps> Mensagem de Relatório. To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180> .

2. Clique **EM OBTER AGORA.**

   ![Mensagem de Relatório - Obter Agora](../../media/ReportMessageGETITNOW.png)

3. Na caixa de diálogo exibida, revise os termos de uso e a política de privacidade e clique em **Continuar.**

4. Entre usando sua conta comercial ou de estudante (para uso comercial) ou sua conta da Microsoft (para uso pessoal).

Depois que o complemento for instalado e habilitado, você verá os seguintes ícones:

- No Outlook, o ícone tem esta aparência:

  ![Ícone de add-in de Mensagem de Relatório para Outlook](../../media/OutlookReportMessageIcon.png)

- No Outlook na Web, o ícone tem esta aparência:

  ![Ícone do complemento Mensagem de Relatório do Outlook na Web](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Para saber como usar o complemento, confira [Usar o complemento Mensagem de Relatório.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>Obter e habilitar o complemento Mensagem de Relatório para sua organização

> [!NOTE]
> Pode levar até 12 horas para que o complemento apareça em sua organização.

1. No centro de administração do Microsoft 365, vá para **Configurações, aplicativos integrados &** página de & Em seguida, clique em Implantar <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> Um **Complemento.**

   ![Página de serviços e complementos no centro de administração do Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.

3. Na próxima página, clique **em Escolher na Loja.**

   ![Implantar uma nova página de complemento](../../media/NewAddInScreen2.png)

4. Na página Selecionar **add-in** exibida,  clique na caixa Pesquisar, insira  **Mensagem** de Relatório e clique no ícone ![ ](../../media/search-icon.png) Pesquisar. Na lista de resultados, encontre a **Mensagem de Relatório** e clique em **Adicionar.**

   ![Selecionar resultados de pesquisa de add-in](../../media/NewAddInScreen3.png)

5. Na caixa de diálogo exibida, revise as informações de licenciamento e privacidade e clique em **Continuar.**

6. Na página **Configurar o complemento** exibida, de configure as seguintes configurações:

   - **Usuários atribuídos:** selecione um dos seguintes valores:

     - **Todos** (padrão)
     - **Usuários/grupos específicos**
     - **Somente eu**

   - **Método de** implantação: selecione um dos seguintes valores:

     - **Corrigido (padrão)**: o complemento é implantado automaticamente para os usuários especificados e não pode removê-lo.
     - **Disponível:** os usuários podem instalar o add-in em **Home** \> **Get add-ins** \> **Admin-managed**.
     - **Opcional**: o complemento é implantado automaticamente para os usuários especificados, mas eles podem optar por removê-lo.

   ![Configurar página de add-in](../../media/configure-add-in.png)

   Quando terminar, clique em **Implantar.**

7. Na página **Implantar Mensagem de** Relatório exibida, você verá um relatório de progresso seguido de uma confirmação de que o complemento foi implantado. Depois de ler as informações, clique em **Próximo.**

   ![Página Implantar Mensagem de Relatório](../../media/deploy-report-message-page.png)

8. Na página **Anunciar o complemento** que aparece, revise as informações e clique em **Fechar.**

   ![Anunciar página de add-in](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a>Saiba como usar o complemento Mensagem de Relatório

As pessoas que têm o complemento atribuído a elas verão os seguintes ícones:

- No Outlook, o ícone tem esta aparência:

  ![Ícone de Relatório de Add-in de Mensagem para Outlook](../../media/OutlookReportMessageIcon.png)

- No Outlook na Web, o ícone tem esta aparência:

  ![Ícone de Aplicativo de Mensagem de Relatório do Outlook na Web](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Quando você notificar os usuários sobre o complemento Mensagem de Relatório, inclua um link para Usar o complemento [Mensagem de Relatório.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>Revisar ou editar configurações para o complemento Mensagem de Relatório

1. No centro de administração do Microsoft 365, vá para a página de & de **serviços** em <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> .

   ![Página Serviços e Add-Ins no novo Centro de Administração do Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Encontre e selecione o **complemento Mensagem** de Relatório.

3. No menu **desdolado** Editar Mensagem de Relatório exibido, revise e edite as configurações conforme apropriado para sua organização. Quando concluir, clique em **Salvar**.

   ![Configurações para o complemento Mensagem de Relatório](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a>Exibir e revisar mensagens relatadas

Para revisar as mensagens que os usuários relatam à Microsoft, você tem estas opções:

- Use o portal de Envios de Administrador. Para obter mais informações, [consulte Exibir envios de usuário para a Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)

- Crie uma regra de fluxo de emails (também conhecida como regra de transporte) para enviar cópias das mensagens relatadas. Para obter instruções, [confira Usar regras de fluxo de emails para ver o que seus usuários estão relatando à Microsoft.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)
