# JavaScript

1. Aula sobre formulários

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  meta
  <meta  content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>

</head>
<body>
  <form>
    <label>
      Nome
      <input class="form-control" type="text" name="nome">
    </label>
    
    <label>
      Último nome
      <input class="form-control" type="text" name="sobrenome">
    </label>
  </form>
  <script>
    const input = document.querySelector('input');
    const labels = input.labels;
    console.assert(labels.length === 1);
    console.log(labels.length);

    input.type = 'hidden';
    console.assert(labels.length === 0); // the input is no longer the label's labeled control
    console.assert(input.labels === null);

    input.type = 'checkbox';
    console.assert(labels.length === 1); // the input is once again the label's labeled control
    console.assert(input.labels === labels); // same value as returned originally
  </script>
</body>
</html>
```


## Anotações

Nesta aula aprendemos como conseguimos selecioniar elementos no documento HTML através das APIs JavaScript.

Também vimos que o JavaScript pode manipular os elementos que estão no documento HTML, alterando seus atritos e valores, mas não se limitando, também vimos que podemos criar novos elementos via JS e adicionar aos elementos pré existentes na tela.