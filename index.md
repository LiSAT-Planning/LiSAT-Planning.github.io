## LiSAT
LiSAT (LiftedSAT) is a SAT-based planner build on top of the lifted planner [`powerlifted`](https://github.com/abcorrea/powerlifted) by A. Corrêa et al.
In contrast to classical SAT-based planners, LiSAT directly translates the lifted planning problem into a SAT formula.
This may yield to lower performance on some small benchmark instances, but allows LiSAT to solve huge planning problems that prior SAT-based planners could not even start to tackle.

### Obtaining and Building LiSAT
LiSAT is available on [github](https://github.com/LiSAT-Planning/LiSAT).
Its README.md contains instructions on how to build LiSAT.

### Running LiSAT
LiSAT has two operational modes: optimal and satisficing, with satisficing being the default mode.

#### Satisficing Mode
In satisficing mode, LiSAT will attempt to solve the given planning problem for **exactly one bound on the plan length**, which is provided via `-l PLANLENGTH` and defaults to `100`.
As such, it may be very slow if there is a significantly shorter plan and may not return any plan if the only plan is longer than `PLANLENGTH`.

We recommend to use the satisficing mode **only** as part of a portfolio containing multiple possible plan lengths. We recommend to use five planners in the portfolio with bounds 10, 25, 50, 100, and 200.

#### Optimal Mode
In optimal mode, LiSAT will iterate over the plan length and will return the shortest plan for the problem.
Note that this mode does not take action costs into account!


### Citing LiSAT

If you are using LiSAT, please cite the following paper which describes how it operates:

```
@inproceedings{Hoeller2022LiftedSAT,
		Author    = {Daniel Höller and Gregor Behnke},
		Title     = {Encoding Lifted Classical Planning in Propositional Logic},
		Booktitle = {Proceedings of the 32nd International Conference on Automated Planning and Scheduling ({ICAPS} 2022)},
		Year      = {2022},
		Publisher = {AAAI Press},
		Pages = {134--144},
}
```
