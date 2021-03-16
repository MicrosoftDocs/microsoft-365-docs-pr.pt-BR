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
ms.openlocfilehash: ddf13ef6627d70128064e2d8bd185203244b12e4
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819803"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>Apagar um dispositivo móvel em Mobilidade Básica e Segurança

Você pode usar o Basic Mobility and Security integrado para o Microsoft 365 para remover apenas informações organizacionais ou para executar uma redefinição de fábrica para excluir todas as informações de um dispositivo móvel e restaurá-la para as configurações de fábrica.

## <a name="before-you-begin"></a>Antes de começar

Dispositivos móveis podem armazenar informações organizacionais confidenciais e fornecer acesso aos recursos do Microsoft 365 da sua organização. Para ajudar a proteger as informações da sua organização, você pode redefinir Fábrica ou Remover dados da empresa:

- **Redefinição de** fábrica : exclui todos os dados no dispositivo móvel de um usuário, incluindo aplicativos instalados, fotos e informações pessoais. Quando a limpeza é concluída, o dispositivo é restaurado para suas configurações de fábrica.

- **Remover dados da** empresa : remove apenas dados da organização e deixa aplicativos, fotos e informações pessoais instalados no dispositivo móvel de um usuário.

- **Quando um dispositivo é apagado (Redefinição** de Fábrica ou Remover Dados da Empresa), o dispositivo é removido da lista de dispositivos gerenciados.
    
- **Redefinir** automaticamente um dispositivo : você pode configurar uma política básica de Mobilidade e Segurança que redefine automaticamente um dispositivo de fábrica depois que o usuário tenta inserir sem êxito a senha do dispositivo um número específico de vezes. Para fazer isso, siga as etapas em [Create device security policies in basic mobility and security](create-device-security-policies.md).
    
- **Se você quiser saber a experiência do usuário** ao apagar o dispositivo, confira Qual é o impacto do usuário e do   [dispositivo?](#whats-the-user-and-device-impact).

## <a name="wipe-a-mobile-device"></a>Apagar um dispositivo móvel

1. Vá para o Centro de administração [do Microsoft 365.](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)

2. Digite Gerenciamento de Dispositivo Móvel no campo de pesquisa e selecione Gerenciamento de Dispositivo **Móvel** na lista de resultados.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Opção de gerenciamento de dispositivo móvel Basic Mobility e Secruity":::

3. Selecione **Gerenciar dispositivos**.

4. Selecione o dispositivo que deseja apagar.

5. Selecione **Gerenciar**.

6. Selecione o tipo de apagamento remoto que deseja executar.

    - Para fazer uma limpeza completa e restaurar o dispositivo em suas configurações de fábrica, selecione **Redefinição de fábrica**.
    - Para fazer uma limpeza seletiva e excluir apenas informações da organização do Microsoft 365, selecione **Remover dados da empresa**.
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
|Os dados do aplicativo do Microsoft 365 serão apagados se o dispositivo estiver protegido pelas políticas de Proteção de Aplicativos do Intune. Os aplicativos não são removidos. Para dispositivos não protegidos por políticas de Gerenciamento de Aplicativo Móvel (MAM), o Outlook e o OneDrive não removerão dados armazenados em cache.<br/>**Observação** Para aplicar políticas de proteção do Aplicativo do Intune, você deve ter uma licença do Intune.|Sim|Sim|
|As configurações de política aplicadas pela Mobilidade Básica e Segurança a dispositivos não são mais impostas; os usuários podem alterar as configurações.|Sim|Sim|
|Os perfis de email criados pela Basic Mobility and Security são removidos e os emails armazenados em cache no dispositivo são excluídos.|Sim|N/D|
>[!NOTE]
>O aplicativo portal da empresa está disponível na App Store para iOS e na Play Store para dispositivos Android.

## <a name="related-topics"></a>Tópicos relacionados

[Configurar a Mobilidade Básica e a Segurança](set-up.md)
