---
title: Preparar seu ambiente de laboratório de Microsoft 365 de avaliação do Defender
description: Preparar a aprovação de participantes, cronogramas, considerações de ambiente e ordem de adoção ao configurar seu laboratório de avaliação do Microsoft 365 Defender ou ambiente piloto
keywords: Microsoft 365 Preparação de avaliação do Defender, Microsoft 365 preparação piloto do Defender, preparação para a execução de um projeto piloto do Microsoft 365 Defender, executar um projeto piloto do defender do Microsoft 365, implantar, preparar, stakeholder, linha do tempo, ambiente, ponto de extremidade, servidor, gerenciamento, adoção
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 7ebb7074b0e06eda96d21142044bd8b9997e094b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841649"
---
# <a name="prepare-your-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Preparar seu Microsoft 365 de avaliação do Defender ou do ambiente piloto

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Criar um Microsoft 365 de avaliação do Defender ou um ambiente piloto e implantá-lo é um processo de três fases:

|![Fase 1: Preparar](../../media/phase-diagrams/prepare.png)<br/>Fase 1: Preparar |[![Fase 2: Configurar](../../media/phase-diagrams/setup.png)](setup-m365deval.md)<br/>[Fase 2: Configurar](setup-m365deval.md) |[![Fase 3: Integrar](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)<br/>[Fase 3: Integrar](config-m365d-eval.md) | [![Voltar ao piloto](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)<br/>[Voltar ao playbook piloto](m365d-pilot.md) |
|--|--|--|--|
|*Você está aqui!* | || |

No momento, você está na fase de preparação.


A preparação é fundamental para qualquer implantação bem-sucedida. Esta seção orientará você sobre o que você precisa considerar ao se preparar para criar um laboratório de avaliação ou um ambiente piloto para sua implantação Microsoft 365 Defender.

## <a name="prerequisites"></a>Pré-requisitos
Saiba mais sobre os requisitos de licenciamento, hardware e software e outras configurações para provisionar e usar Microsoft 365 Defender. Consulte os requisitos mínimos para [Microsoft 365 Defender,](/microsoft-365/security/defender/prerequisites) [Microsoft Defender para Ponto](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements)de Extremidade, Microsoft Defender para [Office 365,](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) [Microsoft Defender para Identidade,](/azure-advanced-threat-protection/atp-prerequisites) [Microsoft Cloud App Security](/azure-advanced-threat-protection/atp-prerequisites).

## <a name="stakeholders-and-sign-off"></a>Stakeholders e sign-off
Identifique todos os participantes envolvidos no projeto e quem pode precisar assinar, revisar ou permanecer informado, seja para avaliação ou execução de um projeto piloto.

>[!NOTE]
>Nem todas as organizações podem ter a maturidade da organização de segurança para ter essas funções. Nesse caso, consulte sua equipe de liderança sobre as responsabilidades de revisão e aprovação.

Adicione participantes à tabela abaixo conforme apropriado para sua organização.

-   SO = Aprovação neste projeto

-   R = Revisar este projeto e fornecer entrada

-   I = Informado deste projeto

| Nome                 | Função                                                                                                                                                                                                          | Action |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| Inserir nome e email | Diretor de Segurança da Informação **(CISO)** Um representante executivo que serve como patrocinador dentro da organização para a *implantação da nova tecnologia.*                                                  | Então     |
| Inserir nome e email | **Head of Cyber Defense Operations Center (CDOC)** Um representante da equipe do CDOC responsável por definir como essa alteração é alinhada com os processos na equipe de operações de *segurança dos clientes.*       | Então     |
| Inserir nome e email | **Arquiteto de Segurança** Um representante da equipe de Segurança responsável por definir como essa alteração é alinhada com a arquitetura *principal de Segurança na organização.*                         | R      |
| Inserir nome e email | **Arquiteto do Local** de Trabalho Um representante da equipe de TI responsável por definir como essa alteração é alinhada com a arquitetura principal do local de trabalho *na organização.*                             | R      |
| Inserir nome e email | **Analista de Segurança** Um representante da equipe do CDOC que pode fornecer comentários sobre os recursos de detecção, a experiência do usuário e a utilidade geral dessa alteração de uma perspectiva de *operações de segurança.* | I      |

## <a name="prepare-your-azure-active-directory"></a>Preparar sua Azure Active Directory
Ignore esta etapa se você já habilitar a sincronização entre o Active Directory e Azure Active Directory local. Revise a documentação de práticas recomendadas existentes Azure Active Directory. As etapas a seguir são otimizadas para avaliar ou executar um projeto piloto Microsoft 365 Defender.

1. Vá para o [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) portal > **Azure AD Conexão**. 
![Imagem da Azure Active Directory portal](../../media/mtp-eval-1.png) <br> 

2. Clique **em Baixar** do **Microsoft Azure Active Directory Conexão** e transfira-o para seu Controlador de Domínio.
![Imagem da página de download do Azure Active Directoru Conexão download](../../media/mtp-eval-2.png) <br>

3. No controlador de domínio, siga o Azure Active Directory Conexão assistente. Leia os termos de licença e o aviso de privacidade e selecione a caixa de seleção se você concordar. Clique em **Continuar**.
![Imagem do Azure AD Conexão página de boas-vindas](../../media/mtp-eval-3.png) <br>

4. Navegue **até Express Configurações**.
![Imagem da página Configurações Express](../../media/mtp-eval-4.png) <br>

5. Insira suas credenciais de administrador global. Clique em **Avançar**.
![Imagem de Conexão página do Azure AD onde você deve inserir suas credenciais de administrador global](../../media/mtp-eval-5.png) <br>

6. Insira suas credenciais de administrador corporativo dos Serviços de Domínio do Active Directory. Clique em **Avançar**.
![Imagem de Conexão página do AD DS onde você deve inserir suas credenciais](../../media/mtp-eval-6.png) <br>

7. Clique **em Instalar** para confirmar a configuração.
![Imagem da página de confirmação de configuração](../../media/mtp-eval-7.png) <br>

8. Parabéns, você configurou com êxito Azure Active Directory Conexão.
![Imagem de uma página de Azure Active Directory Conexão configurada com êxito](../../media/mtp-eval-8.png) <br>

Agora você pode [adicionar usuários e grupos ao Active Directory](/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) e configurar uma política [SAM-R.](/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc)  


## <a name="configuration-order"></a>Ordem de configuração
A tabela a seguir indica a ordem que a Microsoft recomenda para configurar os componentes Microsoft 365 Defender para seu laboratório de avaliação ou implantação do ambiente piloto.

| Componente                               | Descrição                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Classificação da ordem de configuração |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
|Microsoft Defender para Office 365|O Microsoft Defender para Office 365 protege sua organização contra ameaças maliciosas representadas por mensagens de email, links (URLs) e ferramentas de colaboração. <br> [Saiba Mais.](/microsoft-365/security/office-365-security/defender-for-office-365)                                                                                                                                                                                                                                             | 1                   |
|Microsoft Defender para Identidade?|O Microsoft Defender for Identity usa sinais do Active Directory para identificar, detectar e investigar ameaças avançadas, identidades comprometidas e ações internas mal-intencionadas direcionadas à sua organização. <br> [Saiba mais](/azure-advanced-threat-protection/).| 2 |
|Microsoft Cloud App Security| O Microsoft Cloud App Security é um Agente de Segurança de Acesso à Nuvem (CASB) que opera em várias nuvens. Ele fornece visibilidade avançada, controle sobre o percurso de dados e uma análise sofisticada para identificar e combater ameaças cibernéticas em todos os seus serviços em nuvem. <br> [Saiba mais](/cloud-app-security/).                                                                                                                                                                                                                                                                                                                                                                       |3                   |
|Microsoft Defender para Ponto de Extremidade | Os recursos de detecção e resposta de ponto de extremidade do Microsoft Defender ATP fornecem detecções de ataque avançadas que são quase em tempo real e acionáveis. Os analistas de segurança podem priorizar alertas de maneira eficaz, obter visibilidade de todo o escopo de uma violação e executar ações de resposta para remediar ameaças. <br> [Saiba Mais.](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                    |                                                                                                                                                                                                                                    

## <a name="next-step"></a>Próxima etapa
|![Fase 2: Configurar](../../media/setup.png) <br>[Fase 2: Configurar](setup-m365deval.md) | Configurar seu laboratório de avaliação Microsoft 365 Defender ou o ambiente piloto
|:-------|:-----|
