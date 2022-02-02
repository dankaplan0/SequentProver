# Sequent Parser Plans and Information

## Current State of the App:
As things stand, the parser is ready for exploration. The app allows users to choose between 
invertible and non-invertible rules (on a rule-by-rule basis) and explore proof trees created from
sequents by application of those rules. We don't currently allow users to select exactly how a tree
is decomposed, but that may come in the future. 

**To start using the program, run \_\_main\_\_.py.** 

To use your own sequents, create a .txt file where each line has a semicolon separated list of 
antecedents (no quotation marks) and a comma separated list of consequents with a snake turnstile 
(|~) between them (vertical line, tilde). To include first-order propositions, the correct 
syntax is "predicate(name1, name2, ...)".  

For example: 

Antecedent1; Antecedent2 |~ Consequent1; Consequent2

or

Antecedent1(name1, name2); Antecedent2(name2, name1) |~ Consequent1(name3); Consequent2(name1, name3) 


Note the space between last antecedent and the turnstile (same for first consequent), as well as 
the spaces between propositions. 

The accepted connectives are "and" (conjunction), "or" (disjunction), "implies" (conditional), and
"not" (negation). All connectives are lowercase and we currently do not support using symbols. 
Binary connectives occur between two propositions (separated by a space on either side) and unary 
connectives appear in front of their proposition. All non atomic propositions (i.e. ones with 
connectives) must be surrounded by parentheses ("()"), e.g. "(A and B)" or "(not C)". Atomic 
propositions should not be surrounded by parentheses. 

Feel free to peruse the source code, if you so desire. I make no guarantees about its quality since
I am an amateur and if you spot things I can do to make the code better or more readable (or both),
you can contact me at adriananhaltg at gmail dot com. You can also get regular updates (almost 
whenever I add/fix something) from github at https://github.com/LogicalExpressivism/SequentProver

## Troubleshooting
If you're having issues, try the following steps. If it still doesn't work, then you might be 
trying to do something I haven't thought of (not unlikely) or you've found a bug (congratulations).
In that case, if you send me the error it's giving you along with the stack trace, your sequents 
file (if you're not using the default one), and a description of what you're seeing versus what you
expect to see, I might be able to help you out when I get time, or at least give you an 
explanation.

- Ensure your Python installation is the most recent one. You can check this by opening the command
  line (terminal on Mac or powershell on windows and typing "python --version"). There are plenty 
  of tutorials online of how to update Python if you need to.
- Ensure all sequents are formatted properly:
    - propositions are separated from each other by commas
    - Turnstile is made of the vertical line ("|") and tilde ("~")
    - connectives are placed properly in the strings (between or in front of propositions)
    - connectives are all lowercase letters
    - nonbasic propositions (and subpropositions) are surrounded by a set of parentheses
    - propositions do not contain commas or turnstiles
- Ensure you are running the right file
- Ensure you have correctly set the input file 

## Plans for development:
- [x] Recover all functionality from the previous parser.
- [x] Start work on branching rules (complete).
- [ ] Collect individual names and objects.
- [ ] Be able to sort sequents into desirables and undesirables (good and bad).
- [ ] Add quantifiers.
- [ ] Add monotonicity box.
- [ ] Get hooks the natural language parser. 


## Current progress on recovering functionality: COMPLETE
- [x] decompose sequents
- [x] import sequents to decompose
- [x] save decomposed sequents
- [x] display decomposed sequents on command
- [x] change whether we accept reflexivity
- [x] change whether we accept contraction 
- [x] add all rules for decomposition (branching rules)
- [x] allow changing import file

## Possible List of Further Projects (added by Dan 2022/02/01)
- [ ] improve sequent output formatting (it should be possible to draw sequent trees in python)
- [ ] fix quantifiers (maybe?)
- [ ] allow for multiple choices (when decomposing non-invertible rules); alternatively,
     limit amount of choices if combinatorial explosion is feared (perhaps as a variable?)

## Natural Language Processing Arm of Project (added by Dan 2022/02/01)

- [ ] Output sequents from natural language input
- [ ] Feed sequents into sequent prover program

## List of future projects (added by Dan 2022/02/01)

- [ ] check NL arguments against database of good sequents?
- [ ] machine learning for checking new sequents? (i.e. extrapolating database of atomic sequents)