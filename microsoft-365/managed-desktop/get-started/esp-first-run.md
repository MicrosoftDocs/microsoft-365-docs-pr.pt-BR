---
title: Experiência da primeira execução com o piloto automático e a página de status do registro
description: Como implantar a experiência esp, as configurações usadas e as alterações de configuração
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: ec3758a2c452b5b20deab3b3776d631ebd48eaef
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921937"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a>Experiência da primeira execução com o piloto automático e a página de status do registro

A Área de Trabalho Gerenciada da Microsoft usa o [Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot) e a Página de Status de Registro [(ESP)](/windows/deployment/windows-autopilot/enrollment-status) do Microsoft Intune para oferecer a melhor experiência possível de primeira-executar para seus usuários.

A Página de Status do Registro está atualmente em visualização pública.

## <a name="initial-deployment"></a>Implantação inicial

Para fornecer a experiência do ESP, você deve registrar dispositivos no serviço de Área de Trabalho Gerenciada da Microsoft. Para obter mais informações sobre o registro, consulte [Registrar novos dispositivos por](../get-started/register-devices-self.md) conta própria ou Etapas para parceiros [registrarem dispositivos](../get-started/register-devices-partner.md).

Depois que seus dispositivos são registrados com o serviço, você pode habilitar o ESP para seus dispositivos da Área de Trabalho Gerenciada da Microsoft, arquivando um tíquete de suporte por meio do [Portal de Administração](https://portal.azure.com/). Implantaremos inicialmente a configuração do ESP no grupo Teste quando você arquivar o tíquete. Ele é implantado nos outros grupos de implantação subsequentes (First, Fast e Broad) a cada 24 horas. Para pausar a implantação, arquiva outro tíquete solicitando a ressarção de Operações.

## <a name="autopilot-profile-settings"></a>Configurações de perfil de piloto automático

A Área de Trabalho Gerenciada da Microsoft usa essas configurações no perfil do Piloto Automático usado para os dispositivos de seus usuários:


|Setting  |Valor  |
|---------|---------|
|Modo de implantação |  Orientado pelo usuário       |
|Ingressar no Azure AD como     |  Ingressou no Azure AD       |
|Idioma (Região)     | Selecionar usuário        |
|Configurar automaticamente o teclado     | Não        |
|Termos de Licença de Software da Microsoft     |  Ocultar       |
|Configurações de privacidade     | Ocultar        |
|Ocultar opções de conta de alteração     | Mostrar        |
|Tipo de conta de usuário     |  Padrão       |
|Permitir OOBE de Luva Branca     |  Sim       |
|Aplicar modelo de nome de dispositivo     | Sim        |
|Insira um nome     | MMD-%RAND:11%        |

## <a name="enrollment-status-page-settings"></a>Configurações da Página de Status do Registro

A Área de Trabalho Gerenciada da Microsoft usa essas configurações para a experiência da Página de Status de Registro:


|Setting  |Valor  |
|---------|---------|
|Mostrar o progresso da configuração do aplicativo e do perfil     | Sim        |
|Mostrar um erro quando a instalação leva mais tempo do que o número especificado de minutos     |  60       |
|Mostrar mensagem personalizada quando ocorrer erro de limite de tempo     |  Sim       |
|Mensagem de erro     | Sim, está demorando um pouco mais para configurar seu dispositivo do que o esperado. Clique abaixo para começar e terminaremos de configurar em segundo plano        |
|Permitir que os usuários coletem logs sobre erros de instalação     |  Sim       |
|Mostrar página somente para dispositivos provisionados pela experiência inicial (OOBE)     | Sim        |
|Bloquear o uso do dispositivo até que todos os aplicativos e perfis sejam instalados     |  Sim       |
|Permitir que os usuários redefinir o dispositivo se ocorrer um erro de instalação     |  Sim       |
|Permitir que os usuários usem o dispositivo se ocorrer um erro de instalação     |  Sim       |
|Bloquear o uso do dispositivo até que esses aplicativos necessários sejam instalados se eles são atribuídos ao usuário/dispositivo     |  Local de Trabalho Moderno - Correção de Tempo       |



A experiência da Página de Status de Registro ocorre em três fases. Para obter mais, consulte [Informações de controle da Página de Status de Registro.](/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information)

A experiência continua da seguinte forma:

1. A experiência do Piloto Automático é iniciada e o usuário inspeções suas credenciais.
2. O dispositivo abre a Página de Status de Registro e continua por meio das fases de Preparação do Dispositivo e Instalação do Dispositivo. A terceira etapa (Configuração de Conta) atualmente é ignorada na configuração da Área de Trabalho Gerenciada da Microsoft porque o ESP do usuário está desabilitado.  O dispositivo é reiniciado.
3. Após a reinicialização, o dispositivo abre a página de entrada do Windows com **Outro usuário**.
4. Os usuários insiram suas credenciais novamente e a área de trabalho será aberta.

> [!NOTE]
> Os aplicativos Win32 só serão implantados durante o ESP se a versão do Windows 10 for 1903 ou posterior.

![Página inicial da instalação do Autopilot mostrando as fases "preparação do dispositivo" e "configuração do dispositivo".](../../media/mmd-autopilot-screenshot.png)

## <a name="autopilot-for-pre-provisioned-deployment"></a>Piloto automático para implantação pré-provisionada
> [!NOTE]
> O piloto automático para implantação pré-provisionada na Área de Trabalho Gerenciada da Microsoft está atualmente em visualização pública.

## <a name="additional-prerequisites-for-autopilot-for-pre-provisioned-deployment"></a>Pré-requisitos adicionais para o Autopilot para implantação pré-provisionada
- Você deve ter a Página de Status do Registro (ESP) habilitada. Para obter mais informações, consulte [Implantação inicial](#initial-deployment).
- O dispositivo deve ter uma conexão de rede com fio.
- Se você tiver dispositivos que foram registrados usando o portal da Área de Trabalho Gerenciada da Microsoft antes de agosto de 2020, registre-os e registre-os novamente.
- Os dispositivos devem ter uma imagem de fábrica que inclua a atualização cumulativa de novembro de 2020 [19H1/19H2 2020.11C](https://support.microsoft.com/topic/november-19-2020-kb4586819-os-builds-18362-1237-and-18363-1237-preview-25cbb849-74af-b8b8-29b8-68aa925e8cc3) ou [20H1 2020.11C,](https://support.microsoft.com/topic/november-30-2020-kb4586853-os-builds-19041-662-and-19042-662-preview-8fb07fb8-a7dd-ea62-d65e-3305da09f92e) conforme apropriado instalado ou deve ser reimagnado com a imagem mais recente da Área de Trabalho Gerenciada da Microsoft.
- Os dispositivos físicos devem dar suporte ao TPM 2.0 e ao atestado de dispositivo. Não há suporte para máquinas virtuais. O processo de pré-provisionamento usa recursos de auto-implantação do Windows Autopilot, portanto, o TPM 2.0 é necessário. O processo de atestado do TPM também requer acesso a um conjunto de URLs HTTPS que são exclusivas para cada provedor TPM. Para obter mais informações, consulte a entrada para o modo de auto-implantação do Autopilot e a implantação pré-provisionada do Autopilot nos requisitos de [rede do Windows Autopilot.](https://docs.microsoft.com/mem/autopilot/networking-requirements#tpm)

## <a name="sequence-of-events-in-autopilot-for-pre-provisioned-deployment"></a>Sequência de eventos no Piloto Automático para implantação pré-provisionada
1. O administrador de IT reimaja ou redefine o dispositivo, se necessário.
2. O administrador de IT inicializa o dispositivo, atinge a experiência fora da caixa de correio e pressiona a tecla do Windows cinco vezes.
3. O administrador de IT seleciona o Provisionamento do Windows Autopilot e seleciona **Continuar**. Na tela de configuração do Windows Autopilot, serão exibidas informações sobre o dispositivo.
5. O administrador de IT seleciona **Provisionar** para iniciar o processo de provisionamento.
6. O dispositivo inicia o ESP e passa pelas fases de preparação e instalação do dispositivo. Durante a fase de configuração do dispositivo, você verá a instalação do aplicativo **x de x** exibida (dependendo da configuração exata do perfil ESP).
7. A etapa de configuração da conta atualmente é ignorada na configuração da Área de Trabalho Gerenciada da Microsoft, pois desabilitaremos o USER ESP.
8. O dispositivo é reiniciado.

Depois que ele for reiniciado, o dispositivo mostrará a tela de status verde, com um **botão Reseal.**

> [!IMPORTANT]
> Problemas conhecidos : 
> - O ESP não é executado novamente após o Autopilot para a função de reseal de implantação pré-provisionada.
> - O dispositivo não está sendo renomeado pelo Autopilot para implantação pré-provisionada. O dispositivo só será renomeado depois de passar pelo fluxo de usuários esp.


## <a name="change-to-autopilot-and-enrollment-status-page-settings"></a>Alterar para Configurações da Página de Status do Piloto Automático e do Registro

Se a configuração usada pela Área de Trabalho Gerenciada da Microsoft não corresponder exatamente às suas necessidades, você poderá registrar um tíquete de suporte por meio do [Portal de Administração](https://portal.azure.com/). Aqui estão alguns exemplos dos tipos de configuração que você pode precisar:

### <a name="autopilot-settings-change"></a>As configurações do piloto automático mudam

Talvez você queira solicitar um modelo de nome de dispositivo diferente. No entanto, não é possível alterar o Modo de Implantação, Ingressar no Azure AD Como, Configurações de Privacidade ou Tipo de Conta de Usuário.

### <a name="enrollment-status-page-settings-change"></a>Alterações nas configurações da Página de Status de Registro

- Um número maior de minutos para a configuração "Mostrar um erro quando a instalação leva mais tempo do que o número especificado de minutos".
- A mensagem de erro exibida
- Adicionar ou remover aplicativos na configuração "Bloquear o uso do dispositivo até que esses aplicativos necessários sejam instalados se eles são atribuídos ao usuário/dispositivo".

## <a name="required-applications"></a>Aplicativos necessários

- Você deve direcionar aplicativos nos grupos de dispositivos Locais *de* Trabalho Modernos Teste, Primeiro, Rápido e Amplo. Os aplicativos devem ser instalados no contexto "Sistema". Certifique-se de concluir o teste com o ESP no grupo Teste antes de atribuí-los a todos os grupos.
- Nenhum aplicativo deve exigir que o dispositivo seja reiniciado. Recomendamos que os aplicativos sejam definidos como "Não fazer nada" quando você criar o pacote de aplicativos se eles exigirem uma reinicialização.
- Limite os aplicativos necessários apenas para os aplicativos principais que um usuário precisa imediatamente ao entrar no dispositivo.
- Mantenha o tamanho total de todos os aplicativos coletivamente abaixo de 1 GB para evitar tempos-de-tempo durante a fase de instalação do aplicativo.
- O ideal é que os aplicativos não tenham dependências. Se você tiver aplicativos que *devem* ter dependências, configure, teste e valide-os como parte da avaliação do ESP.
- Nenhum aplicativo que exige o contexto "usuário" (por exemplo, o Teams) pode ser incluído na visualização pública do ESP.