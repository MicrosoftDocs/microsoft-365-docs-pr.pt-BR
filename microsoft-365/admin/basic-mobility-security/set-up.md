---
title: Configurar a Mobilidade Básica e a Segurança
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Configurar o Basic Mobility and Security para proteger e gerenciar os dispositivos móveis dos usuários.
ms.openlocfilehash: 38f122141b370468bc591df49b3e1891a8a66a43
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876859"
---
# <a name="set-up-basic-mobility-and-security"></a>Configurar a Mobilidade Básica e a Segurança

O Basic Mobility and Security integrado para o Microsoft 365 ajuda você a proteger e gerenciar dispositivos móveis dos usuários, como iPhones, iPads, Androids e telefones Windows. Você pode criar e gerenciar políticas de segurança de dispositivo, apagar remotamente um dispositivo e exibir relatórios detalhados de dispositivos.

Have questions? Para perguntas frequentes para ajudar a resolver perguntas comuns, consulte Perguntas frequentes sobre mobilidade básica e [segurança.](frequently-asked-questions.md) Esteja ciente de que você não pode usar uma conta de administrador delegada para gerenciar a Mobilidade Básica e Segurança. Para obter mais informações, consulte [Parceiros: oferecer administração delegada.](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e) 

O gerenciamento de dispositivos faz parte do Centro de Conformidade e Segurança &, portanto, você precisará ir lá para dar início à configuração básica de Mobilidade e Segurança.

## <a name="activate-the-basic-mobility-and-security-service"></a>Ativar o serviço Básico de Mobilidade e Segurança

1. Entre no Microsoft 365 com sua conta de administrador global.

2. Vá para [Ativar Mobilidade Básica e Segurança.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)

   Pode levar algum tempo para ativar o Basic Mobility and Security. Quando terminar, você receberá um email explicando as próximas etapas a serem seguidas.

## <a name="set-up-mobile-device-management"></a>Configurar o gerenciamento de dispositivos móveis

Quando o serviço estiver pronto, conclua as etapas a seguir para concluir a instalação.

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a>Etapa 1: (Obrigatório) Configurar domínios para Mobilidade Básica e Segurança

Se você não tiver um domínio personalizado associado ao Microsoft 365 ou se não estiver gerenciando dispositivos Windows, ignore esta seção. Caso contrário, você precisará adicionar registros DNS para o domínio em seu host DNS. Se você já tiver adicionado os registros, como parte da configuração do seu domínio com o Microsoft 365, tudo está definido. Depois que você adicionar os registros, os usuários do Microsoft 365 em sua organização que entrarem em seus dispositivos Windows com um endereço de email que usa seu domínio personalizado serão redirecionados para se inscrever na Mobilidade Básica e Segurança.

Precisa de ajuda para configurar os registros? Encontre seu registrador de domínios e selecione o nome do registrador para ir para a ajuda passo a passo para criar um registro DNS na lista fornecida em Adicionar registros DNS para [conectar seu domínio.](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) Use essas instruções para criar registros CNAME descritos em Simplificar o [registro do Windows sem o Azure AD Premium.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)

Depois de adicionar os dois registros CNAME, volte para o Centro de Conformidade e Segurança & e vá para o Gerenciamento de dispositivos de prevenção contra perda de dados para concluir a  >     próxima etapa.

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>Etapa 2: (Obrigatório) Configurar um certificado APNs para dispositivos iOS

Para gerenciar dispositivos iOS como iPad e iPhones, você precisa criar um certificado APNs.

1. Entre no Microsoft 365 com sua conta de administrador global.

2. No seu tipo de navegador:  [https://protection.office.com](https://protection.office.com/) .

3. Selecione  **Prevenção contra perda de** dados Gerenciamento   >  **de** dispositivos e escolha Certificado **APNs para dispositivos iOS.**

4. Na página Configurações do Certificado de Notificação por Push da Apple, escolha **Avançar.**

5. Selecione **Baixar seu arquivo CSR e** salve a solicitação de assinatura de certificado em algum lugar do computador que você   lembrará. Selecione **Next**.

6. Na página Criar um certificado APNs:

   - Selecione o Apple APNS Portal para abrir o Apple Push Certificates Portal.
   - Sign in with an Apple ID.

     > [!IMPORTANT]
     > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

   - Selecione Criar um Certificado e aceite os Termos de Uso.
   - Navegue até a solicitação de assinatura de certificado que você baixou para seu computador do Microsoft 365 e selectUpload.
   - Download the APN certificate created by the Apple Push Certificate Portal to your computer.

     > [!TIP]
     > If you're having trouble downloading the certificate, refresh your browser.

7. Volte para o Microsoft 365 e selecione **Next**.

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. Selecione  **Concluir**.

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>Etapa 3: (Recomendado) Configurar a autenticação multifa factor

A MFA ajuda a proteger a entrada no Microsoft 365 para registro de dispositivo móvel, exigindo uma segunda forma de autenticação. Os usuários são obrigados a confirmar uma chamada telefônica, uma mensagem de texto ou uma notificação de aplicativo em seu dispositivo móvel depois de inserir corretamente a senha da conta de trabalho. Eles só poderão registrar seu dispositivo depois que essa segunda forma de autenticação for concluída. Depois que os dispositivos do usuário são inscritos no Basic Mobility and Security, os usuários podem acessar os recursos do Microsoft 365 apenas com sua conta corporativa.

Para saber como ativar a MFA no portal do Azure AD, confira Configurar a [autenticação multifacional.](https://go.microsoft.com/fwlink/p/?LinkId=519255)

Depois de configurar a MFA, volte para o Centro **** de Conformidade e Segurança & e navegue até Prevenção contra perda de dados Políticas de dispositivo de gerenciamento de dispositivos para concluir   >     >  ****   a próxima etapa.

### <a name="step-4-recommended-manage-device-security-policies"></a>Etapa 4: (Recomendado) Gerenciar políticas de segurança de dispositivos

A próxima etapa é criar e implantar políticas de segurança de dispositivos para ajudar a proteger os dados da sua organização do Microsoft 365. Por exemplo, você pode ajudar a evitar a perda de dados se um usuário perder o dispositivo criando uma política para bloquear dispositivos após cinco minutos de inatividade e apagar dispositivos após três falhas de entrada.

1. Entre no Microsoft 365 com sua conta de administrador global.

2. Selecione [Ativar Gerenciamento de Dispositivo Móvel.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx) Se o serviço estiver ativado, as etapas de ativação você verá um link para [Gerenciar Dispositivos.](https://admin.microsoft.com/adminportal/home#/MifoDevices)  

3. Vá para Políticas **de dispositivo.**

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Configurações de política básica de segurança e mobilidade":::

4. Crie e implante políticas de segurança de dispositivo apropriadas para sua organização seguindo as etapas em Criar políticas de segurança de [dispositivos em Mobilidade e Segurança Básica.](create-device-security-policies.md)

> [!TIP]
>
> - Ao criar uma nova política, talvez você queira definir a política para permitir o acesso e relatar a violação da política em que um dispositivo de usuário não está em conformidade com a política. Isso permite que você veja quantos dispositivos móveis são afetados pela política sem bloquear o acesso ao Microsoft 365.
>
> - Antes de implantar uma nova política para todos em sua organização, recomendamos testá-la nos dispositivos usados por um pequeno número de usuários.
>
> - Além disso, antes de implantar políticas, deixe sua organização saber os possíveis impactos de registrar um dispositivo em Mobilidade e Segurança Básica. Dependendo de como você configurar as políticas, os dispositivos que não estão em conformidade com políticas (dispositivos não compatíveis) podem ser impedidos de acessar o Microsoft 365. Dispositivos não compatíveis também podem ter aplicativos instalados, fotos e outras informações pessoais que, em um dispositivo inscrito, podem ser excluídos se o dispositivo for apagado. Para obter mais informações, [consulte Apagar um dispositivo móvel em Mobilidade Básica e Segurança.](wipe-mobile-device.md)

## <a name="make-sure-users-enroll-their-devices"></a>Certifique-se de que os usuários inscrevam seus dispositivos

Depois de criar e implantar uma política de gerenciamento de dispositivo móvel, cada usuário licenciado do Microsoft 365 em sua organização que a política de dispositivo aplicar receberá uma mensagem de registro na próxima vez que entrar no Microsoft 365 a partir de seu dispositivo móvel. Eles devem concluir as etapas de inscrição e ativação antes de acessar o email e os documentos do Microsoft 365. Para obter mais informações, consulte [Registrar seu dispositivo móvel usando Mobilidade Básica e Segurança.](enroll-your-mobile-device.md)

> [!IMPORTANT]
> Se o idioma preferencial de um usuário não for compatível com o processo de inscrição, os usuários poderão receber a notificação de registro e as etapas em seus dispositivos móveis em outro idioma. No momento, nem todos os idiomas compatíveis com o Microsoft 365 têm suporte para o processo de inscrição em dispositivos móveis.

Os usuários com dispositivos Android ou iOS são obrigados a instalar o aplicativo Portal da Empresa como parte do processo de inscrição.

## <a name="related-topics"></a>Tópicos Relacionados

[Capacidades de Mobilidade e Segurança Básica](capabilities.md)<br/>
[Criar políticas de segurança de dispositivos em Mobilidade Básica e Segurança](create-device-security-policies.md)