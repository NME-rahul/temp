1. Complement of Halting Problem is Unrecognizable but co-recognizable(meaning its complement is recognizable).
2. Complement of Membership problem is Unrecognizable but co-recognizable.

#### 2. Complement of Membership problem is Unrecognizable but co-recognizable.

The Basic Idea is

1. We have Machine $N$ with decider(always Halts like magic) in it simulating the input $<M>$
2. What $N$ does is first creates a copy of the input $< M > \rightarrow <M, M>$ then fed this to decider,
3. Decider will either Halt anf accept or Halt and Reject.
4. The Machine $N$ will accept reject for what decider accpet and accept what decider reject.
5. Now, Suppse we give input $<N>$ to $N$ itself, it will first create a copy $<N, N>$ and decider will halt and either accpet or reject.
6. If decider Rejecting then $N$ will Accept meaning decider is rejecting and $N$ does not accept the input $N$, BUt what Decider rejects $N$ accepts that means $N$ is accepted, so either decider does not exist or N.

---

1. $L =$ { $< M >$ | $L(M)$ is finite }  OR $L =$ { $< M >$ | $L(M)$ is infinite }
