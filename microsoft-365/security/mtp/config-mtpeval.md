---
title: Configurar os pilares do Microsoft 365 defender para o laboratório de avaliação ou o ambiente piloto
description: Configure os pilares do Microsoft 365 defender, como o Microsoft defender para Office 365, o Microsoft defender para identidade, o Microsoft Cloud app Security e o Microsoft defender para ponto de extremidade, para seu laboratório de avaliação ou ambiente piloto.
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
ms.openlocfilehash: 240ffd7ec8d46da33c43ec2f9cb50cf59c89f11b
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131292"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a>Configurar os pilares do Microsoft 365 defender para seu laboratório de avaliação ou ambiente piloto

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender


Criar um laboratório de avaliação do Microsoft 365 defender ou um ambiente piloto e implantá-lo é um processo de três fases:

|[![Fase 1: preparar](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)<br/>[Fase 1: preparar](prepare-mtpeval.md) |[![Fase 2: configurar](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)<br/>[Fase 2: configurar](setup-mtpeval.md) |![Fase 3: integração](../../media/phase-diagrams/onboard.png)<br/>Fase 3: integração | [![Voltar ao piloto](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[Voltar ao manual do piloto](mtp-pilot.md) |
|--|--|--|--|
|| |*Você está aqui!* | |

Você está atualmente na fase de configuração.

A preparação é fundamental para qualquer implantação bem-sucedida. Neste artigo, você será orientado nos pontos que precisará considerar ao se preparar para implantar o Microsoft defender para ponto de extremidade.


## <a name="microsoft-365-defender-pillars"></a>Pilares do Microsoft 365 defender
O Microsoft 365 defender consiste em quatro pilares. Embora um pilar já possa fornecer o valor para a segurança da sua organização de rede, habilitar os quatro pilares Microsoft 365 defender fornecerá à sua organização o mais valor.

![Image of_Microsoft 365 defender Solution for users, Microsoft defender para identidade, para pontos de extremidade Microsoft defender for Endpoint, para aplicativos de nuvem, segurança do aplicativo do Microsoft Cloud e para dados, Microsoft defender para Office 365](../../media/mtp/m365pillars.png)

Esta seção orientará você a configurar:
-   Microsoft Defender para Office 365
-   Microsoft Defender para Identidade 
-   Microsoft Cloud App Security
-   Microsoft Defender para Ponto de Extremidade


## <a name="configure-microsoft-defender-for-office-365"></a>Configurar o Microsoft defender para Office 365

>[!NOTE]
>Pule esta etapa se você já ativou o defender para Office 365. 

Há um módulo do PowerShell chamado *Office 365 Advanced Threat Protection Configuration Analyzer (orca)* que ajuda a determinar algumas dessas configurações. Ao executar como um administrador em seu locatário, o Get-ORCAReport ajudará a gerar uma avaliação das configurações de higiene de antispam, anti-phishing e outras mensagens. Você pode baixar este módulo no https://www.powershellgallery.com/packages/ORCA/ . 

1. Navegue até a política de gerenciamento de ameaças [do centro de conformidade & segurança do Office 365](https://protection.office.com/homepage)  >  **Threat management**  >  **Policy**.

   ![Página da política de gerenciamento de ameaças do centro de conformidade & of_Office de imagem 365](../../media/mtp-eval-32.png)
 
2. Clique em **anti-phishing**, selecione **criar** e preencha o nome e a descrição da política. Clique em **Avançar**.

   ![Imagem of_Office 365 segurança & centro de conformidade página política de anti-phishing onde você pode nomear sua política](../../media/mtp-eval-33.png)

   > [!NOTE]
   > Edite sua política anti-phishing avançada no Microsoft defender para Office 365. Altere o **limite de phishing avançado** para **2-agressivo**.

3. Clique no menu suspenso **Adicionar uma condição** e selecione seu (s) domínio (s) como domínio do destinatário. Clique em **Avançar**.

   ![Imagem of_Office 365 segurança & centro de conformidade página política de anti-phishing onde você pode adicionar uma condição para seu aplicativo](../../media/mtp-eval-34.png)
 
4. Revise suas configurações. Clique em **criar esta política** para confirmar. 

   ![Imagem of_Office 365 segurança & centro de conformidade página política de anti-phishing onde você pode revisar suas configurações e clicar no botão criar esta política](../../media/mtp-eval-35.png)
 
5. Selecione **anexos seguros** e selecione a opção **Ativar ATP para SharePoint, onedrive e Microsoft Teams** .

   ![Imagem of_Office 365 segurança & centro de conformidade onde você pode ativar a ATP para SharePoint, OneDrive e Microsoft Teams](../../media/mtp-eval-36.png)

6. Clique no ícone + para criar uma nova política de anexo seguro, aplique-a como domínio de destinatário aos seus domínios. Clique em **Salvar**.

   ![Imagem of_Office 365 segurança & centro de conformidade onde você pode criar um novo criar uma nova política de anexo seguro](../../media/mtp-eval-37.png)
 
7. Em seguida, selecione a política de **links seguros** e clique no ícone de lápis para editar a política padrão.

8. Certifique-se de que a opção **não rastrear quando os usuários clicarem em links seguros** não esteja selecionada, enquanto o restante das opções estiver selecionado. Confira [configurações de links seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) para obter detalhes. Clique em **Salvar**. 

   ![Imagem of_Office 365 segurança & centro de conformidade que mostra que a opção não controla quando os usuários clicam em seguro não está selecionado](../../media/mtp-eval-38.png)

9. Em seguida, selecione a política **anti-malware** , selecione o padrão e escolha o ícone de lápis.

10. Clique em **configurações** e selecione **Sim e use o texto de notificação padrão** para habilitar a **resposta de detecção de malware**. Ativar o **filtro de tipos de anexo comuns** . Clique em **Salvar**.

    ![Image of_Office 365 Security & centro de conformidade a página que mostra que a resposta de detecção de malware está ativada com a notificação padrão e o filtro de tipos de anexo comuns está ativado](../../media/mtp-eval-39.png)
  
11. Navegue até [Office 365 Security & centro de conformidade](https://protection.office.com/homepage)  >  **pesquisa**  >  **log de auditoria** pesquisa e ative a auditoria.

    ![Imagem of_Office 365 segurança & centro de conformidade onde você pode ativar a pesquisa de log de auditoria](../../media/mtp-eval-40.png)

12. Integre o Microsoft defender para Office 365 com o Microsoft defender para ponto de extremidade. Navegue até [Office 365 Security & centro de conformidade](https://protection.office.com/homepage)  >  **Gerenciamento de ameaças** de central  >  **Explorer** de segurança e selecione o **Microsoft defender para configurações de ponto de extremidade** no canto superior direito da tela. Na caixa de diálogo de conexão do defender for Endpoint, ative **conectar ao Microsoft defender para ponto de extremidade**.

    ![Imagem of_Office 365 segurança & centro de conformidade onde você pode ativar o Microsoft defender para a conexão de ponto de extremidade no](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a>Configurar o Microsoft defender para identidade

>[!NOTE]
>Pule esta etapa se você já tiver habilitado o Microsoft defender para identidade

1. Navegue até a [central de segurança do Microsoft 365](https://security.microsoft.com/info) > selecione **mais recursos**  >  **Microsoft defender para identidade**.

   ![Imagem of_Microsoft 365 página da central de segurança onde há uma opção para abrir o Microsoft defender para identidade](../../media/mtp-eval-42.png)

2. Clique em **criar** para iniciar o assistente do Microsoft defender para identidade. 

   ![Página do assistente de imagem of_Microsoft defender para identidade onde você deve clicar em criar botão](../../media/mtp-eval-43.png)

3. Escolha **fornecer um nome de usuário e senha para se conectar à sua floresta do Active Directory**.  

   ![Página de boas-vindas do of_Microsoft defender para identidade](../../media/mtp-eval-44.png)

4. Insira suas credenciais locais do Active Directory. Pode ser qualquer conta de usuário que tenha acesso de leitura ao Active Directory.

   ![Imagem of_Microsoft defender da página de serviços de diretório de identidade onde você deve colocar suas credenciais](../../media/mtp-eval-45.png)

5. Em seguida, escolha **baixar a configuração do sensor** e transferir o arquivo para o controlador de domínio.

   ![Imagem of_Microsoft defender para a página de identidade onde você pode selecionar a configuração do sensor de download](../../media/mtp-eval-46.png)

6. Execute a instalação do sensor de identidade do Microsoft defender e comece seguindo o assistente.

   ![Imagem of_Microsoft defender para a página de identidade onde você deve clicar em avançar para seguir o assistente do sensor de identidade do Microsoft defender](../../media/mtp-eval-47.png)
 
7. Clique em **Avançar** no tipo de implantação do sensor.

   ![Imagem of_Microsoft defender para a página de identidade onde você deve clicar em avançar para ir para a próxima página](../../media/mtp-eval-48.png)
 
8. Copie a chave de acesso porque você precisa inseri-la próxima no assistente.

   ![Página sensores de of_the de imagem onde você deve copiar a tecla de acesso que precisa inserir na próxima página do assistente de instalação do sensor de identidade do Microsoft defender](../../media/mtp-eval-49.png)
 
9. Copie a chave de acesso no assistente e clique em **instalar**. 

   ![Imagem of_Microsoft defender para o assistente de sensor de identidade onde você deve fornecer a chave de acesso e clique no botão instalar](../../media/mtp-eval-50.png)

10. Parabéns, você configurou com êxito o Microsoft defender para identidade no seu controlador de domínio.

    ![Imagem of_Microsoft defender para a conclusão da instalação do assistente do sensor de identidade onde você deve clicar no botão concluir](../../media/mtp-eval-51.png)
 
11. Na seção configurações [de identidade do Microsoft defender](https://go.microsoft.com/fwlink/?linkid=2040449) , selecione * * Microsoft defender para ponto de extremidade * * e ative o botão de alternância. Clique em **Salvar**. 

    ![Imagem of_the a página de configurações do Microsoft defender para identidade onde você deve ativar a ativar/desativar o Microsoft defender para ponto de extremidade](../../media/mtp-eval-52.png)

>[!NOTE]
>O Windows Defender ATP foi remarcado como Microsoft defender para ponto de extremidade. As alterações de remarcação em todos os nossos portais estão sendo distribuídas para consistência.


## <a name="configure-microsoft-cloud-app-security"></a>Configurar o Microsoft Cloud app Security

>[!NOTE]
>Pule esta etapa se você já tiver habilitado o Microsoft Cloud app Security. 

1. Navegue até [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **mais recursos**  >  **Microsoft Cloud app Security**.

   ![Imagem of_Microsoft 365 página da central de segurança onde você pode ver o Microsoft Cloud app Card e deve clicar no botão abrir](../../media/mtp-eval-53.png)

2. No prompt de informações para integrar o Microsoft defender para identidade, selecione **habilitar o Microsoft defender para integração de dados de identidade**.
  
   ![Imagem of_the solicitação de informações para integrar o Microsoft defender para identidade onde você deve selecionar o link habilitar o Microsoft defender para identidade de dados de identidade](../../media/mtp-eval-54.png)

   > [!NOTE]
   > Se você não vir esse prompt, pode significar que sua integração de dados do Microsoft defender para identidade já foi habilitada. No entanto, se você não tiver certeza, entre em contato com seu administrador de ti para confirmar. 

3. Vá para **configurações**, ative o **Microsoft defender para habilitar a integração de identidades** e clique em **salvar**. 

   ![Imagem of_the de configurações onde você deve ativar o Microsoft defender para habilitar a integração de identidade e clicar em salvar](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > Para novas instâncias do Microsoft defender para identidade, essa integração é ativada automaticamente. Confirme se a integração do Microsoft defender para identidades foi habilitada antes de prosseguir para a próxima etapa.
 
4. Nas configurações de descoberta de nuvem, selecione **Microsoft defender para a integração de ponto de extremidade** e habilite a integração. Clique em **Salvar**.

   ![Imagem of_the página do Microsoft defender para ponto de extremidade onde a caixa de seleção bloquear aplicativos não aprovados em Microsoft defender para integração de ponto de extremidade está selecionada. Clique em salvar.](../../media/mtp-eval-56.png)

5. Em configurações de descoberta de nuvem, selecione o **enriquecimento do usuário** e habilite a integração com o Azure Active Directory.

   ![Imagem da seção de enriquecimento do usuário em que a caixa de seleção enriquecimento de identificadores de usuário descobertos com o Azure Active Directory está marcada](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a>Configurar o Microsoft defender para ponto de extremidade

>[!NOTE]
>Pule esta etapa se já tiver habilitado o Microsoft defender para ponto de extremidade.

1. Navegue até a central de [segurança da Microsoft 365](https://security.microsoft.com/info)  >  **mais recursos**  >  **central de segurança do Microsoft defender**. Clique em **Abrir**. 

   ![Opção da central de segurança de imagem of_Microsoft defender na página centro de segurança do Microsoft 365](../../media/mtp-eval-58.png)
 
2. Siga o assistente do Microsoft defender para pontos de extremidade. Clique em **Avançar**. 

   ![Imagem of_the página do assistente de boas-vindas do Microsoft defender Security Center](../../media/mtp-eval-59.png)

3. Escolha com base em seu local de armazenamento de dados preferido, política de retenção de dados, tamanho da organização e consentimento para recursos de visualização.

   ![Imagem of_the página para selecionar o país de armazenamento de dados, a política de retenção e o tamanho da organização. Clique em avançar quando terminar de selecionar.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > Você não pode alterar algumas das configurações, como o local de armazenamento de dados, posteriormente. 

   Clique em **Avançar**. 

4. Clique em **continuar** para provisionar seu locatário do Microsoft defender para ponto de extremidade.

   ![Página de of_the de imagem solicitando que você clique no botão continuar para criar sua instância de nuvem](../../media/mtp-eval-61.png)

5. Integração dos pontos de extremidade por meio de políticas de grupo, Microsoft Endpoint Manager ou executando um script local para o Microsoft defender para ponto de extremidade. Para simplificar, este guia usa o script local.

6. Clique em **baixar pacote** e copie o script de integração para seus pontos de extremidade.

   ![Imagem of_page solicitando que você clique no botão baixar pacote para copiar o script de integração para o ponto de extremidade ou pontos de extremidade](../../media/mtp-eval-62.png)

7. No ponto de extremidade, execute o script de integração como administrador e escolha Y. 

   ![Imagem of_the linha de comando onde você executa o script de integração e escolhe Y para continuar](../../media/mtp-eval-63.png)

8. Parabéns, você entrou no primeiro ponto de extremidade.

   ![Imagem of_the linha de comando, onde você obtém a confirmação de que você tenha integrado seu primeiro ponto de extremidade. Pressione qualquer tecla para continuar](../../media/mtp-eval-64.png)

9. Copie-cole o teste de detecção do assistente do Microsoft defender for Endpoint.

   ![Imagem of_the executar uma etapa de teste de detecção onde você deve clicar em copiar para copiar o script de teste de detecção que deve ser colado no prompt de comando](../../media/mtp-eval-65.png)

10. Copie o script do PowerShell para um prompt de comando com privilégios elevados e execute-o. 

    ![Imagem of_command prompt onde você deve copiar o script do PowerShell para um prompt de comando elevado e executá-lo](../../media/mtp-eval-66.png)

11. Selecione **começar a usar o Microsoft defender para ponto de extremidade** do assistente.

    ![A imagem of_the prompt de confirmação do assistente onde você deve clicar em começar a usar o Microsoft defender para ponto de extremidade](../../media/mtp-eval-67.png)
 
12. Visite a [central de segurança do Microsoft defender](https://securitycenter.windows.com/). Vá até **configurações** e selecione **recursos avançados**. 

    ![Imagem do menu configurações da central de segurança do of_Microsoft defender onde você deve selecionar recursos avançados](../../media/mtp-eval-68.png)

13. Ative a integração com o **Microsoft defender para identidade**.  

    ![Image of_Microsoft defender recursos avançados da central de segurança, Microsoft defender para opções de identidade alternar que você precisa ativar](../../media/mtp-eval-69.png)

14. Ative a integração com a **inteligência contra ameaças do Office 365**.

    ![Image of_Microsoft defender central de segurança recursos avançados, opção de inteligência de ameaças do Office 365-você precisa ativar](../../media/mtp-eval-70.png)

15. Ative a integração com **o Microsoft Cloud app Security**.

    ![Image of_Microsoft defender recursos avançados do centro de segurança, opções de segurança do aplicativo Microsoft Cloud que você precisa ativar](../../media/mtp-eval-71.png)

16. Role para baixo e clique em **salvar preferências** para confirmar as novas integrações.

    ![Botão de preferências de of_Save de imagem que você precisa clicar](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a>Iniciar o serviço Microsoft 365 Defender

>[!NOTE]
>A partir de 1º de junho de 2020, a Microsoft habilita automaticamente os recursos do Microsoft 365 defender para todos os locatários qualificados. Confira este [artigo da comunidade técnica da Microsoft sobre a qualificação de licença](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) para obter detalhes. 


Vá para a [central de segurança do Microsoft 365](https://security.microsoft.com/homepage). Navegue até **configurações** e, em seguida, selecione **Microsoft 365 defender**.

![Captura de tela de opção de imagem of_Microsoft 365 defender da página de configurações da central de segurança do Microsoft 365 ](../../media/mtp-eval-72b.png) <br>

Para obter uma orientação mais abrangente, consulte [ativar o Microsoft 365 defender](mtp-enable.md). 

Parabéns! Você acabou de criar o laboratório de avaliação do Microsoft 365 defender ou o ambiente piloto! Agora você pode se familiarizar com a interface do usuário do Microsoft 365 defender! Veja o que você pode aprender no seguinte guia interativo do Microsoft 365 defender e saiba como usar cada painel para suas tarefas de operação de segurança diárias.


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

Em seguida, você pode simular um ataque e ver como os recursos de produtos cruzam detectar, criar alertas e responder automaticamente a um ataque sem arquivo em um ponto de extremidade.

## <a name="next-step"></a>Próxima etapa
|[Fase de simulação de ataque](mtp-pilot-simulate.md) | Execute a simulação de ataque para seu ambiente piloto do Microsoft 365 defender.
|:-------|:-----|
