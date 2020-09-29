---
title: Experiência de primeira execução com o AutoPilot e a página de status do registro
description: Como implantar a experiência de ESP, as configurações usadas e exceções
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 84656e2f0ae9d148c61c27af2a53e157cd44c171
ms.sourcegitcommit: e6283e7c32ba9628fc45e9abc5cd4d21fb3f7ca9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2020
ms.locfileid: "48299234"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a>Experiência de primeira execução com o AutoPilot e a página de status do registro

O Microsoft Managed desktop usa o [Windows AutoPilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot) e a página de status de registro do Microsoft INTUNE [(ESP)](https://docs.microsoft.com/windows/deployment/windows-autopilot/enrollment-status) para fornecer a melhor experiência de primeira execução para os seus usuários.

A página status do registro está atualmente em visualização pública.

## <a name="initial-deployment"></a>Implantação inicial

Para fornecer a experiência de ESP, você deve registrar dispositivos no serviço de área de trabalho gerenciada da Microsoft. Para saber mais sobre o registro, confira [registrar novos dispositivos](../get-started/register-devices-self.md) ou [as etapas de parceiros para registrar dispositivos](../get-started/register-devices-partner.md).

Depois que os dispositivos são registrados com o serviço, você pode habilitar o ESP para seus dispositivos de área de trabalho gerenciada da Microsoft, arquivando um tíquete de suporte através do [portal de administração](https://portal.azure.com/). Inicialmente, implantaremos a configuração de ESP no grupo de teste quando você arquivar o tíquete. Ele é implantado para os outros grupos de implantação subsequentes (primeiro, rápido e abrangente) a cada 24 horas. Para pausar a implantação, arquivo outro tíquete pedindo que as operações sejam mantidas.

## <a name="autopilot-profile-settings"></a>Configurações de perfil do AutoPilot

O Microsoft Managed desktop usa essas configurações no perfil do piloto automático usado para os dispositivos de seus usuários:


|Configuração  |Valor  |
|---------|---------|
|Modo de implantação |  Controlado pelo usuário       |
|Ingressar no Azure AD como     |  Azure AD Unido       |
|Idioma (região)     | Padrão do sistema operacional        |
|Configurar automaticamente o teclado     | Não        |
|Termos de licença para software Microsoft     |  Ocultar       |
|Configurações de privacidade     | Ocultar        |
|Ocultar opções de conta de alteração     | Mostrar        |
|Tipo de conta de usuário     |  Padrão       |
|Permitir branco Glove OOBE     |  Sim       |
|Aplicar modelo de nome do dispositivo     | Sim        |
|Insira um nome     | MMD-% RAND: 11%        |

> [!NOTE]
> Embora o rovisioning "branco Glove" seja habilitado apenas para clientes com ESP ativado, não há suporte para ele no momento na área de trabalho gerenciada da Microsoft.

## <a name="enrollment-status-page-settings"></a>Configurações da página de status do registro

O Microsoft Managed desktop usa estas configurações para a experiência de página de status de registro:


|Configuração  |Valor  |
|---------|---------|
|Mostrar progresso da configuração de aplicativo e perfil     | Sim        |
|Mostrar um erro quando a instalação levar mais tempo do que o número especificado de minutos     |  60       |
|Mostrar mensagem personalizada quando ocorre um erro de limite de tempo     |  Sim       |
|Mensagem de erro     | Sim, está demorando um pouco mais para configurar seu dispositivo do que o esperado. Clique abaixo para começar e terminaremos a configuração em segundo plano        |
|Permitir que os usuários coletem logs sobre erros de instalação     |  Sim       |
|Mostrar apenas a página para dispositivos configurados por experiência inicial (OOBE)     | Sim        |
|Bloquear o uso do dispositivo até que todos os aplicativos e perfis sejam instalados     |  Sim       |
|Permitir que os usuários redefinam o dispositivo se ocorrer erro de instalação     |  Sim       |
|Permitir que os usuários usem dispositivo se ocorrer erro de instalação     |  Sim       |
|Bloquear o uso do dispositivo até que estes aplicativos necessários sejam instalados se forem atribuídos ao usuário/dispositivo     |  Correção de tempo de trabalho moderna       |



A experiência da página de status do registro ocorre em três fases. Para saber mais, confira [informações de acompanhamento de página de status de registro](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information).

A experiência continua da seguinte maneira:

1. A experiência do AutoPilot começa e o usuário insere suas credenciais.
2. O dispositivo abre a página de status do registro e prossegue pelas fases de preparação do dispositivo e configuração do dispositivo. A terceira etapa (configuração da conta) é *ignorada no momento* na configuração da área de trabalho gerenciada da Microsoft porque o ESP do usuário está desabilitado. O dispositivo é reiniciado.
3. Após a reinicialização, o dispositivo abre a página de entrada do Windows com **outro usuário**.
4. Os usuários inserem suas credenciais novamente e a área de trabalho é aberta.

> [!NOTE]
> Os aplicativos Win32 são implantados somente durante o ESP se a versão do Windows 10 for 1903 ou posterior.

![Página inicial da configuração do AutoPilot mostrando as fases "preparação do dispositivo" e "instalação do dispositivo".](../../media/mmd-autopilot-screenshot.png)

## <a name="white-glove-provisioning"></a>Provisionamento de Glove branco

A área de trabalho gerenciada da Microsoft não suporta atualmente o recurso "White Glove" do Windows AutoPilot.

## <a name="exceptions"></a>Exceptions

Se a configuração usada pelo Microsoft Managed desktop não corresponder exatamente às suas necessidades, você poderá arquivar uma solicitação de exceção. Para fazer isso, confira detalhes na [solicitação de uma exceção](../service-description/customizing.md#request-an-exception). Estes são alguns exemplos dos tipos de exceções que você pode precisar:

### <a name="autopilot-exception"></a>Exceção do piloto automático

Você pode querer solicitar um modelo de nome de dispositivo diferente. No entanto, você não pode alterar o modo de implantação, ingressar no Azure como, configurações de privacidade ou tipo de conta de usuário.

### <a name="enrollment-status-page-exception"></a>Exceção da página de status do registro

- Um número maior de minutos para a configuração "mostrar um erro quando a instalação demorar mais do que o número especificado de minutos".
- A mensagem de erro exibida
- Adição ou remoção de aplicativos na configuração "bloquear o uso do dispositivo até que estes aplicativos necessários sejam instalados, se forem atribuídos ao usuário/dispositivo".

## <a name="required-applications"></a>Aplicativos necessários

- Você deve direcionar aplicativos nos grupos de *dispositivos* de área de trabalho moderna Test, First, Fast e amplo. Os aplicativos devem ser instalados no contexto "sistema". Certifique-se de concluir o teste com o ESP no grupo de teste antes de atribuí-los a todos os grupos.
- Nenhum aplicativo deve exigir que o dispositivo seja reiniciado. Recomendamos que os aplicativos sejam configurados como "não fazer nada" quando você criar o pacote de aplicativos, caso eles exijam uma reinicialização.
- Limitar os aplicativos necessários apenas aos aplicativos principais que um usuário precisa imediatamente ao entrar no dispositivo.
- Mantenha o tamanho total de todos os aplicativos coletivamente abaixo de 1 GB para evitar tempos limite durante a fase de instalação do aplicativo.
- O ideal é que os aplicativos não devam ter dependências. Se você tiver aplicativos que *precisam* ter dependências, configure, teste e valide-os como parte da sua avaliação de ESP.
- Nenhum aplicativo que exija o contexto "usuário" (por exemplo, o Teams) pode ser incluído na visualização pública do ESP.
