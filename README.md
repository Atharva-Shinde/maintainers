Parse OWNERS, OWNER_ALIASES in kubernetes/kubernetes then pull information from devstats:
https://k8s.devstats.cncf.io/d/13/developer-activity-counts-by-repository-group?orgId=1&var-period_name=Last%20year&var-metric=contributions&var-repogroup_name=All&var-repo_name=kubernetes%2Fkubernetes&var-country_name=All

and print the github id, pr comment count and devstats contribution count as well.

```
[dims@dims-m1 17:41] ~/go/src/k8s.io/k8s.io ⟩ ../maintainers/maintainers --help
Usage of ../maintainers/maintainers:
      --dryrun                       do not modify any files (default true)
      --repository-devstats string   defaults to "kubernetes/kubernetes" repository (default "kubernetes/kubernetes")
      --repository-github string     defaults to "kubernetes/kubernetes" repository (default "kubernetes/kubernetes")
      --skip-devstats                skip devstat contributions count check
      --skip-github                  skip github PR count check
```

Notes:
- Use `--dryrun=true` to update all the files
- You can specify the repositories from where to fetch the contribution or PR 
  comments using `--repository-devstats` or `--repository-github`
- If you want to skip either the devstats check or the github check use the corresponding flag, either
  `--skip-devstats` or `--skip-github`