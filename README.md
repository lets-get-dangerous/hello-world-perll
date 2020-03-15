# "Hello world!" in perl

    #!/usr/bin/perl
    $_=q$qsjou<vd<r<aia+<rr<bfmmp+<xpsme=\ob$;
    y?<-@*-.b-z? -$+-/a-y?;
    s=\D+=$&=ee

### Будьте [осторожны](http://lurkmore.to/%D0%9F%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%B0_%D0%B8%D0%B7_%D0%BE%D0%B4%D0%BD%D0%BE%D0%B9_%D1%81%D1%82%D1%80%D0%BE%D1%87%D0%BA%D0%B8_%D0%BD%D0%B0_Perl) с запуском [обфусцированного кода]: https://ru.wikipedia.org/wiki/%D0%9E%D0%B1%D1%84%D1%83%D1%81%D0%BA%D0%B0%D1%86%D0%B8%D1%8F_(%D0%BF%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%BD%D0%BE%D0%B5_%D0%BE%D0%B1%D0%B5%D1%81%D0%BF%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D0%B5 на своей машине!

На самом деле этот код является примером обфусцированного кода, но демонстрирует некоторые особенности Perl:

**Специальные переменные.**
**$_** по умолчанию переменная хранит ввод, присваивание, результаты поиска по заданному образцу.

**Кавычки.**
Двойные и одинарные кавычки различаются по поведению. Можно использовать
операторы q и qq, соответственно для одинарных или двойных кавычек.
Могут использоваться как со скобками, парными символами, так и с любыми одинаковыми символами:
q<>, q[], q//, q**, q@@, q44 и т.д.

**Точка с запятой.**
Каждая команда отделяется от других точкой с запятой.Команды могут быть записаны в одну строку.
Точка с запятой не обязательна, только если оператор является последним в блоке

**Регулярные выражения.**
Основной особенностью языка считаются его богатые возможности для работы с текстом, в том числе работа с регулярными выражениями (как гласит wikipedia)
В примере применяются два оператора: s и y.
y (синоним tr) - оператор замены множества символов или транслитерации.
Синтаксис: y/SEARCHLIST/REPLACEMENTLIST/flags
Символы из SEARCHLIST будут заменены на соответствующие символы из REPLACEMENTLIST.
Оператор s - поиск и замена подстроки.
В качестве разделителей вместо "/" могут использоваться любые символы, первый символ после y устанавливает разделитель.
Флаги не обязытельны.
SEARCHLIST/REPLACEMENTLIST в операторе "y" в примере заданы с помощью регулярных выражений диапазонами:

    "<-@*-.b-z" - диапазоны ["<" - "@"] ["*" - "."] ["b" - "z"]
    " -$+-/a-y" - диапазоны ["символ пробела" - "$"]["+" - "/"]["a" - "y"]
 

После применения оператора

    y?<-@*-.b-z? -$+-/a-y?;

переменная $_ примет вид:

    print uc q aha, qq aello, world!\na
    
что равнозначно

    print uc 'h', "ello, world!\n"

Флаг ee - двойной e - [Evaluate](https://perldoc.perl.org/perlop.html#s%2f_PATTERN_%2f_REPLACEMENT_%2fmsixpodualngcer),в операторе "s" приведет к вычислению выражения, т.е. его исполнению.

Функция print имеет синтаксис

    print ДЕСКРИПТОР СПИСОК;
    
    ДЕСКРИПТОР - файловый дескриптор, по умолчанию STDOUT
    СПИСОК - список строковых данных
    
Функция uc - "uppercase", если не указано выражение, преобразует переменную $_.

Статья на хабре о [перл](https://habr.com/ru/post/245659/)
