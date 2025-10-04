# TJ Devries kickstart.nvim installation method in Linux.

This is a small tutorial for the installation method of kickstart.neovim in the linux
terminal, in the easiest manner possible. This will turn neovim into a full-fledged IDE that is just as advanced as any other IDE, but faster, along with the ability to modify it to suit your needs. It is totally setup for you to make it your own, with full instuctions on how to do so. There really is nothing any faster than this, assuming you have a basic understanding of Vim. If you don't, that's ok too. After installing this, you will also get a guided tour on how to use it. It will take practice, like anything else, if you don't already know some vim motions.

**Note**: All of the following commands should be entered in the terminal, in your home
directory. I highly recommend you read ths entire tutorial first before running any of the commands. It's not that long. All of the commands listed bellow are for Debian based distributions. If you are not on a Debian based distribution, you can change out the term " apt " with whatever package manager your system uses.

First, purge neovim from your system by typing the following command
into your terminal:

```bash
sudo apt-get purge neovim
```

This will purge any neovim dependencies that may be older and possibly conflict with
the install of the newest version of Neovim. As of the time of this writing, Debians (and Ubuntu) Advanced Package Tool (apt) will not download the latest version of Neovim.

Next, we need to install the latest version of Neovim. We will do this by
entering the following command into the terminal. This will setup the latest version of neovim on your system globally:

```bash
git clone https://github.com/neovim/neovim
```

Now you need to navigate into your new neovim directory.

```bash
cd neovim
```

Next you need to move to the stable branch of the repo:

```bash
git checkout stable
```

Next you need to run the following command to make sure all the proper tools and
packages are installed on your system:

```bash
sudo apt install build-essential cmake gettext
```

The following command will build neovim:

```bash
make CMAKE_BUILD_TYPE=RelWithDebInfo
```

And.....finally install Neovim to the latest stable version:

```bash
sudo make install
```

You can check the version by entering the command:

```bash
nvim -v
```

Next, enter the following command into your terminal that's going to
create a subdirectory in a hidden .config directory already on you system.
If the directory is not already there, the command will make one for you.
This is where the magic happens:

```bash
git clone https://github.com/nvim-lua/kickstart.nvim.git ~/.config/nvim
```

And that's all there is to it! Once all this is done, the next time you open Neovim
by entering the command " nvim " into the terminal, you will be opening a highly configured
Neovim IDE, but **_you have to close neovim and reopen it_** for the change to take place. It will take a few seconds to load all the configurations, maybe a minute or so depending on you system for this to setup. It is highly suggested that you go to the init.lua file, and read it.
You will need to search this file and uncomment the things you want, and then source the file after
you have uncommented the feature you want. For example, if you want linenumbers, and
relative numbers, you need to uncomment them in the .config/nvim/init.lua file, and then
save the changes and exit neovim. Then once you are back in the terminal, enter the following:

```bash
source ~/.config/nvim/init.lua
```

After you do that, when you open Neovim again you will have the feature you want; in this case
line numbers and relative line numbers. I would highly recommend this feature first to help in
navigation.

## After Note

Any contribution is welcomed, if you notice any mistakes please make a PR addressing it.

Thank you.
