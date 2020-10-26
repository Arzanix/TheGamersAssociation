# The Gamers Association

<img src="Images/tga-discord.jpg" align="left" hspace="50" vspace="10" width="100" height="100" >
<img src="Images/sep.png" align="left" width="25" height="100" >

Repository to knowledge Ark players seeking to self host private Ark dedicated server on Linux(Ubuntu) without using third party libraries.


<a href="https://ark.gamepedia.com/ARK_Survival_Evolved_Wiki">Ark Wiki</a> · <a href="https://github.com/Arzanix/TheGamersAssociation/issues">Request Feature</a>



<!-- ABOUT THE PROJECT -->
### Ark Survival Evolved Dedicated Server Installation

<!-- TGA OFFICIAL SERVERS -->
### TGA Clustered Server

* <img src="/Images/steam.png" width="50" height="50" /> | [Join Ragnarok](steam://connect/213.239.196.16:27015)

* <img src="/Images/steam.png" width="50" height="50" /> | [Join The Island](steam://connect/213.239.196.16:27017)

* <img src="/Images/steam.png" width="50" height="50" /> | [Join The Crystal Isles](steam://connect/213.239.196.16:27019)
<!-- GETTING STARTED -->
## Getting Started
Now before you start you may consider creating a new user, I am lazy therefore have continued with `root` user.

* Creating new `USER`
```sh
addusr <A-LOWERCASE-USERNAME>
```

* Logging in with your new user
```sh
sudo - <YOUR_USERNAME>
```


* Start by updating you distro update/kernel
```sh
sudo apt-get update && sudo apt-get -y upgrade
```
## Prerequisites
If using 64bit architecture Linux servers will require 32 bit binaries to install/run steamcmd

* Installing lib32gcc1
```sh
sudo apt-get install lib32gcc1
```

* [Screens](https://linuxize.com/post/how-to-use-linux-screen/)
```sh
sudo apt-get install screen
```

## Installation
The magic process :D

1. Lets make a new directory for steam commands.
```sh
mkdir steamcmd
```
2. Now lets change directory to the new one we have created (steamcmd)
```sh
cd steamcmd
```

3. Now lets download steam command.
```sh
sudo wget http://media.steampowered.com/installer/steamcmd_linux.tar.gz
```

4. Lets extract steamcmdcmd.linuxize.tar.gz using tar
```sh
sudo tar -xvzf steamcmd_linux.tar.gz
```
5. Verify you have all the files by executing this command.
[Compare](Images/tga1.png)
```sh
ls
```

6. Running steam commands to install server files.
```sh
sudo ./steamcmd.sh
```

7. Logging into `STEAM` as anonymous user
```sh
login anonymous
```

8. Server installation directory. This is where your server files will be including `CONFIG's`, `SAVES`, `MODS`
```sh
force_install_dir ../TGA
```
9. Lets start installing the server files. Arks app is `376030`.
```sh
app_update 376030 validate
```

* If you face issues downloading it or error relating to app "376030" failed to install then re execute this command.

10. Magic done now you may quit steam command.
```sh
quit
```

11. Now lets change directory to the server new directory.
```sh
cd ../TGA
```

 12. Creating server launch script.

 ```sh
 sudo vim startup.sh
 ```
Press `INSET` to start entering text.

 Paste this command in to your startup script. Replace <Map> with your desired map. Here is list of map names.
  `TheIsland`, `TheCenter` , `Ragnarok`, `CrystalIsles` ,
  `Extinction` `ScorchedEarth_P`, `Genesis`, `Aberration_P` , `Valguero_P`.

 ```sh
 ./ShooterGame/Binaries/Linux/ShooterGameServer Ragnarok?listen?SessionName=GameLab? -server -log
 ```

 Now to exit vim and save the changes pressing `ESC`  followed by a colon and `wq` to write and quit`:wq`.


+ If you execute the command `ls` you can see a new file called `startup.sh` and its currently not executable due to permissions. To set permissions for that file and execute it paste this the following command
```sh
sudo chmod +x startup.sh
```

<!-- USAGE EXAMPLES -->
## Usage

You are all set now and your new Ark server is ready for start-up, here is how you start up the servers.

1. Creating a new screen to run the server so we don't have to have our terminal open continually.
```sh
sudo screen -S MyArk
```

2. Running the server startup script
```sh
sudo ./startup.sh
```


## Game Configurations
Bare in mind that your file path will be different to this.
1. Linux path to Ark survival evolved config.
```sh
/Arzanix/Hosts/Ark/Ragnarok/ShooterGame/Saved/Config/LinuxServer
```

2. Windows path to Ark survival evolved config.
```sh
C:\Steam\steamapps\common\ARK\ShooterGame\Saved\Config\WindowsServer
```

* [Game](Configs/LinuxServer/Game.ini) - Game Files (Custom Map spawns etc..)
* [GameUserSettings](Configs/LinuxServer/GameUserSettings.ini) - Game User Settings  (Where server settings are placed such a Gathering, Taming etc..)


<!-- MODS -->
## Mods

Mods Folder Path, This is where you would manually transfer your mods too.
1. Linux path to Ark survival evolved config.
```sh
/Arzanix/Ragnarok/ShooterGame/Content/Mods
```

2. Windows path to Ark survival evolved config.
```sh
C:\Steam\steamapps\common\ARK\ShooterGame\Content\Mods
```
To browse other mods including popular ones you can visit [Ark Survival Evolved Steam Workshop](https://steamcommunity.com/app/346110/workshop/)

* [Classic Fly](https://steamcommunity.com/sharedfiles/filedetails/?id=895711211)
* [Structure Plus (S+))](https://steamcommunity.com/sharedfiles/filedetails/?id=731604991)
* [Better Beacon](https://steamcommunity.com/sharedfiles/filedetails/?id=506506101)
* [Backpack](https://steamcommunity.com/sharedfiles/filedetails/?id=736236773)


## Updating Game Server(s)
Generally it the same process as to install a new server, however `Steam Cmd` will go ahead
and start updating the sever.

1. Change your directory to `steamcmd`.
```sh
cd ../steamcmd
```

2. Executing steam script.
```sh
sudo ./steamcmd.sh
```

3. Loging in as anonymous.
```sh
login anonymous
```
4. The server path you wish to update. Be sure to check the path otherwise you are likely to install a new server
```sh
force_install_dir ../TGA
```

5. Finally lets start updating.
```sh
app_update 376030 validate
```






<!-- ROADMAP -->
## Roadmap
Coming Soon.
See the [open issues](https://github.com/Arzanix/TheGamersAssociation/issues) for a list of proposed features (and known issues).


<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to be learn, inspire, and create. Any contributions you make are **greatly appreciated**.

+ Discord: https://discord.gg/yrvQBDf

+ Project Link: [https://github.com/Arzanix/TheGamersAssociation](https://github.com/Arzanix/TheGamersAssociation)
