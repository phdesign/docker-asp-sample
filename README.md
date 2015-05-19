# Docker sample

# To run locally

## 1. Install DNVM

In Powershell
```
&{$Branch='dev';iex ((new-object net.webclient).DownloadString('https://raw.githubusercontent.com/aspnet/Home/dev/dnvminstall.ps1'))}
```

## 2. Download DNX
```
dnvm upgrade
```
DNVM works by manipulating your path. When you install a runtime it downloads it and adds the path to the dnx binary to your `PATH`. After doing upgrade you should be able to run `dnvm list` and see an active runtime in the list.

You should also be able to run `dnx` and see the help text of the `dnx` command.

## 3. Install dependencies

From within the project folder
```
dnu restore
```

## 4. Run the project

###Windows
```
dnx . web
```
Test it's running by navigating to http://localhost:5001

###OS X / Linux
```
dnx . kestrel 
```
Test it's running by navigating to http://localhost:5004

# To run in docker

* Build: ```docker build -t phdesign/docker-asp-sample .```
* Run: ```docker run -t -d -p 1004:5004 phdesign/docker-asp-sample```
