# Pytest Quest

<details>
<summary><strong>🧑‍💻 O que deverá ser desenvolvido</strong></summary>

Vamos fazer alguns exercícios para consolidar o uso do Pytest e suas funcionalidades.
Aqui, você vai praticar a criação de fixtures, o uso de marcadores, a criação de testes parametrizados e o uso de fixtures builtin, do Pytest.
Para isso, você vai trabalhar com um conversor de números hexadecimais para decimais cujo código já está implementado, servindo apenas como base para a prática do Pytest.

</details>
  
<details>
  <summary><strong>📝 Habilidades a serem trabalhadas</strong></summary>

  Neste exercício, verificamos se você é capaz de:

- Criar seus próprios testes automatizados por meio do módulo `pytest`.
- Executar conjuntos de testes de forma automática.
- Criar suas próprias _fixtures_ de teste.
- Utilizar _fixtures_ de testes do `pytest`.
- Criar testes parametrizados.

</details>

## Orientações
  
<details>
  <summary><strong>🏕️ Ambiente Virtual</strong></summary>
  O Python oferece um recurso chamado de ambiente virtual, que permite sua máquina rodar sem conflitos diferentes tipos de projetos com diferentes versões de bibliotecas.

  1. **Criar o ambiente virtual**

  ```bash
  python3 -m venv .venv
  ```

  2. **Ativar o ambiente virtual**

  ```bash
  source .venv/bin/activate
  ```

  3. **Instalar as dependências no ambiente virtual**

  ```bash
  python3 -m pip install -r dev-requirements.txt
  ```

  Com o seu ambiente virtual ativo, as dependências serão instaladas neste ambiente.
  
  Quando precisar desativar o ambiente virtual, execute o comando `deactivate`. Lembre-se de ativar novamente quando voltar a trabalhar no exercício.

  O arquivo `dev-requirements.txt` contém todas as dependências que serão utilizadas no exercício, ele está agindo como se fosse um `package.json` de um projeto `Node.js`.

  Se o VS Code não reconhecer as dependências instaladas no ambiente virtual criado, será necessário informar o caminho do interpretador Python. Para isso, abra o VS Code e pressione `Ctrl + Shift + P` (no Mac, `Cmd + Shift + P`) e digite `Python: Select Interpreter`. Selecione o interpretador que possui o caminho `./.venv/bin/python` no nome.
</details>

## Exercícios

### 1. Crie uma fixture

Neste primeiro exercício, você vai praticar a criação de uma fixture simples.

<details>

<summary> O que você deve fazer </summary>

Crie o arquivo `tests/conftest.py`.
Em seguida, crie neste arquivo a fixture `custom_fixture`, com o escopo de módulo (ou mais abrangente, como sessão) e que retorna uma lista Python com os números de 1 a 10, incluindo o 1 e o 10.

</details>

### 2. Use um marcador

Neste segundo exercício, você vai praticar o uso de marcadores do Pytest.

<details>

<summary> O que você deverá fazer </summary>

Crie um arquivo `tests/marker_test.py`. Em seguida crie neste arquivo a função de teste `test_dependency_mark`, cujo resultado do teste deve sempre passar. Marque o teste com o marcador `dependency`.

</details>

### 3. Crie testes parametrizados

Agora chegou a hora de praticar a criação de testes parametrizados, evitando a repetição de código.

<details>

<summary> O que você deverá fazer </summary>

No arquivo previamente criado `tests/parametrized_test.py`, crie uma função de teste parametrizada chamada `test_converter` para testar a função `src.hex_converter.hexadecimal_to_decimal`.

A função de teste deve receber dois parâmetros, sendo o primeiro o número hexadecimal na forma de uma string e o segundo o número decimal inteiro equivalente.

O conjunto de valores passados para o marcador de parametrização deve ser o seguinte:

- Hexadecimal `"8"`, inteiro na saída `8`.
- Hexadecimal `"9"`, inteiro na saída `9`.
- Hexadecimal `"a"`, inteiro na saída `10`.
- Hexadecimal `"b"`, inteiro na saída `11`.
- Hexadecimal `"c"`, inteiro na saída `12`.
- Hexadecimal `"e"`, inteiro na saída `14`.
- Hexadecimal `"f"`, inteiro na saída `15`.

Importante ressaltar que o valor hexadecimal `"d"` e seu correspondente inteiro `13` foram deliberadamente omitidos da lista de parâmetros.

O corpo do teste deve verificar se passar o número hexadecimal como parâmetro para a função `hexadecimal_to_decimal` retorna o número decimal esperado.

</details>

### 4. Use fixtures builtin - `monkeypatch`

Neste exercício, você vai praticar o uso de fixtures builtin, do Pytest, mais especificamente a `monkeypatch`.

<details>

<summary> O que você deverá fazer </summary>

No arquivo previamente criado `tests/built_in_fixtures_test.py`, crie uma função de teste chamada `test_monkeypatch`.
Esta função deve utilizar a fixture `monkeypatch` para validar se a chamada a `src.hex_converter.main` retorna `10` quando a pessoa que usa a aplicação digitar a string `"a"`.

</details>

### 5. Use fixtures builtin - `capsys`

Neste exercício, você vai praticar o uso de fixtures builtin, do Pytest, mais especificamente a `capsys`.

<details>

<summary> O que você deverá fazer </summary>

No arquivo previamente criado `tests/built_in_fixtures_test.py`, crie uma função de teste chamada `test_capsys`.
Esta função deve utilizar a fixture `capsys` para validar se a função `src.hex_converter.print_hexadecimal_to_decimal` imprime `10\n` na saída padrão e uma string vazia na saída de erro padrão quando chamada com a string `"a"`.

</details>

### 6. Use fixtures builtin - `tmp_path`

Neste exercício, você vai praticar o uso de fixtures builtin, do Pytest, mais especificamente a `tmp_path`.

<details>

<summary> O que você deverá fazer </summary>

No arquivo previamente criado `tests/built_in_fixtures_test.py`, crie uma função de teste chamada `test_tmp_path`. Esta função deve utilizar a fixture `tmp_path` para criar um arquivo temporário chamado "output.txt" dentro de um diretório temporário.

Em seguida, este diretório deve ser passado como segundo parâmetro da função `write_hexadecimal_to_decimal`, sendo o primeiro parâmetro a string `"a"`.

Por fim, o teste deve verificar se o conteúdo do arquivo "output.txt" é igual a string `"10"`.

Dica: utilize o método `pathlib.Path().read_text()`.

Dica: o teste não traz um retorno devidamente descritivo quando falha. Ative o debugger e ative o breakpoint `User Uncaught Exceptions` na aba `Breakpoints` no menu do debugger.

</details>

---

<!-- mdi versão 1.0 exercício como projeto python ⚠️ não exclua esse comentário -->
