# Debugging
<!-- position: 4 -->

The debug mode of Bludit can be activated in the file `init.php` in the directory `/bl-kernel/boot`. Please change the following (line 11):

`define('DEBUG_MODE', FALSE);`

to

`define('DEBUG_MODE', TRUE);`

The error log `debug.txt` can be found in the directory `/bl-content`.
