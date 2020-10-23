<!--
*** Thanks for checking out this README Template. If you have a suggestion that would
*** make this better, please fork the repo and create a pull request or simply open
*** an issue with the tag "enhancement".
*** Thanks again! Now go create something AMAZING! :D
***
***
***
*** To avoid retyping too much info. Do a search and replace for the following:
*** Arzanix, TheGamersAssociation, twitter_handle, email
-->





<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->


<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://github.com/Arzanix/TheGamersAssociation">
    <img src="Images/tga-discord.jpg" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">The Gamers Association Game Servers</h3>
  <h2 align="center">ARK SURVIVAL EVOLVED</h2>

  <p align="center">
    Repository to knowledge Ark players seeking to self host private Ark dedicated server on Linux(Ubuntu) without using third party libraries.
    <br />
    <a href="https://github.com/Arzanix/TheGamersAssociation"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    ·
    <a href="https://ark.gamepedia.com/ARK_Survival_Evolved_Wiki">Ark Wiki</a>
    ·
    <a href="https://github.com/Arzanix/TheGamersAssociation/issues">Request Feature</a>
  </p>
</p>



<!-- TABLE OF CONTENTS -->
## Table of Contents

* [About the Project](#about-the-project)
  * Created With 💖
* [Getting Started](#getting-started)
  * [Prerequisites](#prerequisites)
  * [Installation](#installation)
* [Usage](#usage)
* [Roadmap](#roadmap)
* [Contributing](#contributing)
* [License](#license)
* [Contact](#contact)
* [Acknowledgements](#acknowledgements)



<!-- ABOUT THE PROJECT -->
## TGA's Ark Servers
![Ark_BG](images/Ark-bg.jpg)

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
### Prerequisites

If using 64bit architecture Linux servers will require 32 bit binaries to install/run steamcmd

* Installing lib32gcc1
```sh
sudo apt-get install lib32gcc1
```

* [Screens](https://linuxize.com/post/how-to-use-linux-screen/)
```sh
sudo apt-get install screen
```

### Installation
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

_For more examples, please refer to the [Documentation](https://example.com)_



<!-- ROADMAP -->
## Roadmap

See the [open issues](https://github.com/Arzanix/TheGamersAssociation/issues) for a list of proposed features (and known issues).



<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to be learn, inspire, and create. Any contributions you make are **greatly appreciated**.

Project Link: [https://github.com/Arzanix/TheGamersAssociation](https://github.com/Arzanix/TheGamersAssociation)
Discord: https://discord.gg/yrvQBDf


<!-- ACKNOWLEDGEMENTS -->
## MODS

* [Structure Plus (S+))]()
* [Better Becon]()
* [Backpack]()
