<div align="center">

## ^ A time Saver Script


</div>

### Description

In the latest version of PHP, you must use GET and POST arrays to pass variables--That's not bad--you just write $foo=$_GET["foo']; and you use $foo--But say you have 80 variable to declare--then it gets time consuming. This will cut the time to nothing.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Darryl Porter](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/darryl-porter.md)
**Level**          |Beginner
**User Rating**    |3.4 (82 globes from 24 users)
**Compatibility**  |PHP 4\.0
**Category**       |[Controls/ Forms/ Dialogs/ Menus](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/controls-forms-dialogs-menus__8-3.md)
**World**          |[PHP](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/php.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/darryl-porter-a-time-saver-script__8-770/archive/master.zip)





### Source Code

<div align="center">
<table border="2" cellpadding="5" cellspacing="0" width="60%" >
  <tr>
    <td width="100%">With the advent of newer version of PHP you can't do
    some
    of the convenient stuff that you used to be able to do. One of
    which is, you can no longer
    pass variable from one page to the other with a form without using the
    super-global variables $_POST
    or $_GET. These were introduced for
    security reasons, but it
    make
    coding that much longer because before you can use a variable you
    must
    declare it using the super-global so your code end up looking like this:<br>
    <br>
    <pre>&lt;form method=POST&gt;<br>
    &lt;input=&quot;text&quot; name=&quot;foo&quot; value=&quot;&quot;&gt; <br>
    &lt;input=&quot;submit&quot;&gt;<br>
 &lt;/form&gt;<br>
    <br></pre>
    You pass this form to the next page and your code looks like this:<br>
    $foo = $_POST[&quot;foo&quot;];<br>
    <br>
    Now you can use $foo like in older version of PHP. You might say, <br>
    what's
    wrong with that. I say nothing--unless you have <br>
    over 80 variable to
    declare, then it becomes tedious.
    <br>
    However, with this little script, it does the work for you.<br>
    <br>
    ------------------------------------------------------------------<br>
    <font color="#008000">/*I use a WHILE LOOP to run throught the GET or POST array.
    <br>
    You could also use a FOREACH LOOP.
    If you are using $_GET, just replace $_POST with $_GET */</font><br>
   <pre> while(list($key,$value)= each($_POST)) <br>
    {</pre>
<br>
    <font color="#008000">/* Creates a file called variable */</font><br>
    <pre>$file = &quot;variables.php&quot;; <br>
$handle = fopen ($file, &quot;a+&quot;);
<br></pre>
    <font color="#008000">/*Replace $_POST with $_GET here as well if you need to.*/</font><br>
    <pre>fwrite ($handle, &quot;&lt;?php $$key = \$_POST[\&quot;$key\&quot;]; ?&gt;&quot;); <br>
    fclose ($handle);<br>
    }<br></pre>
    <font color="#008000">/* Includes the file filled with
    your varaibles. You can now use the variable
    like you used to under the previous versions of PHP. */</font><br>
    <pre>include (&quot;variables.php&quot;);<br><br>
    <font color="#008000"> </pre>
    /* Put this at the bottom of your page. It destroys
the file &quot;variables.php&quot;
    */</font>    <pre>if (file_exists($file)) { <br>
    unlink(&quot;$file&quot;);<br>
    }</pre>And that is that. If you like it, please vote for it, or else
    just leave a comment.<br>
    -----------------------------------</pre></td>
  </tr>
</table>
</div>

