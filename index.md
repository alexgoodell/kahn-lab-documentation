# Kahn Lab Documentation Protocol

## History of this document

This document began in Sept 2017 after continued challenges collaborating on projects that involved significant programming. In general, our projects are large and complicated, while our team has little formal training in software development. Although ad-hoc, piecemeal software development works for small projects, our projects often become larger than expected and are occasionally complicated by inadequate documentation and review methods. This document serves as a guide for all researchers working in the Kahn lab who will use any non-Excel programming language.

## Introduction

Documentation is vital -- it allows others to understand your code, and allows you to better understand your code when you come back to it months afterwards. There are two types of documentation: external and internal. External documentation is generally prose, perhaps mixed with some code snippets, contained in a separate document that explains the inner workings of a program. Internal documentation consists of embedded comments throughout a program. 


## External documentation 

The Kahn lab has no requirement for external documentation. It is suggested that the primary mechanics of your software are described within your scientific manuscript and/or technical appendix. An additional document that gives a more technical explanation can be helpful, but it not required. 

## Internal documentation

At some larger software companies, internal documentation can be kept to a minimum. Often, the tasks outside of academia are straight-forward: display the price, get user passwords, etc. In addition, at most companies, the entire team (including the supervisor) is proficient in the given language. _This is not the case in academic projects._ The Kahn lab has many complex projects in a variety of programming languages. Key team members with important insights are often not proficient in the chosen language. For this reason, internal documentation is vital. The following sections discuss the requirements of internal documentation in the Kahn lab.

### Guidelines

- Variable names should be in English. Avoid excess jargon and/or abbreviations in your variable names. Code does not run faster with shorter variable names! It should be instantly apparent what your variable is by reading its name. If all the variables are well-named, the need to comment can be reduced significantly. 
- Use consistent naming standards. You should use either underscored variables names, ie "user_password" or camel case, ie "userPassword." Remain consistent. 
- Each "action" should have a comment, one line above the beginning of the action. For example, if you have a set of lines that create three Markov states representing HIV infection, then move to another task, you need to comment this first task. Generally, adding a single line before each task is adequate. 
- Do not just state the mechanics of code, just as "create a new variable," but instead describe the overarching task, Tell the "why" not the "how."
- Break your code into sections using hierarchical displays. Use dashes or underscores to designate the beginning of new sections. 
- Use a mixture of block comments (larger comments explaining entire sections) and single-line comments that explain specific paragraphs of code.
- End-line comments (comments at the end of a line) should be avoided. Place comments as a single-line above the action.
- Use ellipses to denote a continuation of above comments.
- Comment the end of long indented blocks. For example, if using an if statement within a while statement, it is useful to mark the end of those blocks with an end-line comment. For example " } # end while"

### Examples

Here is an example of well-documented code.

```python
# ----------- Markov state creation for HIV and TB ----------
# Create three Markov states to represent potential HIV infection status as well as treatment status
hivPositiveOnTreatmentState = createNewState(hiv=True,treatment=False)
hivPositiveNoTreatmentState = createNewState(hiv=True,treatment=False)
hivNegativeNoTreatmentState = createNewState(hiv=False,treatment=False)
# ... repeat for tuberculosis (TB)
tbPositiveOnTreatmentState = createNewState(hiv=True,treatment=False)
tbPositiveNoTreatmentState = createNewState(hiv=True,treatment=False)
tbNegativeNoTreatmentState = createNewState(hiv=False,treatment=False)
```

Here is an example of poorly-documented code. The variable names and function names are cryptic and not consistent (underscores in a variable name, camel case in function name). The comment describes the mechanics of the action, instead of the overarching purpose. There are no sections, though clearly needed. Endline comments are used instead of a single line in front of the action the comment describes. The author repeats information instead of using ellipses. 

```python
hiv_P_O_T = createNewState(hiv=True,treatment=False) # Create variables from createNewState for HIV 
hiv_P_N_T = createNewState(hiv=True,treatment=False)
hiv_N_N_T = createNewState(hiv=False,treatment=False)
tb_P_O_T = createNewState(hiv=True,treatment=False) # Create variables from createNewState for TB
tb_P_N_T = createNewState(hiv=True,treatment=False)
tb_N_N_T = createNewState(hiv=False,treatment=False)
```


## Storing code

The preferred method for storing code in the Kahn lab is Github. Git is a free, version-control system. Github is a website which allows you to store Git repositories for free. Git is an essential tool. Used correctly, it allows programmers to save the state of their code at any time, and "roll-back" to previous versions of code if errors are introduced. It allows collaboration across teams, where individuals can work on seperate parts of code and merge their changes together, with a clear, transparent history. 

Currently, use of Git and Github are recommended, but not required. For projects with significant collaboration requirements, use of Git/Github or a similar version control system is required. 

## Code reviews 

One of the most important methods by which programmers check the reliability of their code is through having it reviewed by other members of the team. Ideally, this would occur on a regular basis, such as weekly. 

## References

McConnell, Steve. Code complete. Pearson Education, 2004.

