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
description: Configurar a Mobilidade Básica e a Segurança para proteger e gerenciar os dispositivos móveis de seus usuários.
ms.openlocfilehash: 2f74307d41d83dd2e6fce2b68283ce0966e850e8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906235"
---
# <a name="set-up-basic-mobility-and-security"></a>Configurar a Mobilidade Básica e a Segurança

A Mobilidade Básica e Segurança Básica interna do Microsoft 365 ajuda você a proteger e gerenciar dispositivos móveis dos usuários, como iPhones, iPads, Androids e telefones Windows. Você pode criar e gerenciar políticas de segurança de dispositivo, apagar remotamente um dispositivo e exibir relatórios detalhados de dispositivos.

Have questions? Para que uma perguntas frequentes ajude a resolver perguntas comuns, consulte [Basic Mobility and Security Frequently-asked questions (Perguntas frequentes)](frequently-asked-questions.md). Esteja ciente de que não é possível usar uma conta de administrador delegada para gerenciar a Mobilidade Básica e a Segurança. Para obter mais informações, consulte [Parceiros: Oferecer administração delegada](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e). 

O gerenciamento de dispositivos faz parte do Centro de Conformidade & segurança, portanto, você precisará ir até lá para dar início à configuração básica de Mobilidade e Segurança.

## <a name="activate-the-basic-mobility-and-security-service"></a>Ativar o serviço de Mobilidade Básica e Segurança

1. Entre no Microsoft 365 com sua conta de administrador global.

2. Vá para [Ativar Mobilidade Básica e Segurança.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)

   Pode levar algum tempo para ativar o Basic Mobility and Security. Quando terminar, você receberá um email explicando as próximas etapas a serem seguidas.

## <a name="set-up-mobile-device-management"></a>Configurar o Gerenciamento de Dispositivo Móvel

Quando o serviço estiver pronto, conclua as etapas a seguir para concluir a instalação.

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a>Etapa 1: (Obrigatório) Configurar domínios para Mobilidade Básica e Segurança

Se você não tiver um domínio personalizado associado ao Microsoft 365 ou se não estiver gerenciando dispositivos Windows, poderá ignorar esta seção. Caso contrário, você precisará adicionar registros DNS para o domínio em seu host DNS. Se você já adicionou os registros, como parte da configuração do seu domínio com o Microsoft 365, você está definido. Depois de adicionar os registros, os usuários do Microsoft 365 em sua organização que se inscredem em seu dispositivo Windows com um endereço de email que usa seu domínio personalizado são redirecionados para se inscrever na Mobilidade Básica e Segurança.

Precisa de ajuda para configurar os registros? Encontre seu registrador de domínios e selecione o nome do registrador para ir para a ajuda passo a passo para criar o registro DNS na lista fornecida em Adicionar registros DNS para [conectar seu domínio](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider). Use essas instruções para criar registros CNAME descritos em Simplificar o [registro do Windows sem o Azure AD Premium](/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium).

Depois de adicionar os dois registros CNAME, volte para o Centro de Conformidade & Segurança e vá para Prevenção contra perda de dados Gerenciamento de dispositivos para concluir  >     a próxima etapa.

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>Etapa 2: (Obrigatório) Configurar um certificado APNs para dispositivos iOS

Para gerenciar dispositivos iOS como iPad e iPhones, você precisa criar um certificado APNs.

1. Entre no Microsoft 365 com sua conta de administrador global.

2. No tipo de navegador:  [https://protection.office.com](https://protection.office.com/) .

3. Selecione  **Prevenção contra perda de** dados Gerenciamento   >  **de** dispositivos e escolha Certificado **APNs para dispositivos iOS**.

4. Na página Configurações do Certificado de Notificação por Push da Apple, escolha **Avançar**.

5. Selecione **Baixar seu arquivo CSR** e salve a solicitação de assinatura de certificado em algum lugar no computador que você   lembrará. Selecione **Próximo**.

6. Na página Criar um certificado APNs:

   - Selecione Apple APNS Portal para abrir o Portal de Certificados push da Apple.
   - Sign in with an Apple ID.

     > [!IMPORTANT]
     > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

   - Selecione Criar um Certificado e aceite os Termos de Uso.
   - Navegue até a solicitação de assinatura de certificado que você baixou para o computador do Microsoft 365 e selecioneUpload.
   - Download the APN certificate created by the Apple Push Certificate Portal to your computer.

     > [!TIP]
     > If you're having trouble downloading the certificate, refresh your browser.

7. Volte para o Microsoft 365 e selecione **Next**.

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. Selecione  **Concluir**.

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>Etapa 3: (Recomendado) Configurar a autenticação multifa factor

O MFA ajuda a proteger a entrada no Microsoft 365 para registro de dispositivo móvel exigindo uma segunda forma de autenticação. Os usuários são obrigados a reconhecer uma chamada telefônica, mensagem de texto ou notificação de aplicativo em seu dispositivo móvel depois de inserir corretamente a senha da conta de trabalho. Eles podem registrar seu dispositivo somente após a conclusão dessa segunda forma de autenticação. Depois que os dispositivos de usuário são inscritos no Basic Mobility and Security, os usuários podem acessar recursos do Microsoft 365 com apenas sua conta de trabalho.

Para saber como ativar o MFA no portal do Azure AD, consulte [Configurar autenticação multifacional](../security-and-compliance/set-up-multi-factor-authentication.md).

Depois de configurar o MFA, volte para o Centro de Conformidade & Segurança e navegue até **Prevenção** contra perda de dados Políticas de dispositivo de gerenciamento de dispositivos para concluir   >     >  ****   a próxima etapa.

### <a name="step-4-recommended-manage-device-security-policies"></a>Etapa 4: (Recomendado) Gerenciar políticas de segurança de dispositivos

A próxima etapa é criar e implantar políticas de segurança de dispositivos para ajudar a proteger seus dados da organização do Microsoft 365. Por exemplo, você pode ajudar a evitar a perda de dados se um usuário perder seu dispositivo criando uma política para bloquear dispositivos após cinco minutos de inatividade e apagar dispositivos após três falhas de entrada.

1. Entre no Microsoft 365 com sua conta de administrador global.

2. Selecione [Ativar Gerenciamento de Dispositivo Móvel](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx). Se o serviço for ativado, em vez disso, as etapas de ativação você verá um link para [Gerenciar Dispositivos](https://admin.microsoft.com/adminportal/home#/MifoDevices)   .

3. Vá para **Políticas de dispositivo**.

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Configurações básicas de política de segurança e mobilidade":::

4. Crie e implante políticas de segurança de dispositivo apropriadas para sua organização seguindo as etapas em Criar políticas de segurança de [dispositivos em Basic Mobility and Security](create-device-security-policies.md).

> [!TIP]
>
> - Ao criar uma nova política, talvez você queira definir a política para permitir acesso e relatar violação de política em que um dispositivo de usuário não está em conformidade com a política. Isso permite ver quantos dispositivos móveis são afetados pela política sem bloquear o acesso ao Microsoft 365.
>
> - Antes de implantar uma nova política para todos em sua organização, recomendamos testá-la nos dispositivos usados por um pequeno número de usuários.
>
> - Além disso, antes de implantar políticas, deixe sua organização saber os possíveis impactos de registrar um dispositivo em Mobilidade Básica e Segurança. Dependendo de como você configura as políticas, dispositivos que não estão em conformidade com políticas (dispositivos não compatíveis) podem ser impedidos de acessar o Microsoft 365. Dispositivos não compatíveis também podem ter aplicativos instalados, fotos e outras informações pessoais que, em um dispositivo inscrito, podem ser excluídos se o dispositivo for apagado. Para obter mais informações, [consulte Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).

## <a name="make-sure-users-enroll-their-devices"></a>Certifique-se de que os usuários inscrevam seus dispositivos

Depois que você criou e implantou uma política de gerenciamento de dispositivo móvel, cada usuário licenciado do Microsoft 365 em sua organização que a política de dispositivo aplica recebe uma mensagem de registro na próxima vez que entrar no Microsoft 365 a partir de seu dispositivo móvel. Eles devem concluir as etapas de registro e ativação antes de acessar emails e documentos do Microsoft 365. Para obter mais informações, consulte [Registrar seu dispositivo móvel usando o Basic Mobility and Security](enroll-your-mobile-device.md).

> [!IMPORTANT]
> Se o idioma preferencial de um usuário não for suportado pelo processo de registro, os usuários poderão receber a notificação de registro e as etapas em seus dispositivos móveis em outro idioma. Nem todos os idiomas com suporte no Microsoft 365 têm suporte no momento para o processo de registro em dispositivos móveis.

Os usuários com dispositivos Android ou iOS são necessários para instalar o aplicativo Portal da Empresa como parte do processo de registro.

## <a name="related-topics"></a>Tópicos Relacionados

[Capacidades de Mobilidade e Segurança Básica](capabilities.md)<br/>
[Criar políticas de segurança de dispositivos em Mobilidade Básica e Segurança](create-device-security-policies.md)