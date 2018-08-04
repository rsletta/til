# Extract git commit messages since &lt;commit&gt;
To quickly get list of events. Usefull for release notes etc...

```git log --format=%B <commit hash>..HEAD > filename.ext```