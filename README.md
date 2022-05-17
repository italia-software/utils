# utils
Utils to manage the italia-software organization

## Mass edit of the repos

You can use [multi-gitter](https://github.com/lindell/multi-gitter) to edit the
repos in one go and automatically create pull requests (or commit directly):

1. [Install multi-gitter](https://github.com/lindell/multi-gitter#install)
2. Clone this repo
3. Edit [script.sh](script.sh) with the changes you want to make
4. Run `multi-gitter` with `--dry-run` to check if everything is OK

   ```shell
   export COMMIT_MESSAGE="chore: my commit message"
   export BRANCH_NAME="my_branch_name" # name of the branch created for the pull request
   export GITHUB_TOKEN="ghp_mygithubtoken"

   multi-gitter run ./script.sh --dry-run -L debug -O italia-software -m "$COMMIT_MESSAGE" -B "$BRANCH_NAME" --token "$GITHUB_TOKEN"
   ```

5. Create the pull requests

   ```shell
   multi-gitter run ./script.sh --dry-run -L debug -O italia-software -m "$COMMIT_MESSAGE" -B "$BRANCH_NAME" --token "$GITHUB_TOKEN"
   ```

### Options

* Use `--fork` if you want to make a PR from a forked repo (if you don't have
  push permissions)
* `-s organization/repository` skips a repository, it can be used as many times
  you want
* Use `-R organization/repository` instead of `-O organization` if you want to
  list the single repositories. It can be used as many times you want
* Use `--skip-pr` and set the branch accordingly (`-B`) if you want to push directly,
  with no PR.

[Additional options](https://github.com/lindell/multi-gitter#-usage-of-run)
