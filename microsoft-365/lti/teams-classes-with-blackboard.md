---
title: Integrar Microsoft Teams classes com Blackboard Learn Ultra
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Integrar Microsoft Teams classes com Blackboard Learn Ultra
ms.openlocfilehash: da98fae3fa5d6be2513147be58747512bea99e16
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314483"
---
# <a name="use-microsoft-teams-classes-with-blackboard-learn-ultra"></a>Usar Microsoft Teams classes com Blackboard Learn Ultra

O trabalho em equipe está no centro de todas as organizações modernas. Ao promover a colaboração, é uma característica de definição de cada instituição bem-sucedida. Você pode aprimorar todos os recursos e recursos do Blackboard Learn Ultra emparelhando-os com Microsoft Teams classes.

Suas aulas podem incluir conversas em tempo real, reuniões em vídeo ou interações assíncronas. Você pode adicionar experiências de compartilhamento e cocriação de arquivos para seus alunos, tudo em um só lugar. Microsoft Teams aulas com Learn Ultra redefinem a dinâmica do ensino e o que significa aprendizagem eficaz.

> [!IMPORTANT]
> Verifique se você definiu com êxito o campo Email da Instituição em seu Sistema de Informações do Aluno (SIS) `help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student\_Information\_System/SIS\_Planning`
>
>A integração Microsoft Teams classes depende do campo de email da instituição em seu SIS para mapear para o UPN (Nome de Entidade de Usuário) do Microsoft Azure Active Directory (AAD) correto. Se nenhum email da instituição tiver sido provisionado, isso será padrão para o email existente. É recomendável que esse campo seja definido para cada usuário garantir que seus dados sejam sincronizados corretamente e que não haja conflito de dados de email entre o Microsoft AAD e o Blackboard Learn Ultra.
>
> Se você não tiver definido esse campo adequadamente no mapeamento do SIS, a integração continuará a funcionar, mas os usuários podem não aparecer nas classes Teams criadas, e erros poderão ocorrer.

## <a name="supporting-institutional-data-mapping--institution-email-sis-field"></a>Suporte ao Mapeamento de Dados Institucionais – Campo do SIS de Email da Instituição

Como parte da evolução com integrações de provedores  de nuvem, o Blackboard Learn Ultra criou um novo campo email de instituição, tanto na integração da Estrutura de Sistema de Informações do Aluno quanto em APIs REST públicas, permitindo que as instituições gerenciem o processo de sincronização de dados efetivamente entre Blackboard Learn Ultra e Microsoft AAD.

### <a name="what-does-the-institution-email-mean-and-what-does-it-support"></a>O que significa o Email da Instituição e o que ele dá suporte?

O **campo Email da** Instituição permite mapeamentos de campo personalizados entre as fontes de dados com suporte externo de um cliente e o Blackboard Learn Ultra. Se fontes de dados são provedores de nuvem, como a Microsoft, o Nome de Princípio do Usuário (UPN) é um identificador exclusivo principal para cada usuário que consiste em um prefixo UPN (o nome da conta do usuário) e um sufixo UPN (um nome de domínio DNS) unido com um símbolo @. Isso cria um endereço de email exclusivo para cada usuário específico dentro do Microsoft Azure Active Directory.

Para garantir que os dados sejam precisos e que as inscrições ou associações entre as classes Blackboard Learn Ultra e Microsoft Teams sejam atingidas corretamente, o endereço de email de um usuário deve corresponder entre ambos os sistemas. No Blackboard Learn Ultra, os usuários podem alterar ou substituir o endereço de email existente na interface do usuário, o que pode resultar em erros de sincronização e o usuário não ser adicionado corretamente a uma Equipe de Classe. O **mapeamento de campo Email** da Instituição garante que esse nível de verificação de segurança e validação possa ser gerenciado corretamente, independentemente de os usuários ter alterado seus emails no Blackboard Learn Ultra ou não.

 Quando dois endereços de email são diferentes, ambos:

- Uma decisão deve ser tomada sobre qual fonte tem precedência e será tomada como emails de pessoa e instituição.
  Ou
- Uma instituição pode definir um mapeamento de campo personalizado em seu Email da Instituição, o que pode resolver um possível conflito.

O **mapeamento de campo Email** da Instituição agora está disponível para todos os tipos de integração do SIS existentes no Advanced Configuration **Configurações** Users Learn Object  >  **Type** Field  >  **Mapping**.

> [!NOTE]
> É importante observar que, por padrão, o Email  da Instituição é definido como o Email da Pessoa para todos os formatos do SIS e deve ser exclusivo para cada pessoa.  Todas as integrações existentes que estão configuradas e em execução terão esse mapeamento de dados in-loco, pois o SIS não importará os usuários se o email for duplicado. Se uma instituição exigir a capacidade de alterar o Email da Instituição para **personalizado,** ele precisará gerenciá-lo por meio da configuração **avançada Configurações** no SIS.

## <a name="requirements"></a>Requirements

A Microsoft Teams de classes está disponível apenas para cursos **de Modo de Exibição de Curso Ultra.** Sua instituição precisa concluir esses requisitos para usá-lo:

- Ter Blackboard Learn Ultra Learn SaaS with Ultra Base Navigation enabled

- Habilitar LTI para uso em cursos.

  a. Vá para o **Painel de Administrador**  >  **Provedores de Ferramentas LTI** Gerenciar Propriedades  >  **Globais**.

  b. Selecione **LTI Habilitado em Cursos** e, opcionalmente, selecione **Habilitado em Organizações**.

  c. Selecione **Enviar**.

- Deve ter LTI configurado

- Adicionar Blackboard Learn Ultra Teams Classes LTI Integration

- Adicionar Microsoft Teams classes LTI 1.3 Tool

- Adicionar a Ferramenta DE API REST e o Compartilhamento de Recursos de Origem Cruzada

- Configurar e aprovar a integração Microsoft Teams classes

## <a name="add-the-blackboard-learn-ultra-teams-classes-lti-13-tool"></a>Adicionar a Ferramenta Learn Ultra Teams Classes LTI 1.3

1. No Painel **de Administrador,** selecione **Provedores de Ferramentas LTI.**

2. Selecione **registrar a Ferramenta LTI 1.3**.

3. No campo **ID do** Cliente, digite ou copie e colar esta ID:

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. Revise todas as configurações que foram pré-preenchidas e em **Status** da Ferramenta e selecione **Habilitado**.

5. Em **Políticas de Instituição,** selecione **Função em Curso, Nome** e Endereço de **Email** e selecione **Sim** para ambos.

6. Selecione **Permitir acesso de serviço de nível e** Permitir Acesso ao Serviço de **Associação.**

## <a name="add-the-microsoft-teams-classes-lti-13-tool"></a>Adicionar a ferramenta Microsoft Teams Classes LTI 1.3

1. No Painel **de Administrador,** selecione **Provedores de Ferramentas LTI.**

2. Selecione **registrar a Ferramenta LTI 1.3**.

3. No campo **ID do** Cliente, digite ou copie e colar esta ID:

   `027328b7-c2e3-4c9e-aaa1-07802dae6c89`

4. Revise todas as configurações que foram pré-preenchidas e em *Status da Ferramenta* e selecione *Habilitado.*

5. Em **Políticas de Instituição,** selecione **Função no Curso, Nome** e Endereço de **Email.** Selecione **Sim** para ambos.

6. Selecione **Permitir acesso de serviço de nível e** Permitir Acesso ao Serviço de **Associação.**

## <a name="add-the-rest-api-tool"></a>Adicionar a ferramenta DE API REST

1. No Painel **de Administrador,** navegue até **Integrações** e selecione **Rest API Integrations**.

2. Selecione **Criar Integração**.

3. No campo **ID do** aplicativo, digite ou copie e colar esta ID:

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. Digite um usuário para essa integração.

   Esse usuário será aquele com acesso à API inicial do qual o aplicativo está associado.

5. Selecione **Enviar**.

## <a name="add-the-cross-origin-resource-sharing"></a>Adicionar o compartilhamento de recursos entre origens

1. No painel **Administrador,** navegue até **Integrações** e selecione * Compartilhamento de Recursos de *origem cruzada.*

2. Selecione **Criar Configuração**.

3. No campo **Origem,** tipo de cópia e colar esta URL:

   `https://bb-ms-teams-ultra-ext.api.blackboard.com`

4. No campo **Headers Permitidos,** digite **Autorização**.

5. Definir **Disponível como** **Sim**.

6. Selecione **Enviar**.

## <a name="configure-and-approve-microsoft-teams-classes-integration"></a>Configurar e aprovar a integração Microsoft Teams classes

Para integrar com êxito sua instância Learn Ultra do Quadro Microsoft Teams com classes de Microsoft Teams, você precisará garantir que o aplicativo Blackboard Learn Ultra seja aprovado para acesso em seu locatário Microsoft Azure. Este é um processo que precisará ser concluído pelo administrador global Microsoft 365 sua instituição.

Esse processo pode ser feito antes ou depois de você ter configurado os aplicativos LTI em sua Instância De Aprendizado de Quadro Preto.

### <a name="before-configuring-the-lti-applications"></a>Antes de configurar os aplicativos LTI

Se você optar por aprovar o aplicativo Azure classes ultra Teams Blackboard antes de configurar as integrações LTI, será necessário redirecionar para o Ponto de Extremidade de Consentimento do Administrador da Plataforma de Identidade da **Microsoft.** A URL é mostrada:

`https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

> [!NOTE]
> Você substituirá **{Tenant}** pela ID Microsoft Azure locatário específica.

### <a name="after-configuring-the-lti-applications"></a>Depois de configurar os aplicativos LTI

1. No Painel **administrador,** navegue até **Ferramentas e Utilitários** e **selecione Microsoft Teams Administrador de Integração.**

2. Selecione **Habilitar Microsoft Teams**.

3. Adicione sua **ID do Locatário da Microsoft** ao campo de texto disponível.

4. Escolha uma das seguintes opções:

   - Se o aplicativo tiver pré-consentimento, ele mostrará uma pequena marca de seleção. Se a marca de seleção for exibida, selecione **Enviar**.

   - Se o consentimento não tiver sido aprovado, siga as etapas descritas para gerar a URL para consentimento e enviá-la ao administrador global Microsoft 365 para aprovação.

5. Depois de confirmar a aprovação, selecione **Repetir para** confirmar e selecione **Enviar**.
