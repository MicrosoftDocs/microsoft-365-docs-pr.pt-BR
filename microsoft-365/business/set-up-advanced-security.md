---
title: Configurar políticas de segurança avançada para os usuários de negócios do Microsoft 365
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Configurar a proteção avançada contra ameaças do Office 365 e proteger dados confidenciais.
ms.openlocfilehash: 4728e11a16fdf8a461f5687632df75699923f846
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "33663622"
---
# <a name="set-up-advanced-security-policies"></a>Configurar políticas de segurança avançadas

Além das políticas que podem ser configuradas no [centro de administração](security-features.md#microsoft-365-business-admin-center-security-features), você pode adicionar proteção adicional contra ameaças da Cyber Configurando a [proteção avançada contra ameaças do Office 365](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653) (ATP). Você também pode proteger informações confidenciais Configurando [prevenção de perda de dados](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e) (DLP), proteção de informações do Azure (AIP), arquivamento do [Exchange Online](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)e também gerenciar seus dispositivos no [portal do Intune](#go-to-intune-admin-center).

Confira as [10 maneiras principais de proteger o plano de negócios do Microsoft 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) para obter uma visão geral das maneiras mais importantes nas quais você pode proteger sua empresa, incluindo o uso da MFA para criar uma segunda forma de entrada.

Consulte [proteger seus vídeos de treinamento de negócios](https://support.office.com/article/e12187b8-216a-4490-9e3b-df34a06fb787) para obter instruções para obter instruções fáceis de seguir.

## <a name="increase-email-malware-protection"></a>Aumentar a proteção contra malware de email

Malware é um software que pode danificar seus computadores ou rede e, possivelmente, roubar dados de você, incluindo informações pessoais ou de clientes. O Microsoft 365 Business inclui um nível de linha de base de proteção contra malware, mas você pode aumentar essa proteção definindo configurações adicionais. Consulte [Ativar](https://support.office.com/article/02b5783a-eea0-42e8-8856-62440718c3f0) vídeo de treinamento de detecção de malware para obter instruções.

## <a name="set-up-advanced-threat-protection-features"></a>Configurar recursos avançados de proteção contra ameaças

- **Proteger contra anexos não seguros:** A ATP identifica o conteúdo mal-intencionado abrindo anexos de email em um ambiente virtual e executando a análise do comportamento resultante. O conteúdo é avaliado para determinar sua intenção (seja normal ou mal-intencionada) e a ATP bloqueia a entrega de anexos não seguros, ajudando a proteger você contra esquemas de phishing e infecções de ransomware. Para ativar a proteção de anexos, consulte [Configurar o Office 365 ATP Safe Attachments](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775) Help Documentation e [proteger contra arquivos mal-intencionados](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5) de vídeo de treinamento curto.
    
- **Proteger seu ambiente quando os usuários clicarem em links mal-intencionados:** A ATP também examina links em email no momento em que um usuário clica neles. Se um link não for seguro, o usuário será avisado para não visitar o site ou informando que o site foi bloqueado. Isso ajuda a proteger contra esquemas de phishing. Para ativar isso, confira [Configurar o Office 365 ATP Safe links](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-atp-safe-links-policies) ajuda documentação e [proteger contra sites mal-intencionados](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa) vídeo de treinamento curto.

- **Proteger seu ambiente contra tentativas de phishing:**  A ATP anti-phishing aplica um conjunto de modelos de aprendizado de máquina junto com algoritmos de detecção de representação a mensagens de entrada para fornecer proteção contra ataques de phishing em que alguém está tentando extrair informações de você fingindo ser um conhecido amostra. Para ativar isso, confira configurar a documentação da ajuda do [ATP anti-phishing](https://docs.microsoft.com/office365/securitycompliance/set-up-anti-phishing-policies) e [proteger contra](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c) o vídeo de treinamento curto de tentativas de phishing.

## <a name="set-up-dlp-features"></a>Configurar recursos de DLP

Consulte [criar uma política de DLP a partir de um modelo](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) para obter um exemplo de como configurar uma política para proteção contra informações de identificação pessoal (PII). 
  
A DLP vem com vários modelos de política prontos para uso para várias localidades diferentes. Por exemplo, dados financeiros da Austrália, ato de informações pessoais do Canadá, dados financeiros dos EUA, etc. Veja o [que os modelos de política de DLP incluem](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) para uma lista completa. Todos esses modelos podem ser habilitados de forma semelhante ao exemplo de modelo PII. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Configurar a retenção de email com o arquivamento do Exchange Online

 Os recursos de licença de arquivamento do **Exchange Online** oferecem a capacidade de ajudar a manter os padrões de conformidade e regulamentação ao preservar o conteúdo de email para fins de descoberta eletrônica. Isso também ajuda a reduzir o risco no caso de litígio e oferece uma maneira de recuperar dados após uma violação de segurança ou quando você precisa recuperar itens excluídos. Para ativar esses recursos, você pode usar a retenção de litígio para preservar todo o conteúdo de um usuário ou usar políticas de retenção para maior personalização. 
  
**Retenção de litígio:** Você pode preservar todo o conteúdo da caixa de correio, incluindo itens excluídos, colocando a caixa de correio de um usuário em retenção de litígio. 
    
Para colocar uma caixa de correio em retenção de litígio, no centro de administração:
    
1. No painel de navegação à esquerda, vá para usuários **ativos**do **usuário** \> .
    
2. Selecione um usuário cuja caixa de correio você deseja colocar em retenção de litígio e, no painel de usuário, expanda **configurações de email** e ao lado de **mais configurações** escolha **Editar propriedades do Exchange**.
    
3. Na página caixa de correio do usuário, escolha * * recursos de caixa de correio * * no painel de navegação esquerdo e, em seguida, escolha o link **habilitar** em **retenção de litígio**.
    
4. Na caixa de diálogo **retenção de litígio** , é possível especificar a duração da retenção de litígio no campo duração da **retenção de litígio** , deixar o campo vazio se você quiser colocar uma retenção infinita. Você também pode adicionar notas e direcionar o proprietário da caixa de correio para um site que pode ser necessário para explicar mais sobre \> o **salvamento**de litígio.
    
**Retenção:** Você pode habilitar políticas de retenção personalizadas, por exemplo, para preservar um período específico de tempo ou excluir o conteúdo permanentemente no final do período de retenção. Para saber mais, confira [visão geral das políticas de retenção](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).
## <a name="set-up-azure-information-protection-features"></a>Configurar recursos de proteção de informações do Azure

A proteção de informações do Azure (AIP) é uma solução baseada em nuvem que ajuda uma organização a classificar e, opcionalmente, proteger seus documentos e emails aplicando rótulos. Os rótulos podem ser aplicados automaticamente por administradores que definem regras e condições, manualmente por usuários ou uma combinação onde os usuários recebem recomendações.

A capacidade de aplicar as seguintes restrições ao enviar emails no Outlook na Web é automaticamente habilitada para todos os usuários:
  
- **Não encaminhar**: os destinatários podem ler a mensagem, mas não podem encaminhar, imprimir ou copiar o conteúdo
    
- **Encrypt**: toda a mensagem é criptografada. Os destinatários devem realizar etapas adicionais para confirmar sua identidade antes de acessar o conteúdo criptografado e não podem remover a criptografia.
    
- **Confidencial**: fornece aos funcionários em sua organização permissões completas para o conteúdo e os anexos de email, mas não para pessoas de fora da organização. Os proprietários de dados podem controlar e revogar o conteúdo em qualquer ponto.
    
- **Altamente confidencial**: essa restrição pode ser aplicada a dados altamente confidenciais, permitindo que os funcionários exibam, editem e respondam, mas não encaminhem, imprimam ou copiem os dados. Os proprietários de dados podem controlar e revogar o conteúdo em qualquer ponto.

### <a name="make-sure-azure-information-protection-is-activated"></a>Verifique se a proteção de informações do Azure está ativada

Para verificar se o AIP está ativado:

1. Entre no [portal do Azure](https://portal.azure.com/).

2. Selecione **todos os serviços** e digite na *proteção de informações do Azure* na **caixa de pesquisa**.

3. Depois que os resultados são exibidos, clique em Iniciar ao lado de **proteção de informações do Azure** para torná-lo favorito e fácil de localizar mais tarde.

4. Selecione \> **ativação da proteção** de **proteção de informações do Azure** e verifique se o status está definido como ativado. 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a>Exibir a política de proteção de informações do Azure e os rótulos padrão 

Para exibir e modificar os rótulos existentes:

1. No painel de proteção de informações do Azure **** \> , selecione **Rótulos**de classificações. <br/>![Rótulos padrão para a proteção de informações do Azure.](media/AIPLabels.png)

2. Você pode escolher qualquer rótulo para exibir opções, você pode alterar o nome de exibição, as cores, etc.
 
3. Confira [modificar e criar novos rótulos](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) se você quiser criar seus próprios. 

### <a name="install-the-azure-information-protection-client-manually"></a>Instalar o cliente de proteção de informações do Azure manualmente

Para instalar manualmente o cliente AIP:

1. Baixe o **AzInfoProtection. exe** do [centro de download da Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).
 
2. Você pode verificar se a instalação funcionou exibindo um documento do Word e certificando-se de que a opção **proteger** está disponível na guia **página inicial** . <br/>![Menu suspenso proteção de guia em um documento do Word.](media/Word_Protect.png)

Confira mais informações em [instalar o cliente](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).

## <a name="go-to-intune-admin-center"></a>Vá para o centro de administração do Intune

1. Entre no [portal do Azure](https://portal.azure.com/).

2. Selecione **todos os serviços** e digite no *Intune* na **caixa de pesquisa**.

3. Após exibir os resultados, clique em Iniciar ao lado de **Microsoft Intune** para torná-lo favorito e fácil de localizar mais tarde.

Além do centro de administração, você pode usar o Intune para registrar e gerenciar os dispositivos de sua organização. Para saber mais, confira [recursos por método de inscrição para dispositivos do Windows](https://docs.microsoft.com/intune/enrollment-method-capabs) e [Opções de registro para dispositivos gerenciados pelo Intune](https://docs.microsoft.com/intune/enrollment-options).

## <a name="microsoft-secure-score"></a>Classificação de Segurança da Microsoft

