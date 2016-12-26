# A sample of `git rebase`

### Assumption

* Sample branches' status



```php
            /--- commit1--- commit2     `feature-1`
           /
*----*----*    `develop`
           \
            \--- commitA --- commitB    `feature-A`
```

* The changes in `feature-1` and `feature-A` have no conflicts

### Do a rebase

#### Case 1: On `feature-A`, rebase `feature-1`

`$ git checkout feature-A`    
`$ git rebase feature-1`
> First, rewinding head to replay your work on top of it...    
> Applying: commitA   
> Applying: commitB

 * Then the commit history will look like this:


```php
                                     /--- commitA --- commitB   `feature-A `
                                    /
            /--- commit1--- commit2   `feature-1`
           /
*----*----*   `develop`                   
```

#### Case 2: On `feature-1`, rebase `feature-A`

`$ git checkout feature-1`    
`$ git rebase feature-A`
> First, rewinding head to replay your work on top of it...    
> Applying: commit1   
> Applying: commit2 

 * Then the commit history will look like this:


```php
                                     /--- commit1 --- commit2   `feature-1 `
                                    /
            /--- commitA--- commitB   `feature-A`
           /
*----*----*   `develop`                   
```
