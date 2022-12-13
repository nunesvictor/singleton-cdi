# singleton-cdi

A experiência que tive foi  a seguinte: ao rodar a aplicação pela primeira vez
e fazer a consulta via `GET` tanto em `/config` como em `/relatorios` o resultado
foi o mesmo:

```json
{
  "formatoRelatorios": "html",
  "tipoGraficos": "pizza"
}
```

Ao realizar o primeiro `PUT` em `/config` com os dados `foo` e `bar` para 
`formatoRelatorios` e `tipoGraficos` respectivamente ao consultar novamente
via `GET` tanto em `/config` como em `/relatorios` o resultado era o mesmo:

```json
{
  "formatoRelatorios": "foo",
  "tipoGraficos": "bar"
}
```

Porém, ao realizar uma alteração via `PUT` em `/relatorios` com os seguintes dados: `hello` e `world` para `formatoRelatorios` e `tipoGraficos` apenas a
consulta do endpoint `/relatorios` via `GET` retornou os dados relatados, 
continuando o endpoint `/config` a retornar:

```json
{
  "formatoRelatorios": "foo",
  "tipoGraficos": "bar"
}
```
