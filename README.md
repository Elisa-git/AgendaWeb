# AgendaWeb
## Links
Crie uma Agenda Web utilizando PHP e MySQL: <br>
https://www.youtube.com/watch?v=P1mqyAShMfo <br>
* Segunda opção: https://social.msdn.microsoft.com/Forums/pt-BR/5212f140-f795-4f33-b4e5-b974f0690de6/como-criar-agenda-usando-php-e-mysql?forum=webgeralpt <br>

Formulário: <br>
https://www.youtube.com/watch?v=_TjHKWdOF94 <br>
Gravando dados no banco (esse é quando o site já ta funcionando) <br>
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

### Grava

<?php
    include("conexao.php");

    $recnome=$_GET["fnome"];
    $recemail=$_GET["femail"];
    $recmsg=$_GET["fmsg"];

    mysqli_query($conexao, "insert into dados (nome, email, msg) values ("recnome", "recemail", "recmsg")");

    header("location:lista.php");
?>

### Lista

<!DOCTYPE html>
<html lang="en">
<head>

    <meta charset="UTF-8">
    <meta name="viewport"content="width=device-width, initial-scale=1.0">

    <title>Listagem de dados PHP</title>
    <link type="text/css" href="css/estilo.css" rel="stylesheet">
    <link type="text/css" href="front-awesome-4.6.0/css/font-awesome.min.css" rel="stylesheet">
    <script type="text/jscript" src="script.js"></script>

</head>
<body>
    <h1 class="titulo">Listagem de Dados PHP</h1>
    <table width="100%" border="1" bordercolor="#EEE" cellspacing="0" cellpadding="10">
        <tr>
            <td><strong>NOME</strong></td>
            <td><strong>EMAIL</strong></td>
            <td><strong>MENSAGEM</strong></td>
            <td width="10"><strong>ALTERAR</strong></td>
            <td width="10"><strong>EXCLUIR</strong></td>
        </tr>
        <?php
            include("conecta.php");
        $seleciona=mysqli_query($conexao, "select * from dados order by id desc");
            while ($campo=mysqli_fetch_array($seleciona)) {?>
                <tr>
                    <td><?$campo["nome"]?></td>
                    <td><?$campo["email"]?></td>
                    <td><?$campo["msg"]?></td>
                    <td align="center"><a href="editar.php?editaid=<?=$campo["id"]?>"><i class="fa fa-edit"></i></a><td>
                    <td align="center"><a href="#" onClick="verifica(<?$campo["id"]?>)"><i class="fa fa-trash"></i></a><td>
                </tr>
        <?php   }?>
    </table>
</body>


