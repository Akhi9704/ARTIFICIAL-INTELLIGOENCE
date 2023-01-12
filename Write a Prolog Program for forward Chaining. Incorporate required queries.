% Define the knowledge base
:- dynamic fact/1.
fact(a).
fact(b).

rule(r1, [a], c).
rule(r2, [b], d).
rule(r3, [c,d], e).

% Define the forward chaining predicate
forward_chain(X) :-
    fact(X).

forward_chain(X) :-
    (rule(Rule, Premises, X),
    check_premises(Premises)),
    asserta(fact(X)).

% Define the check_premises predicate
check_premises([]).

check_premises([Premise|Rest]) :-
    fact(Premise),
    check_premises(Rest).

% Queries
ask(X):- forward_chain(X),write(X), nl.
ask_not(X):- \+forward_chain(X), write(X), nl.
