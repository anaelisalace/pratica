# JavaScript

1. Aula sobre formulários

```html
<!DOCTYPE html>
<html lang="pt-br">

<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>

  <style>
    form {
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    form input,
    form select {
      background-color: papayawhip;
      width: 160px;
      display: flex;
    }

    button {

      font-size: 14px;
      color: rebeccapurple;
      background-color: dimgray;
      border-radius: 5px;

    }
  </style>
</head>

<body>
  <form>
    <label>
      Nome
      <input type="text" name="nome">
    </label>
    <label>
      Último Nome
      <input type="text" name="sobrenome">
    </label>
    <label>
      Gênero
      <select name="genero">
        <option value="m">Masculino</option>
        <option value="f">Feminino</option>
        <option value="nb">Não Binário</option>
        <option value="o">Outros</option>
      </select>

      <fieldset>
        <legend>Pedido</legend>

        <section>
          Tamanho da Pizza

          <label>
            <input type="radio" name="tamanho" id="p">Pequena
          </label>

          <label>
            <input type="radio" name="tamanho" id="M"> Média
          </label>

          <label>
            <input type="radio" name="tamanho" id="G">Grande
          </label>

          <label>
            <input type="radio" name="tamanho" id="gg">Gigante
          </label>
        </section>

      </fieldset>

    </label>
    <footer>
      <button type="reset">Limpar</button>
      <button type="submit">Enviar</button>
    </footer>
  </form>

  <script>
    const form = document.querySelector('form');
    console.log(form);

    form.onsubmit = (event) => {
      event.preventDefault();

      const data = new FormData(event.target);
      console.log(data);

      data.forEach((value, key) => {
        console.log(`${key}, ${value}`);
      })

      const entries = data.entries();
      const pedido = Object.fromEntries(entries);
      console.log(pedido);
    }



  </script>
</body>

</html>
```


## Anotações HTMl

### `<form>`

>`<label>`: representa uma legenda. Pode aninhar o `<input>` dentro do `<label>`

>`<input>`: É usado para acriar controles interativos para formulários. Ele depende do seu atributo `type` para indicar o tipo de dado. Caso o atributo não seja especificado, o padrão adotado é o `text`. 
>
>ATRIBUTOS: 
>
>`type`: É o tipo de controle do formulário. >Exemplos: `buton`, `checkbox`, `date`, `hidden` (escondido), `radio`, `reset`, `submit`.
> 
>`name`: É o nome enviado no controle do formulário. (Usado para identificar o valor)
>
>`value`: É o valor do controle. 
>
>`id`: É o identificador único que deve ser único em todo o documento. 


>`<fieldset>`: É usado para agrupar vários controles em um formulário da web.  `<legend>` fornece uma legenda para o `<fieldset>`.

>`<select>`: Menu de opções. Cada opção de menu é definida por um `<option>` elemento aninhado dentro de `<select>`.


## Anotações CSS


## Anotações Javascript

> VARIÁVEIS
>
> `let`: permite sobrescrever
>
> `const`: NÃO permite sobrescrever
>
> `var`: nunca utilizar
>         
> *Exemplo* 
>
>`const ana = 5;`
>
>*=*  atribuição do valor da variável

 `const form = document.querySelector('form');`
 retorna o primeiro elemento dentro do form. Se nenhuma correspondência for encontrara, retorna `null`.

 `event`: Qualquer ação da tela é um evento.

 `form.onsubmit = (event)`: manipulador do evento (quando o form for enviado)

 `target`: É o alvo. O botão submete o formulário e o target recebe. 

 `preventDefault`: Impede que o evento padrão ocorra.  

 `new FormData(form)`: cria um novo conjunto de dados.

`Object.fromEntries(entries)`: obtém uma lista de valores de um objeto.  