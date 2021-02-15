---
title: Experiência da primeira execução com o piloto automático e a página de status do registro
description: Como implantar a experiência ESP, as configurações usadas e as alterações de configuração
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5e2340c7c0bf00165bb43740d3d095b5b0402fc0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126620"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a>Experiência da primeira execução com o piloto automático e a página de status do registro

A Área de Trabalho Gerenciada da Microsoft usa o [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot) e a Página de Status de Registro [(ESP)](https://docs.microsoft.com/windows/deployment/windows-autopilot/enrollment-status) do Microsoft Intune para fornecer a melhor experiência possível de primeira apresentação aos usuários.

A página Status do Registro está atualmente em visualização pública.

## <a name="initial-deployment"></a>Implantação inicial

Para fornecer a experiência ESP, você deve registrar dispositivos no serviço de Área de Trabalho Gerenciada da Microsoft. Para obter mais informações sobre registro, [consulte Registrar novos dispositivos por](../get-started/register-devices-self.md) conta própria ou etapas para parceiros [registrarem dispositivos.](../get-started/register-devices-partner.md)

Depois que seus dispositivos são registrados no serviço, você pode habilitar o ESP para seus dispositivos da Área de Trabalho Gerenciada da Microsoft, apresentando um tíquete de suporte por meio do [Portal de Administração.](https://portal.azure.com/) Implantaremos inicialmente a configuração esp no grupo teste quando você arquivar o tíquete. Ela é implantada nos outros grupos de implantação subsequentes (First, Fast e Broad) a cada 24 horas. Para pausar a implantação, arquiva outro tíquete solicitando que o Operations mantenha.

## <a name="autopilot-profile-settings"></a>Configurações de perfil do Autopilot

A Área de Trabalho Gerenciada da Microsoft usa essas configurações no perfil do Autopilot usado para os dispositivos dos usuários:


|Setting  |Valor  |
|---------|---------|
|Modo de implantação |  Orientado pelo usuário       |
|Ingressar no Azure AD como     |  Ingressado no Azure AD       |
|Idioma (Região)     | Padrão do sistema operacional        |
|Configurar automaticamente o teclado     | Não        |
|Termos de Licença para Software Microsoft     |  Ocultar       |
|Configurações de privacidade     | Ocultar        |
|Ocultar opções de alteração de conta     | Mostrar        |
|Tipo de conta de usuário     |  Padrão       |
|Permitir OOBE de White Glove     |  Sim       |
|Aplicar modelo de nome de dispositivo     | Sim        |
|Insira um nome     | MMD-%RAND:11%        |

> [!NOTE]
> Embora o provisionamento "ajuda branca" só seja habilitado para clientes com ESP ativado, ele não tem suporte no momento na Área de Trabalho Gerenciada da Microsoft.

## <a name="enrollment-status-page-settings"></a>Configurações da Página de Status do Registro

A Área de Trabalho Gerenciada da Microsoft usa estas configurações para a experiência da Página de Status do Registro:


|Setting  |Valor  |
|---------|---------|
|Mostrar progresso da configuração do aplicativo e do perfil     | Sim        |
|Mostrar um erro quando a instalação demorar mais do que o número especificado de minutos     |  60       |
|Mostrar mensagem personalizada quando ocorrer um erro de limite de tempo     |  Sim       |
|Mensagem de erro     | Sim, está demorando um pouco mais para configurar seu dispositivo do que o esperado. Clique abaixo para começar e concluiremos a configuração em segundo plano        |
|Permitir que os usuários coletem logs sobre erros de instalação     |  Sim       |
|Mostrar somente a página para dispositivos provisionados pela experiência inicial pelo usuário (OOBE)     | Sim        |
|Bloquear o uso de dispositivos até que todos os aplicativos e perfis sejam instalados     |  Sim       |
|Permitir que os usuários redefinir o dispositivo se ocorrer um erro de instalação     |  Sim       |
|Permitir que os usuários usem o dispositivo se ocorrer um erro de instalação     |  Sim       |
|Bloquear o uso de dispositivos até que esses aplicativos necessários sejam instalados se eles são atribuídos ao usuário/dispositivo     |  Modern Workplace - Correção de Tempo       |



A experiência da Página de Status do Registro ocorre em três fases. Para obter mais informações, [consulte Informações de controle da página de status do registro.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information)

A experiência continua da seguinte forma:

1. A experiência do Autopilot é iniciada e o usuário ins dá as credenciais.
2. O dispositivo abre a Página de Status do Registro e passa pelas fases de Preparação do Dispositivo e Configuração do Dispositivo. A terceira etapa (Configuração da *Conta)* atualmente é ignorada na configuração da Área de Trabalho Gerenciada da Microsoft porque o ESP do usuário está desabilitado. O dispositivo é reiniciado.
3. Após a reinicialização, o dispositivo abre a página de entrada do Windows com **Outro usuário.**
4. Os usuários insuem suas credenciais novamente e a área de trabalho é aberta.

> [!NOTE]
> Os aplicativos Win32 só são implantados durante ESP se a versão do Windows 10 for 1903 ou posterior.

![Página inicial da configuração do Autopilot mostrando as fases de "preparação do dispositivo" e "configuração do dispositivo".](../../media/mmd-autopilot-screenshot.png)

## <a name="white-glove-provisioning"></a>Provisionamento de mão branca

No momento, a Área de Trabalho Gerenciada da Microsoft não dá suporte ao recurso "ajuda branca" do Windows Autopilot.

## <a name="change-to-autopilot-and-enrollment-status-page-settings"></a>Alterar para as configurações do Autopilot e da Página de Status do Registro

Se a configuração usada pela Área de Trabalho Gerenciada da Microsoft não corresponder exatamente às suas necessidades, você poderá registrar um tíquete de suporte por meio do [Portal de Administração.](https://portal.azure.com/) Aqui estão alguns exemplos dos tipos de configuração que podem ser necessários:

### <a name="autopilot-settings-change"></a>Alteração das configurações do Autopilot

Talvez você queira solicitar um modelo de nome de dispositivo diferente. No entanto, você não pode alterar o modo de implantação, ingressar no Azure AD como, configurações de privacidade ou tipo de conta de usuário.

### <a name="enrollment-status-page-settings-change"></a>Alteração das configurações da Página de Status do Registro

- Um número maior de minutos para a configuração "Mostrar um erro quando a instalação demorar mais do que o número especificado de minutos".
- A mensagem de erro exibida
- Adicionar ou remover aplicativos na configuração "Bloquear uso do dispositivo até que esses aplicativos necessários sejam instalados se eles são atribuídos ao usuário/dispositivo".

## <a name="required-applications"></a>Aplicativos necessários

- Você deve direcionar aplicativos nos grupos de dispositivos *Test,* First, Fast e Broad do Modern Workplace. Os aplicativos devem ser instalados no contexto "Sistema". Certifique-se de concluir o teste com ESP no grupo teste antes de atribuí-los a todos os grupos.
- Nenhum aplicativo deve exigir que o dispositivo seja reiniciado. Recomendamos que os aplicativos sejam definidos como "Não fazer nada" ao criar o pacote de aplicativos se eles exigirem uma reinicialização.
- Limite os aplicativos necessários apenas aos principais aplicativos de que um usuário precisa imediatamente ao entrar no dispositivo.
- Mantenha o tamanho total de todos os aplicativos coletivamente abaixo de 1 GB para evitar tempos tempos máximos durante a fase de instalação do aplicativo.
- Idealmente, os aplicativos não devem ter nenhuma dependência. Se você tiver aplicativos que *devem* ter dependências, configure, teste e valide-os como parte de sua avaliação esp.
- Nenhum aplicativo que exige o contexto "usuário" (por exemplo, o Teams) pode ser incluído na visualização pública do ESP.
