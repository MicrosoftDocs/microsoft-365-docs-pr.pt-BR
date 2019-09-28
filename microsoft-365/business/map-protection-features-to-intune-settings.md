---
title: Como os recursos de proteção no Microsoft 365 Business mapeiam para as configurações do Intune
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 8/13/2018
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: aad21b1a-c775-469a-b89c-c5d1d59d27db
description: Saiba como os recursos de proteção no Microsoft 365 Business MAP para o Intune Settings. A assinatura fornece a você uma licença para modificar as configurações do Intune.
ms.openlocfilehash: 316dc8efbe69057f049bf8fadd3c3f41c358a33e
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287946"
---
# <a name="how-do-protection-features-in-microsoft-365-business-map-to-intune-settings"></a>Como os recursos de proteção no Microsoft 365 Business mapeiam para as configurações do Intune

## <a name="android-and-ios-application-protection-settings"></a>Configurações de proteção de aplicativos para iOS e Android

A tabela a seguir fornece detalhes sobre como as configurações de política de aplicativos para Android e iOS são mapeadas para as configurações do Intune.
  
Para localizar a configuração do Intune, enquanto estiver conectado com suas credenciais de administrador do Microsoft 365 Business, vá para **centros de administração**e, em seguida, **Intune**.
  
 **Importante:** Uma assinatura do Microsoft 365 Business fornece uma licença para modificar todas as configurações do Intune. Confira [introdução ao Intune para começar.](https://docs.microsoft.com/intune/introduction-intune)
  
Clique no nome da Política que você deseja selecionar (por exemplo, Política de aplicativo para Android) e escolha **Configurações de política**.
  
Em **Proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados**
  
|**Configuração de política de aplicativo do Android ou do iOS**|**Configuração(ões) do Intune**|
|:-----|:-----|
|Excluir arquivos de trabalho de um dispositivo inativo após  <br/> |Intervalo offline (dias) antes que os dados do aplicativo sejam apagados  <br/> |
|Forçar usuários a salvar arquivos de trabalho no OneDrive for Business  <br/> Observe que apenas o OneDrive Pro é permitido  <br/> |Selecione em quais serviços de armazenamento os dados corporativos podem ser salvos  <br/> |
|||
   
Em **Gerenciar como o usuário acessa arquivos do Office em dispositivos móveis**
  
|**Configuração de política de aplicativo do Android ou do iOS**|**Configuração(ões) do Intune**|
|:-----|:-----|
|Excluir arquivos de trabalho de um dispositivo inativo após  <br/> |Intervalo offline (dias) antes que os dados do aplicativo sejam apagados  <br/> |
|Forçar usuários a salvar arquivos de trabalho no OneDrive for Business  <br/> Observe que apenas o OneDrive Pro é permitido  <br/> |Selecione em quais serviços de armazenamento os dados corporativos podem ser salvos  <br/> |
|Criptografar arquivos de trabalho  <br/> |Criptografar dados de aplicativo  <br/> |
|Em **Gerenciar como o usuário acessa arquivos do Office em dispositivos móveis** <br/> ||
|Exigir um PIN ou uma impressão digital para acessar aplicativos do Office  <br/> | Exigir PIN para acessar  <br/>  Isso também define:  <br/> **Permitir PIN simples** como **Sim** <br/> **Comprimento do Pin** como 4  <br/> **Permitir impressões digitais em vez de PIN** como **Sim** <br/> **Desabilitar PIN do aplicativo quando o PIN do dispositivo é gerenciado** como **Não** <br/> |
|Redefinir PIN quando o logon falhar por este número de vezes (essa opção será desabilitada se o PIN não for necessário)  <br/> |Número de tentativas antes de redefinir o PIN  <br/> |
|Exigir que os usuários entrem novamente depois que os aplicativos do Office ficarem ociosos (essa opção será desabilitada se o PIN não for necessário)  <br/> | Verificar novamente os requisitos de acesso após (minutos)  <br/>  Isso também define:  <br/> **Tempo limite** é definido como minutos  <br/>  Esse é o mesmo número de minutos que você definiu no Microsoft 365 Business.  <br/> **Período de cortesia offline** é definido como 720 minutos por padrão  <br/> |
|Negar o acesso aos arquivos de trabalho em dispositivos com jailbreak ou com acesso raiz  <br/> |Bloquear a execução de aplicativos gerenciados em dispositivos com jailbreak ou com acesso raiz  <br/> |
|Permitir que os usuários copiem o conteúdo dos aplicativos do Office para os aplicativos pessoais  <br/> | Restringir recortar, copiar e colar com outros aplicativos  <br/>  Se a opção Microsoft 365 Business for definida como **Ativada**, estas três opções também serão definidas como **Todos os Aplicativos** no Intune:  <br/> **Permitir que o aplicativo transfira dados para outros aplicativos** <br/> **Permitir que o aplicativo receba dados de outros aplicativos** <br/> **Restringir recortar, copiar e colar com outros aplicativos** <br/>  Se a opção Microsoft 365 Business for definida como **Ativada**, todas as opções do Intune serão configuradas como:  <br/> **Permitir que o aplicativo transfira dados para outros aplicativos** é definida como **Aplicativos gerenciados por política** <br/> **Permitir que o aplicativo receba dados de outros aplicativos** é definida como **Todos os Aplicativos** <br/> **Restringir recortar, copiar e colar com outros aplicativos** é definida como **Aplicativos gerenciados por política com Colar** <br/> |
|||
   
## <a name="windows-10-app-protection-settings"></a>Configurações de proteção de aplicativos do Windows 10

A tabela a seguir fornece detalhes sobre como as configurações de política de aplicativos do Windows 10 são mapeadas para as configurações do Intune.
  
Para localizar a configuração do Intune, enquanto estiver conectado com suas credenciais de administrador do Microsoft 365 Business, vá para [portal do Azure](https://portal.azure.com)e, em seguida, selecione **mais serviços**e digite o Intune no **filtro**, selecione **proteção** \> **de aplicativos do Intune Política de aplicativos**.
  
 **Importante**: Uma assinatura do Microsoft 365 Business fornece a você uma licença para modificar apenas as configurações do Intune que são mapeadas para as configurações disponíveis no Microsoft 365 Business. 
  
Clique no nome de política que você deseja selecionar e escolha **Geral, Atribuições**, **Aplicativos permitidos**, **Isentar aplicativos**, **Configurações necessárias** ou **Configurações avançadas** no painel de navegação esquerdo para explorar as configurações disponíveis. 
  
|**Configuração de política de aplicativo do Windows 10**|**Configuração(ões) do Intune**|
|:-----|:-----|
|Criptografar arquivos de trabalho  <br/> |**Configurações avançadas** \> **Proteção de dados**: **Revogar chaves de criptografia ao cancelar registro** e **Revogar acesso a dados protegidos quando o dispositivo é registrado no MDM** são definidas como **Ativadas**.  <br/> |
|Impedir que os usuários copiem dados da empresa para arquivos pessoais.  <br/> |**Configurações necessárias** \> **Modo de Proteção de Informações do Windows**. **Ativado** no Microsoft 365 Business é mapeado para: **Ocultar Substituições**, **Desativado** no Microsoft 365 Business é mapeado para: **Desativado**.  <br/> |
|Controle de acesso a documentos do Office  <br/> | Se for definido como **Ativado** no Microsoft 365 Business,  <br/> **Configurações avançadas** \> **Acesso**, **Usar Windows Hello for Business como um método para entrar no Windows** estará definido como **Ativado**, com as seguintes configurações adicionais:  <br/> **Definir o número mínimo de caracteres necessários para o PIN** é definido como **4**.  <br/> **Configurar o uso de letras maiúsculas no PIN do Windows Hello for Business** é definido como **Não permitir o uso de letras maiúsculas no PIN**.  <br/> **Configurar o uso de letras minúsculas no PIN do Windows Hello for Business** é definido como **Não permitir o uso de letras minúsculas no PIN**.  <br/> **Configurar o uso de caracteres especiais no PIN do Windows Hello for Business** é definido como **Não permitir o uso de caracteres especiais no PIN**.  <br/> **Especificar o período de tempo (em dias) pelo qual um PIN pode ser usado antes que o sistema exija que o usuário o altere** é definido como **0**.  <br/> **Especificar o número de PINs anteriores que podem ser associados a uma conta de usuário que não pode ser reutilizada** é definido como **0**.  <br/> **Número de falhas de autenticação permitidas antes que o dispositivo seja apagado** é definido com o mesmo valor usado no Microsoft 365 Business (5 por padrão).  <br/> **Quantidade máxima de tempo (em minutos) permitida após o dispositivo ficar ocioso que fará com que o dispositivo fique com PIN ou a senha bloqueados** é definida com o mesmo valor usado em Microsoft 365 Business.  <br/> |
|Habilitar a recuperação de dados protegidos  <br/> |**Configurações avançadas** \> **Proteção de dados**: **Mostrar o ícone de proteção de dados corporativos** e **Usar o Azure RMS para WIP** são definidos como **Ativado**.  <br/> |
|Proteger locais de nuvem corporativos adicionais  <br/> |**Configurações avançadas** \> **Domínios protegidos** e **Recursos de nuvem** mostram domínios e sites do SharePoint.  <br/> |
|Os arquivos usados por esses aplicativos estão protegidos  <br/> |A lista de aplicativos protegidos é mostrada em **Aplicativos permitidos**.  <br/> |
|||
   
## <a name="windows-10-device-protection-settings"></a>Configurações de proteção de dispositivo do Windows 10

A tabela a seguir fornece detalhes sobre como as definições de configuração de dispositivo do Windows 10 são mapeadas para configurações do Intune.
  
Para localizar a configuração do Intune, enquanto estiver conectado com suas credenciais de administrador do Microsoft 365 Business, vá para [portal do Azure](https://portal.azure.com)e, em seguida, selecione **mais serviços**e digite o Intune no **filtro**, selecione o dispositivo do **Intune** \> ** ** \> **perfis**de configuração. Selecione **Política de dispositivo para Windows 10** \> **Propriedades** \> **Configurações**.
  
|**Configuração de política de dispositivo do Windows 10**|**Configuração(ões) do Intune**|
|:-----|:-----|
|Ajudar a proteger PCs contra vírus e outras ameaças usando o Windows Defender Antivirus  <br/> |Permitir Monitoramento em Tempo Real = ON  <br/> Permitir Proteção de Nuvem = ON  <br/> Avisar Usuários para Envio de Amostras = Enviar Amostras Confiáveis automaticamente (envio automático de não PII padrão)  <br/> |
|Ajudar a proteger PCs contra ameaças baseadas na Web no Microsoft Edge  <br/> |**SmartScreen** nas **Configurações do Navegador Microsoft Edge** é definido como **Obrigatório**.  <br/> |
|Desligar a tela do dispositivo quando ele ficar ocioso (minutos)  <br/> |Máximo de minutos de inatividade até bloqueios de tela (minutos)  <br/> |
|Permitir que os usuários baixem aplicativos da Microsoft Store  <br/> |Política de URI personalizado  <br/> |
|Permitir que os usuários acessem a Cortana  <br/> |**Geral** \> **Cortana** é definido como **bloquear** no Intune quando definido como **Desativar** no Microsoft 365 Business.  <br/> |
|Permitir que os usuários recebam anúncios e dicas sobre o Windows da Microsoft  <br/> |**Destaque do Windows**, totalmente bloqueado se for definido como **desativar** no Microsoft 365 Business.  <br/> |
|Manter dispositivos Windows 10 atualizados automaticamente  <br/> | Essa configuração está no **Microsoft Intune** \> **Atualizações de serviço - Anéis de Atualização do Windows 10**. Escolha **Política de atualização para dispositivos Windows 10** e **Propriedades** \> **Configurações**.      <br/>  Quando a configuração Microsoft 365 Business é definida como **Ativada**, todas as seguintes configurações são definidas:  <br/> **Ramificação de serviço** é definida como **CB** (CBB quando isso é desativado no Microsoft 365 Business).  <br/> **Atualizações de produtos Microsoft** é definida como **Permitir**.  <br/> **Drivers do Windows** é definida como **Permitir**.  <br/> **Comportamento de atualização automática** é definida como **Instalar automaticamente no horário de manutenção** com:  <br/> **Início após o expediente** é definida como **6h**.  <br/> **Término após o expediente** é definida como **22h**.  <br/> **Período de adiamento de atualização de qualidade (dias)** é definida como **0**.  <br/> **Período de adiamento de atualização de recursos (dias)** é definida como **0**.  <br/> **Modo de download de otimização de entrega** é definida como **HTTP combinado com emparelhamento atrás do mesmo NAT**.  <br/> |
|||
   

