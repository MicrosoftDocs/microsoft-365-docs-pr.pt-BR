---
title: Configurar os pilares de proteção contra ameaças da Microsoft para o laboratório de avaliação ou ambiente piloto
description: Configure os pilares de proteção contra ameaças da Microsoft, como o Office 365 ATP, o Azure ATP, o Microsoft Cloud app Security e o Microsoft defender ATP para seu laboratório de avaliação ou ambiente piloto.
keywords: configurar a avaliação de proteção contra ameaças da Microsoft, configuração de avaliação de proteção contra ameaças da Microsoft, configurar o projeto piloto de proteção contra ameaças da Microsoft, configurar os pilares de proteção contra ameaças da Microsoft, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.openlocfilehash: 7e9060c804fcdb8445c8d833d8a43dc90a738b04
ms.sourcegitcommit: a83acd5b9eeefd2e20e5bac916fe29d09fb53de9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "48418152"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-or-pilot-environment"></a>Configurar os pilares de proteção contra ameaças da Microsoft para seu laboratório de avaliação ou ambiente piloto

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Proteção contra Ameaças da Microsoft


A criação de um laboratório de avaliação de proteção contra ameaças da Microsoft ou ambiente piloto e sua implantação é um processo de três fases:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Preparar o laboratório de avaliação de proteção contra ameaças da Microsoft ou o ambiente piloto" />
      <br/>Fase 1: preparar </a><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab or pilot environment" title="Configurar o laboratório de avaliação de proteção contra ameaças da Microsoft ou o ambiente piloto" />
      <br/>Fase 2: configuração </a><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Configurar cada pilar de proteção contra ameaças da Microsoft para o laboratório de avaliação de proteção contra ameaças da Microsoft ou o ambiente piloto e pontos de extremidade integrados" />
      <br/>Fase 3: configurar o & integrado </a><br>
</td>
  </tr>
</table>

Você está atualmente na fase de configuração.


A preparação é fundamental para qualquer implantação bem-sucedida. Neste artigo, você será orientado nos pontos que precisará considerar ao se preparar para implantar o Microsoft defender ATP.


## <a name="microsoft-threat-protection-pillars"></a>Pilares de proteção contra ameaças da Microsoft
A proteção contra ameaças da Microsoft consiste em quatro pilares. Embora um pilar já possa fornecer um valor para a segurança da sua organização de rede, a habilitação dos quatro pilares de proteção contra ameaças da Microsoft dará à sua organização o mais valor.

![Imagem of_Microsoft solução de proteção contra ameaças para usuários, proteção avançada contra ameaças do Azure, para pontos de extremidade proteção avançada contra ameaças do Microsoft defender, para aplicativos de nuvem, segurança do aplicativo do Microsoft Cloud e para dados, proteção avançada contra ameaças do Office 365  ](../../media/mtp-eval-31.png)

Esta seção orientará você a configurar:
-   Proteção Avançada contra Ameaças do Office 365
-   Proteção Avançada contra Ameaças do Azure 
-   Segurança no aplicativo na nuvem da Microsoft
-   Proteção avançada contra ameaças do Microsoft Defender


## <a name="configure-office-365-advanced-threat-protection"></a>Configurar a proteção avançada contra ameaças do Office 365

>[!NOTE]
>Pule esta etapa se já tiver habilitado a proteção avançada contra ameaças do Office 365. 

Há um módulo do PowerShell chamado *Office 365 Advanced Threat Protection Configuration Analyzer (orca)* que ajuda a determinar algumas dessas configurações. Ao executar como um administrador em seu locatário, o Get-ORCAReport ajudará a gerar uma avaliação das configurações de higiene de antispam, anti-phishing e outras mensagens. Você pode baixar este módulo no https://www.powershellgallery.com/packages/ORCA/ . 

1. Navegue até a política de gerenciamento de ameaças [do centro de conformidade & segurança do Office 365](https://protection.office.com/homepage)  >  **Threat management**  >  **Policy**.

   ![Página da política de gerenciamento de ameaças do centro de conformidade & of_Office de imagem 365](../../media/mtp-eval-32.png)
 
2. Clique em **anti-phishing ATP**, selecione **criar** e preencha o nome e a descrição da política. Clique em **Avançar**.

   ![Imagem of_Office 365 segurança & centro de conformidade página política de anti-phishing onde você pode nomear sua política](../../media/mtp-eval-33.png)

   > [!NOTE]
   > Edite a política de anti-phishing avançada da ATP. Altere o **limite de phishing avançado** para **2-agressivo**.

3. Clique no menu suspenso **Adicionar uma condição** e selecione seu (s) domínio (s) como domínio do destinatário. Clique em **Avançar**.

   ![Imagem of_Office 365 segurança & centro de conformidade página política de anti-phishing onde você pode adicionar uma condição para seu aplicativo](../../media/mtp-eval-34.png)
 
4. Revise suas configurações. Clique em **criar esta política** para confirmar. 

   ![Imagem of_Office 365 segurança & centro de conformidade página política de anti-phishing onde você pode revisar suas configurações e clicar no botão criar esta política](../../media/mtp-eval-35.png)
 
5. Selecione **anexos seguros de ATP** e selecione a opção **Ativar ATP para SharePoint, onedrive e Microsoft Teams** .

   ![Imagem of_Office 365 segurança & centro de conformidade onde você pode ativar a ATP para SharePoint, OneDrive e Microsoft Teams](../../media/mtp-eval-36.png)

6. Clique no ícone + para criar uma nova política de anexo seguro, aplique-a como domínio de destinatário aos seus domínios. Clique em **Salvar**.

   ![Imagem of_Office 365 segurança & centro de conformidade onde você pode criar um novo criar uma nova política de anexo seguro](../../media/mtp-eval-37.png)
 
7. Em seguida, selecione a política de **links seguros de ATP** e clique no ícone de lápis para editar a política padrão.

8. Certifique-se de que a opção **não rastrear quando os usuários clicarem em links seguros** não esteja selecionada, enquanto o restante das opções estiver selecionado. Confira [configurações de links seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) para obter detalhes. Clique em **Salvar**. 

   ![Imagem of_Office 365 segurança & centro de conformidade que mostra que a opção não controla quando os usuários clicam em seguro não está selecionado](../../media/mtp-eval-38.png)

9. Em seguida, selecione a política **anti-malware** , selecione o padrão e escolha o ícone de lápis.

10. Clique em **configurações** e selecione **Sim e use o texto de notificação padrão** para habilitar a **resposta de detecção de malware**. Ativar o **filtro de tipos de anexo comuns** . Clique em **Salvar**.

    ![Image of_Office 365 Security & centro de conformidade a página que mostra que a resposta de detecção de malware está ativada com a notificação padrão e o filtro de tipos de anexo comuns está ativado](../../media/mtp-eval-39.png)
  
11. Navegue até [Office 365 Security & centro de conformidade](https://protection.office.com/homepage)  >  **pesquisa**  >  **log de auditoria** pesquisa e ative a auditoria.

    ![Imagem of_Office 365 segurança & centro de conformidade onde você pode ativar a pesquisa de log de auditoria](../../media/mtp-eval-40.png)

12. Integrar o Office 365 ATP com o Microsoft defender ATP. Navegue até [Office 365 Security & centro de conformidade](https://protection.office.com/homepage)de  >  **Gerenciamento de ameaças**do centro  >  **Explorer** de conformidade e selecione **configurações do WDATP** no canto superior direito da tela. Na caixa de diálogo conexão ATP do Microsoft defender, ative **conectar ao Windows ATP**.

    ![Imagem of_Office 365 segurança & centro de conformidade onde você pode ativar a conexão ATP do Windows Defender](../../media/mtp-eval-41.png)

## <a name="configure-azure-advanced-threat-protection"></a>Configurar a proteção avançada contra ameaças do Azure

>[!NOTE]
>Pule esta etapa se já tiver habilitado a proteção avançada contra ameaças do Azure

1. Navegue até a [central de segurança do Microsoft 365](https://security.microsoft.com/info) > selecione **mais recursos**  >  **proteção avançada contra ameaças do Azure**.

   ![Imagem of_Microsoft 365 página da central de segurança onde há uma opção para abrir a proteção avançada contra ameaças do Azure](../../media/mtp-eval-42.png)

2. Clique em **criar** para iniciar o assistente de proteção avançada contra ameaças do Azure. 

   ![Imagem of_Azure página do assistente de proteção avançada contra ameaças onde você deve clicar em criar botão](../../media/mtp-eval-43.png)

3. Escolha **fornecer um nome de usuário e senha para se conectar à sua floresta do Active Directory**.  

   ![Página de boas-vindas de proteção avançada contra ameaças de imagem of_Azure](../../media/mtp-eval-44.png)

4. Insira suas credenciais locais do Active Directory. Pode ser qualquer conta de usuário que tenha acesso de leitura ao Active Directory.

   ![Imagem of_Azure página serviços de diretório avançado de proteção contra ameaças onde você deve colocar suas credenciais](../../media/mtp-eval-45.png)

5. Em seguida, escolha **baixar a configuração do sensor** e transferir o arquivo para o controlador de domínio.

   ![Imagem of_Azure página proteção avançada contra ameaças, onde você pode selecionar a configuração do sensor de download](../../media/mtp-eval-46.png)

6. Execute a configuração do sensor ATP do Azure e comece seguindo o assistente.

   ![Página de of_Azure proteção avançada contra ameaças, onde você deve clicar em avançar para seguir o assistente do sensor ATP do Azure](../../media/mtp-eval-47.png)
 
7. Clique em **Avançar** no tipo de implantação do sensor.

   ![Imagem of_Azure página proteção avançada contra ameaças onde você deve clicar em avançar para ir para a próxima página](../../media/mtp-eval-48.png)
 
8. Copie a chave de acesso porque você precisa inseri-la próxima no assistente.

   ![Página de sensores de of_the de imagem onde você deve copiar a tecla de acesso que precisa inserir na próxima página do assistente de instalação do sensor ATP do Azure](../../media/mtp-eval-49.png)
 
9. Copie a chave de acesso no assistente e clique em **instalar**. 

   ![Imagem of_Azure proteção avançada contra ameaças à página Assistente do sensor ATP do Azure onde você deve fornecer a tecla de acesso e clique no botão instalar](../../media/mtp-eval-50.png)

10. Parabéns, você configurou com êxito a proteção avançada contra ameaças do Azure no seu controlador de domínio.

    ![Imagem of_Azure proteção avançada contra ameaças para a conclusão da instalação do assistente do sensor ATP no qual você deve clicar no botão concluir](../../media/mtp-eval-51.png)
 
11. Na seção Configurações de [ATP do Azure Azure](https://go.microsoft.com/fwlink/?linkid=2040449) , selecione **Windows Defender ATP**e ative o botão de alternância. Clique em **Salvar**. 

    ![Imagem of_the página de configurações de ATP do Azure Azure onde você deve ativar a opção de ativar o Windows Defender ATP](../../media/mtp-eval-52.png)

>[!NOTE]
>O Windows Defender ATP foi remarcado como Microsoft defender ATP. As alterações de remarcação em todos os nossos portais estão sendo distribuídas para consistência.


## <a name="configure-microsoft-cloud-app-security"></a>Configurar o Microsoft Cloud app Security

>[!NOTE]
>Pule esta etapa se você já tiver habilitado o Microsoft Cloud app Security. 

1. Navegue até [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **mais recursos**  >  **Microsoft Cloud app Security**.

   ![Imagem of_Microsoft 365 página da central de segurança onde você pode ver o Microsoft Cloud app Card e deve clicar no botão abrir](../../media/mtp-eval-53.png)

2. No prompt de informações para integrar o Azure ATP, selecione **habilitar a integração de dados ATP do Azure**.
  
   ![Imagem of_the solicitação de informações para integrar o Azure ATP onde você deve selecionar o link habilitar a integração de dados ATP do Azure](../../media/mtp-eval-54.png)

   > [!NOTE]
   > Se você não vir esse prompt, pode significar que sua integração de dados ATP do Azure já foi habilitada. No entanto, se você não tiver certeza, entre em contato com seu administrador de ti para confirmar. 

3. Vá para **configurações**, ative a opção de ativação da **integração do Azure ATP** e clique em **salvar**. 

   ![Página de configurações de of_the de imagem, onde você deve ativar a integração do Azure ATP e, em seguida, clique em salvar](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > Para novas instâncias ATP do Azure, esta integração alternada é automaticamente ativada. Confirme se a sua integração do Azure ATP foi habilitada antes de prosseguir para a próxima etapa.
 
4. Nas configurações de descoberta de nuvem, selecione **integração do Microsoft defender ATP**e habilite a integração. Clique em **Salvar**.

   ![Imagem of_the página do Microsoft defender ATP onde a caixa de seleção bloquear aplicativos não aprovados em integração ATP do Microsoft defender está selecionada. Clique em salvar.](../../media/mtp-eval-56.png)

5. Em configurações de descoberta de nuvem, selecione o **enriquecimento do usuário**e habilite a integração com o Azure Active Directory.

   ![Imagem da seção de enriquecimento do usuário em que a caixa de seleção enriquecimento de identificadores de usuário descobertos com o Azure Active Directory está marcada](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-advanced-threat-protection"></a>Configurar a proteção avançada contra ameaças do Microsoft defender

>[!NOTE]
>Pule esta etapa se você já tiver habilitado a proteção avançada contra ameaças do Microsoft defender.

1. Navegue até a central de [segurança da Microsoft 365](https://security.microsoft.com/info)  >  **mais recursos**  >  **central de segurança do Microsoft defender**. Clique em **Abrir**. 

   ![Opção da central de segurança de imagem of_Microsoft defender na página centro de segurança do Microsoft 365](../../media/mtp-eval-58.png)
 
2. Siga o assistente de proteção avançada contra ameaças do Microsoft defender. Clique em **Avançar**. 

   ![Imagem of_the página do assistente de boas-vindas do Microsoft defender Security Center](../../media/mtp-eval-59.png)

3. Escolha com base em seu local de armazenamento de dados preferido, política de retenção de dados, tamanho da organização e consentimento para recursos de visualização.

   ![Imagem of_the página para selecionar o país de armazenamento de dados, a política de retenção e o tamanho da organização. Clique em avançar quando terminar de selecionar.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > Você não pode alterar algumas das configurações, como o local de armazenamento de dados, posteriormente. 

   Clique em **Avançar**. 

4. Clique em **continuar** e ele provisionrá o locatário do Microsoft defender ATP.

   ![Página de of_the de imagem solicitando que você clique no botão continuar para criar sua instância de nuvem](../../media/mtp-eval-61.png)

5. Integração dos pontos de extremidade por meio de políticas de grupo, Microsoft Endpoint Manager ou executando um script local para o Microsoft defender ATP. Para simplificar, este guia usa o script local.

6. Clique em **baixar pacote** e copie o script de integração para seus pontos de extremidade.

   ![Imagem of_page solicitando que você clique no botão baixar pacote para copiar o script de integração para o ponto de extremidade ou pontos de extremidade](../../media/mtp-eval-62.png)

7. No ponto de extremidade, execute o script de integração como administrador e escolha Y. 

   ![Imagem of_the linha de comando onde você executa o script de integração e escolhe Y para continuar](../../media/mtp-eval-63.png)

8. Parabéns, você entrou no primeiro ponto de extremidade.

   ![Imagem of_the linha de comando, onde você obtém a confirmação de que você tenha integrado seu primeiro ponto de extremidade. Pressione qualquer tecla para continuar](../../media/mtp-eval-64.png)

9. Copie-cole o teste de detecção do assistente do Microsoft defender ATP.

   ![Imagem of_the executar uma etapa de teste de detecção onde você deve clicar em copiar para copiar o script de teste de detecção que deve ser colado no prompt de comando](../../media/mtp-eval-65.png)

10. Copie o script do PowerShell para um prompt de comando com privilégios elevados e execute-o. 

    ![Imagem of_command prompt onde você deve copiar o script do PowerShell para um prompt de comando elevado e executá-lo](../../media/mtp-eval-66.png)

11. Selecione **começar a usar o Microsoft defender ATP** no assistente.

    ![A imagem of_the prompt de confirmação do assistente onde você deve clicar em Iniciar usando o Microsoft defender ATP](../../media/mtp-eval-67.png)
 
12. Visite a [central de segurança do Microsoft defender](https://securitycenter.windows.com/). Vá até **configurações** e selecione **recursos avançados**. 

    ![Imagem do menu configurações da central de segurança do of_Microsoft defender onde você deve selecionar recursos avançados](../../media/mtp-eval-68.png)

13. Ative a integração com a **proteção avançada contra ameaças do Azure**.  

    ![Image of_Microsoft defender recursos avançados do centro de segurança, opção de proteção avançada contra ameaças do Azure para habilitar](../../media/mtp-eval-69.png)

14. Ative a integração com a **inteligência contra ameaças do Office 365**.

    ![Image of_Microsoft defender central de segurança recursos avançados, opção de inteligência de ameaças do Office 365-você precisa ativar](../../media/mtp-eval-70.png)

15. Ative a integração com **o Microsoft Cloud app Security**.

    ![Image of_Microsoft defender recursos avançados do centro de segurança, opções de segurança do aplicativo Microsoft Cloud que você precisa ativar](../../media/mtp-eval-71.png)

16. Role para baixo e clique em **salvar preferências** para confirmar as novas integrações.

    ![Botão de preferências de of_Save de imagem que você precisa clicar](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-threat-protection-service"></a>Iniciar o serviço da Proteção contra Ameaças da Microsoft

>[!NOTE]
>A partir de 1º de junho de 2020, a Microsoft habilita automaticamente os recursos de proteção contra ameaças da Microsoft para todos os locatários qualificados. Confira este [artigo da comunidade técnica da Microsoft sobre a qualificação de licença](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) para obter detalhes. 


Vá para a [central de segurança do Microsoft 365](https://security.microsoft.com/homepage). Navegue até **configurações** e selecione **proteção contra ameaças da Microsoft**.

![Captura de tela da opção de proteção contra ameaças de imagem of_Microsoft da página de configurações da central de segurança do Microsoft 365 ](../../media/mtp-eval-72b.png) <br>

Para obter uma orientação mais abrangente, consulte [ativar a proteção contra ameaças da Microsoft](mtp-enable.md). 

Parabéns! Você acabou de criar o laboratório de avaliação de proteção contra ameaças da Microsoft ou o ambiente piloto! Agora você pode se familiarizar com a interface de usuário da proteção contra ameaças da Microsoft! Veja o que você pode aprender no seguinte guia interativo de proteção contra ameaças da Microsoft e saiba como usar cada painel para suas tarefas de operação de segurança diárias.


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

Em seguida, você pode simular um ataque e ver como os recursos de produtos cruzam detectar, criar alertas e responder automaticamente a um ataque sem arquivo em um ponto de extremidade.

## <a name="next-step"></a>Próxima etapa
|![Fase de simulação de ataque](../../media/mtp/run-sim.png) <br>[Fase de simulação de ataque](mtp-pilot-simulate.md) | Execute a simulação de ataque para seu ambiente piloto de proteção contra ameaças da Microsoft.
|:-------|:-----|
