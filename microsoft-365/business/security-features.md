---
title: Recursos de segurança do Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-security-compliance
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Saiba mais sobre os recursos de segurança que acompanham o Microsoft 365 Business.
ms.openlocfilehash: 24d4c4e79e7d8737beb82336796956774f127209
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286842"
---
# <a name="microsoft-365-business-security-features"></a>Recursos de segurança do Microsoft 365 Business

O Microsoft 365 Business oferece recursos simplificados de segurança para ajudar a proteger seus dados em PCs, telefones e tablets.
    
## <a name="microsoft-365-business-admin-center-security-features"></a>Recursos de segurança do centro de administração de negócios da Microsoft 365

Você pode gerenciar muitos dos recursos de segurança de negócios do Microsoft 365 no centro de administração, que oferece uma maneira simplificada para ativar ou desativar esses recursos. No centro de administração, você pode fazer o seguinte:
  
![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
- [Definir configurações de gerenciamento de aplicativo para dispositivos Android ou Ios](app-protection-settings-for-android-and-ios.md) . 
    
    Essas configurações incluem a exclusão de arquivos de um dispositivo inativo após um período definido, a criptografia de arquivos de trabalho, exigindo que os usuários definam um PIN, etc.
    
- [Definir configurações de proteção de aplicativo para dispositivos Windows 10](protection-settings-for-windows-10-devices.md) . 
    
    Essas configurações podem ser aplicadas a dados da empresa em dispositivos pertencentes à empresa ou de propriedade pessoal.
    
- [Definir configurações de proteção de dispositivos para dispositivos Windows 10](protection-settings-for-windows-10-pcs.md) . 
    
    Você pode habilitar a criptografia [BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405) para ajudar a proteger os dados caso um dispositivo seja perdido ou roubado, e permitir que o [Windows Exploit Guard](https://go.microsoft.com/fwlink/p/?linkid=871404) forneça proteção avançada contra o ransomware. 
    
- [Remover dados da empresa de dispositivos](remove-company-data.md)
    
    Você pode limpar dados da empresa remotamente se um dispositivo for perdido, roubado ou se um funcionário sair da sua empresa.
    
- [Redefina dispositivos Windows 10 para suas configurações de fábrica](reset-devices-to-factory-settings.md) . 
    
    Você pode redefinir qualquer dispositivo Windows 10 que tenha as configurações de proteção de dispositivo aplicadas a eles.
    
## <a name="additional-security-features"></a>Recursos de segurança adicionais 

Recursos avançados no Microsoft 365 Business estão disponíveis para ajudá-lo a proteger sua empresa contra ameaças e proteger as informações confidenciais.
  
- **[Proteção Avançada contra Ameaças do Office 365](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)**
    
    A proteção avançada contra ameaças (ATP) ajuda a proteger sua empresa contra ataques sofisticados de phishing e ransomware, projetados para comprometer informações de funcionários ou clientes. Os recursos incluem:
    
  - Análise de conexão sofisticada e análise com alimentação de AI para detectar e descartar mensagens perigosas.
    
  - Verificações automáticas de links da Web em email para avaliar se eles fazem parte de um esquema de phishing. Isso impede você de acessar sites não seguros.
    
- **[Visão geral das políticas de prevenção contra perda de dados](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)** (DLP). 
    
    Você pode configurar o DLP para detectar automaticamente informações confidenciais, como números de cartão de crédito, números de seguridade social, etc. para impedir o compartilhamento inadvertido fora da empresa.
    
- **[Arquivamento do Exchange Online](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    A licença de arquivamento do Exchange Online permite que as mensagens sejam facilmente arquivadas com o backup contínuo de dados. Ele armazena todos os emails de um usuário, incluindo itens excluídos, caso eles sejam necessários posteriormente para descoberta ou restauração. Além disso, você pode usar diferentes políticas de retenção para preservar dados de email para litígios, eDiscovery ou para atender aos requisitos de conformidade.
    
- **[Proteção de Informações do Azure](https://go.microsoft.com/fwlink/p/?linkid=871406)**
    
    A proteção de informações ajuda você a controlar o acesso a informações confidenciais em emails e documentos com controles como "não encaminhar" e "não copiar". Você também pode classificar informações confidenciais como "confidencial" e especificar como as informações classificadas podem ser compartilhadas fora e dentro da empresa. A criptografia de nível empresarial é fácil de aplicar a emails e documentos para manter suas informações privadas. O Microsoft 365 Business inclui todos os recursos do [plano de proteção de informações do Azure 1](https://go.microsoft.com/fwlink/p/?linkid=871407). Você também pode instalar o suplemento cliente de proteção de informações do Azure para aplicativos do Office. Para obter mais detalhes, consulte [Azure Information Protection Client admininstrator Guide](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide).
    
- **[Os recursos completos do Intune no portal do Azure](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    Acessar o centro de administração do Intune no portal do Azure permite que você configure recursos de segurança adicionais, como o gerenciamento de dispositivos MacOS, iPhone e dispositivos Android, juntamente com o gerenciamento avançado de dispositivos do Windows, que não estão disponíveis no Microsoft 365 centro de administração de negócios.
    
As seções a seguir descrevem como você pode gerenciar esses recursos no centro &amp; de conformidade de segurança e no centro de administração do Intune. Com o tempo, os controles simplificados serão adicionados ao centro de administração de negócios do Microsoft 365.
  
## <a name="set-up-advanced-threat-protection-features"></a>Configurar recursos avançados de proteção contra ameaças

- **Proteger contra anexos não seguros:** A ATP identifica o conteúdo mal-intencionado abrindo anexos de email em um ambiente virtual e executando a análise do comportamento resultante. O conteúdo é avaliado para determinar sua intenção (seja normal ou mal-intencionada) e a ATP bloqueia a entrega de anexos não seguros, ajudando a proteger você contra esquemas de phishing e infecções de ransomware. Para ativar a proteção de anexos, confira [Configurar políticas de anexos seguros ATP do Office 365](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775).
    
- Proteger seu ambiente quando os usuários clicarem em links mal-intencionados: a ATP também examina os links em email no momento em que um usuário clica neles. Se um link não for seguro, o usuário será avisado para não visitar o site ou informando que o site foi bloqueado. Isso ajuda a proteger contra esquemas de phishing. Você pode [configurar as políticas de links seguros de ATP do office 365](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) ou [configurar as políticas de links seguros de atp do Office 365](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).
    
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
 
3. ConFira [modificar e criar novos rótulos](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) se você quiser criar seus próprios. 

### <a name="install-the-azure-information-protection-client-manually"></a>Instalar o cliente de proteção de informações do Azure manualmente

Para instalar manualmente o cliente AIP:

1. Baixe o **AzInfoProtection. exe** do [centro de download da Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).
 
2. Você pode verificar se a instalação funcionou exibindo um documento do Word e certificando-se de que a opção **proteger** está disponível na guia **página inicial** . <br/>![Menu suspenso proteção de guia em um documento do Word.](media/Word_Protect.png)

Para obter mais informações, consulte, [instalar o cliente](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)

## <a name="go-to-intune-admin-center"></a>Vá para o centro de administração do Intune

1. Entre no [portal do Azure](https://portal.azure.com/).

2. Selecione **todos os serviços** e digite no *Intune* na **caixa de pesquisa**.

3. Após exibir os resultados, clique em Iniciar ao lado de **Microsoft Intune** para torná-lo favorito e fácil de localizar mais tarde.
 
Você pode usar o Intune para registrar e gerenciar os dispositivos de sua organização. Para saber mais, confira [recursos por método de inscrição para dispositivos do Windows](https://docs.microsoft.com/intune/enrollment-method-capabs) e [Opções de registro para dispositivos gerenciados pelo Intune](https://docs.microsoft.com/intune/enrollment-options).
    
## <a name="faq"></a>Perguntas frequentes

 ### <a name="are-these-security-features-available-in-all-markets"></a>Esses recursos de segurança estão disponíveis em todos os mercados?
  
Sim, esses recursos estão disponíveis em todos os mercados onde o Microsoft 365 Business é vendido.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>Como localizar o centro de conformidade &amp; de segurança?
  
1. [Entre no Microsoft 365 Business](https://portal.microsoft.com/) usando suas credenciais de administrador. 
    
2. No painel de navegação à esquerda, localize **centros de administração** e expanda-o. 
    
    ![No painel de navegação esquerdo do centro de administração do Microsoft 365, escolha centros de administração.](media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. Escolha **conformidade &amp; de segurança** para acessar o &amp; centro de conformidade de segurança.