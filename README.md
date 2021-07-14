# dotnet Core Application in LInux 

## Dotnet core is open source these days so hosting application in linux is possible and easy 

## PLatform 

<ol>
  <li>Ubuntu 20.04 OS </li>
  <li> Dotnet 3.x  </li>
</ol>


## Installing software in Ubuntu 20.04

## Step 1

```
sudo apt update 
sudo apt install wget -y
```

## step 2 -- Install package repository 

```
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

## step 3 -- Installing SDK 

```
sudo apt-get update
sudo apt-get install -y apt-transport-https
sudo apt-get update
sudo apt-get install -y dotnet-sdk-3.1
```

## checking dotnet version 

```
dotnet --version
```

##  creating sample application 

```
dotnet new webApp -o myWebApp --no-https
root@bdcfba4c6e6e:/myWebApp# cd /myWebApp/
root@bdcfba4c6e6e:/myWebApp# ls
Pages  Program.cs  Properties  Startup.cs  appsettings.Development.json  appsettings.json  bin  myWebApp.csproj  obj  wwwroot

```
## Building dotnet application 

```
cd myWebApp
dotnet build
```
### Output should be like this 

```
Build succeeded.
    0 Warning(s)
    0 Error(s)
    
```

### RUN dotnet application in Developer mode type 
## it will bound with localhost 

```
dotnet run
```

## Another application --- running method -- 0.0.0.0

```
dotnet watch run  --no-restore --urls http://0.0.0.0:5000
```

## another method to run dll file 

```
dotnet /myWebApp/bin/Debug/netcoreapp3.1/myWebApp.dll  --urls  http://0.0.0.0:5000
```

