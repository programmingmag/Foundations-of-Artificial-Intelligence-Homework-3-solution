# Foundations-of-Artificial-Intelligence-Homework-3-solution

Download Here: [Foundations of Artificial Intelligence Homework 3 solution](https://jarviscodinghub.com/assignment/foundations-of-artificial-intelligence-homework-3-solution/)

For Custom/Original Work email jarviscodinghub@gmail.com/whatsapp +1(541)423-7793

Project description
Dr. Ernest Beakerman has been experimenting with gene knockout mice for the last 10 years. Recently he has
had a major breakthrough with his KM-52a strain. It turns out that the mice are hyper intelligent and possess a
keen grasp of logic far superior to any human. Since mice by their nature are quite friendly the KM-52a mice
have employed themselves to bettering humanity. For instance, Algernon II is now advising the president on
foreign matters and has brought the ISIS crisis to a graceful ending and stopped the spread of AIDS in Africa.
The problem with KM-52a is that, like all other mice, they live at most 4 years. As a result, new generations
must be constantly trained to replace the current mice, which die off very quickly. Additionally, they must be
trained with great speed so that they can spend as much time as possible aiding humanity into a new era of
prosperity.
Dr. Beakerman has employed you in his lab to facilitate the training of KM-52a mice. Each mouse will sit in
front of a computer practicing logic exercises. It will be presented with several first-order logic statements. It
will read them and then type in a logical query, which the statements should be able to prove. Your job is to
write a program that will check each conclusion a mouse makes and give it immediate feedback as to whether
the query can be proven. Thus, the mice will learn very quickly via feedback a strong understanding of logic.
To help you develop your system, Dr Beakerman has provided you with several sample knowledge bases the
mice have produced. The knowledge bases contain sentences with the following defined operators:
NOT X ~X
X OR Y X | Y
X AND Y X & Y
X IMPLIES Y X => Y
Your assignment is:
You will use the resolution inference algorithm, full first-order version (see slide 76 of Monday-Wednesday
slides for session14-15) to solve this problem.
Once you have completed this project Dr. Beakerman will use it to expedite the training of KM-52a mice and
thus usher in a new era of peace and prosperity. After that he will collect his Nobel prize and from then on
forget to ever mention your name when talking about how to train KM-52a mice.
Format for input.txt:


…



…

where
• Each query will be a single literal of the form Predicate(Constant) or ~Predicate(Constant).
• Variables are all single lowercase letters.
• All predicates (such as Sibling) and constants (such as John) are case-sensitive alphabetical strings that
begin with an uppercase letter.
• Each predicate takes at least one argument. Predicates will take at most 100 arguments. A given
predicate name will not appear with different number of arguments.
• There will be at most 100 queries and 1000 sentences in the knowledge base.
• See the sample input below for spacing patterns.
• You can assume that the input format is exactly as it is described. There will be no syntax errors in the
given input.
Format for output.txt:
For each query, determine if that query can be inferred from the knowledge base or not, one query per line:

…

where
each answer should be either TRUE if you can prove that the corresponding query sentence is true given the
knowledge base, or FALSE if you cannot.
Notes and hints:
– Please name your program “homework.xxx” where ‘xxx’ is the extension for the programming
language you choose. (“py” for python, “cpp” for C++, and “java” for Java). If you are using C++11, then
the name of your file should be “homework11.cpp” and if you are using python3.4 then the name of
your file should be “homework3.py”.
– If you decide that the given statement can be inferred from the knowledge base, every variable in each
sentence used in the proving process should be unified with a Constant. So, if you have something like
A(x) => B(John), and you cannot find any x to fulfill the A(x) premise, you cannot say that B(John) is
true.
– All variables are assumed to be universally quantified. There is no existential quantifier in this
homework. There is no need for Skolem functions or Skolem constants.
– Operator priorities apply. Parentheses may be used in the sentences given to you for the KB, to group
terms, e.g., (A(x) | B(x)) => C(x). There will not be any empty parentheses: ().
– It is recommended that you convert the KB to CNF as a pre-processing step. This means using the
definition of implication to eliminate it, working negations into parentheses, possibly using
distributivity rules to simplify some parentheses, and possibly splitting sentences that contain AND
operators into several sentences.
– The knowledge base that you will be given is consistent. So there are no contracting rules or facts in
the knowledge base.
– If you run into a loop and there is no alternative path you can try, report FALSE. An example for this
would be having two rules 1) A(x) => B(x) 2) B(x) => A(x) and wanting to prove A(John). In this case
your program should report FALSE.
– Considering that the size of knowledge base is not small, we recommend using an indexing method for
storing your knowledge base. Such as table-based indexing or tree-based index that you have learned
in class.
– You are free to use any parsing tool such as LEX and YACC if you want (As long as it runs on Vocareum).
Example 1:
For this input.txt:
6
F(Bob)
H(John)
~H(Alice)
~H(John)
G(Bob)
G(Alice)
14
A(x) => H(x)
D(x,y) => ~H(y)
B(x,y) & C(x,y) => A(x) [beware of operator priority]
B(John,Alice)
B(John,Bob)
(D(x,y) & F(y)) => C(x,y) [note parentheses on premises: not
D(John,Alice) strictly required but legal]
F(Bob)
D(John,Bob)
F(x) => G(x)
G(x) => H(x)
H(x) => F(x)
R(x) => H(x)
R(Alice)
your output.txt should be:
TRUE
TRUE
TRUE
FALSE
FALSE
TRUE
Example 2:
For this input.txt:
2
Ancestor(Liz,Billy)
Ancestor(Liz,Bob)
6
Mother(Liz,Charley)
Father(Charley,Billy)
~Mother(x,y) | Parent(x,y)
~Father(x,y) | Parent(x,y)
~Parent(x,y) | Ancestor(x,y)
~(Parent(x,y) & Ancestor(y,z)) | Ancestor(x,z)
your output.txt should be:
TRUE
FALSE
Example 3:
Try for yourself the example from slide 92 of session14-15 of Monday-Wednesday lectures.

