```
function git_branch_name()
{
  branch=$(git symbolic-ref HEAD 2> /dev/null | awk 'BEGIN{FS="/"} {print $NF}')
  if [[ $branch == "" ]];
  then
    :
  else
    echo '('$branch')'
  fi
}

# Enable substitution in the prompt.
setopt prompt_subst

# Config for prompt. PS1 synonym.
prompt='%~ %F{green}$(git_branch_name)%f $ '
```

![image](https://github.com/user-attachments/assets/76f1254c-a2da-46bf-98d9-b95b69f768e5)
