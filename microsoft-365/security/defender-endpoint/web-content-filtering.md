---
title: Filtragem de conteúdo da Web
description: Use a filtragem de conteúdo da Web no Microsoft Defender ATP para controlar e regular o acesso a sites com base em suas categorias de conteúdo.
keywords: proteção da Web, proteção contra ameaças da Web, navegação na Web, monitoramento, relatórios, cartões, lista de domínios, segurança, phishing, malware, exploração, sites, proteção de rede, Edge, Internet Explorer, Chrome, Firefox, navegador da Web
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: dd1b21b306d40ab03fa518f48c8a0bc985191f69
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053264"
---
# <a name="web-content-filtering"></a>Filtragem de conteúdo da Web

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> **A filtragem de conteúdo da Web está atualmente em visualização pública**<br>
> Esta versão de visualização é fornecida sem um contrato de nível de serviço e não é recomendada para cargas de trabalho de produção. Determinados recursos podem não ser suportados ou podem ter recursos restritos.
> Para obter mais informações, consulte Recursos de visualização do [Microsoft Defender for Endpoint](preview.md).

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

A filtragem de conteúdo da Web faz parte dos recursos [de proteção](web-protection-overview.md) da Web no Microsoft Defender para Ponto de Extremidade. Ele permite que sua organização acompanhe e regular o acesso a sites com base em suas categorias de conteúdo. Muitos desses sites, embora não sejam mal-intencionados, podem ser problemáticos devido a regulamentos de conformidade, uso de largura de banda ou outras preocupações.

Configure políticas em seus grupos de dispositivos para bloquear determinadas categorias. O bloqueio de uma categoria impede que os usuários dentro de grupos de dispositivos especificados acessem URLs associadas à categoria. Para qualquer categoria que não seja bloqueada, as URLs são auditadas automaticamente. Os usuários podem acessar as URLs sem interrupção e você reunirá estatísticas de acesso para ajudar a criar uma decisão de política mais personalizada. Seus usuários verão uma notificação de bloqueio se um elemento na página que eles estão exibindo estiver fazendo chamadas para um recurso bloqueado.

A filtragem de conteúdo da Web está disponível nos principais navegadores da Web, com blocos executados por Windows Defender SmartScreen (Microsoft Edge) e Proteção de Rede (Chrome, Firefox, Brave e Opera). Para obter mais informações sobre o suporte ao navegador, consulte a seção pré-requisitos.

Resumindo os benefícios:

- Os usuários são impedidos de acessar sites em categorias bloqueadas, quer eles estão navegando no local ou fora
- Convenientemente, implante políticas em grupos de usuários usando grupos de dispositivos definidos no Microsoft Defender para configurações de controle de acesso baseado em função de [ponto de extremidade](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)
- Acessar relatórios da Web no mesmo local central, com visibilidade sobre blocos reais e uso da Web

## <a name="user-experience"></a>Experiência do usuário

A experiência de bloqueio para navegadores com suporte de terceiros é fornecida pela Proteção de Rede, que fornece um sistema notificando o usuário de uma conexão bloqueada. 

Para uma experiência mais amigável no navegador, considere usar o Microsoft Edge.

## <a name="prerequisites"></a>Pré-requisitos

Antes de tentar esse recurso, certifique-se de ter os seguintes requisitos:

- Licença do Windows 10 Enterprise E5 OU Complemento de Segurança do Microsoft 365 E3 + Microsoft 365 E5.
- Acesso ao portal do Centro de Segurança do Microsoft Defender
- Dispositivos que executam a Atualização de Aniversário do Windows 10 (versão 1607) ou posterior com a atualização mais recente do MoCAMP.

Se Windows Defender SmartScreen não estiver ligado, a Proteção de Rede assumirá o bloqueio. Ele requer [habilenciar a Proteção de](enable-network-protection.md) Rede no dispositivo. Chrome, Firefox, Brave e Opera atualmente são navegadores de terceiros nos quais esse recurso está habilitado.

## <a name="data-handling"></a>Tratamento de dados

Seguiremos qualquer região que você tenha escolhido para usar como parte das configurações de tratamento de dados do [Microsoft Defender for Endpoint.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/data-storage-privacy) Seus dados não sairão do data center nessa região. Além disso, seus dados não serão compartilhados com terceiros, incluindo nossos provedores de dados.

## <a name="turn-on-web-content-filtering"></a>Ativar a filtragem de conteúdo da Web

No menu de navegação à esquerda, selecione **Configurações > Geral > Recursos Avançados**. Role para baixo até ver a entrada para filtragem **de conteúdo da Web**. Alterne a alternância **para As preferências** **Ligar e Salvar.**

### <a name="configure-web-content-filtering-policies"></a>Configurar políticas de filtragem de conteúdo da Web

As políticas de filtragem de conteúdo da Web especificam quais categorias de site são bloqueadas em quais grupos de dispositivos. Para gerenciar as políticas, acesse **Configurações > Regras > filtragem de conteúdo da Web.**

Use o filtro para localizar políticas que contêm determinadas categorias bloqueadas ou são aplicadas a grupos de dispositivos específicos.

### <a name="create-a-policy"></a>Criar uma política

Para adicionar uma nova política:

1. Selecione **Adicionar política** na página **filtragem de** conteúdo da Web em **Configurações**.
2. Especifique um nome.
3. Selecione as categorias a bloquear. Use o ícone de expansão para expandir totalmente cada categoria pai e selecione categorias de conteúdo da Web específicas.
4. Especifique o escopo da política. Selecione os grupos de dispositivos para especificar onde aplicar a política. Somente dispositivos nos grupos de dispositivos selecionados serão impedidos de acessar sites nas categorias selecionadas.
5. Revise o resumo e salve a política. A atualização da política pode levar até 2 horas para ser aplicada aos dispositivos selecionados.

Dica: você pode implantar uma política sem selecionar qualquer categoria em um grupo de dispositivos. Essa ação criará uma política somente de auditoria, para ajudá-lo a entender o comportamento do usuário antes de criar uma política de bloqueio.

>[!NOTE]
>Se você estiver removendo uma política ou alterando grupos de dispositivos ao mesmo tempo, isso pode causar um atraso na implantação da política.

>[!IMPORTANT]
>Bloquear a categoria "Não categorizada" pode levar a resultados inesperados e indesejáveis.  

### <a name="allow-specific-websites"></a>Permitir sites específicos

É possível substituir a categoria bloqueada na filtragem de conteúdo da Web para permitir um único site criando uma política de indicador personalizada. A política de indicador personalizado irá sobressuar a política de filtragem de conteúdo da Web quando ela for aplicada ao grupo de dispositivos em questão.

1. Criar um indicador personalizado no Centro de Segurança do Microsoft Defender, indo para **Configurações**  >  **Indicadores**  >  **URL/Item de**  >  **adoção de domínio**
2. Insira o domínio do site
3. Definir a ação de política como **Permitir**.  

### <a name="reporting-inaccuracies"></a>Imprecisões de relatórios

Se você encontrar um domínio que tenha sido categorizado incorretamente, você poderá relatar imprecisões diretamente para nós na página Relatórios de Filtragem de Conteúdo da Web. Esse recurso está disponível apenas no novo centro de segurança do Microsoft 365 (security.microsoft.com).

Para relatar uma imprecisão, navegue até Relatórios > Web protection > Web **Content Filtering Details > Domains**. Na guia domínios de nossos relatórios de Filtragem de Conteúdo da Web, você verá uma elipse ao lado de cada um dos domínios. Passe o mouse sobre essa reellipse e selecione **Report Inaccuracy**.

Um painel será aberto onde você pode selecionar a prioridade e adicionar detalhes adicionais, como a categoria sugerida para re-categorização. Depois de concluir o formulário, selecione **Enviar**. Nossa equipe revisará a solicitação em um dia útil. Para desbloquear imediatamente, crie um [indicador de autorização personalizado.](indicator-ip-domain.md)

## <a name="web-content-filtering-cards-and-details"></a>Cartões e detalhes de filtragem de conteúdo da Web

Selecione **Relatórios > Proteção da Web** para exibir cartões com informações sobre filtragem de conteúdo da Web e proteção contra ameaças da Web. Os cartões a seguir fornecem informações resumidas sobre a filtragem de conteúdo da Web.

### <a name="web-activity-by-category"></a>Atividade da Web por categoria

Este cartão lista as categorias de conteúdo da Web pai com o maior aumento ou diminuição no número de tentativas de acesso. Entenda as alterações drásticas nos padrões de atividade da Web em sua organização dos últimos 30, 3 meses ou 6 meses. Selecione um nome de categoria para exibir mais informações.

Nos primeiros 30 dias de uso desse recurso, sua organização pode não ter dados suficientes para exibir essas informações.

![Imagem da atividade da Web por cartão de categoria](images/web-activity-by-category600.png)

### <a name="web-content-filtering--summary-card"></a>Cartão de resumo de filtragem de conteúdo da Web

Esse cartão exibe a distribuição de tentativas de acesso bloqueado nas diferentes categorias de conteúdo da Web pai. Selecione uma das barras coloridas para exibir mais informações sobre uma categoria da Web pai específica.

![Imagem do cartão de resumo de filtragem de conteúdo da Web](images/web-content-filtering-summary.png)

### <a name="web-activity-summary-card"></a>Cartão de resumo de atividade da Web

Esse cartão exibe o número total de solicitações de conteúdo da Web em todas as URLs.

![Imagem do cartão de resumo da atividade da Web](images/web-activity-summary.png)

### <a name="view-card-details"></a>Exibir detalhes do cartão

Você pode acessar os **detalhes do Relatório** para cada cartão selecionando uma linha de tabela ou uma barra colorida do gráfico no cartão. A página de detalhes do relatório para cada cartão contém dados estatísticos abrangentes sobre categorias de conteúdo da Web, domínios de site e grupos de dispositivos.

![Imagem dos detalhes do relatório de proteção da Web](images/web-protection-report-details.png)

- **Categorias da Web**: lista as categorias de conteúdo da Web que tiveram tentativas de acesso em sua organização. Selecione uma categoria específica para abrir um sobrevoo de resumo.

- **Domínios**: lista os domínios da Web que foram acessados ou bloqueados em sua organização. Selecione um domínio específico para exibir informações detalhadas sobre esse domínio.

- **Grupos de dispositivos**: lista todos os grupos de dispositivos que geraram atividade da Web em sua organização

Use o filtro de intervalo de tempo na parte superior esquerda da página para selecionar um período de tempo. Você também pode filtrar as informações ou personalizar as colunas. Selecione uma linha para abrir um painel de sobrevoo com ainda mais informações sobre o item selecionado.

## <a name="errors-and-issues"></a>Erros e problemas

### <a name="limitations-and-known-issues-in-this-preview"></a>Limitações e problemas conhecidos nesta visualização

- Somente o Microsoft Edge é suportado se a configuração do sistema operacional do seu dispositivo for Server (cmd > Systeminfo > configuração do sistema operacional). A Proteção de Rede só tem suporte no modo Inspecionar em dispositivos Server, que é responsável por proteger o tráfego em navegadores de terceiros com suporte.

- Os dispositivos não atribuídos terão dados incorretos mostrados no relatório. No pivot Detalhes do relatório > grupos de dispositivos, você pode ver uma linha com um campo Grupo de Dispositivos em branco. Esse grupo contém seus dispositivos não atribuídos antes que eles sejam colocados no grupo especificado. O relatório dessa linha pode não conter uma contagem precisa de dispositivos ou contagens de acesso.

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral da proteção da Web](web-protection-overview.md)
- [Proteção contra ameaças da Web](web-threat-protection.md)
- [Monitorar a segurança da Web](web-protection-monitoring.md)
- [Responder a ameaças da Web](web-protection-response.md)
