# HDDL 2.1 language proposal

## Introduction and purpose
This repository is aimed at defining collaboratively a dialect of PDDL, christened HDDL2.1, able to express numerical and temporal constraints over an Hierarchical Task Network (HTN) formalism. This repository wants to open discussions on the semantics and the syntax needed to extend HDDL. Some benchmarks are being proposed in order to illustrate these needs.

## Motivation
Real world applications of planning, like in industry and robotics, require modelling rich and diverse scenarios. Their resolution usually requires coordinated and concurrent action executions. In several cases, such planning problems are naturally decomposed in a hierarchical way and expressed by a HTN formalism.

The PDDL language used to specify planning domains has evolved to cover the different planning paradigms. However, formulating real and complex scenarios where numerical and temporal constraints concur in defining a solution is still a challenge.
This proposition aims at filling the gap between existing planning languages and operational needs. To do so, we propose to extend HDDL taking inspiration from PDDL 2.1 and ANML to express temporal and numerical expressions.

## The HDDL2.1 language
The main elements that have been proposed so far are:

* _Durative method_ - Like methods in HDDL 1.0, durative methods have parameters, the abstract task they decompose, and the resulting task network, and, like durative actions, they can have duration constraints and a condition that has to hold to apply the decomposition. Note that, unlike durative actions, duration constraints may be not mandatory.
* _Durative actions_ - Durative Actions with intermediate effects have received some criticisms in the past, in particular the fact that they fail in guaranteeing that preconditions/conditions hold over specified intervals, and that effects can take place at arbitrary time points within the action. Even if it is true that forcing all effects to take place at the start and end points of actions, as in PDDL2.1, imposes constraints on how activity can be modelled, it does not represent any constraint on expressiveness. While PDDL2.1 is not the most convenient language for durative actions with intermediate effects, HDDL supports them with ease as they can be naturally divided into sub-actions.
* _Method Duration Constraints_ - Optional constraints may be needed to restrict the allowed value for the duration of the method or the sub-tasks that compose it. Therefore, it could be necessary to be able to refer explicitly to the duration of a subtask and not only to the duration of the method with the variable `?duration`.
* _Method Ordering Constraints_ - To deal with time, it is necessary to generalise the ordering constraints defined in the task network of the method. Task network declaration stays unchanged from HDDL 1.0, but we just propose to declare the ordering constraints via the task ids decorated with time specifiers.
* _HTN Method Constraints and Semantics_ - HDDL 1.0 only accepts equality constraints or inequality on method parameters in the task network. We propose to add constraints, based on the syntax of the constraints used on state trajectory constraints defined in PDDL 3.0. These constraints allow to express logical constraints on the decomposition of the method, in addition to the ordering constraints.
* _Timed initial literals_ - Like in PDDL 2.2, timed initial literals can be needed to express timed events.

## Contributing
We use GitHub issues to track discussion subjects. Contributions are open to everyone who wants to suggest new features for HDDL2.1, propose improvements to existing language elements, or just raise some question. Discussion can happen informally through other media (chat, email, face-to-face...) but important talking points must must be posted in issues so everyone can keep track of the proposals.

If you have something to say, first [check out existing issues](https://github.com/pellierd/BNF-HDDL2.1/issues) or if you don't find a corresponding topic [open a new issue](https://github.com/pellierd/BNF-HDDL2.1/issues/new). 

You can send a [pull request](https://github.com/pellierd/BNF-HDDL2.1/pull/new/main) to submit changes to the language formulation once an issue discussion has been settled and the need for a change has been agreed upon. Pull requests must clearly list of what you've done and link to a related the issue or issues.

If you have a benchmark to propose, follow the same step: create a new issue and after discussion send a [pull request](https://github.com/pellierd/BNF-HDDL2.1/pull/new/main). The benchmarks proposed has to be set in the benchmarks directory of the projet.

Any contribution intentionally submitted for inclusion in the work by you is under the [Creative Commons Attribution 4.0 International (CC BY 4.0) licence](https://creativecommons.org/licenses/by/4.0/).

## How to cite this work
> D. Pellier, H. Fiorino, M. Grand, A. Albore, R. Bailon-Ruiz "HDDL 2.1: Towards Defining an HTN Formalism with Time" (Tech. Repport). [arXiv:2206.01822](https://arxiv.org/abs/2206.01822) [cs.AI]
