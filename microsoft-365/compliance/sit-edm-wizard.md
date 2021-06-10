---
title: Use o Assistente de Correspondência Exata de Dados e Tipo de Informação Confidencial
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Aprenda como usar o assistente do esquema de correspondência exata de dados e tipo de informação confidencial.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5fdf289c403d8c09342a1eac1434c4219bb7b13c
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861654"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a>Use o Assistente de Correspondência Exata de Dados e Tipo de Informação Confidencial

[Criar um tipo personalizado de informação confidencial com classificação baseada em EDM (Correspondência Exata de Dados) ](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)  envolve várias etapas.  Você pode usar esse assistente para criar seu esquema e arquivos de padrão de tipo de informação confidenciais (SIT) (pacote de regras) para ajudar a simplificar o processo.

> [!NOTE]
> O Assistente de Correspondência Exata de Dados e Tipo de Informações Confidenciais está disponível apenas para as nuvens WW E GCC.

Esse assistente pode ser usado em vez do:

- [Definição do esquema para seu banco de dados de informações confidenciais](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [Configurar um padrão (pacote de regras)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

etapas na [Parte 1: configurar a classificação baseada em EDM](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).

## <a name="pre-requisites"></a>Pré-requisitos

1. Familiarize-se com as etapas para criar um tipo personalizado de informações confidenciais com o EDM [fluxo de trabalho em um relance](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).

2. Execute as etapas na seção [Salvar dados confidenciais no formato .csv](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format).

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a>Use o esquema exato de correspondência de dados e o assistente do padrão do tipo de informações confidenciais

1. No centro de Conformidade do Microsoft 365 para seu locatário, acesse **Classificação de dados** > **Correspondência de dados exata**.

2. Escolha **Criar o esquema EDM** para abrir o submenu configuração do assistente de esquema.

![Submenu de configuração do assistente para criação de esquemas EDM](../media/edm-schema-wizard-1.png)

3. Preencha um **Nome** e uma **Descrição** apropriados.

4. Escolha **Ignorar delimitadores e pontuação para todos os** campos de esquema se quiser esse comportamento. Para saber mais sobre como configurar o EDM para ignorar ocorrências ou delimitadores, consulte Creating a custom sensitive information [type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

5. Preencha os valores desejados para seu **Campo de esquema #1** e adicione mais campos, conforme necessário. 

> [!IMPORTANT]
> Pelo menos um, mas não mais de cinco campos de esquema devem ser designados como pesquisáveis.

6. Escolha salvar. O esquema agora será listado.

7. Escolha **Tipos de informações confidenciais do EDM** e **Criar tipo de informações confidenciais EDM** para abrir o assistente de configuração do tipo de informações confidenciais.

8. Escolha **Escolher um esquema EDM existente** e escolha o esquema criado nas etapas 2-6 da lista.

9. Escolha **Próximo** e escolha **Criar padrão**.

10. Escolha o **Nível de confiança** e **Elemento principal**.  Para saber mais sobre como configurar um padrão, consulte [Criar um tipo personalizado de informações confidenciais no Centro de Conformidade](create-a-custom-sensitive-information-type.md)

11.  Escolha o **Tipo de informações confidenciais do elemento principal** para associá-lo. Consulte [Definições da Entidade de Tipo de Informações Confidenciais](sensitive-information-type-entity-definitions.md) para saber mais sobre os tipos de informações confidenciais disponíveis..

12. Escolha **Concluído**.

13. Escolha o **Nível de confiança e a proximidade de caractere** desejados.  Esse será o valor padrão para todo o tipo de informações confidenciais do EDM

13. Escolha **Criar padrão** se quiser criar padrões adicionais para seu tipo de informações confidenciais do EDM.

14. Escolha **Próximo** e preencha o **Nome** e **Descrição para os administradores**.

15. Examine e escolha **Enviar**.

Você pode excluir ou editar o padrão de tipo de informações confidenciais, selecionando-o que superfícies os controles editar e excluir.

> [!IMPORTANT]
> Se você quiser remover um esquema e já estiver associado a um tipo de informações confidenciais do EDM, primeiro é necessário excluir o tipo de informações confidenciais do EDM. em seguida, você pode excluir o esquema.

## <a name="post-creation-steps"></a>Etapas de pós-criação

Depois de usar o assistente para criar o esquema EDM e os arquivos padrão (pacote de regras), você ainda precisará executar as etapas na [Part 2: hash e carregar os dados confidenciais](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) antes de poder usar o tipo personalizado de informações confidenciais do EDM.

Depois de verificar se sua tabela de informações confidenciais foi carregada corretamente, você pode testar se ela está funcionando corretamente.

1. Open **Compliance center** Data  >  **classification** Sensitive Information  >  **Types**.
2. Selecione seu EDM SIT na lista e selecione **Testar** no painel de sobrevoos. 
3. Upload um item que contém dados que você deseja detectar, por exemplo, crie um item que contenha alguns dos dados em sua tabela de informações confidenciais. Se você usou o recurso de match configurável em seu esquema para definir delimitadores ignorados, certifique-se de que o item inclua exemplos com e sem esses delimitadores.
4. Depois que o arquivo tiver sido carregado e verificado, verifique se há corresponde ao seu EDM SIT.
5. Se a **função Test** no SIT detectar uma combinação, verifique se ela não está aparando-a ou extraindo-a incorretamente. Por exemplo, extraindo apenas uma subdstring da cadeia de caracteres completa que ela deve detectar ou detectando apenas a primeira palavra em uma cadeia de caracteres de várias palavras ou incluindo símbolos extras ou caracteres na extração. Consulte [Linguagem de Expressão Regular - Referência Rápida](/dotnet/standard/base-types/regular-expression-language-quick-reference) para a referência de idioma de expressão regular. 

### <a name="troubleshooting"></a>Solução de problemas

Se você não encontrar nenhuma coincidente, tente o seguinte:
- Confirme se seus dados confidenciais foram carregados corretamente usando os comandos explicados na orientação para carregar seus dados confidenciais usando a [ferramenta EDM](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).
- Verifique se os exemplos inseridos no item estão presentes em sua tabela de informações confidenciais e se os delimitadores ignorados estão corretos.
- **Teste** o SIT usado quando configurou o elemento principal em cada um dos seus padrões. Isso confirmará se o SIT é capaz de corresponder aos exemplos no item. 
  -  Se o SIT selecionado para um elemento primário no tipo EDM não encontrar uma combinação no item ou encontrar menos combinações do que você esperava, verifique se ele dá suporte a separadores e delimitadores existentes no conteúdo. Certifique-se de incluir os delimitadores ignorados definidos em seu esquema. 
  -  Se a **função Test** não detectar conteúdo algum, verifique se o SIT selecionado inclui requisitos para palavras-chave adicionais ou outras validações. Para os SITs integrados, consulte Definições de entidade de tipos de informações confidenciais para verificar quais são os [requisitos mínimos](sensitive-information-type-entity-definitions.md) para correspondência de cada tipo.
