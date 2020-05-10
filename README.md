# AgendaWeb
## Links
Crie uma Agenda Web utilizando PHP e MySQL: <br>
https://www.youtube.com/watch?v=P1mqyAShMfo <br>
Formulário: <br>
https://www.youtube.com/watch?v=_TjHKWdOF94
Gravando dados no banco (esse é quando o site já ta funcionando)
https://www.youtube.com/watch?v=yH8R1khGTZs

## Recursos
* Formulario (html);
* Banco de dados (php e mysql);
* Quando passa o mouse em cima uma janela aparece (java escript).

## Banco de dados
## Entidades
* Aluno
* Professor
* Aula
* Livro
* Filial
* Prova

## Consultas
* Consultar dados do aluno;
  * por nível;
  * por aula;
  * por aula refeita;
  * por nota;
  * por status de aprovação;
  * por matrícula.
* Consultar aulas disponiveis;
  * por data;
  * por hora;
  * por nível;
  * por livro;
  * por unidade;
  * por filial;
  * por professor;
  * por quantidade de alunos.
* Número de desistências por aula;
* Número de alunos por aula;
* Consulltar provas de unidade;
  * por data;
  * por hora;
  * por nível;
  * por filial;
  * por professor;
  * por aprovados;
  * por reprovados;
  * por nota;
  * por quantidade de alunos.
* Consultar dados prova final.
  * por data;
  * por hora;
  * por nível;
  * por filial;
  * por professor;
  * por aprovados;
  * por reprovados;
  * por nota;
  * por quantidade de alunos.

## Operações
* Cadastro de uma nova aula;
* Cadastro de prova de unidade;
* Cadastro de prova final;
* Alterações dos dads da prova de unidade;
* Alterações dos dads da prova final;
* Remarcar prova de unidade;
* Remarcar prova final;
* Remover uma aula;
* Alteração dos dados da aula;
* Cadastro de um novo aluno;
* Remover aluno;
* Alteração dos dados de um aluno;
* Cadastro de um novo professor;
* Remover professor;
* Alteração dos dados de um professor;
* Desistencia de uma aula agendada.

## A notações atributos
Criar um uid artificial para aula?

---

## Lembretes
Eu esqueci de colocar sobre a unidade minds no trabalho inicial.
  * Colocar uma caixinha "Qual sua unidade Mentes?" que ao clicar mostra as filiais;
  * Depois disso que a agenda é disponibilizada;
  * Ou eu só ignoro que há filiais e faço só sobre uma unidade.
  
---

## Códigos

### Cadastro

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport"content="width=device-width, initial-scale="1.0">
<title>Mentes</title>
</head>
<body>
    <?php
        //Conxão com o banco
        $db = new PDO("mysql:host=localhost;dbname=mentes;charset=utf8","root","");
 
    ?>
</body>
<body>

    <h1 class="titulo">Formulário de cadastro - PHP</h1>
    <form method="get" action="grava.php" class="formulario">
        <input type="text" name="fnome" placeholder="NOME" required class="input"><br>
        <input type="email" name="femail" placeholder="EMAIL" required class="input"><br>
        <textarea name="fmsg" rows="5" cols="48" required class="input" placeholder="MENSAGEM"></textarea><br>
        <input type="submit" value="GRAVAR" class="botform"><br>

</body>        
</html>
### Conexão

<?php
    $conexao=myslqi_connect("localhost", "root", "", "mentes");
?>

