git stash的使用场景： 当前分支下的某几个文件，前面的修改部分已经放在暂存区，目前在工作区还在进行修改，如果此时需要在当前文件下进行紧急修复bug，就需要把工作区正在修改的文件stash暂存起来，进行bug修复工作，在完成bug修复工作后，提交commit，将暂存的工作区文件内容拿出来继续工作。

恢复暂存时的状态有两种命令：
1. `git stash pop`
2. `git stash apply`

`git stash pop` 命令会在 stash 应用之后丢弃（默认情况下指的是最顶部的）stash，而 `git stash apply` 会将其保留在存储列表中，以备日后重用（或者您可以在之后使用 `git stash drop` 命令移除此 stash）。

除非 `git stash pop` 之后存在冲突，在这种情况下，它将不会删除该 stash，而使其行为与`git stash apply` 的命令完全相同。

### git stash apply + git stash drop
  `git stash apply` 和 `git stash drop` 是 Git 中用于处理储藏(stash)的两个不同命令。这两个命令的主要区别在于它们对储藏列表的处理方式。下面是对这两个命令以及它们之间关系的简单解释：

1. **`git stash apply`**:
    
    - `git stash apply` 命令用于应用储藏列表中的最新储藏，但不会从储藏列表中删除该储藏。
    - 你可以多次应用同一个储藏，因为它不会从储藏列表中被移除。
2. **`git stash drop`**:
    
    - `git stash drop` 命令用于从储藏列表中删除一个特定的储藏。
    - 通常在应用了一个储藏并确认更改后，你可能想要使用 `git stash drop` 来清理储藏列表。

如果你使用了 `git stash apply` 但没有使用 `git stash drop`，以下是可能发生的情况：

- 该储藏将继续保留在储藏列表中，即使你已经应用了它。这意味着储藏列表可能会随着时间的推移而变得越来越长，包含很多不再需要的储藏。

为了保持储藏列表的整洁，通常在应用储藏并确认更改无误后，你会使用 `git stash drop` 来删除不再需要的储藏。如果你想应用并立即从列表中删除储藏，你可以使用 `git stash pop` 命令，它是 `git stash apply` 和 `git stash drop` 的组合。
                                                 