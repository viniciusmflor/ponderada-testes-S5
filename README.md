# Ponderada Testes S5

Neste repositório eu organizei a atividade da semana sobre testes de software com .NET 5. A ideia foi seguir o tutorial do Renato Groffe, fazer os forks dos exemplos e rodar os testes no meu ambiente.

Aqui estão os links dos repositórios que usei, uma explicação curta de cada tipo de teste, dois exemplos de cenário e os prints do terminal com os testes sendo executados.

Tutorial base: [Testes de Software com .NET 5: exemplos de utilização](https://renatogroffe.medium.com/testes-de-software-com-net-5-exemplos-de-utiliza%C3%A7%C3%A3o-9b5514119ba2)

## Barema

(De 0 a 3) - Implementação dos 3 tipos de testes apresentados no artigo (1 ponto para cada tipo de teste implementado)

(De 0 a 2) - Explicação clara e objetiva sobre a aplicação dos testes

(De 0 a 2) - Organização do arquivo readme, com imagens dos testes e coerência dos textos.

## Repositórios utilizados

- Teste de unidade com xUnit: [viniciusmflor/DotNet5-xUnit](https://github.com/viniciusmflor/DotNet5-xUnit)
- Teste com Mock Objects usando Moq: [viniciusmflor/DotNet5-Moq-xUnit-FluentAssertions](https://github.com/viniciusmflor/DotNet5-Moq-xUnit-FluentAssertions)
- Teste BDD com SpecFlow: [viniciusmflor/ASPNETCore5-REST_API-xUnit-SpecFlow-Swagger-Docker_JurosCompostos](https://github.com/viniciusmflor/ASPNETCore5-REST_API-xUnit-SpecFlow-Swagger-Docker_JurosCompostos)

## Teste de Unidade com xUnit

Esse primeiro exemplo é um teste de unidade com xUnit. Ele testa uma parte bem específica do código: a conversão de Fahrenheit para Celsius. Achei esse exemplo bom para entender teste de unidade porque ele não depende de banco, API ou outra parte externa, só da função de conversão mesmo.

Fork utilizado: [viniciusmflor/DotNet5-xUnit](https://github.com/viniciusmflor/DotNet5-xUnit)

Cenários que aparecem no teste:

- Converter 32 °F deve retornar 0 °C.
- Converter 212 °F deve retornar 100 °C.

![Execução do teste de unidade com xUnit](assets/teste-unidade-xunit.png)

## Teste com Mock Objects usando Moq

Nesse segundo exemplo o teste usa Mock Objects com Moq. O objetivo é simular o serviço de consulta de crédito, sem precisar chamar um serviço real. Assim, o teste consegue focar na regra da análise de crédito e verificar se o status retornado está correto. Também foi usado Fluent Assertions para deixar os asserts mais fáceis de ler.

Fork utilizado: [viniciusmflor/DotNet5-Moq-xUnit-FluentAssertions](https://github.com/viniciusmflor/DotNet5-Moq-xUnit-FluentAssertions)

Cenários que aparecem no teste:

- Um CPF inválido deve retornar o status `ParametroEnvioInvalido`.
- Um CPF sem pendências deve retornar o status `SemPendencias`.

![Execução do teste com Moq e Fluent Assertions](assets/teste-mock-moq.png)

## Teste BDD com SpecFlow

O terceiro exemplo é um teste BDD com SpecFlow. Nesse caso, os cenários ficam escritos de um jeito mais próximo da linguagem de negócio, usando Gherkin. O teste valida o cálculo de juros compostos a partir do valor do empréstimo, da quantidade de meses e da taxa de juros.

Fork utilizado: [viniciusmflor/ASPNETCore5-REST_API-xUnit-SpecFlow-Swagger-Docker_JurosCompostos](https://github.com/viniciusmflor/ASPNETCore5-REST_API-xUnit-SpecFlow-Swagger-Docker_JurosCompostos)

Observação: quando rodei esse exemplo, ele tinha uma falha proposital no cálculo. No meu fork eu corrigi usando o arredondamento para duas casas decimais, que já estava indicado no próprio código como a forma correta.

Cenários que aparecem no teste:

- Um empréstimo de R$ 10.000,00 por 12 meses, com taxa de 2,00% ao mês, deve resultar em R$ 12.682,42.
- Um empréstimo de R$ 30.000,00 por 3 meses, com taxa de 3,00% ao mês, deve resultar em R$ 32.781,81.

![Execução do teste BDD com SpecFlow](assets/teste-bdd-specflow.png)
