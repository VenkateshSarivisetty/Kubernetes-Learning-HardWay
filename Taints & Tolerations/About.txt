As a example, if a person standing and any
bug which is trying to stand on a person to
ich him.

For suppose if the person has a Taint, the bug
was not able to fall on him, in other way the
bug was not able to tolerate the taint.

However if the bug has a tolerance, it means
where bug has a taint which matches to person taint
it can easily fall on a person.

In Kubernetes, person is nodes and bug is pods
If any taint applied to node, none of the PODS
will get deployed into that node.

Whereas if any POD has a tolerant it can deployed
into that taint node.

Note: Tolerated Pod can able to deployed into Tainted Node
or any other nodes.


Master is default Tainted to not run any Pods, due to which
none of the pods were running in the master.

