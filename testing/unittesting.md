# Unit testing

## Coverage

### MC/DC coverage

Requires at least *(n + 1)* test cases, where n is the number of conditions in the decision.

MC/DC requires that,

* Each condition in a decision has been shown to independently affect that decision's outcome.
* A condition is shown to independently affect a decision's outcome by varying just that condition while holding fixed all other possible conditions.
* Every point of entry and exit in the program has been invoked at least once.
* Every control statement (i.e., branchpoint) in the program has taken all possible outcomes (i.e., branches) at least once.
* Every non-constant Boolean expression in the program has evaluated to both a True and False result.
* Every non-constant condition in a Boolean expression in the program has evaluated to both a True and False result.
* Every non-constant condition in a Boolean expression in the program has been shown to independently affect that expression's outcome.
