The weird and wonderful world of bash completion


_foo()
{
    local cur=${COMP_WORDS[COMP_CWORD]}
    COMPREPLY=( $(compgen -W "alpha beta bar baz" -- $cur) )
}
complete -F _foo foo

make this a n00b friendly as possible because it took you ages to find a source that lead you through step by step in laymans terms
