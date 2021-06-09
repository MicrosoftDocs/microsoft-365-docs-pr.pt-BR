---
title: Apagar um dispositivo móvel em Mobilidade Básica e Segurança
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
description: Use o Basic Mobility and Security integrado para remover informações de dispositivos inscritos.
ms.openlocfilehash: 8c873923505fe527f5a44df0e8b15d290e92023b
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706137"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>Apagar um dispositivo móvel em Mobilidade Básica e Segurança

Você pode usar o Basic Mobility and Security integrado para Microsoft 365 remover apenas informações organizacionais ou para executar uma redefinição de fábrica para excluir todas as informações de um dispositivo móvel e restaurá-la para as configurações de fábrica.

## <a name="before-you-begin"></a>Antes de começar

Os dispositivos móveis podem armazenar informações organizacionais confidenciais e fornecer acesso aos recursos Microsoft 365 da sua organização. Para ajudar a proteger as informações da sua organização, você pode redefinir Fábrica ou Remover dados da empresa:

- **Redefinição de** fábrica : exclui todos os dados no dispositivo móvel de um usuário, incluindo aplicativos instalados, fotos e informações pessoais. Quando a limpeza é concluída, o dispositivo é restaurado para suas configurações de fábrica.

- **Remover dados da** empresa : remove apenas dados da organização e deixa aplicativos, fotos e informações pessoais instalados no dispositivo móvel de um usuário.

- **Quando um dispositivo é apagado (Redefinição** de Fábrica ou Remover Dados da Empresa), o dispositivo é removido da lista de dispositivos gerenciados.
    
- **Redefinir** automaticamente um dispositivo : você pode configurar uma política básica de Mobilidade e Segurança que redefine automaticamente um dispositivo de fábrica depois que o usuário tenta inserir sem êxito a senha do dispositivo um número específico de vezes. Para fazer isso, siga as etapas em [Create device security policies in basic mobility and security](create-device-security-policies.md).
    
- **Se você quiser saber a experiência do usuário** ao apagar o dispositivo, confira Qual é o impacto do usuário e do   [dispositivo?](#whats-the-user-and-device-impact).

## <a name="wipe-a-mobile-device"></a>Apagar um dispositivo móvel

1. Vá para o centro [de administração Microsoft 365.](../../admin/admin-overview/about-the-admin-center.md)

2. Digite Gerenciamento de Dispositivo Móvel no campo de pesquisa e selecione Gerenciamento de Dispositivo **Móvel** na lista de resultados.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Opção de gerenciamento de dispositivo móvel Basic Mobility e Secruity":::

3. Selecione **Gerenciar dispositivos**.

4. Selecione o dispositivo que deseja apagar.

5. Selecione **Gerenciar**.

6. Selecione o tipo de apagamento remoto que deseja executar.

    - Para fazer uma limpeza completa e restaurar o dispositivo em suas configurações de fábrica, selecione **Redefinição de fábrica**.
    - Para fazer uma limpeza seletiva e excluir apenas Microsoft 365 informações da organização, selecione **Remover dados da empresa**.
    - Para remover o dispositivo da sua organização, selecione **Remover dispositivo**.

7. Selecione **Sim** para confirmar.

## <a name="how-do-i-know-it-worked"></a>Como saber se funcionou?

Você não verá mais o dispositivo móvel na lista de dispositivos gerenciados.

## <a name="why-would-you-want-to-wipe-a-device"></a>Por que você deseja apagar um dispositivo?

Limpe um dispositivo por esses motivos:

- Dispositivos móveis, como smartphones e tablets, estão se tornando mais completos o tempo todo. Isso significa que é mais fácil para seus usuários armazenar informações corporativas confidenciais, como identificação pessoal ou comunicações confidenciais e acessá-la em qualquer lugar. Se um desses dispositivos móveis for perdido ou roubado, a limpeza do dispositivo poderá ajudar a impedir que as informações da sua organização terminam em mãos erradas.
- Quando um usuário sai da organização com um dispositivo pessoal que está inscrito em Mobilidade Básica e Segurança, você pode ajudar a impedir que informações organizacionais vão com esse usuário executando uma redefinição de fábrica.
- Se sua organização fornece dispositivos móveis aos usuários, talvez seja necessário reatribuir dispositivos de vez em quando. Fazer uma Redefinição de Fábrica em um dispositivo antes de atribuí-lo a um novo usuário ajuda a garantir que todas as informações confidenciais do proprietário anterior são excluídas.

## <a name="whats-the-user-and-device-impact"></a>Qual é o impacto do usuário e do dispositivo?

O apagamento é enviado imediatamente para o dispositivo móvel e o dispositivo é marcado como não compatível no Azure active directory. Embora todos os dados são removidos quando um dispositivo é redefinido para os padrões de fábrica, a tabela a seguir descreve qual conteúdo é removido para cada tipo de dispositivo quando um dispositivo quando você remove dados da empresa.

|**Impacto no conteúdo**|**iOS 10 e posterior**|**Android 5 e posterior**|
|:-----|:-----|:-----|
|Microsoft 365 dados do aplicativo serão apagados se o dispositivo estiver protegido pelas políticas de Proteção de Aplicativos do Intune. Os aplicativos não são removidos. Para dispositivos não protegidos por políticas de Gerenciamento de Aplicativo Móvel (MAM), Outlook e OneDrive não removerão dados armazenados em cache.<br/>**Observação** Para aplicar políticas de proteção do Aplicativo do Intune, você deve ter uma licença do Intune.|Sim|Sim|
|As configurações de política aplicadas pela Mobilidade Básica e Segurança a dispositivos não são mais impostas; os usuários podem alterar as configurações.|Sim|Sim|
|Os perfis de email criados pela Basic Mobility and Security são removidos e os emails armazenados em cache no dispositivo são excluídos.|Sim|N/D|
>[!NOTE]
>Portal da Empresa app está disponível na App Store para iOS e na Play Store para dispositivos Android.
