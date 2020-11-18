---
title: Prepare seu ambiente de laboratório de avaliação do Microsoft 365 defender
description: Preparar a aprovação de stakeholder, cronogramas, considerações de ambiente e ordem de adoção ao configurar seu laboratório de avaliação do Microsoft 365 defender ou ambiente piloto
keywords: Versão de avaliação de MTP, preparação piloto de MTP, Prep para executar um projeto piloto do MTP, executar um projeto do MTP do piloto, implantar, preparar, acionista, linha do tempo, ambiente, ponto de extremidade, servidor, gerenciamento, adoção
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: 7149524de868a3670807556f5f423ba0ee4a772a
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131212"
---
# <a name="prepare-your-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Prepare seu laboratório de avaliação do Microsoft 365 defender ou o ambiente piloto

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Criar um laboratório de avaliação do Microsoft 365 defender ou um ambiente piloto e implantá-lo é um processo de três fases:

|![Fase 1: preparar](../../media/phase-diagrams/prepare.png)<br/>Fase 1: preparar |[![Fase 2: configurar](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)<br/>[Fase 2: configurar](setup-mtpeval.md) |[![Fase 3: integração](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)<br/>[Fase 3: integração](config-mtpeval.md) | [![Voltar ao piloto](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[Voltar ao manual do piloto](mtp-pilot.md) |
|--|--|--|--|
|*Você está aqui!* | || |

Você está atualmente na fase de preparação.


A preparação é fundamental para qualquer implantação bem-sucedida. Esta seção orientará você sobre o que você precisa considerar ao se preparar para criar um laboratório de avaliação ou ambiente piloto para sua implantação do Microsoft 365 defender.

## <a name="prerequisites"></a>Pré-requisitos
Saiba mais sobre os requisitos de licenciamento, hardware e software e outras definições de configuração para provisionar e usar o Microsoft 365 defender. Confira os requisitos mínimos para o [microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites), [Microsoft defender para ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements), [Microsoft defender para Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description), [Microsoft defender para identidade](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites), [Microsoft Cloud app Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites).

## <a name="stakeholders-and-sign-off"></a>Participantes e aprovação
Identifique todos os participantes que estão envolvidos no projeto e que talvez precisem ser desligados, revisados ou permaneçam informados, seja para avaliação ou executando um projeto piloto.

>[!NOTE]
>Nem todas as organizações podem ter a maturidade da organização de segurança para ter essas funções. Nesse caso, consulte sua equipe de liderança no responsabilidades de revisão e aprovação.

Adicione participantes à tabela abaixo, conforme apropriado para sua organização.

-   Portanto = aprovação neste projeto

-   R = revise este projeto e forneça a entrada

-   I = informamos este projeto

| Nome                 | Role                                                                                                                                                                                                          | Action |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| Insira o nome e o email | **Diretor de segurança de informações (ciso)** *um representante executivo que atua como patrocinador dentro da organização para a nova implantação de tecnologia.*                                                  | Então     |
| Insira o nome e o email | **Chefe do CDOC (Cyber Defense Operations Center)** *um representante da equipe do CDOC responsável por definir como essa alteração está alinhada com os processos da equipe de operações de segurança do cliente.*       | Então     |
| Insira o nome e o email | **Arquiteto de segurança** *um representante da equipe de segurança responsável por definir como essa alteração é alinhada à arquitetura de segurança principal na organização.*                         | R      |
| Insira o nome e o email | **Arquiteto de área de trabalho** *um representante da equipe de ti encarregado de definir como essa alteração é alinhada à arquitetura principal de local de trabalho na organização.*                             | R      |
| Insira o nome e o email | **Analista de segurança** *um representante da equipe do CDOC que pode fornecer comentários sobre os recursos de detecção, a experiência do usuário e a utilidade geral dessa alteração de uma perspectiva de operações de segurança.* | I      |

## <a name="prepare-your-azure-active-directory"></a>Preparar o Azure Active Directory
Pule esta etapa se você já tiver habilitado a sincronização entre o Active Directory e o Active Directory do Azure no local. Analise a documentação de práticas recomendadas existentes no Azure Active Directory. As etapas a seguir são otimizadas para avaliar ou executar um projeto piloto do Microsoft 365 defender.

1. Vá para o portal [do Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) > **Azure ad Connect**. 
![Imagem da página do portal do Azure Active Directory](../../media/mtp-eval-1.png) <br> 

2. Clique em **baixar** do **Microsoft Azure Active Directory Connect** e transfira-o para o seu controlador de domínio.
![Imagem da página de download do Azure active Directoru Connect](../../media/mtp-eval-2.png) <br>

3. No controlador de domínio, siga o assistente do Azure Active Directory Connect. Leia os termos de licença e o aviso de privacidade e marque a caixa de seleção se você concordar. Clique em **Continuar**.
![Imagem da página de boas-vindas do Azure AD Connect](../../media/mtp-eval-3.png) <br>

4. Navegue até **configurações expressas**.
![Imagem da página de configurações Express](../../media/mtp-eval-4.png) <br>

5. Insira suas credenciais de administrador global. Clique em **Avançar**.
![Imagem da conexão com a página do Azure AD onde você deve inserir suas credenciais de administrador global](../../media/mtp-eval-5.png) <br>

6. Insira as credenciais de administrador corporativo dos serviços de domínio do Active Directory. Clique em **Avançar**.
![Imagem da conexão com a página do AD DS onde você deve inserir suas credenciais](../../media/mtp-eval-6.png) <br>

7. Clique em **instalar** para confirmar a configuração.
![Imagem da página de confirmação de configuração](../../media/mtp-eval-7.png) <br>

8. Parabéns, você configurou com êxito o Azure Active Directory Connect.
![Imagem de uma página de conexão do Azure Active Directory configurada com êxito](../../media/mtp-eval-8.png) <br>

Agora você pode [Adicionar usuários e grupos ao Active Directory](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) e [Configurar uma política Sam-R](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc).  


## <a name="configuration-order"></a>Ordem de configuração
A tabela a seguir indica a ordem que a Microsoft recomenda para configurar os componentes do Microsoft 365 defender para o laboratório de avaliação ou implantação de ambiente piloto.

| Componente                               | Descrição                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Classificação da ordem de configuração |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
|Microsoft Defender para Office 365|O Microsoft Defender para Office 365 protege sua organização contra ameaças maliciosas representadas por mensagens de email, links (URLs) e ferramentas de colaboração. <br> [Saiba Mais.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)                                                                                                                                                                                                                                             | 1                   |
|Microsoft Defender para Identidade|O Microsoft defender para identidade usa sinais do Active Directory para identificar, detectar e investigar ameaças avançadas, identidades comprometidas e ações mal-intencionadas intencionais direcionadas para sua organização. <br> [Saiba mais](https://docs.microsoft.com/azure-advanced-threat-protection/).| duas |
|Segurança no aplicativo na nuvem da Microsoft| O Microsoft Cloud app Security é um CASB (agente de segurança de acesso à nuvem) que opera em várias nuvens. Ele oferece visibilidade avançada, controle sobre a viagem de dados e análises sofisticadas para identificar e combater o ciberataques em todos os seus serviços de nuvem. <br> [Saiba mais](https://docs.microsoft.com/cloud-app-security/).                                                                                                                                                                                                                                                                                                                                                                       |3D                   |
|Microsoft Defender para Ponto de Extremidade | Os recursos de detecção e resposta do Microsoft defender para pontos de extremidade de ponto de extremidade fornecem detecções de ataques avançados quase em tempo real e acionáveis. Os analistas de segurança podem priorizar alertas de maneira eficaz, obter visibilidade de todo o escopo de uma violação e executar ações de resposta para remediar ameaças. <br> [Saiba Mais.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                    |                                                                                                                                                                                                                                    

## <a name="next-step"></a>Próxima etapa
|![Fase 2: configuração](../../media/setup.png) <br>[Fase 2: configuração](setup-mtpeval.md) | Configurar o laboratório de avaliação do Microsoft 365 defender ou o ambiente piloto
|:-------|:-----|

