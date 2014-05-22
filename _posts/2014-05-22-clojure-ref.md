---
layout: seminar
title: An abridged Python-to-Clojure reference
---

||Python|Clojure
||------|-------|
|Booleans|True, False|true, false|
|Arithmetic|+ - * /|+ - * /|
||/ % |quot mod rem|
||+1 -1 max() min()|inc dec max min|
|Java String methods|upper()|.toUpperCase|
||lower()|.toLowerCase|
||capitalize()|.capitalize|
|Lists|[1,2,3]|\'(1 2 3)|
|||(list 1 2 3)|
|Add items to the front of a list|[\'b\', \'c\'].insert(0,\'a\')|(conj \'(\'b\' \'c\') \'a\')|
|Vectors|[1, 2, 3]|[1 2 3]|
|||(vector 1 2 3)|
|Add items to the end of a vector|[\'x\', \'y\'].append(\'z\')|(conj [\'x\' \'y\'] \'z\')|
|Sets||#(1 1 2)|
|||(set \'(1 1 2))|
|Maps|{\'a\': 1, \'b\': 2, \'c\': 3}|{:a 1, :b 2, :c 3}|
|||{:a 1 :b 2 :c 3}|
|||(hash-map :a 1, :b 2, :c 3)|
|Adding items to a map||(conj {:a 1, :b 2} [:c 3])|
|Sequences|[1, 2, 3]|(list 1 2 3)|
|||\'(1 2 3)|
|||[1 2 3]|
|The first element of a list|xs[0]|(first xs)|
|The second element of a list|xs[1]|(second xs)|
|The last element of a list|xs[-1]|(last xs)|
|Everything but the first element of a list|xs[1:]|(rest xs)|
|Functions|def plus2(i): return i + 2|(defn plus2 [i] (+ i 2))|
|(inline)||(fn [x] (+ x 2))|
|||#(+ % 2)|
|Strings|\'Hello world\'|"Hello world"|
||\'Hello\' + \' \' + \"world\"|(str \"Hello\" \" \" \"world\")|
|Map|map( lambda x: x*x, [1,2,3])|(map #(* % %) [1 2 3])|
||[ x*x for x in [1, 2, 3]]||
|Reduce|reduce(lambda x,y: x+y, [1,2,3]|(reduce + [1 2 3])|
||||
|Filter|lambda x: x % 2 != 0, [1,2,3]|(filter even? [1 2 3])|
||||





