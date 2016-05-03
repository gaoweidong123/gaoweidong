<?php
	header('Content-Type:text/html;charset=utf-8');
	$a = new mysqli('localhost','root','','project');
	$a->query('set names utf8');

	$name = $_POST['name'];
	$password = $_POST['password'];
	$sex = $_POST['sex'];
	$idcard = $_POST['idcard'];

	$sql = "select * from model where name = '{$name}'";
	$b = $a->query($sql)
	if ($b->num_rows > 0){
		header('location:message.php?status=error');
	}else{

		$sql = "insert into model(name,password,sex,idcard) value('{$name}','{$password}','{$sex}','{$idcard}')";
		$a->query($sql);
		header('location:message.php?status=ok');
	}








?>