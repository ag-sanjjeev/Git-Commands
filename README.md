# GIT Commands

This repository contains list of common and useful commands used in git system.

## &#9780; Overview:
1. [Introduction](./docs/introduction.md)
	- [Need for git](./docs/introduction.md#-need-for-git)
	- [Associated Files](./docs/introduction.md#-associated-files)
	- [Help Commands](./docs/introduction.md#-help-commands)
	- [Configurations](./docs/introduction.md#-configurations)
	- [Git LFS](./docs/introduction.md#-git-lfs)
	- [Security Practices](./docs/introduction.md#-security-practices)
2. [Git Ignore](./docs/git-ignore.md)
	- [How it works](./docs/git-ignore.md#-how-it-works)
	- [Ignore Specific Files](./docs/git-ignore.md#-ignore-specific-files)
	- [Ignore Specific Directories](./docs/git-ignore.md#-ignore-specific-directories)
	- [Wildcard Patterns](./docs/git-ignore.md#-wildcard-patterns)
	- [Comments](./docs/git-ignore.md#-comments)
	- [Testing Ignored Files](./docs/git-ignore.md#-testing-ignored-files)
	- [Global Ignore File](./docs/git-ignore.md#-global-ignore-file)
3. [Git Attributes](./docs/git-attributes.md)
	- [How it Works](./docs/git-attributes.md#-how-it-works)
	- [Text and Binary](./docs/git-attributes.md#-text-and-binary)
	- [End of Line](./docs/git-attributes.md#-end-of-line)
	- [Delta Compression](./docs/git-attributes.md#-delta-compression)
	- [Linguistic Language](./docs/git-attributes.md#-linguistic-language)
	- [Export Ignore](./docs/git-attributes.md#-export-ignore)
4. [Basic Repository Operations](./docs/basic-repository-operations.md)
	- [Initialize Repository](./docs/basic-repository-operations.md#-initialize-repository)
	- [Staging Area](./docs/basic-repository-operations.md#-staging-area)
	- [Restore](./docs/basic-repository-operations.md#-restore)
	- [Commit Changes](./docs/basic-repository-operations.md#-commit-changes)
	- [Check Status](./docs/basic-repository-operations.md#-check-status)
	- [View Commit Log](./docs/basic-repository-operations.md#-view-commit-log)
	- [Checkout](./docs/basic-repository-operations.md#-checkout)
5. [Branch Operations](./docs/branch-operations.md)
	- [Create Branch](./docs/branch-operations.md#-create-branch)
	- [List Branches](./docs/branch-operations.md#-list-branches)
	- [Switch Branch](./docs/branch-operations.md#-switch-branch)
	- [Move or Rename Branch](./docs/branch-operations.md#-move-or-rename-branch)
	- [Branching Strategies](./docs/branch-operations.md#-branching-strategies)
		- [Feature Branches](./docs/branch-operations.md#-feature-branches)
		- [Gitflow](./docs/branch-operations.md#-gitflow)
	- [Merge Branch](./docs/branch-operations.md#-merge-branch)
	- [Merge Conflicts](./docs/branch-operations.md#-merge-conflicts)
	- [Rebase](./docs/branch-operations.md#-rebase)
	- [Delete a Branch](./docs/branch-operations.md#-delete-a-branch)
6. [Remote Repository](./docs/remote-repository.md)
	- [Add Remote](./docs/remote-repository.md#-add-remote)
	- [Show Remote](./docs/remote-repository.md#-show-remote)
	- [Manipulate Remote](./docs/remote-repository.md#-manipulate-remote)
	- [Fetch Remote](./docs/remote-repository.md#-fetch-remote)
	- [Pull Remote](./docs/remote-repository.md#-pull-remote)
	- [Clone Repository](./docs/remote-repository.md#-clone-repository)
	- [Push Remote](./docs/remote-repository.md#-push-remote)
	- [Fork Repository](./docs/remote-repository.md#-fork-repository)
7. [Git Tags](./docs/git-tags.md)
	- [Types of Tags](./docs/git-tags.md#-types-of-tags)
	- [Creating Tags](./docs/git-tags.md#-creating-tags)
	- [Setting a Tag](./docs/git-tags.md#-setting-a-tag)
	- [Checkout a Tag](./docs/git-tags.md#-checkout-a-tag)
	- [Pushing a Tag](./docs/git-tags.md#-pushing-a-tag)
	- [Deleting a Tag](./docs/git-tags.md#-deleting-a-tag)
	- [Listing Tags](./docs/git-tags.md#-listing-tags)
	- [Show Tag Information](./docs/git-tags.md#-show-tag-information)
8. [Git Objects](./docs/git-objects.md)
	- [Blobs](./docs/git-objects.md#-blobs)
	- [Trees](./docs/git-objects.md#-trees)
	- [Commits](./docs/git-objects.md#-commits)
	- [Relation Between Objects](./docs/git-objects.md#-relation-between-objects)
9. [Git Reset](./docs/git-reset.md)
	- [Hard Reset](./docs/git-reset.md#-hard-reset)
	- [Soft Reset](./docs/git-reset.md#-soft-reset)
	- [Mixed Resets](./docs/git-reset.md#-mixed-resets)
	- [Resets with Merge](./docs/git-reset.md#-resets-with-merge)
	- [Resets with Keep](./docs/git-reset.md#-resets-with-keep)
	- [Allowed Commit References](./docs/git-reset.md#-allowed-commit-references)
11. [Git Submodules](./docs/git-submodules.md)
	- [How Submodule Works](./docs/git-submodules.md#-how-submodule-works)
	- [Add a Submodule](./docs/git-submodules.md#-add-a-submodule)
	- [Initialize a Submodule](./docs/git-submodules.md#-initialize-a-submodule)
	- [Update a Submodule](./docs/git-submodules.md#-update-a-submodule)
	- [Submodule Recursive](./docs/git-submodules.md#-submodule-recursive)
	- [Commit Submodule Changes](./docs/git-submodules.md#-commit-submodule-changes)
	- [Update Main Project](./docs/git-submodules.md#-update-main-project)
	- [Clone with Submodules](./docs/git-submodules.md#-clone-with-submodules)
	- [Pull Changes in Submodules](./docs/git-submodules.md#-pull-changes-in-submodules)
	- [Publishing Submodules Changes](./docs/git-submodules.md#-publishing-submodules-changes)
	- [Deleting Submodules](./docs/git-submodules.md#-deleting-submodules)
	- [Key Considerations](./docs/git-submodules.md#-key-considerations)
12. [Git Subtrees](./docs/git-subtrees.md)
	- [How Subtrees Work](./docs/git-subtrees.md#-how-subtrees-work)
	- [Adding a Subtree](./docs/git-subtrees.md#-adding-a-subtree)
	- [Pulling Changes](./docs/git-subtrees.md#-pulling-changes)
	- [Pushing Changes](./docs/git-subtrees.md#-pushing-changes)
	- [Squash](./docs/git-subtrees.md#-squash)
	- [Onto](./docs/git-subtrees.md#-onto)
	- [Strategy](./docs/git-subtrees.md#-strategy)
	- [Comparison](./docs/git-subtrees.md#-comparison)
13. [Advanced Commands](./docs/advanced-commands.md)
	- [Git Blame](./docs/advanced-commands.md#-git-blame)
	- [Git Cherry-Pick](./docs/advanced-commands.md#-git-cherry-pick)
	- [Git Reflog](./docs/advanced-commands.md#-git-reflog)
	- [Git Revert](./docs/advanced-commands.md#-git-revert)
	- [Git Stash](./docs/advanced-commands.md#-git-stash)

## &#9873; Contribution
Contributions are welcome! If you have any suggestions, bug reports, or feature requests, please open an issue or submit a pull request. Make sure to follow the existing coding style and provide clear documentation for your changes.

## &#9873; Disclaimer
This is not to be consider as official documentation. It is mainly provided for educational purpose. For better understanding, consult with expert and double check with [Official GIT Documentation](https://git-scm.com/doc), Before proceed in real-time implementations.

## &#9873; License
This reference licensed under the [MIT license](LICENSE). Feel free to use, modify, and distribute it as per the terms of the license.

## &#9873; Contact
If you have any questions or need further assistance, please feel free to reach me by referring [My Github Profile](https://github.com/ag-sanjjeev/)

Thanks for reviewing this reference notes!
