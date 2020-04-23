# BASH Promt

Prompt with colored git branch status and command line in new line

```bash
 PS1='\[\033[0;33m\]\[\033[0m\033[0;33m\]\u\[\033[0;36m\] @ \[\033[0;36m\]\h  \w\[\033[0;33m\] ''$(git status &>/dev/null;\
if [ $? -eq 0 ]; then \
  echo "$(echo `git status` | grep "nothing to commit" > /dev/null 2>&1; \
  if [ "$?" -eq "0" ]; then \
    echo "\[\033[0;32m\]"$(__git_ps1 "(%s)"); \
  else \
    echo "\[\033[0;91m\]"$(__git_ps1 "{%s}"); \
  fi) "; \
else \
  echo ""; \
fi)'"\n\[\033[0;33m\]└─\[\033[0m\033[0;33m\] $\[\033[0m\033[0;33m\] ▶\[\033[0m\] "
```

