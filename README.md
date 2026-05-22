# Aplicando Testes

Este repositório documenta a execução de três exemplos de testes de software apresentados no tutorial de Renato Groffe sobre .NET 5.

Os códigos testados estão em forks próprios, e este README reúne os links, os cenários observados e os prints da execução no terminal local.

## Repositórios utilizados

- Teste de unidade com xUnit: [viniciusmflor/DotNet5-xUnit](https://github.com/viniciusmflor/DotNet5-xUnit)
- Teste com Mock Objects usando Moq: [viniciusmflor/DotNet5-Moq-xUnit-FluentAssertions](https://github.com/viniciusmflor/DotNet5-Moq-xUnit-FluentAssertions)
- Teste BDD com SpecFlow: [viniciusmflor/ASPNETCore5-REST_API-xUnit-SpecFlow-Swagger-Docker_JurosCompostos](https://github.com/viniciusmflor/ASPNETCore5-REST_API-xUnit-SpecFlow-Swagger-Docker_JurosCompostos)

## Teste de Unidade com xUnit

O teste de unidade valida uma regra pequena e isolada da aplicação. Neste exemplo, o xUnit foi usado para conferir se a conversão de Fahrenheit para Celsius retorna os valores esperados sem depender de banco de dados, API externa ou interface.

Fork utilizado: [viniciusmflor/DotNet5-xUnit](https://github.com/viniciusmflor/DotNet5-xUnit)

Cenários de exemplo:

- Ao converter 32 °F, o resultado esperado é 0 °C.
- Ao converter 212 °F, o resultado esperado é 100 °C.

![Execução do teste de unidade com xUnit](assets/teste-unidade-xunit.png)
