# GitFlowPractice
## GitFlow工作流

> Vincent Driessen曾经写过一篇博文，题为 `A successful Git branching model`（一个成功的Git分支模型）。Gitflow工作流程就是从这篇文章里来的。
>
> Gitflow工作流程围绕项目发布定义了严格的分支模型。其特色在于，它为不同的分支分配了非常明确的角色，并且定义了使用场景和用法。除了用于功能开发的分支，它还使用独立的分支进行发布前的准备、记录以及后期维护。

<br/>

![GitFlow工作流图解](C:\Users\Administrator\Desktop\GitFlowPractice\Images\git-flow最终图.png)

<br/>

## 分支介绍

| 分支    | 作用                       |
| ------- | -------------------------- |
| master  | 历史迭代分支               |
| develop | 集成最新开发特性的活跃分支 |
| f_xxx   | feature 功能特性开发分支   |
| b_xxx   | bug 修复分支               |
| r_xxx   | release 版本发包分支       |

