# Short name mode enforce exmaple policy

Since Kubernetes 1.34 / OpenShift 4.21 the new default of `short-name-mode` is `enforcing`

```
% man 5 containers-registries.conf
   Short-Name Aliasing: Modes
       The short-name-mode option supports three modes to control  the  be‐
       haviour of short-name resolution.

       • enforcing:  If only one unqualified-search registry is set, use it
         as there is no ambiguity.  If there is more than one registry  and
         the  user  program  is running in a terminal (i.e., stdout & stdin
         are a TTY), prompt the user to select one of the specified  search
         registries.   If the program is not running in a terminal, the am‐
         biguity cannot be resolved which will lead to an error.

       • permissive: Behaves as enforcing but does not lead to an error  if
         the  program  is  not running in a terminal.  Instead, fallback to
         using all unqualified-search registries.

       • disabled: Use all unqualified-search registries without prompting.
```

More Resources:
 * [Breaking Change: Kubernetes 1.34 Tightens Image Name Resolution Rules — What It Means for You](https://www.replicated.com/blog/breaking-change-kubernetes-1-34-tightens-image-name-resolution-rules----what-it-means-for-you)
 * [Container image short names in Podman](https://www.redhat.com/en/blog/container-image-short-names)
 * [CRI-O PR: image pull: enforce shortnames#9401](https://github.com/cri-o/cri-o/pull/9401)


In [policy-short-name-mode-enforcing.yaml](./policy-short-name-mode-enforcing.yaml) is an example policy how to check your running pods.

![Screenshort](screenshot.png)