# Aleo on docker

Login https://bit.ly/rentgpu

Click CLIENT > Create > Edit Image & Config...
Select Docker Image: `ubuntu:20.04`
![image](https://user-images.githubusercontent.com/102939807/208348128-183ddcbb-3e06-49d8-b0c2-c792559383ae.png)

SSH to the instance just created

Run commands below

`apt update -y; apt upgrade -y; apt install cron vim cmake curl libssl-dev libclang-dev git-all wget -y; curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- --profile default`

`source "$HOME/.cargo/env"; rustup update stable; apt install kmod nvidia-cuda-toolkit -y`

`# Check version`
`nvidia-smi`

`# Download damomine`
`wget https://github.com/damomine/aleominer/releases/download/damominer_linux_v2.0.0/damominer_linux_v2.0.0.tar`
`tar -xvf damominer_*.tar ; chmod +x damominer`
`# Run damonine`
`./damominer --address <aleoaddressxxxxxxxxxxxxxxxxxxxxx> --proxy aleo1.damominer.hk:9090 >> aleo.log 2>&1 &`
`# check log`
`tail -f aleo.log`

