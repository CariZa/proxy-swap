# Easily swap your terminal proxy

### Create a proxy bash file

```sh
sudo vim ~/.bash_proxy # Or nano if you MUST
```
##### Insert your proxy details

```text
export http_proxy='http://[USER]:[PASS]@[IP]:[PORT]/'
export https_proxy='http://[USER]:[PASS]@[IP]:[PORT]/'
# Then just echo into terminal so you know what's happening
echo "Using XYZ Proxy" 
```
##### Save that

### Create a proxy swap file

```sh
sudo vim ~/.bash_proxy_swap # Or nano if you ABSOLUTELY HAVE TO
```

##### Unset any proxy details that you have up and running

```text
unset http_proxy
unset https_proxy
# Then just echo into terminal so you know what's happening
echo "NO PROXY USED"
```

##### Save that

### Now for the NOT-SO-MAGIC

##### Open up your bash profile file

```sh
sudo vim ~/.bash_profile # Or nano if you HAVE NO OTHER POSSIBLE MEANS
```

##### Insert a alias for swapping your proxy, and also for importing the proxy file

```text
source ~/.bash_proxy
alias swap_proxy="mv ~/.bash_proxy ~/.bash_proxy.swp && mv ~/.bash_proxy_swap ~/.bash_proxy && mv ~/.bash_proxy.swp ~/.bash_proxy_swap && source ~/.bash_profile"
```

### Then just source your profile file again to adopt the changes

```sh
source ~/.bash_profile
```

### Now if you want to swap your proxy simply run: `swap_proxy` and you should see which proxy you are running
