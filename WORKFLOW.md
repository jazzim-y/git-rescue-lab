# Git Rescue Lab - Workflow

## Task 1: Bisect Finding
* **Bad Commit Hash:** c99fb42
* **Explanation:** The bug was caused because the code was checking the length of the items array (number of distinct products) instead of calculating the total quantity of items in the cart.

## Task 6: Workflow Questions

**1. Branching Strategy Recommendation**
For a small team of 4, I recommend GitHub Flow. I chose this because it is lightweight, keeps the main branch constantly deployable, and avoids the complicated "merge hell" that can happen with heavier strategies like Git Flow. It relies on short-lived feature branches which is perfect for a small, collaborative team.

**2. Removing the Secret from History**
To completely erase the `.env` file from all past commits, we would need to use a tool like `git filter-repo` or the older `git filter-branch`. This assignment didn't require that step because aggressively rewriting the entire repository's history alters all subsequent commit hashes. In a real-world scenario, this is highly destructive and will break the local repositories of any teammates who have already cloned the project, requiring careful team coordination to fix.

**3. Rewriting History**
It was acceptable to rewrite history in Task 2 because the "asdf" commit was only on my local machine and hadn't been shared yet. It would NOT be acceptable to rewrite a commit my teammates had already pulled because changing a commit creates a brand new commit hash. If teammates already have the old hash and I push a new one, it creates divergent timelines and massive merge conflicts (like the `non-fast-forward` error encountered when pushing).
