bash completion in k8s
---
 ~/.bashrc:
 
    source <(kubectl completion bash) 
    alias k=kubectl 
    complete -F __start_kubectl k
    
Apply settings:

    source ~/.bashrc
