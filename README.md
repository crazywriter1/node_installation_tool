# light_node_installation_tool
With that tool you can install your light node really easy


# Prerequisites:

This guide provides step-by-step instructions on how to install Golang version 1.20.2 on a Linux system. Golang, or Go, is an open-source programming language designed for simplicity, efficiency, and ease of use.

# Installation Steps:

### 1. Step
Connect to your server.

#### FAST SETUP 
```
cd $HOME
wget "https://golang.org/dl/go1.20.3.linux-amd64.tar.gz"
sudo rm -rf /usr/local/go
sudo tar -C /usr/local -xzf "go1.20.3.linux-amd64.tar.gz"
rm "go1.20.3.linux-amd64.tar.gz"
echo "export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin" >> $HOME/.bash_profile
source $HOME/.bash_profile
```

### Step 2 - Explanation
Navigate to the home directory by executing the following command:
`cd $HOME`

#### Explanation
Download the Golang installation package (`version 1.20.3` or `version 1.20.2`  if you prefer) for Linux by running the following command: `wget https://golang.org/dl/go1.20.3.linux-amd64.tar.gz`
 

#### Explanation
Remove any existing Golang installation from the /usr/local directory using the following command:
`sudo rm -rf /usr/local/go`

#### Explanation
Extract the downloaded Golang package to the /usr/local directory with the following command:
`sudo tar -C /usr/local -xzf "go1.20.3.linux-amd64.tar.gz"`

#### Explanation
Clean up the downloaded installation package by executing the following command:
`rm "go1.20.3.linux-amd64.tar.gz"`

#### Explanation
Update your $PATH environment variable to include the path to the Go binary files (typically /usr/local/go/bin) and the Go workspace's binary directory ($HOME/go/bin). To do this, add the following line to your shell's configuration file (e.g., ~/.bash_profile) by running the command:
`echo "export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin" >> $HOME/.bash_profile`

#### Explanation
Apply the changes to your current shell session by executing the following command:
`source $HOME/.bash_profile`



At this point, you have successfully installed Golang version 1.20.3 on your Linux system and updated the $PATH environment variable.

To verify your installation, run the following command:

`go version`

This command should display the installed Golang version, which should be "go1.20.3".


#  PLEASE CLONE THE REPO MAKE SURE YOU HAVE GIT ON YOUR SERVER

`git clone https://github.com/crazywriter1/light_node_installation_tool`

## Install Packages

`cd light_node_installation_tool` 

`go mod tidy`

## Run the Tool

`go run main.go`

### Installation Questions That You Will need to answer   with  Examples

1-) `Enter the IP address: <Your Ip Address>` 	135.181.45.156
  
2-) `Enter the port: 9090` 
 (default port)
 
3-)`Enter the network: blockspacerace`

# WARNING

## Please make sure you saved the key 

NAME: my_celes_key
ADDRESS: celestia1824ph5x5pgyt0pun57rn7uj0nvepx2gt9fsvat
MNEMONIC (save this somewhere safe!!!):
real snake ship month invest quality rigid script .......

## Node ID 


`AUTH_TOKEN=$(celestia light auth admin --p2p.network blockspacerace)`

```
curl -X POST \
     -H "Authorization: Bearer $AUTH_TOKEN" \
     -H 'Content-Type: application/json' \
     -d '{"jsonrpc":"2.0","id":0,"method":"p2p.Info","params":[]}' \
     http://localhost:26658
```
     
# Starting & Usefull Commands 

## Start

`cd celestia-node`

`systemctl enable celestia-lightd`

`systemctl start celestia-lightd` - start your node

`journalctl -u celestia-lightd.service -f`  - for logs if das - das - header/store its working

# Commands

`celestia version` - check your celestia version

`systemctl status celestia-lightd`  - check if your node running or not

`systemctl restart celestia-lightd` - restart your node

`systemctl stop celestia-lightd` - stop your node



# Congratulations, Celestia node has been successfully launched.

![WhatsApp Image 2023-05-14 at 19 05 26](https://github.com/crazywriter1/light_node_installation_tool/assets/53251494/bae3b367-16fb-4804-b4ec-17a8605ee9dd)








